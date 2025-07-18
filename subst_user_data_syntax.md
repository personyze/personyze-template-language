# Personyze: template language

Banners, product recommendations, and other Personyze actions are designed by visually editing their parameters.
However sometimes you may wish to do this by editing HTML source code.
Personyze uses regular HTML and CSS with additions that allow to create editable parts in the HTML template.

This guide explains the Personyze HTML template language.

## Preprocessing directives

Dollar-sign followed by braces designates a preprocessing directive, that will be evaluated and substituted with it's result before putting the HTML to the page.

Inside the braces there can be a variable or an expression.

## Preprocess-time variables

To create a preprocess-time variable, use `${menu}` directive at the end of the template, and one or more `${args}` inside the template.
For example here's how to create editable text:

```
<p title="${args->main_text:html}">
	${args->main_text}
</p>

${menu args->main_text name='Main text'}
```

In this example we created editable preprocess-time variable for "Main text".
GUI element will appear and let you change the text.
And this text will be inserted inside `<p>` tag. And also the same text will be put to "title" attribute of this tag.

Here's the syntax for argument expression: "args" keyword, arrow sign and the variable name.
Then 0 or more conversions may follow. Colon sign followed by function name creates the conversion for the variable.
In the example above there's "html" conversion that escapes HTML-special characters,
so the inserted text cannot break the HTML structure (cannot escape outside the attribute, and create another HTML tags).

## User profile variables

The templating language uses 2 levels of text processing. First, preprocess-time variables (arguments) are substituted.
Then user profile variables will be substituted for each user differently.

By default there are these profile variables:

- **first_name**
- **last_name**
- **email**
- **industry**

And you can add more user profile fields. Then you can collect values for those fields from the site (e.g. by offering the user to fill in a form).
And Personyze will substitute these variables in your templates.

To insert a variable, do:

```
${first_name:default('User')}
```

The first preprocessing step can produce variables for the second step. Example:

```
<p>
	${args->main_text:default('Dear, ${first_name:default(''User'')}')}
</p>

${menu args->main_text name='Main text'}
```

## Session and page variables

There're also variables that depend on browsing session.

- **url_host_port** - site domain name.
- **url_path** - URL path (part after the domain name).
- **ur** - The whole URL of the current page.
- **country_code** - 2-letter country code.
- **city** - City name.
- **lang_0** - Primary browser language.
- **known_device_type** - Contains one of 'regular' (desktop screen), 'tablet' or 'phone' (small screen).
- **is_returning_user** - 0 for new users and 1 for returning.
- **landing_url** - URL of landing page.
- **landing_host_port** - Domain part of landing page.
- **landing_path** - URL path part of landing page.
- **part_of_day()** - Contains one of: 'morning', 'afternoon', 'evening', 'night'.
- **weekday** - Weekday number: 0 - Sun, 1 - Mon, 2 - Tue, 3 - Wed, 4 - Thu, 5 - Fri, 6 - Sat
- **day** - Day of month
- **last_month_day** - Last day in current month. Can be 28, 29, 30 or 31.

## Functions that can be applied to variables

The syntax for functions is:

```
:func_name
```

or

```
:func_name(Parameter)
```

or

```
:func_name('Parameter')
```

or

```
:func_name('Parameter 1', 'Parameter 2', 'Parameter 3')
```

If the parameter contains commas or closing parenthesis, or if there are more than 1 parameter, it must be quoted.

Here are supported function names:

- **html** - escapes HTML-special characters. Converts `&` to `&amp;`, `"` to `&quot;`, `<` to `&lt;`.
- **default** - in `args` variables specifies the current value of the variable to which it will be substituted. If the same variable appears multiple times, `default` must be placed only near one of the occurances. In user profile variables this function specifies default variable value, i.e. text that will be printed if the variable is empty.
- **sprintf** - formats a text string. `${p->price:sprintf(Text before %s text after)}` - the value of `${p->price}` will be inserted into the format string in place of `%s`.
Use `%f` to format as number, and use `%[#,###.##]f` to specify thousands and decimal separators and number of digits in thousands group and in fraction (at most). `#` - optional digit, `0` - mandatory digit, so `%[#,###.00]f` for number `12.3` will produce `12.30`. To use arabic digits use `٠` instead of `0`, i.e. `%[#,##٠.##]f` for number `12.3` will produce `١٢.٣`. If you want to always include 2 digits after decimal point, even for whole numbers, do `%[#,###.00]f`. But if you want to include those 2 digits only for fractional numbers (e.g. 12.30), and not for whole numbers (12), use `g` specifier instead of `f`: `%[#,###.00]g`.
- **price** - Format number as price using number format defined in the account. You can have 2 predefined formats. Use `${p->price_after_discount:price}` for the default format, and `${p->price_after_discount:price('alternative')}` for the alternative one. GUI control will appear to let you change the format, and to save it for all templates.
- **json** - JSON-stringify the value. For example: `<button type="button" onclick="alert('Title: ' + ${p->title:json:html})">Show product title</button>`
- **url** - Encode characters that are special to URL. E.g. `?` to `%3F`.
- **round** - Round number.
- **floor** - Round number towards -Infinity.
- **ceil** - Round number towards +Infinity.
- **truncate** - Truncate number (throw away fractional part).
- **ellipsis** - Get first N characters from variable text, and cut off the rest. If there was the rest, an ellipsis sign is then appended. Example: `${p->description_long:ellipsis(50)}`.
- **left** - Get first N characters. Example: `${p->description_long:left(50)}`.
- **right** - Get last N characters.
- **replace** - Replace all occurances of one substring with another substring. Example: `${p->description_long:replace('http://', 'https://')}`.
- **regexp_replace** - replace text by regular expression.
- **lc** - Convert to lower case. Example: `${p->description_long:lc}`.
- **uc** - Convert to upper case.
- **substr** - Starting from character N extract M characters.
- **substring** - Extract substring starting from character N to character M exclusive.
- **text_after** - Extract text after specified word or substring.
- **text_before** - Extract text before specified word or substring.

## Inserting data from Personyze tables

Personyze allows to present data from products catalog, user interests, etc. Example:

```
${foreach products as p where p->price_after_discount < p->price_before_discount limit 5}
	<div>
		${p->title}
	</div>
${end}
```

This is used in product recommendations, where you can choose a recommendation algorithm, and corresponding table name and filters will appear in the template.

For example here is how best seller products are selected:

```
${foreach sum_products as p where p->for_period='recently' and p->n_goal>0 order by p->n_goal desc limit 12}
	...
${end}
```

There can be multiple `${foreach ...}` loops, and they can be nested.
If one of the loops has alias called `main`, then the GUI elements that allow to select recommendation algorith will controls this loop.
By default they will control the first found one.

## Currently viewing product

If product view event is reported on the current page, then details of the currently viewing product can be accessed through `viewing_product` keyword (without `${foreach}`).

```
You're interested in ${viewing_product->color} color.
```

Here're all automatically available tables:

- **viewing_product** - Currently viewing product.
- **last_viewed_product** - Last viewed product.
- **last_extra_product** - Last added to cart product.

## Conditional directives

### if

`${if ...}...${end}` directive allows to include a part of the template depending on some preprocess-time, or user profile variable, or a column from table.
It can also contain `${else if ...}...` and `${else}...` parts.
Example:

```
${foreach products as p where p->price_after_discount < p->price_before_discount limit 5}
	<div>
		${p->title}
	</div>
	<div>
		${if p->price_after_discount < p->price_before_discount}
			${p->price_after_discount}
			<strike>${p->price_before_discount}</strike>
		${else if p->price_after_discount < 10}
			Cheaper than $10.
		${else}
			${p->price_after_discount}
		${end}
	</div>
${end}
```

It's possible to use arguments in conditional expressions:

```
${foreach products as p where p->price_after_discount < p->price_before_discount limit 5}
	${if p->price_after_discount > args->min_price}
		<div>
			${p->title}
		</div>
	${end}
${end}

${menu args->min_price name='Show products not cheaper than', type='number'}
```

### case

Another conditional directive is `${case}...${end}`. It can be of 2 types: boolean and with expression to compare each branch with.

Example of boolean:

```
${case}
	${when known_device_type = 'phone'}
		On phone
	${when known_device_type = 'regular'}
		On desktop
	${else}
		Not known
${end}
```

Example of expression:

```
${case known_device_type}
	${when 'phone'}
		On phone
	${when 'regular'}
		On desktop
	${else}
		Not known
${end}
```

## Conditional blocks

Conditional blocks are HTML tags marked with `${block->block_name}` directive.
They have GUI element that allows to enable the block (to include it), and to disable it.

Example:

```
${block->with_button:default(0)}
<div>
	<button type="button">See more</button>
</div>

${menu block->with_button name='With button'}
```

## HTML structure of templates

There can be any structure. Template can contain any HTML tags, including `<style>`.

However Personyze substitutes some parts in the HTML structure.

If template has elements with `id` attributes these attributes are removed.

Any HTML tag can have `ontplready` attribute with piece of JavaScript that will be executed once the template is inserted into the document.
Within this JavaScript `this` variable will refer to the current element where `ontplready` is found.
Also there will be special variable called `by_id` that will contain references to all the elements that had `id` attribute (that was cut off).
Also `by_id` will be available in event handlers, like "onclick", etc.

```
<div style="background-color:transparent">
	<img id="main_icon" src="https://www.google.com/favicon.ico">
	<button type="button" onclick="alert(by_id.main_icon.width)">Get width</button>
</div>
```

In popup actions, if root element doesn't have `style` attribute with `background-color` explicitly defined, white background will be applied.

There're special class names. Elements that have such class names can be modified or substituted with different elements by the template engine.
These special class names start with a dollar-sign.

Special class names include: [$responsive](#responsive), [$btn](#btn), [$flat_btn](#flat_btn), [$personyze_button_dont_show_again](#personyze_button_dont_show_again),
[$a_add_params](#a_add_params), [$hint](#hint), [$icon](#icon), [$popup](#popup), [$switch-elem](#switch-elem), [$cform](#cform), `$info_lines_scroller`, `$rating`, `$table_slider`, `$table_slider_pagination`, `$button_add_to_cart`.

Special class names are removed from the "class" attribute.

## Recognized special classes

As noted above, HTML elements with special classes are processed by the template engine.

### $responsive

Usually the template root element has class `$responsive`.

```
<div class="$responsive" style="background-color:transparent">
	...
</div>
```

If the root element is `$responsive`, styles in this template can be written not only in `style` attribute, but also in `data-style`.
`data-style` attributes can use special syntax in CSS rules: `sel` function.

```
<div class="$responsive" data-style="background-color:transparent">
	<div data-style="max-width: sel(500px, 80%)">
		...
	</div>
</div>
```

And the template engine will select the best option from `sel` that causes less overflow.
It can select either the first option in all `sel` functions found in the template, or the second one for all (but not differently in each individual element).
Usually the first option is called "Desktop view", and the second one is called "Mobile view".

If the popup element doesn't fit the screen (is too large), and this template is `$responsive`, then the popup will be scaled down by applying `zoom`.

Note that when using `$responsive` regular `style` attributes and `<style>` tags can still be used, as usual.

### $btn

Applies to the element CSS style and behavior to turn this element to a button.

The button can have icon before the text. To specify the icon, use `data-icon="..."` attribute.
Icon name can be one of names found in "Font Awesome 4" icon library.

```
<a class="$btn" data-icon="bullhorn" href="javascript:" onclick="alert(this.dataset.message)" data-message="${args->message:html:default(Hello)}" style="text-decoration:none; padding:0.1em 0.3em">
	Show message
</a>

${menu name='Settings', icon='sliders'}
	${menu args->message name='Message text'}
```

Alternatively use `data-icon_append="..."` attribute to attach icon to the button after the text.

The button element will have the following javascript methods:

- `_set_disabled(value)` - Call with true argument to set "disabled" state for the button. Disabled buttons are dimmed and not clickable. Call with false to reset the disabled state.
- `_get_disabled()` - Get current disabled state (boolean).
- `_load_begin()` - Sets "loading" state for the button. Buttons in the loading state show spinner icon, and are not clickable.
- `_load_end()` - Call to reset the loading state.

```
<a class="$btn" data-icon="bullhorn" href="javascript:" onclick="this._load_begin(); setTimeout(() => {this._load_end(); alert(this.dataset.message)}, 1000)" data-message="${args->message:html:default(Hello)}" style="text-decoration:none; padding:0.1em 0.3em">
	Show message
</a>

${menu name='Settings', icon='sliders'}
	${menu args->message name='Message text'}
```

### $flat_btn

Like [$btn](#btn), but the button looks flat, and changes color on mouse hover.

To specify CSS style on mouse hover, use `data-hover_style="..."` attribute.

### $personyze_button_dont_show_again

When user clicks on the element, Personyze will hide the current action, and will not show it to this user again during specified number of sessions.

Current action ID must be provided in `data-action_id="..."` attribute (use `${action_id}` variable).

Attribute `data-n_sessions="..."` specifies the number of sessions.

```
<img src="https://counter.personyze.com/images/close-buttons/black-16x16.png" style="width:16px; height:16px" class="$personyze_button_dont_show_again" data-action_id="${action_id}" data-n_sessions="1">
```

Usually you'll use [${menu} item](#menu-items) with `type='dontshowagain'` to control how close button looks like.

```
<div class="$responsive" data-style="position:relative; overflow:hidden; ${args->box_style:html:default('max-width: 700px;
background-color: white;
')}">
	${block->show_close_button:default(1)}
	<div class="close-button-wrapper">
		${args->close_button:default('<div onmouseenter="this.style.backgroundColor=this.style.outlineColor" onmouseleave="this.style.backgroundColor=this.style.textDecorationColor" style="display: inline-block; vertical-align: text-bottom; width: 24px; height: 24px; box-sizing: border-box; border-radius: 50%; border: 0px solid; box-shadow: none; padding: 2px; background-color: rgba(0, 0, 0, 0); text-decoration-color: rgba(0, 0, 0, 0); outline-color: rgb(206, 54, 64); outline-width: 9px; color: rgb(10, 4, 4); cursor: pointer; transition: 0.3s;" class="$personyze_button_dont_show_again" data-action_id="${action_id}"><div style="display: block; width: 100%; height: 100%; transition: 0.3s; border-radius: 50%; background-image: linear-gradient(-45deg, transparent 0%, transparent 46%, currentcolor 46%, currentcolor 56%, transparent 56%, transparent 100%), linear-gradient(45deg, transparent 0%, transparent 46%, currentcolor 46%, currentcolor 56%, transparent 56%, transparent 100%);"></div></div>')}
	</div>
	<p>
		Text text text text text text text text text.
		Text text text text text text text text text.
		Text text text text text text text text text.
		Text text text text text text text text text.
	</p>
</div>

${menu name='Layout', icon='bars'}
	${menu args->box_style name='Box Style', type='css'}
${menu name='Close Button', icon='bars'}
	${menu block->show_close_button name='Show Close Button'}
	${menu args->close_button name='Close Button HTML', type='dontshowagain'}
```

### $a_add_params

If the root tag has this class, all the links (HTML `a` elements) in the template will be modified by adding URL parameters to them.
This can be useful for passing ad-tracking parameters.
Which parameters will be added is specified in `data-json-params="..."` attribute.
Use [${menu} item](#menu-items) with `type='external_media_url_params'` to create GUI element in the menu where you can specify the parameters.

```
<div class="$responsive $a_add_params" data-json-params="${args->url_params:html}">
	...
</div>

${menu name='Frame', icon='th-large'}
	${menu args->url_params name='URL additional parameters', type='external_media_url_params'}
```

### $hint

Allows to show tooltip on mouse hover.

The tooltip text is specified in `title="..."` attribute.

```
<a href="https://example.com/" class="$hint" title="Example">Link</a>
```

To include HTML in the tooltip, use nested element marked with `data-content="1"` attribute, instead of using `title="..."` attribute.

```
<a href="https://example.com/" class="$hint">
	<span data-content="1">
		This is <b>Example</b> site.
	</span>
	Link
</a>
```

You can apply CSS style to the tooltip popup by providing it in `data-popup_style="..."` attribute.

```
<a href="https://example.com/" class="$hint" data-popup_style="background-color:gold; color:purple; padding:1em">
	<span data-content="1">
		This is <b>Example</b> site.
	</span>
	Link
</a>
```

### $icon

Renders "Font Awesome 4" icon. The name of the icon is specified in the class attribute.

```
<i class="$icon envelope"></i>
```

OR:

```
<i class="$icon ${args->icon_name:html:default(envelope)}" style="font-size:125%; color:crimson"></i>

${menu args->icon_name name='Icon', type='icon'}
```

### $popup

Allows to show a popup element when the user clicks a button, or hovers some another element.

```
<div>
	<a href="javascript:" id="trigger_1">More info</a>
	<div class="$popup" data-trigger_id="trigger_1" style="max-width:10em; border:solid 1px; border-radius:5px; background-color:lightgreen; padding:1em">Blah blah blah blah blah blah blah.</div>
</div>
```

There a some attributes, that affect the popup behavior:

- `data-trigger_id="..."` id of element that triggers the popup.
- `data-trigger_onmouseover="1"` - if true, trigger the popup on mouse hover, rather than click.
- `data-trigger_onfocus="1"` - if the trigger is a text input field, the popup will be shown when the field gets focus.
- `data-is_modal="1"` - if true, the popup will be a modal dialog.
- `data-json-trigger_transit="..."` - specify one of `{"template": "animator_fade"}` or `{"template": "animator_swap_top"}` to set showing effect.

Example of modal dialog:

```
<div>
	<a href="javascript:" id="trigger_1">More info</a>
	<div id="popup_1" class="$popup" data-trigger_id="trigger_1" data-is_modal="1" data-json-trigger_transit='{"template": "animator_fade"}' style="max-width:10em; border:solid 1px; border-radius:5px; background-color:lightgreen; padding:1em">
		Blah blah blah blah blah blah blah.
		<div>
			<a href="javascript:" onclick="by_id.popup_1._hide()">Close</a>
		</div>
	</div>
</div>
```

### $switch-elem

Creates area where you can switch between different parts of HTML.

Element marked with this class can have 1 or more child elements, each marked with `data-case="case_name"` attribute, and only one of them will be shown at a time.
Also it's possible to show none of the cases.
Initial case is specified with `data-case="case_name"` on the switch itself, and then it's possible to switch to another case using JavaScript.

```
<div id="sw" class="$switch-elem" data-case="step-a" style="position:relative; overflow:hidden">
	<div data-case="step-a" style="width:15em; text-align:center; background-color:lightyellow">
		<p style="padding:2em">Step A.</p>
		<div style="padding:2em">
			<button class="$btn" data-icon_append="angle-right" onclick="by_id.sw._set_case('step-b', null, false, {template: 'animator_swap_bottom'})">Next</button>
		</div>
	</div>
	<div data-case="step-b" style="width:15em; text-align:center; background-color:purple; color:white">
		<p style="padding:2em">Step B.</p>
		<div style="padding:2em">
			<button class="$btn" data-icon="angle-left" onclick="by_id.sw._set_case('step-a', null, false, {template: 'animator_swap_top'})">Previous</button>
			<button class="$btn" data-icon_append="angle-right" onclick="by_id.sw._set_case('step-c', null, false, {template: 'animator_swap_bottom'})">Next</button>
		</div>
	</div>
	<div data-case="step-c" style="width:15em; text-align:center; background-color:teal; color:yellow">
		<p style="padding:2em">Step C.</p>
		<div style="padding:2em">
			<button class="$btn" data-icon="angle-left" onclick="by_id.sw._set_case('step-b', null, false, {template: 'animator_swap_top'})">Previous</button>
		</div>
	</div>
</div>
```

The element marked with `class="$switch-elem"` will have the following JavaScript methods:

- `_set_case(case_name)` - Switch to case. If `case_name` is `null`, will change to empty element.
- `_get_case()` - Get currently showing case.
- `_get_cases()` - Get all cases as array of strings.

### $cform

Allows to create a form that can send data to Personyze. You can use it to collect information about the user and his preferences.

Form must have name specified in the "class" attribute, together with "$cform". For example this `class="$cform form1"` creates form called "name1".
Input fields that belong to the form (the form will send them to Personyze) must be marked with `form="form_name"`.

Form element can have the following attributes:

- `data-required_field_message="Please fill out this field"` - Sets message that will be displayed near required field if sending the form with this field being empty.
- `data-invalid_value_message="Invalid value for this input"` - Sets message that will be displayed near field with invalid input.
- `ontplchange="..."` - JavaScript code that will be executed each time a form value changes.
- `ontplsubmit="..."` - JavaScript code that will be executed when the user submits the form (clicks on button `type="submit"` that belongs to the form). This method can reject the submission by returning anything except boolean true. If it accepts, it must do whatever is needed to submit the form. When submitted successfully, it must call `arguments[1]()`, and when submitted with error `arguments[2](error)`. To submit to Personyze do: `personyze.push(['Submit', '${action_id:html}', this._get_value_ex(), arguments[1], arguments[2]]); return true`.
- `ontplaftersubmit="..."` - JavaScript code that will be executed when `ontplsubmit` completed successfully (called `arguments[1]()`).

Example:

```
<div class="$cform form1" ontplsubmit="personyze.push(['Submit', '${action_id:html}', this._get_value_ex(), arguments[1], arguments[2]]); return true" ontplaftersubmit="alert('Success')">
	...
</div>
```

The form element will have the following JavaScript methods:

- `_get_value()` - Returns object with keys and values for each form input.
- `_get_value_ex()` - Returns object with keys and values as objects. For each input there will be object with "value" property that will contain the input value. Also input properties specified as attributes like `data-prop-prop_name="prop_value"` will be contained in the object.
- `_set_value(new_value)` - Sets the form value.

Form can contain text input fields, checkboxes, drop-down menues, and other HTML input elements.
They must have `form="form_name"` and `name="input_name"` attributes.
Also they can have the following attributes that will be handled by the form:

- `required="1"` - Makes the input required (the form cannot be submitted if this input is not filled in).
- `pattern="..."` - Regular expression to validate the input.
- `data-valid_if="..."` - JavaScript code that will be executed to validate the input. If it returns boolean true, then the value is considered to be ok. If boolean false - the value is invalid, and error message will be shown. Either the message set on the form element in `data-invalid_value_message="..."` attribute, or a default one. If the code returns string, this string will be shown as error message.
- `data-use_hidden="1"` - Normally, if the input is hidden (see about form cases below), it's value is not returned by `form._get_value()` or `form._get_value_ex()`. If you specify this attribute, the input will be included in the form value anyway.
- `data-value_if_hidden="..."` - like `data-use_hidden="1"`, but specifies predefined value that will be returned for this input if it's hidden.
- `data-prop-prop_name="prop_value"` - Inputs can have 0 or more property name/value pairs. They will appear in `form._get_value_ex()`. If you pass the value returned by `form._get_value_ex()` to `personyze.push(['Submit', action_id, value_ex, ...]`, then property called "column" will define to which user profile field on Personyze to store this input value.

```
<input form="form1" name="Email" pattern="[^\s@]+@[^\s@\.]+\.[^\s@]+" required="1" data-prop-column="email" value="${email:html}">
```

Also the form must have at least one submit button - a button that belongs to the form (`form="form_name"`) and has `type="submit"`.

```
<button form="form1" type="submit">Submit</button>
```

Form inputs and input groups can be visible or hidden depending on condition.

```
<div class="$cform form1" ontplsubmit="alert(JSON.stringify(this._get_value()))">
	<div>
		Name: <input form="form1" name="Name">
	</div>

	<label>
		<input form="form1" name="ContactMe" type="checkbox">
		Contact me back
	</label>

	<div form="form1" data-form_case="v.Name!='' && v.ContactMe">
		Phone: <input form="form1" name="Phone" type="tel">
	</div>

	<div>
		<button form="form1" type="submit">Submit</button>
	</div>
</div>
```

## Menu items

When you edit content on Personyze, there's visual editor that has parameters for various parts of the template.
Templating language defines both, the editable parts, and visual controls in the side menu for those parts.

It's possible to give a menu item a name and description, to group menu items in sections with specific order, etc.

The menu definition is found at the end of template HTML. It consists of `${menu}` directives.
There're 2 types of `${menu}` directives: for menu section, and for menu items in the section.

Here's how menu section directive looks like:

```
${menu name='Section name', icon='icon-name'}
```

It has 2 parameters:

- **name** - Text that appears in the GUI
- **icon** - (optional) Icon that also appears in the GUI. Icon name can be one of names found in "Font Awesome 4" icon library. Usually used icons: `image`, `envelope`, `user`, `check`, `times-circle`, `edit`, `font`, etc.

Menu item directive looks like the following:

```
${manu args->arg_name name='Argument name', description='Description...'}

OR:

${menu block->block_name name='Block name', description='Description...'}

OR:

${menu table_alias->column_name name='Column name', description='Description...'}
```

Menu item for argument allows to edit the value of the argument.

Menu item for block allows to switch the block on and off.

Menu item for table column allows to select different column name from drop down menu.

Example of items with sections:

```
${menu name='Text', icon='font'}
	${menu args->headline name='Headline Text'}
	${menu args->headline_style name='Headline Style', type='css'}
${menu name='Close Button', icon='times-circle'}
	${menu args->close_button_style name='Close Button Style', type='css'}
	${menu args->close_button name='Close Button HTML', type='dontshowagain'}
```

The default argument editor offers to edit the value in HTML editor, or in text input box (if this argument has `:html` function which means that this argument is not HTML-capable).
However you can choose specific value editor, for example drop-down menu with options, number editor (that allows to input only numbers), CSS editor (usually used for `style` attribute), etc.
Use `type` parameter to specify which editor to use.
In the example above there's a default editor for `args->headline`, and a CSS editor for `args->headline_style`.

## Field editor types

Some editor types accept parameters that modify their look and behavior.
Parameters are specified as zero or more `param=value` notations in the menu item specification, where the value can be a number, string, or JSON array.

Example:

```
${menu args->n_columns name='Number of columns', type='number', param='min=2', param='max=10', param='placeholder=Columns'}
```

### number

Show input that accepts only numbers. Possible parameters:

- **min** - Lowest possible value.
- **max** - Highest possible value.
- **placeholder** - Text prompt that appears within the input while it's empty.

Example:

```
${menu args->n_columns name='Number of columns', type='number', param='min=2', param='max=10', param='placeholder=Columns'}
```

### checkbox

Possible parameters:

- **value_on** - When checked, this value will be inserted to the template. Default: `1`.
- **value_off** - When unchecked, this value will be inserted to the template. Default: `0`.

Example:

```
<input name="email" ${args->email_required}>
${menu args->email_required name='Required Field', type='checkbox', param='value_on=required="1"', param='value_off=style="opacity:0.5"'}
```

### select

Shows drop-down menu with options.

Example:

```
${menu args->img_position name='Image Position', type='select', param='options=[["On Top","top"],["On Bottom","bottom"],["On Right Side","right"]]'}
```

### textarea

Shows multiline text input box.

Possible parameters:

- **placeholder** - Text prompt that appears within the input while it's empty.
- **autosize** - If is set to `1`, auto resize the box while user types.
- **autosize_max_rows** - Auto resize to at most this number of rows.

### css

Shows visual CSS editor. The produced result is a string for `style` attribute in HTML tags. It also can be used in `<style>` tags as part of CSS rules.

If `with_responsive=1` parameter is specified, will produce result for `data-style` attribute with `sel` functions.
If `$responsive` class is used on the root tag, you usually need to write styles in `data-style` attribute, and to add `with_responsive=1` to corresponding menu items.

Example:

```
${menu args->close_button_style name='Close Button Style', type='css', param='with_responsive=1'}
```

### color

Allows to edit CSS color.

Example:

```
<div style="background-color: ${args->color}">
	...
</div>

${menu args->color name='Background color', type='color'}
```
