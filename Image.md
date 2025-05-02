# Personyze banner templates


## Personal Message



```
<div class="$responsive" data-style="${args->style:html:default('width:sel(700px, 80vw); background-color:#E7E7E7'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(0, 0, 'Box', 'th-large')}">
	<div data-style="position:relative; ${args->td_style:html:default('padding:sel(20px, 3vw) sel(100px, 8vw) 5px; text-align:center; color:black; font-size:14px'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(1, 1, 'Content', 'bookmark')}">
		${args->content:default(Download our FREE Testing Toolkit! Download our FREE Testing Toolkit! Download our FREE Testing Toolkit! Download our FREE Testing Toolkit!):arg_name(Text):arg_section(1, 0, 'Content', 'bookmark')}
		<div style="text-align:inherit">
			<a href="${args->href:html:default('#'):arg_name(URL):arg_section(2, 2, 'Action button', 'link')}" target="${args->target:html:default(_self):input_type(a_target):arg_name(Open link in):arg_section(2, 3, 'Action button', 'link')}" data-style="display:inline-block; ${args->action_button_text_style:html:default('text-decoration:none; width:sel(250px, 40vw); margin:1em 0 0.5em; padding:10px 0; background-color:blue; border-radius:5px; font-size:16px; color:white'):input_type(css):input_props('with_responsive=1'):arg_name(Text style):arg_section(2, 1, 'Action button', 'link')}">
				${args->action_button_text:default(GET IT NOW):arg_name(Text):arg_section(2, 0, 'Action button', 'link')}
			</a>
		</div>
		${block->show_close_button:default(1):arg_name(Show close button):arg_section(3, 0, 'Close button', 'close')}
		<div data-style="position:absolute; cursor:pointer; ${args->close_button_style:html:default('top:8px; right:8px'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(3, 1, 'Close button', 'close')}">
			${args->close_button:default('<div onmouseenter="this.style.backgroundColor=this.style.outlineColor" onmouseleave="this.style.backgroundColor=this.style.textDecorationColor" style="display: inline-block; vertical-align: text-bottom; width: 24px; height: 24px; box-sizing: border-box; border-top-left-radius: 50%; border-top-right-radius: 50%; border-bottom-right-radius: 50%; border-bottom-left-radius: 50%; border: 2px solid; -webkit-box-shadow: rgba(255, 255, 255, 0.2) 0px 1px 0px inset, rgba(0, 0, 0, 0.2) 0px 1px 2px; padding: 3px; background-color: rgb(58, 110, 207); text-decoration-color: rgb(58, 110, 207); outline-color: rgb(206, 54, 64); outline-width: 10px; color: rgb(244, 242, 242); cursor: pointer; transition: all 0.3s ease;" class="$personyze_button_dont_show_again" data-action_id="${action_id}"><div style="display: block; width: 100%; height: 100%; transition: all 0.3s ease 0s; border-top-left-radius: 50%; border-top-right-radius: 50%; border-bottom-right-radius: 50%; border-bottom-left-radius: 50%; background-image: linear-gradient(-45deg, transparent 0%, transparent 46%, currentcolor 46%, currentcolor 56%, transparent 56%, transparent 100%), linear-gradient(45deg, transparent 0%, transparent 46%, currentcolor 46%, currentcolor 56%, transparent 56%, transparent 100%);"></div></div>'):input_type(dontshowagain):arg_name(Close button):arg_section(3, 2, 'Close button', 'close')}
		</div>
	</div>
</div>
```


## 2 Buttons



```
<div class="$responsive" data-style="position:relative; overflow:hidden; ${args->box_style:html:default('max-width: 640px;
background-color: #002856;
width: 640px;
color: #002856;
border-radius: 5px;'):input_type(css):input_props('with_responsive=1'):arg_name(Box style):arg_section(0, 0, 'Box', 'th-large')}" >
	<table style="border-collapse:collapse; border:none">
		<tr style="border:none">
			<td style="border:none; background-repeat:no-repeat; background-position:center; ${args->image_style:html:default('background-image: url(''https://cdn.personyze.com/upload/362/9021b00a37b389c0.jpeg'');
background-size: 100% 100%;'):input_type(css):arg_name(Picture URL):arg_section(1, 0, 'Picture', 'image')}">
				<div data-style="width:${args->image_width:html:default('sel(300px, 40vw)'):input_type(css_length):input_props('with_responsive=1'):arg_name('Image width', 'Picture URL'):arg_section(1, 1, 'Picture', 'image')}; height:${args->image_height:html:default('sel(300px, 40vw)'):input_type(css_length):input_props('with_responsive=1'):arg_name('Image height', 'Picture URL'):arg_section(1, 2, 'Picture', 'image')}"></div>
			</td>
			<td style="border:none; padding:0 1em">
				<div data-style="max-height:${args->image_height:html}">
					<div data-style="outline:0; ${args->title_style:html:default('color: #fff;
font-size: sel(30px, 4vw);
font-weight: 300;
line-height: 32px;
text-align: center;
margin-top: 30px;
margin-right: 0px;
margin-bottom: 0px;
margin-left: 0px;'):input_type(css):input_props('with_responsive=1'):arg_name(Title style):arg_section(2, 1, 'Content', 'bars')}">
						${args->title:default('<div style="text-align: center;">Text Text<br />
Text Text</div>
'):arg_name(Title):arg_section(2, 0, 'Content', 'bars')}
					</div>
					<div data-style="outline:0; ${args->text_style:html:default('text-align: center;
color: #ffffff;
font-size: sel(18px, 4vw);
padding: 5px;
line-height: 24px;
font-weight: 200;'):input_type(css):input_props('with_responsive=1'):arg_name(Title style):arg_section(2, 3, 'Content', 'bars')}">
						${args->text:default('<p style="text-align: center;">Text TextText TextText TextText TextText TextText TextText Text</p>
'):arg_name(Text):arg_section(2, 2, 'Content', 'bars')}
					</div>
					<div style="text-align:center; ${args->buttons_style:html:default('margin-top: 1em;
margin-right: 0;
margin-bottom: 2em;
margin-left: 0;'):input_type(css):input_props('with_responsive=1'):arg_name(Buttons margin):arg_section(3, 4, 'First Button', 'hand-o-up')}">
						${block->show_button:default(1):arg_name(Show button):arg_section(3, 0, 'First Button', 'hand-o-up')}
						<a ${args->href:default('href="javascript:" class="$personyze_button_dont_show_again" data-action_id="${action_id}" data-n_sessions="0"'):input_type(a_attrs):arg_name(URL):arg_section(3, 2, 'First Button', 'hand-o-up')} data-style="${args->button_text_style:html:default('font-family: Arial;
font-size: sel(15px, 4vw);
color: white;
text-decoration: none;
background-color: #f7941e;
padding-top: 15px;
padding-right: 20px;
padding-bottom: 15px;
padding-left: 20px;
border-radius: 2px;
font-weight: bolder;
margin-top: 1px;
margin-right: 1px;
margin-bottom: 1px;
margin-left: 1px;
width: 100%;'):input_type(css):input_props('with_responsive=1'):arg_name(Button text style):arg_section(3, 3, 'First Button', 'hand-o-up')}">  ${args->button_t:default(GOT IT!):arg_name(Text_button):arg_section(3, 1, 'First Button', 'hand-o-up')}
						</a>

						${block->show_button_2:default(1):arg_name(Show second button):arg_section(4, 0, 'Second Button', 'hand-o-up')}
						<a ${args->href_3:input_type(a_attrs):arg_name(URL):arg_section(4, 2, 'Second Button', 'hand-o-up')} data-style="display:inline-block; ${args->button_text_style_2:html:input_type(css):input_props('with_responsive=1'):arg_name(Button text style):arg_section(4, 3, 'Second Button', 'hand-o-up')}">
							${args->button_t_2:arg_name(Text_button):arg_section(4, 1, 'Second Button', 'hand-o-up')}
						</a>
					</div>
				</div>
			</td>
		</tr>
	</table>
	${block->show_close_button:default(1):arg_name(Show close button):arg_section(5, 0, 'Close Button', 'times-circle')}
	<div data-style="position:absolute; cursor:pointer; ${args->close_button_style:html:default('top: 8px;
right: 8px;
z-index: 9999;'):input_type(css):input_props('with_responsive=1'):arg_name(Close Button Style):arg_section(5, 1, 'Close Button', 'times-circle')}">
		${args->close_button:default('<div onmouseenter="this.style.backgroundColor=this.style.outlineColor" onmouseleave="this.style.backgroundColor=this.style.textDecorationColor" style="display: inline-block; vertical-align: text-bottom; width: 24px; height: 24px; box-sizing: border-box; border-top-left-radius: 50%; border-top-right-radius: 50%; border-bottom-right-radius: 50%; border-bottom-left-radius: 50%; border: 2px solid; -webkit-box-shadow: rgba(255, 255, 255, 0.2) 0px 1px 0px inset, rgba(0, 0, 0, 0.2) 0px 1px 2px; padding: 3px; background-color: rgb(207, 120, 58); text-decoration-color: rgb(207, 120, 58); outline-color: rgb(206, 54, 64); outline-width: 10px; color: rgb(10, 4, 4); cursor: pointer; transition: all 0.3s ease;" class="$personyze_button_dont_show_again" data-action_id="${action_id}"><div style="display: block; width: 100%; height: 100%; transition: all 0.3s ease 0s; border-top-left-radius: 50%; border-top-right-radius: 50%; border-bottom-right-radius: 50%; border-bottom-left-radius: 50%; background-image: linear-gradient(-45deg, transparent 0%, transparent 46%, currentcolor 46%, currentcolor 56%, transparent 56%, transparent 100%), linear-gradient(45deg, transparent 0%, transparent 46%, currentcolor 46%, currentcolor 56%, transparent 56%, transparent 100%);"></div></div>'):input_type(dontshowagain):arg_name(Close button):arg_section(5, 2, 'Close Button', 'times-circle')}
	</div>
</div>
```


## Fullscreen few steps popup



```
<table class="$responsive" data-style="border-collapse:collapse; ${args->style:html:default('width: sel(100%, auto);
height: sel(100%, auto);
background-image: url(''https://static.personyze.com/upload/362/7d0a26d42b6f9a72.jpeg'');
background-size: cover;
background-color: white;')}">
	<tr>
		<td data-style="position:relative; ${args->style_2:html:default('background-color: rgba(9, 6, 6, 0.57);
color: black;
text-align: center;
vertical-align: middle;
padding-top: 10%;
padding-right: sel(10%, 10px);
padding-bottom: 10%;
padding-left: sel(10%, 10px);')}">
			<img src="${args->image_src:html:default('https://counter.personyze.com/images/logo.png')}" style="${args->image_style:html:default('width:auto; height:auto; border:none')}">
			<div id="sw" class="$switch-elem" data-case="0">
				<div data-case="0">
					<div data-style="margin:${args->margin:html:default('sel(12px, 8px)')} 0; ${args->style_t1:html:default('color:white; font-size:sel(25px, 5vw)')}">
						${args->text_1:default(Your Title Goes Here)}
					</div>
					<div data-style="margin:${args->margin:html} 0; ${args->style_t2:html:default('color: white;
font-size: sel(14px, 4vw);')}">
						${args->text_2:default(Sub tile goes here Sub tile goes here Sub tile goes hereSub tile goes hereSub tile goes hereSub tile goes hereSub tile goes hereSub tile goes hereSub tile goes hereSub tile goes hereSub tile goes hereSub tile goes hereSub tile goes here Sub tile goes hereSub tile goes here Sub tile goes here v Sub tile goes here vSub tile goes here)}
					</div>
					<div data-style="margin:${args->margin:html} 0">
						${settings->a:onclick('by_id.sw._set_case(1, null, false, {template: ''animator_fade''})')}
						<a class="$flat_btn" with_responsive="1" onclick="by_id.sw._set_case(1, null, false, {template: 'animator_fade'})" data-style="display:inline-block; width:${args->button_width:html:default('sel(110px, 33vw)')}; height:${args->button_height:html:default(30px)}; line-height:${args->button_height:html}; ${args->yes_style:html:default('background-color: rgb(96, 142, 77);
color: white;
border-radius: 15px;
box-shadow: 0 0 2px rgba(13, 7, 7, 0.6);
margin: 10px;')}" hover_style="${args->yes_h_style:html:default('color: white;
background-color: red;')}">
							${args->yes_1:default(Button 1)}
						</a>
						${block->with_second_button:default(1)}
						<a class="$flat_btn $personyze_button_dont_show_again" with_responsive="1" data-action_id="${action_id:html}" data-style="display:inline-block; width:${args->button_width:html}; height:${args->button_height:html}; line-height:${args->button_height:html}; ${args->b2_style:html:default('background-color: rgb(160, 131, 131);
color: white;
border-radius: 15px;
box-shadow: 0 0 2px rgba(13, 7, 7, 0.6);')}" hover_style="${args->yes_h_style:html}">
							${args->b2_1:default(close)}
						</a>
					</div>
				</div>

				<div data-case="1">
					<div data-style="margin:${args->margin:html} 0; ${args->style_t4:html:default('color:white; font-size:sel(25px, 5vw)')}">
						${args->text_4:default(Your offer goes here Your offer goes here Your offer goes hereYour offer goes hereYour offer goes here)}
					</div>
					<div data-style="margin:${args->margin:html} 0">
						<a class="$flat_btn" with_responsive="1" href="${args->href_2:html:default('#')}" target="${args->target_2:html:default(_blank)}" data-style="display:inline-block; width:${args->button_width:html}; height:${args->button_height:html}; line-height:${args->button_height:html}; ${args->yes_style:html}" hover_style="${args->yes_h_style:html}">
							${args->close_1:default(Get offer)}
						</a>
					</div>
					<div data-style="margin:${args->margin:html} 0">
						${block->with_close_4:default(1)}
						<a class="$personyze_button_dont_show_again" data-action_id="${action_id:html}" data-style="${args->b4_style:html:default('text-decoration: none;
color: rgba(256, 256, 256, 0.83);')}">
							${args->b4_1:default('<br />
<br />
Close')}
						</a>
					</div>
				</div>
			</div>
			${block->show_close_button:default(1)}
			<div data-style="position:absolute; cursor:pointer; ${args->close_button_style:html:default('top: 6px;
right: 6px;
')}">
				${args->close_button:default('<div onmouseenter="this.style.backgroundColor=this.style.outlineColor" onmouseleave="this.style.backgroundColor=this.style.textDecorationColor" style="display: inline-block; vertical-align: text-bottom; width: 24px; height: 24px; box-sizing: border-box; border-radius: 50%; border: 2px solid; box-shadow: rgba(255, 255, 255, 0.2) 0px 1px 0px inset, rgba(0, 0, 0, 0.2) 0px 1px 2px; padding: 3px; background-color: white; text-decoration-color: white; outline-color: rgb(206, 54, 64); outline-width: 10px; color: rgb(10, 4, 4); cursor: pointer; transition: all 0.3s ease 0s;" class="$personyze_button_dont_show_again" data-action_id="${action_id}"><div style="display: block; width: 100%; height: 100%; transition: all 0.3s ease 0s; border-radius: 50%; background-image: linear-gradient(-45deg, transparent 0%, transparent 46%, currentcolor 46%, currentcolor 56%, transparent 56%, transparent 100%), linear-gradient(45deg, transparent 0%, transparent 46%, currentcolor 46%, currentcolor 56%, transparent 56%, transparent 100%);"></div></div>')}
			</div>
		</td>
	</tr>
</table>

${menu name='Box', icon='th-large'}
	${menu args->style name='Style', type='css', param='with_responsive=1'}
	${menu args->style_2 name='Style', type='css', param='with_responsive=1'}
	${menu args->margin name='Paragraph spacing', type='css_length', param='with_responsive=1'}
	${menu args->button_width name='Button Width', type='css_length', param='with_responsive=1'}
	${menu args->button_height name='Button Height', type='css_length', param='with_responsive=1'}
${menu name='Logo', icon='image'}
	${menu args->image_src name='URL', type='personyze_media_url'}
	${menu args->image_style name='Image style', type='css', param='with_responsive=1'}
${menu name='Step 1', icon='bars'}
	${menu args->style_t1 name='Style', type='css', param='with_responsive=1'}
	${menu args->style_t2 name='Style', type='css', param='with_responsive=1'}
	${menu args->text_1 name='Line 1'}
	${menu args->text_2 name='Line 1'}
	${menu args->yes_1 name='Button 1 text'}
	${menu args->b2_1 name='Button 2 text'}
	${menu args->yes_style name='Button 1 Style', type='css'}
	${menu args->yes_h_style name='Button 1 Hover Style', type='css'}
	${menu block->with_second_button name='Show Button 2'}
	${menu args->b2_style name='Button 2 Style', type='css'}
${menu name='Step 2', icon='bars'}
	${menu args->text_4 name='Line 1'}
	${menu args->style_t4 name='Style', type='css', param='with_responsive=1'}
	${menu args->href_2 name='Button 3 URL'}
	${menu args->target_2 name='Button 3 Open link in', type='a_target'}
	${menu args->close_1 name='Button 3 text'}
	${menu block->with_close_4 name='Show Close Link'}
	${menu args->b4_1 name='Close Link'}
	${menu args->b4_style name='Close Link Style', type='css'}
${menu name='Close Button', icon='times-circle'}
	${menu block->show_close_button name='Show close button'}
	${menu args->close_button_style name='Close Button Style', type='css', param='with_responsive=1'}
	${menu args->close_button name='Close button', type='dontshowagain'}
```


## Message



```
<link href='https://fonts.googleapis.com/css?family=Source+Sans+Pro:400,300,600,700' rel='stylesheet' type='text/css'>
<link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/font-awesome/4.4.0/css/font-awesome.min.css">
<style id="pahkuhou2_styles"></style>
<div id="pahkuhou2_popup" style="position:relative; box-sizing: border-box; ${args->style:html:default('width: 352px;
background-color: rgba(236, 240, 241, 1);
border: 7px solid #fff;
text-align: center;
')}" data-action_id="${action_id:html}">

${block->show_close_button:default(1)}
<div style="cursor:pointer; position:absolute; z-index:1; ${args->close_button_style:html:default('top: 15px;
right: 8px;
')}">
    ${args->close_button:default('<div onmouseenter="this.style.backgroundColor=this.style.outlineColor" onmouseleave="this.style.backgroundColor=this.style.textDecorationColor" style="display: inline-block; vertical-align: text-bottom; width: 24px; height: 24px; box-sizing: border-box; border-radius: 50%; border: 0px solid; box-shadow: none; padding: 2px; background-color: rgba(0, 0, 0, 0); text-decoration-color: rgba(0, 0, 0, 0); outline-color: rgb(206, 54, 64); outline-width: 15px; color: rgb(10, 4, 4); cursor: pointer; transition: all 0.3s ease 0s;" class="$personyze_button_dont_show_again" data-action_id="${action_id}"><div style="display: block; width: 100%; height: 100%; transition: all 0.3s ease 0s; border-radius: 50%; background-image: linear-gradient(-45deg, transparent 0%, transparent 43%, currentcolor 43%, currentcolor 59%, transparent 59%, transparent 100%), linear-gradient(45deg, transparent 0%, transparent 43%, currentcolor 43%, currentcolor 59%, transparent 59%, transparent 100%);"></div></div>')}
</div>

<div style="position: absolute; padding: 4px 10px; margin-top: -5px; ${args->title_style:html:default('background-color: white;
color: rgb(83, 112, 167);
font-family: Source Sans Pro,sans-serif;
font-size: 16px;
font-weight: 600;
letter-spacing: 1px;
')}">${args->title_text:default(NEW!)}</div>
<div style="padding: 0 20px; margin-top: 40px; ${args->content_style:html:default('font-size: 17px;
color: #464646;
line-height: 24px;
font-family: Source Sans Pro,sans-serif;
font-weight: 400;
text-align: center;
')}">${args->content_text:default('<div style="text-align: center;">I know where you live!&nbsp;&nbsp;<br />
Scroll down or close me and I will go away.&nbsp;</div>
')}</div>

<a href="${args->button_link:html}" onclick="${args->button_link_js:html}" target="${args->button_target:html:default(_blank)}" style="${args->button_style:html:default('display: inline-block;
margin-top: 20px;
margin-right: 0;
margin-bottom: 30px;
margin-left: 0;
text-align: center;
width: 120px;
font-size: 15px;
color: white;
border-bottom: 2px solid rgb(83, 112, 167);
background-color: rgb(83, 112, 167);
border-radius: 4px;
padding-top: 8px;
padding-right: 0;
padding-bottom: 8px;
padding-left: 0;
text-decoration: none;
')}">${args->button_caption:default(Some Button)}</a>

<a href="${args->button2_link:html}" onclick="${args->button2_link_js:html}" target="${args->button2_target:html}" style="${args->button2_style:html}">${args->button2_caption}</a>
</div>
<div class="pahkuhou2-plus" style="position:absolute; top:50%; transform:translateY(-50%); display: block; cursor: pointer; ${args->label_style:html:default('font-family: Source Sans Pro,sans-serif;
font-size: 13px;
text-align: left;
letter-spacing: 1px;
')}" data-width="${args->label_width:html:default(55)}" data-height="${args->label_height:html:default(110)}" data-bgcolor="${args->label_bgcolor:html:default('#a78c53')}" ontplready="
    var popup = by_id.pahkuhou2_popup,
    style = by_id.pahkuhou2_styles,
    direction = 'right';

    switch(_S_T.act_params['${action_id:html}'].popup_settings.position_number) {
        case 1:
        case 4:
        case 7: direction = 'left'; break;
    };

    style.innerHTML = '.pahkuhou2-popup { margin-' + direction + ': 0; -webkit-transition: all 1s ease; -moz-transition: all 1s ease; -o-transition: all 1s ease; transition: all 1s ease; } ' +
        '.pahkuhou2-plus { ' + direction + ': -2000px; -webkit-transition: all 1.25s ease; -moz-transition: all 1.25s ease; -o-transition: all 1.25s ease; transition: all 1.25s ease; } ' +
        '@media all and (max-width: 900px) { .pahkuhou2-popup { margin-' + direction + ': -2000px; } .pahkuhou2-plus { ' + direction + ': 0; } }';

    var plus = this,
    popup_width = popup.getBoundingClientRect().width,
    Direction = direction[0].toUpperCase() + direction.substring(1);

    var c = plus.children[0],
        w = +plus.dataset.width.replace(/[^0-9\.-]/g, ''),
        h = (+plus.dataset.height.replace(/[^0-9\.-]/g, '')) / 2;

    plus.style['border-top'] = h + 'px solid transparent';
    plus.style['border-bottom'] = h + 'px solid transparent';
    plus.style['border' + Direction] = w + 'px solid ' + plus.dataset.bgcolor;

    if (c) c.style.transform = 'translate(' + (direction === 'left' ? -w : w - (+getComputedStyle(c).width.replace(/[^0-9\.-]/g, ''))) + 'px, -50%)';

    plus.addEventListener('click', function () {
        plus.style[direction] = '-' + popup_width + 'px';
        popup.style['margin' + Direction] = 0;
    });

    document.addEventListener('scroll', function () {
        var scrolled = window.pageYOffset || document.documentElement.scrollTop;

        if (scrolled < 150) return;

        popup.style['margin' + Direction] = '-' + popup_width + 'px';
        plus.style[direction] = 0;
    });
">

    <span style="position: absolute; ${args->label_title_style:html:default('line-height: 1;
text-align: center;
width: 2.5em;
color: white;
')}">
        ${args->label_title:default(SALE)}
    </span>
</div>

${menu name='Popup', icon='th-large'}
	${menu args->style name='Style', type='css'}
${menu name='Title', icon='bookmark'}
	${menu args->title_text name='Text'}
	${menu args->title_style name='Style', type='css'}
${menu name='Content', icon='bookmark'}
	${menu args->content_text name='Text'}
	${menu args->content_style name='Style', type='css'}
${menu name='Button', icon='check'}
	${menu args->button_caption name='Caption'}
	${menu args->button_link name='Link', type='url'}
	${menu args->button_link_js name='Javascript', type='source_javascript'}
	${menu args->button_target name='Open link in', type='a_target'}
	${menu args->button_style name='Style', type='css'}
${menu name='Second Button', icon='check'}
	${menu args->button2_caption name='Caption'}
	${menu args->button2_link name='Link', type='url'}
	${menu args->button2_link_js name='Javascript', type='source_javascript'}
	${menu args->button2_target name='Open link in', type='a_target'}
	${menu args->button2_style name='Style', type='css'}
${menu name='Close button', icon='close'}
	${menu args->close_button name='Close button', type='dontshowagain'}
${menu name='Label', icon='bookmark'}
	${menu args->label_title name='Text'}
	${menu args->label_title_style name='Style', type='css'}
	${menu args->label_width name='Width, px'}
	${menu args->label_height name='Height, px'}
	${menu args->label_bgcolor name='Background color', type='color'}
	${menu args->label_style name='Style', type='css'}
```


## Tall-banner



```
<div class="$responsive" data-style="box-sizing: border-box;
margin: 0 auto;
position: relative;
overflow: hidden;
${args->style:html:default('
width: 160px;
height: 600px;
border: 1px solid #0c0c0e'):input_type(css):input_props('with_responsive=1'):arg_name(Box style):arg_section(0, 0, 'Box', 'th-large')}
">
<div data-style="position: absolute;
	width:100%;
	height: 100%;
	background-image: url(${args->image_bgc:html:default():input_type(personyze_media_url):arg_name(Background image):arg_section(0, 1, 'Box', 'th-large')});
	background-repeat: no-repeat;
	background-position: 0 50%;
	${args->img_bg_style:html:default('background-color:#33313E'):input_type(css):input_props('with_responsive=1'):arg_name(Background style):arg_section(0, 2, 'Box', 'th-large')}"></div>

		<div data-style="position: absolute; width:100%;
		${args->content_title1_position:html:default('
		text-align: center;
		top: 80px'):input_type(css):input_props('with_responsive=1'):arg_name(Title position):arg_section(1, 0, 'Title', 'bookmark')}">
		<span data-style="
			${args->action_text_style:html:default('
			font-family: Viga;
			color: #fff;
			font-size: 25px;
			line-height: 0.9;
			letter-spacing: 2px'):input_type(css):input_props('with_responsive=1'):arg_name(Title line 1 font):arg_section(1, 2, 'Title', 'bookmark')}">
			${args->title:default(ANNUAL):arg_name(Title line 1):arg_section(1, 1, 'Title', 'bookmark')}
			<span data-style="
				${args->action_text2_style:html:default('
				color: #fff;
				font-size: 22px;
				letter-spacing: 1px'):input_type(css):input_props('with_responsive=1'):arg_name(Title line 2 font):arg_section(1, 4, 'Title', 'bookmark')}
				">${args->title2:default(BUSINESS):arg_name(Title line 2):arg_section(1, 3, 'Title', 'bookmark')}</span>  <span data-style="
			${args->action_text3_style:html:default('
			color: #fff;
			font-size: 18px;
			letter-spacing: 0'):input_type(css):input_props('with_responsive=1'):arg_name(Title line 3 font):arg_section(1, 6, 'Title', 'bookmark')}
			">${args->title3:default(CONFERENCE):arg_name(Title line 3):arg_section(1, 5, 'Title', 'bookmark')}</span></span>
		</div>
		<div data-style="position: absolute;
			width: 100%;
			${args->content_style:html:default('
			font-family: ''Open Sans'';
			color: #fff;
			text-align: center;
			top: 250px;
			font-size: 22px;
			line-height: 0.9;
			letter-spacing: 0'):input_type(css):input_props('with_responsive=1'):arg_name(Line 4 font):arg_section(2, 0, 'Text', 'file-text')}
			">${args->title4:default('for<br />
innovative<br />
technologies'):arg_name(Line 4):arg_section(2, 1, 'Text', 'file-text')}
		</div>

<div data-style="position: absolute;
width: 100%;
${args->button_style:html:default('text-align: center;
bottom: 150px;'):input_type(css):input_props('with_responsive=1'):arg_name(Button position):arg_section(4, 3, 'Button', 'hand-o-up')}">
<a href="${args->href:html:default('#'):arg_name(URL):arg_section(4, 1, 'Button', 'hand-o-up')}" target="${args->target:html:default(_self):input_type(a_target):arg_name(Open link in):arg_section(4, 2, 'Button', 'hand-o-up')}"
	data-style="letter-spacing: 0;
	${args->button_text_style:html:default('
	font-family: Viga;
	color: #fff;
	font-size: 20px;
	line-height: 1;
	letter-spacing: 0;
	padding: 10px 20px;
	text-decoration: none;
	background-color: #fc5729'):input_type(css):input_props('with_responsive=1'):arg_name(Button style):arg_section(4, 4, 'Button', 'hand-o-up')}">
	${args->title_button:default(ATTEND):arg_name(Button text):arg_section(4, 0, 'Button', 'hand-o-up')}
</a>
</div>
<div data-style="position: absolute;
width: 100%;
${args->pace_position:html:default('
text-align: center;
bottom: 35px'):input_type(css):input_props('with_responsive=1'):arg_name(Position_Place_1):arg_section(3, 0, 'Place', 'file-text')}
">
<span data-style="
	${args->place_style:html:default('font-family: ''Open Sans'';
	font-weight: 200;
	color: #fff;
	font-size: 12px;
	line-height: 1;
	letter-spacing: 0'):input_type(css):input_props('with_responsive=1'):arg_name(Style_Place_1):arg_section(3, 1, 'Place', 'file-text')}
	">${args->title_place:default('July 25-26, Paris'):arg_name(Place_text):arg_section(3, 2, 'Place', 'file-text')}</span>
</div>
${block->show_close_button:default(1):arg_name(Show close button):arg_section(5, 0, 'Close Button', 'times-circle')}
<div data-style="position:absolute; cursor:pointer; ${args->close_button_style:html:default('top:5px; right:5px;z-index:9999'):input_type(css):input_props('with_responsive=1'):arg_name(Close_btn_Style):arg_section(5, 1, 'Close Button', 'times-circle')}">
	${args->close_button:default('<div onmouseenter="this.style.backgroundColor=this.style.outlineColor" onmouseleave="this.style.backgroundColor=this.style.textDecorationColor" style="display: inline-block; vertical-align: text-bottom; width: 24px; height: 24px; box-sizing: border-box; border-top-left-radius: 50%; border-top-right-radius: 50%; border-bottom-right-radius: 50%; border-bottom-left-radius: 50%; border: 0px solid; -webkit-box-shadow: rgba(255, 255, 255, 0.2) 0px 1px 0px inset, rgba(0, 0, 0, 0.2) 0px 1px 2px; padding: 2px; background-color: rgba(0, 0, 0, 0); text-decoration-color: rgba(0, 0, 0, 0); outline-color: rgb(206, 54, 64); outline-width: 6px; color: rgb(244, 242, 242); cursor: pointer; transition: all 0.3s ease;" class="$personyze_button_dont_show_again" data-action_id="${action_id}"><div style="display: block; width: 100%; height: 100%; transition: all 0.3s ease 0s; border-top-left-radius: 50%; border-top-right-radius: 50%; border-bottom-right-radius: 50%; border-bottom-left-radius: 50%; background-image: linear-gradient(-45deg, transparent 0%, transparent 48%, currentcolor 48%, currentcolor 54%, transparent 54%, transparent 100%), linear-gradient(45deg, transparent 0%, transparent 48%, currentcolor 48%, currentcolor 54%, transparent 54%, transparent 100%);"></div></div>'):input_type(dontshowagain):arg_name(Close button):arg_section(5, 2, 'Close Button', 'times-circle')}
</div>
<link rel="stylesheet" type="text/css" href="https://fonts.googleapis.com/css?family=Viga:400|Open+Sans:400,700">
</div>
```


## Two button popup/banner



```
<div class="$responsive" data-style="position:relative; display:inline-block; ${args->style:html:default('background-color: white;
padding: 43px;
max-width: 600px;
border-radius: 5px;'):input_type(css):input_props('with_responsive=1'):arg_name(Box style):arg_section(0, 0, 'Box', 'th-large')}">
	${block->show_close_button:default(1):arg_name(Show close button):arg_section(5, 0, 'Close Button', 'times-circle')}
	<div data-style="position:absolute; cursor:pointer; ${args->close_button_style:html:default('top: -12px;
right: -10px;
z-index: 9999;'):input_type(css):input_props('with_responsive=1'):arg_name(Close_btn_Style):arg_section(5, 1, 'Close Button', 'times-circle')}">
		${args->close_button:default('<div onmouseenter="this.style.backgroundColor=this.style.outlineColor" onmouseleave="this.style.backgroundColor=this.style.textDecorationColor" style="display: inline-block; vertical-align: text-bottom; width: 22px; height: 22px; box-sizing: border-box; border-top-left-radius: 50%; border-top-right-radius: 50%; border-bottom-right-radius: 50%; border-bottom-left-radius: 50%; border: 0px solid; -webkit-box-shadow: rgba(255, 255, 255, 0.2) 0px 1px 0px inset, rgba(0, 0, 0, 0.2) 0px 1px 2px; padding: 6px; background-color: black; text-decoration-color: black; outline-color: rgb(206, 54, 64); outline-width: 10px; color: rgb(255, 255, 255); cursor: pointer; transition: all 0.3s ease;" class="$personyze_button_dont_show_again" data-action_id="${action_id}"><div style="display: block; width: 100%; height: 100%; transition: all 0.3s ease 0s; border-top-left-radius: 50%; border-top-right-radius: 50%; border-bottom-right-radius: 50%; border-bottom-left-radius: 50%; background-image: linear-gradient(-45deg, transparent 0%, transparent 46%, currentcolor 46%, currentcolor 56%, transparent 56%, transparent 100%), linear-gradient(45deg, transparent 0%, transparent 46%, currentcolor 46%, currentcolor 56%, transparent 56%, transparent 100%);"></div></div>'):input_type(dontshowagain):arg_name(Close button):arg_section(5, 2, 'Close Button', 'times-circle')}
	</div>

	<table data-style="width:100%; border-collapse:collapse">
		<tr>
			<td style="text-align:center; padding:0">
				<img src="${args->image_src:html:default('https://static.personyze.com/upload/362/2ced8f83fce5a056.png'):input_type(personyze_media_url):arg_name(URL):arg_section(1, 0, 'Image', 'image')}" style="vertical-align:bottom; ${args->image_style:html:default('width: sel(550px, 60vw);
height: sel(33px, 40vw);
max-width: 400px;'):input_type(css):input_props('with_responsive=1'):arg_name(Text 1 style):arg_section(1, 1, 'Image', 'image')}">
			</td>
		</tr>
		<tr>
			<td style="text-align:center; ${args->text_1_style:html:default('background-color: rgba(0, 0, 0, 0);
color: white;'):input_type(css):input_props('with_responsive=1'):arg_name(Text 1 style):arg_section(2, 0, 'Text 1', 'bars')}">
				<div data-style="${args->line_1_style:html:default('color:black; text-align:center; font-family:Fjalla One,san-serif; font-weight:normal; font-size:28px; line-height:38px; padding:10px 40px; text-transform:uppercase; letter-spacing:2px'):input_type(css):input_props('with_responsive=1'):arg_name(Text 1 style):arg_section(2, 2, 'Text 1', 'bars')}">
					${args->line_1:default(Text Text):arg_name(Text 1 line 1):arg_section(2, 1, 'Text 1', 'bars')}
				</div>
				<div data-style="${args->line_2_style:html:default('color:black; text-align:center; font-family:Helvetica,san-serif; font-weight:normal; font-size:15px; padding:10px 0; letter-spacing:1px'):input_type(css):input_props('with_responsive=1'):arg_name(Text 1 style):arg_section(2, 4, 'Text 1', 'bars')}">
					${args->line_2:default('Text Text Text Text Text Text<br />
Text Text Text Text Text Text Text Text'):arg_name(Text 1 line 2):arg_section(2, 3, 'Text 1', 'bars')}
				</div>
			</td>
		</tr>
		<tr>
			<td style="text-align:center; padding:1em">
				<a ${args->href:default('href="javascript:" class="$personyze_button_dont_show_again" data-action_id="${action_id}" data-n_sessions="0"'):input_type(a_attrs):arg_name(URL):arg_section(3, 1, 'Button', 'hand-o-up')}
					data-style="display:inline-block; ${args->button_text_style:html:default('font-family: Fjalla One,san-serif;
font-weight: normal;
font-size: 13px;
width: 40%;
height: 40px;
line-height: 40px;
text-align: center;
text-transform: uppercase;
border: 1px solid black;
border-radius: 3px;
background-color: white;
color: black;
padding: 0;'):input_type(css):input_props('with_responsive=1'):arg_name(Button text style):arg_section(3, 2, 'Button', 'hand-o-up')}">  ${args->button_t:default(Close):arg_name(Text_button):arg_section(3, 0, 'Button', 'hand-o-up')}
				</a>

				${block->show_button_2:default(1):arg_name(Show second button):arg_section(4, 0, 'Second Button', 'hand-o-up')}
				<a ${args->href_2:default('href=""'):input_type(a_attrs):arg_name(URL):arg_section(4, 2, 'Second Button', 'hand-o-up')}
					data-style="display:inline-block; ${args->button_text_style_2:html:default('font-family: Fjalla One,san-serif;
font-weight: normal;
font-size: 13px;
width: 40%;
height: 40px;
line-height: 40px;
text-align: center;
text-transform: uppercase;
border: 0;
border-radius: 3px;
background-color: rgb(74, 135, 86);
color: rgb(248, 249, 247);
padding: 0;'):input_type(css):input_props('with_responsive=1'):arg_name(Button text style):arg_section(4, 3, 'Second Button', 'hand-o-up')}">
					${args->button_t_2:default(View):arg_name(Text_button):arg_section(4, 1, 'Second Button', 'hand-o-up')}
				</a>
			</td>
		</tr>
	</table>

	<link rel="stylesheet" type="text/css" href="https://fonts.googleapis.com/css?family=Playfair+Display+SC:400|Open+Sans:400,300|Oswald:400,700">
</div>
```


## Bottom bar



```
<div class="$responsive" data-style="position:relative; ${args->style:html:default('width: 100%;
padding-top: 10px;
padding-right: 25px;
padding-bottom: 10px;
padding-left: 25px;
text-align: center;
color: #fff;
background-color: black;
box-sizing: border-box;
vertical-align: middle;
')}">
    <link href="https://fonts.googleapis.com/css?family=Poppins" rel="stylesheet">
    <span data-style="${args->title_text_style:html:default('font-weight: normal;
font-size: 15px;
line-height: 30px;
color: white;
text-align: justify;
padding: 0px;
margin: 0;
vertical-align: middle;
')}">${args->title_text:default(YOUR TEXT)}</span>

	${block->with_button:default(1)}
	<a ${args->button_link:default('href=""')} data-style="${args->button_style:html:default('display: inline-block;
color: #fff;
font-family: Khand,sans-serif;
font-weight: normal;
font-size: 14px;
text-transform: uppercase;
text-decoration: none;
margin-left: 16px;
background-color: rgb(118, 177, 109);
padding-top: 5px;
padding-right: 15px;
padding-bottom: 5px;
padding-left: 15px;
border-radius: 20px;
')}">
		${args->button_caption:default(Learn more!)}
	</a>

	${block->with_button_2:default(1)}
	<a ${args->button_2_link:default('href=""')} data-style="${args->button_2_style:html:default('line-height: 24px;
color: #f1c40f;
border-radius: 5px;
font-family: Poppins,sans-serif;
font-weight: normal;
font-size: 10px;
text-decoration: none;
margin-top: auto;
margin-right: auto;
margin-bottom: auto;
margin-left: 16px;
vertical-align: middle;
')}">
		${args->button_2_caption:default(Contact us)}
	</a>

    ${block->show_close_button:default(1)}
    <div data-style="${args->close_button_style:html:default('position: absolute;
top: 12px;
right: 10px;
')}">
        ${args->close_button:default('<div onmouseenter="this.style.backgroundColor=this.style.outlineColor" onmouseleave="this.style.backgroundColor=this.style.textDecorationColor" style="display: inline-block; vertical-align: text-bottom; width: 24px; height: 24px; box-sizing: border-box; border-radius: 50%; border: 2px solid; -webkit-box-shadow: rgba(255, 255, 255, 0.2) 0px 1px 0px inset, rgba(0, 0, 0, 0.2) 0px 1px 2px; padding: 3px; background-color: rgba(146, 83, 83, 0.98); text-decoration-color: rgba(146, 83, 83, 0.98); outline-color: rgb(206, 54, 64); outline-width: 10px; color: rgb(255, 255, 255); cursor: pointer; transition: all 0.3s ease 0s;" class="$personyze_button_dont_show_again" data-action_id="${action_id}"><div style="display: block; width: 100%; height: 100%; transition: all 0.3s ease 0s; border-radius: 50%; background-image: linear-gradient(-45deg, transparent 0%, transparent 46%, currentcolor 46%, currentcolor 56%, transparent 56%, transparent 100%), linear-gradient(45deg, transparent 0%, transparent 46%, currentcolor 46%, currentcolor 56%, transparent 56%, transparent 100%);"></div></div>')}
    </div>
</div>

${menu name='Box', icon='th-large'}
	${menu args->style name='Style', type='css', param='with_responsive=1'}
${menu name='Title', icon='bookmark'}
	${menu args->title_text name='Text'}
	${menu args->title_text_style name='Style', type='css', param='with_responsive=1'}
${menu name='Button', icon='hand-o-up'}
	${menu block->with_button name='With button'}
	${menu args->button_link name='Link', type='a_attrs'}
	${menu args->button_caption name='Caption'}
	${menu args->button_style name='Style', type='css', param='with_responsive=1'}
${menu name='Second Button', icon='hand-o-up'}
	${menu block->with_button_2 name='With button'}
	${menu args->button_2_link name='Link', type='a_attrs'}
	${menu args->button_2_caption name='Caption'}
	${menu args->button_2_style name='Style', type='css', param='with_responsive=1'}
${menu name='Close button', icon='close'}
	${menu block->show_close_button name='Show close button'}
	${menu args->close_button_style name='Style', type='css', param='with_responsive=1'}
	${menu args->close_button name='Close button', type='dontshowagain'}
```


## Small popup



```
<div class="$responsive" data-style="position:relative; display:inline-block; ${args->style:html:default('background-color: rgb(256, 256, 256);
padding: 10px;
border-radius: 2px;
width: 280px;
box-shadow: 0 0 8px 4px rgb(222, 207, 207);
margin-top: 1px;
margin-right: 15px;
margin-bottom: 1px;
margin-left: 1px;'):input_type(css):input_props('with_responsive=1'):arg_name(Box style):arg_section(0, 0, 'Box', 'th-large')}">
	${block->show_close_button:default(1):arg_name(Show close button):arg_section(4, 0, 'Close Button', 'times-circle')}
	<div data-style="position:absolute; cursor:pointer; ${args->close_button_style:html:default('text-align: right;
width: 100%;
top: -10px;'):input_type(css):input_props('with_responsive=1'):arg_name(Close_btn_Style):arg_section(4, 1, 'Close Button', 'times-circle')}">
		${args->close_button:default('<div onmouseenter="this.style.backgroundColor=this.style.outlineColor" onmouseleave="this.style.backgroundColor=this.style.textDecorationColor" style="display: inline-block; vertical-align: text-bottom; width: 24px; height: 24px; box-sizing: border-box; border-top-left-radius: 50%; border-top-right-radius: 50%; border-bottom-right-radius: 50%; border-bottom-left-radius: 50%; border: 0px solid; -webkit-box-shadow: rgba(255, 255, 255, 0.2) 0px 1px 0px inset, rgba(0, 0, 0, 0.2) 0px 1px 2px; padding: 5px; background-color: rgb(190, 61, 22); text-decoration-color: rgb(190, 61, 22); outline-color: rgb(110, 88, 52); outline-width: 10px; color: rgb(246, 244, 244); cursor: pointer; transition: all 0.3s ease;" class="$personyze_button_dont_show_again" data-action_id="${action_id}"><div style="display: block; width: 100%; height: 100%; transition: all 0.3s ease 0s; border-top-left-radius: 50%; border-top-right-radius: 50%; border-bottom-right-radius: 50%; border-bottom-left-radius: 50%; background-image: linear-gradient(-45deg, transparent 0%, transparent 46%, currentcolor 46%, currentcolor 56%, transparent 56%, transparent 100%), linear-gradient(45deg, transparent 0%, transparent 46%, currentcolor 46%, currentcolor 56%, transparent 56%, transparent 100%);"></div></div>'):input_type(dontshowagain):arg_name(Close button):arg_section(4, 2, 'Close Button', 'times-circle')}
	</div>

	<table data-style="width:100%; border-collapse:collapse">

		<tr>
			<td style="text-align:center; ${args->text_1_style:html:default('background-color: rgba(0, 0, 0, 0);
color: white;'):input_type(css):input_props('with_responsive=1'):arg_name(Text 1 style):arg_section(1, 0, 'Text 1', 'bars')}">
				<div data-style="${args->line_1_style:html:default('font-size: 20px;
color: rgba(38, 38, 63, 0.73);
padding-top: 40px;
padding-right: 20px;
padding-bottom: 15px;
padding-left: 20px;
font-weight: bold;'):input_type(css):input_props('with_responsive=1'):arg_name(Text 1 style):arg_section(1, 2, 'Text 1', 'bars')}">
					${args->line_1:default(TEXT TEXT TEXT TEXT  TEXT TEXT):arg_name(Text 1 line 1):arg_section(1, 1, 'Text 1', 'bars')}
				</div>
				<div data-style="${args->line_2_style:html:default('font-size: 14px;
color: rgb(90, 58, 58);
padding-top: 0px;
padding-right: 20px;
padding-bottom: 15px;
padding-left: 20px;
font-weight: lighter;
text-align: center;'):input_type(css):input_props('with_responsive=1'):arg_name(Text 1 style):arg_section(1, 4, 'Text 1', 'bars')}">
					${args->line_2:default(Text Text Text):arg_name(Text 1 line 2):arg_section(1, 3, 'Text 1', 'bars')}
				</div>
			</td>
		</tr>
		<tr>
			<td style="text-align:center; padding:1em">
				<a ${args->href:default('href=""'):input_type(a_attrs):arg_name(URL):arg_section(2, 1, 'Button', 'hand-o-up')}
					data-style="display:inline-block; ${args->button_text_style:html:default('font-size: 14px;
color: rgb(256, 256, 256);
text-decoration: none;
background-color: rgba(71,206,144,1);
padding-top: 8px;
padding-right: 15px;
padding-bottom: 8px;
padding-left: 15px;
border-radius: 2px;
font-weight: 600;
margin: 5px;
text-transform: uppercase;'):input_type(css):input_props('with_responsive=1'):arg_name(Button text style):arg_section(2, 2, 'Button', 'hand-o-up')}">  ${args->button_t:default(View Offer):arg_name(Text_button):arg_section(2, 0, 'Button', 'hand-o-up')}
				</a>

				${block->show_button_2:default(1):arg_name(Show second button):arg_section(3, 0, 'Second Button', 'hand-o-up')}
				<a ${args->href_2:default('href="javascript:" class="$personyze_button_dont_show_again" data-action_id="${action_id}" data-n_sessions="0"'):input_type(a_attrs):arg_name(URL):arg_section(3, 2, 'Second Button', 'hand-o-up')}
					data-style="display:inline-block; ${args->button_text_style_2:html:default('color: rgba(42, 28, 28, 0.45);'):input_type(css):input_props('with_responsive=1'):arg_name(Button text style):arg_section(3, 3, 'Second Button', 'hand-o-up')}">
					${args->button_t_2:default(Not interested):arg_name(Text_button):arg_section(3, 1, 'Second Button', 'hand-o-up')}
				</a>
			</td>
		</tr>
	</table>

	<link rel="stylesheet" type="text/css" href="https://fonts.googleapis.com/css?family=Playfair+Display+SC:400|Open+Sans:400,300|Oswald:400,700">
</div>
```


## Popup



```
<div class="$responsive" data-style="position:relative; display:inline-block; ${args->style:html:default('background-color: rgb(253, 253, 253);
padding-top: 6px;
padding-right: 6px;
padding-bottom: 15px;
padding-left: 6px;
border-radius: 5px;
max-width: sel(100%, 90vw);
width: 400px;
border: solid thin rgb(203, 155, 155);
height: auto;
')}">
	${block->show_close_button:default(1)}
	<div data-style="position:absolute; cursor:pointer; ${args->close_button_style:html:default('top: -12px;
right: sel(-10px, -5px);
z-index: 9999;
')}">
		${args->close_button:default('<div onmouseenter="this.style.backgroundColor=this.style.outlineColor" onmouseleave="this.style.backgroundColor=this.style.textDecorationColor" style="display: inline-block; vertical-align: text-bottom; width: 22px; height: 22px; box-sizing: border-box; border-radius: 50%; border: 0px solid; -webkit-box-shadow: rgba(255, 255, 255, 0.2) 0px 1px 0px inset, rgba(0, 0, 0, 0.2) 0px 1px 2px; padding: 6px; background-color: black; text-decoration-color: black; outline-color: rgb(206, 54, 64); outline-width: 10px; color: rgb(255, 255, 255); cursor: pointer; transition: all 0.3s ease 0s;" class="$personyze_button_dont_show_again" data-action_id="${action_id}"><div style="display: block; width: 100%; height: 100%; transition: all 0.3s ease 0s; border-radius: 50%; background-image: linear-gradient(-45deg, transparent 0%, transparent 46%, currentcolor 46%, currentcolor 56%, transparent 56%, transparent 100%), linear-gradient(45deg, transparent 0%, transparent 46%, currentcolor 46%, currentcolor 56%, transparent 56%, transparent 100%);"></div></div>')}
	</div>
<div data-style="${args->line_11_style:html:default('color: rgb(36, 36, 66);
text-align: center;
font-family: Arial;
font-weight: bold;
font-size: 20px;
line-height: 38px;
padding: 5px;
text-transform: uppercase;
letter-spacing: 1px;
')}">
					${args->line_11:default(Your title goes here)}
				</div>
				<div data-style="${args->line_12_style:html:default('color: rgb(89, 58, 58);
text-align: center;
font-family: Arial;
font-weight: normal;
font-size: 13px;
padding-top: 5px;
padding-right: 0;
padding-bottom: 10px;
padding-left: 0;
letter-spacing: 1px;
')}">
					${args->line_12:default(Free text)}
				</div>
	<table data-style="width:100%; border-collapse:collapse">
		<tr>
			<td style="text-align:center; padding:0">
				<img src="${args->image_src:html:default('https://cdn.personyze.com/upload/362/18d08e19c0855cd3.jpeg')}" style="vertical-align:bottom; ${args->image_style:html:default('max-width: 95%;
')}">
			</td>
		</tr>
		<tr>
			<td style="text-align:center; ${args->text_1_style:html:default('background-color: rgba(0, 0, 0, 0);
color: rgb(231, 219, 219);
')}">
				<div data-style="${args->line_1_style:html:default('color: rgb(70, 42, 42);
text-align: center;
font-family: Arial;
font-weight: bold;
font-size: 20px;
line-height: 38px;
padding: 5px;
text-transform: uppercase;
letter-spacing: 1px;
')}">
					${args->line_1:default(Your title goes here)}
				</div>
				<div data-style="${args->line_2_style:html:default('color: rgb(132, 185, 131);
')}">
					${args->line_2:default(Free)}
				</div>
			</td>
		</tr>
		<tr>
			<td style="text-align:center; padding:1em">
				<a ${args->href:default('href=""')}
					data-style="display:inline-block; ${args->button_text_style:html:default('font-family: Arial;
font-weight: normal;
font-size: 13px;
width: 40%;
height: 30px;
line-height: 30px;
text-align: center;
text-transform: uppercase;
border: 1px solid rgb(160, 65, 65);
border-radius: 3px;
background-color: rgb(118, 66, 66);
color: rgb(249, 247, 247);
padding: 0;
')}">  ${args->button_t:default(MORE INFO)}
				</a>

				${block->show_button_2:default(1)}
				<a ${args->href_2}
					data-style="display:inline-block; ${args->button_text_style_2:html}">
					${args->button_t_2}
				</a>
			</td>
		</tr>
	</table>

	<link rel="stylesheet" type="text/css" href="https://fonts.googleapis.com/css?family=Playfair+Display+SC:400|Open+Sans:400,300|Oswald:400,700">
</div>

${menu name='Box', icon='th-large'}
	${menu args->style name='Box style', type='css', param='with_responsive=1'}
${menu name='Text Header', icon='bars'}
	${menu args->line_11 name='Text 11 line 11'}
	${menu args->line_11_style name='Text 11 style', type='css', param='with_responsive=1'}
	${menu args->line_12 name='Text 1 line 2'}
	${menu args->line_12_style name='Text 12 style', type='css', param='with_responsive=1'}
${menu name='Image', icon='image'}
	${menu args->image_src name='URL', type='personyze_media_url'}
	${menu args->image_style name='Text 1 style', type='css', param='with_responsive=1'}
${menu name='Text 1', icon='bars'}
	${menu args->text_1_style name='Text 1 style', type='css', param='with_responsive=1'}
	${menu args->line_1 name='Text 1 line 1'}
	${menu args->line_1_style name='Text 1 style', type='css', param='with_responsive=1'}
	${menu args->line_2 name='Text 1 line 2'}
	${menu args->line_2_style name='Text 1 style', type='css', param='with_responsive=1'}
${menu name='Button', icon='hand-o-up'}
	${menu args->button_t name='Text_button'}
	${menu args->href name='URL', type='a_attrs'}
	${menu args->button_text_style name='Button text style', type='css', param='with_responsive=1'}
${menu name='Second Button', icon='hand-o-up'}
	${menu block->show_button_2 name='Show second button'}
	${menu args->button_t_2 name='Text_button'}
	${menu args->href_2 name='URL', type='a_attrs'}
	${menu args->button_text_style_2 name='Button text style', type='css', param='with_responsive=1'}
${menu name='Close Button', icon='times-circle'}
	${menu block->show_close_button name='Show close button'}
	${menu args->close_button_style name='Close_btn_Style', type='css', param='with_responsive=1'}
	${menu args->close_button name='Close button', type='dontshowagain'}
```


## Popup



```
<div class="$responsive" data-style="position:relative; display:inline-block; ${args->style:html:default('background-color: rgba(124, 176, 120, 0.55);
padding-top: 0px;
padding-right: 25px;
padding-bottom: 0px;
padding-left: 25px;
border-top-left-radius: 10px;
border-top-right-radius: 10px;
border-bottom-right-radius: 30px;
border-bottom-left-radius: 30px;
width: auto;
background-image: url(''https://cdn.personyze.com/upload/362/5c566581bb271535.jpeg'');
background-size: contain;
background-repeat: no-repeat;'):input_type(css):input_props('with_responsive=1'):arg_name(Box style):arg_section(0, 0, 'Box', 'th-large')}">
	${block->show_close_button:default(1):arg_name(Show close button):arg_section(4, 0, 'Close Button', 'times-circle')}
	<div data-style="position:absolute; cursor:pointer; ${args->close_button_style:html:default('float: right;
width: 92%;
text-align: right;
position: absolute;
top: -10px;
right: -5px;'):input_type(css):input_props('with_responsive=1'):arg_name(Close_btn_Style):arg_section(4, 1, 'Close Button', 'times-circle')}">
		${args->close_button:default('<div onmouseenter="this.style.backgroundColor=this.style.outlineColor" onmouseleave="this.style.backgroundColor=this.style.textDecorationColor" style="display: inline-block; vertical-align: text-bottom; width: 24px; height: 24px; box-sizing: border-box; border-top-left-radius: 50%; border-top-right-radius: 50%; border-bottom-right-radius: 50%; border-bottom-left-radius: 50%; border: 2px solid; -webkit-box-shadow: rgba(255, 255, 255, 0.2) 0px 1px 0px inset, rgba(0, 0, 0, 0.2) 0px 1px 2px; padding: 3px; background-color: rgb(207, 120, 58); text-decoration-color: rgb(207, 120, 58); outline-color: rgb(206, 54, 64); outline-width: 10px; color: rgb(10, 4, 4); cursor: pointer; transition: all 0.3s ease;" class="$personyze_button_dont_show_again" data-action_id="${action_id}"><div style="display: block; width: 100%; height: 100%; transition: all 0.3s ease 0s; border-top-left-radius: 50%; border-top-right-radius: 50%; border-bottom-right-radius: 50%; border-bottom-left-radius: 50%; background-image: linear-gradient(-45deg, transparent 0%, transparent 46%, currentcolor 46%, currentcolor 56%, transparent 56%, transparent 100%), linear-gradient(45deg, transparent 0%, transparent 46%, currentcolor 46%, currentcolor 56%, transparent 56%, transparent 100%);"></div></div>'):input_type(dontshowagain):arg_name(Close button):arg_section(4, 2, 'Close Button', 'times-circle')}
	</div>

	<table data-style="width:100%; border-collapse:collapse">

		<tr>
			<td style="text-align:center; ${args->text_1_style:html:default('background-color: rgba(0, 0, 0, 0);
color: white;'):input_type(css):input_props('with_responsive=1'):arg_name(Text 1 style):arg_section(1, 0, 'Text 1', 'bars')}">
				<div data-style="${args->line_1_style:html:default('font-size: 28px;
color: rgb(251, 250, 250);
padding-top: 40px;
padding-right: 20px;
padding-bottom: 0px;
padding-left: 0px;
font-weight: bold;
text-align: left;
text-transform: none;'):input_type(css):input_props('with_responsive=1'):arg_name(Text 1 style):arg_section(1, 2, 'Text 1', 'bars')}">
					${args->line_1:default(Title goes here):arg_name(Text 1 line 1):arg_section(1, 1, 'Text 1', 'bars')}
				</div>
				<div data-style="${args->line_2_style:html:default('font-size: 18px;
margin-top: 0;
margin-right: 0;
margin-bottom: 0px;
margin-left: 0;
font-weight: 400;
color: rgb(256, 256, 256);
line-height: 1.3;
text-align: left;'):input_type(css):input_props('with_responsive=1'):arg_name(Text 1 style):arg_section(1, 4, 'Text 1', 'bars')}">
					${args->line_2:default('Description goes here<br />
&nbsp;'):arg_name(Text 1 line 2):arg_section(1, 3, 'Text 1', 'bars')}
				</div>
			</td>
		</tr>
		<tr>
			<td style="text-align:center; padding:1em">
				<a ${args->href:default('href="" data-personyze-click-target=""'):input_type(a_attrs):arg_name(URL):arg_section(2, 1, 'Button', 'hand-o-up')}
					data-style="display:inline-block; ${args->button_text_style:html:default('height: auto;
border: 2px solid rgb(70, 143, 61);
line-height: 25px;
text-align: center;
color: rgb(251, 250, 250);
border-radius: 15px;
font-size: 1.2em;
text-decoration: none;
padding-top: 0px;
padding-right: 15px;
padding-bottom: 0px;
padding-left: 15px;
width: 80%;
background-color: rgb(70, 143, 61);'):input_type(css):input_props('with_responsive=1'):arg_name(Button text style):arg_section(2, 2, 'Button', 'hand-o-up')}">  ${args->button_t:default(MORE INFO):arg_name(Text_button):arg_section(2, 0, 'Button', 'hand-o-up')}
				</a>

				${block->show_button_2:default(0):arg_name(Show second button):arg_section(3, 0, 'Second Button', 'hand-o-up')}
				<a ${args->href_2:input_type(a_attrs):arg_name(URL):arg_section(3, 2, 'Second Button', 'hand-o-up')}
					data-style="display:inline-block; ${args->button_text_style_2:html:input_type(css):input_props('with_responsive=1'):arg_name(Button text style):arg_section(3, 3, 'Second Button', 'hand-o-up')}">
					${args->button_t_2:arg_name(Text_button):arg_section(3, 1, 'Second Button', 'hand-o-up')}
				</a>
			</td>
		</tr>
	</table>


</div>
```


## Top or Bottom Bar



```
<div class="$responsive" data-style="position:relative; ${args->style:html:default('width:100%; padding:12px 48px; text-align:center; color:#fff; background-color:rgba(0,0,0,.8); box-sizing:border-box'):input_type(css):input_props(with_responsive=1):arg_name(Style):arg_section(0, 0, 'Box', 'th-large')}">
    <link href="https://fonts.googleapis.com/css?family=Poppins" rel="stylesheet">
    <span data-style="${args->title_text_style:html:default('font-family:Poppins,sans-serif; font-weight:normal; font-size:11px; line-height:28px'):input_type(css):input_props(with_responsive=1):arg_name(Style):arg_section(1, 1, 'Title', 'bookmark')}">${args->title_text:default('Sign up for personalized <span style="color:#ffff00;">deal alerts</span> and <span style="color:#ffff00;">exclusive discounts</span>'):arg_name(Text):arg_section(1, 0, 'Title', 'bookmark')}</span><a href="${args->button_link:html:default('javascript:'):input_type(url):arg_name(Link):arg_section(2, 2, 'Button', 'hand-o-up')}" onclick="${args->button_link_js:html:input_type(source_javascript):arg_name(Javascript):arg_section(2, 3, 'Button', 'hand-o-up')}" data-style="${args->button_style:html:default('display: inline-block;
width: 120px;
line-height: 24px;
color: #fff;
background-color: rgb(6, 224, 60);
border-radius: 5px;
font-family: Poppins,sans-serif;
font-weight: normal;
font-size: 10px;
text-decoration: none;
margin-left: 16px;
vertical-align: middle;'):input_type(css):input_props(with_responsive=1):arg_name(Style):arg_section(2, 1, 'Button', 'hand-o-up')}">${args->button_caption:default(Join Now):arg_name(Caption):arg_section(2, 0, 'Button', 'hand-o-up')}</a>
    ${block->show_close_button:default(1):arg_name(Show close button):arg_section(3, 0, 'Close button', 'close')}
    <div data-style="${args->close_button_style:html:default('position:absolute; top:18px; right:16px'):input_type(css):input_props(with_responsive=1):arg_name(Style):arg_section(3, 1, 'Close button', 'close')}">
        ${args->close_button:default('<img src="http://counter.emarketer.com/images/close-buttons/rect-white-orange-16x16.png" style="width:16px; height:16px; [object CSSStyleDeclaration]" class="$emarketer_button_dont_show_again" data-action_id="${action_id}" data-n_sessions="0">'):input_type(dontshowagain):arg_name(Close button):arg_section(3, 2, 'Close button', 'close')}
    </div>
</div>

```


## Personal Message



```
<div class="$responsive" data-style="${args->style:html:default('width:sel(700px, 80vw); background-color:#E7E7E7'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(0, 0, 'Box', 'th-large')}">
	<div data-style="position:relative; ${args->td_style:html:default('padding:sel(20px, 3vw) sel(100px, 8vw) 5px; text-align:center; color:black; font-size:14px'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(1, 1, 'Content', 'bookmark')}">
		${args->content:default(Download our FREE Testing Toolkit! Download our FREE Testing Toolkit! Download our FREE Testing Toolkit! Download our FREE Testing Toolkit!):arg_name(Text):arg_section(1, 0, 'Content', 'bookmark')}
		<div style="text-align:inherit">
			<a href="${args->href:html:default('#'):arg_name(URL):arg_section(2, 2, 'Action button', 'link')}" target="${args->target:html:default(_self):input_type(a_target):arg_name(Open link in):arg_section(2, 3, 'Action button', 'link')}" data-style="display:inline-block; ${args->action_button_text_style:html:default('text-decoration:none; width:sel(250px, 40vw); margin:1em 0 0.5em; padding:10px 0; background-color:blue; border-radius:5px; font-size:16px; color:white'):input_type(css):input_props('with_responsive=1'):arg_name(Text style):arg_section(2, 1, 'Action button', 'link')}">
				${args->action_button_text:default(GET IT NOW):arg_name(Text):arg_section(2, 0, 'Action button', 'link')}
			</a>
		</div>
		${block->show_close_button:default(1):arg_name(Show close button):arg_section(3, 0, 'Close button', 'close')}
		<div data-style="position:absolute; cursor:pointer; ${args->close_button_style:html:default('top:8px; right:8px'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(3, 1, 'Close button', 'close')}">
			${args->close_button:default('<div onmouseenter="this.style.backgroundColor=this.style.outlineColor" onmouseleave="this.style.backgroundColor=this.style.textDecorationColor" style="display: inline-block; vertical-align: text-bottom; width: 24px; height: 24px; box-sizing: border-box; border-top-left-radius: 50%; border-top-right-radius: 50%; border-bottom-right-radius: 50%; border-bottom-left-radius: 50%; border: 2px solid; -webkit-box-shadow: rgba(255, 255, 255, 0.2) 0px 1px 0px inset, rgba(0, 0, 0, 0.2) 0px 1px 2px; padding: 3px; background-color: rgb(58, 110, 207); text-decoration-color: rgb(58, 110, 207); outline-color: rgb(206, 54, 64); outline-width: 10px; color: rgb(244, 242, 242); cursor: pointer; transition: all 0.3s ease;" class="$emarketer_button_dont_show_again" data-action_id="${action_id}"><div style="display: block; width: 100%; height: 100%; transition: all 0.3s ease 0s; border-top-left-radius: 50%; border-top-right-radius: 50%; border-bottom-right-radius: 50%; border-bottom-left-radius: 50%; background-image: linear-gradient(-45deg, transparent 0%, transparent 46%, currentcolor 46%, currentcolor 56%, transparent 56%, transparent 100%), linear-gradient(45deg, transparent 0%, transparent 46%, currentcolor 46%, currentcolor 56%, transparent 56%, transparent 100%);"></div></div>'):input_type(dontshowagain):arg_name(Close button):arg_section(3, 2, 'Close button', 'close')}
		</div>
	</div>
</div>
```


## 2 Buttons tempalte



```
<div class="$responsive" data-style="position:relative; display:inline-block; ${args->style:html:default('background-color: rgb(49, 43, 73);
padding: 25px;
box-shadow: 0 0 3px 2px rgb(49, 43, 73);
border-radius: 14px;
width: 500px;'):input_type(css):input_props('with_responsive=1'):arg_name(Box style):arg_section(0, 0, 'Box', 'th-large')}">
	${block->show_close_button:default(1):arg_name(Show close button):arg_section(5, 0, 'Close Button', 'times-circle')}
	<div data-style="position:absolute; cursor:pointer; ${args->close_button_style:html:default('direction: inherit;
text-align: right;
width: 100%;
top: 12px;
left: -8px;'):input_type(css):input_props('with_responsive=1'):arg_name(Close_btn_Style):arg_section(5, 1, 'Close Button', 'times-circle')}">
		${args->close_button:default('<div onmouseenter="this.style.backgroundColor=this.style.outlineColor" onmouseleave="this.style.backgroundColor=this.style.textDecorationColor" style="display: inline-block; vertical-align: text-bottom; width: 22px; height: 22px; box-sizing: border-box; border-top-left-radius: 50%; border-top-right-radius: 50%; border-bottom-right-radius: 50%; border-bottom-left-radius: 50%; border: 0px solid; -webkit-box-shadow: rgba(255, 255, 255, 0.2) 0px 1px 0px inset, rgba(0, 0, 0, 0.2) 0px 1px 2px; padding: 3px; background-color: rgba(13, 7, 7, 0); text-decoration-color: rgba(13, 7, 7, 0); outline-color: rgb(206, 54, 64); outline-width: 10px; color: white; cursor: pointer; transition: all 0.3s ease;" class="$emarketer_button_dont_show_again" data-action_id="${action_id}"><div style="display: block; width: 100%; height: 100%; transition: all 0.3s ease 0s; border-top-left-radius: 50%; border-top-right-radius: 50%; border-bottom-right-radius: 50%; border-bottom-left-radius: 50%; background-image: linear-gradient(-45deg, transparent 0%, transparent 46%, currentcolor 46%, currentcolor 56%, transparent 56%, transparent 100%), linear-gradient(45deg, transparent 0%, transparent 46%, currentcolor 46%, currentcolor 56%, transparent 56%, transparent 100%);"></div></div>'):input_type(dontshowagain):arg_name(Close button):arg_section(5, 2, 'Close Button', 'times-circle')}
	</div>

	<table data-style="width:100%; border-collapse:collapse">
		<tr>
			<td style="text-align:center; padding:0">
				<img src="${args->image_src:html:default('https://counter.emarketer.com/images/logo.png'):input_type(emarketer_media_url):arg_name(URL):arg_section(1, 0, 'Image', 'image')}" style="vertical-align:bottom; ${args->image_style:html:default('width: sel(auto, 60vw);
height: sel(auto, 40vw);'):input_type(css):input_props('with_responsive=1'):arg_name(Text 1 style):arg_section(1, 1, 'Image', 'image')}">
			</td>
		</tr>
		<tr>
			<td style="text-align:center; ${args->text_1_style:html:default('background-color: rgba(0, 0, 0, 0);
color: white;'):input_type(css):input_props('with_responsive=1'):arg_name(Text 1 style):arg_section(2, 0, 'Text 1', 'bars')}">
				<div data-style="${args->line_1_style:html:default('font-size: 18px;
color: white;
padding: 40px;'):input_type(css):input_props('with_responsive=1'):arg_name(Text 1 style):arg_section(2, 2, 'Text 1', 'bars')}">
					${args->line_1:default(TEXT TEXT TEXT TEXT TEXT TEXT TEXT TEXT TEXT TEXT TEXT TEXT TEXT TEXT TEXT TEXT):arg_name(Text 1 line 1):arg_section(2, 1, 'Text 1', 'bars')}
				</div>
				<div data-style="${args->line_2_style:html:default('font-size:15px'):input_type(css):input_props('with_responsive=1'):arg_name(Text 1 style):arg_section(2, 4, 'Text 1', 'bars')}">
					${args->line_2:arg_name(Text 1 line 2):arg_section(2, 3, 'Text 1', 'bars')}
				</div>
			</td>
		</tr>
		<tr>
			<td style="text-align:center; padding:1em">
				<a ${args->href:default('href=""'):input_type(a_attrs):arg_name(URL):arg_section(3, 1, 'Button', 'hand-o-up')}
					data-style="display:inline-block; ${args->button_text_style:html:default('font-size: 14px;
color: rgb(36, 20, 20);
text-decoration: none;
background-color: rgb(103, 256, 73);
padding-top: 8px;
padding-right: 20px;
padding-bottom: 8px;
padding-left: 20px;
border-radius: 15px;
font-weight: bold;
margin: 5px;'):input_type(css):input_props('with_responsive=1'):arg_name(Button text style):arg_section(3, 2, 'Button', 'hand-o-up')}">  ${args->button_t:default(Button 1):arg_name(Text_button):arg_section(3, 0, 'Button', 'hand-o-up')}
				</a>

				${block->show_button_2:default(1):arg_name(Show second button):arg_section(4, 0, 'Second Button', 'hand-o-up')}
				<a ${args->href_2:default('href="Button 2"'):input_type(a_attrs):arg_name(URL):arg_section(4, 2, 'Second Button', 'hand-o-up')}
					data-style="display:inline-block; ${args->button_text_style_2:html:default('font-size: 14px;
color: rgba(256, 256, 256, 0.77);
text-decoration: none;
background-color: rgb(169, 185, 208);
padding-top: 8px;
padding-right: 20px;
padding-bottom: 8px;
padding-left: 20px;
border-radius: 15px;
font-weight: bold;
margin: 5px;'):input_type(css):input_props('with_responsive=1'):arg_name(Button text style):arg_section(4, 3, 'Second Button', 'hand-o-up')}">
					${args->button_t_2:default(Button 2):arg_name(Text_button):arg_section(4, 1, 'Second Button', 'hand-o-up')}
				</a>
			</td>
		</tr>
	</table>

	<link rel="stylesheet" type="text/css" href="https://fonts.googleapis.com/css?family=Playfair+Display+SC:400|Open+Sans:400,300|Oswald:400,700">
</div>
```


## 2 buttons



```
<div class="$responsive" data-style="position:relative; display:inline-block; ${args->style:html:default('background-color: rgb(49, 43, 73);
padding: 25px;
border-radius: 2px;
width: 550px;'):input_type(css):input_props('with_responsive=1'):arg_name(Box style):arg_section(0, 0, 'Box', 'th-large')}">
	${block->show_close_button:default(1):arg_name(Show close button):arg_section(4, 0, 'Close Button', 'times-circle')}
	<div data-style="position:absolute; cursor:pointer; ${args->close_button_style:html:default('float: right;
width: 92%;
text-align: right;'):input_type(css):input_props('with_responsive=1'):arg_name(Close_btn_Style):arg_section(4, 1, 'Close Button', 'times-circle')}">
		${args->close_button:default('<div onmouseenter="this.style.backgroundColor=this.style.outlineColor" onmouseleave="this.style.backgroundColor=this.style.textDecorationColor" style="display: inline-block; vertical-align: text-bottom; width: 24px; height: 24px; box-sizing: border-box; border-top-left-radius: 50%; border-top-right-radius: 50%; border-bottom-right-radius: 50%; border-bottom-left-radius: 50%; border: 2px solid; -webkit-box-shadow: rgba(255, 255, 255, 0.2) 0px 1px 0px inset, rgba(0, 0, 0, 0.2) 0px 1px 2px; padding: 3px; background-color: rgb(207, 120, 58); text-decoration-color: rgb(207, 120, 58); outline-color: rgb(206, 54, 64); outline-width: 10px; color: rgb(10, 4, 4); cursor: pointer; transition: all 0.3s ease;" class="$emarketer_button_dont_show_again" data-action_id="${action_id}"><div style="display: block; width: 100%; height: 100%; transition: all 0.3s ease 0s; border-top-left-radius: 50%; border-top-right-radius: 50%; border-bottom-right-radius: 50%; border-bottom-left-radius: 50%; background-image: linear-gradient(-45deg, transparent 0%, transparent 46%, currentcolor 46%, currentcolor 56%, transparent 56%, transparent 100%), linear-gradient(45deg, transparent 0%, transparent 46%, currentcolor 46%, currentcolor 56%, transparent 56%, transparent 100%);"></div></div>'):input_type(dontshowagain):arg_name(Close button):arg_section(4, 2, 'Close Button', 'times-circle')}
	</div>

	<table data-style="width:100%; border-collapse:collapse">

		<tr>
			<td style="text-align:center; ${args->text_1_style:html:default('background-color: rgba(0, 0, 0, 0);
color: white;'):input_type(css):input_props('with_responsive=1'):arg_name(Text 1 style):arg_section(1, 0, 'Text 1', 'bars')}">
				<div data-style="${args->line_1_style:html:default('font-size: 22px;
color: white;
padding-top: 40px;
padding-right: 20px;
padding-bottom: 15px;
padding-left: 20px;
font-weight: bold;'):input_type(css):input_props('with_responsive=1'):arg_name(Text 1 style):arg_section(1, 2, 'Text 1', 'bars')}">
					${args->line_1:default(TEXT TEXT TEXT TEXT TEXT TEXT TEXT TEXT TEXT TEXT TEXT TEXT TEXT TEXT TEXT TEXT):arg_name(Text 1 line 1):arg_section(1, 1, 'Text 1', 'bars')}
				</div>
				<div data-style="${args->line_2_style:html:default('font-size: 14px;
color: white;
padding-top: 0px;
padding-right: 20px;
padding-bottom: 15px;
padding-left: 20px;
font-weight: lighter;
text-align: center;'):input_type(css):input_props('with_responsive=1'):arg_name(Text 1 style):arg_section(1, 4, 'Text 1', 'bars')}">
					${args->line_2:default(TEXT TEXT TEXT TEXT TEXT TEXT TEXT TEXT TEXT TEXT TEXT TEXT TEXT TEXT TEXTEXT TEXT TEXT TEXT TEXT TEXT TEXT TEXT TEXT TEXT TEXT TEXT TEXT TEXT TEXT TEXTT TEXT):arg_name(Text 1 line 2):arg_section(1, 3, 'Text 1', 'bars')}
				</div>
			</td>
		</tr>
		<tr>
			<td style="text-align:center; padding:1em">
				<a ${args->href:default('href=""'):input_type(a_attrs):arg_name(URL):arg_section(2, 1, 'Button', 'hand-o-up')}
					data-style="display:inline-block; ${args->button_text_style:html:default('width: sel(200px, auto);
padding: sel(10px, 1vw);
border-width: 2px;
text-align: center;
font-size: sel(25px, 5vw);
background-color: rgb(220, 73, 20);
border-color: rgb(220, 73, 20);
box-shadow: 0 0 3px black;
color: rgb(256, 256, 256);
border-radius: 0px;
margin: 8px;'):input_type(css):input_props('with_responsive=1'):arg_name(Button text style):arg_section(2, 2, 'Button', 'hand-o-up')}">  ${args->button_t:default('<span style="font-weight:bold">YES</span><span style="font-size:60%">, I want it</span>'):arg_name(Text_button):arg_section(2, 0, 'Button', 'hand-o-up')}
				</a>

				${block->show_button_2:default(1):arg_name(Show second button):arg_section(3, 0, 'Second Button', 'hand-o-up')}
				<a ${args->href_2:default('href="javascript:" class="$emarketer_button_dont_show_again" data-action_id="${action_id}" data-n_sessions="0"'):input_type(a_attrs):arg_name(URL):arg_section(3, 2, 'Second Button', 'hand-o-up')}
					data-style="display:inline-block; ${args->button_text_style_2:html:default('width: sel(200px, auto);
padding: sel(10px, 1vw);
border-width: 2px;
text-align: center;
font-size: sel(25px, 5vw);
background-color: rgb(238, 232, 232);
border-color: rgb(220, 73, 20);
box-shadow: 0 0 3px black;
color: rgb(120, 79, 79);
border-radius: 0px;
margin: 8px;'):input_type(css):input_props('with_responsive=1'):arg_name(Button text style):arg_section(3, 3, 'Second Button', 'hand-o-up')}">
					${args->button_t_2:default('<span style="font-weight:bold">NO</span><span style="font-size:60%">, not now thanks</span>'):arg_name(Text_button):arg_section(3, 1, 'Second Button', 'hand-o-up')}
				</a>
			</td>
		</tr>
	</table>

	<link rel="stylesheet" type="text/css" href="https://fonts.googleapis.com/css?family=Playfair+Display+SC:400|Open+Sans:400,300|Oswald:400,700">
</div>
```


## Small Popup



```
<div class="$responsive" data-style="position:relative; display:inline-block; ${args->style:html:default('background-color: rgb(256, 256, 256);
padding: 10px;
border-radius: 2px;
width: 280px;
box-shadow: 0 0 8px 4px rgb(222, 207, 207);
margin-top: 1px;
margin-right: 15px;
margin-bottom: 1px;
margin-left: 1px;'):input_type(css):input_props('with_responsive=1'):arg_name(Box style):arg_section(0, 0, 'Box', 'th-large')}">
	${block->show_close_button:default(1):arg_name(Show close button):arg_section(4, 0, 'Close Button', 'times-circle')}
	<div data-style="position:absolute; cursor:pointer; ${args->close_button_style:html:default('text-align: right;
width: 100%;
top: -10px;'):input_type(css):input_props('with_responsive=1'):arg_name(Close_btn_Style):arg_section(4, 1, 'Close Button', 'times-circle')}">
		${args->close_button:default('<div onmouseenter="this.style.backgroundColor=this.style.outlineColor" onmouseleave="this.style.backgroundColor=this.style.textDecorationColor" style="display: inline-block; vertical-align: text-bottom; width: 24px; height: 24px; box-sizing: border-box; border-top-left-radius: 50%; border-top-right-radius: 50%; border-bottom-right-radius: 50%; border-bottom-left-radius: 50%; border: 0px solid; -webkit-box-shadow: rgba(255, 255, 255, 0.2) 0px 1px 0px inset, rgba(0, 0, 0, 0.2) 0px 1px 2px; padding: 5px; background-color: rgb(190, 61, 22); text-decoration-color: rgb(190, 61, 22); outline-color: rgb(110, 88, 52); outline-width: 10px; color: rgb(246, 244, 244); cursor: pointer; transition: all 0.3s ease;" class="$emarketer_button_dont_show_again" data-action_id="${action_id}"><div style="display: block; width: 100%; height: 100%; transition: all 0.3s ease 0s; border-top-left-radius: 50%; border-top-right-radius: 50%; border-bottom-right-radius: 50%; border-bottom-left-radius: 50%; background-image: linear-gradient(-45deg, transparent 0%, transparent 46%, currentcolor 46%, currentcolor 56%, transparent 56%, transparent 100%), linear-gradient(45deg, transparent 0%, transparent 46%, currentcolor 46%, currentcolor 56%, transparent 56%, transparent 100%);"></div></div>'):input_type(dontshowagain):arg_name(Close button):arg_section(4, 2, 'Close Button', 'times-circle')}
	</div>

	<table data-style="width:100%; border-collapse:collapse">

		<tr>
			<td style="text-align:center; ${args->text_1_style:html:default('background-color: rgba(0, 0, 0, 0);
color: white;'):input_type(css):input_props('with_responsive=1'):arg_name(Text 1 style):arg_section(1, 0, 'Text 1', 'bars')}">
				<div data-style="${args->line_1_style:html:default('font-size: 20px;
color: rgba(38, 38, 63, 0.73);
padding-top: 40px;
padding-right: 20px;
padding-bottom: 15px;
padding-left: 20px;
font-weight: bold;'):input_type(css):input_props('with_responsive=1'):arg_name(Text 1 style):arg_section(1, 2, 'Text 1', 'bars')}">
					${args->line_1:default(TEXT TEXT TEXT TEXT  TEXT TEXT):arg_name(Text 1 line 1):arg_section(1, 1, 'Text 1', 'bars')}
				</div>
				<div data-style="${args->line_2_style:html:default('font-size: 14px;
color: rgb(90, 58, 58);
padding-top: 0px;
padding-right: 20px;
padding-bottom: 15px;
padding-left: 20px;
font-weight: lighter;
text-align: center;'):input_type(css):input_props('with_responsive=1'):arg_name(Text 1 style):arg_section(1, 4, 'Text 1', 'bars')}">
					${args->line_2:default(Text Text Text):arg_name(Text 1 line 2):arg_section(1, 3, 'Text 1', 'bars')}
				</div>
			</td>
		</tr>
		<tr>
			<td style="text-align:center; padding:1em">
				<a ${args->href:default('href=""'):input_type(a_attrs):arg_name(URL):arg_section(2, 1, 'Button', 'hand-o-up')}
					data-style="display:inline-block; ${args->button_text_style:html:default('font-size: 14px;
color: rgb(256, 256, 256);
text-decoration: none;
background-color: rgba(71,206,144,1);
padding-top: 8px;
padding-right: 15px;
padding-bottom: 8px;
padding-left: 15px;
border-radius: 2px;
font-weight: 600;
margin: 5px;
text-transform: uppercase;'):input_type(css):input_props('with_responsive=1'):arg_name(Button text style):arg_section(2, 2, 'Button', 'hand-o-up')}">  ${args->button_t:default(View Offer):arg_name(Text_button):arg_section(2, 0, 'Button', 'hand-o-up')}
				</a>

				${block->show_button_2:default(1):arg_name(Show second button):arg_section(3, 0, 'Second Button', 'hand-o-up')}
				<a ${args->href_2:default('href="javascript:" class="$emarketer_button_dont_show_again" data-action_id="${action_id}" data-n_sessions="0"'):input_type(a_attrs):arg_name(URL):arg_section(3, 2, 'Second Button', 'hand-o-up')}
					data-style="display:inline-block; ${args->button_text_style_2:html:default('color: rgba(42, 28, 28, 0.45);'):input_type(css):input_props('with_responsive=1'):arg_name(Button text style):arg_section(3, 3, 'Second Button', 'hand-o-up')}">
					${args->button_t_2:default(Not interested):arg_name(Text_button):arg_section(3, 1, 'Second Button', 'hand-o-up')}
				</a>
			</td>
		</tr>
	</table>

	<link rel="stylesheet" type="text/css" href="https://fonts.googleapis.com/css?family=Playfair+Display+SC:400|Open+Sans:400,300|Oswald:400,700">
</div>
```


## Simple Popup



```
<div class="$responsive" data-style="position:relative; display:inline-block; ${args->style:html:default('background-color: rgb(238, 232, 232);
padding: 10px;
border-radius: 2px;
width: 580px;
box-shadow: 0 0 8px 4px rgb(222, 207, 207);
margin-top: 1px;
margin-right: 15px;
margin-bottom: 1px;
margin-left: 1px;'):input_type(css):input_props('with_responsive=1'):arg_name(Box style):arg_section(0, 0, 'Box', 'th-large')}">
	${block->show_close_button:default(1):arg_name(Show close button):arg_section(4, 0, 'Close Button', 'times-circle')}
	<div data-style="position:absolute; cursor:pointer; ${args->close_button_style:html:default('text-align: right;
width: 100%;
top: -10px;'):input_type(css):input_props('with_responsive=1'):arg_name(Close_btn_Style):arg_section(4, 1, 'Close Button', 'times-circle')}">
		${args->close_button:default('<div onmouseenter="this.style.backgroundColor=this.style.outlineColor" onmouseleave="this.style.backgroundColor=this.style.textDecorationColor" style="display: inline-block; vertical-align: text-bottom; width: 24px; height: 24px; box-sizing: border-box; border-radius: 50%; border: 0px solid; box-shadow: rgba(255, 255, 255, 0.2) 0px 1px 0px inset, rgba(0, 0, 0, 0.2) 0px 1px 2px; padding: 5px; background-color: rgb(190, 61, 22); text-decoration-color: rgb(190, 61, 22); outline-color: rgb(110, 88, 52); outline-width: 10px; color: rgb(246, 244, 244); cursor: pointer; transition: all 0.3s ease 0s;" class="$emarketer_button_dont_show_again" data-action_id="${action_id}"><div style="display: block; width: 100%; height: 100%; transition: all 0.3s ease 0s; border-radius: 50%; background-image: linear-gradient(-45deg, transparent 0%, transparent 46%, currentcolor 46%, currentcolor 56%, transparent 56%, transparent 100%), linear-gradient(45deg, transparent 0%, transparent 46%, currentcolor 46%, currentcolor 56%, transparent 56%, transparent 100%);"></div></div>'):input_type(dontshowagain):arg_name(Close button):arg_section(4, 2, 'Close Button', 'times-circle')}
	</div>

	<table data-style="width:100%; border-collapse:collapse">

		<tr>
			<td style="text-align:center; ${args->text_1_style:html:default('background-color: rgba(0, 0, 0, 0);
color: white;'):input_type(css):input_props('with_responsive=1'):arg_name(Text 1 style):arg_section(1, 0, 'Text 1', 'bars')}">
				<div data-style="${args->line_1_style:html:default('font-size: 20px;
color: rgba(38, 38, 63, 0.73);
padding-top: 40px;
padding-right: 20px;
padding-bottom: 15px;
padding-left: 20px;
font-weight: bold;'):input_type(css):input_props('with_responsive=1'):arg_name(Text 1 style):arg_section(1, 2, 'Text 1', 'bars')}">
					${args->line_1:default(TEXT TEXT TEXT TEXT  TEXT TEXT):arg_name(Text 1 line 1):arg_section(1, 1, 'Text 1', 'bars')}
				</div>
				<div data-style="${args->line_2_style:html:default('font-size: 14px;
color: rgb(90, 58, 58);
padding-top: 0px;
padding-right: 20px;
padding-bottom: 15px;
padding-left: 20px;
font-weight: lighter;
text-align: center;'):input_type(css):input_props('with_responsive=1'):arg_name(Text 1 style):arg_section(1, 4, 'Text 1', 'bars')}">
					${args->line_2:default(Text Text Text):arg_name(Text 1 line 2):arg_section(1, 3, 'Text 1', 'bars')}
				</div>
			</td>
		</tr>
		<tr>
			<td style="text-align:center; padding:1em">
				<a ${args->href:default('href=""'):input_type(a_attrs):arg_name(URL):arg_section(2, 1, 'Button', 'hand-o-up')}
					data-style="display:inline-block; ${args->button_text_style:html:default('font-size: 14px;
color: rgb(256, 256, 256);
text-decoration: none;
background-color: rgb(68, 126, 88);
padding-top: 8px;
padding-right: 15px;
padding-bottom: 8px;
padding-left: 15px;
border-radius: 2px;
font-weight: 600;
margin: 5px;
text-transform: uppercase;'):input_type(css):input_props('with_responsive=1'):arg_name(Button text style):arg_section(2, 2, 'Button', 'hand-o-up')}">  ${args->button_t:default(MORE DETAILS):arg_name(Text_button):arg_section(2, 0, 'Button', 'hand-o-up')}
				</a>

				${block->show_button_2:default(1):arg_name(Show second button):arg_section(3, 0, 'Second Button', 'hand-o-up')}
				<a ${args->href_2:default('href="javascript:" class="$emarketer_button_dont_show_again" data-action_id="${action_id}" data-n_sessions="0"'):input_type(a_attrs):arg_name(URL):arg_section(3, 2, 'Second Button', 'hand-o-up')}
					data-style="display:inline-block; ${args->button_text_style_2:html:default('color: rgba(42, 28, 28, 0.45);'):input_type(css):input_props('with_responsive=1'):arg_name(Button text style):arg_section(3, 3, 'Second Button', 'hand-o-up')}">
					${args->button_t_2:default(Dismissed):arg_name(Text_button):arg_section(3, 1, 'Second Button', 'hand-o-up')}
				</a>
			</td>
		</tr>
	</table>

	<link rel="stylesheet" type="text/css" href="https://fonts.googleapis.com/css?family=Playfair+Display+SC:400|Open+Sans:400,300|Oswald:400,700">
</div>
```


## Popup with image



```
<div class="$responsive" data-style="position:relative; display:inline-block; ${args->style:html:default('background-color: rgba(20, 10, 11, 0.8);
padding: 43px;
max-width: 600px;
border-radius: 5px;'):input_type(css):input_props('with_responsive=1'):arg_name(Box style):arg_section(0, 0, 'Box', 'th-large')}">
	${block->show_close_button:default(1):arg_name(Show close button):arg_section(5, 0, 'Close Button', 'times-circle')}
	<div data-style="position:absolute; cursor:pointer; ${args->close_button_style:html:default('top: -17px;
right: -10px;
z-index: 9999;'):input_type(css):input_props('with_responsive=1'):arg_name(Close_btn_Style):arg_section(5, 1, 'Close Button', 'times-circle')}">
		${args->close_button:default('<div onmouseenter="this.style.backgroundColor=this.style.outlineColor" onmouseleave="this.style.backgroundColor=this.style.textDecorationColor" style="display: inline-block; vertical-align: text-bottom; width: 29px; height: 29px; box-sizing: border-box; border-radius: 50%; border: 0px solid; box-shadow: rgba(255, 255, 255, 0.2) 0px 1px 0px inset, rgba(0, 0, 0, 0.2) 0px 1px 2px; padding: 6px; background-color: rgb(206, 54, 64); text-decoration-color: rgb(206, 54, 64); outline-color: rgb(206, 54, 64); outline-width: 10px; color: rgb(255, 255, 255); cursor: pointer; transition: all 0.3s ease 0s;" class="$emarketer_button_dont_show_again" data-action_id="${action_id}"><div style="display: block; width: 100%; height: 100%; transition: all 0.3s ease 0s; border-radius: 50%; background-image: linear-gradient(-45deg, transparent 0%, transparent 46%, currentcolor 46%, currentcolor 56%, transparent 56%, transparent 100%), linear-gradient(45deg, transparent 0%, transparent 46%, currentcolor 46%, currentcolor 56%, transparent 56%, transparent 100%);"></div></div>'):input_type(dontshowagain):arg_name(Close button):arg_section(5, 2, 'Close Button', 'times-circle')}
	</div>

	<table data-style="width:100%; border-collapse:collapse">
		<tr>
			<td style="text-align:center; padding:0">
				<img src="${args->image_src:html:default('https://cdn.e-marketer.io/upload/362/7d0a26d42b6f9a72.jpeg'):input_type(emarketer_media_url):arg_name(URL):arg_section(1, 0, 'Image', 'image')}" style="vertical-align:bottom; ${args->image_style:html:default('width: sel(550px, 60vw);
height: sel(33px, 40vw);
max-width: 400px;'):input_type(css):input_props('with_responsive=1'):arg_name(Text 1 style):arg_section(1, 1, 'Image', 'image')}">
			</td>
		</tr>
		<tr>
			<td style="text-align:center; ${args->text_1_style:html:default('background-color: rgba(0, 0, 0, 0);
color: white;'):input_type(css):input_props('with_responsive=1'):arg_name(Text 1 style):arg_section(2, 0, 'Text 1', 'bars')}">
				<div data-style="${args->line_1_style:html:default('font-size: 18px;
font-weight: 900;
padding: 10px;'):input_type(css):input_props('with_responsive=1'):arg_name(Text 1 style):arg_section(2, 2, 'Text 1', 'bars')}">
					${args->line_1:default(Text Text):arg_name(Text 1 line 1):arg_section(2, 1, 'Text 1', 'bars')}
				</div>
				<div data-style="${args->line_2_style:html:default('font-size:15px'):input_type(css):input_props('with_responsive=1'):arg_name(Text 1 style):arg_section(2, 4, 'Text 1', 'bars')}">
					${args->line_2:default(Text Text Text Text Text Text Text Text Text Text Text Text Text Text):arg_name(Text 1 line 2):arg_section(2, 3, 'Text 1', 'bars')}
				</div>
			</td>
		</tr>
		<tr>
			<td style="text-align:center; padding:1em">
				<a ${args->href:default('href="javascript:" class="$emarketer_button_dont_show_again" data-action_id="${action_id}" data-n_sessions="0"'):input_type(a_attrs):arg_name(URL):arg_section(3, 1, 'Button', 'hand-o-up')}
					data-style="display:inline-block; ${args->button_text_style:html:default('font-family: Open Sans;
font-size: 23px;
color: white;
text-decoration: none;
background-color: rgba(128, 128, 128, 0.9);
padding-top: 4px;
padding-right: 20px;
padding-bottom: 4px;
padding-left: 20px;
box-shadow: 0 0 2px rgb(222, 202, 202);'):input_type(css):input_props('with_responsive=1'):arg_name(Button text style):arg_section(3, 2, 'Button', 'hand-o-up')}">  ${args->button_t:default(Close):arg_name(Text_button):arg_section(3, 0, 'Button', 'hand-o-up')}
				</a>

				${block->show_button_2:default(1):arg_name(Show second button):arg_section(4, 0, 'Second Button', 'hand-o-up')}
				<a ${args->href_2:default('href=""'):input_type(a_attrs):arg_name(URL):arg_section(4, 2, 'Second Button', 'hand-o-up')}
					data-style="display:inline-block; ${args->button_text_style_2:html:default('margin: 15px;
font-family: Open Sans;
font-size: 23px;
color: white;
text-decoration: none;
background-color: #4E8150;
padding-top: 4px;
padding-right: 21px;
padding-bottom: 4px;
padding-left: 20px;
box-shadow: 0 0 2px rgb(149, 189, 127);'):input_type(css):input_props('with_responsive=1'):arg_name(Button text style):arg_section(4, 3, 'Second Button', 'hand-o-up')}">
					${args->button_t_2:default(View):arg_name(Text_button):arg_section(4, 1, 'Second Button', 'hand-o-up')}
				</a>
			</td>
		</tr>
	</table>

	<link rel="stylesheet" type="text/css" href="https://fonts.googleapis.com/css?family=Playfair+Display+SC:400|Open+Sans:400,300|Oswald:400,700">
</div>
```


## popup



```
<div class="$responsive" data-style="position:relative; ${args->style:html:default('width: 300px;
padding-top: 20px;
padding-right: 30px;
padding-bottom: 20px;
padding-left: 28px;
text-align: center;
color: #fff;
background-color: #002d73;
box-sizing: border-box;
box-shadow: 6px 1px 1px 1px rgba(65, 90, 134, 0.02);
border-radius: 5px;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(0, 0, 'Box', 'th-large')}">
    <link href="https://fonts.googleapis.com/css?family=Khand" rel="stylesheet">
    <span data-style="${args->title_text_style:html:default('font-weight: normal;
font-size: 12px;
text-transform: uppercase;
font-family: Arial;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(1, 1, 'Title', 'bookmark')}">${args->title_text:default(Congrats you have 15% off waiting for you at cart):arg_name(Text):arg_section(1, 0, 'Title', 'bookmark')}</span><a href="${args->button_link:html:default('https://www.refrigiwear.com/cart'):input_type(url):arg_name(Link):arg_section(2, 2, 'Button', 'hand-o-up')}" onclick="${args->button_link_js:html:input_type(source_javascript):arg_name(Javascript):arg_section(2, 3, 'Button', 'hand-o-up')}" data-style="${args->button_style:html:default('display: inline-block;
color: #fff;
font-family: Khand,sans-serif;
font-weight: normal;
font-size: 15px;
text-transform: uppercase;
text-decoration: none;
margin: 11px;
background-color: rgb(133, 185, 121);
padding: 5px;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(2, 1, 'Button', 'hand-o-up')}">${args->link_text:default(Prod3x15):arg_name(Text):arg_section(2, 0, 'Button', 'hand-o-up')}</a>
    ${block->show_close_button:default(1):arg_name(Show close button):arg_section(3, 0, 'Close button', 'close')}
    <div data-style="${args->close_button_style:html:default('position: absolute;
top: -10px;
right: -5px;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(3, 1, 'Close button', 'close')}">
        ${args->close_button:default('href="javascript:" class="$emarketer_button_dont_show_again" data-action_id="${action_id}" data-n_sessions="0"'):input_type(dontshowagain):arg_name(Close button):arg_section(3, 2, 'Close button', 'close')}
    </div>
</div>
```


## 2 Buttons



```
<div class="$responsive" data-style="position:relative; overflow:hidden; ${args->box_style:html:default('max-width: 640px;
background-color: #002856;
width: 640px;
color: #002856;
border-radius: 5px;'):input_type(css):input_props('with_responsive=1'):arg_name(Box style):arg_section(0, 0, 'Box', 'th-large')}" >
	<table style="border-collapse:collapse; border:none">
		<tr style="border:none">
			<td style="border:none; background-repeat:no-repeat; background-position:center; ${args->image_style:html:default('background-image: url(''https://cdn.e-marketer.io/upload/362/9021b00a37b389c0.jpeg'');
background-size: 100% 100%;'):input_type(css):arg_name(Picture URL):arg_section(1, 0, 'Picture', 'image')}">
				<div data-style="width:${args->image_width:html:default('sel(300px, 40vw)'):input_type(css_length):input_props('with_responsive=1'):arg_name('Image width', 'Picture URL'):arg_section(1, 1, 'Picture', 'image')}; height:${args->image_height:html:default('sel(300px, 40vw)'):input_type(css_length):input_props('with_responsive=1'):arg_name('Image height', 'Picture URL'):arg_section(1, 2, 'Picture', 'image')}"></div>
			</td>
			<td style="border:none; padding:0 1em">
				<div data-style="max-height:${args->image_height:html}">
					<div data-style="outline:0; ${args->title_style:html:default('color: #fff;
font-size: sel(30px, 4vw);
font-weight: 300;
line-height: 32px;
text-align: center;
margin-top: 30px;
margin-right: 0px;
margin-bottom: 0px;
margin-left: 0px;'):input_type(css):input_props('with_responsive=1'):arg_name(Title style):arg_section(2, 1, 'Content', 'bars')}">
						${args->title:default('<div style="text-align: center;">Text Text<br />
Text Text</div>
'):arg_name(Title):arg_section(2, 0, 'Content', 'bars')}
					</div>
					<div data-style="outline:0; ${args->text_style:html:default('text-align: center;
color: #ffffff;
font-size: sel(18px, 4vw);
padding: 5px;
line-height: 24px;
font-weight: 200;'):input_type(css):input_props('with_responsive=1'):arg_name(Title style):arg_section(2, 3, 'Content', 'bars')}">
						${args->text:default('<p style="text-align: center;">Text TextText TextText TextText TextText TextText TextText Text</p>
'):arg_name(Text):arg_section(2, 2, 'Content', 'bars')}
					</div>
					<div style="text-align:center; ${args->buttons_style:html:default('margin-top: 1em;
margin-right: 0;
margin-bottom: 2em;
margin-left: 0;'):input_type(css):input_props('with_responsive=1'):arg_name(Buttons margin):arg_section(3, 4, 'First Button', 'hand-o-up')}">
						${block->show_button:default(1):arg_name(Show button):arg_section(3, 0, 'First Button', 'hand-o-up')}
						<a ${args->href:default('href="javascript:" class="$emarketer_button_dont_show_again" data-action_id="${action_id}" data-n_sessions="0"'):input_type(a_attrs):arg_name(URL):arg_section(3, 2, 'First Button', 'hand-o-up')} data-style="${args->button_text_style:html:default('font-family: Arial;
font-size: sel(15px, 4vw);
color: white;
text-decoration: none;
background-color: #f7941e;
padding-top: 15px;
padding-right: 20px;
padding-bottom: 15px;
padding-left: 20px;
border-radius: 2px;
font-weight: bolder;
margin-top: 1px;
margin-right: 1px;
margin-bottom: 1px;
margin-left: 1px;
width: 100%;'):input_type(css):input_props('with_responsive=1'):arg_name(Button text style):arg_section(3, 3, 'First Button', 'hand-o-up')}">  ${args->button_t:default(GOT IT!):arg_name(Text_button):arg_section(3, 1, 'First Button', 'hand-o-up')}
						</a>

						${block->show_button_2:default(1):arg_name(Show second button):arg_section(4, 0, 'Second Button', 'hand-o-up')}
						<a ${args->href_3:input_type(a_attrs):arg_name(URL):arg_section(4, 2, 'Second Button', 'hand-o-up')} data-style="display:inline-block; ${args->button_text_style_2:html:input_type(css):input_props('with_responsive=1'):arg_name(Button text style):arg_section(4, 3, 'Second Button', 'hand-o-up')}">
							${args->button_t_2:arg_name(Text_button):arg_section(4, 1, 'Second Button', 'hand-o-up')}
						</a>
					</div>
				</div>
			</td>
		</tr>
	</table>
	${block->show_close_button:default(1):arg_name(Show close button):arg_section(5, 0, 'Close Button', 'times-circle')}
	<div data-style="position:absolute; cursor:pointer; ${args->close_button_style:html:default('top: 8px;
right: 8px;
z-index: 9999;'):input_type(css):input_props('with_responsive=1'):arg_name(Close Button Style):arg_section(5, 1, 'Close Button', 'times-circle')}">
		${args->close_button:default('<div onmouseenter="this.style.backgroundColor=this.style.outlineColor" onmouseleave="this.style.backgroundColor=this.style.textDecorationColor" style="display: inline-block; vertical-align: text-bottom; width: 24px; height: 24px; box-sizing: border-box; border-top-left-radius: 50%; border-top-right-radius: 50%; border-bottom-right-radius: 50%; border-bottom-left-radius: 50%; border: 2px solid; -webkit-box-shadow: rgba(255, 255, 255, 0.2) 0px 1px 0px inset, rgba(0, 0, 0, 0.2) 0px 1px 2px; padding: 3px; background-color: rgb(207, 120, 58); text-decoration-color: rgb(207, 120, 58); outline-color: rgb(206, 54, 64); outline-width: 10px; color: rgb(10, 4, 4); cursor: pointer; transition: all 0.3s ease;" class="$emarketer_button_dont_show_again" data-action_id="${action_id}"><div style="display: block; width: 100%; height: 100%; transition: all 0.3s ease 0s; border-top-left-radius: 50%; border-top-right-radius: 50%; border-bottom-right-radius: 50%; border-bottom-left-radius: 50%; background-image: linear-gradient(-45deg, transparent 0%, transparent 46%, currentcolor 46%, currentcolor 56%, transparent 56%, transparent 100%), linear-gradient(45deg, transparent 0%, transparent 46%, currentcolor 46%, currentcolor 56%, transparent 56%, transparent 100%);"></div></div>'):input_type(dontshowagain):arg_name(Close button):arg_section(5, 2, 'Close Button', 'times-circle')}
	</div>
</div>
```


## Timer popup



```
<div class="$responsive" data-style="position:relative; background-color:#0B0B0B; text-align:center; box-sizing:border-box; ${args->style:html:default('width: sel(430px, auto);
padding-top: 30px;
padding-right: 0px;
padding-bottom: 60px;
padding-left: 0px;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(0, 0, 'Box', 'th-large')}">
    <style>@font-face { font-family:Segment7Standard; src:url('https://static.emarketer.com/upload/4241/12050534867b94b3.otf'); }</style>
    <link href="https://fonts.googleapis.com/css?family=Oswald:400" rel="stylesheet">
    ${block->show_close_button:default(0):arg_name(Show close button):arg_section(6, 0, 'Close button', 'close')}
    <div style="position:absolute; top:16px; right:16px">
        ${args->close_button:input_type(dontshowagain):arg_name(Close button):arg_section(6, 1, 'Close button', 'close')}
    </div>
    <div data-style="vertical-align:middle; ${args->logo_style:html:default('text-align:center; padding:0 0 40px;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(1, 1, 'Logo', 'image')}">
        <img src="${args->logo_url:html:default('https://cdn.e-marketer.io/upload/362/185f3236b1b4ab52.png'):input_type(emarketer_media_url):arg_name(URL):arg_section(1, 0, 'Logo', 'image')}">
    </div>
    <div data-style="vertical-align:middle; ${args->content_style:html:default('color:white; text-align:center; font-family:Oswald,san-serif; font-weight:normal; font-size:30px; line-height:38px; padding:10px 40px; text-transform:uppercase'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(2, 1, 'Content', 'bars')}">
        ${args->content_text:default(100% Sign-in bonus to $300):arg_name(Text):arg_section(2, 0, 'Content', 'bars')}
    </div>
    <div style="position:relative; display:inline-block; margin-top:8px; text-align:center; background-color:#010101; width:400px; height:170px">
        <div style="position:absolute; left:0; right:0; white-space:nowrap"><div style="display:inline-block; vertical-align:top"><div style="width:200px; height:170px; text-align:center;"><div style="display:inline-block; height:100%; vertical-align:middle"></div><div style="display:inline-block; vertical-align:middle; padding:0 4px"><div style="margin-top:24px; line-height:1; color:#213B2D; font-size:154px; font-family:Segment7Standard; transform:scaleX(0.85) skewX(-4deg);">88</div></div></div></div><div style="position:absolute; display:inline-block; left:0; right:0"><div style="line-height:1; color:#39E34C; font-size: 154px; font-family: serif; transform: skewX(-5deg); margin-top:-8px">:</div></div><div style="display:inline-block; vertical-align:top"><div style="width:200px; height:170px; text-align:center;"><div style="display:inline-block; height:100%; vertical-align:middle"></div><div style="display:inline-block; vertical-align:middle; padding:0 4px;"><div style="margin-top:24px; line-height:1; color:#213B2D; font-size: 154px; font-family:Segment7Standard; transform:scaleX(0.85) skewX(-4deg);">88</div></div></div></div></div>
        <div class="$timer_base" data-value="${args->timer_value:html:default(12780):input_type(time):input_props('is_span=1'):arg_name(Start time):arg_section(3, 0, 'Timer', 'hourglass-start')}" values_count="2" block_style="width:200px; height:170px; background-color:0; text-align:center" number_style="margin-top:24px; line-height:1; color:#39E34C; font-size:154px; font-family:Segment7Standard; transform: scaleX(.85) skewX(-4deg)" no_captions="1" autostart="1"></div>
    </div>
    <div style="margin-top:45px; white-space:nowrap">
        <a href="${args->signin_button_href:html:default('#'):input_type(url):arg_name(URL):arg_section(4, 1, 'Sign-in button', 'check')}" onclick="${args->signin_button_js:html:input_type(source_javascript):arg_name(Javascript):arg_section(4, 3, 'Sign-in button', 'check')}" target="${args->signin_button_target:html:default(_self):input_type(a_target):arg_name(Open link in):arg_section(4, 2, 'Sign-in button', 'check')}" data-style="display:inline-block; vertical-align:top; ${args->signin_button_style:html:default('font-family:Oswald,san-serif; font-weight:normal; font-size:24px; width:100px; height:51px; line-height:51px; text-align:center; text-decoration:none; text-transform:uppercase; border-radius:3px; color:white; padding:0'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(4, 4, 'Sign-in button', 'check')}">${args->signin_button_label:default(Sign-in):arg_name(Label):arg_section(4, 0, 'Sign-in button', 'check')}</a>
        <a href="${args->join_button_href:html:default('#'):input_type(url):arg_name(URL):arg_section(5, 1, 'Join button', 'check')}" onclick="${args->join_button_js:html:input_type(source_javascript):arg_name(Javascript):arg_section(5, 3, 'Join button', 'check')}" target="${args->join_button_target:html:default(_self):input_type(a_target):arg_name(Open link in):arg_section(5, 2, 'Join button', 'check')}" data-style="display:inline-block; vertical-align:top; ${args->join_button_style:html:default('font-family: Oswald,san-serif;
font-weight: normal;
font-size: 24px;
width: 120px;
height: 51px;
line-height: 51px;
text-align: center;
text-decoration: none;
text-transform: uppercase;
border-radius: 3px;
background-color: #369425;
color: white;
padding: 0;
border-bottom-width: 2px;
border-top-color: rgba(0, 0, 0, 1);
border-right-color: rgba(0, 0, 0, 1);
border-bottom-color: #25661A;
border-left-color: rgba(0, 0, 0, 1);
border-top-style: none;
border-right-style: none;
border-bottom-style: solid;
border-left-style: none;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(5, 4, 'Join button', 'check')}">${args->join_button_label:default(Join now):arg_name(Label):arg_section(5, 0, 'Join button', 'check')}</a>
    </div>
</div>

```


## Popup with image on top



```
<div class="$responsive" data-style="position:relative; display:inline-block; ${args->style:html:default('background-color: white;
padding: 0px;
max-width: 600px;
border-radius: 5px;
border: solid thin rgb(237, 223, 223);'):input_type(css):input_props('with_responsive=1'):arg_name(Box style):arg_section(0, 0, 'Box', 'th-large')}">
	${block->show_close_button:default(1):arg_name(Show close button):arg_section(5, 0, 'Close Button', 'times-circle')}
	<div data-style="position:absolute; cursor:pointer; ${args->close_button_style:html:default('top: -12px;
right: -10px;
z-index: 9999;'):input_type(css):input_props('with_responsive=1'):arg_name(Close_btn_Style):arg_section(5, 1, 'Close Button', 'times-circle')}">
		${args->close_button:default('<div onmouseenter="this.style.backgroundColor=this.style.outlineColor" onmouseleave="this.style.backgroundColor=this.style.textDecorationColor" style="display: inline-block; vertical-align: text-bottom; width: 22px; height: 22px; box-sizing: border-box; border-top-left-radius: 50%; border-top-right-radius: 50%; border-bottom-right-radius: 50%; border-bottom-left-radius: 50%; border: 0px solid; -webkit-box-shadow: rgba(255, 255, 255, 0.2) 0px 1px 0px inset, rgba(0, 0, 0, 0.2) 0px 1px 2px; padding: 6px; background-color: black; text-decoration-color: black; outline-color: rgb(206, 54, 64); outline-width: 10px; color: rgb(255, 255, 255); cursor: pointer; transition: all 0.3s ease;" class="$emarketer_button_dont_show_again" data-action_id="${action_id}"><div style="display: block; width: 100%; height: 100%; transition: all 0.3s ease 0s; border-top-left-radius: 50%; border-top-right-radius: 50%; border-bottom-right-radius: 50%; border-bottom-left-radius: 50%; background-image: linear-gradient(-45deg, transparent 0%, transparent 46%, currentcolor 46%, currentcolor 56%, transparent 56%, transparent 100%), linear-gradient(45deg, transparent 0%, transparent 46%, currentcolor 46%, currentcolor 56%, transparent 56%, transparent 100%);"></div></div>'):input_type(dontshowagain):arg_name(Close button):arg_section(5, 2, 'Close Button', 'times-circle')}
	</div>

	<table data-style="width:100%; border-collapse:collapse">
		<tr>
			<td style="text-align:center; padding:0">
				<img src="${args->image_src:html:default('https://cdn.e-marketer.io/upload/362/18d08e19c0855cd3.jpeg'):input_type(emarketer_media_url):arg_name(URL):arg_section(1, 0, 'Image', 'image')}" style="vertical-align:bottom; ${args->image_style:html:default('width: sel(auto, 60vw);
height: sel(33px, 40vw);
max-width: 400px;'):input_type(css):input_props('with_responsive=1'):arg_name(Text 1 style):arg_section(1, 1, 'Image', 'image')}">
			</td>
		</tr>
		<tr>
			<td style="text-align:center; ${args->text_1_style:html:default('background-color: rgba(0, 0, 0, 0);
color: white;'):input_type(css):input_props('with_responsive=1'):arg_name(Text 1 style):arg_section(2, 0, 'Text 1', 'bars')}">
				<div data-style="${args->line_1_style:html:default('color: black;
text-align: center;
font-family: Arial;
font-weight: normal;
font-size: 20px;
line-height: 38px;
padding: 5px;
text-transform: uppercase;
letter-spacing: 2px;'):input_type(css):input_props('with_responsive=1'):arg_name(Text 1 style):arg_section(2, 2, 'Text 1', 'bars')}">
					${args->line_1:default(Your title goes here):arg_name(Text 1 line 1):arg_section(2, 1, 'Text 1', 'bars')}
				</div>
				<div data-style="${args->line_2_style:html:default('color: rgb(89, 58, 58);
text-align: center;
font-family: Arial;
font-weight: normal;
font-size: 13px;
padding-top: 5px;
padding-right: 0;
padding-bottom: 10px;
padding-left: 0;
letter-spacing: 1px;'):input_type(css):input_props('with_responsive=1'):arg_name(Text 1 style):arg_section(2, 4, 'Text 1', 'bars')}">
					${args->line_2:default(Description):arg_name(Text 1 line 2):arg_section(2, 3, 'Text 1', 'bars')}
				</div>
			</td>
		</tr>
		<tr>
			<td style="text-align:center; padding:1em">
				<a ${args->href:default('href="javascript:" class="$emarketer_button_dont_show_again" data-action_id="${action_id}" data-n_sessions="0"'):input_type(a_attrs):arg_name(URL):arg_section(3, 1, 'Button', 'hand-o-up')}
					data-style="display:inline-block; ${args->button_text_style:html:default('font-family: Arial;
font-weight: normal;
font-size: 13px;
width: 40%;
height: 40px;
line-height: 40px;
text-align: center;
text-transform: uppercase;
border: 1px solid #f7941d;
border-radius: 3px;
background-color: #f7941d;
color: #002856;
padding: 0;'):input_type(css):input_props('with_responsive=1'):arg_name(Button text style):arg_section(3, 2, 'Button', 'hand-o-up')}">  ${args->button_t:default(Close):arg_name(Text_button):arg_section(3, 0, 'Button', 'hand-o-up')}
				</a>

				${block->show_button_2:default(0):arg_name(Show second button):arg_section(4, 0, 'Second Button', 'hand-o-up')}
				<a ${args->href_2:input_type(a_attrs):arg_name(URL):arg_section(4, 2, 'Second Button', 'hand-o-up')}
					data-style="display:inline-block; ${args->button_text_style_2:html:input_type(css):input_props('with_responsive=1'):arg_name(Button text style):arg_section(4, 3, 'Second Button', 'hand-o-up')}">
					${args->button_t_2:arg_name(Text_button):arg_section(4, 1, 'Second Button', 'hand-o-up')}
				</a>
			</td>
		</tr>
	</table>

	<link rel="stylesheet" type="text/css" href="https://fonts.googleapis.com/css?family=Playfair+Display+SC:400|Open+Sans:400,300|Oswald:400,700">
</div>
```


## Tall-banner



```
<div class="$responsive" data-style="box-sizing: border-box;
margin: 0 auto;
position: relative;
overflow: hidden;
${args->style:html:default('
width: 160px;
height: 600px;
border: 1px solid #0c0c0e'):input_type(css):input_props('with_responsive=1'):arg_name(Box style):arg_section(0, 0, 'Box', 'th-large')}
">
<div data-style="position: absolute;
	width:100%;
	height: 100%;
	background-image: url(${args->image_bgc:html:default():input_type(emarketer_media_url):arg_name(Background image):arg_section(0, 1, 'Box', 'th-large')});
	background-repeat: no-repeat;
	background-position: 0 50%;
	${args->img_bg_style:html:default('background-color:#33313E'):input_type(css):input_props('with_responsive=1'):arg_name(Background style):arg_section(0, 2, 'Box', 'th-large')}"></div>

		<div data-style="position: absolute; width:100%;
		${args->content_title1_position:html:default('
		text-align: center;
		top: 80px'):input_type(css):input_props('with_responsive=1'):arg_name(Title position):arg_section(1, 0, 'Title', 'bookmark')}">
		<span data-style="
			${args->action_text_style:html:default('
			font-family: Viga;
			color: #fff;
			font-size: 25px;
			line-height: 0.9;
			letter-spacing: 2px'):input_type(css):input_props('with_responsive=1'):arg_name(Title line 1 font):arg_section(1, 2, 'Title', 'bookmark')}">
			${args->title:default(ANNUAL):arg_name(Title line 1):arg_section(1, 1, 'Title', 'bookmark')}
			<span data-style="
				${args->action_text2_style:html:default('
				color: #fff;
				font-size: 22px;
				letter-spacing: 1px'):input_type(css):input_props('with_responsive=1'):arg_name(Title line 2 font):arg_section(1, 4, 'Title', 'bookmark')}
				">${args->title2:default(BUSINESS):arg_name(Title line 2):arg_section(1, 3, 'Title', 'bookmark')}</span>  <span data-style="
			${args->action_text3_style:html:default('
			color: #fff;
			font-size: 18px;
			letter-spacing: 0'):input_type(css):input_props('with_responsive=1'):arg_name(Title line 3 font):arg_section(1, 6, 'Title', 'bookmark')}
			">${args->title3:default(CONFERENCE):arg_name(Title line 3):arg_section(1, 5, 'Title', 'bookmark')}</span></span>
		</div>
		<div data-style="position: absolute;
			width: 100%;
			${args->content_style:html:default('
			font-family: ''Open Sans'';
			color: #fff;
			text-align: center;
			top: 250px;
			font-size: 22px;
			line-height: 0.9;
			letter-spacing: 0'):input_type(css):input_props('with_responsive=1'):arg_name(Line 4 font):arg_section(2, 0, 'Text', 'file-text')}
			">${args->title4:default('for<br />
innovative<br />
technologies'):arg_name(Line 4):arg_section(2, 1, 'Text', 'file-text')}
		</div>

<div data-style="position: absolute;
width: 100%;
${args->button_style:html:default('text-align: center;
bottom: 150px;'):input_type(css):input_props('with_responsive=1'):arg_name(Button position):arg_section(4, 3, 'Button', 'hand-o-up')}">
<a href="${args->href:html:default('#'):arg_name(URL):arg_section(4, 1, 'Button', 'hand-o-up')}" target="${args->target:html:default(_self):input_type(a_target):arg_name(Open link in):arg_section(4, 2, 'Button', 'hand-o-up')}"
	data-style="letter-spacing: 0;
	${args->button_text_style:html:default('
	font-family: Viga;
	color: #fff;
	font-size: 20px;
	line-height: 1;
	letter-spacing: 0;
	padding: 10px 20px;
	text-decoration: none;
	background-color: #fc5729'):input_type(css):input_props('with_responsive=1'):arg_name(Button style):arg_section(4, 4, 'Button', 'hand-o-up')}">
	${args->title_button:default(ATTEND):arg_name(Button text):arg_section(4, 0, 'Button', 'hand-o-up')}
</a>
</div>
<div data-style="position: absolute;
width: 100%;
${args->pace_position:html:default('
text-align: center;
bottom: 35px'):input_type(css):input_props('with_responsive=1'):arg_name(Position_Place_1):arg_section(3, 0, 'Place', 'file-text')}
">
<span data-style="
	${args->place_style:html:default('font-family: ''Open Sans'';
	font-weight: 200;
	color: #fff;
	font-size: 12px;
	line-height: 1;
	letter-spacing: 0'):input_type(css):input_props('with_responsive=1'):arg_name(Style_Place_1):arg_section(3, 1, 'Place', 'file-text')}
	">${args->title_place:default('July 25-26, Paris'):arg_name(Place_text):arg_section(3, 2, 'Place', 'file-text')}</span>
</div>
${block->show_close_button:default(1):arg_name(Show close button):arg_section(5, 0, 'Close Button', 'times-circle')}
<div data-style="position:absolute; cursor:pointer; ${args->close_button_style:html:default('top:5px; right:5px;z-index:9999'):input_type(css):input_props('with_responsive=1'):arg_name(Close_btn_Style):arg_section(5, 1, 'Close Button', 'times-circle')}">
	${args->close_button:default('<div onmouseenter="this.style.backgroundColor=this.style.outlineColor" onmouseleave="this.style.backgroundColor=this.style.textDecorationColor" style="display: inline-block; vertical-align: text-bottom; width: 24px; height: 24px; box-sizing: border-box; border-top-left-radius: 50%; border-top-right-radius: 50%; border-bottom-right-radius: 50%; border-bottom-left-radius: 50%; border: 0px solid; -webkit-box-shadow: rgba(255, 255, 255, 0.2) 0px 1px 0px inset, rgba(0, 0, 0, 0.2) 0px 1px 2px; padding: 2px; background-color: rgba(0, 0, 0, 0); text-decoration-color: rgba(0, 0, 0, 0); outline-color: rgb(206, 54, 64); outline-width: 6px; color: rgb(244, 242, 242); cursor: pointer; transition: all 0.3s ease;" class="$emarketer_button_dont_show_again" data-action_id="${action_id}"><div style="display: block; width: 100%; height: 100%; transition: all 0.3s ease 0s; border-top-left-radius: 50%; border-top-right-radius: 50%; border-bottom-right-radius: 50%; border-bottom-left-radius: 50%; background-image: linear-gradient(-45deg, transparent 0%, transparent 48%, currentcolor 48%, currentcolor 54%, transparent 54%, transparent 100%), linear-gradient(45deg, transparent 0%, transparent 48%, currentcolor 48%, currentcolor 54%, transparent 54%, transparent 100%);"></div></div>'):input_type(dontshowagain):arg_name(Close button):arg_section(5, 2, 'Close Button', 'times-circle')}
</div>
<link rel="stylesheet" type="text/css" href="https://fonts.googleapis.com/css?family=Viga:400|Open+Sans:400,700">
</div>
```


## Simple banner/popup with link



```
<div class="$responsive">
	<a href="${args->href:html:default('#'):arg_name(Link URL):arg_section(1, 0, 'Link', 'link')}" target="${args->target:html:default(_self):input_type(a_target):arg_name(Open link in):arg_section(1, 1, 'Link', 'link')}" style="display:inline-block; position:relative; text-decoration:none">
		<img src="${args->image_src:html:default('https://cdn.e-marketer.io/upload/362/18d08e19c0855cd3.jpeg'):input_type(emarketer_media_url):arg_name(Image URL):arg_section(0, 0, 'Image', 'image')}" style="vertical-align:middle; ${args->image_style:html:default('max-width: sel(600px, 80vw);
width: 400px;'):input_type(css):input_props('with_responsive=1'):arg_name(Image style):arg_section(0, 1, 'Image', 'image')}">
		${block->show_text:default(0):arg_name(Show text):arg_section(2, 0, 'Text', 'bars')}
		<div data-style="position:absolute; ${args->text_style:html:input_type(css):input_props('with_responsive=1'):arg_name(Text style):arg_section(2, 1, 'Text', 'bars')}">
			${args->text:arg_name(Text):arg_section(2, 2, 'Text', 'bars')}
		</div>
		<span>
			${block->show_close_button:default(1):arg_name(Show close button):arg_section(3, 0, 'Close Button', 'times-circle')}
			<div data-style="position:absolute; cursor:pointer; ${args->close_button_style:html:default('top:5px; right:5px;z-index:9999'):input_type(css):input_props('with_responsive=1'):arg_name(Close button position):arg_section(3, 1, 'Close Button', 'times-circle')}">
				${args->close_button:default('<div onmouseenter="this.style.backgroundColor=this.style.outlineColor" onmouseleave="this.style.backgroundColor=this.style.textDecorationColor" style="display: inline-block; vertical-align: text-bottom; width: 24px; height: 24px; box-sizing: border-box; border-top-left-radius: 50%; border-top-right-radius: 50%; border-bottom-right-radius: 50%; border-bottom-left-radius: 50%; border: 0px solid; -webkit-box-shadow: none; padding: 3px; background-color: rgba(0, 0, 0, 0); text-decoration-color: rgba(0, 0, 0, 0); outline-color: rgb(206, 54, 64); outline-width: 10px; color: rgb(10, 4, 4); cursor: pointer; transition: all 0.3s ease;" class="$emarketer_button_dont_show_again" data-action_id="${action_id}"><div style="display: block; width: 100%; height: 100%; transition: all 0.3s ease 0s; border-top-left-radius: 50%; border-top-right-radius: 50%; border-bottom-right-radius: 50%; border-bottom-left-radius: 50%; background-image: linear-gradient(-45deg, transparent 0%, transparent 46%, currentcolor 46%, currentcolor 56%, transparent 56%, transparent 100%), linear-gradient(45deg, transparent 0%, transparent 46%, currentcolor 46%, currentcolor 56%, transparent 56%, transparent 100%);"></div></div>'):input_type(dontshowagain):arg_name(Close button):arg_section(3, 2, 'Close Button', 'times-circle')}
			</div>
		</span>
	</a>
</div>
```


## Two button popup/banner



```
<div class="$responsive" data-style="position:relative; display:inline-block; ${args->style:html:default('background-color: white;
padding: 43px;
max-width: 600px;
border-radius: 5px;'):input_type(css):input_props('with_responsive=1'):arg_name(Box style):arg_section(0, 0, 'Box', 'th-large')}">
	${block->show_close_button:default(1):arg_name(Show close button):arg_section(5, 0, 'Close Button', 'times-circle')}
	<div data-style="position:absolute; cursor:pointer; ${args->close_button_style:html:default('top: -12px;
right: -10px;
z-index: 9999;'):input_type(css):input_props('with_responsive=1'):arg_name(Close_btn_Style):arg_section(5, 1, 'Close Button', 'times-circle')}">
		${args->close_button:default('<div onmouseenter="this.style.backgroundColor=this.style.outlineColor" onmouseleave="this.style.backgroundColor=this.style.textDecorationColor" style="display: inline-block; vertical-align: text-bottom; width: 22px; height: 22px; box-sizing: border-box; border-top-left-radius: 50%; border-top-right-radius: 50%; border-bottom-right-radius: 50%; border-bottom-left-radius: 50%; border: 0px solid; -webkit-box-shadow: rgba(255, 255, 255, 0.2) 0px 1px 0px inset, rgba(0, 0, 0, 0.2) 0px 1px 2px; padding: 6px; background-color: black; text-decoration-color: black; outline-color: rgb(206, 54, 64); outline-width: 10px; color: rgb(255, 255, 255); cursor: pointer; transition: all 0.3s ease;" class="$emarketer_button_dont_show_again" data-action_id="${action_id}"><div style="display: block; width: 100%; height: 100%; transition: all 0.3s ease 0s; border-top-left-radius: 50%; border-top-right-radius: 50%; border-bottom-right-radius: 50%; border-bottom-left-radius: 50%; background-image: linear-gradient(-45deg, transparent 0%, transparent 46%, currentcolor 46%, currentcolor 56%, transparent 56%, transparent 100%), linear-gradient(45deg, transparent 0%, transparent 46%, currentcolor 46%, currentcolor 56%, transparent 56%, transparent 100%);"></div></div>'):input_type(dontshowagain):arg_name(Close button):arg_section(5, 2, 'Close Button', 'times-circle')}
	</div>

	<table data-style="width:100%; border-collapse:collapse">
		<tr>
			<td style="text-align:center; padding:0">
				<img src="${args->image_src:html:default('https://static.emarketer.com/upload/362/2ced8f83fce5a056.png'):input_type(emarketer_media_url):arg_name(URL):arg_section(1, 0, 'Image', 'image')}" style="vertical-align:bottom; ${args->image_style:html:default('width: sel(550px, 60vw);
height: sel(33px, 40vw);
max-width: 400px;'):input_type(css):input_props('with_responsive=1'):arg_name(Text 1 style):arg_section(1, 1, 'Image', 'image')}">
			</td>
		</tr>
		<tr>
			<td style="text-align:center; ${args->text_1_style:html:default('background-color: rgba(0, 0, 0, 0);
color: white;'):input_type(css):input_props('with_responsive=1'):arg_name(Text 1 style):arg_section(2, 0, 'Text 1', 'bars')}">
				<div data-style="${args->line_1_style:html:default('color:black; text-align:center; font-family:Fjalla One,san-serif; font-weight:normal; font-size:28px; line-height:38px; padding:10px 40px; text-transform:uppercase; letter-spacing:2px'):input_type(css):input_props('with_responsive=1'):arg_name(Text 1 style):arg_section(2, 2, 'Text 1', 'bars')}">
					${args->line_1:default(Text Text):arg_name(Text 1 line 1):arg_section(2, 1, 'Text 1', 'bars')}
				</div>
				<div data-style="${args->line_2_style:html:default('color:black; text-align:center; font-family:Helvetica,san-serif; font-weight:normal; font-size:15px; padding:10px 0; letter-spacing:1px'):input_type(css):input_props('with_responsive=1'):arg_name(Text 1 style):arg_section(2, 4, 'Text 1', 'bars')}">
					${args->line_2:default('Text Text Text Text Text Text<br />
Text Text Text Text Text Text Text Text'):arg_name(Text 1 line 2):arg_section(2, 3, 'Text 1', 'bars')}
				</div>
			</td>
		</tr>
		<tr>
			<td style="text-align:center; padding:1em">
				<a ${args->href:default('href="javascript:" class="$emarketer_button_dont_show_again" data-action_id="${action_id}" data-n_sessions="0"'):input_type(a_attrs):arg_name(URL):arg_section(3, 1, 'Button', 'hand-o-up')}
					data-style="display:inline-block; ${args->button_text_style:html:default('font-family: Fjalla One,san-serif;
font-weight: normal;
font-size: 13px;
width: 40%;
height: 40px;
line-height: 40px;
text-align: center;
text-transform: uppercase;
border: 1px solid black;
border-radius: 3px;
background-color: white;
color: black;
padding: 0;'):input_type(css):input_props('with_responsive=1'):arg_name(Button text style):arg_section(3, 2, 'Button', 'hand-o-up')}">  ${args->button_t:default(Close):arg_name(Text_button):arg_section(3, 0, 'Button', 'hand-o-up')}
				</a>

				${block->show_button_2:default(1):arg_name(Show second button):arg_section(4, 0, 'Second Button', 'hand-o-up')}
				<a ${args->href_2:default('href=""'):input_type(a_attrs):arg_name(URL):arg_section(4, 2, 'Second Button', 'hand-o-up')}
					data-style="display:inline-block; ${args->button_text_style_2:html:default('font-family: Fjalla One,san-serif;
font-weight: normal;
font-size: 13px;
width: 40%;
height: 40px;
line-height: 40px;
text-align: center;
text-transform: uppercase;
border: 0;
border-radius: 3px;
background-color: rgb(74, 135, 86);
color: rgb(248, 249, 247);
padding: 0;'):input_type(css):input_props('with_responsive=1'):arg_name(Button text style):arg_section(4, 3, 'Second Button', 'hand-o-up')}">
					${args->button_t_2:default(View):arg_name(Text_button):arg_section(4, 1, 'Second Button', 'hand-o-up')}
				</a>
			</td>
		</tr>
	</table>

	<link rel="stylesheet" type="text/css" href="https://fonts.googleapis.com/css?family=Playfair+Display+SC:400|Open+Sans:400,300|Oswald:400,700">
</div>
```


## Bottom bar



```
<div class="$responsive" data-style="position:relative; ${args->style:html:default('width: 100%;
padding-top: 10px;
padding-right: sel(48px, 5px);
padding-bottom: 10px;
padding-left: sel(48px, 5px);
text-align: center;
color: #fff;
background-color: rgb(47, 41, 76);
box-sizing: border-box;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(0, 0, 'Box', 'th-large')}">
    <link href="https://fonts.googleapis.com/css?family=Khand" rel="stylesheet">
    <span data-style="${args->title_text_style:html:default('font-family:Khand,sans-serif; font-weight:normal; font-size:15px; text-transform:uppercase'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(1, 1, 'Title', 'bookmark')}">${args->title_text:default(Your text goes here...Your text goes here...Your text goes here...Your text goes here):arg_name(Text):arg_section(1, 0, 'Title', 'bookmark')}</span><a href="${args->button_link:html:default('javascript:'):input_type(url):arg_name(Link):arg_section(2, 2, 'Button', 'hand-o-up')}" onclick="${args->button_link_js:html:input_type(source_javascript):arg_name(Javascript):arg_section(2, 3, 'Button', 'hand-o-up')}" data-style="${args->button_style:html:default('display: inline-block;
color: #fff;
font-family: Khand,sans-serif;
font-weight: normal;
font-size: 14px;
text-transform: uppercase;
text-decoration: none;
margin-left: 16px;
background-color: rgb(133, 185, 121);
padding-top: 5px;
padding-right: 15px;
padding-bottom: 5px;
padding-left: 15px;
border-radius: 20px;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(2, 1, 'Button', 'hand-o-up')}">${args->link_text:default('CTA with link/JS'):arg_name(Text):arg_section(2, 0, 'Button', 'hand-o-up')}</a>
    ${block->show_close_button:default(1):arg_name(Show close button):arg_section(3, 0, 'Close button', 'close')}
    <div data-style="${args->close_button_style:html:default('position: absolute;
top: 13px;
right: 16px;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(3, 1, 'Close button', 'close')}">
        ${args->close_button:default('<div onmouseenter="this.style.backgroundColor=this.style.outlineColor" onmouseleave="this.style.backgroundColor=this.style.textDecorationColor" style="display: inline-block; vertical-align: text-bottom; width: 24px; height: 24px; box-sizing: border-box; border-top-left-radius: 50%; border-top-right-radius: 50%; border-bottom-right-radius: 50%; border-bottom-left-radius: 50%; border: 2px solid; -webkit-box-shadow: rgba(255, 255, 255, 0.2) 0px 1px 0px inset, rgba(0, 0, 0, 0.2) 0px 1px 2px; padding: 3px; background-color: rgb(212, 192, 192); text-decoration-color: rgb(212, 192, 192); outline-color: rgb(206, 54, 64); outline-width: 10px; color: rgb(10, 4, 4); cursor: pointer; transition: all 0.3s ease;" class="$emarketer_button_dont_show_again" data-action_id="${action_id}"><div style="display: block; width: 100%; height: 100%; transition: all 0.3s ease 0s; border-top-left-radius: 50%; border-top-right-radius: 50%; border-bottom-right-radius: 50%; border-bottom-left-radius: 50%; background-image: linear-gradient(-45deg, transparent 0%, transparent 46%, currentcolor 46%, currentcolor 56%, transparent 56%, transparent 100%), linear-gradient(45deg, transparent 0%, transparent 46%, currentcolor 46%, currentcolor 56%, transparent 56%, transparent 100%);"></div></div>'):input_type(dontshowagain):arg_name(Close button):arg_section(3, 2, 'Close button', 'close')}
    </div>
</div>
```


## Small popup



```
<div class="$responsive" data-style="position:relative; display:inline-block; ${args->style:html:default('background-color: rgb(256, 256, 256);
padding: 10px;
border-radius: 2px;
width: 280px;
box-shadow: 0 0 8px 4px rgb(222, 207, 207);
margin-top: 1px;
margin-right: 15px;
margin-bottom: 1px;
margin-left: 1px;'):input_type(css):input_props('with_responsive=1'):arg_name(Box style):arg_section(0, 0, 'Box', 'th-large')}">
	${block->show_close_button:default(1):arg_name(Show close button):arg_section(4, 0, 'Close Button', 'times-circle')}
	<div data-style="position:absolute; cursor:pointer; ${args->close_button_style:html:default('text-align: right;
width: 100%;
top: -10px;'):input_type(css):input_props('with_responsive=1'):arg_name(Close_btn_Style):arg_section(4, 1, 'Close Button', 'times-circle')}">
		${args->close_button:default('<div onmouseenter="this.style.backgroundColor=this.style.outlineColor" onmouseleave="this.style.backgroundColor=this.style.textDecorationColor" style="display: inline-block; vertical-align: text-bottom; width: 24px; height: 24px; box-sizing: border-box; border-top-left-radius: 50%; border-top-right-radius: 50%; border-bottom-right-radius: 50%; border-bottom-left-radius: 50%; border: 0px solid; -webkit-box-shadow: rgba(255, 255, 255, 0.2) 0px 1px 0px inset, rgba(0, 0, 0, 0.2) 0px 1px 2px; padding: 5px; background-color: rgb(190, 61, 22); text-decoration-color: rgb(190, 61, 22); outline-color: rgb(110, 88, 52); outline-width: 10px; color: rgb(246, 244, 244); cursor: pointer; transition: all 0.3s ease;" class="$emarketer_button_dont_show_again" data-action_id="${action_id}"><div style="display: block; width: 100%; height: 100%; transition: all 0.3s ease 0s; border-top-left-radius: 50%; border-top-right-radius: 50%; border-bottom-right-radius: 50%; border-bottom-left-radius: 50%; background-image: linear-gradient(-45deg, transparent 0%, transparent 46%, currentcolor 46%, currentcolor 56%, transparent 56%, transparent 100%), linear-gradient(45deg, transparent 0%, transparent 46%, currentcolor 46%, currentcolor 56%, transparent 56%, transparent 100%);"></div></div>'):input_type(dontshowagain):arg_name(Close button):arg_section(4, 2, 'Close Button', 'times-circle')}
	</div>

	<table data-style="width:100%; border-collapse:collapse">

		<tr>
			<td style="text-align:center; ${args->text_1_style:html:default('background-color: rgba(0, 0, 0, 0);
color: white;'):input_type(css):input_props('with_responsive=1'):arg_name(Text 1 style):arg_section(1, 0, 'Text 1', 'bars')}">
				<div data-style="${args->line_1_style:html:default('font-size: 20px;
color: rgba(38, 38, 63, 0.73);
padding-top: 40px;
padding-right: 20px;
padding-bottom: 15px;
padding-left: 20px;
font-weight: bold;'):input_type(css):input_props('with_responsive=1'):arg_name(Text 1 style):arg_section(1, 2, 'Text 1', 'bars')}">
					${args->line_1:default(TEXT TEXT TEXT TEXT  TEXT TEXT):arg_name(Text 1 line 1):arg_section(1, 1, 'Text 1', 'bars')}
				</div>
				<div data-style="${args->line_2_style:html:default('font-size: 14px;
color: rgb(90, 58, 58);
padding-top: 0px;
padding-right: 20px;
padding-bottom: 15px;
padding-left: 20px;
font-weight: lighter;
text-align: center;'):input_type(css):input_props('with_responsive=1'):arg_name(Text 1 style):arg_section(1, 4, 'Text 1', 'bars')}">
					${args->line_2:default(Text Text Text):arg_name(Text 1 line 2):arg_section(1, 3, 'Text 1', 'bars')}
				</div>
			</td>
		</tr>
		<tr>
			<td style="text-align:center; padding:1em">
				<a ${args->href:default('href=""'):input_type(a_attrs):arg_name(URL):arg_section(2, 1, 'Button', 'hand-o-up')}
					data-style="display:inline-block; ${args->button_text_style:html:default('font-size: 14px;
color: rgb(256, 256, 256);
text-decoration: none;
background-color: rgba(71,206,144,1);
padding-top: 8px;
padding-right: 15px;
padding-bottom: 8px;
padding-left: 15px;
border-radius: 2px;
font-weight: 600;
margin: 5px;
text-transform: uppercase;'):input_type(css):input_props('with_responsive=1'):arg_name(Button text style):arg_section(2, 2, 'Button', 'hand-o-up')}">  ${args->button_t:default(View Offer):arg_name(Text_button):arg_section(2, 0, 'Button', 'hand-o-up')}
				</a>

				${block->show_button_2:default(1):arg_name(Show second button):arg_section(3, 0, 'Second Button', 'hand-o-up')}
				<a ${args->href_2:default('href="javascript:" class="$emarketer_button_dont_show_again" data-action_id="${action_id}" data-n_sessions="0"'):input_type(a_attrs):arg_name(URL):arg_section(3, 2, 'Second Button', 'hand-o-up')}
					data-style="display:inline-block; ${args->button_text_style_2:html:default('color: rgba(42, 28, 28, 0.45);'):input_type(css):input_props('with_responsive=1'):arg_name(Button text style):arg_section(3, 3, 'Second Button', 'hand-o-up')}">
					${args->button_t_2:default(Not interested):arg_name(Text_button):arg_section(3, 1, 'Second Button', 'hand-o-up')}
				</a>
			</td>
		</tr>
	</table>

	<link rel="stylesheet" type="text/css" href="https://fonts.googleapis.com/css?family=Playfair+Display+SC:400|Open+Sans:400,300|Oswald:400,700">
</div>
```


## Popup



```
<div class="$responsive" data-style="position:relative; display:inline-block; ${args->style:html:default('background-color: rgb(253, 253, 253);
padding-top: 6px;
padding-right: 6px;
padding-bottom: 15px;
padding-left: 6px;
border-radius: 5px;
max-width: sel(100%, 90vw);
width: 400px;
border: solid thin rgb(203, 155, 155);'):input_type(css):input_props('with_responsive=1'):arg_name(Box style):arg_section(0, 0, 'Box', 'th-large')}">
	${block->show_close_button:default(1):arg_name(Show close button):arg_section(5, 0, 'Close Button', 'times-circle')}
	<div data-style="position:absolute; cursor:pointer; ${args->close_button_style:html:default('top: -12px;
right: sel(-10px, -5px);
z-index: 9999;'):input_type(css):input_props('with_responsive=1'):arg_name(Close_btn_Style):arg_section(5, 1, 'Close Button', 'times-circle')}">
		${args->close_button:default('<div onmouseenter="this.style.backgroundColor=this.style.outlineColor" onmouseleave="this.style.backgroundColor=this.style.textDecorationColor" style="display: inline-block; vertical-align: text-bottom; width: 22px; height: 22px; box-sizing: border-box; border-top-left-radius: 50%; border-top-right-radius: 50%; border-bottom-right-radius: 50%; border-bottom-left-radius: 50%; border: 0px solid; -webkit-box-shadow: rgba(255, 255, 255, 0.2) 0px 1px 0px inset, rgba(0, 0, 0, 0.2) 0px 1px 2px; padding: 6px; background-color: black; text-decoration-color: black; outline-color: rgb(206, 54, 64); outline-width: 10px; color: rgb(255, 255, 255); cursor: pointer; transition: all 0.3s ease;" class="$emarketer_button_dont_show_again" data-action_id="${action_id}"><div style="display: block; width: 100%; height: 100%; transition: all 0.3s ease 0s; border-top-left-radius: 50%; border-top-right-radius: 50%; border-bottom-right-radius: 50%; border-bottom-left-radius: 50%; background-image: linear-gradient(-45deg, transparent 0%, transparent 46%, currentcolor 46%, currentcolor 56%, transparent 56%, transparent 100%), linear-gradient(45deg, transparent 0%, transparent 46%, currentcolor 46%, currentcolor 56%, transparent 56%, transparent 100%);"></div></div>'):input_type(dontshowagain):arg_name(Close button):arg_section(5, 2, 'Close Button', 'times-circle')}
	</div>

	<table data-style="width:100%; border-collapse:collapse">
		<tr>
			<td style="text-align:center; padding:0">
				<img src="${args->image_src:html:default('https://cdn.e-marketer.io/upload/362/18d08e19c0855cd3.jpeg'):input_type(emarketer_media_url):arg_name(URL):arg_section(1, 0, 'Image', 'image')}" style="vertical-align:bottom; ${args->image_style:html:default('max-width: 95%;'):input_type(css):input_props('with_responsive=1'):arg_name(Text 1 style):arg_section(1, 1, 'Image', 'image')}">
			</td>
		</tr>
		<tr>
			<td style="text-align:center; ${args->text_1_style:html:default('background-color: rgba(0, 0, 0, 0);
color: white;'):input_type(css):input_props('with_responsive=1'):arg_name(Text 1 style):arg_section(2, 0, 'Text 1', 'bars')}">
				<div data-style="${args->line_1_style:html:default('color: rgb(70, 42, 42);
text-align: center;
font-family: Arial;
font-weight: bold;
font-size: 20px;
line-height: 38px;
padding: 5px;
text-transform: uppercase;
letter-spacing: 1px;'):input_type(css):input_props('with_responsive=1'):arg_name(Text 1 style):arg_section(2, 2, 'Text 1', 'bars')}">
					${args->line_1:default(Your title goes here):arg_name(Text 1 line 1):arg_section(2, 1, 'Text 1', 'bars')}
				</div>
				<div data-style="${args->line_2_style:html:default('color: rgb(89, 58, 58);
text-align: center;
font-family: Arial;
font-weight: normal;
font-size: 13px;
padding-top: 5px;
padding-right: 0;
padding-bottom: 10px;
padding-left: 0;
letter-spacing: 1px;'):input_type(css):input_props('with_responsive=1'):arg_name(Text 1 style):arg_section(2, 4, 'Text 1', 'bars')}">
					${args->line_2:default(Text Text Text):arg_name(Text 1 line 2):arg_section(2, 3, 'Text 1', 'bars')}
				</div>
			</td>
		</tr>
		<tr>
			<td style="text-align:center; padding:1em">
				<a ${args->href:default('href=""'):input_type(a_attrs):arg_name(URL):arg_section(3, 1, 'Button', 'hand-o-up')}
					data-style="display:inline-block; ${args->button_text_style:html:default('font-family: Arial;
font-weight: normal;
font-size: 13px;
width: 40%;
height: 30px;
line-height: 30px;
text-align: center;
text-transform: uppercase;
border: 1px solid rgb(160, 65, 65);
border-radius: 3px;
background-color: rgb(118, 66, 66);
color: rgb(249, 247, 247);
padding: 0;'):input_type(css):input_props('with_responsive=1'):arg_name(Button text style):arg_section(3, 2, 'Button', 'hand-o-up')}">  ${args->button_t:default(MORE INFO):arg_name(Text_button):arg_section(3, 0, 'Button', 'hand-o-up')}
				</a>

				${block->show_button_2:default(1):arg_name(Show second button):arg_section(4, 0, 'Second Button', 'hand-o-up')}
				<a ${args->href_2:input_type(a_attrs):arg_name(URL):arg_section(4, 2, 'Second Button', 'hand-o-up')}
					data-style="display:inline-block; ${args->button_text_style_2:html:input_type(css):input_props('with_responsive=1'):arg_name(Button text style):arg_section(4, 3, 'Second Button', 'hand-o-up')}">
					${args->button_t_2:arg_name(Text_button):arg_section(4, 1, 'Second Button', 'hand-o-up')}
				</a>
			</td>
		</tr>
	</table>

	<link rel="stylesheet" type="text/css" href="https://fonts.googleapis.com/css?family=Playfair+Display+SC:400|Open+Sans:400,300|Oswald:400,700">
</div>
```


## Popup



```
<div class="$responsive" data-style="position:relative; display:inline-block; ${args->style:html:default('background-color: rgba(124, 176, 120, 0.55);
padding-top: 0px;
padding-right: 25px;
padding-bottom: 0px;
padding-left: 25px;
border-top-left-radius: 10px;
border-top-right-radius: 10px;
border-bottom-right-radius: 30px;
border-bottom-left-radius: 30px;
width: auto;
background-image: url(''https://cdn.e-marketer.io/upload/362/5c566581bb271535.jpeg'');
background-size: contain;
background-repeat: no-repeat;'):input_type(css):input_props('with_responsive=1'):arg_name(Box style):arg_section(0, 0, 'Box', 'th-large')}">
	${block->show_close_button:default(1):arg_name(Show close button):arg_section(4, 0, 'Close Button', 'times-circle')}
	<div data-style="position:absolute; cursor:pointer; ${args->close_button_style:html:default('float: right;
width: 92%;
text-align: right;
position: absolute;
top: -10px;
right: -5px;'):input_type(css):input_props('with_responsive=1'):arg_name(Close_btn_Style):arg_section(4, 1, 'Close Button', 'times-circle')}">
		${args->close_button:default('<div onmouseenter="this.style.backgroundColor=this.style.outlineColor" onmouseleave="this.style.backgroundColor=this.style.textDecorationColor" style="display: inline-block; vertical-align: text-bottom; width: 24px; height: 24px; box-sizing: border-box; border-top-left-radius: 50%; border-top-right-radius: 50%; border-bottom-right-radius: 50%; border-bottom-left-radius: 50%; border: 2px solid; -webkit-box-shadow: rgba(255, 255, 255, 0.2) 0px 1px 0px inset, rgba(0, 0, 0, 0.2) 0px 1px 2px; padding: 3px; background-color: rgb(207, 120, 58); text-decoration-color: rgb(207, 120, 58); outline-color: rgb(206, 54, 64); outline-width: 10px; color: rgb(10, 4, 4); cursor: pointer; transition: all 0.3s ease;" class="$emarketer_button_dont_show_again" data-action_id="${action_id}"><div style="display: block; width: 100%; height: 100%; transition: all 0.3s ease 0s; border-top-left-radius: 50%; border-top-right-radius: 50%; border-bottom-right-radius: 50%; border-bottom-left-radius: 50%; background-image: linear-gradient(-45deg, transparent 0%, transparent 46%, currentcolor 46%, currentcolor 56%, transparent 56%, transparent 100%), linear-gradient(45deg, transparent 0%, transparent 46%, currentcolor 46%, currentcolor 56%, transparent 56%, transparent 100%);"></div></div>'):input_type(dontshowagain):arg_name(Close button):arg_section(4, 2, 'Close Button', 'times-circle')}
	</div>

	<table data-style="width:100%; border-collapse:collapse">

		<tr>
			<td style="text-align:center; ${args->text_1_style:html:default('background-color: rgba(0, 0, 0, 0);
color: white;'):input_type(css):input_props('with_responsive=1'):arg_name(Text 1 style):arg_section(1, 0, 'Text 1', 'bars')}">
				<div data-style="${args->line_1_style:html:default('font-size: 28px;
color: rgb(251, 250, 250);
padding-top: 40px;
padding-right: 20px;
padding-bottom: 0px;
padding-left: 0px;
font-weight: bold;
text-align: left;
text-transform: none;'):input_type(css):input_props('with_responsive=1'):arg_name(Text 1 style):arg_section(1, 2, 'Text 1', 'bars')}">
					${args->line_1:default(Title goes here):arg_name(Text 1 line 1):arg_section(1, 1, 'Text 1', 'bars')}
				</div>
				<div data-style="${args->line_2_style:html:default('font-size: 18px;
margin-top: 0;
margin-right: 0;
margin-bottom: 0px;
margin-left: 0;
font-weight: 400;
color: rgb(256, 256, 256);
line-height: 1.3;
text-align: left;'):input_type(css):input_props('with_responsive=1'):arg_name(Text 1 style):arg_section(1, 4, 'Text 1', 'bars')}">
					${args->line_2:default('Description goes here<br />
&nbsp;'):arg_name(Text 1 line 2):arg_section(1, 3, 'Text 1', 'bars')}
				</div>
			</td>
		</tr>
		<tr>
			<td style="text-align:center; padding:1em">
				<a ${args->href:default('href="" data-emarketer-click-target=""'):input_type(a_attrs):arg_name(URL):arg_section(2, 1, 'Button', 'hand-o-up')}
					data-style="display:inline-block; ${args->button_text_style:html:default('height: auto;
border: 2px solid rgb(70, 143, 61);
line-height: 25px;
text-align: center;
color: rgb(251, 250, 250);
border-radius: 15px;
font-size: 1.2em;
text-decoration: none;
padding-top: 0px;
padding-right: 15px;
padding-bottom: 0px;
padding-left: 15px;
width: 80%;
background-color: rgb(70, 143, 61);'):input_type(css):input_props('with_responsive=1'):arg_name(Button text style):arg_section(2, 2, 'Button', 'hand-o-up')}">  ${args->button_t:default(MORE INFO):arg_name(Text_button):arg_section(2, 0, 'Button', 'hand-o-up')}
				</a>

				${block->show_button_2:default(0):arg_name(Show second button):arg_section(3, 0, 'Second Button', 'hand-o-up')}
				<a ${args->href_2:input_type(a_attrs):arg_name(URL):arg_section(3, 2, 'Second Button', 'hand-o-up')}
					data-style="display:inline-block; ${args->button_text_style_2:html:input_type(css):input_props('with_responsive=1'):arg_name(Button text style):arg_section(3, 3, 'Second Button', 'hand-o-up')}">
					${args->button_t_2:arg_name(Text_button):arg_section(3, 1, 'Second Button', 'hand-o-up')}
				</a>
			</td>
		</tr>
	</table>


</div>
```


## Copy Coupon Banner



```
<div class="$responsive" data-style="position:relative; ${args->style:html:default('width:100%; padding:12px 48px; text-align:center; color:#fff; background-color:rgba(0,0,0,.8); box-sizing:border-box'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(0, 0, 'Box', 'th-large')}">
    <link href="https://fonts.googleapis.com/css?family=Poppins" rel="stylesheet">
    <span data-style="${args->title_text_style:html:default('font-family:Poppins,sans-serif; font-weight:normal; font-size:11px; line-height:28px'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(1, 1, 'Title', 'bookmark')}">${args->title_text:default('Add code&nbsp;&nbsp;<span class="want-copy" style="color:#f1c40f;">FREESHP</span>&nbsp;to your shopping cart and get 10% off'):arg_name(Text):arg_section(1, 0, 'Title', 'bookmark')}</span><a href="${args->button_link:html:default('javascript:'):input_type(url):arg_name(Link):arg_section(2, 2, 'Button', 'hand-o-up')}" onclick="${args->button_link_js:html:default('var e = this.previousElementSibling.querySelector(''.want-copy'');
if (e)
{	var r = document.createRange();
	r.selectNode(e);
	var s = getSelection();
	s.removeAllRanges();
	s.addRange(r);
	document.execCommand("Copy");
	new ns.ElemsAnnotator(''info'').add(e, "Copied!").annotate(5000);
}'):input_type(source_javascript):arg_name(Javascript):arg_section(2, 3, 'Button', 'hand-o-up')}" data-style="${args->button_style:html:default('display: inline-block;
width: 120px;
line-height: 24px;
color: rgb(62, 50, 50);
background-color: RGB(252, 204, 3);
border-radius: 5px;
font-family: Poppins,sans-serif;
font-weight: normal;
font-size: 10px;
text-decoration: none;
margin-left: 16px;
vertical-align: middle;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(2, 1, 'Button', 'hand-o-up')}">${args->button_caption:default(Copy CODE):arg_name(Caption):arg_section(2, 0, 'Button', 'hand-o-up')}</a>
    ${block->show_close_button:default(1):arg_name(Show close button):arg_section(3, 0, 'Close button', 'close')}
    <div data-style="${args->close_button_style:html:default('position:absolute; top:18px; right:16px'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(3, 1, 'Close button', 'close')}">
        ${args->close_button:default('<a href="javascript:" style="font-size: 24px; color: rgb(253, 253, 253); font-weight: bold; line-height: 1; text-decoration: none;" class="$emarketer_button_dont_show_again" data-action_id="${action_id}">×</a>'):input_type(dontshowagain):arg_name(Close button):arg_section(3, 2, 'Close button', 'close')}
    </div>
</div>
```


## Copy coupon code



```
<div class="$responsive" data-style="position:relative; ${args->style:html:default('width: 100%;
padding-top: sel(19px, 5px);
padding-right: 48px;
padding-bottom: sel(7px, 12px);
padding-left: 48px;
text-align: center;
color: #fff;
background-color: rgb(0, 0, 0);
box-sizing: border-box;
height: sel(70px, auto);
')}">
    <link href="https://fonts.googleapis.com/css?family=Poppins" rel="stylesheet">
    <span data-style="${args->title_text_style:html:default('font-family: Poppins,sans-serif;
font-weight: normal;
font-size: 18px;
line-height: 28px;
')}">${args->title_text:default('Welcome to Kleidermafia Use&nbsp;<span class="want-copy" style="color:#f1c40f;"> MAFIA20&nbsp;</span>to get 20% Off Welcome Coupon')}</span><a href="${args->button_link:html:default('javascript:')}" onclick="${args->button_link_js:html:default('var e = this.previousElementSibling.querySelector(''.want-copy'');
if (e)
{	var r = document.createRange();
	r.selectNode(e);
	var s = getSelection();
	s.removeAllRanges();
	s.addRange(r);
	document.execCommand("Copy");
	new ns.ElemsAnnotator(''info'').add(e, "Copied!").annotate(5000);
}')}" data-style="${args->button_style:html:default('display: inline-block;
line-height: 24px;
color: #000000;
background-color: #ffc520;
border-radius: 5px;
font-family: Poppins,sans-serif;
font-weight: normal;
font-size: 13px;
text-decoration: none;
margin-left: 16px;
vertical-align: middle;
padding-top: 3px;
padding-right: 10px;
padding-bottom: 3px;
padding-left: 10px;
width: auto;
')}">${args->button_caption:default(Copy CODE)}</a>
    ${block->show_close_button:default(1)}
    <div data-style="${args->close_button_style:html:default('position: absolute;
top: 22px;
right: 16px;
')}">
        ${args->close_button:default('<div onmouseenter="this.style.backgroundColor=this.style.outlineColor" onmouseleave="this.style.backgroundColor=this.style.textDecorationColor" style="display: inline-block; vertical-align: text-bottom; width: 24px; height: 24px; box-sizing: border-box; border-radius: 50%; border: 2px solid; box-shadow: rgba(255, 255, 255, 0.2) 0px 1px 0px inset, rgba(0, 0, 0, 0.2) 0px 1px 2px; padding: 3px; background-color: rgb(207, 120, 58); text-decoration-color: rgb(207, 120, 58); outline-color: rgb(206, 54, 64); outline-width: 10px; color: rgb(10, 4, 4); cursor: pointer; transition: all 0.3s ease 0s;" class="$personyze_button_dont_show_again" data-action_id="${action_id}"><div style="display: block; width: 100%; height: 100%; transition: all 0.3s ease 0s; border-radius: 50%; background-image: linear-gradient(-45deg, transparent 0%, transparent 46%, currentcolor 46%, currentcolor 56%, transparent 56%, transparent 100%), linear-gradient(45deg, transparent 0%, transparent 46%, currentcolor 46%, currentcolor 56%, transparent 56%, transparent 100%);"></div></div>')}
    </div>
</div>

${menu name='Box', icon='th-large'}
	${menu args->style name='Style', type='css', param='with_responsive=1'}
${menu name='Title', icon='bookmark'}
	${menu args->title_text name='Text'}
	${menu args->title_text_style name='Style', type='css', param='with_responsive=1'}
${menu name='Button', icon='hand-o-up'}
	${menu args->button_caption name='Caption'}
	${menu args->button_style name='Style', type='css', param='with_responsive=1'}
	${menu args->button_link name='Link', type='url'}
	${menu args->button_link_js name='Javascript', type='source_javascript'}
${menu name='Close button', icon='close'}
	${menu block->show_close_button name='Show close button'}
	${menu args->close_button_style name='Style', type='css', param='with_responsive=1'}
	${menu args->close_button name='Close button', type='dontshowagain'}
```


## Two columns



```
<div class="$responsive" data-style="position:relative; ${args->style:html:default('width: 650px;
background-color: white;
color: #424242;
font-family: Roboto,san-serif;
font-size: 16px;
padding: 50px;
border-radius: 2px;
box-sizing: border-box;
box-shadow: 0px 0px 8px 6px rgba(0, 0, 0, 0.3);'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(0, 0, 'Frame', 'th-large')}">
	<link rel="stylesheet" href="https://fonts.googleapis.com/css?family=Roboto:400,400i,700,700i,900">
	${block->x:default(1):arg_name(With close button):arg_section(9, 0, 'Close button', 'close')}
		<div style="position: absolute; top: 5px; right: 5px; cursor:pointer;">
			${args->x:default('<div onmouseenter="this.style.backgroundColor=this.style.outlineColor" onmouseleave="this.style.backgroundColor=this.style.textDecorationColor" style="display: inline-block; vertical-align: text-bottom; width: 24px; height: 24px; box-sizing: border-box; border-top-left-radius: 50%; border-top-right-radius: 50%; border-bottom-right-radius: 50%; border-bottom-left-radius: 50%; border: 2px solid; -webkit-box-shadow: rgba(255, 255, 255, 0.2) 0px 1px 0px inset, rgba(0, 0, 0, 0.2) 0px 1px 2px; padding: 3px; background-color: rgb(207, 120, 58); text-decoration-color: rgb(207, 120, 58); outline-color: rgb(206, 54, 64); outline-width: 8px; color: rgb(10, 4, 4); cursor: pointer; transition: all 0.3s ease;" class="$personyze_button_dont_show_again" data-action_id="${action_id}"><div style="display: block; width: 100%; height: 100%; transition: all 0.3s ease 0s; border-top-left-radius: 50%; border-top-right-radius: 50%; border-bottom-right-radius: 50%; border-bottom-left-radius: 50%; background-image: linear-gradient(-45deg, transparent 0%, transparent 47%, currentcolor 47%, currentcolor 55%, transparent 55%, transparent 100%), linear-gradient(45deg, transparent 0%, transparent 47%, currentcolor 47%, currentcolor 55%, transparent 55%, transparent 100%);"></div></div>'):input_type(dontshowagain):arg_name(Close button):arg_section(9, 1, 'Close button', 'close')}
		</div>
	${block->welcome:default(1):arg_name(With welcome message):arg_section(1, 0, 'Welcome message', 'th-large')}
		<div data-style="${args->welcome_style:html:default('text-align: center;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(1, 2, 'Welcome message', 'th-large')}">${args->welcome_text:default(Text Text):arg_name(Text):arg_section(1, 1, 'Welcome message', 'th-large')}</div>
	${block->title:default(1):arg_name(With title):arg_section(2, 0, 'Title', 'th-large')}
		<div data-style="${args->title_style:html:default('margin: 10px 60px 0; font-size: 32px; font-weight: 700; color: #41436e; text-align: center;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(2, 2, 'Title', 'th-large')}">${args->title_text:default(Text Text Text TextText Text):arg_name(Text):arg_section(2, 1, 'Title', 'th-large')}</div>
	${block->description:default(1):arg_name(With description):arg_section(3, 0, 'Description', 'th-large')}
		<div data-style="${args->description_style:html:default('text-align: center; margin-top: 10px;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(3, 2, 'Description', 'th-large')}">${args->description_text:default(Text TextText TextText TextText TextText TextText TextText TextText TextText TextText TextText TextText TextText TextText TextText TextText Text):arg_name(Text):arg_section(3, 1, 'Description', 'th-large')}</div>
	<div data-style="${args->columns_block_style:html:default('margin: 20px 20px 0;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(4, 0, 'Columns', 'th-large')}">
		${block->left_column:default(1):arg_name(With left column):arg_section(5, 0, 'Left column', 'th-large')}
			<div data-style="${args->left_column_style:html:default('width: 50%; max-width: 100%; display: inline-block; vertical-align: top; box-sizing: border-box;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(5, 2, 'Left column', 'th-large')}">
				${args->left_column_content:default('<ul style="list-style-type: none; padding: 0; line-height: 2;">
	<li><img src="https://cdn.personyze.com/upload/4822/51930df8070b6c0b.png" style="position: relative; top: 5px; margin-right: 12px;" />Text Text</li>
	<li><img src="https://cdn.personyze.com/upload/4822/51930df8070b6c0b.png" style="position: relative; top: 5px; margin-right: 12px;" />Text Text</li>
	<li><img src="https://cdn.personyze.com/upload/4822/51930df8070b6c0b.png" style="position: relative; top: 5px; margin-right: 12px;" />Text Text</li>
	<li><br />
	Text TextText TextText TextText TextTexText</li>
</ul>
'):arg_name(Content):arg_section(5, 1, 'Left column', 'th-large')}
			</div>${block->right_column:default(1):arg_name(With right column):arg_section(6, 0, 'Right column', 'th-large')}<div data-style="${args->right_column_style:html:default('width: 50%; max-width: 100%; display: inline-block; vertical-align: top; background-color: #f5f5f5; padding: 25px 27px; line-height: 1.5; box-sizing: border-box;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(6, 2, 'Right column', 'th-large')}">
				${args->right_column_content:default('<p style="margin-top: 0;">Text TextText TextText TextText TextText TextText Text</p>

<p>I don&#39;t mind receiving this weekly - <span style="font-weight: 700;">just takes 10 seconds to look at it</span>.&rdquo;</p>

<p style="margin-bottom: 0; font-style: italic;">&mdash; Senior System Engineer</p>
'):arg_name(Content):arg_section(6, 1, 'Right column', 'th-large')}
			</div>
	</div>
	<div data-style="${args->button1_block_style:html:default('margin-top: 25px; text-align: center;'):input_type(css):input_props('with_responsive=1'):arg_name(Block style):arg_section(7, 2, 'Button 1', 'hand-o-up')}">
		<a ${args->button1_link:default('href="" data-personyze-click-target=""'):input_type(a_attrs):arg_name(URL):arg_section(7, 1, 'Button 1', 'hand-o-up')} data-style="${args->button1_style:html:default('display: inline-block; padding: 12px 40px; background-color: #4b6cc9; color: white; font-size: 14px; text-transform: uppercase; text-decoration: none; border-radius: 2px;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(7, 3, 'Button 1', 'hand-o-up')}">${args->button1_text:default(Text TextText TextText TextText Text):arg_name(Text):arg_section(7, 0, 'Button 1', 'hand-o-up')}</a>
	</div>
	<div data-style="${args->button2_block_style:html:default('margin-top: 25px; text-align: center;'):input_type(css):input_props('with_responsive=1'):arg_name(Block style):arg_section(8, 2, 'Button 2', 'hand-o-up')}">
		<a ${args->button2_link:default('href="" data-personyze-click-target=""'):input_type(a_attrs):arg_name(URL):arg_section(8, 1, 'Button 2', 'hand-o-up')} data-style="${args->button2_style:html:default('color: #4b6cc9; text-decoration: none;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(8, 3, 'Button 2', 'hand-o-up')}">${args->button2_text:default(Text TextText TextText TextText TextText Text):arg_name(Text):arg_section(8, 0, 'Button 2', 'hand-o-up')}</a>
	</div>
</div>
```


## Banner



```
<div class="$responsive $a_add_params" data-style="position:relative; display:inline-block; overflow: hidden; ${args->style:html:default('width: 400px; height: 300px; background-color: white; color: black; font-family: Roboto,san-serif; font-size: 16px; border: 1px solid #E8E8E8; border-radius: 5px; box-sizing: border-box;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(0, 0, 'Frame', 'th-large')}" data-json-params="${args->url_params:html:default('[]'):input_type(external_media_url_params):arg_name(URL additional parameters):arg_section(0, 3, 'Frame', 'th-large')}" direction:${args->direction:default(ltr):input_type(select):input_props('options=[["Left to right","ltr"],["Right to left","rtl"]]'):arg_name(Localization settings):arg_section(0, 1, 'Frame', 'th-large')};">
    <link rel="stylesheet" href="https://fonts.googleapis.com/css?family=Roboto:400,400i,700,700i,900">
	${block->x:default(0):arg_name(With close button):arg_section(4, 0, 'Close button', 'close')}
	<div style="position: absolute; ${args->x_position:html:input_type(css):input_props('with_responsive=1'):arg_name(Position):arg_section(4, 2, 'Close button', 'close')}; cursor:pointer;">
		${args->x:input_type(dontshowagain):arg_name(Close button):arg_section(4, 1, 'Close button', 'close')}
	</div>

	<table style="width: 100%; height: 100%; border: 0; border-collapse: collapse;">
		<tr>
			<td data-style="${args->line1_style:html:default('background-image: url(''https://cdn.personyze.com/upload/362/5c566581bb271535.jpeg'');
background-size: cover;
background-repeat: no-repeat;
background-position: center;'):input_type(css):input_props('with_responsive=1'):arg_name(Block style):arg_section(1, 0, 'Line 1', 'picture-o')}">
				<div data-style="${args->line1_text_style:html:input_type(css):input_props('with_responsive=1'):arg_name(Text style):arg_section(1, 2, 'Line 1', 'picture-o')}">${args->line1_text:html:arg_name(Text):arg_section(1, 1, 'Line 1', 'picture-o')}</div>
			</td>
		</tr>
		<tr style="height: 1px;">
			<td data-style="${args->line2_style:html:default('background-color: #F1F2F6; text-align: center; vertical-align: middle;'):input_type(css):input_props('with_responsive=1'):arg_name(Block style):arg_section(2, 0, 'Line 2', 'picture-o')}">
				<div data-style="display: inline-block; ${args->line2_text_style:html:default('margin: 20px 10px; font-size: 18px; color: ##040507; vertical-align: middle;'):input_type(css):input_props('with_responsive=1'):arg_name(Text style):arg_section(2, 2, 'Line 2', 'picture-o')}">${args->line2_text:default(TEXT TEXT):arg_name(Text):arg_section(2, 1, 'Line 2', 'picture-o')}</div>
				<a ${args->href:default('href="" data-personyze-click-target=""'):input_type(a_attrs):arg_name(URL):arg_section(2, 5, 'Line 2', 'picture-o')}
					data-style="display: inline-block; ${args->button_text_style:html:default('margin: 20px 10px; padding: 0 8px; height: 32px; line-height: 32px; font-size: 16px; font-weight: 600; background-color: transparent; color: #4C4D51; border: 2px solid #929397; border-radius: 5px; text-align: center; vertical-align: middle; text-decoration: none;'):input_type(css):input_props('with_responsive=1'):arg_name(Button text style):arg_section(2, 3, 'Line 2', 'picture-o')}">  ${args->button_text:default(SHOP NOW):arg_name(Text_button):arg_section(2, 4, 'Line 2', 'picture-o')}
				</a>
			</td>
		</tr>
	</table>

    ${block->with_label:default(1):arg_name(With Label):arg_section(3, 0, 'Label', 'th-large')}
    <div data-style="position: absolute; display: inline-block; ${args->label_style:html:default('top: 10px; right: 12px; padding: 0 16px; height: 32px; line-height: 32px; font-size: 16px; font-weight: 600; background-color: #DF6E2D; color: #FBF6EC; border-radius: 16px; vertical-align: middle;'):input_type(css):input_props('with_responsive=1'):arg_name(Label style):arg_section(3, 2, 'Label', 'th-large')}">
    	${args->currency:html:arg_name(Currency symbol):arg_section(0, 2, 'Frame', 'th-large')}
    	${args->price:sprintf('%[#.00]f'):default(TEXT):arg_name(Price):arg_section(3, 1, 'Label', 'th-large')}
    </div>
</div>
```


## Items dispaly



```
<div class="$responsive $a_add_params" data-style="display:block; position:relative; ${args->style:html:default('max-width: 100vw; margin: 0 auto; box-sizing: border-box;')}" data-json-params="${args->url_params:html}">
    <link rel="stylesheet" href="https://fonts.googleapis.com/css?family=Open+Sans:400,400i,500,500i,600,600i,700,700i">
	<style>
		.-s-t-202007031-card {
			width: 100% !important;
			margin: 0 0 1.5rem !important;
		}

		@media (max-width: 785px) and (min-width: 512px) {
			.-s-t-202007031-card {
				width: 49% !important;
			    margin-right: 2% !important;;
			    margin-bottom: 2% !important;;
			}
		}

		@media (min-width: 786px) {
			.-s-t-202007031-card {
			    width: 32% !important;;
			    margin-right: 2% !important;;
			    margin-bottom: 2% !important;;
			}
		}

		@media (min-width: 786px) {
			.-s-t-202007031-card:nth-of-type(3n+3) {
				margin-right: 0 !important;;
			}
		}

		@media (max-width: 785px) and (min-width: 512px) {
			.-s-t-202007031-card:nth-of-type(2n+2) {
				margin-right: 0 !important;;
			}
		}
	</style>
	${block->item1:default(1)}
	<div class="-s-t-202007031-card" data-style="display: inline-block; float: left; ${args->item_style:html:default('background-color: #E5F0F9; border:1px solid #CAE0F3; font-family: &quot;Open Sans&quot;, Arial, sans-serif;')}; box-sizing: border-box;">
		<a ${args->item1_link_url:default('href="#" data-personyze-click-target=""')} data-style="display: block; ${args->item_image_style:html:default('max-height: 160px; margin: 0 0 1.6rem; overflow: hidden; color: #006ec7; text-decoration: none; cursor: pointer; outline: none;')}; box-sizing: border-box;">
			<img src="${args->item1_image_url:html:default('https://cdn.personyze.com/upload/362/1bab0cf807153953.jpeg')}" style="width: 100%; height: auto; border: 0;" />
		</a>
		<div data-style="${args->item_text_style:html:default('min-height: 18.4rem; margin: 0 25px;')}; box-sizing: border-box;">
			<a ${args->item1_link_url} data-style="${args->item_title_style:html:default('display: -webkit-box; -webkit-line-clamp: 2; -webkit-box-orient: vertical; max-height: 160px; margin: 0 0 1.6rem; overflow: hidden; color: #34383c; text-decoration:none; cursor:pointer; outline: none; font-weight: 600; font-size: 1.8rem; line-height: 2.4rem;')}; box-sizing: border-box;">${args->item1_title:default(text  text texttext  text texttext  text texttext  text texttext  text texttext  text texttext  text texttext  text texttext  text texttext  text texttext  text text)}</a>
			<p data-style="${args->item_description_style:html:default('display: -webkit-box; -webkit-line-clamp: 4; -webkit-box-orient: vertical; margin: 0 0 1.6rem; font-size:14px; overflow: hidden; line-height: 22px; color: #4C5157;')}; box-sizing: border-box;">${args->item1_description:default(text  text texttext  text texttext  text texttext  text texttext  text texttext  text texttext  text texttext  text texttext  text texttext  text texttext  text texttext  text text)}</p>
		</div>
		<a ${args->item1_link_url} data-style="display: block; ${args->item_link_style:html:default('padding: 12px 25px; text-decoration: none; cursor: pointer; outline: none; text-transform: uppercase; font-weight: 600; color: rgba(0, 110, 199, .75); border-top: 1px solid #CAE0F3;')}; box-sizing: border-box;">${args->item1_link_text:default(Recommended for you)}</a>
	</div>
	${block->item2:default(1)}
	<div class="-s-t-202007031-card" data-style="display: inline-block; float: left; ${args->item_style:html}; box-sizing: border-box;">
		<a ${args->item2_link_url:default('href=""')} data-style="display: block; ${args->item_image_style:html}; box-sizing: border-box;">
			<img src="${args->item2_image_url:html:default('https://cdn.personyze.com/upload/362/7d0a26d42b6f9a72.jpeg')}" style="width: 100%; height: auto; border: 0;" />
		</a>
		<div data-style="${args->item_text_style:html}; box-sizing: border-box;">
			<a ${args->item2_link_url} data-style="${args->item_title_style:html}; box-sizing: border-box;">${args->item2_title:default(text  text texttext  text texttext  text texttext  text texttext  text text)}</a>
			<p data-style="${args->item_description_style:html}; box-sizing: border-box;">${args->item2_description:default(text  text texttext  text texttext  text texttext  text texttext  text texttext  text texttext  text texttext  text texttext  text text)}</p>
		</div>
		<a ${args->item2_link_url} data-style="display: block; ${args->item_link_style:html}; box-sizing: border-box;">${args->item2_link:default(Read More)}</a>
	</div>
	${block->item3:default(1)}
	<div class="-s-t-202007031-card" style="display: inline-block; float: left; ${args->item_style:html}; box-sizing: border-box;">
		<a ${args->item3_link_url:default('href="#" data-personyze-click-target=""')} data-style="display: block; ${args->item_image_style:html}; box-sizing: border-box;" target="_blank">
			<img src="${args->item3_image_url:html:default('https://cdn.personyze.com/upload/362/1bab0cf807153953.jpeg')}" style="width: 100%; height: auto; border: 0;" />
		</a>
		<div data-style="${args->item_text_style:html}; box-sizing: border-box;">
			<a ${args->item3_link_url} data-style="${args->item_title_style:html}; box-sizing: border-box;">${args->item3_title:default(text  text te  xttext  text texttext  text texttext  text texttext  text texttext  text texttext  text text)}</a>
			<p data-style="${args->item_description_style:html}; box-sizing: border-box;">${args->item3_description:default(Text text  text text text  text texttext  text texttext  text texttext  text texttext  text texttext  text texttext  text texttext  text texttext  text texttext  text texttext  text texttext  text text)}</p>
		</div>
		<a ${args->item3_link_url} data-style="display: block; ${args->item_link_style:html}; box-sizing: border-box;">${args->item3_link:default(Recommended for you)}</a>
	</div>
	${block->item4:default(0)}
	<div class="-s-t-202007031-card" style="display: inline-block; float: left; ${args->item_style:html}; box-sizing: border-box;">
		<a ${args->item4_link_url} data-style="display: block; ${args->item_image_style:html}; box-sizing: border-box;" target="_blank">
			<img src="${args->item3_image_url:html}" style="width: 100%; height: auto; border: 0;" />
		</a>
		<div data-style="${args->item_text_style:html}; box-sizing: border-box;">
			<a ${args->item4_link_url} data-style="${args->item_title_style:html}; box-sizing: border-box;">${args->item4_title}</a>
			<p data-style="${args->item_description_style:html}; box-sizing: border-box;">${args->item4_description}</p>
		</div>
		<a ${args->item4_link_url} data-style="display: block; ${args->item_link_style:html}; box-sizing: border-box;">${args->item4_link}</a>
	</div>
</div>

${menu name='Frame', icon='th-large'}
	${menu args->style name='Style', type='css', param='with_responsive=1'}
	${menu args->url_params name='URL additional parameters', type='external_media_url_params'}
${menu name='Item frame', icon='th-large'}
	${menu args->item_style name='Style', type='css', param='with_responsive=1'}
	${menu args->item_image_style name='Image style', type='css', param='with_responsive=1'}
	${menu args->item_text_style name='Text block style', type='css', param='with_responsive=1'}
	${menu args->item_title_style name='Title style', type='css', param='with_responsive=1'}
	${menu args->item_description_style name='Description style', type='css', param='with_responsive=1'}
	${menu args->item_link_style name='Link style', type='css', param='with_responsive=1'}
${menu name='Item 1', icon='bookmark'}
	${menu block->item1 name='With item 1'}
	${menu args->item1_image_url name='Image URL', type='personyze_media_url'}
	${menu args->item1_title name='Title'}
	${menu args->item1_description name='Description'}
	${menu args->item1_link_text name='Link text'}
	${menu args->item1_link_url name='Link URL', type='a_attrs'}
${menu name='Item 2', icon='bookmark'}
	${menu block->item2 name='With item 2'}
	${menu args->item2_image_url name='Image URL', type='personyze_media_url'}
	${menu args->item2_title name='Title'}
	${menu args->item2_description name='Description'}
	${menu args->item2_link name='Link text'}
	${menu args->item2_link_url name='Link URL', type='a_attrs'}
${menu name='Item 3', icon='bookmark'}
	${menu block->item3 name='With item 3'}
	${menu args->item3_image_url name='Image URL', type='personyze_media_url'}
	${menu args->item3_title name='Title'}
	${menu args->item3_description name='Description'}
	${menu args->item3_link name='Link text'}
	${menu args->item3_link_url name='Link URL', type='a_attrs'}
${menu name='Item 4', icon='bookmark'}
	${menu block->item4 name='With item 4'}
	${menu args->item4_title name='Title'}
	${menu args->item4_description name='Description'}
	${menu args->item4_link name='Link text'}
	${menu args->item4_link_url name='Link URL', type='a_attrs'}
```


## Big Slider with 2 images and 2 call to action



```
<div class="$responsive $a_add_params -s-t-root" data-style="display:inline-block; position:relative; ${args->style:html:default('width: 100%;
height: auto;
min-height: 26rem;
background: rgb(248, 248, 248);
background-image: url(''https://cdn.personyze.com/upload/362/1bab0cf807153953.jpeg'');
background-size: cover;
background-position: 50% 50%;
font-family: ''Open Sans'', Arial, sans-serif;
text-align: left;
border: none;
overflow: hidden;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(0, 0, 'Frame', 'th-large')}; box-sizing: border-box;" data-json-params="${args->url_params:html:input_type(external_media_url_params):arg_name(URL additional parameters):arg_section(0, 1, 'Frame', 'th-large')}">
    <style>
        .-s-t-root {
            padding: 8% !important;
        }
        .-s-t-content {
            max-width: 104rem !important;
            margin: 0 auto !important;
            padding: 0 1rem !important;
            box-sizing: box-content !important;
        }
        .-s-t-text {
            display: inline-block !important;
            margin-top: 3.5rem !important;
            max-width: 80rem !important;
        }
        .-s-t-title {
            font-size: 2.8rem !important;
        }
        .-s-t-description {
            font-size: 2.2rem !important;
        }
        .-s-t-image {
            margin-top: 5rem !important;
            max-height: 100% !important;
            text-align: center !important;
            box-sizing: box-content !important;
        }
        @media (min-width: 512px) {
            .-s-t-root {
                padding: 0 6% !important;
            }
            .-s-t-content {
                padding: 6rem 2rem !important;
            }
            .-s-t-text {
                width: 60% !important;
            }
            .-s-t-title {
                font-size: 3.5rem !important;
            }
            .-s-t-description {
                font-size: 2.8rem !important;
            }
            .-s-t-image {
                display: inline-block !important;
                float: right !important;
                margin-top: 0 !important;
                margin-bottom: 6rem !important;
                max-width: 85% !important;
                width: 35% !important;
            }
        }
    </style>
    ${block->x:default(1):arg_name(With close button):arg_section(7, 0, 'Close button', 'close')}
    <div style="position: absolute; ${args->x_position:html:default('top: 5px; right: 5px;'):input_type(css):input_props('with_responsive=1'):arg_name(Position):arg_section(7, 2, 'Close button', 'close')}; cursor:pointer;">
        ${args->x:default('<div onmouseenter="this.style.backgroundColor=this.style.outlineColor" onmouseleave="this.style.backgroundColor=this.style.textDecorationColor" style="display: inline-block; vertical-align: text-bottom; width: 24px; height: 24px; box-sizing: border-box; border-top-left-radius: 50%; border-top-right-radius: 50%; border-bottom-right-radius: 50%; border-bottom-left-radius: 50%; border: 2px solid; -webkit-box-shadow: rgba(255, 255, 255, 0.2) 0px 1px 0px inset, rgba(0, 0, 0, 0.2) 0px 1px 2px; padding: 3px; background-color: rgb(207, 120, 58); text-decoration-color: rgb(207, 120, 58); outline-color: rgb(206, 54, 64); outline-width: 10px; color: rgb(10, 4, 4); cursor: pointer; transition: all 0.3s ease;" class="$personyze_button_dont_show_again" data-action_id="${action_id}"><div style="display: block; width: 100%; height: 100%; transition: all 0.3s ease 0s; border-top-left-radius: 50%; border-top-right-radius: 50%; border-bottom-right-radius: 50%; border-bottom-left-radius: 50%; background-image: linear-gradient(-45deg, transparent 0%, transparent 46%, currentcolor 46%, currentcolor 56%, transparent 56%, transparent 100%), linear-gradient(45deg, transparent 0%, transparent 46%, currentcolor 46%, currentcolor 56%, transparent 56%, transparent 100%);"></div></div>'):input_type(dontshowagain):arg_name(Close button):arg_section(7, 1, 'Close button', 'close')}
    </div>
    <div class="-s-t-content">
        <div class="-s-t-text">
            ${block->title:default(1):arg_name(With title):arg_section(1, 0, 'Title', 'bookmark')}
            <div data-style="${args->title_block_style:html:default('margin-left: 1rem;'):input_type(css):arg_name(Block style):arg_section(1, 1, 'Title', 'bookmark')}">
                <a class="-s-t-title" ${args->link:default('href="" data-personyze-click-target=""'):input_type(a_attrs):arg_name(Link URL):arg_section(5, 0, 'Link URL', 'bookmark')} data-style="${args->title_style:html:default('line-height: 145%; background-color: white; color: #006ec7; border-top: 0.1rem solid white; border-bottom: 0.1rem solid white; box-shadow: 1rem 0.15rem white, 1rem -0.15rem white, -1rem 0.15rem white, -1rem -0.15rem white; font-weight: 200;'):input_type(css):arg_name(Style):arg_section(1, 3, 'Title', 'bookmark')}; text-decoration: none;">${args->title:default(Your title):arg_name(Text):arg_section(1, 2, 'Title', 'bookmark')}</a>
            </div>
            ${block->description:default(1):arg_name(With description):arg_section(2, 0, 'Description', 'bookmark')}
            <div data-style="${args->description_block_style:html:default('margin-left: 1rem;'):input_type(css):arg_name(Block style):arg_section(2, 1, 'Description', 'bookmark')}">
                <span class="-s-t-description" data-style="${args->description_style:html:default('line-height: 149%; background-color: white; color: #4C5157; border-top: 0.1rem solid white; border-bottom: 0.1rem solid white; box-shadow: 1rem 0.15rem white, 1rem -0.15rem white, -1rem 0.15rem white, -1rem -0.15rem white; font-weight: 200;'):input_type(css):arg_name(Style):arg_section(2, 3, 'Description', 'bookmark')}; text-decoration: none;">${args->description:default(Your description):arg_name(Text):arg_section(2, 2, 'Description', 'bookmark')}</span>
            </div>
            ${block->button:default(1):arg_name(With button):arg_section(3, 0, 'Button', 'text-height')}
            <a ${args->link} data-style="${args->button_style:html:default('display: inline-block;
margin-top: 4rem;
padding-top: 1rem;
padding-right: 2rem;
padding-bottom: 1rem;
padding-left: 2rem;
line-height: 2rem;
background-color: #006ec7;
color: white;
border-color: #006ec7;
border-radius: 0.5rem;
border-width: 0.2rem;
border-style: solid;
font-size: 1.6rem;
font-weight: normal;
letter-spacing: 0.1rem;
white-space: nowrap;'):input_type(css):arg_name(Style):arg_section(3, 2, 'Button', 'text-height')}; text-decoration: none;">${args->button_text:default(Buy it):arg_name(Text):arg_section(3, 1, 'Button', 'text-height')}
            </a>
            ${block->button2:default(1):arg_name(With button 2):arg_section(6, 0, 'Second button', 'text-height')}
            <a ${args->link2:default('href="" data-personyze-click-target=""'):input_type(a_attrs):arg_name(Link URL):arg_section(6, 3, 'Second button', 'text-height')}} data-style="${args->button2_style:html:default('display: inline-block;
margin-top: 4rem;
padding-top: 1rem;
padding-right: 2rem;
padding-bottom: 1rem;
padding-left: 2rem;
line-height: 2rem;
background-color: rgb(71, 123, 77);
color: white;
border-color: rgb(220, 229, 229);
border-radius: 0.5rem;
border-width: 0.2rem;
border-style: solid;
font-size: 1.6rem;
font-weight: normal;
letter-spacing: 0.1rem;
white-space: nowrap;'):input_type(css):arg_name(Style):arg_section(6, 2, 'Second button', 'text-height')}; text-decoration: none;">${args->button2_text:default(Buy it more):arg_name(Text):arg_section(6, 1, 'Second button', 'text-height')}
            </a>
        </div>
        ${block->image:default(1):arg_name(With image):arg_section(4, 0, 'Image', 'image')}
        <div class="-s-t-image">
            <a ${args->link} style="text-decoration: none;">
                <img data-src="${args->image_url:html:default('https://cdn.personyze.com/upload/362/7d0a26d42b6f9a72.jpeg'):input_type(personyze_media_url):arg_name(Image URL):arg_section(4, 1, 'Image', 'image')}" alt="cp2 promotional action product bboard en prod" data-style="${args->image_style:html:default('max-width: 100%; max-height: 28rem; box-sizing: box-content;'):input_type(css):arg_name(Style):arg_section(4, 2, 'Image', 'image')}">
            </a>
            <img data-src="${args->shadow_url:html:default('https://cdn.personyze.com/upload/4241/854f4b7eec00d6a3.png'):input_type(personyze_media_url):arg_name(Shadow image URL):arg_section(4, 3, 'Image', 'image')}" data-style="${args->shadow_style:html:default('opacity: 0.2; max-width: 80%;'):input_type(css):arg_name(Shadow style):arg_section(4, 4, 'Image', 'image')}">
        </div>
    </div>
</div>
```


## Responsive CTA: Top Image (Mobile), Side Image (Desktop)

Image Position Changes Based on Device

```
<div class="$responsive" data-style="position:relative; overflow:hidden; ${args->box_style:html:default('max-width: sel(100%, 100vw);
background-color: rgb(231, 233, 227);
width: 900px;
border-radius: 5px;
padding: 0px;')}">
	<style>
		@media (max-width: 768px)
		{	.ac${action_id:html} {flex-direction:column}
		}
	</style>
	<div class="ac${action_id:html}" style="display:flex; align-items:stretch">
		<div style="background-repeat:no-repeat; background-position:center; ${args->image_style:html:default('background-image: url(''https://cdn.personyze.com/upload/5971/99feeb36688f640a.png'');
background-color: rgba(256, 256, 256, 0);
background-size: contain;
padding: 0px;
margin: 20px;')}">
			<div data-style="width:${args->image_width:html:default(350px)}; height:${args->image_height:html:default(300px)}"></div>
		</div>
		<div style="padding:0 1em">
			<div data-style="max-height:${args->image_height:html}">
				<div data-style="outline:0; ${args->title_style:html:default('font-size: sel(30px, 22px);
font-weight: 700;
line-height: sel(32px, 35px);
text-align: center;
margin-top: 50px;
margin-right: 0px;
margin-bottom: 0px;
margin-left: 0px;
text-transform: uppercase;
width: sel(450px, auto);
max-width: 100%;
height: auto;
visibility: visible;')}">
					${args->title:default('<div style="text-align: center;">TITLE TITLE&nbsp;&nbsp;<br />
&nbsp;</div>
')}
				</div>
				<div data-style="outline:0; ${args->text_style:html:default('font-size: sel(22px, 17px);
font-weight: 300;
line-height: sel(25px, 20px);
text-align: center;
margin: 0px;
color: rgb(13, 7, 7);
width: sel(440px, auto);
height: auto;
display: block;
box-sizing: content-box;
float: none;')}">
					${args->text:default('TEXTTEXTTEXTTEXTTEXTTEXTTETE<br />
TEXTTEXTTEXTTEXTTEXTTEXTTETE<br />
TEXTTEXTTEXTTEXTTEXTTEXTTETE<br />
TEXTTEXTTEXTTEXTTEXTTEXTTETE')}
				</div>
				<div style="text-align:center; ${args->buttons_style:html:default('margin-top: 4em;
margin-right: 0;
margin-bottom: 2em;
margin-left: 0;')}">
					${block->show_button:default(1)}
					<a ${args->href:default('href=""')} data-style="${args->button_text_style:html:default('font-family: Arial;
font-size: sel(15px, 13px);
color: white;
text-decoration: none;
background-color: #f7941e;
padding-top: 15px;
padding-right: 20px;
padding-bottom: 15px;
padding-left: 20px;
border-radius: 2px;
font-weight: bolder;
width: 100%;')}">  ${args->button_t:default(GOT IT)}
					</a>

					${block->show_button_2:default(0)}
					<a ${args->href_3:default('href=""')} data-style="display:inline-block; ${args->button_text_style_2:html}">
						${args->button_t_2}
					</a>
				</div>
			</div>
		</div>
	</div>
	${block->show_close_button:default(1)}
	<div data-style="position:absolute; cursor:pointer; ${args->close_button_style:html:default('top: 8px;
right: 8px;
z-index: 9999;')}">
		${args->close_button:default('<div onmouseenter="this.style.backgroundColor=this.style.outlineColor" onmouseleave="this.style.backgroundColor=this.style.textDecorationColor" style="display: inline-block; vertical-align: text-bottom; width: 24px; height: 24px; box-sizing: border-box; border-top-left-radius: 50%; border-top-right-radius: 50%; border-bottom-right-radius: 50%; border-bottom-left-radius: 50%; border: 0px solid; -webkit-box-shadow: none; padding: 3px; background-color: rgba(207, 58, 58, 0); text-decoration-color: rgba(207, 58, 58, 0); outline-color: rgb(206, 54, 64); outline-width: 10px; color: rgb(10, 4, 4); cursor: pointer; transition: all 0.3s ease;" class="$personyze_button_dont_show_again" data-action_id="${action_id}"><div style="display: block; width: 100%; height: 100%; transition: all 0.3s ease 0s; border-top-left-radius: 50%; border-top-right-radius: 50%; border-bottom-right-radius: 50%; border-bottom-left-radius: 50%; background-image: linear-gradient(-45deg, transparent 0%, transparent 46%, currentcolor 46%, currentcolor 56%, transparent 56%, transparent 100%), linear-gradient(45deg, transparent 0%, transparent 46%, currentcolor 46%, currentcolor 56%, transparent 56%, transparent 100%);"></div></div>')}
	</div>
</div>

${menu name='Box', icon='th-large'}
	${menu args->box_style name='Box style', type='css', param='with_responsive=1'}
${menu name='Picture', icon='image'}
	${menu args->image_style name='Picture URL', type='css'}
	${menu args->image_width name='Image width', type='css_length', param='with_responsive=1'}
	${menu args->image_height name='Image height', type='css_length', param='with_responsive=1'}
${menu name='Content', icon='bars'}
	${menu args->title name='Title'}
	${menu args->title_style name='Title style', type='css', param='with_responsive=1'}
	${menu args->text name='Text'}
	${menu args->text_style name='Title style', type='css', param='with_responsive=1'}
${menu name='First Button', icon='hand-o-up'}
	${menu block->show_button name='Show button'}
	${menu args->button_t name='Text_button'}
	${menu args->href name='URL', type='a_attrs'}
	${menu args->button_text_style name='Button text style', type='css', param='with_responsive=1'}
	${menu args->buttons_style name='Buttons margin', type='css', param='with_responsive=1'}
${menu name='Second Button', icon='hand-o-up'}
	${menu block->show_button_2 name='Show second button'}
	${menu args->button_t_2 name='Text_button'}
	${menu args->href_3 name='URL', type='a_attrs'}
	${menu args->button_text_style_2 name='Button text style', type='css', param='with_responsive=1'}
${menu name='Close Button', icon='times-circle'}
	${menu block->show_close_button name='Show close button'}
	${menu args->close_button_style name='Close Button Style', type='css', param='with_responsive=1'}
	${menu args->close_button name='Close button', type='dontshowagain'}
```


## Image/banner with text layer

Simple banner with optional text and multiple buttons

```
<div class="$responsive" data-style="position:relative; box-sizing:border-box; ${args->style:html:default('margin: 0px;
text-align: center;
width: auto;
height: auto;
')}">
	<img src="${args->img_src:html:default('https://cdn.personyze.com/upload/362/6413c369509b8110.jpeg')}" data-style="display:block; width:auto; height:auto; ${args->img_style:html:default('max-width: 100%;
max-height: 300px;
object-fit: fill;
')}">

	${block->with_close_button:default(0)}
	<div data-style="position:absolute; z-index:1; cursor:pointer; ${args->close_button_style:html:default('text-align: right;
width: auto;
top: 10px;
right: 10px;
bottom: 0;
position: absolute;
left: 0px;
')}">
		${args->close_button:default('<div onmouseenter="this.style.backgroundColor=this.style.outlineColor" onmouseleave="this.style.backgroundColor=this.style.textDecorationColor" style="display: inline-block; vertical-align: text-bottom; width: 24px; height: 24px; box-sizing: border-box; border-radius: 50%; border: 2px solid; box-shadow: rgba(255, 255, 255, 0.2) 0px 1px 0px inset, rgba(0, 0, 0, 0.2) 0px 1px 2px; padding: 3px; background-color: rgb(207, 120, 58); text-decoration-color: rgb(207, 120, 58); outline-color: rgb(206, 54, 64); outline-width: 10px; color: rgb(10, 4, 4); cursor: pointer; transition: all 0.3s ease 0s;" class="$personyze_button_dont_show_again" data-action_id="${action_id}"><div style="display: block; width: 100%; height: 100%; transition: all 0.3s ease 0s; border-radius: 50%; background-image: linear-gradient(-45deg, transparent 0%, transparent 46%, currentcolor 46%, currentcolor 56%, transparent 56%, transparent 100%), linear-gradient(45deg, transparent 0%, transparent 46%, currentcolor 46%, currentcolor 56%, transparent 56%, transparent 100%);"></div></div>')}
	</div>

	<div style="position:absolute; top:0; left:0; width:100%; height:100%; display:flex; flex-direction:column-reverse">
		${block->with_button_1:default(0)}
		<div style="flex-shrink:0; display:flex; flex-wrap:wrap; justify-content:center; align-items:center">
			<a ${args->href:default('href="#"')}
				data-style="display:inline-block; ${args->button_text_style:html:default('margin: 2em;
padding-top: 0;
padding-right: 18px;
padding-bottom: 0;
padding-left: 18px;
font-size: 11px;
border: none;
border-radius: 5px;
letter-spacing: 2px;
color: #fff;
background-color: #F8BA31;
box-sizing: border-box;
height: 32px;
line-height: 32px;
font-weight: 700;
text-decoration: inherit;
')}">  ${args->button_t:default(TRY IT)}
			</a>

			${block->with_button_2}
			<a ${args->href_2:default('href="javascript:" class="$personyze_button_dont_show_again" data-action_id="${action_id}" data-n_sessions="0"')}
				data-style="display:inline-block; ${args->button_text_style_2:html:default('margin-top: 2em;
margin-right: 2em;
margin-bottom: 2em;
margin-left: 10px;
color: #fff;
font-size: 12px;
font-family: Poppins, Helvetica, Arial, sans-serif;
text-transform: none;
')}">
				${args->button_t_2:default(Not now)}
			</a>
		</div>
		${block->with_text:default(0)}
		<div data-style="flex-grow:1000; ${args->text_1_style:html:default('text-align: center;
')}">
			<div style="width:100%; height:100%; overflow:auto">
				<div data-style="${args->line_1_style:html:default('font-size: 28px;
color: white;
padding-top: 60px;
padding-right: 60px;
padding-bottom: 30px;
padding-left: 60px;
font-weight: bold;
')}">
					${args->line_1:default(TEXT TEXT)}
				</div>
				<div data-style="${args->line_2_style:html:default('font-size: 14px;
color: rgb(224, 215, 215);
padding-top: 0px;
padding-right: 0px;
padding-bottom: 30px;
padding-left: 0px;
font-weight: lighter;
text-align: center;
')}">
					${args->line_2:default(TEXT TEXT TEXT TEXT)}
				</div>
			</div>
		</div>
	</div>

	${block->with_banner_href:default(1)}
	<a ${args->banner_href:default('href=""')} style="position:absolute; display:block; left:0; top:0; width:100%; height:100%"></a>
</div>

${menu name='Image', icon='image'}
	${menu args->img_src name='Image URL', type='media_url'}
	${menu args->img_style name='Image style', type='css', param='with_responsive=1'}
	${menu args->style name='Box style', type='css', param='with_responsive=1'}
${menu name='Whole banner link', icon='external-link'}
	${menu block->with_banner_href name='Whole banner link', onchange='block.with_button_1 = block.with_button_1 && !block.with_banner_href; block.with_button_2 = block.with_button_2 && !block.with_banner_href'}
	${menu args->banner_href name='URL', type='a_attrs'}
${menu name='Text 1', icon='bars'}
	${menu block->with_text name='Show text'}
	${menu args->text_1_style name='Text 1 style', type='css', param='with_responsive=1'}
	${menu args->line_1 name='Text 1 line 1'}
	${menu args->line_1_style name='Text 1 style', type='css', param='with_responsive=1'}
	${menu args->line_2 name='Text 1 line 2'}
	${menu args->line_2_style name='Text 1 style', type='css', param='with_responsive=1'}
${menu name='Button', icon='hand-o-up'}
	${menu block->with_button_1 name='Show button', onchange='block.with_banner_href = block.with_banner_href && !block.with_button_1'}
	${menu args->button_t name='Text_button'}
	${menu args->href name='URL', type='a_attrs'}
	${menu args->button_text_style name='Button text style', type='css', param='with_responsive=1'}
${menu name='Second Button', icon='hand-o-up'}
	${menu block->with_button_2 name='Show second button', onchange='block.with_banner_href = block.with_banner_href && !block.with_button_1'}
	${menu args->button_t_2 name='Text_button'}
	${menu args->href_2 name='URL', type='a_attrs'}
	${menu args->button_text_style_2 name='Button text style', type='css', param='with_responsive=1'}
${menu name='Close Button', icon='times-circle'}
	${menu block->with_close_button name='Show close button'}
	${menu args->close_button_style name='Close_btn_Style', type='css', param='with_responsive=1'}
	${menu args->close_button name='Close button', type='dontshowagain'}
```


## Full-Screen Overlay

Full-Page promotion popup

```
<table class="$responsive" data-style="border-collapse:collapse; ${args->style:html:default('width: sel(100%, auto);
height: sel(100%, auto);
background-image: none;
background-size: contain;
background-color: white;
background-repeat: repeat;
display: table;
overflow: hidden;
min-width: 0;
')}">
	<tr>
		<td data-style="position:relative; ${args->style_2:html:default('background-color: rgb(253, 253, 253);
color: black;
text-align: center;
vertical-align: middle;
padding-top: 10%;
padding-right: sel(10%, 10px);
padding-bottom: 10%;
padding-left: sel(10%, 10px);
width: auto;
height: auto;
')}">
			<img src="${args->image_src:html:default('https://cdn.personyze.com/upload/362/705130cf0b17aa64.png')}" style="${args->image_style:html:default('width: auto;
height: auto;
border: none;
')}">
			<div>
				<div data-style="margin:${args->margin:html:default('sel(12px, 8px)')} 0; ${args->style_t1:html:default('color: rgb(9, 9, 9);
font-size: sel(25px, 5vw);
width: 100%;
')}">
					${args->text_1:default(Your Title Goes Here)}
				</div>
				<div data-style="margin:${args->margin:html} 0; ${args->style_t2:html:default('color: rgb(10, 6, 6);
font-size: sel(14px, 4vw);
')}">
					${args->text_2:default('Sub tile goes here Sub tile goes here Sub tile goes<br />
Sub tile goes here Sub tile goes here Sub tile goes<br />
Sub tile goes here Sub tile goes here Sub tile goes<br />
Sub tile goes here Sub tile goes here Sub tile goes<br />
Sub tile goes here Sub tile goes here Sub tile goes<br />
Sub tile goes here Sub tile goes here Sub tile goes<br />
&nbsp;')}
				</div>
				<div data-style="margin:${args->margin:html} 0">
					${block->with_button:default(1)}
					<a class="$flat_btn" with_responsive="1" data-style="display:inline-block; width:${args->button_width:html:default('sel(130px, 33vw)')}; height:${args->button_height:html:default(30px)}; line-height:${args->button_height:html}; ${args->yes_style:html:default('height: auto;
border: 5px solid rgb(6, 3, 3);
border-radius: 26px;
background-color: rgb(2, 2, 2);
margin-top: 20px;
margin-right: 1px;
margin-bottom: 1px;
margin-left: 1px;
padding-top: 10px;
padding-right: 30px;
padding-bottom: 10px;
padding-left: 30px;
color: rgb(251, 250, 250);
text-align: center;
font-size: 22px;
text-decoration: none;
font-weight: bold;
width: 130px;
text-transform: none;
font-family: sans-serif;
')}" hover_style="${args->yes_h_style:html:default('border: 5px solid rgb(237, 2, 13);
border-radius: 26px;
background-color: rgb(237, 2, 13);
')}" ${args->yes_attrs:default('href="" data-personyze-click-target=""')}>
						${args->yes_1:default(Button 1)}
					</a>

					${block->with_second_button:default(1)}
					<a class="$flat_btn $personyze_button_dont_show_again" with_responsive="1" data-action_id="${action_id:html}" data-style="display:inline-block; width:${args->button_width:html}; height:${args->button_height:html}; line-height:${args->button_height:html}; ${args->b2_style:html:default('height: auto;
border: 5px solid rgb(44, 203, 39);
border-radius: 26px;
background-color: rgb(44, 203, 39);
margin-top: 20px;
margin-right: 1px;
margin-bottom: 1px;
margin-left: 1px;
padding-top: 10px;
padding-right: 30px;
padding-bottom: 10px;
padding-left: 30px;
color: rgb(247, 246, 246);
text-align: center;
font-size: 22px;
text-decoration: none;
font-weight: bold;
width: 130px;
text-transform: none;
font-family: sans-serif;
')}" hover_style="${args->yes_h_style:html}" ${args->b2_attrs}>
						${args->b2_1:default(Button 2)}
					</a>
				</div>
			</div>

			${block->show_close_button:default(1)}
			<div data-style="position:absolute; cursor:pointer; ${args->close_button_style:html:default('top: 6px;
right: 6px;
')}">
				${args->close_button:default('<a href="javascript:" style="font-size: 72px; color: black; font-weight: 700; line-height: 1; text-decoration: none; position: absolute; top: 15px; right: 15px;" class="$personyze_button_dont_show_again" data-action_id="${action_id}">×</a>')}
			</div>
		</td>
	</tr>
</table>

${menu name='Box', icon='th-large'}
	${menu args->style name='Style', type='css', param='with_responsive=1'}
	${menu args->style_2 name='Style', type='css', param='with_responsive=1'}
	${menu args->margin name='Paragraph spacing', type='css_length', param='with_responsive=1'}
	${menu args->button_width name='Button Width', type='css_length', param='with_responsive=1'}
	${menu args->button_height name='Button Height', type='css_length', param='with_responsive=1'}
${menu name='Top Image', icon='image'}
	${menu args->image_src name='URL', type='personyze_media_url'}
	${menu args->image_style name='Image style', type='css', param='with_responsive=1'}
${menu name='Text', icon='bars'}
	${menu args->text_1 name='Line 1'}
	${menu args->style_t1 name='Style', type='css', param='with_responsive=1'}
	${menu args->text_2 name='Line 1'}
	${menu args->style_t2 name='Style', type='css', param='with_responsive=1'}
${menu name='Button', icon='bars'}
	${menu block->with_button name='Show Button'}
	${menu args->yes_1 name='Button 1 text'}
	${menu args->yes_attrs name='Button action', type='a_attrs'}
	${menu args->yes_style name='Button  Style', type='css'}
	${menu args->yes_h_style name='Button  Hover Style', type='css'}
${menu name='Button 2', icon='bars'}
	${menu block->with_second_button name='Show Button 2'}
	${menu args->b2_1 name='Button text'}
	${menu args->b2_attrs name='Button action', type='a_attrs'}
	${menu args->b2_style name='Button 2 Style', type='css'}
${menu name='Close Button', icon='times-circle'}
	${menu block->show_close_button name='Show close button'}
	${menu args->close_button_style name='Close Button Style', type='css', param='with_responsive=1'}
	${menu args->close_button name='Close button', type='dontshowagain'}
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
