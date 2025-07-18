## Form with 2 buttons



```
<div class="$responsive" data-style="position:relative; background-color:white; box-sizing:border-box; ${args->style:html:default('width:sel(500px, 90vw); padding:30px 40px')}" onupdate="var df=ns.joyquery('child::div', this).get(0).style, dl=ns.joyquery('child::div:last-child', this).get(0).style, fs=this.style; df.backgroundColor=fs.borderTopColor; df.border=fs.border; df.borderBottom='none'; df.borderTopLeftRadius=fs.borderTopLeftRadius; df.borderTopRightRadius=fs.borderTopRightRadius; dl.border=fs.border; dl.borderTop='none'; dl.borderBottomLeftRadius=fs.borderBottomLeftRadius; dl.borderBottomRightRadius=fs.borderBottomRightRadius; fs.borderRadius=0; fs.border='none'">
    <link href="https://fonts.googleapis.com/css?family=Fjalla+One" rel="stylesheet">
    ${block->show_close_button:default(1)}
    <div style="width:1px; vertical-align:middle" class="$copystyle" data-from="preceding-sibling::*" data-js="s.padding=fs.padding">
        ${args->close_button:default('<img src="http://counter.personyze.com/images/close-buttons/black-16x16.png" style="position:absolute; top:16px; right:16px; width:16px; height:16px;" class="$personyze_button_dont_show_again" data-action_id="${action_id}" data-n_sessions="0">')}
    </div>
    <div class="$switch-elem" data-case="a">
		<div data-case="a" class="$cform st_f" ontplsubmit="personyze.push(['Submit', '${action_id:html}', this._get_value_ex(), arguments[1], arguments[2]]); return true" ontplaftersubmit="this.parentNode._set_case('b', null, false, {template: 'animator_fade'}); var redir=this.dataset.redir, t=this.dataset.redirDelay; if (redir) setTimeout(function() {location.href=redir}, t*1000)" data-redir="${args->redir:html}" data-redir-delay="${args->redir_delay:html}" style="margin:8px 0 10px">
			<div data-style="vertical-align:middle; ${args->logo_style:html:default('text-align:center; padding:0 0 40px;')}">
				<img src="${args->logo_url:html:default('https://static.personyze.com/upload/362/2ced8f83fce5a056.png')}">
			</div>
			<div data-style="vertical-align:middle; ${args->message_style:html:default('color:black; text-align:center; font-family:Helvetica,san-serif; font-weight:normal; font-size:15px; padding:10px 0; letter-spacing:1px')}">
				${args->message_text:default('Don&#39;t miss out')}
			</div>
			<div data-style="vertical-align:middle; ${args->content_style:html:default('color:black; text-align:center; font-family:Fjalla One,san-serif; font-weight:normal; font-size:28px; line-height:38px; padding:10px 40px; text-transform:uppercase; letter-spacing:2px')}">
				${args->content_text:default('Exclusives, offers, and the latest from us')}
			</div>
			<div>
				<span data-style="${args->email_field_label_style:html:default('font-family:Helvetica,san-serif; font-weight:normal; font-size:13px')}">${args->email_field_label:default('Email Address*')}</span>
				<div style="margin-top:4px">
					<input form="st_f" name="email" data-prop-column="email" pattern="^[^\s@]+@[^\s@\.]+\.[^\s@]+$" required="1" placeholder="${args->email_field_placeholder:html:default(Email Address)}" data-style="${args->email_field_style:html:default('font-family: Helvetica,san-serif;
font-weight: normal;
font-size: 13px;
width: 100%;
height: 40px;
padding: 10px;
box-sizing: border-box;
border: 1px solid rgb(196,196,196);
border-radius: 3px;
color: rgb(162,162,162);')}">
				</div>
			</div>
			<div style="margin-top:20px; white-space:nowrap">
				<div style="display:inline-block; vertical-align:top; width:50%; box-sizing:border-box; padding-right:10px">
					<div class="$personyze_button_dont_show_again" data-action_id="${action_id:html}" data-n_sessions="0" data-style="box-sizing:border-box; ${args->cancel_button_style:html:default('font-family:Fjalla One,san-serif; font-weight:normal; font-size:13px; width:100%; height:40px; line-height:40px; text-align:center; text-transform:uppercase; border:1px solid black; border-radius:3px; background-color:white; color:black; padding:0')}">${args->cancel_button_label:default(No Thanks)}</div>
				</div><div style="display:inline-block; vertical-align:top; width:50%; box-sizing:border-box; padding-left:10px">
					<button form="st_f" type="submit" class="$flat_btn" data-style="display:inline-block; ${args->action_button_style:html:default('font-family:Fjalla One,san-serif; font-weight:normal; font-size:13px; width:100%; height:40px; line-height:40px; text-align:center; text-transform:uppercase; border:0; border-radius:3px; background-color:black; color:white; padding:0')}">
						${args->action_button_label:default(Sign Up)}
					</button>
				</div>
			</div>
		</div>
		<div data-case="b">
			${args->success:default(Thank you!)}
		</div>
	</div>
    <div data-style="${args->info_style:html:default('margin-top:55px; font-family:Helvetica,san-serif; font-weight:normal; font-size:11px; text-align:center; color:rgb(162,162,162)')}">${args->info_text:default('By signing up, you agree to our&nbsp;<a href="#" style="text-decoration:underline; cursor:pointer; color:inherit">Privacy Policy</a> and <a href="#" style="text-decoration:underline; cursor:pointer; color:inherit">Terms of Use</a>')}</div>
</div>

${menu name='Box', icon='th-large'}
	${menu args->style name='Style', type='css', param='with_responsive=1'}
${menu name='Logo', icon='image'}
	${menu args->logo_url name='URL', type='personyze_media_url'}
	${menu args->logo_style name='Style', type='css', param='with_responsive=1'}
${menu name='Call message', icon='bars'}
	${menu args->message_text name='Text'}
	${menu args->message_style name='Style', type='css', param='with_responsive=1'}
${menu name='Content', icon='bars'}
	${menu args->content_text name='Text'}
	${menu args->content_style name='Style', type='css', param='with_responsive=1'}
${menu name='Email field', icon='envelope'}
	${menu args->email_field_label name='Label'}
	${menu args->email_field_label_style name='Label style', type='css', param='with_responsive=1'}
	${menu args->email_field_placeholder name='Field placeholder'}
	${menu args->email_field_style name='Field style', type='css', param='with_responsive=1'}
${menu name='Info', icon='info'}
	${menu args->info_text name='Text'}
	${menu args->info_style name='Style', type='css', param='with_responsive=1'}
${menu name='Action button', icon='check'}
	${menu args->action_button_label name='Label'}
	${menu args->action_button_style name='Style', type='css', param='with_responsive=1'}
${menu name='After submit', icon='check'}
	${menu args->success name='Thank you text'}
	${menu args->redir name='After submit redirect to this URL'}
	${menu args->redir_delay name='Redirect delay, sec', type='number'}
${menu name='Cancel button', icon='close'}
	${menu args->cancel_button_label name='Label'}
	${menu args->cancel_button_style name='Style', type='css', param='with_responsive=1'}
${menu name='Close button', icon='close'}
	${menu block->show_close_button name='Show close button'}
	${menu args->close_button name='Close button', type='dontshowagain'}
```


## Coupon



```
<div class="$responsive" data-style="box-sizing: border-box;
position: relative;
overflow: hidden;
${args->style:html:default('width: 500px;
height: 250px;
background-color: #10bfd2;
border: 4px dashed white;
')}">

	${block->show_close_button:default(1)}
	<div data-style="position:absolute; cursor:pointer; ${args->close_button_style:html:default('top: 5px;
right: 5px;
z-index: 9999;
')}">
		${args->close_button:default('<div onmouseenter="this.style.backgroundColor=this.style.outlineColor" onmouseleave="this.style.backgroundColor=this.style.textDecorationColor" style="display: inline-block; vertical-align: text-bottom; width: 24px; height: 24px; box-sizing: border-box; border-radius: 50%; border: 0px solid; -webkit-box-shadow: none; padding: 2px; background-color: rgba(0, 0, 0, 0); text-decoration-color: rgba(0, 0, 0, 0); outline-color: rgb(206, 54, 64); outline-width: 15px; color: rgb(10, 4, 4); cursor: pointer; transition: 0.3s;" class="$personyze_button_dont_show_again" data-action_id="${action_id}"><div style="display: block; width: 100%; height: 100%; transition: 0.3s; border-radius: 50%; background-image: linear-gradient(-45deg, transparent 0%, transparent 43%, currentcolor 43%, currentcolor 59%, transparent 59%, transparent 100%), linear-gradient(45deg, transparent 0%, transparent 43%, currentcolor 43%, currentcolor 59%, transparent 59%, transparent 100%);"></div></div>')}
	</div>

	<div class="$switch-elem" data-case="a">
		<div data-case="a" class="$cform st_f" ontplsubmit="personyze.push(['Submit', '${action_id:html}', this._get_value_ex(), arguments[1], arguments[2]]); return true" ontplaftersubmit="this.parentNode._set_case('b', null, false, {template: 'animator_fade'}); var redir=this.dataset.redir, t=this.dataset.redirDelay; if (redir) setTimeout(function() {location.href=redir}, t*1000)" data-redir="${args->redir:html}" data-redir-delay="${args->redir_delay:html}" style="position:absolute; width:100%; height:100%">

			<div data-style="position: absolute;
			${args->title1_position:html:default('top: 5px;
width: 100%;
text-align: center;
')}">
				<span data-style="
				${args->title1_text_style:html:default('font-size: 14px;
color: white;
font-style: italic;
background-color: #06474d;
padding-top: 5px;
padding-right: 10px;
padding-bottom: 5px;
padding-left: 10px;
line-height: 2;
box-shadow: 3px 1px 4px 2px rgba(59,73,74,0.5);
')}">${args->title1:default(Want access to exclusive discounts)}</span>
			</div>

			<div data-style="position: absolute;
			width: 100%;
			${args->title_position:html:default('
			top: 35px;
			text-align: center')}">
				<div data-style="${args->title2_rotation:html:default('
				position: absolute;
				top: -10px;
				left: 10px;
				-moz-transform: rotate(-25deg);
				-ms-transform: rotate(-25deg);
				-webkit-transform: rotate(-25deg);
				-o-transform: rotate(-25deg);
				transform: rotate(-25deg)')}">
					<span data-style="font-weight: 600;
					font-style: normal;
					${args->title2_style:html:default('
					font-family: Lemonada, cursive;
					font-size: 30px;
					letter-spacing: 0;
					line-height: 1;
					color: white;
					text-shadow: 2px 2px 4px #000000')}">${args->title2:default(up to)}</span>
				</div>

				<span data-style="font-weight: 600;
				font-style: normal;
				${args->title3_style:html:default('
				font-size: 70px;
				letter-spacing: 10px;
				line-height: 1;
				font-family: Luckiest Guy, cursive;
				color: white;
				text-shadow: 2px 2px 4px #000000')}">${args->title3:default(70% off?)}</span>
			</div>


			<div data-style="position: absolute;
			${args->email_block_position:html:default('
			bottom: 10px;
			width: 100%;
			text-align: center')}">
				<span data-style="
				${args->email_block_text_style:html:default('
				color: #000;
				font-style: italic;
				font-size: 12px')}">${args->email_title1:default(Enter your email below to get access to these deals)}</span><br>
				<input form="st_f" name="email" data-prop-column="email" pattern="^[^\s@]+@[^\s@\.]+\.[^\s@]+$" required="1" placeholder="Enter your email here" data-style="
				outline: 0;
				border: none;
				padding: 5px 0;
				${args->email_input_style:html:default(' width: 400px;
				text-align: center;
				color:#0c0c0c')}">
				<div><input form="st_f" type="submit" value="${args->button_tex:html:default(i want crazy deals!)}"  data-style="cursor: pointer;
				outline:0;margin-top: 5px; padding: 15px;border: none;
				${args->button_style:html:default('
				font-size: 25px;
				width: 400px;
				background-color: #b80003;
				text-transform: uppercase;
				color: white')}"></div>
				<a href="javascript:" data-style="${args->button_not_action_style:html:default('color: white;
				font-style: italic;
				font-size: 12px;
				text-decoration: underline')}"
				class="$personyze_button_dont_show_again" data-action_id="${action_id:html}">
				${args->button_not_action_text:default('No thanks, I''d like paying full price')}
				</a>
			</div>

		</div>

		<div data-case="b">
			${args->success:default(Thank you!)}
		</div>
	</div>

	<link href="https://fonts.googleapis.com/css?family=Lemonada:600,700|Luckiest+Guy" rel="stylesheet">
</div>

${menu name='Box', icon='th-large'}
	${menu args->style name='Box style', type='css', param='with_responsive=1'}
${menu name='Title', icon='bookmark'}
	${menu args->title1 name='Text1'}
	${menu args->title1_position name='Title1 position', type='css', param='with_responsive=1'}
	${menu args->title1_text_style name='Title1 text style', type='css', param='with_responsive=1'}
${menu name='Title2', icon='bookmark'}
	${menu args->title2 name='Text2'}
	${menu args->title3 name='Text3'}
	${menu args->title3_style name='Title3 text style', type='css', param='with_responsive=1'}
	${menu args->title_position name='Title position', type='css', param='with_responsive=1'}
	${menu args->title2_rotation name='Title2 rotation', type='css', param='with_responsive=1'}
	${menu args->title2_style name='Title2 text style', type='css', param='with_responsive=1'}
${menu name='Email block', icon='envelope'}
	${menu args->email_title1 name='Title1'}
	${menu args->email_block_position name='Email block position', type='css', param='with_responsive=1'}
	${menu args->email_block_text_style name='Email block text style', type='css', param='with_responsive=1'}
	${menu args->email_input_style name='Email block text style', type='css', param='with_responsive=1'}
${menu name='Button', icon='hand-o-up'}
	${menu args->button_tex name='Text button'}
	${menu args->button_style name='Button style', type='css', param='with_responsive=1'}
	${menu args->button_not_action_style name='Button not action style', type='css', param='with_responsive=1'}
	${menu args->button_not_action_text name='Text'}
${menu name='Close Button', icon='times-circle'}
	${menu block->show_close_button name='Show close button'}
	${menu args->close_button_style name='Close Button Style', type='css', param='with_responsive=1'}
	${menu args->close_button name='Close button', type='dontshowagain'}
${menu name='After submit', icon='check'}
	${menu args->success name='Thank you text'}
	${menu args->redir name='After submit redirect to this URL'}
	${menu args->redir_delay name='Redirect delay, sec', type='number'}
```


## Form



```
<div class="$responsive" data-style="position:relative; background-image:url(${args->bgimage_url:html:default('https://www.abbotsfordchrysler.com/wp-content/uploads/2019/04/AC-RAM1500-Features-ComfortDriving.jpg')}); overflow:hidden; ${args->style:html:default('width: sel(600px, 90vw);
background-size: cover;
background-position: center;
background-repeat: no-repeat;
box-sizing: border-box;
border: 1px solid #a6a6a6;
border-radius: 4px;
background-color: rgba(0, 0, 0, 0.7);')}">
    <link href="https://fonts.googleapis.com/css?family=Montserrat:400,700|Open+Sans:400,600" rel="stylesheet">
    ${block->show_close_button:default(1)}
    <div style="position:absolute; top:16px; right:16px; z-index:2">
        ${args->close_button:default('<img src="https://counter.personyze.com/images/close-buttons/rect-white-orange-16x16.png" style="width:16px; height:16px" class="$personyze_button_dont_show_again" data-action_id="${action_id}" data-n_sessions="0">')}
    </div>
     <div class="$switch-elem" data-case="a" data-style="width:100%; height:100%; box-sizing:border-box; ${args->shading_style:html:default('background-color: rgba(0, 0, 0, 0.07);')}; ${args->send_confirm_style:html:default('padding:30px; font-family:Open Sans,san-serif; font-weight:normal; font-size:sel(18px, 14px); color:white; text-align:center')}">
		<div data-case="a" class="$cform st_f" ontplsubmit="personyze.push(['Submit', '${action_id:html}', this._get_value_ex(), arguments[1], arguments[2]]); return true" ontplaftersubmit="this.parentNode._set_case('b', null, false, {template: 'animator_fade'}); var redir=this.dataset.redir, t=this.dataset.redirDelay; if (redir) setTimeout(function() {location.href=redir}, t*1000)" data-redir="${args->redir:html}" data-redir-delay="${args->redir_delay:html}" style="position:relative; width:100%; height:100%">
            <div data-style="${args->message_style:html:default('color: white;
font-family: Montserrat,san-serif;
font-weight: 700;
font-size: sel(40px, 22px);
line-height: 1;
text-align: left;')}">
                ${args->message_text:default(Title)}
            </div>
            <div data-style="${args->gift_style:html:default('margin-top: 8px;
color: white;
font-family: Montserrat,san-serif;
font-weight: 900;
font-size: sel(18px, 14px);
line-height: 1.25;
text-align: left;')}">
                ${args->gift_text:default(Sub Title)}
            </div>
            <div>
                <div data-style="${args->content_style:html:default('margin-bottom: 14px;
color: white;
font-family: Open Sans,san-serif;
font-weight: 800;
font-size: sel(12px, 14px);
line-height: 1.25;
text-align: left;')}">
                    ${args->content_text}
                </div>

                <div data-style="${args->style7:html:default('text-align: center;
font-size: 18px;')}">
					${block->with_f2:default(1)}
					<div>
						<input form="st_f" name="Name" required="1" data-prop-column="${args->f2_db:html:default(first_name)}" data-style="box-sizing:border-box; ${args->f1_style:html:default('margin-bottom:20px; padding:10px; font-family:Open Sans,san-serif; font-weight:600; font-size:selsel(20px, 5vw); width:100%; border:1px solid rgb(62,62,62); border-radius:4px; color:rgb(122,122,122); text-align:left')}" placeholder="${args->f2:html:default(Name)}">
					</div>
					${block->with_f6:default(1)}
					<div>
						<input form="st_f" name="Phone" type="tel" required="${args->f6_req:html:default(1)}" data-prop-column="${args->f6_db:html}" data-style="box-sizing:border-box; ${args->f1_style:html}" placeholder="${args->f6:html:default(Telephone)}">
					</div>
					<div>
						<input form="st_f" name="Email" pattern="^[^\s@]+@[^\s@\.]+\.[^\s@]+$" required="1" data-prop-column="${args->f3_db:html:default(email)}" data-style="box-sizing:border-box; ${args->f1_style:html}" placeholder="${args->f3:html:default(E-Mail)}">
					</div>
					${block->with_f5:default(0)}
					<div>
						<textarea form="st_f" name="Details" data-style="box-sizing:border-box; ${args->f5_style:html}" placeholder="${args->f5:html}"></textarea>
					</div>
					${block->with_f4:default(0)}
					<div data-style="${args->style9:html}">
						<label>
							<input form="st_f" name="Checkbox" type="checkbox" data-prop-column="${args->f4_db:html}" value="1">
							${args->text_9}
						</label>
					</div>
				</div>

                <button form="st_f" type="submit" class="$flat_btn" with_responsive="1" style="display:block; border:0; white-space:normal; box-sizing:border-box; ${args->button_style:html:default('display:block; padding:8px 32px; font-family:Open Sans,san-serif; font-weight:normal; font-size:sel(18px, 14px); width:100%; min-height:44px; background-color:#5492dd; color:white; border-bottom:2px solid #3f75bd; border-radius:4px; text-transform:uppercase')}" hover_style="${args->button_h_style:html:default('background-color: #FFFFFF;
border-color: #5492dd;
color: #5492dd;')}">
					${args->button_caption:default(CONTACT ME)}
                </button>
            </div>
        </div>
		<div data-case="b">
			${args->success:default('<div style="text-align: center; font-size:30px ;">Thank you! We will schedule you in.</div>
')}
		</div>
    </div>

    ${args->footer:default('<p style="color: #ffffff; padding: 35px; text-size: 10px;">We will try to meet your preferred date and time. We are GDPR compliant and will not spam you. By clicking the above button, you agree to our <a data-saferedirecturl="https://www.google.com/url?q=https://www.abbotsfordchrysler.com/privacy-policy/&amp;source=gmail&amp;ust=1559168237409000&amp;usg=AFQjCNHZwC-vxhrIxYb-rjytZTwobPcUrA" href="https://www.abbotsfordchrysler.com/privacy-policy/" style="color:#fff;" target="_blank"><b>Privacy Policy</b></a>.</p>
')}

</div>

${menu name='Box', icon='th-large'}
	${menu args->style name='Style', type='css', param='with_responsive=1'}
	${menu args->bgimage_url name='URL', type='personyze_media_url'}
	${menu args->shading_style name='Shading', type='css', param='with_responsive=1'}
	${menu args->style7 name='Fields area Style', type='css', param='with_responsive=1'}
${menu name='Call message', icon='bars'}
	${menu args->message_text name='Text'}
	${menu args->message_style name='Style', type='css', param='with_responsive=1'}
${menu name='Gift', icon='gift'}
	${menu args->gift_text name='Text'}
	${menu args->gift_style name='Style', type='css', param='with_responsive=1'}
${menu name='Info', icon='bars'}
	${menu args->content_text name='Text'}
	${menu args->content_style name='Style', type='css', param='with_responsive=1'}
${menu name='Close button', icon='close'}
	${menu block->show_close_button name='Show close button'}
	${menu args->close_button name='Close button', type='dontshowagain'}
${menu name='Name Box', icon='edit'}
	${menu block->with_f2 name='With Name'}
	${menu args->f2_db name='Name save to database', type='select_social', param='with_empty=1'}
	${menu args->f2 name='Name Placeholder Text'}
	${menu args->f1_style name='Input style', type='css', param='with_responsive=1'}
${menu name='Telephone Box', icon='edit'}
	${menu block->with_f6 name='With Telephone'}
	${menu args->f6_db name='Telephone save to database', type='select_social', param='with_empty=1'}
	${menu args->f6_req name='Telephone is required field', type='checkbox', param='value_on=1', param='value_off='}
	${menu args->f6 name='Telephone Placeholder Text'}
${menu name='Email Box', icon='envelope'}
	${menu args->f3_db name='Email save to database', type='select_social', param='with_empty=1'}
	${menu args->f3 name='Email Placeholder Text'}
	${menu args->send_confirm_style name='Confirmation style', type='css', param='with_responsive=1'}
${menu name='Details Box', icon='edit'}
	${menu block->with_f5 name='With Details'}
	${menu args->f5 name='Details Placeholder Text'}
	${menu args->f5_style name='Input style', type='css', param='with_responsive=1'}
${menu name='Checkbox', icon='edit'}
	${menu block->with_f4 name='With Checkbox'}
	${menu args->style9 name='Checkbox Style', type='css', param='with_responsive=1'}
	${menu args->f4_db name='Checkbox save to database', type='select_social', param='with_empty=1'}
	${menu args->text_9 name='Text'}
${menu name='Action button', icon='check'}
	${menu args->button_caption name='Caption'}
	${menu args->button_style name='Style', type='css'}
	${menu args->button_h_style name='Hover Style', type='css'}
${menu name='After submit', icon='check'}
	${menu args->success name='Thank you text'}
	${menu args->redir name='After submit redirect to this URL'}
	${menu args->redir_delay name='Redirect delay, sec', type='number'}
${menu name='Footer', icon='bars'}
	${menu args->footer name='Footer'}
```


## Form survey



```
<div class="$responsive" data-style="position:relative; background-image:url(${args->bgimage_url:html:default('https://cdn.personyze.com/upload/362/73175c19db520d5f.png')}); ${args->style:html:default('width: sel(500px, auto);
background-position: bottom;
background-repeat: no-repeat;
background-color: white;
padding: 30px;
border-radius: 10px;
background-image: url(''https://cdn.personyze.com/upload/362/73175c19db520d5f.png'');
')}">
	${block->show_close_button:default(1)}
	<div style="position:absolute; top:16px; right:16px; z-index:1">
		${args->close_button:default('<a href="javascript:" style="font-size: 24px; color: rgba(0, 0, 0, 0.39); font-weight: bold; line-height: 1; text-decoration: none;" class="$personyze_button_dont_show_again" data-action_id="${action_id}">×</a>')}
	</div>
	<div class="$switch-elem" data-case="a">
		<div data-case="a" class="$cform st_f" ontplsubmit="personyze.push(['Submit', '${action_id:html}', this._get_value_ex(), arguments[1], arguments[2]]); return true" ontplaftersubmit="this.parentNode._set_case('b', null, false, {template: 'animator_fade'}); var redir=this.dataset.redir, t=this.dataset.redirDelay; if (redir) setTimeout(function() {location.href=redir}, t*1000)" data-redir="${args->redir:html}" data-redir-delay="${args->redir_delay:html}">
			<div data-style="${args->title_style:html:default('padding-top: 1em;
padding-right: 0.5em;
padding-bottom: 1em;
padding-left: 0.5em;
font-family: Helvetica,san-serif;
font-size: sel(18px, 16px);
color: rgba(0, 0, 0, 0.89);')}">${args->title_text:default('<div style="text-align: center;"><span style="font-size:22px;">Tell us how we can improve?</span></div>
')}</div>

			${block->with_rating:default(1)}
			<div data-style="${args->rating_style:html:default('font-size: 22px;
padding: 10;
margin-top: 1px;
margin-right: 1px;
margin-bottom: 13px;
margin-left: 1px;
color: rgb(214, 225, 221);')}">
				<input form="st_f" name="rating" type="hidden" value="0" data-prop-column="${args->rating_db:html:default(account_lifetime_value)}">
				<span class="$repeat-elem" data-length="5">
					<b onmouseover="var p = this.parentNode, c = Array.prototype.slice.call(p.parentNode.children); i = c.indexOf(p); c.map(function (item, j) { if (j) item.style.color = i >= j ? '${args->check_star_color:html:default('#ffe085')}' : 'inherit' });" onclick="var p = this.parentNode; p.parentNode.children[0].value = Array.prototype.indexOf.call(p.parentNode.children, p);" onmouseout="var p = this.parentNode.parentNode.children, c = Array.prototype.slice.call(p); i = p[0].value; c.map(function (item, j) { if (j) item.style.color = i >= j ? '${args->check_star_color:html}' : 'inherit' });" style="cursor:pointer">${args->star:default('★')}</b>
				</span>
			</div>

			${block->with_email:default(1)}
			<div data-style="${args->email_place:html:default('margin-top: 0px;
margin-right: 0px;
margin-bottom: 0.6em;
margin-left: 0px;')}">
				<input form="st_f" name="Email" pattern="^[^\s@]+@[^\s@\.]+\.[^\s@]+|$" ${args->email_req:default('required="1"')} data-prop-column="${args->email_db:html:default(email)}" data-style="box-sizing:border-box; ${args->input_style:html:default('padding: 15px;
font-family: Open Sans,san-serif;
font-weight: 300;
font-size: 14px;
width: 100%;
border: 1px solid rgb(62,62,62);
border-radius: 4px;
color: rgb(122,122,122);
text-align: left;
background-color: rgba(249, 247, 247, 0.8);
')}" placeholder="${args->email:html:default(Enter your email address)}" value="${email:html}" ontplready="this.value=this.value.trim()">
			</div>

			${block->with_textarea:default(1)}
			<div data-style="${args->textarea_place:html}">
				<textarea form="st_f" name="feedback" ${args->textarea_req:default('required="1"')} rows="${args->textarea_rows:html:default(5)}" data-style="max-width:100%; box-sizing:border-box; ${args->input_style:html}; ${args->textarea_style:html}" placeholder="${args->textarea_placeholder:html:default(How can we improve?)}" data-prop-column="${args->feedback_db:html:default(account_lifetime_value)}"></textarea>
			</div>
			<div style="display:flex; align-items:center; ${args->button_box_style:html:default('justify-content: center;
')}">
				<button class="$flat_btn" with_responsive="1" data-style="${args->cancel_style:html:default('margin:1em; padding:.5em 1em; font-family:Helvetica,san-serif; font-size:12px; background-color:white; color:gray; border:none')}" hover_style="${args->cancel_h_style:html:default('background-color:gray; color:white')}" onclick="_S_T.dismiss_action(${action_id:html});">${args->cancel_text:default(Cancel)}</button>
				<button form="st_f" type="submit" class="$flat_btn" with_responsive="1" data-style="${args->submit_style:html:default('margin:1em; padding-top: .5em;
padding-right: 1em;
padding-bottom: .5em;
padding-left: 1em;
font-family: Helvetica,san-serif;
font-size: 12px;
background-color: #12ae64;
color: white;
border: none;')}" hover_style="${args->submit_h_style:html:default('background-color:#189110; color:white')}">${args->submit_text:default(Submit)}</button>
			</div>
		</div>
		<div data-case="b">
			<div data-style="${args->after_submit_style:html:default('padding:1em; font-family:Helvetica,san-serif; font-size:sel(18px, 16px); text-align:center; color:black')}">
				${args->success:default(Thank you!)}
			</div>
		</div>
	</div>
</div>

${menu name='Box', icon='th-large'}
	${menu args->style name='Style', type='css', param='with_responsive=1'}
	${menu args->bgimage_url name='URL', type='personyze_media_url'}
	${menu args->button_box_style name='Style', type='css', param='with_responsive=1'}
	${menu args->input_style name='Input style', type='css', param='with_responsive=1'}
${menu name='Title', icon='bars'}
	${menu args->title_text name='Text'}
	${menu args->title_style name='Style', type='css', param='with_responsive=1'}
${menu name='Rating', icon='star'}
	${menu block->with_rating name='With Rating'}
	${menu args->rating_db name='Rating save to database', type='select_social', param='with_empty=1'}
	${menu args->rating_style name='Style', type='css', param='with_responsive=1'}
	${menu args->check_star_color name='Check star color', type='color'}
	${menu args->star name='Star Glyph'}
${menu name='Email Box', icon='envelope'}
	${menu block->with_email name='With Email Box'}
	${menu args->email_db name='Email save to database', type='select_social', param='with_empty=1'}
	${menu args->email name='Email Placeholder Text'}
	${menu args->email_place name='Placement', type='css', param='with_responsive=1'}
	${menu args->email_req name='Email is required field', type='checkbox', param='value_on=required="1"', param='value_off='}
${menu name='Text area', icon='bars'}
	${menu block->with_textarea name='With Textarea'}
	${menu args->feedback_db name='Feedback save to database', type='select_social', param='with_empty=1'}
	${menu args->textarea_placeholder name='Placeholder'}
	${menu args->textarea_rows name='Rows', type='number'}
	${menu args->textarea_place name='Placement', type='css', param='with_responsive=1'}
	${menu args->textarea_style name='Style', type='css', param='with_responsive=1'}
	${menu args->textarea_req name='Textarea is required field', type='checkbox', param='value_on=required="1"', param='value_off='}
${menu name='Submit button', icon='check'}
	${menu args->submit_text name='Text'}
	${menu args->submit_style name='Style', type='css', param='with_responsive=1'}
	${menu args->submit_h_style name='Hover Style', type='css'}
${menu name='After submit', icon='check'}
	${menu args->success name='Thank you text'}
	${menu args->after_submit_style name='Style', type='css', param='with_responsive=1'}
	${menu args->redir name='After submit redirect to this URL'}
	${menu args->redir_delay name='Redirect delay, sec', type='number'}
${menu name='Cancel button', icon='times'}
	${menu args->cancel_text name='Text'}
	${menu args->cancel_style name='Style', type='css', param='with_responsive=1'}
	${menu args->cancel_h_style name='Hover Style', type='css'}
${menu name='Close button', icon='close'}
	${menu block->show_close_button name='Show close button'}
	${menu args->close_button name='Close button', type='dontshowagain'}
```


## Form



```
<div class="$responsive" data-style="position:relative; background-image:url(${args->bgimage_url:html}); overflow:hidden; ${args->style:html:default('border-radius: 3px;
box-shadow: 0 0 7px 5px rgba(189, 148, 148, 0.7);
width: 500px;
color: rgba(3, 1, 1, 0.9);
')}">
    <link href="https://fonts.googleapis.com/css?family=Montserrat:400,700|Open+Sans:400,600" rel="stylesheet">
    ${block->show_close_button:default(1)}
    <div style="position:absolute; top:16px; right:16px; z-index:2">
        ${args->close_button:default('<div onmouseenter="this.style.backgroundColor=this.style.outlineColor" onmouseleave="this.style.backgroundColor=this.style.textDecorationColor" style="display: inline-block; vertical-align: text-bottom; width: 24px; height: 24px; box-sizing: border-box; border-top-left-radius: 50%; border-top-right-radius: 50%; border-bottom-right-radius: 50%; border-bottom-left-radius: 50%; border: 2px solid; -webkit-box-shadow: rgba(255, 255, 255, 0.2) 0px 1px 0px inset, rgba(0, 0, 0, 0.2) 0px 1px 2px; padding: 3px; background-color: rgb(207, 120, 58); text-decoration-color: rgb(207, 120, 58); outline-color: rgb(206, 54, 64); outline-width: 10px; color: rgb(10, 4, 4); cursor: pointer; transition: all 0.3s ease;" class="$personyze_button_dont_show_again" data-action_id="${action_id}"><div style="display: block; width: auto; height: 100%; transition: all 0.3s ease 0s; border-top-left-radius: 50%; border-top-right-radius: 50%; border-bottom-right-radius: 50%; border-bottom-left-radius: 50%; background-image: linear-gradient(-45deg, transparent 0%, transparent 46%, currentcolor 46%, currentcolor 56%, transparent 56%, transparent 100%), linear-gradient(45deg, transparent 0%, transparent 46%, currentcolor 46%, currentcolor 56%, transparent 56%, transparent 100%);"></div></div>')}
    </div>
	<style data-pc="${args->pc:html:default('rgb(127, 130, 154)')}" ontplready="var v=['::-webkit-input-placeholder', '::-moz-placeholder', ':-moz-placeholder', ':-ms-input-placeholder'], t='', i; for (i=0; i&lt;v.length; i++) t += '.st_sw '+v[i]+' {color: '+this.dataset.pc+' !important}'; if (this.styleSheet) this.styleSheet.cssText = t; else this.textContent = t;"></style>
     <div class="$switch-elem st_sw" id="st_sw" data-case="a" data-style="width:auto; height:auto; box-sizing:border-box; ${args->shading_style:html:default('background-color: rgb(256, 256, 256);
width: auto;
height: auto;
')}; ${args->send_confirm_style:html:default('padding-top: 30px;
padding-right: sel(30px, 1vw);
padding-bottom: 30px;
padding-left: sel(30px, 1vw);
font-family: Open Sans,san-serif;
font-weight: normal;
font-size: sel(18px, 14px);
color: rgb(42, 24, 24);
text-align: center;
')}">
		<div
			data-case="a"
			class="$cform st_f"
			ontplsubmit="personyze.push(['Submit', ${action_id:json:html}, this._get_value_ex(), arguments[1], arguments[2]]); return true"
			ontplaftersubmit="var sw=this.parentNode; sw._set_case('b', null, false, {template: 'animator_fade'}); var js=this.dataset.customJs, redir=this.dataset.redir, t=this.dataset.redirDelay; if (js.trim()) new Function('action_id', 'by_id', 'data', 'report_error', js).call(this, ${action_id:json:html}, by_id, this._get_value()); if (redir) setTimeout(function() {location.href=redir}, t*1000)"
			data-custom-js="${args->customjs:html}"
			data-redir="${args->redir:html}"
			data-redir-delay="${args->redir_delay:html}"
			data-required_field_message="${args->required_field_message:html:default(Please fill out this field)}"
			data-invalid_value_message="${args->invalid_value_message:html:default(Invalid value for this input)}"
			style="position:relative; width:auto; height:auto"
		>
            <div data-style="${args->message_style:html:default('color: rgb(16, 9, 9);
font-family: Montserrat,san-serif;
font-weight: normal;
font-size: sel(24px, 22px);
line-height: 1;
text-align: left;')}">
                ${args->message_text}
            </div>
            <div id="st_m" data-style="${args->gift_style:html:default('margin-top: 8px;
color: rgb(9, 5, 5);
font-family: Montserrat,san-serif;
font-weight: 600;
font-size: 20px;
line-height: 1.55;
text-align: left;
')}">
                ${args->gift_text:default(Title)}
            </div>
            <div>
                <div data-style="${args->content_style:html:default('color: rgb(6, 3, 3);
font-family: Open Sans,san-serif;
font-weight: 400;
font-size: 14px;
text-align: left;
padding-top: 15px;
padding-right: 1px;
padding-bottom: 19px;
padding-left: 1px;
line-height: 24px;
width: auto;
')}">
                    ${args->content_text:default(Sub title)}
                </div>

                <div data-style="${args->style7:html:default('text-align: left;
font-size: 18px;
color: rgb(9, 5, 5);
')}">
					${block->with_f2:default(1)}
					<div>
						<input form="st_f" name="Name" required="1" data-prop-column="${args->f2_db:html:default(first_name)}" data-style="box-sizing:border-box; ${args->f1_style:html:default('margin-bottom: 20px;
padding: 15px;
font-family: Open Sans,san-serif;
font-weight: 300;
font-size: 14px;
width: sel(400px, 85%);
border: 1px solid rgb(62,62,62);
border-radius: 4px;
color: rgb(13, 7, 7);
text-align: left;
background-color: rgba(253, 253, 253, 0);
height: 40px;
')}" placeholder="${args->f2:html:default(Name)}">
					</div>
					${block->with_f6:default(0)}
					<div>
						<input form="st_f" name="Phone" type="tel" required="${args->f6_req:html}" data-prop-column="${args->f6_db:html}" data-style="box-sizing:border-box; ${args->f1_style:html}" placeholder="${args->f6:html}">
					</div>
					<div>
						<input form="st_f" name="Email" pattern="^[^\s@]+@[^\s@\.]+\.[^\s@]+$" required="1" data-prop-column="${args->f3_db:html:default(email)}" data-style="box-sizing:border-box; ${args->f1_style:html}" placeholder="${args->f3:html:default(E-mail)}" value="${email:html}" ontplready="this.value=this.value.trim()">
					</div>
					${block->with_f7:default(1)}
					<div>
						<input form="st_f" name="Line2" required="${args->f7_req:html}" data-prop-column="${args->f7_db:html:default(phone)}" data-style="box-sizing:border-box; ${args->f1_style:html}" placeholder="${args->f7:html:default(Phone)}">
					</div>
					${block->with_f8:default(1)}
					<div>
						<input form="st_f" name="Line3" required="${args->f8_req:html}" data-prop-column="${args->f8_db:html}" data-style="box-sizing:border-box; ${args->f1_style:html}" placeholder="${args->f8:html:default(Company)}">
					</div>
					${block->with_f9:default(0)}
					<div>
						<select form="st_f" name="Dropdown" required="${args->f9_req:html}" data-prop-column="${args->f9_db:html}" data-style="box-sizing:border-box; ${args->f1_style:html}">
							${args->f9_options}
						</select>
					</div>
					${block->with_f5:default(0)}
					<div>
						<textarea form="st_f" name="Details" data-style="box-sizing:border-box; ${args->f5_style:html}" placeholder="${args->f5:html}"></textarea>
					</div>
					${block->with_f4:default(0)}
					<div data-style="${args->style9:html:default('color: rgb(9, 5, 5);
font-size: 12px;
text-align: left;')}">
						<label>
							<input form="st_f" name="Checkbox" type="checkbox" data-prop-column="${args->f4_db:html}" value="1">
							${args->text_9}
						</label>
					</div>
				</div>

                <button form="st_f" type="submit" class="$flat_btn" with_responsive="1" style="display:block; border:0; white-space:normal; box-sizing:border-box; ${args->button_style:html:default('display: block;
padding-top: 12px;
padding-right: 20px;
padding-bottom: 12px;
padding-left: 20px;
font-family: Open Sans,san-serif;
background-color: #FF6300;
color: rgb(238, 232, 232);
border-radius: 50px;
text-transform: uppercase;
letter-spacing: 2px;
height: 45px;
width: 220px;
margin-top: 10px;
margin-right: auto;
margin-bottom: 40px;
margin-left: auto;
')}" hover_style="${args->button_h_style:html:default('display: block;
padding-top: 15px;
padding-right: 35px;
padding-bottom: 15px;
padding-left: 35px;
font-family: Open Sans,san-serif;
background-color: #111111;
color: #FFFFFF;
border-radius: 50px;
text-transform: uppercase;
letter-spacing: 2px;
')}">
					${args->button_caption:default(Submit)}
                </button>
            </div>
			<div data-style="${args->style9:html}">
				${args->ds:default(Free text)}
			</div>
        </div>
		<div data-case="b" id="st_b" data-style="${args->style10:html:default('color: rgb(199, 179, 179);')}">
			${args->success:default('<div style="text-align: center; font-size: 30px; ">Awesome! We Will Keep You Posted.</div>
')}
		</div>
    </div>
</div>

${menu name='Box', icon='th-large'}
	${menu args->style name='Style', type='css', param='with_responsive=1'}
	${menu args->bgimage_url name='URL', type='personyze_media_url'}
	${menu args->shading_style name='Shading', type='css', param='with_responsive=1'}
	${menu args->style7 name='Fields area Style', type='css', param='with_responsive=1'}
${menu name='Call message', icon='bars'}
	${menu args->message_text name='Text'}
	${menu args->message_style name='Style', type='css', param='with_responsive=1'}
${menu name='Gift', icon='gift'}
	${menu args->gift_text name='Text'}
	${menu args->gift_style name='Style', type='css', param='with_responsive=1'}
	${menu args->ds name='No text'}
${menu name='Info', icon='bars'}
	${menu args->content_text name='Text'}
	${menu args->content_style name='Style', type='css', param='with_responsive=1'}
${menu name='Close button', icon='close'}
	${menu block->show_close_button name='Show close button'}
	${menu args->close_button name='Close button', type='dontshowagain'}
${menu name='Name Box', icon='edit'}
	${menu block->with_f2 name='With Name'}
	${menu args->f2_db name='Name save to database', type='select_social', param='with_empty=1'}
	${menu args->f2 name='Name Placeholder Text'}
	${menu args->pc name='Input placeholder color', type='color'}
	${menu args->f1_style name='Input style', type='css', param='with_responsive=1'}
${menu name='Telephone Box', icon='edit'}
	${menu block->with_f6 name='With Telephone'}
	${menu args->f6_db name='Telephone save to database', type='select_social', param='with_empty=1'}
	${menu args->f6_req name='Telephone is required field', type='checkbox'}
	${menu args->f6 name='Telephone Placeholder Text'}
${menu name='Email Box', icon='envelope'}
	${menu args->f3_db name='Email save to database', type='select_social', param='with_empty=1'}
	${menu args->f3 name='Email Placeholder Text'}
	${menu args->send_confirm_style name='Confirmation style', type='css', param='with_responsive=1'}
${menu name='Line 2 Box', icon='edit'}
	${menu block->with_f7 name='With Line 2'}
	${menu args->f7_db name='Line 2 save to database', type='select_social', param='with_empty=1'}
	${menu args->f7_req name='Line 2 is required field', type='checkbox'}
	${menu args->f7 name='Line 2 Placeholder Text'}
${menu name='Line 3 Box', icon='edit'}
	${menu block->with_f8 name='With Line 3'}
	${menu args->f8_db name='Line 3 save to database', type='select_social', param='with_empty=1'}
	${menu args->f8_req name='Line 3 is required field', type='checkbox'}
	${menu args->f8 name='Line 3 Placeholder Text'}
${menu name='Dropdown List Box', icon='edit'}
	${menu block->with_f9 name='With Dropdown List'}
	${menu args->f9_db name='Dropdown List save to database', type='select_social', param='with_empty=1'}
	${menu args->f9_req name='Dropdown List is required field', type='checkbox'}
	${menu args->f9_options name='Options', type='select_options'}
${menu name='Details Box', icon='edit'}
	${menu block->with_f5 name='With Details'}
	${menu args->f5 name='Details Placeholder Text'}
	${menu args->f5_style name='Input style', type='css', param='with_responsive=1'}
${menu name='Checkbox', icon='edit'}
	${menu block->with_f4 name='With Checkbox'}
	${menu args->style9 name='Checkbox Style', type='css', param='with_responsive=1'}
	${menu args->f4_db name='Checkbox save to database', type='select_social', param='with_empty=1'}
	${menu args->text_9 name='Text'}
${menu name='Action button', icon='check'}
	${menu args->button_caption name='Caption'}
	${menu args->button_style name='Style', type='css'}
	${menu args->button_h_style name='Hover Style', type='css'}
${menu name='After submit', icon='check'}
	${menu args->success name='Thank you text'}
	${menu args->customjs name='After submit execute this JavaScript', type='textarea'}
	${menu args->style10 name='Thank you text Style', type='css', param='with_responsive=1'}
	${menu args->redir name='After submit redirect to this URL'}
	${menu args->redir_delay name='Redirect delay, sec', type='number'}
${menu name='Other', icon='sliders'}
	${menu args->required_field_message name='Required field message'}
	${menu args->invalid_value_message name='Invalid value message'}
```


## Top/bottom bar



```
<div class="$responsive" data-style="position:relative; background-image:url(${args->bgimage_url:html}); overflow:hidden; ${args->style:html:default('background-size: contain;
background-position: bottom;
background-repeat: no-repeat;
border-radius: 3px;
background-color: rgb(151, 84, 84);
box-shadow: 0 0 7px 5px rgba(189, 148, 148, 0.7);
color: rgba(42, 24, 24, 0.9);
font-family: Open Sans,san-serif;
width: 100%;')}">
    <link href="https://fonts.googleapis.com/css?family=Montserrat:400,700|Open+Sans:400,600" rel="stylesheet">
    ${block->show_close_button:default(1)}
    <div style="position:absolute; top:16px; right:16px; z-index:2">
        ${args->close_button:default('<div onmouseenter="this.style.backgroundColor=this.style.outlineColor" onmouseleave="this.style.backgroundColor=this.style.textDecorationColor" style="display: inline-block; vertical-align: text-bottom; width: 29px; height: 29px; box-sizing: border-box; border-top-left-radius: 50%; border-top-right-radius: 50%; border-bottom-right-radius: 50%; border-bottom-left-radius: 50%; border: 0px solid; -webkit-box-shadow: rgba(255, 255, 255, 0.2) 0px 1px 0px inset, rgba(0, 0, 0, 0.2) 0px 1px 2px; padding: 6px; background-color: rgb(255, 255, 255); text-decoration-color: rgb(255, 255, 255); outline-color: rgb(206, 54, 64); outline-width: 14px; color: rgb(10, 4, 4); cursor: pointer; transition: all 0.3s ease;" class="$personyze_button_dont_show_again" data-action_id="${action_id}"><div style="display: block; width: 100%; height: 100%; transition: all 0.3s ease 0s; border-top-left-radius: 50%; border-top-right-radius: 50%; border-bottom-right-radius: 50%; border-bottom-left-radius: 50%; background-image: linear-gradient(-45deg, transparent 0%, transparent 44%, currentcolor 44%, currentcolor 58%, transparent 58%, transparent 100%), linear-gradient(45deg, transparent 0%, transparent 44%, currentcolor 44%, currentcolor 58%, transparent 58%, transparent 100%);"></div></div>')}
    </div>
	<style data-pc="${args->pc:html:default('rgb(127, 130, 154)')}" ontplready="var v=['::-webkit-input-placeholder', '::-moz-placeholder', ':-moz-placeholder', ':-ms-input-placeholder'], t='', i; for (i=0; i&lt;v.length; i++) t += '.st_sw '+v[i]+' {color: '+this.dataset.pc+' !important}'; if (this.styleSheet) this.styleSheet.cssText = t; else this.textContent = t;"></style>
     <div class="$switch-elem st_sw" id="st_sw" data-case="a" data-style="width:100%; height:100%; box-sizing:border-box; ${args->shading_style:html:default('background-color: rgb(149, 143, 188);')}; ${args->send_confirm_style:html:default('padding-top: 30px;
padding-right: sel(30px, 1vw);
padding-bottom: 30px;
padding-left: sel(30px, 1vw);
font-weight: normal;
font-size: sel(18px, 14px);
color: rgb(42, 24, 24);
text-align: center;')}">
		<div
			data-case="a"
			class="$cform st_f"
			ontplsubmit="personyze.push(['Submit', ${action_id:json:html}, this._get_value_ex(), arguments[1], arguments[2]]); return true"
			ontplaftersubmit="
				var sw=this.parentNode;
				sw._set_case('b', null, false, {template: 'animator_fade'});
				var js=this.dataset.customJs.trim(), redir=this.dataset.redir.trim(), t=this.dataset.redirDelay, v=this._get_value();
				if (js) new Function('action_id', 'by_id', 'data', 'report_error', js).call(this, ${action_id:json:html}, by_id, v);
				if (redir) setTimeout(function() {location.href=redir.replace(/\{([^{\r\n]+)\}/g, function(a, w) {return v[w]==null ? a : encodeURIComponent(v[w])})}, t*1000)
			"
			data-custom-js="${args->customjs:html}"
			data-redir="${args->redir:html}"
			data-redir-delay="${args->redir_delay:html}"
			data-required_field_message="${args->required_field_message:html:default(Please fill out this field)}"
			data-invalid_value_message="${args->invalid_value_message:html:default(Invalid value for this input)}"
			style="position:relative; width:100%; height:100%"
		>
            <div data-style="${args->message_style:html:default('color: rgb(16, 9, 9);
font-family: Montserrat,san-serif;
font-weight: normal;
font-size: sel(24px, 22px);
line-height: 1;
text-align: left;')}">
                ${args->message_text:default('<div style="text-align: center;">Get Free copy of <strong>E-Book</strong> guide</div>
')}
            </div>
            <div id="st_m" data-style="${args->gift_style:html:default('margin-top: 8px;
color: rgb(9, 5, 5);
font-family: Montserrat,san-serif;
font-weight: 600;
font-size: 20px;
line-height: 1.55;
text-align: left;
margin: 0 0 0.5em 0;')}">
                ${args->gift_text}
            </div>
            <div>
                <div data-style="${args->content_style:html:default('color: rgb(6, 3, 3);
font-weight: 400;
font-size: 14px;
text-align: left;
padding: 0;')}">
                    ${args->content_text}
                </div>

				${block->with_f2:default(1)}
				<div style="display:inline-block; vertical-align:middle">
					<input form="st_f" name="${args->f2_name:html:default(Name)}" required="1" data-prop-column="${args->f2_db:html:default(first_name)}" data-style="box-sizing:border-box; ${args->f1_style:html:default('padding-top: 2px;
padding-right: 4px;
padding-bottom: 2px;
padding-left: 4px;
margin: 0.35em;
font-weight: 500;
font-size: 23px;
width: sel(300px, 85%);
border: none;
border-radius: 4px;
color: rgb(13, 7, 7);
text-align: left;
background-color: rgb(256, 256, 256);')}" placeholder="${args->f2:html:default('Name:')}">
				</div>
				${block->with_f6:default(0)}
				<div style="display:inline-block; vertical-align:middle">
					<input form="st_f" name="${args->f6_name:html}" type="tel" required="${args->f6_req:html}" data-prop-column="${args->f6_db:html}" data-style="box-sizing:border-box; ${args->f1_style:html}" placeholder="${args->f6:html}">
				</div>
				<div style="display:inline-block; vertical-align:middle">
					<input form="st_f" name="${args->f3_name:html:default(Email)}" pattern="^[^\s@]+@[^\s@\.]+\.[^\s@]+$" required="1" data-prop-column="${args->f3_db:html:default(email)}" data-style="box-sizing:border-box; ${args->f1_style:html}" placeholder="${args->f3:html:default('Email:')}" value="${email:html}" ontplready="this.value=this.value.trim()">
				</div>
				${block->with_f7:default(0)}
				<div style="display:inline-block; vertical-align:middle">
					<input form="st_f" name="${args->f7_name:html}" required="${args->f7_req:html}" data-prop-column="${args->f7_db:html}" data-style="box-sizing:border-box; ${args->f1_style:html}" placeholder="${args->f7:html}">
				</div>
				${block->with_f8:default(0)}
				<div style="display:inline-block; vertical-align:middle">
					<input form="st_f" name="${args->f8_name:html}" required="${args->f8_req:html}" data-prop-column="${args->f8_db:html}" data-style="box-sizing:border-box; ${args->f1_style:html}" placeholder="${args->f8:html}">
				</div>
				${block->with_f9:default(0)}
				<div style="display:inline-block; vertical-align:middle">
					<select form="st_f" name="${args->f9_name:html}" required="${args->f9_req:html}" data-prop-column="${args->f9_db:html}" data-style="box-sizing:border-box; ${args->f1_style:html}">
						${args->f9_options}
					</select>
				</div>
				${block->with_f5:default(0)}
				<div style="display:inline-block; vertical-align:middle">
					<textarea form="st_f" name="${args->f5_name:html}" data-style="box-sizing:border-box; ${args->f5_style:html}" placeholder="${args->f5:html}"></textarea>
				</div>
				${block->with_f4:default(0)}
				<div data-style="display:inline-block; vertical-align:middle; ${args->style9:html:default('color: rgb(9, 5, 5);
font-size: 12px;
text-align: left;')}">
					<label>
						<input form="st_f" name="${args->f4_name:html}" type="checkbox" data-prop-column="${args->f4_db:html}" value="1">
						${args->text_9}
					</label>
				</div>

                <button form="st_f" type="submit" class="$flat_btn" with_responsive="1" style="display:inline-block; vertical-align:middle; border:0; white-space:normal; box-sizing:border-box; ${args->button_style:html:default('padding-top: 2px;
padding-right: 4px;
padding-bottom: 2px;
padding-left: 4px;
margin: 0.35em;
font-weight: 500;
font-size: 18px;
width: sel(200px, 85%);
border: none;
border-radius: 4px;
background-color: rgb(6, 3, 3);
color: white;')}" hover_style="${args->button_h_style:html:default('background-color: rgb(6, 3, 3);
color: #FFFFFF;
box-shadow: rgb(169 37 37 / 46%) 0px 0px 20px 0px;')}">
					${args->button_caption:default(Get Ebook)}
                </button>
            </div>
			<div data-style="${args->style9:html}">
				${args->ds}
			</div>
        </div>
		<div data-case="b" id="st_b" data-style="${args->style10:html:default('color: rgb(15, 9, 9);')}">
			${args->success:default('<div style="text-align: center; font-size: 30px; "><span style="font-size:12px;">Awesome! We Will Keep You Posted.</span></div>
')}
		</div>
    </div>
</div>

${menu name='Box', icon='th-large'}
	${menu args->style name='Style', type='css', param='with_responsive=1'}
	${menu args->bgimage_url name='URL', type='personyze_media_url'}
	${menu args->shading_style name='Shading', type='css', param='with_responsive=1'}
${menu name='Call message', icon='bars'}
	${menu args->message_text name='Text'}
	${menu args->message_style name='Style', type='css', param='with_responsive=1'}
${menu name='Gift', icon='gift'}
	${menu args->gift_text name='Text'}
	${menu args->gift_style name='Style', type='css', param='with_responsive=1'}
	${menu args->ds name='No text'}
${menu name='Info', icon='bars'}
	${menu args->content_text name='Text'}
	${menu args->content_style name='Style', type='css', param='with_responsive=1'}
${menu name='Close button', icon='close'}
	${menu block->show_close_button name='Show close button'}
	${menu args->close_button name='Close button', type='dontshowagain'}
${menu name='Name Box', icon='edit'}
	${menu block->with_f2 name='With Name'}
	${menu args->f2_name name='Field name'}
	${menu args->f2_db name='Name save to database', type='select_social', param='with_empty=1'}
	${menu args->f2 name='Name Placeholder Text'}
	${menu args->pc name='Input placeholder color', type='color'}
	${menu args->f1_style name='Input style', type='css', param='with_responsive=1'}
${menu name='Telephone Box', icon='edit'}
	${menu block->with_f6 name='With Telephone'}
	${menu args->f6_db name='Telephone save to database', type='select_social', param='with_empty=1'}
	${menu args->f6_name name='Field name'}
	${menu args->f6_req name='Telephone is required field', type='checkbox'}
	${menu args->f6 name='Telephone Placeholder Text'}
${menu name='Email Box', icon='envelope'}
	${menu args->f3_name name='Field name'}
	${menu args->f3_db name='Email save to database', type='select_social', param='with_empty=1'}
	${menu args->f3 name='Email Placeholder Text'}
	${menu args->send_confirm_style name='Confirmation style', type='css', param='with_responsive=1'}
${menu name='Line 2 Box', icon='edit'}
	${menu block->with_f7 name='With Line 2'}
	${menu args->f7_db name='Line 2 save to database', type='select_social', param='with_empty=1'}
	${menu args->f7_name name='Field name'}
	${menu args->f7_req name='Line 2 is required field', type='checkbox'}
	${menu args->f7 name='Line 2 Placeholder Text'}
${menu name='Line 3 Box', icon='edit'}
	${menu block->with_f8 name='With Line 3'}
	${menu args->f8_db name='Line 3 save to database', type='select_social', param='with_empty=1'}
	${menu args->f8_name name='Field name'}
	${menu args->f8_req name='Line 3 is required field', type='checkbox'}
	${menu args->f8 name='Line 3 Placeholder Text'}
${menu name='Dropdown List Box', icon='edit'}
	${menu block->with_f9 name='With Dropdown List'}
	${menu args->f9_db name='Dropdown List save to database', type='select_social', param='with_empty=1'}
	${menu args->f9_name name='Field name'}
	${menu args->f9_req name='Dropdown List is required field', type='checkbox'}
	${menu args->f9_options name='Options', type='select_options'}
${menu name='Details Box', icon='edit'}
	${menu block->with_f5 name='With Details'}
	${menu args->f5 name='Details Placeholder Text'}
	${menu args->f5_name name='Field name'}
	${menu args->f5_style name='Input style', type='css', param='with_responsive=1'}
${menu name='Checkbox', icon='edit'}
	${menu block->with_f4 name='With Checkbox'}
	${menu args->style9 name='Checkbox Style', type='css', param='with_responsive=1'}
	${menu args->f4_name name='Field name'}
	${menu args->f4_db name='Checkbox save to database', type='select_social', param='with_empty=1'}
	${menu args->text_9 name='Text'}
${menu name='Action button', icon='check'}
	${menu args->button_caption name='Caption'}
	${menu args->button_style name='Style', type='css'}
	${menu args->button_h_style name='Hover Style', type='css'}
${menu name='After submit', icon='check'}
	${menu args->success name='Thank you text'}
	${menu args->customjs name='After submit execute this JavaScript', type='textarea'}
	${menu args->style10 name='Thank you text Style', type='css', param='with_responsive=1'}
	${menu args->redir name='After submit redirect to this URL. Placeholders like {Field name} will be substituted'}
	${menu args->redir_delay name='Redirect delay, sec', type='number'}
${menu name='Other', icon='sliders'}
	${menu args->required_field_message name='Required field message'}
	${menu args->invalid_value_message name='Invalid value message'}
```


## Responsive Countdown Form with Required Fields

Lead capture form with editable container, working countdown timer, required field toggles, checkbox consent, and redirect/success logic.

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


## Responsive Form with

Lead capture form with editable container,  required field toggles.

```
<div class="$responsive" data-style="position:relative; overflow:hidden; ${args->box_style:html:default('max-width: 700px;
background-color: white;
')}">
  <style>
    .st-fl { display: inline-flex; align-items: stretch; width: 100%; }
    .st-im { width: ${args->image_width:default(320px)}; height: ${args->image_height:default(420px)}; }
    .st-cn { min-height: ${args->image_height}; padding: 20px; box-sizing: border-box; }

    @media (max-width: 599px) {
      .st-fl { flex-direction: column-reverse; }
      .st-im { width: ${args->image_width_mob:default(150px)}; height: ${args->image_height_mob:default(180px)}; }
      .st-cn { min-height: auto; min-width: ${args->image_width_mob}; }
    }

    .$btn {
      font-weight: bold;
      text-transform: uppercase;
      padding: 12px 30px;
      border-radius: 50px;
      background-color: #111;
      color: white;
      border: none;
      cursor: pointer;
      transition: background-color 0.3s ease;
    }

    .$btn:hover {
      background-color: #000;
    }

    .close-button-wrapper {
      position: absolute;
      top: 10px;
      right: 10px;
      z-index: 10;
    }
  </style>

  <div class="st-fl">
    <div style="background-image:url('${args->image_src:html:default('https://cdn.personyze.com/upload/362/5630c0948581ce13.jpeg')}'); background-size:cover; background-position:center;">
      <div class="st-im"></div>
    </div>

    <div class="st-cn">
      <div class="$switch-elem" data-case="a">
        <form data-case="a" class="$cform st_f"
              ontplsubmit="personyze.push(['Submit', '${action_id:html}', this._get_value_ex(), arguments[1], arguments[2]]); return true"
              ontplaftersubmit="this.parentNode._set_case('b', null, false, {template: 'animator_fade'}); var redir=this.dataset.redir, t=this.dataset.redirDelay|0; if (redir) setTimeout(function(){location.href=redir}, t*1000)"
              data-redir="${args->redir:html}" data-redir-delay="${args->redir_delay:html}"
              data-required_field_message="${args->required_field_message:html:default(Please fill out this field)}"
              data-invalid_value_message="${args->invalid_value_message:html:default(Invalid value for this input)}"
        >

          <div data-style="${args->title_style:html:default('text-align: center;
color: black;
font-size: sel(32px, 4vw);
font-weight: bold;
margin-top: 0;
margin-right: 0;
margin-bottom: 20px;
margin-left: 0;
')}">
            ${args->title:default('<img src="https://cdn.personyze.com/upload/362/4c53a78c4a0882c4.png" style="width:200px" /><br />
Your title')}
          </div>

          <div data-style="${args->text_style:html:default('text-align: center;
color: black;
font-size: sel(14px, 4vw);
margin-top: 0;
margin-right: 0;
margin-bottom: 20px;
margin-left: 0;
')}">
            ${args->text:default(Free text)}
          </div>

          ${block->with_first_name:default(1)}
          <div style="text-align:center">
            <input form="st_f" name="first_name" data-prop-column="first_name"
                   required="${args->first_name_required:html:default(1)}"
                   placeholder="${args->first_name_placeholder:html:default(First Name)}"
                   data-style="${args->first_name_input_style:html:default('width: sel(315px, 90%);
padding: 12px;
font-size: 14px;
border: 1px solid #ccc;
margin-bottom: 15px;
')}">
          </div>

          <div style="text-align:center">
            <input form="st_f" name="email" data-prop-column="email" pattern="^[^\\s@]+@[^\\s@\\.]+\\.[^\\s@]+$" required="1"
                   placeholder="${args->email_placeholder:html:default(Email)}"
                   data-style="${args->email_input_style:html:default('width: sel(315px, 90%);
padding: 12px;
font-size: 14px;
border: 1px solid #ccc;
margin-bottom: 15px;
')}">
          </div>

          <div style="text-align:center">
            <button form="st_f" type="submit" class="$btn" data-style="${args->button_style:html:default('background-color: rgb(45, 156, 20);
padding-top: 4px;
padding-right: 18.4px;
padding-bottom: 4px;
padding-left: 18.4px;
')}">
              ${args->button_tex:default(SUBSCRIBE)}
            </button>
          </div>

          ${block->with_terms:default(1)}
          <div data-style="${args->terms_style:html:default('text-align: center;
font-size: 12px;
margin-top: 15px;
')}">
            ${args->terms:default('By signing up to our newsletter, you agree to our Terms &amp; Conditions.')}
          </div>
        </form>

        <div data-case="b">
          ${args->success:default('<div style="text-align: center; font-size: 30px;">Awesome! We will keep you posted.</div>
')}
        </div>
      </div>
    </div>
  </div>

  ${block->show_close_button:default(1)}
  <div class="close-button-wrapper">
    ${args->close_button:default('<div onmouseenter="this.style.backgroundColor=this.style.outlineColor" onmouseleave="this.style.backgroundColor=this.style.textDecorationColor" style="display: inline-block; vertical-align: text-bottom; width: 24px; height: 24px; box-sizing: border-box; border-radius: 50%; border: 0px solid; box-shadow: none; padding: 2px; background-color: rgba(0, 0, 0, 0); text-decoration-color: rgba(0, 0, 0, 0); outline-color: rgb(206, 54, 64); outline-width: 9px; color: rgb(10, 4, 4); cursor: pointer; transition: 0.3s;" class="$personyze_button_dont_show_again" data-action_id="${action_id}"><div style="display: block; width: 100%; height: 100%; transition: 0.3s; border-radius: 50%; background-image: linear-gradient(-45deg, transparent 0%, transparent 46%, currentcolor 46%, currentcolor 56%, transparent 56%, transparent 100%), linear-gradient(45deg, transparent 0%, transparent 46%, currentcolor 46%, currentcolor 56%, transparent 56%, transparent 100%);"></div></div>')}
  </div>
</div>

${menu name='Layout', icon='bars'}
	${menu args->box_style name='Box Style', type='css'}
${menu name='Image', icon='bars'}
	${menu args->image_src name='Image URL', type='personyze_media_url'}
	${menu args->image_width name='Image Width', type='css_length'}
	${menu args->image_height name='Image Height', type='css_length'}
	${menu args->image_width_mob name='Mobile Width', type='css_length'}
	${menu args->image_height_mob name='Mobile Height', type='css_length'}
${menu name='Texts', icon='bars'}
	${menu args->title name='Title'}
	${menu args->title_style name='Title Style', type='css'}
	${menu args->text name='Subtext'}
	${menu args->text_style name='Subtext Style', type='css'}
${menu name='Fields', icon='bars'}
	${menu block->with_first_name name='Show First Name'}
	${menu args->first_name_required name='First Name Required?', type='checkbox'}
	${menu args->first_name_placeholder name='First Name Placeholder'}
	${menu args->first_name_input_style name='First Name Style', type='css'}
	${menu args->email_placeholder name='Email Placeholder'}
	${menu args->email_input_style name='Email Style', type='css'}
${menu name='CTA Button', icon='bars'}
	${menu args->button_tex name='Button Text'}
	${menu args->button_style name='Button Style', type='css'}
${menu name='Terms', icon='bars'}
	${menu block->with_terms name='Show Terms'}
	${menu args->terms name='Terms Text'}
	${menu args->terms_style name='Terms Style', type='css'}
${menu name='Success & Logic', icon='bars'}
	${menu args->success name='Thank You Message'}
	${menu args->redir name='Redirect URL'}
	${menu args->redir_delay name='Redirect Delay (s)', type='number'}
${menu name='Close Button', icon='bars'}
	${menu block->show_close_button name='Show Close Button'}
	${menu args->close_button name='Close Button HTML', type='dontshowagain'}
${menu name='Validation', icon='bars'}
	${menu args->required_field_message name='Required Field Message'}
	${menu args->invalid_value_message name='Invalid Value Message'}
```


## Inline Ebook Signup Form

A sleek, responsive signup form template ideal for capturing leads directly on your site. It includes customizable input fields and an inline submission button.

```
<div class="$responsive" data-style="position:relative; overflow:hidden; ${args->style:html:default('background-size: cover;
background-position: center;
border-radius: 8px;
background-color: rgba(245, 245, 245, 0.43);
box-shadow: 0 4px 10px rgba(0,0,0,0.2);
color: #333;
font-family: Montserrat, Open Sans, sans-serif;
width: 100%;
background-image: url(https://cdn.personyze.com/upload/362/5630c0948581ce13.jpeg);
')}">

    <link href="https://fonts.googleapis.com/css?family=Montserrat:400,700|Open+Sans:400,600" rel="stylesheet">

    ${block->show_close_button:default(1)}
    <div style="position:absolute; top:10px; right:10px; z-index:2;">
        ${args->close_button:default('<div class="$personyze_button_dont_show_again" data-action_id="${action_id}" style="cursor:pointer;font-size:16px;color:#666;">✕</div>')}
    </div>

    <div class="$switch-elem st_sw" id="st_sw" data-case="a" data-style="box-sizing:border-box; ${args->shading_style:html:default('background-color: rgba(255,255,255,0.9); padding:20px; text-align:center; border-radius:8px;')}">
        <div data-case="a" class="$cform st_f"
            ontplsubmit="personyze.push(['Submit', ${action_id:json:html}, this._get_value_ex(), arguments[1], arguments[2]]); return true"
            ontplaftersubmit="
                var sw=this.parentNode;
                sw._set_case('b', null, false, {template: 'animator_fade'});
                var js=this.dataset.customJs.trim(), redir=this.dataset.redir.trim(), t=this.dataset.redirDelay, v=this._get_value();
                if (js) new Function('action_id', 'by_id', 'data', 'report_error', js).call(this, ${action_id:json:html}, by_id, v);
                if (redir) setTimeout(function() {location.href=redir.replace(/\{([^\{\r\n]+)\}/g, function(a, w) {return v[w]==null ? a : encodeURIComponent(v[w])})}, t*1000)
            "
            data-custom-js="${args->customjs:html}"
            data-redir="${args->redir:html:default('https://personyze.com/panel/id/362#cat=Campaigns/condition.actions.tracker-c1819-cv8')}"
            data-redir-delay="${args->redir_delay:html:default(7)}"
            data-required_field_message="${args->required_field_message:html:default(Please fill out this field)}"
            data-invalid_value_message="${args->invalid_value_message:html:default(Invalid value)}">

            <div data-style="${args->message_style:html:default('font-size:24px; margin-bottom:10px; color:#222;')}">
                ${args->message_text:default('<strong>Get Your Free E-Book Guide</strong>')}
            </div>

            <div data-style="${args->content_style:html:default('font-size:14px; margin-bottom:20px; color:#555;')}">
                ${args->content_text:default(Fill out the form below to receive your copy directly to your email.)}
            </div>

            <div style="margin-bottom:10px; display:flex; justify-content:center; align-items:center; flex-wrap:wrap; gap:5px;">
                ${block->with_f2:default(1)}
                <div style="display:;">
                    <input form="st_f" name="${args->f2_name:html:default(Name)}" required="1" data-prop-column="${args->f2_db:html:default(first_name)}" data-style="${args->f1_style:html:default('padding:8px; border-radius:4px; border:1px solid #ccc;')}" placeholder="${args->f2:html:default(Name)}">
                </div>

                <div style="display:inline-block;">
                    <input form="st_f" name="${args->f3_name:html:default(Email)}" type="email" required="1" data-prop-column="${args->f3_db:html:default(email)}" data-style="${args->f1_style:html}" placeholder="${args->f3:html:default(Email)}">
                </div>

                ${block->with_f6:default(0)}
                <div style="display:inline-block;">
                    <input form="st_f" name="${args->f6_name:html}" type="tel" required="${args->f6_req:html}" data-prop-column="${args->f6_db:html}" data-style="${args->f1_style:html}" placeholder="${args->f6:html}">
                </div>

                ${block->with_f5:default(0)}
                <div style="display:inline-block;">
                    <textarea form="st_f" name="${args->f5_name:html}" data-style="${args->f5_style:html:default('padding:8px; border-radius:4px; border:1px solid #ccc;')}" placeholder="${args->f5:html}"></textarea>
                </div>

                <button form="st_f" type="submit" class="$flat_btn" with_responsive="1" data-style="${args->button_style:html:default('background-color:#007BFF;color:#fff;padding:10px 20px;border-radius:4px;cursor:pointer;')}" hover_style="${args->button_h_style:html:default('background-color:#0056b3;')}">
                    ${args->button_caption:default(Download Ebook)}
                </button>
            </div>
        </div>

        <div data-case="b" id="st_b" data-style="${args->style10:html:default('color:#222;padding:20px;font-size:20px;')}">
            ${args->success:default(Thank you! Your ebook is on its way.)}
        </div>

    </div>
</div>

${menu name='Form Settings', icon='sliders'}
	${menu args->style name='Container Style', description='Controls the main container styling.', type='css', param='with_responsive=1'}
${menu name='Content', icon='edit'}
	${menu args->message_text name='Main Heading', description='Primary message displayed on top of the form.'}
	${menu args->content_text name='Description', description='Brief description or instruction for users.'}
${menu name='Input Fields', icon='form'}
	${menu args->f1_style name='Field Style', description='Styling for input fields.', type='css', param='with_responsive=1'}
${menu name='Close Button', icon='close'}
	${menu block->show_close_button name='Show Close Button', description='Toggle visibility of the close button.'}
${menu name='Submit Button', icon='check'}
	${menu args->button_caption name='Button Caption', description='Text displayed on the submit button.'}
	${menu args->button_style name='Button Style', description='Styling for the submit button.', type='css'}
	${menu args->button_h_style name='Button Hover Style', description='Styling for button hover state.', type='css'}
${menu name='After Submission', icon='check-circle'}
	${menu args->success name='Thank You Message', description='Message displayed after successful form submission.'}
	${menu args->redir name='Redirect URL', description='URL to redirect after form submission (supports placeholders).'}
	${menu args->redir_delay name='Redirect Delay (sec)', description='Delay before redirecting after submission.', type='number'}
	${menu args->customjs name='Custom JavaScript', description='JS code executed after submission.', type='textarea'}
```


