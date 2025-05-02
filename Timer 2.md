## Countdown Banner with Dual CTA & Custom Branding

Includes customizable background image, logo placement, editable title and message, animated countdown timer, and two clear CTA buttons:

```
<link href="https://fonts.googleapis.com/css?family=Arimo:400,700&display=swap" rel="stylesheet">
<div class="$responsive" data-style="position:relative; display:inline-block; min-width: 100%; background-color: ${args->framebgcolor:html:default('rgb(29, 59, 78)')}; ${args->style:html:default('display: table-cell;
width: auto;
height: 150px;
vertical-align: middle;
text-align: center;
border-radius: 10px;
background-size: cover;
background-repeat: no-repeat;
background-position: bottom;
background-image: url(''https://cdn.personyze.com/upload/362/5630c0948581ce13.jpeg'');
')} + ');')}">

  <!-- Close Button -->
  ${block->x:default(1)}
  <div style="position: absolute; top: 5px; right: 5px; cursor:pointer;">
    ${args->x:default('<a href="javascript:" style="font-size: 21px; color: rgb(255, 255, 255); text-decoration: none; background: rgba(255, 255, 255, 0.1); padding: 6px 12px; border-radius: 50%;" class="$personyze_button_dont_show_again" data-action_id="${action_id}">×</a>')}
  </div>

  <!-- Logo Block -->
  ${block->logo:default(1)}
  <div data-style="text-align:center; margin-bottom: 10px;">
    <img src="${args->logo_src:html:default('https://cdn.personyze.com/upload/362/836ce71c4644386c.png')}" data-style="${args->logo_style:html:default('padding: 0px; margin: 20px; max-width: 120px;')}" />
  </div>

  <!-- Title -->
  ${block->title:default(1)}
  <div data-style="${args->title_style:html:default('margin: 10px 20px; color: white; font-size: 26px; font-weight: bold; text-align: center; font-family: Arimo, sans-serif;')}">
    ${args->title_text:default(Countdown Begins Now)}
  </div>

  <div style="display:flex; flex-wrap:wrap; justify-content:center; align-items:center; gap: 15px; margin-top: 10px;">
    <!-- Left Text -->
    ${block->with_left_text:default(1)}
    <div data-style="${args->left_style:html:default('margin-top: 10px; margin-right: 20px; margin-bottom: 10px; margin-left: 20px; color: white; font-size: 18px; text-align: center; font-family: Arimo, sans-serif;')}">
      ${args->left_text:default('<strong>Limited Time Offer!</strong><br />Act fast before it ends.')}
    </div>

    <!-- Timer -->
    <div class="$timer_custom animate-pulse" data-action_id="${action_id:html}" data-json-value='{"start":{"type":"fixed_date","fixed_date_date":"1745020800"},"design":{"timer_background_style":"display: table-cell; white-space: nowrap; vertical-align: middle; text-align: center;","timer_box_style":"display: inline-block; text-align: center; margin: 0 6px; max-width: 100vw;","timer_caption_days":"Days","timer_caption_hours":"Hours","timer_caption_minutes":"Minutes","timer_caption_seconds":"Seconds","timer_caption_style":"color: white; font-size: 10pt; font-family: Arimo, sans-serif; font-weight: bold; text-transform: uppercase; margin-top: 5px;","timer_number_style":"color: white; font-size: 28pt; font-family: Oswald, sans-serif; font-weight: bold; line-height: 1em; background-color: #da3047; padding: 10px; min-width: 60px; box-sizing: border-box;"}}' data-style="${args->timersubstrate_style:html:default('margin: 10px 0px;')}"></div>

    <!-- CTA Button 1 -->
    ${block->button1:default(1)}
    <a ${args->href1:default('href="javascript:"')} data-style="display:inline-block; ${args->button1_style:html:default('margin: 10px 10px; font-size: 14px; color: #fff; text-decoration: none; background-color: #ff041d; padding: 12px 25px; border-radius: 25px; font-weight: 600; text-transform: uppercase; box-shadow: 0 4px 10px rgba(0,0,0,0.3); transition: transform 0.3s ease;')}" onmouseover="this.style.transform='scale(1.05)'" onmouseout="this.style.transform='scale(1)'"><span>${args->button1_text:default(REGISTER NOW)}</span></a>

    <!-- CTA Button 2 -->
    ${block->button2:default(1)}
    <a ${args->href2:default('href="javascript:"')} data-style="display:inline-block; ${args->button2_style:html:default('margin: 10px 10px; font-size: 14px; color: #fff; text-decoration: underline; background: transparent; padding: 12px 25px; border-radius: 25px; font-weight: 500; text-transform: uppercase;')}" onmouseover="this.style.opacity='0.8'" onmouseout="this.style.opacity='1'"><span>${args->button2_text:default(Maybe Later)}</span></a>
  </div>

  <!-- Optional Content -->
  ${block->content:default(0)}
  <div data-style="${args->content_style:html:default('padding: 15px;
color: white;
font-size: 16px;
text-align: center;
')}">
    ${args->content_text:default(FREE TEXT)}
  </div>
</div>

<!-- Menus -->

${menu name='Banner Settings', icon='th-large'}
	${menu args->framebgcolor name='Background color', type='color'}
	${menu args->style name='Banner CSS', type='css', param='with_responsive=1'}
${menu name='Logo Settings', icon='image'}
	${menu block->logo name='Show logo'}
	${menu args->logo_src name='Logo image URL', type='personyze_media_url'}
	${menu args->logo_style name='Logo style', type='css', param='with_responsive=1'}
${menu name='Title Block', icon='heading'}
	${menu block->title name='Show title'}
	${menu args->title_text name='Text'}
	${menu args->title_style name='Title style (CSS)', type='css', param='with_responsive=1'}
${menu name='Left Text', icon='align-left'}
	${menu block->with_left_text name='Show left text'}
	${menu args->left_text name='Text/HTML'}
	${menu args->left_style name='Left text style', type='css', param='with_responsive=1'}
${menu name='Timer Design', icon='paint-brush'}
	${menu args->timersubstrate_style name='Wrapper style', type='css', param='with_responsive=1'}
${menu name='CTA Button 1', icon='hand-pointer-o'}
	${menu block->button1 name='Show button 1'}
	${menu args->button1_text name='Text'}
	${menu args->href1 name='URL', type='a_attrs'}
	${menu args->button1_style name='Style', type='css', param='with_responsive=1'}
${menu name='CTA Button 2', icon='hand-o-up'}
	${menu block->button2 name='Show button 2'}
	${menu args->button2_text name='Text'}
	${menu args->href2 name='URL', type='a_attrs'}
	${menu args->button2_style name='Style', type='css', param='with_responsive=1'}
${menu name='Content Block', icon='file-text-o'}
	${menu block->content name='Show content block'}
	${menu args->content_text name='Text'}
	${menu args->content_style name='Style', type='css', param='with_responsive=1'}
${menu name='Close Button', icon='times'}
	${menu block->x name='Show close button'}
	${menu args->x name='Close button HTML', type='dontshowagain'}
```


## Modern Countdown Banner with Background Image and Registration CTA



```
<link href="https://fonts.googleapis.com/css?family=Arimo:400,700&display=swap" rel="stylesheet">
<div class="$responsive" data-style="position:relative; display:inline-block; min-width: 100%; background-color: ${args->framebgcolor:html:default('rgba(57, 49, 49, 0)')}; ${args->style:html:default('width: sel(100%, 100vw);
background-color: #0066ee;
background-image: url(''https://cdn.personyze.com/upload/362/440d445de06596d4.png'');
')}">

  <!-- Close Button -->
  ${block->x:default(1)}
  <div style="position: absolute; top: 5px; right: 5px; cursor:pointer;">
    ${args->x:default('<a href="javascript:" style="font-size: 24px; color: rgb(237, 233, 233); font-weight: lighter; line-height: normal; text-decoration: none; position: absolute; top: -4px; right: 6px;" class="$personyze_button_dont_show_again" data-action_id="${action_id}">×</a>')}
  </div>

  <!-- Logo Block -->
  ${block->logo:default(0)}
  <span>
    <img src="${args->logo_src:html}" data-style="${args->logo_style:html:default('padding: 0px; margin: 20px;')}">
  </span>

  <!-- Title Block -->
  ${block->title:default(0)}
  <div data-style="${args->title_style:html:default('margin: 10px 20px; color: white; font-size: 24px; text-align: center;')}">
    ${args->title_text:default(TITLE GOES HERE)}
  </div>

  <div style="display:flex; flex-wrap:wrap; justify-content:center; align-items:center">
    <!-- Left Text -->
    ${block->with_left_text:default(1)}
    <div data-style="${args->left_style:html:default('margin: 10px 20px; color: white; font-size: 24px; text-align: center; font-family: Montserrat, Helvetica, Arial, sans-serif;')}">
      ${args->left_text:default('<strong>THE CLOCK IS TICKING</strong><br><span style="font-size:20px;"> Starts Nov. 8 in NY</span>')}
    </div>

    <!-- Timer -->
    <div class="$timer_custom" data-action_id="${action_id:html}" data-json-value='{"start":${args->value:html:default('{"type":"fixed_date","fixed_date_date":"1762560000","fixed_date_timezone":"420","fixed_date_time":"28800","cookie_based_days":"0","cookie_based_hours":1,"cookie_based_minutes":1,"cookie_based_restart":0,"cookie_based_restart_after":"hours","cookie_based_restart_after_hours":"1","cookie_based_restart_after_weekday":"0","restart_everytime_days":"0","restart_everytime_hours":1,"restart_everytime_minutes":1,"timeup_action":"","timeup_message":"","timeup_message_style":""}')},"design":{"timer_separator":":","timer_separator_style":"min-width:auto","timer_background_style":${args->timer_background_style:json:html:default('display: table-cell;
white-space: nowrap;
vertical-align: middle;
text-align: center;
')},"timer_box_style":${args->timer_box_style:json:html:default('display: inline-block;
min-width: 36px;
margin: 0px;
background-color: rgba(246, 245, 245, 0);
border: 3px solid rgba(246, 245, 245, 0);
border-radius: 10px;
text-align: center;
color: rgb(250, 250, 250);
')},"timer_caption_days":${args->timer_caption_days:json:html:default(DAY)},"timer_caption_hours":${args->timer_caption_hours:json:html:default(HRS)},"timer_caption_minutes":${args->timer_caption_minutes:json:html:default(MIN)},"timer_caption_seconds":${args->timer_caption_seconds:json:html:default(SEC)},"timer_caption_style":${args->timer_caption_style:json:html:default('color: #fff;
font-size: 8pt;
font-family: Arial;
font-weight: bold;
')},"timer_number_style":${args->timer_number_style:json:html:default('color: white;
font-size: 26pt;
font-family: Arial;
font-weight: bold;
line-height: 1em;
margin-top: 15px;
')}}}' data-style="${args->timersubstrate_style:html:default('margin: 0 10px;')}"></div>

    <!-- CTA Button -->
    ${block->with_bottom_button:default(1)}
    <a ${args->bottom_href:default('href="#"')} data-style="display:inline-block; ${args->bottom_button_style:html:default('margin: 10px auto; padding: 2px 15px; font-size: 15px; font-weight: 600; background-color: #ff041d; color: #fff; border-radius: 25px; text-align: center; text-decoration: none; width: 130px; font-family: Montserrat, sans-serif;')}">
      ${args->bottom_button_text:default(REGISTER NOW)}
    </a>
  </div>

  <!-- Optional Content -->
  ${block->content:default(0)}
  <div data-style="${args->content_style:html:default('padding: 15px; color: white; font-size: 16px; text-align: center;')}">
    ${args->content_text:default(FREE TEXT)}
  </div>
</div>

<!-- Menus -->

${menu name='Frame', icon='th-large'}
	${menu args->framebgcolor name='Background color', description='Banner background color', type='color'}
	${menu args->style name='Custom CSS', description='Full CSS for the banner', type='css', param='with_responsive=1'}
${menu name='Close Button', icon='times'}
	${menu block->x name='Show close button'}
	${menu args->x name='Close button HTML', type='dontshowagain'}
${menu name='Logo', icon='image'}
	${menu block->logo name='Show logo'}
	${menu args->logo_src name='Logo URL', type='personyze_media_url'}
	${menu args->logo_style name='Logo style', type='css', param='with_responsive=1'}
${menu name='Title Block', icon='heading'}
	${menu block->title name='Show title'}
	${menu args->title_text name='Title text'}
	${menu args->title_style name='CSS style', type='css', param='with_responsive=1'}
${menu name='Left Text', icon='align-left'}
	${menu block->with_left_text name='Show text block'}
	${menu args->left_text name='HTML content'}
	${menu args->left_style name='Text style', type='css', param='with_responsive=1'}
${menu name='Timer', icon='clock-o'}
	${menu args->value name='Countdown settings', description='Configure countdown logic and behavior', type='timer_custom_params'}
	${menu args->timersubstrate_style name='Wrapper style', type='css', param='with_responsive=1'}
	${menu args->timer_background_style name='Timer background', type='css', param='with_responsive=1'}
	${menu args->timer_box_style name='Timer box', type='css', param='with_responsive=1'}
	${menu args->timer_number_style name='Number style', type='css', param='with_responsive=1'}
	${menu args->timer_caption_style name='Caption style', type='css', param='with_responsive=1'}
	${menu args->timer_caption_days name='Label: Days'}
	${menu args->timer_caption_hours name='Label: Hours'}
	${menu args->timer_caption_minutes name='Label: Minutes'}
	${menu args->timer_caption_seconds name='Label: Seconds'}
${menu name='CTA Button', icon='hand-pointer-o'}
	${menu block->with_bottom_button name='Show CTA button'}
	${menu args->bottom_button_text name='Button text'}
	${menu args->bottom_href name='Button URL', type='a_attrs'}
	${menu args->bottom_button_style name='Button style', type='css', param='with_responsive=1'}
${menu name='Content Block', icon='file-text-o'}
	${menu block->content name='Show extra text'}
	${menu args->content_text name='Text'}
	${menu args->content_style name='Text style', type='css', param='with_responsive=1'}
```


## Customizable Playful Countdown Banner with Animation Options

A fun countdown banner with customizable text, timer, and CTA button animations. Perfect for engaging promotions!

```
<div class="$responsive" data-style="position: relative; display: flex; flex-direction: column; align-items: center; padding: 20px; background: linear-gradient(135deg, #ffc3a0, #ffafbd); border-radius: 16px; flex-wrap: wrap; ${args->container_style:html}">

  <!-- Close Button -->
  ${block->x:default(1)}
  <div style="position: absolute; top: 10px; right: 10px; cursor: pointer;">
    ${args->x:default('<a href="javascript:" class="$personyze_button_dont_show_again" data-action_id="${action_id}" style="font-size: 24px; color: #fff; background: rgba(0,0,0,0.2); padding: 6px 12px; border-radius: 50%; text-decoration: none;">&times;</a>')}
  </div>

  <div style="display: flex; width: 100%; justify-content: space-between; align-items: center; flex-wrap: wrap;">
    <!-- Left Text Block -->
    ${block->with_left_text:default(1)}
    <div data-style="${args->left_style:html:default('color: #222; font-size: 28px; font-family: sans-serif; text-align: left; max-width: 300px;')}" style="flex: 1 1 auto;">
      ${args->left_text:default('<strong>Let the Countdown Begin!</strong><br><span style="font-size:18px; font-weight: normal;">Only days away from the fun!</span>')}
    </div>

    <!-- Optional Logo -->
    ${block->logo:default(1)}
    <div data-style="text-align:right; max-width: 150px;" style="flex: 0 0 auto;">
      <img src="${args->logo_src:html:default('https://cdn.personyze.com/upload/362/18a94c1299224ec8.png')}" data-style="${args->logo_style:html:default('width: 100%; max-width: 120px; border-radius: 12px;')}">
    </div>
  </div>

  <!-- Timer Block -->
  <div class="$timer_custom" data-action_id="${action_id:html}" data-json-value='{"start":${args->value:html:default('{"type":"fixed_date","fixed_date_date":"1762560000","fixed_date_timezone":"420","fixed_date_time":"28800","cookie_based_days":"0","cookie_based_hours":"","cookie_based_minutes":"","cookie_based_restart":0,"cookie_based_restart_after":"hours","cookie_based_restart_after_hours":"1","cookie_based_restart_after_weekday":"0","restart_everytime_days":"0","restart_everytime_hours":"","restart_everytime_minutes":"","timeup_action":"","timeup_message":"","timeup_message_style":""}')},"design":{"timer_separator":":","timer_separator_style":${args->timer_separator_style:json:html:default('display: flex;
align-items: center;
justify-content: center;
font-size: 28pt;
color: #ff69b4;
font-weight: bold;
text-align: center;
padding: 10px;
')},"timer_background_style":${args->timer_background_style:json:html:default('display: inline-flex;
text-align: center;
')},"timer_box_style":${args->timer_box_style:json:html:default('display: inline-block;
margin-right: 6px;
background-color: #fff;
color: #ff69b4;
border-radius: 12px;
padding: 10px;
font-family: sans-serif;
')},"timer_caption_days":${args->timer_caption_days:json:html:default(DAYS)},"timer_caption_hours":${args->timer_caption_hours:json:html:default(HOURS)},"timer_caption_minutes":${args->timer_caption_minutes:json:html:default(MINUTES)},"timer_caption_seconds":${args->timer_caption_seconds:json:html:default(SECONDS)},"timer_caption_style":${args->timer_caption_style:json:html:default('font-size: 10px;
color: #333;
font-weight: bold;
margin-top: 5px;
')},"timer_number_style":${args->timer_number_style:json:html:default('font-size: 24px;
font-weight: bold;
')}}}' data-style="${args->timersubstrate_style:html:default('margin: 20px 0;')}">
  </div>

  <!-- Buttons Block (Mobile Centered) -->
  <div style="display: flex; flex-direction: column; justify-content: center; align-items: center; width: 100%; text-align: center;">
  <!-- CTA Button 1 -->
  ${block->button1:default(1)}
  <a ${args->href1:default('href="#"')} data-style="${args->button1_style:html:default('font-size: 18px;
background-color: #ff69b4;
color: #fff;
padding-top: 12px;
padding-right: 24px;
padding-bottom: 12px;
padding-left: 24px;
border-radius: 30px;
text-decoration: none;
font-family: sans-serif;
box-shadow: 0 4px 10px rgba(0,0,0,0.2);
margin-top: 10px;
')} animation: ${args->button1_animation:html:default(shake)} 1.5s infinite;" onmouseover="this.style.opacity='0.9'" onmouseout="this.style.opacity='1'">
    ${args->button1_text:default('? Let’s Go!')}
  </a>

    <!-- CTA Button 2 -->
    ${block->button2:default(1)}
    <a ${args->href2:default('href="#"')} data-style="${args->button2_style:html:default('font-size: 14px; background: transparent; color: #ecf0f1; padding: 10px 20px; text-decoration: underline; font-family: Arial, sans-serif; margin-top: 10px; border-radius: 20px;')}" onmouseover="this.style.opacity='0.8'" onmouseout="this.style.opacity='1'">
      ${args->button2_text:default(Maybe Later)}
    </a>
  </div>

</div>
<!-- Bounce Animation CSS -->
<style>
@keyframes bounce {
  0%, 100% { transform: translateY(0); }
  50% { transform: translateY(-6px); }
}
@keyframes pulse {
  0%, 100% { transform: scale(1); }
  50% { transform: scale(1.05); }
}
@keyframes shake {
  0%, 100% { transform: translateX(0); }
  25% { transform: translateX(-4px); }
  75% { transform: translateX(4px); }
}
</style>
<!-- Menus -->

${menu name='Banner Settings', icon='th-large'}
	${menu args->container_style name='Extra container styles', type='css', param='with_responsive=1'}
${menu name='Left Text', icon='align-left'}
	${menu block->with_left_text name='Show left text'}
	${menu args->left_text name='Left text'}
	${menu args->left_style name='Left text style', type='css', param='with_responsive=1'}
${menu name='Countdown Timer', icon='clock-o'}
	${menu args->value name='Countdown logic', description='Set the countdown logic: fixed date, relative, or recurring', type='timer_custom_params'}
	${menu args->timersubstrate_style name='Wrapper style', type='css', param='with_responsive=1'}
	${menu args->timer_background_style name='Timer background', type='css', param='with_responsive=1'}
	${menu args->timer_box_style name='Timer box', type='css', param='with_responsive=1'}
	${menu args->timer_number_style name='Number style', type='css', param='with_responsive=1'}
	${menu args->timer_caption_style name='Caption style', type='css', param='with_responsive=1'}
	${menu args->timer_separator_style name='Colon style (:)', type='css', param='with_responsive=1'}
	${menu args->timer_caption_days name='Label: Days'}
	${menu args->timer_caption_hours name='Label: Hours'}
	${menu args->timer_caption_minutes name='Label: Minutes'}
	${menu args->timer_caption_seconds name='Label: Seconds'}
${menu name='CTA Button 1', icon='hand-pointer-o'}
	${menu block->button1 name='Show button'}
	${menu args->button1_text name='Button text'}
	${menu args->href1 name='URL', type='a_attrs'}
	${menu args->button1_style name='Style', type='css', param='with_responsive=1'}
	${menu args->button1_animation name='Animation type', description='Select an animation for the button or disable it', type='select', param='options=[["None",""],["Bounce","bounce"],["Pulse","pulse"],["Shake","shake"]]'}
${menu name='CTA Button 2', icon='hand-o-up'}
	${menu block->button2 name='Show second button'}
	${menu args->button2_text name='Button 2 text'}
	${menu args->href2 name='URL', type='a_attrs'}
	${menu args->button2_style name='Style', type='css', param='with_responsive=1'}
${menu name='Logo', icon='image'}
	${menu block->logo name='Show logo'}
	${menu args->logo_src name='Logo URL', type='personyze_media_url'}
	${menu args->logo_style name='Logo style', type='css', param='with_responsive=1'}
${menu name='Close Button', icon='times'}
	${menu block->x name='Show close button'}
	${menu args->x name='Close button HTML', type='dontshowagain'}
```


## Customizable Playful Countdown

This template offers a customizable background, text styles, timer design, and button styles.

```
<link href="https://fonts.googleapis.com/css2?family=Arimo:wght@400;700&family=Oswald:wght@500&display=swap" rel="stylesheet">
<div class="$responsive" data-style="position:relative; display:flex; flex-direction:column; align-items:center; justify-content:center; min-width:100%; padding: 2rem; background: linear-gradient(135deg, #e94e77 0%, #d14060 100%); border-radius: 16px; color: #fff; font-family: 'Arimo', sans-serif;">

  ${block->x:default(1)}
  <div style="position:absolute; top:10px; right:10px; cursor:pointer;">
    ${args->x:default('<div class="$personyze_button_dont_show_again" data-action_id="${action_id}" style="font-size: 24px; color: white;">×</div>
')}
  </div>

  ${block->title:default(1)}
  <h2 data-style="font-size: 2rem; margin-bottom: 0.5rem; text-align: center; font-family: 'Oswald', sans-serif;">
    ${args->title_text:default('? Huge Event Coming Soon')}
  </h2>

  ${block->left_text:default(1)}
  <p data-style="font-size: 1rem; margin-bottom: 1rem; text-align: center;">
    ${args->left_text:default('Don''t miss our limited-time offer. The clock is ticking!')}
  </p>

  <div class="$timer_custom" data-action_id="${action_id:html}" data-json-value='{
    "start": ${args->value:html:default('{"type":"fixed_date","fixed_date_date":"1745020800","fixed_date_timezone":"","fixed_date_time":"","cookie_based_days":"0","cookie_based_hours":"","cookie_based_minutes":"","cookie_based_restart":0,"cookie_based_restart_after":"hours","cookie_based_restart_after_hours":"0","cookie_based_restart_after_weekday":"0","restart_everytime_days":"0","restart_everytime_hours":"","restart_everytime_minutes":"","timeup_action":"","timeup_message":"","timeup_message_style":""}')},
    "design": {
      "timer_background_style": ${args->timer_background_style:json:html:default('display: flex;
gap: 10px;
justify-content: center;
')},
      "timer_box_style": ${args->timer_box_style:json:html:default('padding: 1rem;
background-color: rgba(255,255,255,0.1);
border-radius: 10px;
min-width: 60px;
text-align: center;
')},
      "timer_number_style": ${args->timer_number_style:json:html:default('font-size: 2rem;
font-weight: bold;
color: #fff;
text-align: center;
')},
      "timer_caption_style": ${args->timer_caption_style:json:html:default('font-size: 0.75rem;
text-align: center;
text-transform: uppercase;
margin-top: 5px;
color: #ffdede;
')},
      "timer_caption_days": ${args->timer_caption_days:json:html:default(Days)},
      "timer_caption_hours": ${args->timer_caption_hours:json:html:default(Hours)},
      "timer_caption_minutes": ${args->timer_caption_minutes:json:html:default(Minutes)},
      "timer_caption_seconds": ${args->timer_caption_seconds:json:html:default(Seconds)}
    }
  }' data-style="margin: 1rem 0;"></div>

  ${block->with_bottom_button:default(1)}
  <a ${args->bottom_href:default('href="#"')} data-style="display:inline-block; padding: 0.75rem 1.5rem; background-color: #ffffff; color: #e94e77; font-weight: bold; font-size: 1rem; border-radius: 30px; text-decoration: none; margin-top: 1rem; transition: background 0.3s; font-family: 'Arimo', sans-serif;">
    ${args->bottom_button_text:default(Reserve Your Spot)}
  </a>
</div>

${menu name='Title', icon='heading'}
	${menu block->title name='Show title'}
	${menu args->title_text name='Title text'}
${menu name='Subtitle', icon='comment'}
	${menu block->left_text name='Show subtitle'}
	${menu args->left_text name='Subtitle text'}
${menu name='Timer Settings', icon='clock-o'}
	${menu args->value name='Timer logic', description='Set the countdown logic (fixed/relative/recurring)', type='timer_custom_params'}
${menu name='Timer Styling', icon='paint-brush'}
	${menu args->timer_background_style name='Layout style', type='css'}
	${menu args->timer_box_style name='Box style', type='css'}
	${menu args->timer_number_style name='Number style', type='css'}
	${menu args->timer_caption_style name='Caption style', type='css'}
	${menu args->timer_caption_days name='Label: Days'}
	${menu args->timer_caption_hours name='Label: Hours'}
	${menu args->timer_caption_minutes name='Label: Minutes'}
	${menu args->timer_caption_seconds name='Label: Seconds'}
${menu name='CTA Button', icon='hand-pointer-o'}
	${menu block->with_bottom_button name='Show button'}
	${menu args->bottom_button_text name='Text'}
	${menu args->bottom_href name='Link', type='a_attrs'}
```


## Countdown with Clean Look

A sleek, modern countdown banner with logo, text, and call-to-action (CTA) buttons, designed for a professional and clean look.

```
<div class="$responsive" data-style="position: relative; display: flex; flex-direction: row; justify-content: space-between; align-items: center; padding: 20px 40px; background-color: #2c3e50; color: #ecf0f1; border-radius: 12px; min-width: 100%; ${args->container_style:html:default('padding-top: 20px;
padding-right: sel(40px, 10px);
padding-bottom: 20px;
padding-left: sel(40px, 10px);
')}">

  <!-- Close Button -->
  ${block->x:default(1)}
  <div style="position: absolute; top: 10px; right: 10px; cursor: pointer;">
    ${args->x:default('<a href="javascript:" style="font-size: 24px; color: rgb(255, 255, 255); background: rgba(0, 0, 0, 0.2); padding: 6px 12px; border-radius: 50%; text-decoration: none;" class="$personyze_button_dont_show_again" data-action_id="${action_id}">×</a>')}
  </div>

  <div style="display: flex; width: 100%; justify-content: space-between; align-items: center; flex-wrap: wrap;">
    <!-- Left Block (Logo and Text) -->
    <div style="display: flex; flex: 1 1 auto; justify-content: flex-start; gap: 20px; flex-wrap: wrap;">
      <!-- Logo -->
      ${block->logo:default(1)}
      <div data-style="flex: 0 0 auto; max-width: 120px; ${args->logo_visibility_mobile:html:default('display: block;')}">
        <img src="${args->logo_src:html:default('https://cdn.personyze.com/upload/362/18a94c1299224ec8.png')}" data-style="${args->logo_style:html:default('width: 100%;
max-width: 120px;
border-radius: 10px;
')}">
      </div>

      <!-- Text Block -->
      ${block->with_left_text:default(1)}
      <div data-style="${args->left_style:html:default('color: #fff; font-size: 22px; font-family: Arial, sans-serif; text-align: left; font-weight: 600; max-width: 300px;')}" style="flex: 1 1 auto;">
        ${args->left_text:default('<strong>Let the Countdown Begin!</strong><br><span style="font-size:18px; font-weight: normal;">Only days away from the fun!</span>')}
      </div>
    </div>

    <!-- Timer Block -->
    <div class="$timer_custom" data-action_id="${action_id:html}" data-json-value='{"start":${args->value:html:default('{"type":"fixed_date","fixed_date_date":"1762560000","fixed_date_timezone":"420","fixed_date_time":"28800","cookie_based_days":"0","cookie_based_hours":"","cookie_based_minutes":"","cookie_based_restart":0,"cookie_based_restart_after":"hours","cookie_based_restart_after_hours":"1","cookie_based_restart_after_weekday":"0","restart_everytime_days":"0","restart_everytime_hours":"","restart_everytime_minutes":"","timeup_action":"","timeup_message":"","timeup_message_style":""}')},"design":{"timer_separator":":","timer_separator_style":${args->timer_separator_style:json:html:default('display: flex;
align-items: center;
justify-content: center;
font-size: 28pt;
color: #ff69b4;
font-weight: bold;
text-align: center;
padding: 10px;
')},"timer_background_style":${args->timer_background_style:json:html:default('display: inline-flex;
text-align: center;
width: sel(441.71875px, 100%);
')},"timer_box_style":${args->timer_box_style:json:html:default('display: inline-block;
margin-right: 6px;
background-color: #fff;
color: #ff69b4;
border-radius: 12px;
padding: 10px;
font-family: sans-serif;
')},"timer_caption_days":${args->timer_caption_days:json:html:default(DAYS)},"timer_caption_hours":${args->timer_caption_hours:json:html:default(HOURS)},"timer_caption_minutes":${args->timer_caption_minutes:json:html:default(MINUTES)},"timer_caption_seconds":${args->timer_caption_seconds:json:html:default(SECONDS)},"timer_caption_style":${args->timer_caption_style:json:html:default('font-size: 10px;
color: #333;
font-weight: bold;
margin-top: 5px;
')},"timer_number_style":${args->timer_number_style:json:html:default('font-size: 24px;
font-weight: bold;
')}}}' data-style="${args->timersubstrate_style:html:default('margin: 20px 0;')}">
    </div>
  </div>

  <!-- Buttons Block (Mobile Centered) -->
  <div style="display: flex; flex-direction: column; justify-content: center; align-items: center; width: 100%; text-align: center;">
    <!-- CTA Button 1 -->
    ${block->button1:default(1)}
    <a ${args->href1:default('href="#"')} data-style="${args->button1_style:html:default('font-size: 18px; background-color: #2ecc71; color: #fff; padding-top: 12px; padding-right: 24px; padding-bottom: 12px; padding-left: 24px; border-radius: 30px; text-decoration: none; font-family: Arial, sans-serif; box-shadow: 0 4px 10px rgba(0,0,0,0.2); margin-top: 10px; animation: bounce 1.5s infinite;')}" onmouseover="this.style.opacity='0.9'" onmouseout="this.style.opacity='1'">
      ${args->button1_text:default('? Get Started')}
    </a>

    <!-- CTA Button 2 -->
    ${block->button2:default(1)}
    <a ${args->href2:default('href="#"')} data-style="${args->button2_style:html:default('font-size: 14px; background: transparent; color: #ecf0f1; padding: 10px 20px; text-decoration: underline; font-family: Arial, sans-serif; margin-top: 10px; border-radius: 20px;')}" onmouseover="this.style.opacity='0.8'" onmouseout="this.style.opacity='1'">
      ${args->button2_text:default(Maybe Later)}
    </a>
  </div>

</div>

<!-- Menus -->





































<!-- Bounce Animation CSS -->
<style>
@keyframes bounce {
  0%, 100% { transform: translateY(0); }
  50% { transform: translateY(-6px); }
}
</style>

${menu name='Banner Settings', icon='th-large'}
	${menu args->container_style name='Extra container styles', type='css', param='with_responsive=1'}
${menu name='Logo Settings', icon='image'}
	${menu block->logo name='Show logo'}
	${menu args->logo_src name='Logo URL', type='personyze_media_url'}
	${menu args->logo_style name='Logo style', type='css', param='with_responsive=1'}
	${menu args->logo_visibility_mobile name='Hide Logo on Mobile', description='Check to hide the logo on mobile devices', type='checkbox'}
${menu name='Left Text', icon='align-left'}
	${menu block->with_left_text name='Show left text'}
	${menu args->left_text name='Left text'}
	${menu args->left_style name='Left text style', type='css', param='with_responsive=1'}
${menu name='Countdown Timer', icon='clock-o'}
	${menu args->value name='Countdown logic', description='Set the countdown logic: fixed date, relative, or recurring', type='timer_custom_params'}
	${menu args->timersubstrate_style name='Wrapper style', type='css', param='with_responsive=1'}
	${menu args->timer_background_style name='Timer background', type='css', param='with_responsive=1'}
	${menu args->timer_box_style name='Timer box', type='css', param='with_responsive=1'}
	${menu args->timer_number_style name='Number style', type='css', param='with_responsive=1'}
	${menu args->timer_caption_style name='Caption style', type='css', param='with_responsive=1'}
	${menu args->timer_separator_style name='Colon style (:)', type='css', param='with_responsive=1'}
	${menu args->timer_caption_days name='Label: Days'}
	${menu args->timer_caption_hours name='Label: Hours'}
	${menu args->timer_caption_minutes name='Label: Minutes'}
	${menu args->timer_caption_seconds name='Label: Seconds'}
${menu name='CTA Button 1', icon='hand-pointer-o'}
	${menu block->button1 name='Show button'}
	${menu args->button1_text name='Button text'}
	${menu args->href1 name='URL', type='a_attrs'}
	${menu args->button1_style name='Style', type='css', param='with_responsive=1'}
${menu name='CTA Button 2', icon='hand-o-up'}
	${menu block->button2 name='Show second button'}
	${menu args->button2_text name='Button 2 text'}
	${menu args->href2 name='URL', type='a_attrs'}
	${menu args->button2_style name='Style', type='css', param='with_responsive=1'}
${menu name='Close Button', icon='times'}
	${menu block->x name='Show close button'}
	${menu args->x name='Close button HTML', type='dontshowagain'}
```


## Timer with optional pointing arrow



```
<style>
  @keyframes bounce {
    0%, 100% { transform: translateY(0); }
    50% { transform: translateY(-6px); }
  }
  @keyframes pulse {
    0%, 100% { transform: scale(1); }
    50% { transform: scale(1.05); }
  }
  @keyframes shake {
    0%, 100% { transform: translateX(0); }
    25% { transform: translateX(-4px); }
    75% { transform: translateX(4px); }
  }
</style>

<div class="$responsive" data-style="position:relative; display:flex; flex-direction:column; align-items:center; background-color: ${args->framebgcolor:html:default('rgba(29,59,78,0.95)')}; border-radius: 16px; padding: sel(20px, 16px); width: 100%; text-align: center; backdrop-filter: blur(5px); ${args->style:html:default('box-shadow: 0 0 10px rgba(0,0,0,0.3);
width: 950.171875px;
margin-top: 0;
margin-right: 0;
margin-bottom: 0;
margin-left: auto;
')}">

  <!-- Close Button -->
  ${block->x:default(1)}
  <div style="position: absolute; top: 10px; right: 10px; cursor: pointer;">
    ${args->x:default('<a href="javascript:" class="$personyze_button_dont_show_again" data-action_id="${action_id}" style="font-size: 24px; color: #fff; background: rgba(0,0,0,0.2); padding: 6px 12px; border-radius: 50%; text-decoration: none;">&times;</a>')}
  </div>

  <!-- Logo -->
  ${block->logo:default(1)}
  <div style="max-width: 140px;">
    <img src="${args->logo_src:html:default('https://cdn.personyze.com/upload/362/4c53a78c4a0882c4.png')}" data-style="${args->logo_style:html:default('width: 100%; max-width: 120px; border-radius: 12px;')}" />
  </div>

  <!-- Text -->
  ${block->with_left_text:default(1)}
  <div data-style="${args->left_style:html:default('margin: 10px 0; color: white; font-size: sel(22px, 16px); font-family: Arial, sans-serif;')}" style="max-width: 400px;">
    ${args->left_text:default('<strong>Time is Running Out!</strong><br><span style="font-size: sel(18px, 14px);">Don’t miss your chance to save!</span>')}
  </div>

  <!-- Timer -->
  <div class="$timer_custom" data-action_id="${action_id:html}" data-json-value='{
    "start": ${args->value:html:default('{"type":"fixed_date","fixed_date_date":"1745020800","fixed_date_timezone":"","fixed_date_time":"","cookie_based_days":"0","cookie_based_hours":"1","cookie_based_minutes":"1","cookie_based_restart":0,"cookie_based_restart_after":"hours","cookie_based_restart_after_hours":"1","cookie_based_restart_after_weekday":"0","restart_everytime_days":"0","restart_everytime_hours":"1","restart_everytime_minutes":"1","timeup_action":"","timeup_message":"","timeup_message_style":""}')},
    "design": {
      "timer_background_style": ${args->timer_background_style:json:html:default('display: flex; justify-content: center;')},
      "timer_box_style": ${args->timer_box_style:json:html:default('display: inline-block; background-color: #fff; color: #000; border-radius: 8px; padding: 10px; font-size: sel(18px, 12px); font-family: Arial, sans-serif; margin: 0 4px;')},
      "timer_caption_days": ${args->timer_caption_days:json:html:default(Days)},
      "timer_caption_hours": ${args->timer_caption_hours:json:html:default(Hours)},
      "timer_caption_minutes": ${args->timer_caption_minutes:json:html:default(Minutes)},
      "timer_caption_seconds": ${args->timer_caption_seconds:json:html:default(Seconds)},
      "timer_caption_style": ${args->timer_caption_style:json:html:default('color: #888; font-size: sel(10px, 7px); font-weight: bold;')},
      "timer_number_style": ${args->timer_number_style:json:html:default('font-size: sel(24px, 14px); font-weight: bold; color: #2c3e50;')}
    }
  }' data-style="${args->timersubstrate_style:html:default('margin: 20px 0;')}">
  </div>

  <!-- Buttons -->
  <div style="display:flex; flex-wrap:wrap; justify-content:center; gap: 10px;">
    ${block->button1:default(1)}
    <a ${args->href1:default('href="#"')} data-style="${args->button1_style:html:default('font-size: 16px;
background-color: #3498db;
color: #fff;
padding-top: 10px;
padding-right: 24px;
padding-bottom: 10px;
padding-left: 24px;
border-radius: 30px;
text-decoration: none;
font-family: Arial, sans-serif;
')}" style="animation: ${args->button1_animation:html:default(bounce)} 1.5s infinite;">
      ${args->button1_text:default(Join Now)}
    </a>

    ${block->button2:default(1)}
    <a ${args->href2:default('href="#"')} data-style="${args->button2_style:html:default('font-size: 14px;
background: transparent;
color: #eee;
text-decoration: underline;
padding-top: 10px;
padding-right: 20px;
padding-bottom: 10px;
padding-left: 20px;
font-family: Arial, sans-serif;
border-radius: 20px;
')}">
      ${args->button2_text:default(Maybe Later)}
    </a>
  </div>

  <!-- Arrow -->
  ${block->arrow:default(1)}
  <div data-style="position: absolute; border-color:${args->framebgcolor:html}; border-width:${args->arrow_size:html:default(20px)}; border-style:solid; width:0; height:0; ${args->arrow_side:html:default('top:100%; left:50%; transform:translateX(-50%); border-left-color:transparent; border-right-color:transparent; border-bottom-color:transparent;')}"></div>
</div>

${menu name='Banner Settings', icon='th-large'}
	${menu args->framebgcolor name='Background color', type='color'}
	${menu args->style name='Custom CSS', type='css', param='with_responsive=1'}
${menu name='Logo Settings', icon='image'}
	${menu block->logo name='Show logo'}
	${menu args->logo_src name='Logo image', type='personyze_media_url'}
	${menu args->logo_style name='Logo style', type='css', param='with_responsive=1'}
${menu name='Text Block', icon='align-left'}
	${menu block->with_left_text name='Show text block'}
	${menu args->left_text name='Text content'}
	${menu args->left_style name='Text style', type='css', param='with_responsive=1'}
${menu name='Timer', icon='clock-o'}
	${menu args->value name='Timer logic', type='timer_custom_params'}
	${menu args->timersubstrate_style name='Wrapper style', type='css', param='with_responsive=1'}
	${menu args->timer_background_style name='Timer background', type='css', param='with_responsive=1'}
	${menu args->timer_box_style name='Box style', type='css', param='with_responsive=1'}
	${menu args->timer_number_style name='Number style', type='css', param='with_responsive=1'}
	${menu args->timer_caption_style name='Caption style', type='css', param='with_responsive=1'}
	${menu args->timer_caption_days name='Label: Days'}
	${menu args->timer_caption_hours name='Label: Hours'}
	${menu args->timer_caption_minutes name='Label: Minutes'}
	${menu args->timer_caption_seconds name='Label: Seconds'}
${menu name='CTA Buttons', icon='hand-pointer-o'}
	${menu block->button1 name='Show button 1'}
	${menu args->button1_text name='Button 1 text'}
	${menu args->href1 name='Button 1 URL', type='a_attrs'}
	${menu args->button1_style name='Button 1 style', type='css', param='with_responsive=1'}
	${menu args->button1_animation name='Button animation', type='select', param='options=[["None",""],["Bounce","bounce"],["Pulse","pulse"],["Shake","shake"]]'}
	${menu block->button2 name='Show button 2'}
	${menu args->button2_text name='Button 2 text'}
	${menu args->href2 name='Button 2 URL', type='a_attrs'}
	${menu args->button2_style name='Button 2 style', type='css', param='with_responsive=1'}
${menu name='Arrow', icon='caret-down'}
	${menu block->arrow name='Show arrow'}
	${menu args->arrow_side name='Arrow side', type='select', param='options=[["Top","top:100%; left:50%; transform:translateX(-50%); border-left-color:transparent; border-right-color:transparent; border-bottom-color:transparent;"],["Bottom","bottom:100%; left:50%; transform:translateX(-50%); border-left-color:transparent; border-right-color:transparent; border-top-color:transparent;"],["Left","left:100%; top:50%; transform:translateY(-50%); border-top-color:transparent; border-bottom-color:transparent; border-right-color:transparent;"],["Right","right:100%; top:50%; transform:translateY(-50%); border-top-color:transparent; border-bottom-color:transparent; border-left-color:transparent;"]]'}
	${menu args->arrow_size name='Arrow size', type='css_length', param='with_responsive=1'}
```


## Timer-Based Email Capture Form with Dual CTA

A responsive email capture popup with a countdown timer, customizable call-to-action

```
<style>
  body, div, a, input, button, span {
    font-family: 'Montserrat', 'Open Sans', Arial, sans-serif;
  }

  @keyframes bounce {
    0%,100% { transform: translateY(0); }
    50% { transform: translateY(-6px); }
  }

  .form-container {
    background-image: url(${args->bgimage_url:html:default('https://cdn.personyze.com/upload/362/6413c369509b8110.jpeg')});
    background-size: cover;
    background-position: center;
    padding: 20px;
    border-radius: 10px;
    box-shadow: 0 0 10px rgba(0,0,0,0.4);
    position: relative;
    text-align: center;
    color: #fff;
  }

  .timer-block, .form-fields {
    margin-top: 15px;
  }

  .submit-button {
    background-color: #28a745;
    color: #fff;
    border: none;
    padding: 10px 20px;
    border-radius: 20px;
    font-weight: bold;
    cursor: pointer;
    transition: background-color 0.3s;
  }

  .submit-button:hover {
    background-color: #218838;
  }

  @media (max-width: 768px) {
    .form-container {
      padding: 15px;
    }
  }
</style>

<div class="$responsive" data-style="${args->box_style:html:default('background-image: url(''https://cdn.personyze.com/upload/362/5630c0948581ce13.jpeg'');
background-size: cover;
background-position: center;
padding-top: 20px;
padding-right: 2px;
padding-bottom: 20px;
padding-left: 2px;
border-radius: 10px;
box-shadow: 0 0 10px rgba(0,0,0,0.4);
position: relative;
text-align: center;
color: #fff;
width: 100%;
max-width: 600px;
height: auto;
')}">

  ${block->x:default(1)}
  <div style="position:absolute; top:10px; right:10px; cursor:pointer;">
    ${args->x:default('<a href="javascript:" style="font-size: 24px; color: rgb(255, 255, 255); text-decoration: none; position: absolute; right: 5px; top: 0px;" class="$personyze_button_dont_show_again" data-action_id="${action_id}">&times;</a>')}
  </div>

  <div class="$switch-elem" data-case="a">
    <form data-case="a" class="$cform st_f" id="st_f"
          ontplsubmit="personyze.push(['Submit', '${action_id:html}', this._get_value_ex(), arguments[1], arguments[2]]); return true"
          ontplaftersubmit="this.parentNode._set_case('b', null, false, {template: 'animator_fade'}); var js=this.dataset.customJs||''; if(js.trim()) new Function('action_id','by_id','data','report_error', js).call(this, '${action_id:html}', by_id, this._get_value()); var redir=this.dataset.redir, t=this.dataset.redirDelay|0, autoClose=this.dataset.autoClose|0; if (redir) setTimeout(function(){ location.href=redir }, t*1000); else if (autoClose) setTimeout(function(){ document.querySelector('[data-action_id=${action_id:html}]')?.click(); }, autoClose*1000);"
          data-redir="${args->redir:html}" data-redir-delay="${args->redir_delay:html}" data-auto-close="${args->auto_close_delay:html}" data-custom-js="${args->customjs:html}">

      <div data-style="${args->message_style:html:default('font-size: 24px;
font-weight: 600;
margin-bottom: 5px;
')}">
        ${args->message_text:default(Exclusive Offer!)}
      </div>

      <div data-style="${args->gift_style:html:default('font-size: 18px;
margin-bottom: 10px;
')}">
        ${args->gift_text:default(Sign up today and receive a special discount!)}
      </div>

      <div data-style="${args->timersubstrate_style:html:default('margin:15px 0;')}">
        <div class="$timer_custom" data-action_id="${action_id:html}" data-value='{"start":${args->value:html:default('{"type":"cookie_based","fixed_date_date":"","fixed_date_timezone":"","fixed_date_time":"","cookie_based_days":"3","cookie_based_hours":4,"cookie_based_minutes":1,"cookie_based_restart":0,"cookie_based_restart_after":"hours","cookie_based_restart_after_hours":"0","cookie_based_restart_after_weekday":"0","restart_everytime_days":"0","restart_everytime_hours":"","restart_everytime_minutes":"","timeup_action":"","timeup_message":"","timeup_message_style":""}')},"design":{"timer_separator":":","timer_separator_style":${args->timer_separator_style:json:html:default('font-size: 14px;
color: rgb(251, 247, 247);
background-color: rgba(225, 24, 24, 0.64);
margin-top: 10px;
margin-right: 0px;
margin-bottom: 0px;
margin-left: 0px;
height: auto;
')},"timer_box_style":${args->timer_box_style:json:html:default('display: inline-block;
padding: 5px;
background-color: #fff;
border-radius: 5px;
margin-top: 0;
margin-right: 5px;
margin-bottom: 0;
margin-left: 5px;
')},"timer_number_style":${args->timer_number_style:json:html:default('font-size: 20px;
font-weight: bold;
color: #333;
')},"timer_caption_style":${args->timer_caption_style:json:html:default('font-size: 10px;
color: #666;
')},"timer_caption_days":${args->timer_caption_days:json:html:default(Days)},"timer_caption_hours":${args->timer_caption_hours:json:html:default(Hours)},"timer_caption_minutes":${args->timer_caption_minutes:json:html:default(Minutes)},"timer_caption_seconds":${args->timer_caption_seconds:json:html:default(Seconds)}}}'></div>
      </div>

      <div style="margin-top:10px;">
        <input form="st_f" name="Email" type="email" required data-prop-column="email" data-style="${args->email_input_style:html:default('width: 40%;
padding: 10px;
margin-bottom: 10px;
border-radius: 5px;
border: 1px solid #ddd;
')}" placeholder="${args->email_placeholder:html:default(Enter your email)}">

        <button form="st_f" type="submit" data-style="${args->submit_button_style:html:default('background-color: #28a745;
color: #fff;
border: none;
padding-top: 11px;
padding-right: 20px;
padding-bottom: 11px;
padding-left: 20px;
border-radius: 5px;
font-weight: bold;
cursor: pointer;
transition: background-color 0.3s;
')}" hover_style="${args->submit_button_hover_style:html:default('background-color:#218838;')}">
          ${args->button_caption:default(Subscribe Now)}
        </button>

        ${block->maybe_later:default(1)}
        <div style="margin-top:10px;">
          <a ${args->maybe_later_link:default('href="javascript:" class="$personyze_button_dont_show_again" data-action_id="${action_id}" data-n_sessions="0"')} data-style="${args->maybe_later_style:html:default('color: #eee;text-decoration: underline;font-size: 14px;')}" role="button">
            ${args->maybe_later_text:default(Maybe Later)}
          </a>
        </div>
      </div>
    </form>

    <div data-case="b" id="st_b">
      ${args->success:default(Thank you for subscribing!)}
    </div>
  </div>
</div>

${menu name='Banner Settings', icon='th-large'}
	${menu args->box_style name='Container Style', description='Overall style for the popup container', type='css', param='with_responsive=1'}
${menu name='Main Message', icon='comment'}
	${menu args->message_text name='Main Message Text'}
	${menu args->message_style name='Main Message Style', description='CSS styling for the main heading', type='css', param='with_responsive=1'}
${menu name='Gift Message', icon='gift'}
	${menu args->gift_text name='Gift Message Text'}
	${menu args->gift_style name='Gift Message Style', description='CSS styling for the subheading', type='css', param='with_responsive=1'}
${menu name='Timer Settings', icon='clock-o'}
	${menu args->value name='Countdown Logic', type='timer_custom_params'}
	${menu args->timersubstrate_style name='Timer Wrapper Style', description='Style for the timer container', type='css', param='with_responsive=1'}
	${menu args->timer_box_style name='Box Style', description='Style for each timer box', type='css', param='with_responsive=1'}
	${menu args->timer_number_style name='Number Style', description='Style for timer digits', type='css', param='with_responsive=1'}
	${menu args->timer_caption_style name='Caption Style', description='Style for the labels (Days, Hours)', type='css', param='with_responsive=1'}
	${menu args->timer_separator_style name='Colon Style (:)', description='Style for the colon (:) between digits', type='css', param='with_responsive=1'}
	${menu args->timer_caption_days name='Label: Days'}
	${menu args->timer_caption_hours name='Label: Hours'}
	${menu args->timer_caption_minutes name='Label: Minutes'}
	${menu args->timer_caption_seconds name='Label: Seconds'}
${menu name='Email Input', icon='envelope'}
	${menu args->email_placeholder name='Email Placeholder'}
	${menu args->email_input_style name='Email Input Style', description='Style for the email input field', type='css', param='with_responsive=1'}
${menu name='Submit Button', icon='check'}
	${menu args->button_caption name='Submit Button Text'}
	${menu args->submit_button_style name='Submit Button Style', type='css', param='with_responsive=1'}
	${menu args->submit_button_hover_style name='Submit Button Hover Style', type='css', param='with_responsive=1'}
${menu name='Maybe Later CTA', icon='hand-o-up'}
	${menu block->maybe_later name='Show Maybe Later Button'}
	${menu args->maybe_later_text name='Button Text'}
	${menu args->maybe_later_link name='Button Link', type='a_attrs'}
	${menu args->maybe_later_style name='Button Style', type='css', param='with_responsive=1'}
${menu name='After Submit', icon='check-circle'}
	${menu args->success name='Success Message'}
	${menu args->customjs name='Custom JavaScript'}
	${menu args->redir name='Redirect URL'}
	${menu args->redir_delay name='Redirect Delay (sec)', type='number'}
	${menu args->auto_close_delay name='Auto Close Delay (sec)', type='number'}
${menu name='Close Button', icon='times'}
	${menu block->x name='Enable Close Button'}
	${menu args->x name='Close Button HTML', type='dontshowagain'}
```


## Responsive Countdown Form with Required Fields

Lead capture form with editable container, working countdown timer, required field toggles, checkbox consent, and redirect/success logic. All fields are styled and validated.

```
<!-- Form Template with Fixed Required Toggles and HTML Note Editor -->

<style>
  body, div, a, input, button, span, textarea, select {
    font-family: 'Montserrat', 'Open Sans', Arial, sans-serif;
  }
  .form-container {
    background-image: url(${args->bgimage_url:html:default('https://cdn.personyze.com/upload/362/6413c369509b8110.jpeg')});
    background-size: cover;
    background-position: center;
    padding: 20px;
    border-radius: 10px;
    box-shadow: 0 0 10px rgba(0,0,0,0.4);
    position: relative;
    text-align: center;
    color: #fff;
  }
  .form-fields input,
  .form-fields select,
  .form-fields textarea {
    display: block;
    width: 90%;
    max-width: 400px;
    margin: 10px auto;
    padding: 10px;
    border: 1px solid #ccc;
    border-radius: 6px;
    font-size: 14px;
  }
  .form-fields input[type="checkbox"] {
    width: auto;
  }
  .form-fields .checkbox-wrapper {
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 8px;
    margin: 12px auto 8px auto;
    max-width: 400px;
  }
  .checkbox-note {
    font-size: 12px;
    color: #ccc;
    text-align: center;
    margin-top: 4px;
  }
  .submit-button {
    background-color: #28a745;
    color: #fff;
    border: none;
    padding: 10px 25px;
    border-radius: 20px;
    font-weight: bold;
    cursor: pointer;
    transition: background-color 0.3s;
    margin-top: 15px;
  }
  .submit-button:hover {
    background-color: #218838;
  }
  @media (max-width: 768px) {
    .form-container {
      padding: 15px;
    }
    .form-fields input,
    .form-fields select,
    .form-fields textarea {
      width: 95%;
    }
  }
</style>

<div class="$responsive" data-style="${args->box_style:html:default('background-image: url(''https://cdn.personyze.com/upload/362/ace46de3a2bab43a.png'');
background-size: cover;
background-position: center;
padding-top: 40px;
padding-right: 1px;
padding-bottom: 20px;
padding-left: 1px;
border-radius: 10px;
box-shadow: 0 0 10px rgba(0,0,0,0.4);
position: relative;
text-align: center;
color: #fff;
width: 100%;
max-width: 500px;
height: auto;
')}">
  ${block->x:default(1)}
  <div style="position:absolute; top:10px; right:10px; cursor:pointer;">
    ${args->x:default('<a href="javascript:" style="font-size: 24px; color: rgb(255, 255, 255); text-decoration: none; position: absolute; right: 5px; top: 0px;" class="$personyze_button_dont_show_again" data-action_id="${action_id}">×</a>')}
  </div>
  <div class="$switch-elem" data-case="a">
    <form data-case="a" class="$cform st_f" id="st_f"
          ontplsubmit="personyze.push(['Submit', '${action_id:html}', this._get_value_ex(), arguments[1], arguments[2]]); return true"
          ontplaftersubmit="this.parentNode._set_case('b', null, false, {template: 'animator_fade'}); var js=this.dataset.customJs||''; if(js.trim()) new Function('action_id','by_id','data','report_error', js).call(this, '${action_id:html}', by_id, this._get_value()); var redir=this.dataset.redir, t=this.dataset.redirDelay|0, autoClose=this.dataset.autoClose|0; if (redir) setTimeout(function(){ location.href=redir }, t*1000); else if (autoClose) setTimeout(function(){ document.querySelector('[data-action_id=${action_id:html}]')?.click(); }, autoClose*1000);"
          data-redir="${args->redir:html}" data-redir-delay="${args->redir_delay:html:default(55)}" data-auto-close="${args->auto_close_delay:html:default(80)}" data-custom-js="${args->customjs:html}">

      <div data-style="${args->message_style:html:default('font-size: 24px;
font-weight: 600;
margin-bottom: 5px;
')}">
        ${args->message_text:default(Exclusive Offer!)}
      </div>
      <div data-style="${args->gift_style:html:default('font-size: 18px;
margin-bottom: 10px;
')}">
        ${args->gift_text:default(Sign up today and receive a special discount!)}
      </div>

      <!-- Timer (do not modify) -->
      <div data-style="${args->timersubstrate_style:html:default('margin:15px 0;')}">
        <div class="$timer_custom" data-action_id="${action_id:html}" data-value='{"start":${args->value:html:default('{"type":"cookie_based","cookie_based_days":"3","cookie_based_hours":"4","cookie_based_minutes":"1"}')},"design":{"timer_separator":":","timer_separator_style":${args->timer_separator_style:json:html:default('font-size: 14px; color: rgb(251, 247, 247); background-color: rgba(225, 24, 24, 0.64); margin-top: 10px;')},"timer_box_style":${args->timer_box_style:json:html:default('display:inline-block;padding:5px;background-color:#fff;border-radius:5px;margin:0 5px;')},"timer_number_style":${args->timer_number_style:json:html:default('font-size:20px;font-weight:bold;color:#333;')},"timer_caption_style":${args->timer_caption_style:json:html:default('font-size:10px;color:#666;')},"timer_caption_days":${args->timer_caption_days:json:html:default(Days)},"timer_caption_hours":${args->timer_caption_hours:json:html:default(Hours)},"timer_caption_minutes":${args->timer_caption_minutes:json:html:default(Minutes)},"timer_caption_seconds":${args->timer_caption_seconds:json:html:default(Seconds)}}}'></div>
      </div>

      <div class="form-fields">
        <!-- Inputs -->
        <input form="st_f" type="email" name="Email" required="${args->email_required:html}" data-prop-column="${args->email_db:html:default(email)}" placeholder="${args->email_placeholder:html:default(Enter your email)}" data-style="${args->email_input_style:html:default('width: 400px;
')}">
        <input form="st_f" type="text" name="first_name" required="${args->first_name_required:html:default(1)}" data-prop-column="${args->first_name_db:html:default(first_name)}" placeholder="${args->first_name_placeholder:html:default(First Name)}" data-style="${args->first_name_style:html}">
        <input form="st_f" type="tel" name="phone" required="${args->phone_required:html}" data-prop-column="${args->phone_db:html:default(phone)}" placeholder="${args->phone_placeholder:html:default(Phone Number)}" data-style="${args->phone_style:html}">

        <!-- Checkbox -->
        ${block->with_checkbox:default(1)}
        <div class="checkbox-wrapper" data-style="${args->checkbox_style:html:default('text-align: left;
float: none;
display: inline-flex;
')}">
          <input form="st_f" type="checkbox" name="consent" required="${args->checkbox_required:html:default(1)}" data-prop-column="${args->checkbox_db:html:default(partner_id)}">
          <span>${args->checkbox_label:default(I agree to terms and conditions)}</span>
        </div>
        <div class="checkbox-note">${args->checkbox_note:default(We respect your privacy leran more)}</div>

        <button form="st_f" type="submit" class="submit-button" data-style="${args->submit_button_style:html}" hover_style="${args->submit_button_hover_style:html}">
          ${args->button_caption:default(Subscribe Now)}
        </button>

        ${block->maybe_later:default(1)}
        <div style="margin-top:10px;">
          <a ${args->maybe_later_link:default('href="javascript:" class="$personyze_button_dont_show_again" data-action_id="${action_id}" data-n_sessions="0"')} data-style="${args->maybe_later_style:html:default('color: rgb(255, 252, 252);
')}" role="button">
            ${args->maybe_later_text:default(Maybe Later)}
          </a>
        </div>
      </div>
    </form>

    <div data-case="b" id="st_b" data-style="${args->success_style:html:default('font-size: 18px;
margin-top: 20px;
color: #fff;
')}">
      ${args->success:default(Thank you for subscribing!)}
    </div>
  </div>
</div>

${menu name='Container', icon='th-large'}
	${menu args->box_style name='Container Style', type='css'}
${menu name='Main Texts', icon='comment'}
	${menu args->message_text name='Main Message'}
	${menu args->message_style name='Main Message Style', type='css'}
	${menu args->gift_text name='Sub Message'}
	${menu args->gift_style name='Sub Message Style', type='css'}
${menu name='Timer', icon='clock-o'}
	${menu args->value name='Countdown Logic', type='timer_custom_params'}
	${menu args->timersubstrate_style name='Timer Wrapper Style', type='css'}
	${menu args->timer_separator_style name='Colon Style', type='css'}
	${menu args->timer_box_style name='Box Style', type='css'}
	${menu args->timer_number_style name='Number Style', type='css'}
	${menu args->timer_caption_style name='Caption Style', type='css'}
	${menu args->timer_caption_days name='Label: Days'}
	${menu args->timer_caption_hours name='Label: Hours'}
	${menu args->timer_caption_minutes name='Label: Minutes'}
	${menu args->timer_caption_seconds name='Label: Seconds'}
${menu name='Form Fields', icon='edit'}
	${menu args->email_placeholder name='Email Placeholder'}
	${menu args->email_input_style name='Email Style', type='css'}
	${menu args->email_db name='Save Email to DB', type='select_social'}
	${menu args->email_required name='Email Required?', type='checkbox', param='value_on=1', param='value_off='}
	${menu args->first_name_placeholder name='First Name Placeholder'}
	${menu args->first_name_style name='First Name Style', type='css'}
	${menu args->first_name_db name='Save First Name to DB', type='select_social'}
	${menu args->first_name_required name='First Name Required?', type='checkbox', param='value_on=1', param='value_off='}
	${menu args->phone_placeholder name='Phone Placeholder'}
	${menu args->phone_style name='Phone Style', type='css'}
	${menu args->phone_db name='Save Phone to DB', type='select_social'}
	${menu args->phone_required name='Phone Required?', type='checkbox', param='value_on=1', param='value_off='}
${menu name='Checkbox Field', icon='check-square'}
	${menu block->with_checkbox name='Show Checkbox'}
	${menu args->checkbox_label name='Checkbox Label'}
	${menu args->checkbox_style name='Checkbox Style', type='css'}
	${menu args->checkbox_db name='Save Checkbox to DB', type='select_social'}
	${menu args->checkbox_required name='Checkbox Required?', type='checkbox', param='value_on=1', param='value_off='}
	${menu args->checkbox_note name='Checkbox Note Text (HTML)'}
${menu name='CTA Button', icon='hand-pointer-o'}
	${menu args->button_caption name='Button Text'}
	${menu args->submit_button_style name='Button Style', type='css'}
	${menu args->submit_button_hover_style name='Hover Style', type='css'}
${menu name='After Submit', icon='check'}
	${menu args->success name='Thank You Message'}
	${menu args->success_style name='Thank You Message Style', type='css'}
	${menu args->customjs name='Custom JS After Submit'}
	${menu args->redir name='Redirect URL'}
	${menu args->redir_delay name='Redirect Delay (s)', type='number'}
	${menu args->auto_close_delay name='Auto Close (s)', type='number'}
${menu name='Maybe Later', icon='clock-o'}
	${menu block->maybe_later name='Show Maybe Later Button'}
	${menu args->maybe_later_text name='Maybe Later Text'}
	${menu args->maybe_later_link name='Maybe Later Link', type='a_attrs'}
	${menu args->maybe_later_style name='Maybe Later Style', type='css'}
${menu name='Close Button', icon='times'}
	${menu block->x name='Show Close Button'}
	${menu args->x name='Close Button HTML', type='dontshowagain'}
```


## Countdown Promotion Banner

Includes editable images, text blocks, logos, CTA buttons, and decorative shapes with full styling control.

```
<div class="$responsive ${args->mobile_img_order:html:default(img-mobile-top img-desktop-left)}"
     data-style="${args->banner_style:html:default('background-color: #004481;
position: relative;
padding-top: 20px;
padding-right: 40px;
padding-bottom: 20px;
padding-left: 40px;
border-radius: 8px;
overflow: hidden;
color: #fff;
')}">

  <style>
    .banner-flex-container {
      display:flex;
      align-items:center;
      justify-content:space-between;
      gap:20px;
      position:relative;
    }

    @media (max-width:768px){
      .banner-flex-container { flex-direction:column; }
      .img-mobile-top .image-container{ order:-1 !important; }
      .img-mobile-bottom .image-container{ order:2 !important; }
      .banner-content, .logo-container { text-align:center; }
      .cta-row { justify-content:center !important; }
    }

    @media (min-width:769px){
      .img-desktop-left .image-container{ order:-1 !important; }
      .img-desktop-right .image-container{ order:2 !important; }
    }

    .image-container img, .logo-container img { width:100%; height:auto; object-fit:cover; }
  </style>

  <!-- Close Button -->
  ${block->close_button:default(1)}
  <div style="position:absolute; top:10px; right:10px; cursor:pointer; z-index:10;">
    ${args->close_button_html:default('<div onmouseenter="this.style.backgroundColor=this.style.outlineColor" onmouseleave="this.style.backgroundColor=this.style.textDecorationColor" style="display: inline-block; vertical-align: text-bottom; width: 24px; height: 24px; box-sizing: border-box; border-radius: 50%; border: 0px solid; -webkit-box-shadow: rgba(255, 255, 255, 0.2) 0px 1px 0px inset, rgba(0, 0, 0, 0.2) 0px 1px 2px; padding: 2px; background-color: rgba(0, 0, 0, 0); text-decoration-color: rgba(0, 0, 0, 0); outline-color: rgb(206, 54, 64); outline-width: 4px; color: rgb(244, 244, 244); cursor: pointer; transition: 0.3s;" class="$personyze_button_dont_show_again" data-action_id="${action_id}"><div style="display: block; width: 100%; height: 100%; transition: 0.3s; border-radius: 50%; background-image: linear-gradient(-45deg, transparent 0%, transparent 49%, currentcolor 49%, currentcolor 53%, transparent 53%, transparent 100%), linear-gradient(45deg, transparent 0%, transparent 49%, currentcolor 49%, currentcolor 53%, transparent 53%, transparent 100%);"></div></div>')}
  </div>

  <!-- Banner Flex Container -->
  <div class="banner-flex-container">

    <!-- Optional Image -->
    ${block->right_image:default(1)}
    <div class="image-container" style="${args->right_image_style:html:default('width: 21%;
max-width: 500px;
margin-top: 0;
margin-right: 0;
margin-bottom: -24px;
margin-left: 0;
')}">
      <img src="${args->right_image_src:html:default('https://cdn.personyze.com/upload/362/705130cf0b17aa64.png')}" alt="Banking Image">
    </div>

    <!-- Banner Content -->
    <div class="banner-content" data-style="${args->banner_content_style:html:default('flex: 1;
max-width: 600px;
position: relative;
z-index: 2;
color: #fff;
')}">

      <!-- Optional Logo -->
      ${block->with_logo:default(1)}
      <div class="logo-container" style="${args->logo_style:html:default('width:180px; margin-bottom:15px;')}">
        <img src="${args->logo_src:html:default('https://cdn.personyze.com/upload/362/18a94c1299224ec8.png')}" alt="Bank Logo">
      </div>

      <!-- Headline -->
      <div class="banner-headline" data-style="${args->headline_style:html:default('font-size: 28px;
font-weight: bold;
margin-bottom: 10px;
')}">
        ${args->headline_text:default('Experience the Live <span style="color:#ffe500;">Concert of the Year!</span>')}
        <div class="tooltip">${args->headline_tooltip:default(Get your tickets today!)}</div>
      </div>

      <!-- Timer (Verified Working Version) -->
      <div data-style="${args->timersubstrate_style:html:default('margin:15px 0;')}">
        <div class="$timer_custom" data-action_id="${action_id:html}" data-value='{"start":${args->value:html:default('{"type":"fixed_date","fixed_date_date":"1745625600","fixed_date_timezone":"","fixed_date_time":"","cookie_based_days":"3","cookie_based_hours":4,"cookie_based_minutes":1,"cookie_based_restart":0,"cookie_based_restart_after":"hours","cookie_based_restart_after_hours":"0","cookie_based_restart_after_weekday":"0","restart_everytime_days":"0","restart_everytime_hours":"","restart_everytime_minutes":"","timeup_action":"","timeup_message":"","timeup_message_style":""}')},"design":{"timer_separator":":","timer_separator_style":${args->timer_separator_style:json:html:default('font-size: 14px;
color: #fff;
background-color: rgba(225, 24, 24, 0);
margin-top: 10px;
')},"timer_box_style":${args->timer_box_style:json:html:default('display: inline-block;
padding: 5px;
background-color: #fff;
border-radius: 5px;
margin-top: 0;
margin-right: 5px;
margin-bottom: 0;
margin-left: 5px;
')},"timer_number_style":${args->timer_number_style:json:html:default('font-size: 20px;
font-weight: bold;
color: #333;
text-align: center;
')},"timer_caption_style":${args->timer_caption_style:json:html:default('font-size: 10px;
color: #666;
')},"timer_caption_days":${args->timer_caption_days:json:html:default(Days)},"timer_caption_hours":${args->timer_caption_hours:json:html:default(Hours)},"timer_caption_minutes":${args->timer_caption_minutes:json:html:default(Minutes)},"timer_caption_seconds":${args->timer_caption_seconds:json:html:default(Seconds)}}}'></div>
      </div>

      <!-- Subheading -->
      <div class="banner-subheading" data-style="${args->subheading_style:html:default('font-size: 16px;
margin-bottom: 20px;
')}">
        ${args->subheading_text:default(Get your tickets now and be part of an unforgettable night!)}
      </div>

      <!-- CTA Row -->
      <div class="cta-row" data-style="${args->cta_row_style:html:default('display:flex;align-items:center;gap:20px;')}">
        ${block->primary_cta:default(1)}<a ${args->primary_cta_link:default('href="#"')} class="signup-btn" data-style="${args->primary_cta_style:html:default('background-color: #ffe500;
color: #004481;
border: 2px solid #ffe500;
padding-top: 12px;
padding-right: 24px;
padding-bottom: 12px;
padding-left: 24px;
border-radius: 6px;
font-weight: 600;
text-decoration: none;
')}">${args->primary_cta_text:default(Buy Tickets)}</a>
        ${block->secondary_cta:default(1)}<a ${args->secondary_cta_link:default('href="#"')} class="signin-link" data-style="${args->secondary_cta_style:html:default('color:#fff;text-decoration:underline;')}">${args->secondary_cta_text:default(Learn More)}</a>
      </div>
    </div>
  </div>

  ${block->with_shape:default(1)}<div style="${args->shape_style:html:default('position:absolute;bottom:-20px;left:-20px;width:100px;height:100px;background:#ffe500;border-radius:50%;opacity:0.3;')}"></div>
  ${block->with_shape2:default(1)}<div style="${args->shape2_style:html:default('position:absolute;top:-30px;right:-30px;width:120px;height:120px;background:#00a1e0;transform:rotate(45deg);opacity:0.2;')}"></div>
</div>
<!-- PERSONYZE MENU OPTIONS -->

${menu name='Banner Container', icon='th-large'}
	${menu args->banner_style name='Banner Container Style', type='css', param='with_responsive=1'}
${menu name='Close Button', icon='times'}
	${menu block->close_button name='Show Close Button'}
	${menu args->close_button_html name='Close Button HTML', type='dontshowagain'}
${menu name='Optional Logo', icon='image'}
	${menu block->with_logo name='Show Logo'}
	${menu args->logo_src name='Logo URL', type='personyze_media_url'}
	${menu args->logo_style name='Logo Style', type='css', param='with_responsive=1'}
${menu name='Optional Main Image and Dirction', icon='image'}
	${menu block->right_image name='Show Main Image'}
	${menu args->right_image_src name='Main Image URL', type='personyze_media_url'}
	${menu args->right_image_style name='Main Image Style', type='css', param='with_responsive=1'}
	${menu args->mobile_img_order name='Image Position', type='select', param='options=[["Mobile top, Desktop right","img-mobile-top img-desktop-right"],["Mobile bottom, Desktop right","img-mobile-bottom img-desktop-right"],["Mobile top, Desktop left","img-mobile-top img-desktop-left"],["Mobile bottom, Desktop left","img-mobile-bottom img-desktop-left"]]'}
${menu name='Main Content', icon='align-left'}
	${menu args->banner_content_style name='Content Area Style', type='css', param='with_responsive=1'}
${menu name='Headline', icon='heading'}
	${menu args->headline_text name='Headline Text'}
	${menu args->headline_style name='Headline Style', type='css', param='with_responsive=1'}
	${menu args->headline_tooltip name='Tooltip Text'}
${menu name='Subheading', icon='paragraph'}
	${menu args->subheading_text name='Subheading Text'}
	${menu args->subheading_style name='Subheading Style', type='css', param='with_responsive=1'}
${menu name='Timer', icon='clock-o'}
	${menu args->value name='Countdown logic', type='timer_custom_params'}
	${menu args->timersubstrate_style name='Timer Container Style', type='css', param='with_responsive=1'}
	${menu args->timer_separator_style name='Timer Separator Style', type='css', param='with_responsive=1'}
	${menu args->timer_box_style name='Timer Box Style', type='css', param='with_responsive=1'}
	${menu args->timer_number_style name='Timer Number Style', type='css', param='with_responsive=1'}
	${menu args->timer_caption_style name='Timer Caption Style', type='css', param='with_responsive=1'}
	${menu args->timer_caption_days name='Label: Days', description='Removing this will hide the Days number'}
	${menu args->timer_caption_hours name='Label: Hours', description='Removing this will hide the Hours number'}
	${menu args->timer_caption_minutes name='Label: Minutes', description='Removing this will hide the Minutes number'}
	${menu args->timer_caption_seconds name='Label: Seconds', description='Removing this will hide the Seconds number'}
${menu name='CTA Row', icon='hand-pointer-o'}
	${menu args->cta_row_style name='CTA Row Style', type='css', param='with_responsive=1'}
${menu name='Primary CTA', icon='hand-o-up'}
	${menu block->primary_cta name='Show Primary CTA'}
	${menu args->primary_cta_text name='Primary CTA Text'}
	${menu args->primary_cta_link name='Primary CTA Link', type='a_attrs'}
	${menu args->primary_cta_style name='Primary CTA Style', type='css', param='with_responsive=1'}
${menu name='Secondary CTA', icon='sign-in'}
	${menu block->secondary_cta name='Show Secondary CTA'}
	${menu args->secondary_cta_text name='Secondary CTA Text'}
	${menu args->secondary_cta_link name='Secondary CTA Link', type='a_attrs'}
	${menu args->secondary_cta_style name='Secondary CTA Style', type='css', param='with_responsive=1'}
${menu name='Decorative Shapes', icon='paint-brush'}
	${menu block->with_shape name='Show Shape 1'}
	${menu args->shape_style name='Shape 1 Style', type='css', param='with_responsive=1'}
	${menu block->with_shape2 name='Show Shape 2'}
	${menu args->shape2_style name='Shape 2 Style', type='css', param='with_responsive=1'}
```


## Full Screen Timer

Designed to occupy 100% of viewport width and height. Easy editing of images, timer alignment, headlines, CTAs, decorative shapes, and more.

```
<div class="$responsive ${args->desktop_content_order:html:default(desktop-content-left)} ${args->mobile_content_order:html:default(mobile-timer-top)}"
     data-style="${args->banner_style:html:default('background-color: #0A2540;
position: relative;
padding-top: 20px;
padding-right: 40px;
padding-bottom: 20px;
padding-left: 40px;
color: #fff;
display: flex;
justify-content: center;
align-items: center;
width: 100%;
height: 100%;
box-sizing: border-box;
')}">

  <style>
    .banner-flex-container {
      display:flex; align-items:center; justify-content:center; gap:20px; max-width:1200px; width:100%;
    }
    .timer-container, .content-container { flex:1; max-width:500px; text-align:center; }

    @media (max-width:768px){
      .banner-flex-container { flex-direction:column; }
      .mobile-timer-top .timer-container { order:-1; }
      .mobile-timer-bottom .timer-container { order:2; }
      .logo-container { justify-content:center; margin:auto; }
      .cta-row { justify-content:center !important; }
    }

    @media (min-width:769px){
      .desktop-content-left .content-container { order:-1; }
      .desktop-content-right .timer-container { order:-1; }
      .cta-row { justify-content:flex-start; }
    }

    .logo-container img { width:100%; height:auto; object-fit:contain; }
    .cta-row { display:flex; gap:10px; margin-top:20px; }
  </style>

  ${block->close_button:default(1)}
  <div style="position:absolute;top:10px;right:10px;cursor:pointer;z-index:10;">
    ${args->close_button_html:default('<div onmouseenter="this.style.backgroundColor=this.style.outlineColor" onmouseleave="this.style.backgroundColor=this.style.textDecorationColor" style="display: inline-block; vertical-align: text-bottom; width: 30px; height: 30px; box-sizing: border-box; border-radius: 50%; border: 0px solid; box-shadow: rgba(255, 255, 255, 0.2) 0px 1px 0px inset, rgba(0, 0, 0, 0.2) 0px 1px 2px; padding: 7px; background-color: rgba(0, 0, 0, 0.51); text-decoration-color: rgba(0, 0, 0, 0.51); outline-color: rgb(255, 102, 102); outline-width: 5px; color: white; cursor: pointer; transition: 0.3s;" class="$personyze_button_dont_show_again" data-action_id="${action_id}"><div style="display: block; width: 100%; height: 100%; transition: 0.3s; border-radius: 50%; background-image: linear-gradient(-45deg, transparent 0%, transparent 48%, currentcolor 48%, currentcolor 54%, transparent 54%, transparent 100%), linear-gradient(45deg, transparent 0%, transparent 48%, currentcolor 48%, currentcolor 54%, transparent 54%, transparent 100%);"></div></div>')}
  </div>

  <div class="banner-flex-container">

    <div class="timer-container" style="${args->timer_container_style:html}">

      ${block->above_timer_text:default(1)}
      <div class="above-timer-text" style="${args->above_timer_text_style:html:default('font-size: 16px;
margin-bottom: 10px;
color: #fff;
')}">
        ${args->above_timer_text_content:default(Limited-time offer!)}
      </div>

      ${block->timer_block:default(1)}
      <div class="$timer_custom" data-action_id="${action_id:html}" data-json-value='{
        "start":${args->value:html:default('{"type":"cookie_based","fixed_date_date":"","fixed_date_timezone":"","fixed_date_time":"","cookie_based_days":"3","cookie_based_hours":4,"cookie_based_minutes":1,"cookie_based_restart":0,"cookie_based_restart_after":"hours","cookie_based_restart_after_hours":"0","cookie_based_restart_after_weekday":"0","restart_everytime_days":"0","restart_everytime_hours":"","restart_everytime_minutes":"","timeup_action":"","timeup_message":"","timeup_message_style":""}')},
        "design":{
          "timer_separator":":",
          "timer_separator_style":${args->timer_separator_style:json:html:default('font-size: 14px;
color: #fff;
background-color: rgba(115, 58, 58, 0);
')},
          "timer_box_style":${args->timer_box_style:json:html:default('display: inline-block;
padding: 5px;
background-color: #fff;
border-radius: 5px;
margin-top: 0;
margin-right: 5px;
margin-bottom: 0;
margin-left: 5px;
')},
          "timer_number_style":${args->timer_number_style:json:html:default('font-size: 20px;
font-weight: bold;
color: #333;
')},
          "timer_caption_style":${args->timer_caption_style:json:html:default('font-size: 10px;
color: #666;
')},
          "timer_caption_days":${args->timer_caption_days:json:html:default(Days)},
          "timer_caption_hours":${args->timer_caption_hours:json:html:default(Hours)},
          "timer_caption_minutes":${args->timer_caption_minutes:json:html:default(Minutes)},
          "timer_caption_seconds":${args->timer_caption_seconds:json:html:default(Seconds)}
        }
      }'></div>
    </div>

    <div class="content-container" style="${args->content_container_style:html}">
      ${block->with_logo:default(1)}
      <div class="logo-container ${args->logo_position_desktop:html:default(desktop-center)} ${args->logo_position_mobile:html:default(mobile-center)}"
           style="${args->logo_style:html:default('width: 150px;
margin: auto;
')}">
        <img src="${args->logo_src:html:default('https://cdn.personyze.com/upload/362/18a94c1299224ec8.png')}" alt="Logo">
      </div>

      <div class="banner-headline" style="${args->headline_style:html:default('font-size:32px;font-weight:bold;margin-top:15px;')}">
        ${args->headline_text:default('Meet the Future of Tech: The <span style="color:#34D399;">XGizmo Pro!</span> ?')}
      </div>

      <div class="banner-subheading" style="${args->subheading_style:html:default('font-size:18px;margin-top:10px;')}">
        ${args->subheading_text:default(Experience innovation with cutting-edge features designed for you.)}
      </div>

      <div class="cta-row" style="${args->cta_row_style_desktop:html:default('display: flex;
align-items: center;
gap: 20px;
justify-content: center;
')}">
        ${block->primary_cta:default(1)}
        <a ${args->primary_cta_link:default('href="#"')} style="${args->primary_cta_style:html:default('background-color:#34D399;color:#0A2540;padding:12px 24px;border-radius:6px;font-weight:600;text-decoration:none;')}">
          ${args->primary_cta_text:default(Order Now)}
        </a>

        ${block->secondary_cta:default(1)}
        <a ${args->secondary_cta_link:default('href="#"')} style="${args->secondary_cta_style:html:default('color:#fff;text-decoration:underline;padding:12px;')}">
          ${args->secondary_cta_text:default(Explore Features)}
        </a>
      </div>
    </div>
  </div>

  ${block->with_shape:default(1)}
  <div style="${args->shape_style:html:default('position:absolute;bottom:-30px;left:-30px;width:120px;height:120px;background:#34D399;border-radius:50%;opacity:0.3;')}"></div>

  ${block->with_shape2:default(1)}
  <div style="${args->shape2_style:html:default('position:absolute;top:-30px;right:-30px;width:140px;height:140px;background:#6366F1;transform:rotate(45deg);opacity:0.2;')}"></div>
</div>

${menu name='Banner Container', icon='th-large'}
	${menu args->banner_style name='Banner Style', type='css'}
${menu name='Close Button', icon='times'}
	${menu block->close_button name='Show Close Button'}
	${menu args->close_button_html name='Close Button HTML', type='dontshowagain'}
${menu name='Content Layout', icon='columns'}
	${menu args->desktop_content_order name='Desktop Content Position', type='select', param='options=[["Text Left, Timer Right","desktop-content-left"],["Text Right, Timer Left","desktop-content-right"]]'}
	${menu args->mobile_content_order name='Mobile Timer Position', type='select', param='options=[["Timer Top","mobile-timer-top"],["Timer Bottom","mobile-timer-bottom"]]'}
	${menu args->content_container_style name='Content Container CSS', type='css'}
${menu name='Optional Logo', icon='image'}
	${menu block->with_logo name='Show Logo'}
	${menu args->logo_src name='Logo URL', type='personyze_media_url'}
	${menu args->logo_style name='Logo CSS', type='css'}
	${menu args->logo_position_desktop name='Desktop Logo Alignment', type='select', param='options=[["Center","desktop-center"],["Left","desktop-left"],["Right","desktop-right"]]'}
	${menu args->logo_position_mobile name='Mobile Logo Alignment', type='select', param='options=[["Center","mobile-center"],["Left","mobile-left"],["Right","mobile-right"]]'}
${menu name='Above Timer Text', icon='text-height'}
	${menu block->above_timer_text name='Show Text Above Timer'}
	${menu args->above_timer_text_content name='Above Timer Text', type='text'}
	${menu args->above_timer_text_style name='Above Timer Text CSS', type='css'}
${menu name='Timer Settings', icon='clock-o'}
	${menu block->timer_block name='Show Timer'}
	${menu args->value name='Countdown Logic', type='timer_custom_params'}
	${menu args->timer_container_style name='Timer Container CSS', type='css'}
	${menu args->timer_separator_style name='Colon CSS', type='css'}
	${menu args->timer_box_style name='Timer Box CSS', type='css'}
	${menu args->timer_number_style name='Timer Number CSS', type='css'}
	${menu args->timer_caption_style name='Caption CSS', type='css'}
	${menu args->timer_caption_days name='Label: Days'}
	${menu args->timer_caption_hours name='Label: Hours'}
	${menu args->timer_caption_minutes name='Label: Minutes'}
	${menu args->timer_caption_seconds name='Label: Seconds'}
${menu name='Headline', icon='heading'}
	${menu args->headline_text name='Headline Text'}
	${menu args->headline_style name='Headline CSS', type='css'}
${menu name='Subheading', icon='paragraph'}
	${menu args->subheading_text name='Subheading Text'}
	${menu args->subheading_style name='Subheading CSS', type='css'}
${menu name='CTA Alignment', icon='hand-pointer-o'}
	${menu args->cta_row_style_desktop name='CTA Container CSS', type='css'}
${menu name='Primary CTA', icon='hand-o-up'}
	${menu block->primary_cta name='Show Primary CTA'}
	${menu args->primary_cta_text name='Primary CTA Text'}
	${menu args->primary_cta_link name='Primary CTA Link', type='a_attrs'}
	${menu args->primary_cta_style name='Primary CTA CSS', type='css'}
${menu name='Secondary CTA', icon='sign-in'}
	${menu block->secondary_cta name='Show Secondary CTA'}
	${menu args->secondary_cta_text name='Secondary CTA Text'}
	${menu args->secondary_cta_link name='Secondary CTA Link', type='a_attrs'}
	${menu args->secondary_cta_style name='Secondary CTA CSS', type='css'}
${menu name='Decorative Shapes', icon='paint-brush'}
	${menu block->with_shape name='Show Shape 1'}
	${menu args->shape_style name='Shape 1 CSS', type='css'}
	${menu block->with_shape2 name='Show Shape 2'}
	${menu args->shape2_style name='Shape 2 CSS', type='css'}
```


