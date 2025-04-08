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

- **html** - escapes HTML-special characters. Converts `&` to `&amp;`, `"` to `&quot;`, `<` to `&lt;`.
- **default** - specifies the current value of the variable to which it will be substituted. If the same variable appears multiple times, `default` must be placed only near one of the occurances.
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

Any HTML tag can have `ontplready` attribute with piece of Javascript that will be executed once the template is inserted into the document.
Within this Javascript `this` variable will refer to the current element where `ontplready` is found.
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

Usually the template root element has class `$responsive`.

```
<div class="$responsive" style="background-color:transparent">
	...
</div>
```

If the root element is `$responsive`, styles can be written not only in `style` attribute, but also in `data-style`.
`data-style` attributes can use special syntax in CSS rules: `sel` function.

```
<div class="$responsive" data-style="background-color:transparent">
	<div data-style="max-width: sel(500px, 80%)">
		...
	</div>
</div>
```

And the template engine will select the best option from `sel` that causes less overflow.
It can select either the first option in all `sel` function in the template, or the second one (but not differently on different elements).
Usually the first option is called "Desktop view", and the second one is called "Mobile view".

If the popup element doesn't fit the screen (is too large), and this template is `$responsive`, then the popup will be scaled down by applying `zoom`.

Note that when using `$responsive` regular `style` attributes and `<style>` tags can still be used, as usual.

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
- **icon** - (optional) Icon that also appears in the GUI. Icon name can be one of names from "Font Awesome 4". Usually used icons: `image`, `envelope`, `user`, `check`, `times-circle`, `edit`, `font`, etc.

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
${menu args->email_required name='Required Field', type='checkbox', param='value_on=required', param='value_off=style="opacity:0.5"'}
```

### select

Shows drop-down menu with options.

Example:

```
${menu args->img_position name='Image Position', type='select', param='options=[["On Top","top"],["On Bottom","bottom"],["On Right Side","right"]]'}
```

## textarea

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
