## Alert Popup

A responsive, dynamic popup that alerts users. It features a customizable close button and two editable CTA buttons,

```
<style>
  /* Alert Container */
  .alert-container {
    position: relative;
    background-color: #FFE5E5; /* Light red background */
    border: 1px solid #FF0000; /* Red border for alert */
    border-radius: 8px;
    padding: 16px;
    width: 320px; /* Adjust as needed */
    margin: 0 auto;
    box-shadow: 0 2px 6px rgba(0,0,0,0.1);
    font-family: Arial, sans-serif;
  }

  /* Alert Label in top-left */
  .alert-label {
    position: absolute;
    top: 8px;
    left: 8px;
    background-color: #FF0000;
    color: #FFF;
    font-size: 12px;
    font-weight: bold;
    padding: 4px 8px;
    border-radius: 4px;
  }

  /* Close Button (X) in top-right */
  .close-btn {
    position: absolute;
    top: 8px;
    right: 8px;
    font-size: 18px;
    font-weight: bold;
    color: #000;
    text-decoration: none;
    cursor: pointer;
  }

  /* Main Alert Text */
  .alert-text {
    margin-top: 36px;
    text-align: center;
    font-size: 16px;
    color: #333;
    line-height: 1.4;
  }

  /* CTA Button Container */
  .cta-container {
    text-align: center;
    margin-top: 16px;
    display: flex;
    justify-content: center;
    gap: 10px;
    flex-wrap: wrap;
  }

  /* CTA Button Style */
  .cta-button {
    background-color: #FF0000;
    color: #FFF;
    border: none;
    border-radius: 4px;
    padding: 8px 16px;
    font-size: 14px;
    cursor: pointer;
    text-decoration: none;
    display: inline-block;
  }
  .cta-button:hover {
    background-color: #CC0000;
  }

  /* Responsive Adjustments */
  @media (max-width: 480px) {
    .alert-container {
      width: 90%;
    }
    .alert-text {
      font-size: 14px;
    }
  }
</style>

<div class="alert-container">
  <!-- Alert Label -->
  <div class="alert-label">
    ${args->alert_label:default(IMPORTANT ALERT)}
  </div>

  <!-- Personyze Editable Close Button (Default: Top-Right) -->
  ${args->close_button:default('<a href="javascript:" style="font-size: 24px; color: black; font-weight: lighter; line-height: 1; text-decoration: none; position: absolute; right: 10px; top: 5px;" class="$personyze_button_dont_show_again" data-action_id="${action_id}" title="Close">×</a>')}

  <!-- Main Alert Text -->
  <div class="alert-text">
    ${args->alert_text:default(Your account will expire in 3 days. Please take action immediately!)}
  </div>

  <!-- CTA Buttons -->
  <div class="cta-container">
    <a href="${args->cta1_href:html:default('href="#"')}"
       class="cta-button"
       data-style="${args->cta1_style:html}"
       title="Primary Action">
      ${args->cta1_text:default(Renew Now)}
    </a>
    <a href="${args->cta2_href:html:default('href="javascript:"')}"
       class="cta-button"
       data-style="${args->cta2_style:html}"
       title="Secondary Action">
      ${args->cta2_text:default(Maybe Later)}
    </a>
  </div>
</div>

<!-- PERSONYZE MENU OPTIONS -->

${menu name='Alert Settings', icon='exclamation-triangle'}
	${menu args->alert_label name='Alert Label', description='Label text (top-left)'}
	${menu args->alert_text name='Alert Text', description='Main alert message'}
${menu name='CTA Button 1', icon='hand-pointer-o'}
	${menu args->cta1_text name='CTA 1 Text'}
	${menu args->cta1_href name='CTA 1 URL', type='a_attrs'}
	${menu args->cta1_style name='CTA 1 Style', type='css'}
${menu name='CTA Button 2', icon='hand-o-up'}
	${menu args->cta2_text name='CTA 2 Text'}
	${menu args->cta2_href name='CTA 2 URL', type='a_attrs'}
	${menu args->cta2_style name='CTA 2 Style', type='css'}
${menu name='Close Button', icon='times'}
	${menu args->close_button name='Close button HTML', type='dontshowagain'}
```


## Tall Banner with CTA & Image Options

vertically oriented banner template featuring flexible image, text, and dual CTA button configurations—including custom JavaScript, auto-dismiss behavior, and animations—for robust technical customization.

```
<div class="$responsive" data-style="box-sizing: border-box;
margin: 0 auto;
position: relative;
overflow: hidden;
${args->style:html:default('width: 160px;
height: 600px;
border: 1px solid #1a1a1a;
background-color: #222;
')}">

  <!-- Background Image -->
  <div data-style="position: absolute;
    width: 100%;
    height: 100%;
    background-image: url(${args->image_bgc:html:default('https://cdn.personyze.com/upload/362/ace46de3a2bab43a.png')});
    background-repeat: no-repeat;
    background-position: center 50%;
    ${args->img_bg_style:html:default('background-color: #111;')}">
  </div>

  <!-- Optional Foreground Image -->
  ${block->with_image:default(1)}
  <div data-style="position: absolute; width: 100%; top: 10px; text-align: center;">
    <img src="${args->foreground_image:html:default('https://cdn.personyze.com/upload/362/836ce71c4644386c.png')}"
         alt="${args->foreground_image_alt:html:default(Image)}"
         data-style="${args->foreground_image_style:html:default('max-width: 140px; height: auto; background-color: #fafafa; border-radius: 20px; padding: 5px; margin-top: 15px;')}">
  </div>
  ${endblock}

  <!-- Title -->
  <div data-style="position: absolute; width: 100%; ${args->content_title_position:html:default('text-align: center; top: 80px;')}">
    <span data-style="${args->title_style:html:default('font-family: Viga; color: #fff; font-size: 25px; line-height: 1.2; letter-spacing: 1px;')}">
      ${args->title:default(UNIVERSITY CREATIVE EVENT)}
    </span>
  </div>

  <!-- Description -->
  <div data-style="position: absolute; width: 100%; ${args->content_style:html:default('font-family: Open Sans; color: #ccc; text-align: center; top: 250px; font-size: 22px; line-height: 1.2;')}">
    ${args->title4:default('for<br />innovative<br />technologies')}
  </div>

  <!-- CTA Buttons -->
  <div data-style="position: absolute; width: 100%; ${args->button_style:html:default('text-align: center; bottom: 150px;')}">

    ${block->button1:default(1)}
    <div style="margin-bottom: 15px;">
      <a ${args->href1:default('href="#"')}
         data-js="${args->cta_js:html}"
         data-dismiss="${args->cta_dismiss:html}"
         target="${args->target:html:default(_self)}"
         data-style="${args->button1_style:html:default('font-size: 16px;
background-color: #3498db;
color: #fff;
padding-top: 10px;
padding-right: 24px;
padding-bottom: 10px;
padding-left: 24px;
border-radius: 30px;
text-decoration: none;
')}"
         style="animation: ${args->button1_animation:html:default(bounce)} 1.5s infinite;"
         class="$personyze_button">
         ${args->button1_text:default(Join Now)}
      </a>
    </div>
    ${endblock}

    ${block->button2:default(1)}
    <div>
      <a ${args->href2:default('href="#"')}
         target="${args->target:html}"
         data-style="${args->button2_style:html:default('font-size: 14px;
background: transparent;
color: #eee;
text-decoration: underline;
padding-top: 10px;
padding-right: 20px;
padding-bottom: 10px;
padding-left: 20px;
border-radius: 20px;
')}"
         class="$personyze_button">
         ${args->button2_text:default(Maybe Later)}
      </a>
    </div>
    ${endblock}

  </div>

  <!-- Close Button -->
  ${block->x:default(1)}
  <div data-style="${args->close_button_style:html:default('position: absolute; top: 3px; right: 3px; z-index: 9999;')}" title="Close">
    ${args->x:default('<a href="javascript:" class="$personyze_button_dont_show_again" data-action_id="${action_id}" style="font-size: 20px; color: #fff; background: rgba(0,0,0,0.3); padding: 6px 12px; border-radius: 50%; text-decoration: none;">&times;</a>')}
  </div>

</div>

${menu name='Box', icon='th-large'}
	${menu args->style name='Box Style', type='css', param='with_responsive=1'}
	${menu args->image_bgc name='Background Image', type='personyze_media_url'}
	${menu args->img_bg_style name='Background Style', type='css', param='with_responsive=1'}
${menu name='Image', icon='image'}
	${menu block->with_image name='Show Foreground Image'}
	${menu args->foreground_image name='Image URL', type='personyze_media_url'}
	${menu args->foreground_image_alt name='Image Alt'}
	${menu args->foreground_image_style name='Image Style', type='css', param='with_responsive=1'}
${menu name='Text Block', icon='font'}
	${menu args->title name='Title Text'}
	${menu args->title_style name='Title Style', type='css', param='with_responsive=1'}
	${menu args->content_title_position name='Title Position', type='css', param='with_responsive=1'}
	${menu args->title4 name='Description Text'}
	${menu args->content_style name='Description Style', type='css', param='with_responsive=1'}
${menu name='Primary CTA Button', icon='hand-pointer-o'}
	${menu block->button1 name='Show Button'}
	${menu args->button1_text name='Button Text'}
	${menu args->href1 name='Button URL', type='a_attrs'}
	${menu args->button1_style name='Button Style', type='css', param='with_responsive=1'}
	${menu args->button1_animation name='Animation', type='select', param='options=[["None",""],["Bounce","bounce"],["Pulse","pulse"],["Shake","shake"]]'}
	${menu args->cta_js name='JS on Click'}
	${menu args->cta_dismiss name='Auto Dismiss'}
${menu name='Secondary CTA Button', icon='hand-o-up'}
	${menu block->button2 name='Show Second Button'}
	${menu args->button2_text name='Second Button Text'}
	${menu args->href2 name='Second Button URL', type='a_attrs'}
	${menu args->button2_style name='Second Button Style', type='css', param='with_responsive=1'}
${menu name='Close Button', icon='times-circle'}
	${menu block->x name='Show Close Button'}
	${menu args->close_button_style name='Close Button Style', type='css', param='with_responsive=1'}
	${menu args->x name='Close Button HTML', type='dontshowagain'}
```


## Banner with optional image on the left



```
<div class="$responsive" data-style="position:relative; overflow:hidden; ${args->box_style:html:default('background-color: rgba(244, 246, 249, 1);
height: sel(auto, auto);
max-height: none;
width: sel(auto, 0);
max-width: sel(none, none);
padding: 22px;
background-image: url(''https://cdn.personyze.com/upload/5919/227ba665b2cfbdbe.png'');
background-size: cover;
border: none;
')}">
	<style>
		@media (max-width: 768px)
		{	.ac${action_id:html} {flex-direction:column}
		}
	</style>
	<div class="ac${action_id:html}" style="display:flex; align-items:stretch">
		<div style="background-repeat:no-repeat; background-position:center; ${args->image_style:html:default('background-image: url(''https://www.personyze.com/wp-content/uploads/Group-183.svg'');
background-size: contain;
background-position: center;
background-repeat: no-repeat;
background-color: rgba(256, 256, 256, 0);
padding: 0px;
margin: 0px;
position: static;
top: center;
max-height: none;
width: 300px;
height: 200px;
')}">
			<div data-style=""></div>
		</div>
		<div style="padding:0 1em">
			<div data-style="max-height:${args->image_height:html}">
				<div data-style="outline:0; ${args->title_style:html:default('font-family: sans-serif;
font-size: 24px;
font-weight: bold;
line-height: 20px;
text-align: left;
text-transform: capitalize;
color: rgb(245, 245, 245);
margin-top: 28px;
margin-right: 0px;
margin-bottom: 0px;
margin-left: 16px;
width: sel(auto, auto);
max-width: 100%;
height: auto;
')}">
					${args->title:default('<div>Title goes here&nbsp;<br />
&nbsp;</div>
')}
				</div>
				<div data-style="outline:0; ${args->text_style:html:default('font-family: sans-serif;
font-size: 15px;
font-weight: normal;
line-height: 20px;
text-align: left;
text-transform: capitalize;
margin-top: 0px;
margin-right: 0px;
margin-bottom: 0px;
margin-left: 16px;
color: rgb(256, 256, 256);
width: 100%;
height: auto;
')}">
					${args->text:default('Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.')}
				</div>
				<div style="text-align:center; ${args->buttons_style:html:default('margin-top: 1.5em;
margin-right: 0;
margin-bottom: 0em;
margin-left: 16px;
')}">
					${block->show_button:default(1)}
					<a ${args->href:default('href=""')} data-style="${args->button_text_style:html:default('font-family: sans-serif;
font-size: sel(16px, 13px);
color: white;
text-decoration: none;
background-color: #1697F3;
padding-top: 8px;
padding-right: 16px;
padding-bottom: 8px;
padding-left: 16px;
border: solid 2px #1697F3;
border-radius: 4px;
font-weight: bolder;
width: 100%;
')}">  ${args->button_t:default(Call to Action)}
					</a>

					${block->show_button_2:default(1)}
					<a ${args->href_3:default('href=""')} data-style="display:inline-block; ${args->button_text_style_2:html:default('font-family: sans-serif;
font-size: sel(16px, 13px);
font-weight: bold;
text-decoration: none;
color: rgb(256, 256, 256);
background-color: rgba(256, 256, 256, 0);
border: solid rgb(256, 256, 256) 2px;
border-radius: 4px;
padding-top: 8px;
padding-right: 16px;
padding-bottom: 8px;
padding-left: 16px;
margin-top: 0px;
margin-right: 0px;
margin-bottom: 0px;
margin-left: 16px;
width: auto;
')}">
						${args->button_t_2:default(Secondary)}
					</a>
				</div>
			</div>
		</div>
	</div>
	${block->show_close_button:default(1)}
	<div data-style="position:absolute; cursor:pointer; ${args->close_button_style:html:default('top: sel(8px, 8px);
right: sel(8px, 8px);
z-index: 9999;
')}">
		${args->close_button:default('<div onmouseenter="this.style.backgroundColor=this.style.outlineColor" onmouseleave="this.style.backgroundColor=this.style.textDecorationColor" style="display: inline-block; vertical-align: text-bottom; width: 24px; height: 24px; box-sizing: border-box; border-radius: 50%; border: 0px solid; -webkit-box-shadow: rgba(255, 255, 255, 0.2) 0px 1px 0px inset, rgba(0, 0, 0, 0.2) 0px 1px 2px; padding: 2px; background-color: rgba(0, 0, 0, 0); text-decoration-color: rgba(0, 0, 0, 0); outline-color: rgb(179, 199, 209); outline-width: 15px; color: rgb(255, 255, 255); cursor: pointer; transition: 0.3s;" class="$personyze_button_dont_show_again" data-action_id="${action_id}"><div style="display: block; width: 100%; height: 100%; transition: 0.3s; border-radius: 50%; background-image: linear-gradient(-45deg, transparent 0%, transparent 43%, currentcolor 43%, currentcolor 59%, transparent 59%, transparent 100%), linear-gradient(45deg, transparent 0%, transparent 43%, currentcolor 43%, currentcolor 59%, transparent 59%, transparent 100%);"></div></div>')}
	</div>
</div>

${menu name='Box', icon='th-large'}
	${menu args->box_style name='Box style', type='css', param='with_responsive=1'}
${menu name='Logo Picture', icon='image'}
	${menu args->image_style name='Picture URL', type='css'}
${menu name='Content', icon='bars'}
	${menu args->title name='Title'}
	${menu args->title_style name='Title style', type='css', param='with_responsive=1'}
	${menu args->text name='Text'}
	${menu args->text_style name='Text style', type='css', param='with_responsive=1'}
${menu name='First Button', icon='hand-o-up'}
	${menu block->show_button name='Show button'}
	${menu args->button_t name='Text button'}
	${menu args->href name='URL', type='a_attrs'}
	${menu args->button_text_style name='Button text style', type='css', param='with_responsive=1'}
	${menu args->buttons_style name='Buttons placment margin', type='css', param='with_responsive=1'}
${menu name='Second Button', icon='hand-o-up'}
	${menu block->show_button_2 name='Show second button'}
	${menu args->button_t_2 name='Text button'}
	${menu args->href_3 name='URL', type='a_attrs'}
	${menu args->button_text_style_2 name='Button text style', type='css', param='with_responsive=1'}
${menu name='Close Button', icon='times-circle'}
	${menu block->show_close_button name='Show close button'}
	${menu args->close_button_style name='Close Button Style', type='css', param='with_responsive=1'}
	${menu args->close_button name='Close button', type='dontshowagain'}
```


## A message block for promo text

CTA with icons

```
<!-- ✅ MAIN HTML BANNER CODE -->
<div class="$responsive" data-style="box-sizing: border-box; position: relative; background-color: ${args->background_color:html:default('#E54944')}; border-radius: 10px; padding: 28px 24px; ${args->box_size:html:default('max-width: 360px;
')} margin: 0 auto; box-shadow: 0 2px 10px rgba(0,0,0,0.1); font-family: Arial, sans-serif;">

  <!-- ✅ Internal CSS -->
  <style>
    .saas-banner-headline {
      text-align: center;
      margin-bottom: 8px;
    }
    .saas-banner-tagline {
      text-align: center;
      margin-bottom: 6px;
    }
    .saas-banner-description {
      text-align: center;
      line-height: 1.5;
      margin-bottom: 16px;
    }
    .saas-banner-button {
      display: inline-flex;
      align-items: center;
      justify-content: center;
      text-align: center;
      text-decoration: none;
      width: auto;
      gap: 8px;
      flex-direction: row;
    }
    .saas-banner-button.icon-left i { order: -1; }
    .saas-banner-button.icon-right i { order: 1; }
  </style>

  <!-- ✅ Content Blocks -->
  ${block->with_tagline:default(1)}
  <div class="saas-banner-tagline" data-style="${args->tagline_style:html:default('text-transform: uppercase;
color: white;
font-size: 12px;
font-weight: 600;
letter-spacing: 1px;
')}">
    ${args->tagline:default(MODERN SAAS)}
  </div>

  ${block->with_headline:default(1)}
  <div class="saas-banner-headline" data-style="${args->headline_style:html:default('font-size: 22px;
font-weight: bold;
color: white;
')}">
    ${args->headline:default(Exclusive Offers Only Today!)}
  </div>

  ${block->with_description:default(1)}
  <div class="saas-banner-description" data-style="${args->description_style:html:default('font-size: 14px;
color: white;
')}">
    ${args->description:default('Don''t miss out!')}
  </div>

  ${block->with_cta:default(1)}
  <div style="text-align:center;">
    <a class="saas-banner-button ${args->cta_icon_position:html:default(icon-left)}" ${args->cta_link:default('href="#"')} data-style="${args->cta_style:html:default('background-color: white;
color: rgb(62, 38, 38);
padding: 12px;
border-radius: 6px;
font-weight: bold;
font-size: 14px;
display: inline-flex;
align-items: center;
justify-content: center;
width: auto;
')}">
      <span>${args->cta_text:default('SEE TODAY''S DEALS')}</span>
      ${if args->cta_icon_class:default(angle-double-right) != ''}<i class="$icon ${args->cta_icon_class:html}" style="${args->cta_icon_style:html:default('margin-top: 0;
margin-right: 4px;
margin-bottom: 0;
margin-left: 4px;
font-size: 14px;
color: rgb(22, 22, 22);
')}"></i>${end}
    </a>
  </div>

  ${block->with_secondary_cta:default(1)}
  <div style="margin-top: 12px; text-align: center;">
    <a ${args->cta_link_2:default('href="javascript:" class="$personyze_button_dont_show_again" data-action_id="${action_id}" data-n_sessions="0"')}
       data-style="${args->cta_style_2:html:default('background: none;
border: none;
color: white;
font-size: 14px;
text-decoration: underline;
display: inline-block;
')}">
      ${args->cta_text_2:default('No, thanks')}
    </a>
  </div>

  <!-- ✅ Minimal Close Button -->
  ${block->with_close_button:default(1)}
  <div data-style="${args->close_button_style:html:default('position: absolute;
top: 10px;
right: 10px;
z-index: 99;
')}">
    ${args->close_button:default('<div onmouseenter="this.style.backgroundColor=this.style.outlineColor" onmouseleave="this.style.backgroundColor=this.style.textDecorationColor" style="display: inline-block; vertical-align: text-bottom; width: 17px; height: 17px; box-sizing: border-box; border-radius: 50%; border: 0px solid; -webkit-box-shadow: none; padding: 2px; background-color: rgba(0, 0, 0, 0); text-decoration-color: rgba(0, 0, 0, 0); outline-color: rgb(206, 54, 64); outline-width: 7px; color: rgb(242, 242, 242); cursor: pointer; transition: 0.3s;" class="$personyze_button_dont_show_again" data-action_id="${action_id}"><div style="display: block; width: 100%; height: 100%; transition: 0.3s; border-radius: 50%; background-image: linear-gradient(-45deg, transparent 0%, transparent 47%, currentcolor 47%, currentcolor 55%, transparent 55%, transparent 100%), linear-gradient(45deg, transparent 0%, transparent 47%, currentcolor 47%, currentcolor 55%, transparent 55%, transparent 100%);"></div></div>')}
  </div>
</div>

<!-- ✅ PERSONYZE MENU OPTIONS -->

${menu name='Banner Container', icon='th-large'}
	${menu args->background_color name='Background Color', type='color'}
	${menu args->box_size name='Box Width (max-width)', type='css', param='with_responsive=1'}
${menu name='Text Settings', icon='font'}
	${menu block->with_tagline name='Show Tagline'}
	${menu args->tagline name='Tagline Text'}
	${menu args->tagline_style name='Tagline Style', type='css', param='with_responsive=1'}
	${menu block->with_headline name='Show Headline'}
	${menu args->headline name='Headline Text'}
	${menu args->headline_style name='Headline Style', type='css', param='with_responsive=1'}
	${menu block->with_description name='Show Description'}
	${menu args->description name='Description Text'}
	${menu args->description_style name='Description Style', type='css', param='with_responsive=1'}
${menu name='CTA Button', icon='hand-o-up'}
	${menu block->with_cta name='Show Primary CTA'}
	${menu args->cta_text name='CTA Button Text'}
	${menu args->cta_link name='CTA Link', type='a_attrs'}
	${menu args->cta_style name='CTA Button Style', type='css', param='with_responsive=1'}
	${menu args->cta_icon_class name='Icon', type='icon'}
	${menu args->cta_icon_style name='Icon Style', type='css'}
	${menu args->cta_icon_position name='Icon Position', type='select', param='options=[["Before text","icon-left"],["After text","icon-right"]]'}
	${menu block->with_secondary_cta name='Show Secondary CTA'}
	${menu args->cta_text_2 name='Secondary CTA Text'}
	${menu args->cta_link_2 name='Secondary CTA Link', type='a_attrs'}
	${menu args->cta_style_2 name='Secondary CTA Style', type='css', param='with_responsive=1'}
${menu name='Close Button', icon='times-circle'}
	${menu block->with_close_button name='Show Close Button'}
	${menu args->close_button_style name='Close Button Position', type='css', param='with_responsive=1'}
	${menu args->close_button name='Close Button HTML', type='dontshowagain'}
```


## Promo message



```
<div class="$responsive" data-style="background-color: transparent; padding: 0;">

  <div data-style="${args->box_style:html:default('padding: 30px 20px;
border-radius: 12px;
max-width: 600px;
margin: 0 auto;
font-family: Arial, sans-serif;
color: white;
text-align: center;
position: relative;
overflow: hidden;
background-color: rgba(15,15,31,0.95);
background-image: url(https://cdn.personyze.com/upload/362/58f2fab3982ab06c.png);
background-size: cover;
background-position: center;
')}">

    <!-- ❌ Close Button -->
    ${block->with_close_button:default(1)}
    <div data-style="${args->close_button_style:html:default('position: absolute;
top: 10px;
right: 10px;
z-index: 10;')}">
      ${args->close_button:default('<div onmouseenter="this.style.backgroundColor=this.style.outlineColor" onmouseleave="this.style.backgroundColor=this.style.textDecorationColor" style="display: inline-block; vertical-align: text-bottom; width: 24px; height: 24px; box-sizing: border-box; border-radius: 50%; border: 0px solid; -webkit-box-shadow: rgba(255, 255, 255, 0.2) 0px 1px 0px inset, rgba(0, 0, 0, 0.2) 0px 1px 2px; padding: 5px; background-color: rgba(195, 195, 195, 0.46); text-decoration-color: rgba(195, 195, 195, 0.46); outline-color: rgb(206, 54, 64); outline-width: 10px; color: rgb(252, 250, 250); cursor: pointer; transition: 0.3s;" class="$personyze_button_dont_show_again" data-action_id="${action_id}"><div style="display: block; width: 100%; height: 100%; transition: 0.3s; border-radius: 50%; background-image: linear-gradient(-45deg, transparent 0%, transparent 46%, currentcolor 46%, currentcolor 56%, transparent 56%, transparent 100%), linear-gradient(45deg, transparent 0%, transparent 46%, currentcolor 46%, currentcolor 56%, transparent 56%, transparent 100%);"></div></div>')}
    </div>

    <!-- ? Headline Block -->
    ${block->with_text:default(1)}
    <div>
      <div data-style="${args->topline_style:html:default('font-size: 18px; color: #ffbcbc; margin-bottom: 10px;')}">
        ${args->topline:default(Wait)}
      </div>
      <div data-style="${args->headline_style:html:default('font-size: 26px; color: #ff5c5c; font-weight: bold; margin-bottom: 15px;')}">
        ${args->headline:default(END OF YEAR SALE IS NOW ON)}
      </div>
      <div data-style="${args->subheadline_style:html:default('font-size: 18px; color: white; margin-bottom: 20px;')}">
        ${args->subheadline:default('Get <b>20%</b> off everything!')}
      </div>
    </div>

    <!-- ✅ Copy Coupon CTA -->
    ${block->copy_mode:default(1)}
    <button onclick="var code=document.getElementById('pzy-discount-code').innerText; navigator.clipboard.writeText(code); var msg=document.getElementById('pzy-copied-msg'); if(msg){ msg.style.display='block'; setTimeout(function(){msg.style.display='none';},2000); }"
      data-style="${args->cta_style:html:default('background-color: #ea4c5e;
color: white;
font-weight: bold;
font-size: 16px;
padding: 14px 32px;
border-radius: 6px;
border: none;
cursor: pointer;
margin-bottom: 15px;
text-decoration: none;')}">
      <span id="pzy-discount-code">${args->discount_code:default(SAVE20)}</span>
    </button>

    <!-- ✅ Link Button CTA -->
    ${block->link_mode:default(0)}
    <a ${args->cta_link:default('href="#"')}
      data-style="${args->cta_style:html}">
      ${args->cta_text:default(CLAIM MY DISCOUNT)}
    </a>

    <!-- ✨ Copied Message (copy mode only) -->
    ${block->copy_mode:default(1)}
    <div id="pzy-copied-msg" data-style="${args->copied_style:html:default('display: none;
font-size: 13px;
color: #b2ffb2;')}">
      ${args->copied_message:default(Copied! Use this code at checkout.)}
    </div>

  </div>
</div>

<!-- ✅ PERSONYZE MENU OPTIONS -->

${menu name='Layout & Background', icon='th-large'}
	${menu args->box_style name='Box Style', type='css', param='with_responsive=1'}
${menu name='Headline Block', icon='font'}
	${menu block->with_text name='Show Headline Block'}
	${menu args->topline name='Topline Text'}
	${menu args->topline_style name='Topline Style', type='css', param='with_responsive=1'}
	${menu args->headline name='Headline Text'}
	${menu args->headline_style name='Headline Style', type='css', param='with_responsive=1'}
	${menu args->subheadline name='Subheadline Text'}
	${menu args->subheadline_style name='Subheadline Style', type='css', param='with_responsive=1'}
${menu name='CTA (Copy Coupon Button)', icon='check-circle'}
	${menu block->copy_mode name='Use Copy Coupon Button'}
	${menu args->discount_code name='Discount Code'}
	${menu args->copied_message name='Copied Message Text'}
	${menu args->copied_style name='Copied Message Style', type='css', param='with_responsive=1'}
	${menu args->cta_style name='Button Style', type='css', param='with_responsive=1'}
${menu name='CTA (Link Button)', icon='external-link'}
	${menu block->link_mode name='Use Link Button'}
	${menu args->cta_text name='CTA Link Text'}
	${menu args->cta_link name='CTA Link URL', type='a_attrs'}
	${menu args->cta_style name='Button Style', type='css', param='with_responsive=1'}
${menu name='Close Button', icon='times-circle'}
	${menu block->with_close_button name='Show Close Button'}
	${menu args->close_button_style name='Close Button Style', type='css', param='with_responsive=1'}
	${menu args->close_button name='Close Button', type='dontshowagain'}
```


## Message box



```
<div class="$responsive" data-style="box-sizing:border-box; position:relative; ${args->style:html:default('background-color: #0b1545;
color: white;
text-align: center;
padding-top: 40px;
padding-right: 20px;
padding-bottom: 40px;
padding-left: 20px;
border: 3px none white;
max-width: 600px;
margin-top: 40px;
margin-right: auto;
margin-bottom: 40px;
margin-left: auto;
border-radius: 8px;
font-family: Arial, sans-serif;
')}">

	<!-- Close Button -->
	${block->with_close_button:default(0)}
	<div data-style="position:absolute; z-index:1; cursor:pointer; ${args->close_button_style:html:default('top: 10px;
right: 10px;
')}">
		${args->close_button:default('<div onmouseenter="this.style.backgroundColor=this.style.outlineColor" onmouseleave="this.style.backgroundColor=this.style.textDecorationColor" style="display: inline-block; width: 24px; height: 24px; border-radius: 50%; background-color: rgb(207, 120, 58); text-decoration-color: rgb(207, 120, 58); outline-color: rgb(206, 54, 64); color: #fff; cursor: pointer; transition: all 0.3s ease;"><div style="width: 100%; height: 100%; border-radius: 50%; background-image: linear-gradient(-45deg, transparent 0%, transparent 46%, currentcolor 46%, currentcolor 56%, transparent 56%, transparent 100%), linear-gradient(45deg, transparent 0%, transparent 46%, currentcolor 46%, currentcolor 56%, transparent 56%, transparent 100%);"></div></div>')}
	</div>

	<!-- Main Content -->
	${block->with_text:default(1)}
	<div data-style="${args->text_1_style:html:default('text-align: center;
')}">
		<div style="width:100%; height:auto; overflow:auto">
			<div data-style="${args->line_1_style:html:default('font-size: 36px;
font-weight: bold;
margin-bottom: 15px;
')}">
				${args->line_1:default(GET 50% OFF)}
			</div>
			<div data-style="${args->line_2_style:html:default('font-size: 16px;
line-height: 1.5;
margin-bottom: 25px;
')}">
				${args->line_2:default('Get 50% off any of our plans today.<br />
Prices go back up at midnight!')}
			</div>
		</div>
	</div>

	<!-- Button(s) -->
	${block->with_button_1:default(1)}
	<div style="text-align:center;">
		<a ${args->href:default('href="#"')}
		   data-style="${args->button_text_style:html:default('background-color: #2d7ff9;
color: white;
padding-top: 14px;
padding-right: 30px;
padding-bottom: 14px;
padding-left: 30px;
text-decoration: none;
font-weight: bold;
border-radius: 25px;
font-size: 16px;
display: inline-block;
')}">
			${args->button_t:default(Shop now)}
		</a>
	</div>

	${block->with_button_2:default(1)}
	<div style="text-align:center;">
		<a ${args->href_2:default('href="javascript:" class="$personyze_button_dont_show_again" data-action_id="${action_id}" data-n_sessions="0"')}
		   data-style="${args->button_text_style_2:html:default('margin-top: 10px;
display: inline-block;
font-size: 12px;
color: #aaa;
')}">
			${args->button_t_2:default(Maybe later)}
		</a>
	</div>

	<!-- Optional Banner-Wide Link -->
	${block->with_banner_href:default(0)}
	<a ${args->banner_href:default('href=""')} style="position:absolute; display:block; left:0; top:0; width:100%; height:100%"></a>
</div>

<!-- MENU ITEMS -->

${menu name='Box Style', icon='th-large'}
	${menu args->style name='Box style', type='css', param='with_responsive=1'}
${menu name='Text Content', icon='bars'}
	${menu block->with_text name='Show text'}
	${menu args->text_1_style name='Text 1 container style', type='css', param='with_responsive=1'}
	${menu args->line_1 name='Headline text'}
	${menu args->line_1_style name='Headline style', type='css', param='with_responsive=1'}
	${menu args->line_2 name='Subtext'}
	${menu args->line_2_style name='Subtext style', type='css', param='with_responsive=1'}
${menu name='Button 1', icon='hand-o-up'}
	${menu block->with_button_1 name='Show main button'}
	${menu args->button_t name='Main button text'}
	${menu args->href name='Main button URL', type='a_attrs'}
	${menu args->button_text_style name='Main button style', type='css', param='with_responsive=1'}
${menu name='Button 2', icon='hand-o-up'}
	${menu block->with_button_2 name='Show second button'}
	${menu args->button_t_2 name='Second button text'}
	${menu args->href_2 name='Second button URL', type='a_attrs'}
	${menu args->button_text_style_2 name='Second button style', type='css', param='with_responsive=1'}
${menu name='Close Button', icon='times-circle'}
	${menu block->with_close_button name='Show close button'}
	${menu args->close_button_style name='Close button style', type='css', param='with_responsive=1'}
	${menu args->close_button name='Close button', type='dontshowagain'}
${menu name='Whole Banner Link', icon='external-link'}
	${menu block->with_banner_href name='Whole banner link'}
	${menu args->banner_href name='URL', type='a_attrs'}
```


## Promotion box



```
<div class="$responsive" data-style="${args->box_style:html:default('
background-color: #0c1222;
color: white;
border-radius: 12px;
padding: 30px 20px;
max-width: 320px;
margin: 0 auto;
font-family: Arial, sans-serif;
text-align: center;
position: relative;
')}">

  <!-- Close Button -->
  ${block->with_close_button:default(1)}
  <div data-style="${args->close_button_style:html:default('position: absolute;
top: 10px;
right: 10px;
z-index: 1;
')}">
    ${args->close_button:default('<div onmouseenter="this.style.backgroundColor=this.style.outlineColor" onmouseleave="this.style.backgroundColor=this.style.textDecorationColor" style="display: inline-block; vertical-align: text-bottom; width: 24px; height: 24px; box-sizing: border-box; border-radius: 50%; border: 0px solid; -webkit-box-shadow: none; padding: 2px; background-color: rgba(0, 0, 0, 0); text-decoration-color: rgba(0, 0, 0, 0); outline-color: rgb(206, 54, 64); outline-width: 6px; color: rgb(254, 246, 246); cursor: pointer; transition: 0.3s;" class="$personyze_button_dont_show_again" data-action_id="${action_id}"><div style="display: block; width: 100%; height: 100%; transition: 0.3s; border-radius: 50%; background-image: linear-gradient(-45deg, transparent 0%, transparent 48%, currentcolor 48%, currentcolor 54%, transparent 54%, transparent 100%), linear-gradient(45deg, transparent 0%, transparent 48%, currentcolor 48%, currentcolor 54%, transparent 54%, transparent 100%);"></div></div>')}
  </div>

  <!-- Product Image -->
  <div style="margin-bottom: 20px;">
    <img src="${args->product_img:html:default('https://cdn.personyze.com/upload/362/12c399634f8bb5c5.jpeg')}"
         data-style="${args->product_img_style:html:default('max-width: 180px;
height: auto;
display: block;
margin-top: 0;
margin-right: auto;
margin-bottom: 0;
margin-left: auto;
')}">
  </div>

  <!-- Label -->
  <div data-style="${args->label_style:html:default('
font-size: 11px;
text-transform: uppercase;
color: #ccc;
letter-spacing: 1px;
margin-bottom: 10px;
')}">
    ${args->label:default(New Arrival)}
  </div>

  <!-- Headline -->
  <div data-style="${args->headline_style:html:default('font-size: 18px;
font-weight: bold;
line-height: 1.4;
margin-bottom: 12px;
')}">
    ${args->headline:default(Apple AirPods Max)}
  </div>

  <!-- Description -->
  <div data-style="${args->desc_style:html:default('font-size: 13px;
color: #aaa;
line-height: 1.6;
margin-bottom: 20px;
')}">
    ${args->description:default(New colors available)}
  </div>

  <!-- CTA Button -->
  ${block->with_cta:default(1)}
  <a ${args->cta_link:default('href="#"')}
     data-style="${args->cta_style:html:default('display: inline-block;
background-color: white;
color: black;
font-weight: bold;
padding-top: 10px;
padding-right: 20px;
padding-bottom: 10px;
padding-left: 20px;
border-radius: 4px;
font-size: 13px;
text-decoration: none;
')}">
    ${args->cta_text:default(SHOP NOW)}
  </a>
</div>

<!-- ✅ PERSONYZE MENU OPTIONS -->

${menu name='Container', icon='th-large'}
	${menu args->box_style name='Box Style', type='css', param='with_responsive=1'}
${menu name='Product Image', icon='image'}
	${menu args->product_img name='Product Image URL', type='media_url'}
	${menu args->product_img_style name='Product Image Style', type='css', param='with_responsive=1'}
${menu name='Label', icon='tag'}
	${menu args->label name='Label Text'}
	${menu args->label_style name='Label Style', type='css', param='with_responsive=1'}
${menu name='Headline', icon='header'}
	${menu args->headline name='Headline Text'}
	${menu args->headline_style name='Headline Style', type='css', param='with_responsive=1'}
${menu name='Description', icon='file-text'}
	${menu args->description name='Description Text'}
	${menu args->desc_style name='Description Style', type='css', param='with_responsive=1'}
${menu name='CTA Button', icon='hand-o-up'}
	${menu block->with_cta name='Show CTA Button'}
	${menu args->cta_text name='CTA Button Text'}
	${menu args->cta_link name='CTA Link URL', type='a_attrs'}
	${menu args->cta_style name='CTA Button Style', type='css', param='with_responsive=1'}
${menu name='Close Button', icon='times-circle'}
	${menu block->with_close_button name='Show Close Button'}
	${menu args->close_button_style name='Close Button Style', type='css', param='with_responsive=1'}
	${menu args->close_button name='Close Button', type='dontshowagain'}
```


## Promotion box



```
<div class="$responsive" data-style="${args->box_style:html:default('background-image: url(''https://cdn.personyze.com/upload/362/d1e04fbcc2e445de.png'');
background-size: cover;
background-position: center;
color: white;
padding-top: 30px;
padding-right: 20px;
padding-bottom: 30px;
padding-left: 20px;
border-radius: 12px;
max-width: 250px;
margin-top: 0;
margin-right: auto;
margin-bottom: 0;
margin-left: auto;
font-family: Arial, sans-serif;
position: relative;
text-align: center;
background-color: rgb(14, 8, 8);
')}">

  <!-- Close Button -->
  ${block->with_close_button:default(1)}
  <div data-style="${args->close_button_style:html:default('position: absolute;
top: 10px;
right: 10px;
z-index: 1;
')}">
    ${args->close_button:default('<div onmouseenter="this.style.backgroundColor=this.style.outlineColor" onmouseleave="this.style.backgroundColor=this.style.textDecorationColor" style="display: inline-block; vertical-align: text-bottom; width: 24px; height: 24px; box-sizing: border-box; border-radius: 50%; border: 0px solid; -webkit-box-shadow: rgba(255, 255, 255, 0.2) 0px 1px 0px inset, rgba(0, 0, 0, 0.2) 0px 1px 2px; padding: 6px; background-color: rgba(206, 187, 187, 0.36); text-decoration-color: rgba(206, 187, 187, 0.36); outline-color: rgb(206, 54, 64); outline-width: 15px; color: rgb(238, 238, 238); cursor: pointer; transition: 0.3s;" class="$personyze_button_dont_show_again" data-action_id="${action_id}"><div style="display: block; width: 100%; height: 100%; transition: 0.3s; border-radius: 50%; background-image: linear-gradient(-45deg, transparent 0%, transparent 43%, currentcolor 43%, currentcolor 59%, transparent 59%, transparent 100%), linear-gradient(45deg, transparent 0%, transparent 43%, currentcolor 43%, currentcolor 59%, transparent 59%, transparent 100%);"></div></div>')}
  </div>

  <!-- Logo / Brand -->
  <div data-style="${args->logo_style:html:default('font-size: 16px;
font-weight: bold;
margin-bottom: 10px;
color: white;
')}">
    ${args->logo_text:default('@Personzye')}
  </div>

  <!-- Headline -->
  <div data-style="${args->headline_style:html:default('
font-size: 14px;
text-transform: uppercase;
letter-spacing: 1px;
margin-bottom: 10px;
font-weight: bold;
')}">
    ${args->headline:default(4th of July Sale)}
  </div>

  <!-- Main Offer -->
  <div data-style="${args->main_offer_style:html:default('
font-size: 38px;
font-weight: bold;
margin-bottom: 15px;
')}">
    ${args->main_offer:default(30% OFF)}
  </div>

  <!-- Subheadline -->
  <div data-style="${args->subheadline_style:html:default('
font-size: 13px;
margin-bottom: 25px;
color: white;
')}">
    ${args->subheadline:default(Sign up to lock in your 30% off)}
  </div>

  <!-- Primary CTA -->
  ${block->with_primary_cta:default(1)}
  <div style="margin-bottom: 15px;">
    <a ${args->primary_cta_link:default('href="#"')}
       data-style="${args->primary_cta_style:html:default('
background-color: white;
color: #1a1a1a;
font-weight: bold;
font-size: 14px;
border-radius: 30px;
padding: 12px 30px;
text-decoration: none;
display: inline-block;
')}">
      ${args->primary_cta_text:default(YES)}
    </a>
  </div>

  <!-- Secondary CTA -->
  ${block->with_secondary_cta:default(1)}
  <div>
    <a ${args->secondary_cta_link:default('href="javascript:" class="$personyze_button_dont_show_again" data-action_id="${action_id}" data-n_sessions="0"')}
       data-style="${args->secondary_cta_style:html:default('font-size: 13px;
color: white;
text-decoration: underline;
font-weight: normal;
')}">
      ${args->secondary_cta_text:default(NO)}
    </a>
  </div>
</div>

<!-- ✅ PERSONYZE MENU OPTIONS -->

${menu name='Background Style', icon='picture-o'}
	${menu args->box_style name='Box style', type='css', param='with_responsive=1'}
${menu name='Brand', icon='flag'}
	${menu args->logo_text name='Logo text'}
	${menu args->logo_style name='Logo style', type='css', param='with_responsive=1'}
${menu name='Headline', icon='header'}
	${menu args->headline name='Headline'}
	${menu args->headline_style name='Headline style', type='css', param='with_responsive=1'}
${menu name='Main Offer', icon='percent'}
	${menu args->main_offer name='Main Offer Text'}
	${menu args->main_offer_style name='Main Offer Style', type='css', param='with_responsive=1'}
${menu name='Subheadline', icon='bars'}
	${menu args->subheadline name='Subheadline'}
	${menu args->subheadline_style name='Subheadline style', type='css', param='with_responsive=1'}
${menu name='Primary CTA', icon='check-circle'}
	${menu block->with_primary_cta name='Show Primary CTA'}
	${menu args->primary_cta_text name='CTA Text'}
	${menu args->primary_cta_link name='CTA URL', type='a_attrs'}
	${menu args->primary_cta_style name='CTA Style', type='css', param='with_responsive=1'}
${menu name='Secondary CTA', icon='times-circle'}
	${menu block->with_secondary_cta name='Show Secondary CTA'}
	${menu args->secondary_cta_text name='Secondary CTA Text'}
	${menu args->secondary_cta_link name='Secondary CTA URL', type='a_attrs'}
	${menu args->secondary_cta_style name='Secondary CTA Style', type='css', param='with_responsive=1'}
${menu name='Close Button', icon='close'}
	${menu block->with_close_button name='Show close button'}
	${menu args->close_button_style name='Close button style', type='css', param='with_responsive=1'}
	${menu args->close_button name='Close button', type='dontshowagain'}
```


## Banner with decorative shape

Options for mobile/desktop Image position and decorative shape

```
<div class="$responsive" data-style="box-sizing: border-box; position: relative; ${args->box_style:html:default('background-color: white;
border-radius: 10px;
padding: 20px;
max-width: 1200px;
margin-top: 0;
margin-right: auto;
margin-bottom: 0;
margin-left: auto;
box-shadow: 0 2px 10px rgba(0,0,0,0.1);
font-family: Arial, sans-serif;
')}" data-mobile-img-order="${args->mobile_img_order:html:default(image_top_of_text)}">

  <style>
    @media (max-width: 768px) {
      .responsive-flex-container {
        flex-direction: column;
        align-items: center;
        text-align: center;
      }
      .image_top_of_text .image-container,
      .image_top_left .image-container {
        order: -1 !important;
        text-align: center;
      }
      .image_bottom_of_text .image-container,
      .image_bottom_left .image-container {
        order: 2 !important;
        text-align: center;
      }
      .cta-left {
        text-align: center !important;
      }
    }
    @media (min-width: 769px) {
      .image_top_left .image-container,
      .image_bottom_left .image-container {
        order: -1;
      }
      .image_top_of_text .image-container,
      .image_bottom_of_text .image-container {
        order: 1;
      }
    }
  </style>

  <div class="responsive-flex-container ${args->mobile_img_order:html}" style="display: flex; flex-wrap: wrap; align-items: center; justify-content: space-between; gap: 20px;">
    ${block->with_image:default(1)}
    <div class="image-container" style="flex: 1 1 40%; min-width: 250px; text-align: right; position: relative;">
      <img src="${args->side_img:html:default('https://cdn.personyze.com/upload/362/b0aa717b038e0d99.png')}"
           data-style="${args->side_img_style:html:default('max-width: 100%;
height: 300px;
border-radius: 8px;
')}" alt="Image">
    </div>

    <!-- Left Content -->
    <div style="flex: 1 1 55%; min-width: 300px; position: relative;">
      <div data-style="${args->headline_style:html:default('font-size: 28px;
font-weight: bold;
color: #002D9C;
margin-bottom: 10px;
')}">
        ${args->headline:default('Drive Growth with <span style="color:#56B86E">Smarter SaaS</span>')}
      </div>
      <div data-style="${args->subheadline_style:html:default('font-size: 20px;
color: #002D9C;
margin-bottom: 10px;
')}">
        ${args->subheadline:default(Personalize your customer experience and increase conversion rates)}
      </div>
      <div data-style="${args->supporting_text_style:html:default('font-size: 18px;
color: #002D9C;
')}">
        ${args->supporting_text:default('Join <span style="color:#56B86E; font-weight:bold;">1,000+</span> successful SaaS teams')}
      </div>

      <!-- CTA Button -->
      ${block->with_cta:default(1)}
      <div class="cta-left" style="margin-top: 20px; text-align: left;">
        <a ${args->cta_link:default('href="#"')}
           data-style="${args->cta_style:html:default('background-color: #002D9C;
color: white;
padding-top: 12px;
padding-right: 28px;
padding-bottom: 12px;
padding-left: 28px;
border-radius: 30px;
text-decoration: none;
display: inline-block;
font-weight: bold;
font-size: 16px;
')}">
          ${args->cta_text:default(Get Started)}
        </a>
      </div>

      <!-- Secondary Button -->
      ${block->with_cta_2:default(1)}
      <div class="cta-left" style="margin-top: 12px; text-align: left;">
        <a ${args->cta_link_2:default('href="javascript:" class="$personyze_button_dont_show_again" data-action_id="${action_id}" data-n_sessions="0"')}
           data-style="${args->cta_style_2:html:default('background: none;
border: none;
color: #666;
font-size: 14px;
text-decoration: underline;
display: inline-block;
margin-top: 10px;
')}" role="button">
          ${args->cta_text_2:default(Maybe Later)}
        </a>
      </div>

      <!-- Abstract Graphic Elements -->
      ${block->with_shape:default(1)}
      <div data-style="${args->shape_style:html:default('position: absolute;
top: -37px;
left: -20px;
width: 80px;
height: 80px;
background-color: #56B86E;
clip-path: polygon(0 0, 30% 0, 0 100%);
opacity: 0.4;
')}"></div>
      ${block->with_shape_2:default(1)}
      <div data-style="${args->shape_style_2:html:default('position: absolute;
bottom: -20px;
left: 50px;
width: 50px;
height: 50px;
background-color: #FFC107;
border-radius: 50%;
opacity: 0.3;
')}"></div>
      ${block->with_shape_3:default(1)}
      <div data-style="${args->shape_style_3:html:default('position: absolute;
bottom: -60px;
right: -30px;
width: 60px;
height: 60px;
background-color: #00B8D9;
transform: rotate(45deg);
opacity: 0.25;
')}"></div>
    </div>
  </div>

  <!-- Close Button -->
  ${block->with_close_button:default(1)}
  <div data-style="${args->close_button_style:html:default('position: absolute;
top: 10px;
right: 10px;
z-index: 99;
')}">
    ${args->close_button:default('<div onmouseenter="this.style.backgroundColor=this.style.outlineColor" onmouseleave="this.style.backgroundColor=this.style.textDecorationColor" style="display: inline-block; vertical-align: text-bottom; width: 24px; height: 24px; box-sizing: border-box; border-radius: 50%; border: 0px solid; -webkit-box-shadow: none; padding: 5px; background-color: rgba(231, 231, 231, 0.4); text-decoration-color: rgba(231, 231, 231, 0.4); outline-color: rgb(206, 54, 64); outline-width: 8px; color: rgb(10, 4, 4); cursor: pointer; transition: 0.3s;" class="$personyze_button_dont_show_again" data-action_id="${action_id}"><div style="display: block; width: 100%; height: 100%; transition: 0.3s; border-radius: 50%; background-image: linear-gradient(-45deg, transparent 0%, transparent 47%, currentcolor 47%, currentcolor 55%, transparent 55%, transparent 100%), linear-gradient(45deg, transparent 0%, transparent 47%, currentcolor 47%, currentcolor 55%, transparent 55%, transparent 100%);"></div></div>')}
  </div>
</div>


<!-- ✅ PERSONYZE MENU OPTIONS -->

${menu name='Box Style', icon='th-large'}
	${menu args->box_style name='Box Style', type='css', param='with_responsive=1'}
${menu name='Headline Block', icon='font'}
	${menu args->headline name='Headline Text'}
	${menu args->headline_style name='Headline Style', type='css', param='with_responsive=1'}
	${menu args->subheadline name='Subheadline Text'}
	${menu args->subheadline_style name='Subheadline Style', type='css', param='with_responsive=1'}
	${menu args->supporting_text name='Supporting Text'}
	${menu args->supporting_text_style name='Supporting Text Style', type='css', param='with_responsive=1'}
${menu name='CTA Button', icon='hand-o-up'}
	${menu block->with_cta name='Show CTA Button'}
	${menu args->cta_text name='CTA Button Text'}
	${menu args->cta_link name='CTA Link URL', type='a_attrs'}
	${menu args->cta_style name='CTA Button Style', type='css', param='with_responsive=1'}
${menu name='Secondary CTA', icon='hand-o-up'}
	${menu block->with_cta_2 name='Show Secondary Button'}
	${menu args->cta_text_2 name='Secondary Button Text'}
	${menu args->cta_link_2 name='Secondary Button Link', type='a_attrs'}
	${menu args->cta_style_2 name='Secondary Button Style', type='css', param='with_responsive=1'}
${menu name='Image', icon='image'}
	${menu block->with_image name='Show Image'}
	${menu args->side_img name='Image URL', type='media_url'}
	${menu args->side_img_style name='Image Style', type='css', param='with_responsive=1'}
	${menu args->mobile_img_order name='Mobile Image Position', type='select', param='options=[["Mobile image on top and desktop right","image_top_of_text"],["Mobile image on bottom and desktop right","image_bottom_of_text"],["Mobile image on top and desktop left","image_top_left"],["Mobile image on bottom and desktop left","image_bottom_left"]]'}
${menu name='Decorative Shapes', icon='paint-brush'}
	${menu block->with_shape name='Show Shape 1'}
	${menu args->shape_style name='Shape 1 Style', type='css', param='with_responsive=1'}
	${menu block->with_shape_2 name='Show Shape 2'}
	${menu args->shape_style_2 name='Shape 2 Style', type='css', param='with_responsive=1'}
	${menu block->with_shape_3 name='Show Shape 3'}
	${menu args->shape_style_3 name='Shape 3 Style', type='css', param='with_responsive=1'}
${menu name='Close Button', icon='times-circle'}
	${menu block->with_close_button name='Show Close Button'}
	${menu args->close_button_style name='Close Button Style', type='css', param='with_responsive=1'}
	${menu args->close_button name='Close Button', type='dontshowagain'}
```


## Full width banner with shapes



```
<!-- ✅ SAAS Webinar Banner with Abstract Shapes + Logo Position -->
<div class="$responsive" data-style="${args->box_style:html:default('background-color: rgba(61, 37, 80, 0.9);
border-radius: 0px;
padding: 40px;
width: 100vw;
max-width: 100%;
margin-top: 0;
margin-right: auto;
margin-bottom: 0;
margin-left: auto;
color: white;
font-family: Arial, sans-serif;
position: relative;
overflow: hidden;
')}">

  <style>
    @media (max-width: 768px) {
      .webinar-banner-flex {
        flex-direction: column !important;
        text-align: center;
      }
      .webinar-banner-logo {
        text-align: center !important;
        margin-bottom: 16px;
      }
      .webinar-banner-buttons {
        flex-direction: column;
        gap: 12px;
        align-items: center;
      }
    }

    .webinar-banner-logo.left   { text-align: left; }
    .webinar-banner-logo.center { text-align: center; }
    .webinar-banner-logo.right  { text-align: right; }

    .webinar-banner-buttons {
      display: flex;
      gap: 16px;
      flex-wrap: wrap;
      margin-top: 30px;
    }

    .webinar-banner-buttons a {
      padding: 14px 28px;
      border-radius: 8px;
      font-weight: bold;
      font-size: 16px;
      text-decoration: none;
      display: inline-block;
    }

    .btn-primary {
      background-color: #007bff;
      color: white;
    }

    .btn-secondary {
      background-color: transparent;
      border: 2px solid white;
      color: white;
    }

    .abstract-shape {
      position: absolute;
      z-index: 0;
      opacity: 0.3;
    }
  </style>

  <div class="webinar-banner-flex" style="display: flex; flex-wrap: wrap; align-items: center; justify-content: space-between; gap: 20px; position: relative; z-index: 1;">

    <!-- ✅ Logo -->
    ${block->with_logo:default(1)}
    <div class="webinar-banner-logo ${args->logo_position:html:default(left)}" style="flex: 1 1 100%; margin-bottom: 20px;">
      <img src="${args->logo_url:html:default('https://cdn.personyze.com/upload/362/836ce71c4644386c.png')}" data-style="${args->logo_style:html:default('max-height: 40px;
')}" alt="Logo">
    </div>

    <!-- ✅ Main Content -->
    <div style="flex: 1 1 100%;">
      <div data-style="${args->headline_style:html:default('font-size: 36px;
font-weight: bold;
margin-bottom: 20px;
')}">
        ${args->headline:default(Join our Live SaaS Webinar)}
      </div>
      <div data-style="${args->description_style:html:default('font-size: 18px;
line-height: 1.5;
')}">
        ${args->description:default(Discover how to personalize your SaaS experience and boost user engagement in our upcoming live webinar.)}
      </div>

      <!-- ✅ Buttons -->
      ${block->with_cta:default(1)}
      <div class="webinar-banner-buttons">
        <a ${args->cta_link:default('href="#"')} data-style="${args->cta_style:html}" class="btn-primary">${args->cta_text:default(Register Now)}</a>
        ${block->with_cta_2:default(1)}
        <a ${args->cta_link_2:default('href="#"')} data-style="${args->cta_style_2:html}" class="btn-secondary">${args->cta_text_2:default(Maybe Later)}</a>
      </div>
    </div>
  </div>

  <!-- ✅ Abstract Shapes -->
  ${block->with_shape:default(1)}
  <div class="abstract-shape shape-1" data-style="${args->shape_style_1:html:default('top: 0;
left: 0;
width: 80px;
height: 80px;
background-color: rgb(0, 256, 151);
clip-path: polygon(0 0, 100% 0, 0 100%);
')}"></div>
  ${block->with_shape_2:default(1)}
  <div class="abstract-shape shape-2" data-style="${args->shape_style_2:html:default('bottom: 0;
right: 0;
width: 80px;
height: 80px;
background-color: #6f42c1;
clip-path: polygon(100% 100%, 0 100%, 100% 0);
')}"></div>

  <!-- ✅ Close Button -->
  ${block->with_close_button:default(1)}
  <div data-style="${args->close_button_style:html:default('position: absolute;
top: 10px;
right: 10px;
z-index: 999;
')}">
    ${args->close_button:default('<div onmouseenter="this.style.backgroundColor=this.style.outlineColor" onmouseleave="this.style.backgroundColor=this.style.textDecorationColor" style="display: inline-block; vertical-align: text-bottom; width: 24px; height: 24px; box-sizing: border-box; border-radius: 50%; border: 0px solid; -webkit-box-shadow: none; padding: 5px; background-color: rgba(0, 0, 0, 0); text-decoration-color: rgba(0, 0, 0, 0); outline-color: rgb(206, 54, 64); outline-width: 6px; color: rgb(255, 252, 252); cursor: pointer; transition: 0.3s;" class="$personyze_button_dont_show_again" data-action_id="${action_id}"><div style="display: block; width: 100%; height: 100%; transition: 0.3s; border-radius: 50%; background-image: linear-gradient(-45deg, transparent 0%, transparent 48%, currentcolor 48%, currentcolor 54%, transparent 54%, transparent 100%), linear-gradient(45deg, transparent 0%, transparent 48%, currentcolor 48%, currentcolor 54%, transparent 54%, transparent 100%);"></div></div>')}
  </div>
</div>

<!-- ✅ PERSONYZE MENU OPTIONS -->

${menu name='Box Style', icon='th-large'}
	${menu args->box_style name='Banner Container Style', type='css', param='with_responsive=1'}
${menu name='Logo', icon='image'}
	${menu block->with_logo name='Show Logo'}
	${menu args->logo_url name='Logo URL', type='media_url'}
	${menu args->logo_style name='Logo Style', type='css', param='with_responsive=1'}
	${menu args->logo_position name='Logo Position', type='select', param='options=[["Left","left"],["Center","center"],["Right","right"]]'}
${menu name='Text', icon='font'}
	${menu args->headline name='Headline Text'}
	${menu args->headline_style name='Headline Style', type='css', param='with_responsive=1'}
	${menu args->description name='Description Text'}
	${menu args->description_style name='Description Style', type='css', param='with_responsive=1'}
${menu name='CTA Buttons', icon='hand-o-up'}
	${menu block->with_cta name='Show Primary CTA'}
	${menu args->cta_text name='Primary CTA Text'}
	${menu args->cta_link name='Primary CTA Link', type='a_attrs'}
	${menu args->cta_style name='Primary CTA Style', type='css', param='with_responsive=1'}
	${menu block->with_cta_2 name='Show Secondary CTA'}
	${menu args->cta_text_2 name='Secondary CTA Text'}
	${menu args->cta_link_2 name='Secondary CTA Link', type='a_attrs'}
	${menu args->cta_style_2 name='Secondary CTA Style', type='css', param='with_responsive=1'}
${menu name='Shapes', icon='paint-brush'}
	${menu block->with_shape name='Show Shape 1'}
	${menu args->shape_style_1 name='Shape 1 Style', type='css', param='with_responsive=1'}
	${menu block->with_shape_2 name='Show Shape 2'}
	${menu args->shape_style_2 name='Shape 2 Style', type='css', param='with_responsive=1'}
${menu name='Close Button', icon='times-circle'}
	${menu block->with_close_button name='Show Close Button'}
	${menu args->close_button_style name='Close Button Style', type='css', param='with_responsive=1'}
	${menu args->close_button name='Close Button HTML', type='dontshowagain'}
```


## Bottom/Top Bar



```
<!-- ✅ Blurred Background Banner with Customizable Background Image and Button Alignment -->
<div class="$responsive" data-style="${args->box_style:html:default('border-radius: 0px;
overflow: hidden;
max-width: 100%;
width: 100%;
margin-top: 0;
margin-right: auto;
margin-bottom: 0;
margin-left: auto;
font-family: Arial, sans-serif;
position: relative;
')}">

  <!-- ✅ Internal CSS -->
  <style>
    @media (max-width: 768px) {
      .blur-banner-layout {
        flex-direction: column;
        text-align: center;
        padding: 20px;
        gap: 12px;
      }
      .blur-banner-logo {
        margin-bottom: 12px;
      }
      .blur-banner-content {
        text-align: center;
      }
      .blur-banner-buttons {
        flex-direction: column;
        align-items: center;
        justify-content: center;
      }
    }

    .blurred-background {
      position: absolute;
      top: 0; left: 0; right: 0; bottom: 0;
      z-index: 1;
    }

    .blur-banner-overlay {
      background-color: ${args->overlay_color:html:default('rgba(0, 0, 0, 0.47)')};
      padding: 24px 32px;
      position: relative;
      z-index: 2;
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 20px;
      flex-wrap: wrap;
    }

    .blur-banner-buttons {
      display: flex;
      flex-wrap: wrap;
      gap: 12px;
    }

    .blur-banner-button {
      display: inline-flex;
      align-items: center;
      justify-content: center;
      font-weight: bold;
      font-size: 14px;
      padding: 12px 20px;
      border-radius: 6px;
      text-decoration: none;
      white-space: nowrap;
    }

    .blur-banner-button.icon-left i { order: -1; margin-right: 8px; }
    .blur-banner-button.icon-right i { order: 1; margin-left: 8px; }
  </style>

  <!-- ✅ Background Image -->
  <div class="blurred-background"
       data-style="${args->bg_style:html:default('background-image: url(''https://cdn.personyze.com/upload/362/73175c19db520d5f.png'');
background-size: contain;
background-position: center;
filter: blur(6px);
background-repeat: repeat;
')}">
  </div>

  <!-- ✅ Foreground Overlay -->
  <div class="blur-banner-layout blur-banner-overlay">

    <!-- ✅ Logo + Text -->
    <div style="flex: 1 1 auto;">
      ${block->with_logo:default(0)}
      <div class="blur-banner-logo">
        <img src="${args->logo_img:html:default('https://cdn.personyze.com/upload/362/personyze-logo-white.png')}"
             data-style="${args->logo_style:html:default('height: 40px; max-width: 120px;')}" alt="Logo">
      </div>

      <div class="blur-banner-content">
        <div data-style="${args->headline_style:html:default('color: white;
font-size: 20px;
font-weight: bold;
margin-bottom: 6px;
')}">
          ${args->headline:default(Join our Live SaaS Webinar)}
        </div>
        <div data-style="${args->desc_style:html:default('color: white;
font-size: 14px;
')}">
          ${args->desc:default('Discover how to personalize your SaaS experience<br />
and boost user engagement in our upcoming live webinar.')}
        </div>
      </div>
    </div>

    <!-- ✅ Buttons Block (moveable) -->
    <div class="blur-banner-buttons" data-style="${args->button_block_style:html:default('text-align: center;
width: sel(173.171875px, auto);
')}">
      ${block->with_cta:default(1)}
      <a class="blur-banner-button ${args->cta_icon_position:html:default(icon-left)}"
         ${args->cta_link:default('href="#"')}
         data-style="${args->cta_style:html:default('background-color: white; color: black;')}" >
        <span>${args->cta_text:default(Learn More)}</span>
        ${if args->cta_icon_class != ''}<i class="$icon ${args->cta_icon_class:html}" style="${args->cta_icon_style:html:default('font-size: 14px;
')}"></i>${end}
      </a>

      ${block->with_cta_2:default(0)}
      <a class="blur-banner-button ${args->cta_icon_position_2:html:default(icon-left)}"
         ${args->cta_link_2:default('href="#"')}
         data-style="${args->cta_style_2:html:default('background-color: transparent; border: 2px solid white; color: white;')}" >
        <span>${args->cta_text_2:default(Maybe Later)}</span>
        ${if args->cta_icon_class_2 != ''}<i class="$icon ${args->cta_icon_class_2:html}" style="${args->cta_icon_style_2:html:default('font-size: 14px;
')}"></i>${end}
      </a>
    </div>
  </div>

  <!-- ✅ Close Button -->
  ${block->with_close_button:default(1)}
  <div data-style="${args->close_button_style:html:default('position: absolute;
top: 10px;
right: 10px;
z-index: 99;
')}">
    ${args->close_button:default('<div class="$personyze_button_dont_show_again" data-action_id="${action_id}" style="display: inline-block; width: 20px; height: 20px; background-color: rgba(255,255,255,0.3); color: white; text-align: center; line-height: 20px; border-radius: 50%; font-size: 16px; cursor: pointer;">×</div>')}
  </div>
</div>

<!-- ✅ PERSONYZE MENU OPTIONS -->

${menu name='Container', icon='th-large'}
	${menu args->box_style name='Outer Container Style', type='css', param='with_responsive=1'}
	${menu args->bg_style name='Background Image CSS (blur, size, etc)', type='css', param='with_responsive=1'}
	${menu args->overlay_color name='Overlay Mask Color', type='color'}
${menu name='Logo Block', icon='image'}
	${menu block->with_logo name='Show Logo'}
	${menu args->logo_img name='Logo Image URL', type='media_url'}
	${menu args->logo_style name='Logo Style', type='css', param='with_responsive=1'}
${menu name='Text Block', icon='font'}
	${menu args->headline name='Headline Text'}
	${menu args->headline_style name='Headline Style', type='css', param='with_responsive=1'}
	${menu args->desc name='Description Text'}
	${menu args->desc_style name='Description Style', type='css', param='with_responsive=1'}
${menu name='Buttons', icon='hand-o-up'}
	${menu args->button_block_style name='Button Container Style', type='css', param='with_responsive=1'}
	${menu block->with_cta name='Show Primary CTA'}
	${menu args->cta_text name='Primary CTA Text'}
	${menu args->cta_link name='Primary CTA Link', type='a_attrs'}
	${menu args->cta_style name='Primary CTA Style', type='css', param='with_responsive=1'}
	${menu args->cta_icon_class name='Primary Icon Class', type='icon'}
	${menu args->cta_icon_style name='Primary Icon Style', type='css'}
	${menu args->cta_icon_position name='Primary Icon Position', type='select', param='options=[["Before Text","icon-left"],["After Text","icon-right"]]'}
	${menu block->with_cta_2 name='Show Secondary CTA'}
	${menu args->cta_text_2 name='Secondary CTA Text'}
	${menu args->cta_link_2 name='Secondary CTA Link', type='a_attrs'}
	${menu args->cta_style_2 name='Secondary CTA Style', type='css', param='with_responsive=1'}
	${menu args->cta_icon_class_2 name='Secondary Icon Class', type='icon'}
	${menu args->cta_icon_style_2 name='Secondary Icon Style', type='css'}
	${menu args->cta_icon_position_2 name='Secondary Icon Position', type='select', param='options=[["Before Text","icon-left"],["After Text","icon-right"]]'}
${menu name='Close Button', icon='times-circle'}
	${menu block->with_close_button name='Show Close Button'}
	${menu args->close_button_style name='Close Button Style', type='css', param='with_responsive=1'}
	${menu args->close_button name='Close Button HTML', type='dontshowagain'}
```


## Animated Image Banner with Optional Overlay

A flexible, full-width image banner with built-in animation effects, click-through tracking, optional text and CTA button overlays, and an optional dark mask to boost text readability on bright images. Ideal for promotions, announcements, or driving conversions.

```
<style>
  /* ✅ Animation Presets */
  @keyframes fadeInUp {
    0% { opacity: 0; transform: translateY(20px); }
    100% { opacity: 1; transform: translateY(0); }
  }
  @keyframes slideInLeft {
    0% { opacity: 0; transform: translateX(-100%); }
    100% { opacity: 1; transform: translateX(0); }
  }
  @keyframes zoomIn {
    0% { transform: scale(0.8); opacity: 0; }
    100% { transform: scale(1); opacity: 1; }
  }
  .anim-fadeInUp { animation: fadeInUp 0.8s ease-out; }
  .anim-slideInLeft { animation: slideInLeft 0.8s ease-out; }
  .anim-zoomIn { animation: zoomIn 0.6s ease-out; }

  .responsive img:hover {
    transform: scale(1.03);
    transition: transform 0.4s ease;
  }
  .responsive:hover {
    box-shadow: 0 10px 25px rgba(0, 0, 0, 0.25);
  }
  .pulse-close {
    animation: pulse 1.8s infinite;
  }
  @keyframes pulse {
    0% { transform: scale(1); }
    50% { transform: scale(1.15); }
    100% { transform: scale(1); }
  }
</style>

<div class="$responsive responsive ${args->animation_class:html:default(anim-fadeInUp)}" data-style="position:relative; display:inline-block; ${args->style:html:default('box-sizing: inherit;
background-image: url(''https://cdn.personyze.com/upload/362/c8e7302d0a03f885.png'');
')}">

  <img src="${args->img_src:html:default('https://cdn.personyze.com/upload/362/26f1e623fa1a34ea.png')}"
       style="display:block; width:auto; height:auto; max-width:100vw; ${args->img_style:html:default('max-width: 500px;
')}">

  ${block->with_mask:default(1)}
  <div style="position:absolute; top:0; left:0; width:100%; height:100%; ${args->mask_style:html:default('background-color: rgba(0, 0, 0, 0.71);
')}"></div>

  ${block->with_close_button:default(1)}
  <div style="position:absolute; cursor:pointer; ${args->close_button_style:html:default('text-align: right;
width: 100%;
top: -10px;
right: -10px;
z-index: 9999;
')}">
    ${args->close_button:default('<div onmouseenter="this.style.backgroundColor=this.style.outlineColor" onmouseleave="this.style.backgroundColor=this.style.textDecorationColor" style="display: inline-block; vertical-align: text-bottom; width: 22px; height: 22px; box-sizing: border-box; border-radius: 50%; border: 0px solid; -webkit-box-shadow: rgba(255, 255, 255, 0.2) 0px 1px 0px inset, rgba(0, 0, 0, 0.2) 0px 1px 2px; padding: 6px; background-color: rgb(248, 186, 49); text-decoration-color: rgb(248, 186, 49); outline-color: rgb(206, 54, 64); outline-width: 15px; color: rgb(255, 255, 255); cursor: pointer; transition: 0.3s;" class="$personyze_button_dont_show_again" data-action_id="${action_id}"><div style="display: block; width: 100%; height: 100%; transition: 0.3s; border-radius: 50%; background-image: linear-gradient(-45deg, transparent 0%, transparent 43%, currentcolor 43%, currentcolor 59%, transparent 59%, transparent 100%), linear-gradient(45deg, transparent 0%, transparent 43%, currentcolor 43%, currentcolor 59%, transparent 59%, transparent 100%);"></div></div>')}
  </div>

  ${block->with_banner_href:default(1)}
  <a ${args->banner_href:default('href="#" target="_blank" data-personyze-click-target=""')}
     style="position:absolute; display:block; left:0; top:0; width:100%; height:100%; z-index:5;"></a>

  ${block->with_text:default(1)}
  <div style="position:absolute; top:0; left:0; width:100%; height:100%; display:flex; flex-direction:column; align-items:center; justify-content:center; text-align:center;">
    <div data-style="${args->title_style:html:default('font-size: 22px;
font-weight: bold;
color: #fff;
margin-bottom: 10px;
')}">
      ${args->title:default(Your Limited-Time Offer)}
    </div>
    ${block->with_cta:default(1)}
    <a ${args->cta_link:default('href="#"')} data-style="${args->cta_style:html:default('background-color: #F8BA31;
color: white;
padding-top: 10px;
padding-right: 20px;
padding-bottom: 10px;
padding-left: 20px;
border-radius: 6px;
font-weight: bold;
font-size: 14px;
text-decoration: none;
display: inline-block;
')}">
      ${args->cta_text:default(Claim Now)}
    </a>
  </div>
</div>

${menu name='Container', icon='th-large', description='Customize overall container style'}
	${menu args->style name='Container Style', description='Style for outer banner container', type='css', param='with_responsive=1'}
${menu name='Image', icon='image', description='Set the banner image and appearance'}
	${menu args->img_src name='Image URL', description='Upload or select banner image', type='media_url'}
	${menu args->img_style name='Image Style', description='Styling for image element', type='css', param='with_responsive=1'}
${menu name='Image Mask', icon='adjust', description='Add a dark overlay to make white text readable'}
	${menu block->with_mask name='Enable Image Mask', description='Overlay the image with a semi-transparent mask'}
	${menu args->mask_style name='Mask Style', description='Customize the mask appearance (e.g., color, opacity)', type='css', param='with_responsive=1'}
${menu name='Click Target', icon='external-link', description='Make banner clickable'}
	${menu block->with_banner_href name='Enable Banner Click', description='Enable full clickable area'}
	${menu args->banner_href name='Click URL', description='Destination when banner is clicked', type='a_attrs'}
${menu name='Close Button', icon='times-circle', description='Add a close (X) button'}
	${menu block->with_close_button name='Show Close Button', description='Show or hide the dismiss button'}
	${menu args->close_button_style name='Close Button Style', description='CSS for close button position/style', type='css', param='with_responsive=1'}
	${menu args->close_button name='Close Button HTML', description='Custom HTML for close button', type='dontshowagain'}
${menu name='Animation Settings', icon='magic', description='Choose how the banner animates on load'}
	${menu args->animation_class name='Animation Type', description='Select animation style or disable', type='select', param='options=[["None",""],["Fade In Up","anim-fadeInUp"],["Slide In Left","anim-slideInLeft"],["Zoom In","anim-zoomIn"]]'}
${menu name='Overlay Text & CTA', icon='font', description='Enable optional title and CTA button'}
	${menu block->with_text name='Show Text Overlay', description='Toggle the overlay text area'}
	${menu args->title name='Overlay Headline', description='Headline text shown over the image'}
	${menu args->title_style name='Overlay Headline Style', description='CSS styling for the overlay text', type='css', param='with_responsive=1'}
	${menu block->with_cta name='Show CTA Button', description='Add a CTA button inside the banner'}
	${menu args->cta_text name='CTA Button Text', description='Label for the CTA button'}
	${menu args->cta_link name='CTA Link', description='Target URL for the CTA button', type='a_attrs'}
	${menu args->cta_style name='CTA Button Style', description='CSS for the CTA button appearance', type='css', param='with_responsive=1'}
```


## Info Banner with CTAs

 clean, responsive banner featuring an info message, primary and secondary call-to-action buttons, and an optional top image for visual impact.

```
<!-- Info Message Banner with CTA Buttons and Optional Top Image -->
<div class="$responsive" data-style="${args->box_style:html:default('background-color: #E7E7E7;
padding: 20px;
border-radius: 8px;
margin: auto;
position: relative;
width: 510.171875px;
height: auto;
')}">

  <!-- Optional Top Image: toggled by block->with_image -->
  ${block->with_image:default(1)}
    <img
      src="${args->image_url:html:default('https://cdn.personyze.com/upload/362/836ce71c4644386c.png')}"
      alt="${args->image_alt:html:default(Top Image)}"
      data-style="${args->image_style:html:default('max-width: 200px;
height: auto;
display: block;
margin-top: auto;
margin-right: auto;
margin-bottom: 20px;
margin-left: auto;
')}"
    />
  ${endblock}

  <div data-style="${args->td_style:html:default('padding: 20px; text-align: center; color: #333; font-size: 14px;')}">
    ${args->content:default('Info Message: Download our FREE Testing Toolkit! Discover how our toolkit can help you optimize your testing process and boost efficiency.')}

    <!-- Primary and Secondary CTA Buttons -->
    ${block->with_cta:default(1)}
    <div style="margin-top: 20px;">
      <a ${args->cta_link:default('href="#"')}
         data-style="${args->cta_style:html:default('display: inline-block;
padding-top: 10px;
padding-right: 20px;
padding-bottom: 10px;
padding-left: 20px;
background-color: #007bff;
color: white;
text-decoration: none;
border-radius: 5px;
')}"
         class="btn-primary"
         title="Primary action button">
         ${args->cta_text:default(GET IT NOW)}
      </a>
      ${block->with_cta_2:default(1)}
      <a ${args->cta_link_2:default('href="#"')}
         data-style="${args->cta_style_2:html:default('display:inline-block; padding: 10px 20px; background-color: gray; color: white; text-decoration: none; border-radius: 5px; margin-left: 10px;')}"
         class="btn-secondary"
         title="Secondary action button: Maybe Later">
         ${args->cta_text_2:default(Maybe Later)}
      </a>
      ${endblock}
    </div>
    ${endblock}

    <!-- Close Button -->
    ${block->with_close_button:default(1)}
    <div data-style="${args->close_button_style:html:default('position: absolute;
top: 8px;
right: 8px;
')}" title="Close this banner">
      ${args->close_button:default('<div onmouseenter="this.style.backgroundColor=this.style.outlineColor" onmouseleave="this.style.backgroundColor=this.style.textDecorationColor" style="display: inline-block; vertical-align: text-bottom; width: 24px; height: 24px; box-sizing: border-box; border-radius: 50%; border: 0px solid; -webkit-box-shadow: none; padding: 4px; background-color: rgba(0, 0, 0, 0); text-decoration-color: rgba(0, 0, 0, 0); outline-color: rgb(206, 54, 64); outline-width: 5px; color: rgb(10, 4, 4); cursor: pointer; transition: 0.3s;" class="$personyze_button_dont_show_again" data-action_id="${action_id}"><div style="display: block; width: 100%; height: 100%; transition: 0.3s; border-radius: 50%; background-image: linear-gradient(-45deg, transparent 0%, transparent 48%, currentcolor 48%, currentcolor 54%, transparent 54%, transparent 100%), linear-gradient(45deg, transparent 0%, transparent 48%, currentcolor 48%, currentcolor 54%, transparent 54%, transparent 100%);"></div></div>')}
    </div>
    ${endblock}

  </div>
</div>

<!-- PERSONYZE MENU OPTIONS -->

${menu name='Box Style', icon='th-large'}
	${menu args->box_style name='Banner Container Style', type='css', param='with_responsive=1'}
${menu name='Image', icon='image'}
	${menu block->with_image name='Show Top Image'}
	${menu args->image_url name='Image URL', type='media_url'}
	${menu args->image_alt name='Image Alt Text'}
	${menu args->image_style name='Image Style', type='css', param='with_responsive=1'}
${menu name='Content', icon='font'}
	${menu args->content name='Message Text'}
	${menu args->td_style name='Text Container Style', type='css', param='with_responsive=1'}
${menu name='Primary CTA Button', icon='link'}
	${menu block->with_cta name='Show Primary CTA'}
	${menu args->cta_text name='Primary CTA Text'}
	${menu args->cta_link name='Primary CTA Link', type='a_attrs'}
	${menu args->cta_style name='Primary CTA Style', type='css', param='with_responsive=1'}
${menu name='Secondary CTA Button', icon='clock'}
	${menu block->with_cta_2 name='Show Secondary CTA'}
	${menu args->cta_text_2 name='Secondary CTA Text'}
	${menu args->cta_link_2 name='Secondary CTA Link', type='a_attrs'}
	${menu args->cta_style_2 name='Secondary CTA Style', type='css', param='with_responsive=1'}
${menu name='Close Button', icon='times-circle'}
	${menu block->with_close_button name='Show Close Button'}
	${menu args->close_button_style name='Close Button Style', type='css', param='with_responsive=1'}
	${menu args->close_button name='Close Button HTML', type='dontshowagain'}
```


## Responsive Full-Width Top Bar Banner with Inline CTA & Close Button

A fully responsive top bar banner template for Personyze featuring a logo, customizable text, primary and secondary CTA buttons, and an inline close button. All elements are easily styled via the Personyze CSS editor for seamless integration

```
<style>
  /* System fonts only */
  body, div, a, input, button, span {
    font-family: Arial, sans-serif;
    margin: 0;
    padding: 0;
    box-sizing: border-box;
  }

  /* Animation Keyframes */
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

  /* Responsive Adjustments */
  @media (max-width: 768px) {
    .$responsive {
      flex-direction: column;
      padding: 16px;
    }
    .button-container {
      flex-direction: column;
      align-items: center;
      gap: 8px;
    }
    /* On mobile, place the close button at the top of the button container */
    .button-container .close-btn {
      order: -1;
    }
  }

  /* Transparent corner fix */
  .transparent-corner {
    background-color: transparent !important;
  }
</style>

<!-- Template Content -->
<div class="$responsive" data-style="position: relative;
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: space-between;
  background-color: ${args->framebgcolor:html:default('rgb(40, 43, 65)')};
  border-radius: 16px;
  padding: sel(20px, 16px);
  width: 100%;
  text-align: center;
  ${args->style:html:default('height: auto;
border-radius: 15px;
width: 100%;
box-sizing: border-box;
')}
">

  <!-- Left Block: Logo and Text -->
  <div style="display: flex; flex: 1 1 auto; align-items: center; gap: 20px; flex-wrap: wrap;">
    <!-- Logo -->
    ${block->logo:default(1)}
    <div style="flex: 0 0 auto; max-width: 120px; ${args->logo_visibility_mobile:html}">
      <img src="${args->logo_src:html:default('https://cdn.personyze.com/upload/362/18a94c1299224ec8.png')}"
           data-style="${args->logo_style:html:default('width: 100%; max-width: 120px; border-radius: 10px;')}"
           alt="Logo">
    </div>
    <!-- Text -->
    ${block->with_left_text:default(1)}
    <div style="flex: 1 1 auto;"
         data-style="${args->left_style:html:default('color: #fff; font-size: sel(22px, 16px); font-weight: 600;')}">
      ${args->left_text:default('<strong>Time is Running Out!</strong><br /><span style="font-size: sel(18px, 14px); font-weight: normal;">Don’t miss your chance to save!</span>')}
    </div>
  </div>

  <!-- Buttons Block -->
  <div class="button-container" style="display: flex; flex-wrap: wrap; justify-content: center; gap: 10px;">
    ${block->button1:default(1)}
    <a ${args->href1:default('href="#"')}
       data-style="${args->button1_style:html:default('font-size: 16px; background-color: #3498db; color: #fff; padding: 10px 24px; border-radius: 30px; text-decoration: none;')}"
       style="animation: ${args->button1_animation:html:default(bounce)} 1.5s infinite;">
      ${args->button1_text:default(Join Now)}
    </a>
    ${block->button2:default(1)}
    <a ${args->href2:default('href="javascript:"')}
       data-style="${args->button2_style:html:default('font-size: 14px; background: transparent; color: #eee; text-decoration: underline; padding: 10px 20px; border-radius: 20px;')}"
       onmouseover="this.style.opacity='0.8'" onmouseout="this.style.opacity='1'">
      ${args->button2_text:default(Maybe Later)}
    </a>
    <!-- Close Button placed inline with CTA buttons -->

    ${args->x:default('<a href="javascript:" style="font-size: 24px; color: rgb(252, 252, 252); font-weight: lighter; line-height: 1; text-decoration: none; position: absolute; top: 10px; right: 10px;" class="$personyze_button_dont_show_again" data-action_id="${action_id}" title="Close">×</a>')}
  </div>
</div>

<!-- PERSONYZE MENU OPTIONS -->

${menu name='Banner Settings', icon='th-large'}
	${menu args->framebgcolor name='Background color', description='Banner background color', type='color'}
	${menu args->style name='Custom CSS styles for the banner', description='Full CSS for the banner container', type='css', param='with_responsive=1'}
${menu name='Logo Settings', icon='image'}
	${menu block->logo name='Show logo'}
	${menu args->logo_src name='Logo URL', type='personyze_media_url'}
	${menu args->logo_style name='Logo style', type='css', param='with_responsive=1'}
	${menu args->logo_visibility_mobile name='Hide logo on mobile', type='checkbox'}
${menu name='Text Block', icon='align-left'}
	${menu block->with_left_text name='Show text block'}
	${menu args->left_text name='Text content'}
	${menu args->left_style name='Text style', type='css', param='with_responsive=1'}
${menu name='CTA Button', icon='hand-pointer-o'}
	${menu block->button1 name='Show CTA button 1'}
	${menu args->button1_text name='Button text'}
	${menu args->href1 name='Button URL', type='a_attrs'}
	${menu args->button1_style name='Button style', type='css', param='with_responsive=1'}
	${menu args->button1_animation name='Button animation', type='select', param='options=[["None",""],["Bounce","bounce"],["Pulse","pulse"],["Shake","shake"]]'}
${menu name='CTA Button 2', icon='hand-o-up'}
	${menu block->button2 name='Show CTA button 2'}
	${menu args->button2_text name='Button 2 text'}
	${menu args->href2 name='Button 2 URL', type='a_attrs'}
	${menu args->button2_style name='Button 2 style', type='css', param='with_responsive=1'}
${menu name='Close Button', icon='times'}
	${menu args->x name='Close button HTML', type='dontshowagain'}
```


## Minimalist design bar message



```
<div class="$responsive" data-style="box-sizing: border-box; position: relative; ${args->box_style:html:default('background-color: #5253A4;
border-radius: 14px;
padding: 24px 32px;
max-width: 100%;
margin: 0 auto;
font-family: Arial, sans-serif;
')}">

  <style>
    @media (max-width: 768px) {
      .travel-banner-flex {
        flex-direction: column !important;
        text-align: center;
      }
      .cta-banner-button {
        margin-top: 16px;
      }
    }

    .cta-banner-button.icon-left i {
      order: -1;
      margin-right: 8px;
    }

    .cta-banner-button.icon-right i {
      order: 1;
      margin-left: 8px;
    }
  </style>

  <div class="travel-banner-flex" style="display: flex; flex-wrap: wrap; align-items: center; justify-content: space-between; gap: 20px;">

    <!-- Main Text -->
    <div data-style="${args->text_style:html:default('color: white;
font-size: 20px;
font-weight: 600;
')}">
      ${args->text:default('✈️ Escape the ordinary – discover exclusive travel deals and getaways!')}
    </div>

    <!-- CTA Button -->
    ${block->with_cta:default(1)}
    <div>
      <a class="cta-banner-button ${args->cta_icon_position:html:default(icon-left)}" ${args->cta_link:default('href="#"')}
         data-style="${args->cta_style:html:default('background-color: white;
color: black;
padding-top: 14px;
padding-right: 28px;
padding-bottom: 14px;
padding-left: 28px;
border-radius: 10px;
font-size: 16px;
font-weight: bold;
text-decoration: none;
display: inline-flex;
align-items: center;
justify-content: center;
')}">
        <span>${args->cta_text:default(Book Now)}</span>
        ${if args->cta_icon_class:default(angle-right) != ''}<i class="$icon ${args->cta_icon_class:html}" style="${args->cta_icon_style:html:default('font-size: 16px;
margin: 0px;
padding: 5px;
')}"></i>${end}
      </a>
    </div>
  </div>

  <!-- Close Button -->
  ${block->with_close_button:default(1)}
  <div data-style="${args->close_button_style:html:default('position: absolute;
top: 10px;
right: 10px;
z-index: 99;
')}">
    ${args->close_button:default('<div class="$personyze_button_dont_show_again" data-action_id="${action_id}" style="display: inline-block; width: 20px; height: 20px; background-color: rgba(255,255,255,0.4); color: white; text-align: center; line-height: 20px; border-radius: 50%; font-size: 16px; cursor: pointer;">×</div>')}
  </div>
</div>

<!-- ✅ PERSONYZE MENU OPTIONS -->

${menu name='Banner Container', icon='th-large'}
	${menu args->box_style name='Container Style', type='css', param='with_responsive=1'}
${menu name='Main Text', icon='font'}
	${menu args->text name='Promo Text'}
	${menu args->text_style name='Text Style', type='css', param='with_responsive=1'}
${menu name='CTA Button', icon='hand-o-up'}
	${menu block->with_cta name='Show CTA'}
	${menu args->cta_text name='CTA Text'}
	${menu args->cta_link name='CTA Link', type='a_attrs'}
	${menu args->cta_style name='CTA Style', type='css', param='with_responsive=1'}
	${menu args->cta_icon_class name='Icon Class', type='icon'}
	${menu args->cta_icon_style name='Icon Style', type='css'}
	${menu args->cta_icon_position name='Icon Position', type='select', param='options=[["Before Text","icon-left"],["After Text","icon-right"]]'}
${menu name='Close Button', icon='times-circle'}
	${menu block->with_close_button name='Show Close Button'}
	${menu args->close_button_style name='Close Button Style', type='css', param='with_responsive=1'}
	${menu args->close_button name='Close Button HTML', type='dontshowagain'}
```


## Review mesaage box



```
<div class="$responsive" data-style="box-sizing: border-box; position: relative; ${args->box_style:html:default('
background-color: white;
border-radius: 10px;
padding: 20px;
max-width: 600px;
margin: 0 auto;
box-shadow: 0 2px 10px rgba(0,0,0,0.1);
font-family: Arial, sans-serif;
')}">

  <!-- Close Button -->
  ${block->with_close_button:default(1)}
  <div data-style="${args->close_button_style:html:default('
position: absolute;
top: 10px;
right: 10px;
z-index: 1;
')}">
    ${args->close_button:default('<div style="width: 24px; height: 24px; background-color: rgba(0,0,0,0.05); border-radius: 50%; text-align: center; line-height: 24px; font-weight: bold; color: #333; cursor: pointer;">×</div>')}
  </div>

  <!-- Title -->
  <div data-style="${args->title_style:html:default('
font-size: 22px;
font-weight: bold;
margin-bottom: 20px;
text-align: center;
color: #000;
')}">
    ${args->title:default(Here is what our customers said)}
  </div>

  <!-- Testimonial Row -->
  <div style="display: flex; flex-wrap: wrap; align-items: center; justify-content: center; gap: 20px; text-align: center;">

    <!-- User Image -->
    <div>
      <img src="${args->user_image:html:default('https://cdn.personyze.com/upload/362/12cb99165533447c.png')}"
           data-style="${args->user_image_style:html:default('width: 60px;
height: 60px;
border-radius: 50%;
object-fit: cover;
')}">
    </div>

    <!-- Text Block -->
    <div style="flex: 1 1 300px;">
      <div data-style="${args->review_text_style:html:default('font-size: 14px;
color: #333;
margin-bottom: 10px;
text-align: center;
')}">
        ${args->review_text:default(I was totally satisfied with how Andrew dealt with our prenuptial agreement. We were able to get legal recognition within two weeks!)}
      </div>
      <div data-style="${args->reviewer_name_style:html:default('font-weight: bold;
font-size: 14px;
color: #000;
text-align: center;
')}">
        ${args->reviewer_name:default(Liz Sure)}
      </div>
    </div>
  </div>

  <!-- CTA Button -->
  ${block->with_cta:default(1)}
  <div style="text-align: center; margin-top: 20px;">
    <a ${args->cta_link:default('href="#"')}
       data-style="${args->cta_style:html:default('background-color: #4a70f8;
color: white;
padding-top: 10px;
padding-right: 20px;
padding-bottom: 10px;
padding-left: 20px;
border-radius: 8px;
font-weight: bold;
text-decoration: none;
font-size: 14px;
display: inline-block;
')}">
      ${args->cta_text:default(See more reviews)}
    </a>
  </div>
</div>

<!-- ✅ PERSONYZE MENU OPTIONS -->

${menu name='Box Style', icon='th-large'}
	${menu args->box_style name='Box style', type='css', param='with_responsive=1'}
${menu name='Title', icon='header'}
	${menu args->title name='Headline'}
	${menu args->title_style name='Headline style', type='css', param='with_responsive=1'}
${menu name='User Image', icon='user-circle'}
	${menu args->user_image name='User image URL', type='media_url'}
	${menu args->user_image_style name='User image style', type='css', param='with_responsive=1'}
${menu name='Review Content', icon='comment'}
	${menu args->review_text name='Testimonial text'}
	${menu args->review_text_style name='Text style', type='css', param='with_responsive=1'}
	${menu args->reviewer_name name='Reviewer name'}
	${menu args->reviewer_name_style name='Reviewer name style', type='css', param='with_responsive=1'}
${menu name='CTA Button', icon='hand-o-up'}
	${menu block->with_cta name='Show CTA button'}
	${menu args->cta_text name='CTA button text'}
	${menu args->cta_link name='CTA link', type='a_attrs'}
	${menu args->cta_style name='CTA button style', type='css', param='with_responsive=1'}
${menu name='Close Button', icon='times-circle'}
	${menu block->with_close_button name='Show close button'}
	${menu args->close_button_style name='Close button style', type='css', param='with_responsive=1'}
	${menu args->close_button name='Close button', type='dontshowagain'}
```


## Promotion Banner with Optional Image, Logo, and CTA Buttons

It includes an optional logo positioned above the headline text, optional main promotional image with responsive positioning options (top/bottom on mobile, left/right on desktop), customizable primary and secondary CTA buttons, optional decorative CSS shapes, and a close button

```
<div class="$responsive ${args->mobile_img_order:html:default(img-mobile-top img-desktop-right)}"
     data-style="${args->banner_style:html:default('background-color:#004481; position:relative; padding:20px 40px; border-radius:8px; overflow:hidden; color:#fff;')}">

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
    ${args->close_button_html:default('<div onmouseenter="this.style.backgroundColor=this.style.outlineColor" onmouseleave="this.style.backgroundColor=this.style.textDecorationColor" style="display: inline-block; vertical-align: text-bottom; width: 24px; height: 24px; box-sizing: border-box; border-radius: 50%; border: 0px solid; -webkit-box-shadow: none; padding: 2px; background-color: rgba(0, 0, 0, 0); text-decoration-color: rgba(0, 0, 0, 0); outline-color: rgb(206, 54, 64); outline-width: 7px; color: rgb(245, 245, 245); cursor: pointer; transition: 0.3s;" class="$personyze_button_dont_show_again" data-action_id="${action_id}"><div style="display: block; width: 100%; height: 100%; transition: 0.3s; border-radius: 50%; background-image: linear-gradient(-45deg, transparent 0%, transparent 47%, currentcolor 47%, currentcolor 55%, transparent 55%, transparent 100%), linear-gradient(45deg, transparent 0%, transparent 47%, currentcolor 47%, currentcolor 55%, transparent 55%, transparent 100%);"></div></div>')}
  </div>

  <!-- Banner Flex Container -->
  <div class="banner-flex-container">

    <!-- Optional Image -->
    ${block->right_image:default(1)}
    <div class="image-container" style="${args->right_image_style:html:default('width: 21%;
max-width: 500px;
margin-top: 0px;
margin-right: 0px;
margin-bottom: -24px;
margin-left: 0px;
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
      <div class="logo-container" style="${args->logo_style:html:default('width: 180px;
margin-bottom: 15px;
')}">
        <img src="${args->logo_src:html:default('https://cdn.personyze.com/upload/362/18a94c1299224ec8.png')}" alt="Bank Logo">
      </div>

      <!-- Headline -->
      <div class="banner-headline" data-style="${args->headline_style:html:default('font-size: 28px;
font-weight: bold;
margin-bottom: 10px;
')}">
        ${args->headline_text:default('Grow Your Savings with Our <span style="color:#ffe500;">High-Yield Accounts</span>')}
        <div class="tooltip">${args->headline_tooltip:default(Rates subject to terms and conditions.)}</div>
      </div>

      <!-- Subheading -->
      <div class="banner-subheading" data-style="${args->subheading_style:html:default('font-size: 16px;
margin-bottom: 20px;
')}">
        ${args->subheading_text:default(Open an account online in just minutes and start earning today.)}
      </div>

      <!-- CTA Row -->
      <div class="cta-row" data-style="${args->cta_row_style:html:default('display: flex;
align-items: center;
gap: 20px;
')}">
        <!-- Primary CTA -->
        ${block->primary_cta:default(1)}<a ${args->primary_cta_link:default('href="#"')}
           class="signup-btn"
           data-style="${args->primary_cta_style:html:default('background-color:#ffe500;color:#004481;border:2px solid #ffe500;padding:12px 24px;border-radius:6px;font-weight:600;text-decoration:none;')}">
          ${args->primary_cta_text:default(Open Account)}
        </a>

        <!-- Secondary CTA -->
        ${block->secondary_cta:default(1)}<a ${args->secondary_cta_link:default('href="#"')}
           class="signin-link"
           data-style="${args->secondary_cta_style:html:default('color:#fff;text-decoration:underline;')}">
          ${args->secondary_cta_text:default(Learn More)}
        </a>
      </div>
    </div>
  </div>

  <!-- Decorative CSS Shapes -->
  ${block->with_shape:default(1)}<div style="${args->shape_style:html:default('position: absolute;
bottom: -20px;
left: -20px;
width: 100px;
height: 100px;
background: #ffe500;
border-radius: 50%;
opacity: 0.3;
')}"></div>
  ${block->with_shape2:default(1)}<div style="${args->shape2_style:html:default('position: absolute;
top: -30px;
right: -30px;
width: 120px;
height: 120px;
background: #00a1e0;
transform: rotate(45deg);
opacity: 0.2;
')}"></div>

</div>

<!-- PERSONYZE MENU -->

${menu name='Banner Container', icon='th-large'}
	${menu args->banner_style name='Banner Style', type='css', param='with_responsive=1'}
${menu name='Close Button', icon='times'}
	${menu block->close_button name='Show Close Button'}
	${menu args->close_button_html name='Close Button HTML', type='dontshowagain'}
${menu name='Optional Logo', icon='image'}
	${menu block->with_logo name='Show Logo'}
	${menu args->logo_src name='Logo URL', type='personyze_media_url'}
	${menu args->logo_style name='Logo Style', type='css', param='with_responsive=1'}
${menu name='Optional Main Image', icon='image'}
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


## Single-Line top/bottom bar

Full screen width, featuring an optional coupon code with double-click copy-to-clipboard, toggleable Apple/Google icons (each with its own link), an optional “Download app” link, and a close button.

```
<!-- HEAD + STYLE -->
<style>
  .banner-offer {
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 8px;
    font-family: Arial, sans-serif;
    font-size: 14px;
    line-height: 1.4;
  }
  .banner-offer img {
    height: 18px; /* icon size */
    vertical-align: middle;
  }
  .coupon-code:hover::after {
    content: attr(data-tooltip);
    position: absolute;
    background: #333;
    color: #fff;
    font-size: 12px;
    padding: 4px 8px;
    border-radius: 4px;
    top: -32px; /* position above */
    left: 50%;
    transform: translateX(-50%);
    white-space: nowrap;
    pointer-events: none;
    opacity: 0.85;
    z-index: 9999;
  }
</style>

<!-- BANNER CONTAINER -->
<div class="$responsive"
     data-style="${args->banner_style:html:default('background-color: #fff;
padding: 10px;
text-align: center;
border-bottom: 0px solid #000;
min-width: 99%;
')}">

  <!-- Close Button SINGLE-LINE TOGGLE -->
  ${block->close_button:default(1)}<div style="position:absolute; top:5px; right:5px;">
    ${args->close_button_html:default('<div onmouseenter="this.style.backgroundColor=this.style.outlineColor" onmouseleave="this.style.backgroundColor=this.style.textDecorationColor" style="display: inline-block; vertical-align: text-bottom; width: 27px; height: 27px; box-sizing: border-box; border-radius: 50%; border: 0px solid; -webkit-box-shadow: none; padding: 2px; background-color: rgba(0, 0, 0, 0); text-decoration-color: rgba(0, 0, 0, 0); outline-color: rgb(206, 54, 64); outline-width: 5px; color: rgb(10, 4, 4); cursor: pointer; transition: 0.3s;" class="$personyze_button_dont_show_again" data-action_id="${action_id}"><div style="display: block; width: 100%; height: 100%; transition: 0.3s; border-radius: 50%; background-image: linear-gradient(-45deg, transparent 0%, transparent 48%, currentcolor 48%, currentcolor 54%, transparent 54%, transparent 100%), linear-gradient(45deg, transparent 0%, transparent 48%, currentcolor 48%, currentcolor 54%, transparent 54%, transparent 100%);"></div></div>')}
  </div>

  <!-- Banner content row -->
  <div class="banner-offer" data-style="${args->offer_text_style:html:default('color: #000;
font-size: 14px;
')}">

    <!-- Main Offer Text (always shown) -->
    ${args->offer_text:default('Enjoy 10% off. Use code:')}

    <!-- Coupon Code (toggle) -->
    ${block->coupon_code:default(1)}<span class="coupon-code"
      data-style="${args->coupon_code_style:html:default('font-weight: bold;
color: red;
margin-top: 0;
margin-right: 6px;
margin-bottom: 0;
margin-left: 6px;
cursor: pointer;
position: relative;
')}"
      data-tooltip="Double-click to copy"
      ondblclick="navigator.clipboard.writeText('${args->coupon_code_value:html:default(APPORDER)}'); alert('Coupon code copied!')"
    >
      ${args->coupon_code_value}
    </span>

    <!-- Apple Icon (toggle) -->
    ${block->apple_icon:default(1)}<a ${args->apple_icon_link:default('href="#"')}>
      <img src="${args->apple_icon_src:html:default('https://cdn.personyze.com/upload/362/fc0a267b78425575.svg')}" alt="Apple Store Icon">
    </a>

    <!-- Google Icon (toggle) -->
    ${block->google_icon:default(1)}<a ${args->google_icon_link:default('href="#"')}>
      <img src="${args->google_icon_src:html:default('https://cdn.personyze.com/upload/362/3630764c3a3750f5.svg')}" alt="Google Play Icon">
    </a>

    <!-- Download Link (toggle) -->
    ${block->download_link:default(0)}<a ${args->download_attrs:default('href="#"')}
       data-style="${args->download_link_style:html:default('font-weight:bold; color:#000; text-decoration:none;')}"
       style="margin-left:6px;">
      Download app
    </a>
  </div>
</div>

<!-- PERSONYZE MENU -->

${menu name='Banner Container', icon='th-large'}
	${menu args->banner_style name='Banner Style', description='Main container CSS (e.g. full width, fixed top, etc.)', type='css', param='with_responsive=1'}
${menu name='Offer Text', icon='comment'}
	${menu args->offer_text name='Banner Text (HTML)'}
	${menu args->offer_text_style name='Banner Text Style', type='css', param='with_responsive=1'}
${menu name='Coupon Code', icon='tag'}
	${menu block->coupon_code name='Show Coupon Code?'}
	${menu args->coupon_code_value name='Coupon Code Text'}
	${menu args->coupon_code_style name='Coupon Code Style', description='Double-click to copy', type='css', param='with_responsive=1'}
${menu name='Close Button', icon='times'}
	${menu block->close_button name='Show Close Button'}
	${menu args->close_button_html name='Close Button HTML', type='dontshowagain'}
${menu name='Apple Icon', icon='apple'}
	${menu block->apple_icon name='Show Apple Icon'}
	${menu args->apple_icon_src name='Apple Icon (Media)', description='Select Apple icon from library', type='personyze_media_url'}
	${menu args->apple_icon_link name='Apple Icon Link', description='Where Apple icon links to', type='a_attrs'}
${menu name='Google Icon', icon='android'}
	${menu block->google_icon name='Show Google Icon'}
	${menu args->google_icon_src name='Google Icon (Media)', description='Select Google badge from library', type='personyze_media_url'}
	${menu args->google_icon_link name='Google Icon Link', description='Where Google icon links to', type='a_attrs'}
${menu name='Download Link', icon='hand-pointer-o'}
	${menu block->download_link name='Show Download Link'}
	${menu args->download_attrs name='Download Link Attributes', type='a_attrs'}
	${menu args->download_link_style name='Download Link Style', type='css', param='with_responsive=1'}
```


## Animated Notification Bar with Full Customization

It features a smooth vertical scrolling animation with full user control over the animation speed, duration, and easing style through intuitive menu settings. Each notification line includes customizable text, optional icons, and buttons with editable links and CSS styling.

```
<div style="position: relative; overflow: hidden; font-family: 'Montserrat', Arial, sans-serif; width:100%;">

  ${block->show_close_button:default(1)}
  <div style="position:absolute;top:10px;right:10px;cursor:pointer;z-index:10;display:">
    ${args->close_button_html:default('<div onmouseenter="this.style.backgroundColor=this.style.outlineColor" onmouseleave="this.style.backgroundColor=this.style.textDecorationColor" style="display: inline-block; vertical-align: text-bottom; width: 35px; height: 35px; box-sizing: border-box; border-radius: 50%; padding: 9px; background-color: rgba(75,75,75,0.65); outline-color: rgb(206,54,64); outline-width: 8px; color: rgb(254,253,253); transition: 0.3s;" class="$personyze_button_dont_show_again" data-action_id="${action_id}"><div style="width:100%;height:100%;transition:0.3s;border-radius:50%;background-image:linear-gradient(-45deg,transparent 47%,currentcolor 47%,currentcolor 55%,transparent 55%),linear-gradient(45deg,transparent 47%,currentcolor 47%,currentcolor 55%,transparent 55%);"></div></div>')}
  </div>

  <div style="${args->style:html:default('background-color: rgb(54, 32, 32);
color: #fff;
border-radius: 0px;
text-align: center;
font-size: 15px;
padding: 8px;
width: 100%;
margin: auto;
line-height: 2em;
overflow: hidden;
height: 2.5em;
position: relative;
')}">
    <div style="animation: ${args->animation_type:html:default(scrollCustom)} ${args->anim_duration:html:default(10s)} ${args->anim_easing:html:default(ease-in-out)} infinite;">

      ${block->with_line_1:default(1)}
      <div style="padding:5px;height:2.5em;">
        <i class="$icon ${args->line_1_icon:html:default(user)}" style="${args->line_1_icon_style:html:default('font-size:18px;margin-right:4px;vertical-align:middle;')}"></i>
        <span style="vertical-align:middle;">${args->line_1_text:default(Welcome to Our Website!)}</span>
        ${block->with_line_1_button:default(1)}
        <a ${args->line_1_button} style="${args->line_1_button_style:html:default('color: inherit;
text-decoration: underline;
margin-left: 4px;
vertical-align: middle;
')}">${args->line_1_button_text:default(Learn More)}</a>
      </div>

      ${block->with_line_2:default(1)}
      <div style="padding:5px;height:2.5em;">
        <i class="$icon ${args->line_2_icon:html:default(star)}" style="${args->line_2_icon_style:html:default('font-size:18px;margin-right:4px;vertical-align:middle;')}"></i>
        <span style="vertical-align:middle;">${args->line_2_text:default(Special Offer Available!)}</span>
        ${block->with_line_2_button:default(1)}
        <a ${args->line_2_button} style="${args->line_2_button_style:html:default('color: inherit;
text-decoration: underline;
margin-left: 4px;
vertical-align: middle;
')}">${args->line_2_button_text:default(Claim Now)}</a>
      </div>

      ${block->with_line_3:default(1)}
      <div style="padding:5px;height:2.5em;">
        <i class="$icon ${args->line_3_icon:html:default(info-circle)}" style="${args->line_3_icon_style:html:default('font-size:18px;margin-right:4px;vertical-align:middle;')}"></i>
        <span style="vertical-align:middle;">${args->line_3_text:default(Discover Our Features)}</span>
        ${block->with_line_3_button:default(1)}
        <a ${args->line_3_button} style="${args->line_3_button_style:html:default('color: inherit;
text-decoration: underline;
margin-left: 4px;
vertical-align: middle;
')}">${args->line_3_button_text:default(Explore)}</a>
      </div>

      ${block->with_line_4:default(1)}
      <div style="padding:5px;height:2.5em;">
        <i class="$icon ${args->line_4_icon:html:default(envelope)}" style="${args->line_4_icon_style:html:default('font-size:18px;margin-right:4px;vertical-align:middle;')}"></i>
        <span style="vertical-align:middle;">${args->line_4_text:default(Subscribe to Our Newsletter)}</span>
        ${block->with_line_4_button:default(1)}
        <a ${args->line_4_button} style="${args->line_4_button_style:html:default('color: inherit;
text-decoration: underline;
margin-left: 4px;
vertical-align: middle;
')}">${args->line_4_button_text:default(Subscribe)}</a>
      </div>

    </div>
  </div>
</div>

<style>
@keyframes scrollCustom {
  0%,20% { transform: translateY(0%); }
  25%,45% { transform: translateY(-25%); }
  50%,70% { transform: translateY(-50%); }
  75%,95% { transform: translateY(-75%); }
  100% { transform: translateY(0%); }
}
</style>

${menu name='Animation Settings', icon='cog'}
	${menu args->anim_duration name='Animation Duration', type='text'}
	${menu args->anim_easing name='Animation Easing', type='select', param='options=[["Linear","linear"],["Ease","ease"],["Ease-in","ease-in"],["Ease-out","ease-out"],["Ease-in-out","ease-in-out"]]'}
	${menu args->animation_type name='Animation Type', type='select', param='options=[["Scroll Vertical","scrollCustom"],["Fade","fade"],["Flip","flip"],["Slide Right","slideRight"]]'}
${menu name='Close Button', icon='times'}
	${menu block->show_close_button name='Show Close Button'}
	${menu args->close_button_html name='Close Button HTML', type='dontshowagain'}
${menu name='Content Controls', icon='edit'}
	${menu block->with_line_1 name='Show Line 1'}
	${menu args->line_1_icon name='Line 1 Icon', type='icon'}
	${menu args->line_1_text name='Line 1 Text', type='text'}
	${menu args->line_1_button name='Line 1 Link', type='a_attrs'}
	${menu args->line_1_button_text name='Line 1 Button Text', type='text'}
	${menu args->line_1_button_style name='Line 1 Button CSS', type='css'}
	${menu block->with_line_2 name='Show Line 2'}
	${menu args->line_2_icon name='Line 2 Icon', type='icon'}
	${menu args->line_2_text name='Line 2 Text', type='text'}
	${menu args->line_2_button name='Line 2 Link', type='a_attrs'}
	${menu args->line_2_button_text name='Line 2 Button Text', type='text'}
	${menu args->line_2_button_style name='Line 2 Button CSS', type='css'}
	${menu block->with_line_3 name='Show Line 3'}
	${menu args->line_3_icon name='Line 3 Icon', type='icon'}
	${menu args->line_3_text name='Line 3 Text', type='text'}
	${menu args->line_3_button name='Line 3 Link', type='a_attrs'}
	${menu args->line_3_button_text name='Line 3 Button Text', type='text'}
	${menu args->line_3_button_style name='Line 3 Button CSS', type='css'}
	${menu block->with_line_4 name='Show Line 4'}
	${menu args->line_4_icon name='Line 4 Icon', type='icon'}
	${menu args->line_4_text name='Line 4 Text', type='text'}
	${menu args->line_4_button name='Line 4 Link', type='a_attrs'}
	${menu args->line_4_button_text name='Line 4 Button Text', type='text'}
	${menu args->line_4_button_style name='Line 4 Button CSS', type='css'}
${menu name='Settings', icon='sliders'}
	${menu args->style name='Main Container Style', type='css'}
```


## Full-Screen Responsive Banner Template

designed to occupy 100% of viewport width and height, providing a clean and visually appealing layout. It supports easy editing of images, alignment, headlines, CTAs, decorative shapes, and more.

```
<div class="$responsive ${args->mobile_img_order:html:default(img-mobile-top img-desktop-right)}"
     data-style="${args->banner_style:html:default('background-color: #0A2540;
position: relative;
padding-top: 20px;
padding-right: 40px;
padding-bottom: 20px;
padding-left: 40px;
border-radius: 0px;
overflow: hidden;
color: #fff;
display: flex;
justify-content: center;
align-items: center;
box-sizing: border-box;
width: 100%;
height: 100%;
')}">

  <style>
    .banner-flex-container {
      display:flex;
      align-items:center;
      justify-content:center;
      gap:20px;
      width:100%;
      max-width:1200px;
    }

    @media (max-width:768px){
      .banner-flex-container { flex-direction:column; text-align:center; }
      .img-mobile-top .image-container { order:-1 !important; }
      .img-mobile-bottom .image-container { order:2 !important; }
      .logo-container { justify-content:center !important; margin:0 auto 15px !important; }
    }

    @media (min-width:769px){
      .img-desktop-left .image-container { order:-1 !important; }
      .img-desktop-right .image-container { order:2 !important; }
    }

    .image-container img, .logo-container img { width:100%; height:auto; object-fit:cover; display:block; }

    .cta-row-container {
      display:flex;
      justify-content:center;
      gap:10px;
    }
  </style>

  ${block->close_button:default(1)}
  <div style="position:absolute;top:10px;right:10px;cursor:pointer;z-index:10;">
    ${args->close_button_html:default('<div onmouseenter="this.style.backgroundColor=this.style.outlineColor" onmouseleave="this.style.backgroundColor=this.style.textDecorationColor" style="display: inline-block; vertical-align: text-bottom; width: 35px; height: 35px; box-sizing: border-box; border-radius: 50%; border: 0px solid; box-shadow: none; padding: 9px; background-color: rgba(75, 75, 75, 0.65); text-decoration-color: rgba(75, 75, 75, 0.65); outline-color: rgb(206, 54, 64); outline-width: 8px; color: rgb(254, 253, 253); cursor: pointer; transition: 0.3s;" class="$personyze_button_dont_show_again" data-action_id="${action_id}"><div style="display: block; width: 100%; height: 100%; transition: 0.3s; border-radius: 50%; background-image: linear-gradient(-45deg, transparent 0%, transparent 47%, currentcolor 47%, currentcolor 55%, transparent 55%, transparent 100%), linear-gradient(45deg, transparent 0%, transparent 47%, currentcolor 47%, currentcolor 55%, transparent 55%, transparent 100%);"></div></div>')}
  </div>

  <div class="banner-flex-container">

    ${block->right_image:default(1)}
    <div class="image-container" style="${args->right_image_style:html:default('flex:1; max-width:500px;')}">
      <img src="${args->right_image_src:html:default('https://cdn.personyze.com/upload/362/08ca0a5265164e9d.png')}" style="${args->right_image_img_style:html:default('object-fit: contain;
padding: 15px;
max-height: 45vh;
width: 100%;
')}" alt="Cool Gadget">
    </div>

    <div class="banner-content" style="${args->banner_content_style:html:default('flex: 1;
max-width: 600px;
color: #fff;
')}">

      ${block->with_logo:default(1)}
      <div class="logo-container ${args->logo_position_desktop:html:default(desktop-center)} ${args->logo_position_mobile:html:default(mobile-center)}" style="${args->logo_style:html:default('width: 150px;
margin-bottom: 15px;
display: flex;
')}">
        <img src="${args->logo_src:html:default('https://cdn.personyze.com/upload/362/18a94c1299224ec8.png')}" alt="Tech Logo">
      </div>

      <div class="banner-headline" style="${args->headline_style:html:default('font-size:32px;font-weight:bold;margin-bottom:10px;line-height:1.2;')}">
        ${args->headline_text:default('Meet the Future of Tech: The <span style="color:#34D399;">XGizmo Pro!</span> ?')}
        <div class="tooltip">${args->headline_tooltip:default(Limited stock available!)}</div>
      </div>

      <div class="banner-subheading" style="${args->subheading_style:html:default('font-size: 18px;
margin-bottom: 20px;
')}">
        ${args->subheading_text:default(Experience innovation with cutting-edge features designed for you.)}
      </div>

      <div class="cta-row-container">
        <div class="cta-row" style="${args->cta_row_style_desktop:html:default('display: flex;
align-items: center;
gap: 20px;
justify-content: center;
')}">
          ${block->primary_cta:default(1)}
          <a ${args->primary_cta_link:default('href="#"')} class="signup-btn" style="${args->primary_cta_style:html:default('background-color: #34D399;
color: #0A2540;
border: 2px solid #34D399;
padding-top: 12px;
padding-right: 24px;
padding-bottom: 12px;
padding-left: 24px;
border-radius: 6px;
font-weight: 600;
text-decoration: none;
')}">
            ${args->primary_cta_text:default(Order Now)}
          </a>

          ${block->secondary_cta:default(1)}
          <a ${args->secondary_cta_link:default('href="#"')} class="signin-link" style="${args->secondary_cta_style:html:default('color:#fff;text-decoration:underline;')}">
            ${args->secondary_cta_text:default(Explore Features)}
          </a>
        </div>
      </div>
    </div>
  </div>

  ${block->with_shape:default(1)}<div style="${args->shape_style:html:default('position:absolute;bottom:-30px;left:-30px;width:120px;height:120px;background:#34D399;border-radius:50%;opacity:0.3;')}"></div>

  ${block->with_shape2:default(1)}<div style="${args->shape2_style:html:default('position:absolute;top:-30px;right:-30px;width:140px;height:140px;background:#6366F1;transform:rotate(45deg);opacity:0.2;')}"></div>
</div>

${menu name='Banner Container', icon='th-large'}
	${menu args->banner_style name='Banner Style', type='css', param='with_responsive=1'}
${menu name='Close Button', icon='times'}
	${menu block->close_button name='Show Close Button'}
	${menu args->close_button_html name='Close Button HTML', type='dontshowagain'}
${menu name='Optional Logo', icon='image'}
	${menu block->with_logo name='Show Logo'}
	${menu args->logo_src name='Logo URL', type='personyze_media_url'}
	${menu args->logo_style name='Logo Style', type='css', param='with_responsive=1'}
	${menu args->logo_position_desktop name='Desktop Logo Alignment', type='select', param='options=[["Center","desktop-center"],["Left","desktop-left"],["Right","desktop-right"]]'}
	${menu args->logo_position_mobile name='Mobile Logo Alignment', type='select', param='options=[["Center","mobile-center"],["Left","mobile-left"],["Right","mobile-right"]]'}
${menu name='Main Image', icon='image'}
	${menu block->right_image name='Show Main Image'}
	${menu args->right_image_src name='Main Image URL', type='personyze_media_url'}
	${menu args->right_image_img_style name='Main Image (Inner) Style', description='Control image fit, e.g., object-fit: cover/contain', type='css', param='with_responsive=1'}
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
${menu name='CTA Alignment', icon='hand-pointer-o'}
	${menu args->cta_row_style_desktop name='CTA Buttons Container Style', description='CSS for button alignment (e.g., justify-content:center;)', type='css', param='with_responsive=1'}
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


## Scheduled Maintenance Notification Banner

Includes optional FontAwesome icons, close button, customizable title, description, and actionable link.

```
<!-- Load FontAwesome -->
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css">

<div class="$responsive" data-style="${args->banner_style:html:default('position: relative;
background-color: #1E69F0;
border-radius: 8px;
padding-top: 16px;
padding-right: 20px;
padding-bottom: 16px;
padding-left: 20px;
color: #FFFFFF;
font-family: Arial, sans-serif;
box-shadow: 0 4px 8px rgba(0,0,0,0.2);
max-width: 320px;
')}">

  <style>
    .banner-icon {
      display: inline-flex;
      align-items: center;
      justify-content: center;
      font-size: 20px;
      margin-right: 8px;
    }
    .banner-headline {
      font-size: 16px;
      font-weight: 600;
      margin-bottom: 6px;
    }
    .banner-description {
      font-size: 14px;
      margin-bottom: 8px;
      line-height: 1.4;
    }
    .banner-link {
      font-size: 14px;
      text-decoration: underline;
      cursor: pointer;
    }
  </style>

  <!-- Personyze Close Button -->
  ${block->close_button:default(1)}
  <div style="${args->close_button_style:html:default('position: absolute;
top: 10px;
right: 10px;
cursor: pointer;
')}">
    ${args->close_button_html:default('<div onmouseenter="this.style.backgroundColor=this.style.outlineColor" onmouseleave="this.style.backgroundColor=this.style.textDecorationColor" style="display: inline-block; vertical-align: text-bottom; width: 17px; height: 17px; box-sizing: border-box; border-radius: 50%; border: 0px solid; -webkit-box-shadow: none; padding: 2px; background-color: rgba(0, 0, 0, 0); text-decoration-color: rgba(0, 0, 0, 0); outline-color: rgb(206, 54, 64); outline-width: 5px; color: rgb(247, 247, 247); cursor: pointer; transition: 0.3s;" class="$personyze_button_dont_show_again" data-action_id="${action_id}"><div style="display: block; width: 100%; height: 100%; transition: 0.3s; border-radius: 50%; background-image: linear-gradient(-45deg, transparent 0%, transparent 48%, currentcolor 48%, currentcolor 54%, transparent 54%, transparent 100%), linear-gradient(45deg, transparent 0%, transparent 48%, currentcolor 48%, currentcolor 54%, transparent 54%, transparent 100%);"></div></div>')}
  </div>

  <div style="display:flex;align-items:center;">
    ${block->with_icon:default(1)}
    <div class="banner-icon">
      <i class="$icon ${args->icon_class:html:default(bell)}" style="${args->icon_style:html:default('color:#FFFFFF;')}"></i>
    </div>

    <div>
      ${block->with_headline:default(1)}
      <div class="banner-headline" style="${args->headline_style:html}">
        ${args->headline:default(Scheduled Maintenance)}
      </div>

      ${block->with_description:default(1)}
      <div class="banner-description" style="${args->description_style:html}">
        ${args->description:default('16 Apr 2025 from 19:00 to 21:00 EDT')}
      </div>

      ${block->with_link:default(1)}
      <div>
        <a ${args->link_attrs:default('href="#"')} class="banner-link" style="${args->link_style:html:default('color: rgb(252, 252, 252);
')}">
          ${args->link_text:default(View latest updates)}
        </a>
      </div>
    </div>
  </div>
</div>

<!-- ✅ COMPLETE PERSONYZE MENU -->

${menu name='Banner Container', icon='square'}
	${menu args->banner_style name='Banner Style', type='css', param='with_responsive=1'}
${menu name='Close Button', icon='times-circle'}
	${menu block->close_button name='Show Close Button'}
	${menu args->close_button_html name='Close Button HTML', type='dontshowagain'}
	${menu args->close_button_style name='Close Button Style', type='css', param='with_responsive=1'}
${menu name='Icon Settings', icon='info-circle'}
	${menu block->with_icon name='Show Icon'}
	${menu args->icon_class name='Icon', type='icon'}
	${menu args->icon_style name='Icon Style', type='css', param='with_responsive=1'}
${menu name='Headline Text', icon='header'}
	${menu block->with_headline name='Show Headline'}
	${menu args->headline name='Headline Text'}
	${menu args->headline_style name='Headline Style', type='css', param='with_responsive=1'}
${menu name='Description Text', icon='align-left'}
	${menu block->with_description name='Show Description'}
	${menu args->description name='Description Text'}
	${menu args->description_style name='Description Style', type='css', param='with_responsive=1'}
${menu name='Link Settings', icon='link'}
	${menu block->with_link name='Show Link'}
	${menu args->link_text name='Link Text'}
	${menu args->link_attrs name='Link Attributes', type='a_attrs'}
	${menu args->link_style name='Link Style', type='css', param='with_responsive=1'}
```


