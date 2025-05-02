# Personyze form templates


## Form with 2 buttons



```
<div class="$responsive" data-style="position:relative; background-color:white; box-sizing:border-box; ${args->style:html:default('width:sel(500px, 90vw); padding:30px 40px'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(0, 0, 'Box', 'th-large')}" onupdate="var df=ns.joyquery('child::div', this).get(0).style, dl=ns.joyquery('child::div:last-child', this).get(0).style, fs=this.style; df.backgroundColor=fs.borderTopColor; df.border=fs.border; df.borderBottom='none'; df.borderTopLeftRadius=fs.borderTopLeftRadius; df.borderTopRightRadius=fs.borderTopRightRadius; dl.border=fs.border; dl.borderTop='none'; dl.borderBottomLeftRadius=fs.borderBottomLeftRadius; dl.borderBottomRightRadius=fs.borderBottomRightRadius; fs.borderRadius=0; fs.border='none'">
    <link href="https://fonts.googleapis.com/css?family=Fjalla+One" rel="stylesheet">
    ${block->show_close_button:default(1):arg_name(Show close button):arg_section(9, 0, 'Close button', 'close')}
    <div style="width:1px; vertical-align:middle" class="$copystyle" data-from="preceding-sibling::*" data-js="s.padding=fs.padding">
        ${args->close_button:default('<img src="http://counter.personyze.com/images/close-buttons/black-16x16.png" style="position:absolute; top:16px; right:16px; width:16px; height:16px;" class="$personyze_button_dont_show_again" data-action_id="${action_id}" data-n_sessions="0">'):input_type(dontshowagain):arg_name(Close button):arg_section(9, 1, 'Close button', 'close')}
    </div>
    <div class="$switch-elem" data-case="a">
		<div data-case="a" class="$cform st_f" ontplsubmit="personyze.push(['Submit', '${action_id:html}', this._get_value_ex(), arguments[1], arguments[2]]); return true" ontplaftersubmit="this.parentNode._set_case('b', null, false, {template: 'animator_fade'}); var redir=this.dataset.redir, t=this.dataset.redirDelay; if (redir) setTimeout(function() {location.href=redir}, t*1000)" data-redir="${args->redir:html:arg_name(After submit redirect to this URL):arg_section(7, 1, 'After submit', 'check')}" data-redir-delay="${args->redir_delay:html:input_type(number):arg_name('Redirect delay, sec'):arg_section(7, 2, 'After submit', 'check')}" style="margin:8px 0 10px">
			<div data-style="vertical-align:middle; ${args->logo_style:html:default('text-align:center; padding:0 0 40px;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(1, 1, 'Logo', 'image')}">
				<img src="${args->logo_url:html:default('https://static.personyze.com/upload/362/2ced8f83fce5a056.png'):input_type(personyze_media_url):arg_name(URL):arg_section(1, 0, 'Logo', 'image')}">
			</div>
			<div data-style="vertical-align:middle; ${args->message_style:html:default('color:black; text-align:center; font-family:Helvetica,san-serif; font-weight:normal; font-size:15px; padding:10px 0; letter-spacing:1px'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(2, 1, 'Call message', 'bars')}">
				${args->message_text:default('Don&#39;t miss out'):arg_name(Text):arg_section(2, 0, 'Call message', 'bars')}
			</div>
			<div data-style="vertical-align:middle; ${args->content_style:html:default('color:black; text-align:center; font-family:Fjalla One,san-serif; font-weight:normal; font-size:28px; line-height:38px; padding:10px 40px; text-transform:uppercase; letter-spacing:2px'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(3, 1, 'Content', 'bars')}">
				${args->content_text:default('Exclusives, offers, and the latest from us'):arg_name(Text):arg_section(3, 0, 'Content', 'bars')}
			</div>
			<div>
				<span data-style="${args->email_field_label_style:html:default('font-family:Helvetica,san-serif; font-weight:normal; font-size:13px'):input_type(css):input_props('with_responsive=1'):arg_name(Label style):arg_section(4, 1, 'Email field', 'envelope')}">${args->email_field_label:default('Email Address*'):arg_name(Label):arg_section(4, 0, 'Email field', 'envelope')}</span>
				<div style="margin-top:4px">
					<input form="st_f" name="email" data-prop-column="email" pattern="^[^\s@]+@[^\s@\.]+\.[^\s@]+$" required="1" placeholder="${args->email_field_placeholder:html:default(Email Address):arg_name(Field placeholder):arg_section(4, 2, 'Email field', 'envelope')}" data-style="${args->email_field_style:html:default('font-family: Helvetica,san-serif;
font-weight: normal;
font-size: 13px;
width: 100%;
height: 40px;
padding: 10px;
box-sizing: border-box;
border: 1px solid rgb(196,196,196);
border-radius: 3px;
color: rgb(162,162,162);'):input_type(css):input_props('with_responsive=1'):arg_name(Field style):arg_section(4, 3, 'Email field', 'envelope')}">
				</div>
			</div>
			<div style="margin-top:20px; white-space:nowrap">
				<div style="display:inline-block; vertical-align:top; width:50%; box-sizing:border-box; padding-right:10px">
					<div class="$personyze_button_dont_show_again" data-action_id="${action_id:html}" data-n_sessions="0" data-style="box-sizing:border-box; ${args->cancel_button_style:html:default('font-family:Fjalla One,san-serif; font-weight:normal; font-size:13px; width:100%; height:40px; line-height:40px; text-align:center; text-transform:uppercase; border:1px solid black; border-radius:3px; background-color:white; color:black; padding:0'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(8, 1, 'Cancel button', 'close')}">${args->cancel_button_label:default(No Thanks):arg_name(Label):arg_section(8, 0, 'Cancel button', 'close')}</div>
				</div><div style="display:inline-block; vertical-align:top; width:50%; box-sizing:border-box; padding-left:10px">
					<button form="st_f" type="submit" class="$flat_btn" data-style="display:inline-block; ${args->action_button_style:html:default('font-family:Fjalla One,san-serif; font-weight:normal; font-size:13px; width:100%; height:40px; line-height:40px; text-align:center; text-transform:uppercase; border:0; border-radius:3px; background-color:black; color:white; padding:0'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(6, 1, 'Action button', 'check')}">
						${args->action_button_label:default(Sign Up):arg_name(Label):arg_section(6, 0, 'Action button', 'check')}
					</button>
				</div>
			</div>
		</div>
		<div data-case="b">
			${args->success:default(Thank you!):arg_name(Thank you text):arg_section(7, 0, 'After submit', 'check')}
		</div>
	</div>
    <div data-style="${args->info_style:html:default('margin-top:55px; font-family:Helvetica,san-serif; font-weight:normal; font-size:11px; text-align:center; color:rgb(162,162,162)'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(5, 1, 'Info', 'info')}">${args->info_text:default('By signing up, you agree to our&nbsp;<a href="#" style="text-decoration:underline; cursor:pointer; color:inherit">Privacy Policy</a> and <a href="#" style="text-decoration:underline; cursor:pointer; color:inherit">Terms of Use</a>'):arg_name(Text):arg_section(5, 0, 'Info', 'info')}</div>
</div>
```


## Form with several fields



```
<div class="$responsive" data-style="${args->style:html:default('width:480px; font-size:15px'):input_type(css):input_props('with_responsive=1'):arg_name(Box style):arg_section(0, 0, 'Box', 'th-large')}" onupdate="var fs=ns.joyquery('child::span>span', this).get(0).style; for (var e,i=ns.joyquery('descendant::input', this); e=i();) e.style.cssText+=';'+fs.cssText">
	<span style="display:none"><span data-style="box-sizing:border-box; ${args->input_style:html:default('outline:none; border-top:none; border-left:none; border-right:none; border-bottom:solid gray 1px; margin:0.5em 0'):input_type(css):input_props('with_responsive=1'):arg_name(Input style):arg_section(6, 0, 'Inputs', 'th-large')}"></span></span>
	<div data-style="position:relative; ${args->title_box_style:html:default('background-color:#34194D; color:white; padding:1em 2em; border-radius:5px 5px 0 0'):input_type(css):input_props('with_responsive=1'):arg_name(Title box style):arg_section(1, 0, 'Title box', 'th-large')}">
		<div data-style="${args->title_1_style:html:default('font-size:135%'):input_type(css):input_props('with_responsive=1'):arg_name(Title line 1 style):arg_section(1, 2, 'Title box', 'th-large')}">
			${args->title_1:default(Title line 1):arg_name(Line 1):arg_section(1, 1, 'Title box', 'th-large')}
		</div>
		<div data-style="${args->title_2_style:html:default('font-size:100%'):input_type(css):input_props('with_responsive=1'):arg_name(Title line 1 style):arg_section(1, 4, 'Title box', 'th-large')}">
			${args->title_2:default(Title line 2):arg_name(Line 2):arg_section(1, 3, 'Title box', 'th-large')}
		</div>
		${block->show_close_button:default(1):arg_name(Show close button):arg_section(4, 0, 'Close Button', 'times-circle')}
		<div data-style="position:absolute; cursor:pointer; ${args->close_button_style:html:default('top:10px; right:10px; z-index:9999'):input_type(css):input_props('with_responsive=1'):arg_name(Close Button Style):arg_section(4, 1, 'Close Button', 'times-circle')}">
			${args->close_button:default('<img src="//counter.personyze.com/images/close-buttons/rect-white-orange-16x16.png" class="$personyze_button_dont_show_again" data-action_id="${action_id}">'):input_type(dontshowagain):arg_name(Close button):arg_section(4, 2, 'Close Button', 'times-circle')}
		</div>
	</div>
	<div class="$switch-elem" data-case="a">
		<div data-case="a" class="$cform st_f" ontplsubmit="personyze.push(['Submit', '${action_id:html}', this._get_value_ex(), arguments[1], arguments[2]]); return true" ontplaftersubmit="this.parentNode._set_case('b', null, false, {template: 'animator_fade'}); var redir=this.dataset.redir, t=this.dataset.redirDelay; if (redir) setTimeout(function() {location.href=redir}, t*1000)" data-redir="${args->redir:html:arg_name(After submit redirect to this URL):arg_section(11, 1, 'After submit', 'check')}" data-redir-delay="${args->redir_delay:html:input_type(number):arg_name('Redirect delay, sec'):arg_section(11, 2, 'After submit', 'check')}" data-style="${args->content_box_style:html:default('background-color:white; color:black; padding:1em 2em; border:solid silver 1px'):input_type(css):input_props('with_responsive=1'):arg_name(Title box style):arg_section(5, 0, 'Content box', 'th-large')}">
			<div data-style="${args->content_style:html:default('font-size:120%'):input_type(css):input_props('with_responsive=1'):arg_name(Content style):arg_section(5, 2, 'Content box', 'th-large')}">
				${args->content:default(Content):arg_name(Content):arg_section(5, 1, 'Content box', 'th-large')}
			</div>

			${block->f1:default(1):arg_name('With field #1'):arg_section(7, 0, 'Field #1', 'th-large')}
			<input form="st_f" name="Field 1" data-prop-column="${args->f1_db:html:default(first_name):input_type(select_social):input_props('with_empty=1'):arg_name('Field #1 save to database'):arg_section(7, 4, 'Field #1', 'th-large')}" data-style="${args->f1_style:html:default('width:45%; float:left'):input_type(css):input_props('with_responsive=1'):arg_name(Input style):arg_section(7, 2, 'Field #1', 'th-large')}" placeholder="${args->f1:html:default(First name):arg_name('Field #1 placeholder text'):arg_section(7, 1, 'Field #1', 'th-large')}" ontplready="${args->f1_required:html:input_type(checkbox):input_props('value_off=','value_on=this.required=1'):arg_name('Field #1 is required'):arg_section(7, 3, 'Field #1', 'th-large')}">

			${block->f2:default(1):arg_name('With field #2'):arg_section(8, 0, 'Field #2', 'th-large')}
			<input form="st_f" name="Field 2" data-prop-column="${args->f2_db:html:default(last_name):input_type(select_social):input_props('with_empty=1'):arg_name('Field #2 save to database'):arg_section(8, 4, 'Field #2', 'th-large')}" data-style="${args->f2_style:html:default('width:45%; float:right'):input_type(css):input_props('with_responsive=1'):arg_name(Input style):arg_section(8, 2, 'Field #2', 'th-large')}" placeholder="${args->f2:html:default(Last name):arg_name('Field #2 placeholder text'):arg_section(8, 1, 'Field #2', 'th-large')}" ontplready="${args->f2_required:html:input_type(checkbox):input_props('value_off=','value_on=this.required=1'):arg_name('Field #2 is required'):arg_section(8, 3, 'Field #2', 'th-large')}">

			${block->f3:default(1):arg_name('With field #3'):arg_section(9, 0, 'Field #3', 'th-large')}
			<input form="st_f" name="Field 3" data-prop-column="${args->f3_db:html:default(email):input_type(select_social):input_props('with_empty=1'):arg_name('Field #3 save to database'):arg_section(9, 4, 'Field #3', 'th-large')}" data-style="${args->f3_style:html:default('width:100%; float:left'):input_type(css):input_props('with_responsive=1'):arg_name(Input style):arg_section(9, 2, 'Field #3', 'th-large')}" placeholder="${args->f3:html:default(Email):arg_name('Field #3 placeholder text'):arg_section(9, 1, 'Field #3', 'th-large')}" ontplready="${args->f3_required:html:default('this.required=1'):input_type(checkbox):input_props('value_off=','value_on=this.required=1'):arg_name('Field #3 is required'):arg_section(9, 3, 'Field #3', 'th-large')}">

			${block->f4:default(1):arg_name('With field #4'):arg_section(10, 0, 'Field #4', 'th-large')}
			<input form="st_f" name="Field 4" data-prop-column="${args->f4_db:html:input_type(select_social):input_props('with_empty=1'):arg_name('Field #4 save to database'):arg_section(10, 4, 'Field #4', 'th-large')}" data-style="${args->f4_style:html:default('width:45%; float:left'):input_type(css):input_props('with_responsive=1'):arg_name(Input style):arg_section(10, 2, 'Field #4', 'th-large')}" placeholder="${args->f4:html:default(Custom field 1):arg_name('Field #4 placeholder text'):arg_section(10, 1, 'Field #4', 'th-large')}" ontplready="${args->f4_required:html:input_type(checkbox):input_props('value_off=','value_on=this.required=1'):arg_name('Field #4 is required'):arg_section(10, 3, 'Field #4', 'th-large')}">

			${block->f5:default(1):arg_name('With field #5'):arg_section(12, 0, 'Field #5', 'th-large')}
			<input form="st_f" name="Field 5" data-prop-column="${args->f5_db:html:input_type(select_social):input_props('with_empty=1'):arg_name('Field #5 save to database'):arg_section(12, 4, 'Field #5', 'th-large')}" data-style="${args->f5_style:html:default('width:45%; float:right'):input_type(css):input_props('with_responsive=1'):arg_name(Input style):arg_section(12, 2, 'Field #5', 'th-large')}" placeholder="${args->f5:html:default(Custom field 2):arg_name('Field #5 placeholder text'):arg_section(12, 1, 'Field #5', 'th-large')}" ontplready="${args->f5_required:html:input_type(checkbox):input_props('value_off=','value_on=this.required=1'):arg_name('Field #5 is required'):arg_section(12, 3, 'Field #5', 'th-large')}">

			${block->f6:default(1):arg_name('With field #6'):arg_section(13, 0, 'Field #6', 'th-large')}
			<input form="st_f" name="Field 6" data-prop-column="${args->f6_db:html:input_type(select_social):input_props('with_empty=1'):arg_name('Field #6 save to database'):arg_section(13, 4, 'Field #6', 'th-large')}" data-style="${args->f6_style:html:default('width:100%; float:left'):input_type(css):input_props('with_responsive=1'):arg_name(Input style):arg_section(13, 2, 'Field #6', 'th-large')}" placeholder="${args->f6:html:default(Custom field 3):arg_name('Field #6 placeholder text'):arg_section(13, 1, 'Field #6', 'th-large')}" ontplready="${args->f6_required:html:input_type(checkbox):input_props('value_off=','value_on=this.required=1'):arg_name('Field #6 is required'):arg_section(13, 3, 'Field #6', 'th-large')}">

			${block->f7:default(1):arg_name('With field #7'):arg_section(14, 0, 'Field #7', 'th-large')}
			<input form="st_f" name="Field 7" data-prop-column="${args->f7_db:html:input_type(select_social):input_props('with_empty=1'):arg_name('Field #7 save to database'):arg_section(14, 4, 'Field #7', 'th-large')}" data-style="${args->f7_style:html:default('width:45%; float:left'):input_type(css):input_props('with_responsive=1'):arg_name(Input style):arg_section(14, 2, 'Field #7', 'th-large')}" placeholder="${args->f7:html:default(Custom field 4):arg_name('Field #7 placeholder text'):arg_section(14, 1, 'Field #7', 'th-large')}" ontplready="${args->f7_required:html:input_type(checkbox):input_props('value_off=','value_on=this.required=1'):arg_name('Field #7 is required'):arg_section(14, 3, 'Field #7', 'th-large')}">

			${block->f8:default(1):arg_name('With field #8'):arg_section(15, 0, 'Field #8', 'th-large')}
			<input form="st_f" name="Field 8" data-prop-column="${args->f8_db:html:input_type(select_social):input_props('with_empty=1'):arg_name('Field #8 save to database'):arg_section(15, 4, 'Field #8', 'th-large')}" data-style="${args->f8_style:html:default('width:45%; float:right'):input_type(css):input_props('with_responsive=1'):arg_name(Input style):arg_section(15, 2, 'Field #8', 'th-large')}" placeholder="${args->f8:html:default(Custom field 5):arg_name('Field #8 placeholder text'):arg_section(15, 1, 'Field #8', 'th-large')}" ontplready="${args->f8_required:html:input_type(checkbox):input_props('value_off=','value_on=this.required=1'):arg_name('Field #8 is required'):arg_section(15, 3, 'Field #8', 'th-large')}">

			${block->f9:default(1):arg_name('With field #9'):arg_section(2, 0, 'Field #9', 'th-large')}
			<input form="st_f" name="Field 9" data-prop-column="${args->f9_db:html:input_type(select_social):input_props('with_empty=1'):arg_name('Field #9 save to database'):arg_section(2, 4, 'Field #9', 'th-large')}" data-style="${args->f9_style:html:default('width:100%; float:left'):input_type(css):input_props('with_responsive=1'):arg_name(Input style):arg_section(2, 2, 'Field #9', 'th-large')}" placeholder="${args->f9:html:default(Custom field 6):arg_name('Field #9 placeholder text'):arg_section(2, 1, 'Field #9', 'th-large')}" ontplready="${args->f9_required:html:input_type(checkbox):input_props('value_off=','value_on=this.required=1'):arg_name('Field #9 is required'):arg_section(2, 3, 'Field #9', 'th-large')}">

			<div style="clear:both"></div>

			<div style="text-align:center">
				<button form="st_f" type="submit" class="$flat_btn" data-style="outline:0; border:none;
					${args->button_style:html:default('
					padding: 5px;
					line-height: 1.3;
					background-color: #ac9166;
					color: white'):input_type(css):input_props('with_responsive=1'):arg_name(Submit Button style):arg_section(3, 1, 'Submit Button', 'th-large')}">
					${args->button_text:default(Submit):arg_name(Submit Button Text):arg_section(3, 0, 'Submit Button', 'th-large')}
				</button>
			</div>
		</div>
		<div data-case="b">
			${args->success:default(Thank you!):arg_name(Thank you text):arg_section(11, 0, 'After submit', 'check')}
		</div>
	</div>
</div>
```


## Hotel



```
<div class="$responsive" data-style="box-sizing:border-box; position:relative; overflow:hidden; background-image: url(${args->image_bg:html:default('//counter.personyze.com/images/html_customizer/Hotel.jpg'):input_type(personyze_media_url):arg_name(bg image):arg_section(0, 1, 'Box', 'th-large')});
background-repeat:no-repeat; ${args->style:html:default('width: 480px; height: 180px; border: 1px solid #0c0c0e; background-position: 0 50%'):input_type(css):input_props('with_responsive=1'):arg_name(Box style):arg_section(0, 0, 'Box', 'th-large')}">
	${block->show_close_button:default(1):arg_name(Show close button):arg_section(4, 0, 'Close Button', 'times-circle')}
	<div data-style="position:absolute; cursor:pointer; ${args->close_button_style:html:default('top:5px; right:5px;z-index:9999'):input_type(css):input_props('with_responsive=1'):arg_name(Close_btn_Style):arg_section(4, 1, 'Close Button', 'times-circle')}">
		${args->close_button:default('<img src="//counter.personyze.com/images/close-buttons/rect-white-orange-24x24.png" class="$personyze_button_dont_show_again" data-action_id="${action_id}">'):input_type(dontshowagain):arg_name(Close button):arg_section(4, 2, 'Close Button', 'times-circle')}
	</div>

	<div data-style="position: absolute;
	${args->title_block:html:default('
	top: 10px;
	left: 10px;
	width: 280px;
	height: 160px'):input_type(css):input_props('with_responsive=1'):arg_name(Block position):arg_section(1, 0, 'Main block', 'list-alt')}">

		<div data-style="width: 100%;
		height: 100%;
		${args->main_block_style:html:default('
			background-color: #2d383a;
		opacity: 0.8;
		filter: blur(1px) grayscale(20%)'):input_type(css):input_props('with_responsive=1'):arg_name(Main style):arg_section(1, 1, 'Main block', 'list-alt')}">
		</div>

		<div class="$switch-elem" data-case="a" data-style="position: absolute; color:white;
		${args->main_title_position:html:default('
		left: 10px;
		top: 10px'):input_type(css):input_props('with_responsive=1'):arg_name(Title position):arg_section(2, 0, 'Title', 'bookmark')}">
			<div data-case="a" class="$cform st_f" ontplsubmit="personyze.push(['Submit', '${action_id:html}', this._get_value_ex(), arguments[1], arguments[2]]); return true" ontplaftersubmit="this.parentNode._set_case('b', null, false, {template: 'animator_fade'}); var redir=this.dataset.redir, t=this.dataset.redirDelay; if (redir) setTimeout(function() {location.href=redir}, t*1000)" data-redir="${args->redir:html:arg_name(After submit redirect to this URL):arg_section(5, 1, 'After submit', 'check')}" data-redir-delay="${args->redir_delay:html:input_type(number):arg_name('Redirect delay, sec'):arg_section(5, 2, 'After submit', 'check')}">
				<span data-style="${args->title_text1_style:html:default('font-size: 20px;
				color: white;
				font-family: Oxygen, sans-serif;
				line-height: 1;
				font-weight: 300'):input_type(css):input_props('with_responsive=1'):arg_name(Text1 style):arg_section(2, 2, 'Title', 'bookmark')}">
					${args->title1:default('Subscribe &'):arg_name(Text1):arg_section(2, 1, 'Title', 'bookmark')}
				</span>

				<div data-style="
				${args->title_text2_style:html:default('
				color: white;
				font-family: Oxygen, sans-serif;
				font-size: 40px;
				line-height: 1;
				font-weight: 700'):input_type(css):input_props('with_responsive=1'):arg_name(Text2 style):arg_section(2, 4, 'Title', 'bookmark')}">
					${args->title2:default(GET 10% OFF):arg_name(Text2):arg_section(2, 3, 'Title', 'bookmark')}
				</div>
				<div data-style="
				${args->title_text3_style:html:default('
				color: white;
				font-family: Oxygen, sans-serif;
				font-size: 20px;
				line-height: 1;
				font-weight: 300'):input_type(css):input_props('with_responsive=1'):arg_name(Text3 style):arg_section(2, 6, 'Title', 'bookmark')}">
					${args->title3:default(for your next trip):arg_name(Text3):arg_section(2, 5, 'Title', 'bookmark')}
				</div>

				<div style="${args->email_block_position:html:default('margin-top:14px; background-color:white'):input_type(css):input_props('with_responsive=1'):arg_name(Email block position):arg_section(3, 1, 'Email block', 'envelope')}">
					<input form="st_f" name="email" data-prop-column="email" pattern="^[^\s@]+@[^\s@\.]+\.[^\s@]+$" required="1" placeholder="${args->email_text:html:default(Enter your email id here):arg_name(Email Text):arg_section(3, 0, 'Email block', 'envelope')}"
					data-style="outline: 0;
					border: none;
					text-align: center;
					${args->email_block_text_position:html:default('
					font-family: Oxygen, sans-serif;
					width: 186px;
					font-size: 12px;
					color: #282c2d'):input_type(css):input_props('with_responsive=1'):arg_name(Email block style):arg_section(3, 2, 'Email block', 'envelope')}">
					<button form="st_f" type="submit" class="$flat_btn"  data-style="
					cursor: pointer;
					outline:0;
					border: none;
					${args->email_button_style:html:default('
					font-family: Oxygen, sans-serif;
					font-size: 14px;
					padding: 5px;
					line-height: 1.3;
					background-color: #ac9166;
					color: white'):input_type(css):input_props('with_responsive=1'):arg_name(Email Button style):arg_section(3, 4, 'Email block', 'envelope')}">
						${args->button_text:default(Submit):arg_name(Button Text):arg_section(3, 3, 'Email block', 'envelope')}
					</button>
				</div>
			</div>

			<div data-case="b">
				${args->success:default(Thank you!):arg_name(Thank you text):arg_section(5, 0, 'After submit', 'check')}
			</div>
		</div>
	</div>
	<link href="https://fonts.googleapis.com/css?family=Oxygen:300,400,700" rel="stylesheet">
</div>
```


## Coupon



```
<div class="$responsive" data-style="box-sizing: border-box;
position: relative;
overflow: hidden;
${args->style:html:default('width: 500px;
height: 250px;
background-color: #10bfd2;
border: 4px dashed white'):input_type(css):input_props('with_responsive=1'):arg_name(Box style):arg_section(0, 0, 'Box', 'th-large')}">

	${block->show_close_button:default(1):arg_name(Show close button):arg_section(5, 0, 'Close Button', 'times-circle')}
	<div data-style="position:absolute; cursor:pointer; ${args->close_button_style:html:default('top:5px; right:5px;z-index:9999'):input_type(css):input_props('with_responsive=1'):arg_name(Close Button Style):arg_section(5, 1, 'Close Button', 'times-circle')}">
		${args->close_button:default('<img src="//counter.personyze.com/images/close-buttons/rect-white-orange-24x24.png" class="$personyze_button_dont_show_again" data-action_id="${action_id}">'):input_type(dontshowagain):arg_name(Close button):arg_section(5, 2, 'Close Button', 'times-circle')}
	</div>

	<div class="$switch-elem" data-case="a">
		<div data-case="a" class="$cform st_f" ontplsubmit="personyze.push(['Submit', '${action_id:html}', this._get_value_ex(), arguments[1], arguments[2]]); return true" ontplaftersubmit="this.parentNode._set_case('b', null, false, {template: 'animator_fade'}); var redir=this.dataset.redir, t=this.dataset.redirDelay; if (redir) setTimeout(function() {location.href=redir}, t*1000)" data-redir="${args->redir:html:arg_name(After submit redirect to this URL):arg_section(6, 1, 'After submit', 'check')}" data-redir-delay="${args->redir_delay:html:input_type(number):arg_name('Redirect delay, sec'):arg_section(6, 2, 'After submit', 'check')}" style="position:absolute; width:100%; height:100%">

			<div data-style="position: absolute;
			${args->title1_position:html:default('
			top: 5px;
			width: 100%;
			text-align: center'):input_type(css):input_props('with_responsive=1'):arg_name(Title1 position):arg_section(1, 1, 'Title', 'bookmark')}">
				<span data-style="
				${args->title1_text_style:html:default('
				font-size: 14px;
				color: white;
				font-style: italic;
				background-color: #06474d;
				padding: 5px 10px;
				line-height: 2;
				box-shadow: 3px 1px 4px 2px rgba(59,73,74,0.5)'):input_type(css):input_props('with_responsive=1'):arg_name(Title1 text style):arg_section(1, 2, 'Title', 'bookmark')}">${args->title1:default(Want access to exclusive discounts):arg_name(Text1):arg_section(1, 0, 'Title', 'bookmark')}</span>
			</div>

			<div data-style="position: absolute;
			width: 100%;
			${args->title_position:html:default('
			top: 35px;
			text-align: center'):input_type(css):input_props('with_responsive=1'):arg_name(Title position):arg_section(2, 3, 'Title2', 'bookmark')}">
				<div data-style="${args->title2_rotation:html:default('
				position: absolute;
				top: -10px;
				left: 10px;
				-moz-transform: rotate(-25deg);
				-ms-transform: rotate(-25deg);
				-webkit-transform: rotate(-25deg);
				-o-transform: rotate(-25deg);
				transform: rotate(-25deg)'):input_type(css):input_props('with_responsive=1'):arg_name(Title2 rotation):arg_section(2, 4, 'Title2', 'bookmark')}">
					<span data-style="font-weight: 600;
					font-style: normal;
					${args->title2_style:html:default('
					font-family: Lemonada, cursive;
					font-size: 30px;
					letter-spacing: 0;
					line-height: 1;
					color: white;
					text-shadow: 2px 2px 4px #000000'):input_type(css):input_props('with_responsive=1'):arg_name(Title2 text style):arg_section(2, 5, 'Title2', 'bookmark')}">${args->title2:default(up to):arg_name(Text2):arg_section(2, 0, 'Title2', 'bookmark')}</span>
				</div>

				<span data-style="font-weight: 600;
				font-style: normal;
				${args->title3_style:html:default('
				font-size: 70px;
				letter-spacing: 10px;
				line-height: 1;
				font-family: Luckiest Guy, cursive;
				color: white;
				text-shadow: 2px 2px 4px #000000'):input_type(css):input_props('with_responsive=1'):arg_name(Title3 text style):arg_section(2, 2, 'Title2', 'bookmark')}">${args->title3:default(70% off?):arg_name(Text3):arg_section(2, 1, 'Title2', 'bookmark')}</span>
			</div>


			<div data-style="position: absolute;
			${args->email_block_position:html:default('
			bottom: 10px;
			width: 100%;
			text-align: center'):input_type(css):input_props('with_responsive=1'):arg_name(Email block position):arg_section(3, 1, 'Email block', 'envelope')}">
				<span data-style="
				${args->email_block_text_style:html:default('
				color: #000;
				font-style: italic;
				font-size: 12px'):input_type(css):input_props('with_responsive=1'):arg_name(Email block text style):arg_section(3, 2, 'Email block', 'envelope')}">${args->email_title1:default(Enter your email below to get access to these deals):arg_name(Title1):arg_section(3, 0, 'Email block', 'envelope')}</span><br>
				<input form="st_f" name="email" data-prop-column="email" pattern="^[^\s@]+@[^\s@\.]+\.[^\s@]+$" required="1" placeholder="Enter your email here" data-style="
				outline: 0;
				border: none;
				padding: 5px 0;
				${args->email_input_style:html:default(' width: 400px;
				text-align: center;
				color:#0c0c0c'):input_type(css):input_props('with_responsive=1'):arg_name(Email block text style):arg_section(3, 3, 'Email block', 'envelope')}">
				<div><input form="st_f" type="submit" value="${args->button_tex:html:default(i want crazy deals!):arg_name(Text button):arg_section(4, 0, 'Button', 'hand-o-up')}"  data-style="cursor: pointer;
				outline:0;margin-top: 5px; padding: 15px;border: none;
				${args->button_style:html:default('
				font-size: 25px;
				width: 400px;
				background-color: #b80003;
				text-transform: uppercase;
				color: white'):input_type(css):input_props('with_responsive=1'):arg_name(Button style):arg_section(4, 1, 'Button', 'hand-o-up')}"></div>
				<a href="javascript:" data-style="${args->button_not_action_style:html:default('color: white;
				font-style: italic;
				font-size: 12px;
				text-decoration: underline'):input_type(css):input_props('with_responsive=1'):arg_name(Button not action style):arg_section(4, 2, 'Button', 'hand-o-up')}"
				class="$personyze_button_dont_show_again" data-action_id="${action_id:html}">
				${args->button_not_action_text:default('No thanks, I''d like paying full price'):arg_name(Text):arg_section(4, 3, 'Button', 'hand-o-up')}
				</a>
			</div>

		</div>

		<div data-case="b">
			${args->success:default(Thank you!):arg_name(Thank you text):arg_section(6, 0, 'After submit', 'check')}
		</div>
	</div>

	<link href="https://fonts.googleapis.com/css?family=Lemonada:600,700|Luckiest+Guy" rel="stylesheet">
</div>
```


## Survey



```
<div class="$responsive" data-style="position:relative; background-image:url(${args->bgimage_url:html:default('https://static.personyze.com/upload/4241/3c0dd06f655c428d.jpeg'):input_type(personyze_media_url):arg_name(URL):arg_section(0, 1, 'Box', 'th-large')}); ${args->style:html:default('width: sel(500px, auto);
background-size: cover;
background-position: bottom;
background-repeat: no-repeat;
box-sizing: border-box;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(0, 0, 'Box', 'th-large')}">
    <link rel="stylesheet" href="https://use.fontawesome.com/releases/v5.0.9/css/solid.css" integrity="sha384-29Ax2Ao1SMo9Pz5CxU1KMYy+aRLHmOu6hJKgWiViCYpz3f9egAJNwjnKGgr+BXDN" crossorigin="anonymous">
    <link rel="stylesheet" href="https://use.fontawesome.com/releases/v5.0.9/css/all.css" integrity="sha384-5SOiIsAziJl6AWe0HWRKTXlfcSHKmYV4RBF18PPJ173Kzn7jzMyFuTtk8JA7QQG1" crossorigin="anonymous">
    ${block->show_close_button:default(1):arg_name(Show close button):arg_section(7, 0, 'Close button', 'close')}
    <div style="position:absolute; top:16px; right:16px; z-index:1">
        ${args->close_button:default('<img src="http://counter.personyze.com/images/close-buttons/black-16x16.png" class="$personyze_button_dont_show_again" data-action_id="${action_id}" data-n_sessions="0">'):input_type(dontshowagain):arg_name(Close button):arg_section(7, 1, 'Close button', 'close')}
    </div>
    <div class="$switch-elem" data-case="a">
        <div data-case="a" class="$cform st_f" ontplsubmit="personyze.push(['Submit', '${action_id:html}', this._get_value_ex(), arguments[1], arguments[2]]); return true" ontplaftersubmit="this.parentNode._set_case('b', null, false, {template: 'animator_fade'}); var redir=this.dataset.redir, t=this.dataset.redirDelay; if (redir) setTimeout(function() {location.href=redir}, t*1000)" data-redir="${args->redir:html:arg_name(After submit redirect to this URL):arg_section(5, 2, 'After submit', 'check')}" data-redir-delay="${args->redir_delay:html:input_type(number):arg_name('Redirect delay, sec'):arg_section(5, 3, 'After submit', 'check')}">
            <div data-style="${args->title_style:html:default('padding-top: 1em;
padding-right: 0.5em;
padding-bottom: 1em;
padding-left: 0.5em;
font-family: Helvetica,san-serif;
font-size: sel(18px, 16px);
background-color: rgba(255,255,255,.5);
color: black;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(1, 1, 'Title', 'bars')}">${args->title_text:default(Have a minute? We LOVE feedbacks!):arg_name(Text):arg_section(1, 0, 'Title', 'bars')}</div>
            <div data-style="${args->rating_style:html:default('padding:.5em .5em 0; font-size:sel(48px,32px); color:white; text-shadow:0px 6px 6px rgba(0, 0, 0, 0.5)'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(2, 1, 'Rating', 'star')}">
                <input form="st_f" name="rating" type="hidden" value="0" data-prop-column="${args->rating_db:html:default(custom_i_1):input_type(select_social):input_props('with_empty=1'):arg_name(Rating save to database):arg_section(2, 0, 'Rating', 'star')}">
                <span class="$repeat-elem" data-length="5">
                    <i class="fas fa-star" onmouseover="var p = this.parentNode, c = Array.prototype.slice.call(p.parentNode.children); i = c.indexOf(p); c.map(function (item, j) { if (j) item.style.color = i >= j ? '${args->check_star_color:html:default('#ffe085'):input_type(color):arg_name(Check star color):arg_section(2, 2, 'Rating', 'star')}' : 'inherit' });" onclick="var p = this.parentNode; p.parentNode.children[0].value = Array.prototype.indexOf.call(p.parentNode.children, p);" onmouseout="var p = this.parentNode.parentNode.children, c = Array.prototype.slice.call(p); i = p[0].value; c.map(function (item, j) { if (j) item.style.color = i >= j ? '${args->check_star_color:html:default('#ffe085'):input_type(color):arg_name(Check star color):arg_section(2, 2, 'Rating', 'star')}' : 'inherit' });" style="cursor:pointer"></i>
                </span>
            </div>
            <div data-style="${args->textarea_place:html:default('padding:1em 1em 0'):input_type(css):input_props('with_responsive=1'):arg_name(Placement):arg_section(3, 3, 'Text area', 'bars')}">
                <textarea form="st_f" name="feedback" required="1" rows="${args->textarea_rows:html:default(5):input_type(number):arg_name(Rows):arg_section(3, 2, 'Text area', 'bars')}" data-style="max-width:100%; ${args->textarea_style:html:default('width:100%; font-family:Helvetica,san-serif; font-size:12px; background-color:rgba(255, 255, 255, .8); box-sizing:border-box'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(3, 4, 'Text area', 'bars')}" placeholder="${args->textarea_placeholder:html:default(How can we improve?):arg_name(Placeholder):arg_section(3, 1, 'Text area', 'bars')}" data-prop-column="${args->feedback_db:html:default(custom_t_2):input_type(select_social):input_props('with_empty=1'):arg_name(Feedback save to database):arg_section(3, 0, 'Text area', 'bars')}"></textarea>
            </div>
            <div style="white-space:nowrap">
                <div style="display:inline-block; vertical-align:top; width:50%; padding:1em; box-sizing:border-box; text-align:left">
                    <button class="$flat_btn" with_responsive="1" data-style="${args->cancel_style:html:default('padding:.5em 1em; font-family:Helvetica,san-serif; font-size:12px; background-color:white; color:gray; border:none'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(6, 1, 'Cancel button', 'times')}" hover_style="${args->cancel_h_style:html:default('background-color:gray; color:white'):input_type(css):arg_name(Hover Style):arg_section(6, 2, 'Cancel button', 'times')}" onclick="_S_T.dismiss_action(${action_id:html});">${args->cancel_text:default(Cancel):arg_name(Text):arg_section(6, 0, 'Cancel button', 'times')}</button>
                </div><div style="display:inline-block; vertical-align:top; width:50%; padding:1em; box-sizing:border-box; text-align:right">
                    <button form="st_f" type="submit" class="$flat_btn" with_responsive="1" data-style="${args->submit_style:html:default('padding:.5em 1em; font-family:Helvetica,san-serif; font-size:12px; background-color:#12ae64; color:white; border:none'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(4, 1, 'Submit button', 'check')}" hover_style="${args->submit_h_style:html:default('background-color:#189110; color:white'):input_type(css):arg_name(Hover Style):arg_section(4, 2, 'Submit button', 'check')}">${args->submit_text:default(Submit):arg_name(Text):arg_section(4, 0, 'Submit button', 'check')}</button>
                </div>
            </div>
        </div>
        <div data-case="b">
            <div data-style="${args->after_submit_style:html:default('padding:1em; font-family:Helvetica,san-serif; font-size:sel(18px, 16px); text-align:center; color:white'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(5, 1, 'After submit', 'check')}">
                ${args->success:default(Thank you!):arg_name(Thank you text):arg_section(5, 0, 'After submit', 'check')}
            </div>
        </div>
    </div>
</div>
```


## Form



```
<div class="$responsive" data-style="position:relative; background-image:url(${args->bgimage_url:html:default('https://static.personyze.com/upload/4035/73df51e772d27739.png'):input_type(personyze_media_url):arg_name(URL):arg_section(0, 1, 'Box', 'th-large')}); overflow:hidden; ${args->style:html:default('width:sel(500px, 90vw); background-size:cover; background-position:center; background-repeat:no-repeat; box-sizing:border-box; border:1px solid #a6a6a6; border-radius:4px'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(0, 0, 'Box', 'th-large')}">
    <link href="https://fonts.googleapis.com/css?family=Montserrat:400,700|Open+Sans:400,600" rel="stylesheet">
    ${block->show_close_button:default(1):arg_name(Show close button):arg_section(4, 0, 'Close button', 'close')}
    <div style="position:absolute; top:16px; right:16px; z-index:2">
        ${args->close_button:default('<img src="https://counter.personyze.com/images/close-buttons/rect-white-orange-16x16.png" style="width:16px; height:16px" class="$personyze_button_dont_show_again" data-action_id="${action_id}" data-n_sessions="0">'):input_type(dontshowagain):arg_name(Close button):arg_section(4, 1, 'Close button', 'close')}
    </div>
     <div class="$switch-elem" data-case="a" data-style="width:100%; height:100%; box-sizing:border-box; ${args->shading_style:html:default('background-color: rgba(0, 0, 0, 0.07);'):input_type(css):input_props('with_responsive=1'):arg_name(Shading):arg_section(0, 2, 'Box', 'th-large')}; ${args->send_confirm_style:html:default('padding:30px; font-family:Open Sans,san-serif; font-weight:normal; font-size:sel(18px, 14px); color:white; text-align:center'):input_type(css):input_props('with_responsive=1'):arg_name(Confirmation style):arg_section(6, 2, 'Email Box', 'envelope')}">
		<div data-case="a" class="$cform st_f" ontplsubmit="personyze.push(['Submit', '${action_id:html}', this._get_value_ex(), arguments[1], arguments[2]]); return true" ontplaftersubmit="this.parentNode._set_case('b', null, false, {template: 'animator_fade'}); var redir=this.dataset.redir, t=this.dataset.redirDelay; if (redir) setTimeout(function() {location.href=redir}, t*1000)" data-redir="${args->redir:html:default():arg_name(After submit redirect to this URL):arg_section(10, 1, 'After submit', 'check')}" data-redir-delay="${args->redir_delay:html:default():input_type(number):arg_name('Redirect delay, sec'):arg_section(10, 2, 'After submit', 'check')}" style="position:relative; width:100%; height:100%">
            <div data-style="${args->message_style:html:default('color: white;
font-family: Montserrat,san-serif;
font-weight: 700;
font-size: sel(40px, 22px);
line-height: 1;
text-align: left;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(1, 1, 'Call message', 'bars')}">
                ${args->message_text:default('Subscribe &amp; Save'):arg_name(Text):arg_section(1, 0, 'Call message', 'bars')}
            </div>
            <div data-style="${args->gift_style:html:default('margin-top:8px; color:white; font-family:Montserrat,san-serif; font-weight:400; font-size:sel(18px, 14px); line-height:1.25; text-align:left'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(2, 1, 'Gift', 'gift')}">
                ${args->gift_text:default(Save 15% OFF Your First Order):arg_name(Text):arg_section(2, 0, 'Gift', 'gift')}
            </div>
            <div>
                <div data-style="${args->content_style:html:default('margin-bottom:14px; color:white; font-family:Open Sans,san-serif; font-weight:400; font-size:sel(18px, 14px); line-height:1.25; text-align:left'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(3, 1, 'Info', 'bars')}">
                    ${args->content_text:default('Get promotions, discounts &amp; special offers'):arg_name(Text):arg_section(3, 0, 'Info', 'bars')}
                </div>

                <div data-style="${args->style7:html:default('text-align: center;
font-size: 18px;'):input_type(css):input_props('with_responsive=1'):arg_name(Fields area Style):arg_section(0, 3, 'Box', 'th-large')}">
					${block->with_f2:default(1):arg_name(With Name):arg_section(5, 0, 'Name Box', 'edit')}
					<div>
						<input form="st_f" name="Name" required="1" data-prop-column="${args->f2_db:html:default(first_name):input_type(select_social):input_props('with_empty=1'):arg_name(Name save to database):arg_section(5, 1, 'Name Box', 'edit')}" data-style="box-sizing:border-box; ${args->f1_style:html:default('margin-bottom:20px; padding:10px; font-family:Open Sans,san-serif; font-weight:600; font-size:selsel(20px, 5vw); width:100%; border:1px solid rgb(62,62,62); border-radius:4px; color:rgb(122,122,122); text-align:left'):input_type(css):input_props('with_responsive=1'):arg_name(Input style):arg_section(5, 3, 'Name Box', 'edit')}" placeholder="${args->f2:html:default(Name):arg_name(Name Placeholder Text):arg_section(5, 2, 'Name Box', 'edit')}">
					</div>
					<div>
						<input form="st_f" name="Email" pattern="^[^\s@]+@[^\s@\.]+\.[^\s@]+$" required="1" data-prop-column="${args->f3_db:html:default(email):input_type(select_social):input_props('with_empty=1'):arg_name(Email save to database):arg_section(6, 0, 'Email Box', 'envelope')}" data-style="box-sizing:border-box; ${args->f1_style:html:default('margin-bottom:20px; padding:10px; font-family:Open Sans,san-serif; font-weight:600; font-size:selsel(20px, 5vw); width:100%; border:1px solid rgb(62,62,62); border-radius:4px; color:rgb(122,122,122); text-align:left'):input_type(css):input_props('with_responsive=1'):arg_name(Input style):arg_section(5, 3, 'Name Box', 'edit')}" placeholder="${args->f3:html:default(E-Mail):arg_name(Email Placeholder Text):arg_section(6, 1, 'Email Box', 'envelope')}">
					</div>
					${block->with_f5:default(1):arg_name(With Details):arg_section(7, 0, 'Details Box', 'edit')}
					<div>
						<textarea form="st_f" name="Details" data-style="box-sizing:border-box; ${args->f5_style:html:default('margin-bottom: 20px;
padding: 10px;
font-family: Open Sans,san-serif;
font-weight: bolder;
font-size: selsel(20px, 5vw);
width: 100%;
border: 1px solid rgb(62,62,62);
border-radius: 4px;
color: rgb(122,122,122);
text-align: left;
font-size: 12px;'):input_type(css):input_props('with_responsive=1'):arg_name(Input style):arg_section(7, 2, 'Details Box', 'edit')}" placeholder="${args->f5:html:default(Details):arg_name(Details Placeholder Text):arg_section(7, 1, 'Details Box', 'edit')}"></textarea>
					</div>
					${block->with_f4:default(1):arg_name(With Checkbox):arg_section(8, 0, 'Checkbox', 'edit')}
					<div data-style="${args->style9:html:default('margin:1em 0; text-align:left; font-size:sel(14px, 4vw)'):input_type(css):input_props('with_responsive=1'):arg_name(Checkbox Style):arg_section(8, 1, 'Checkbox', 'edit')}">
						<label>
							<input form="st_f" name="Checkbox" type="checkbox" data-prop-column="${args->f4_db:html:default(custom_i_2):input_type(select_social):input_props('with_empty=1'):arg_name(Checkbox save to database):arg_section(8, 2, 'Checkbox', 'edit')}" value="1">
							${args->text_9:default(Send me newsletter):arg_name(Text):arg_section(8, 3, 'Checkbox', 'edit')}
						</label>
					</div>
				</div>

                <button form="st_f" type="submit" class="$flat_btn" with_responsive="1" style="display:block; border:0; white-space:normal; box-sizing:border-box; ${args->button_style:html:default('display:block; padding:8px 32px; font-family:Open Sans,san-serif; font-weight:normal; font-size:sel(18px, 14px); width:100%; min-height:44px; background-color:#5492dd; color:white; border-bottom:2px solid #3f75bd; border-radius:4px; text-transform:uppercase'):input_type(css):arg_name(Style):arg_section(9, 1, 'Action button', 'check')}" hover_style="${args->button_h_style:html:default('background-color:#E6E62A; border-color:#9c9c12; color:black'):input_type(css):arg_name(Hover Style):arg_section(9, 2, 'Action button', 'check')}">
					${args->button_caption:default(Get my exclusive coupon code):arg_name(Caption):arg_section(9, 0, 'Action button', 'check')}
                </button>
            </div>
        </div>
		<div data-case="b">
			${args->success:default(Thank you!):arg_name(Thank you text):arg_section(10, 0, 'After submit', 'check')}
		</div>
    </div>
</div>
```


## Form



```
<div class="$responsive" data-style="position:relative; background-image:url(${args->bgimage_url:html:input_type(personyze_media_url):arg_name(URL):arg_section(0, 1, 'Box', 'th-large')}); overflow:hidden; ${args->style:html:default('width: sel(350px, auto);
height: auto;
background-size: contain;
background-position: center;
background-repeat: no-repeat;
box-sizing: border-box;
border: 1px solid #a6a6a6;
border-radius: 4px;
background-color: rgb(253, 253, 253);
box-shadow: 0 0 3px rgb(208, 181, 181);'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(0, 0, 'Box', 'th-large')}">
    <link href="https://fonts.googleapis.com/css?family=Montserrat:400,700|Open+Sans:400,600" rel="stylesheet">
    ${block->show_close_button:default(1):arg_name(Show close button):arg_section(4, 0, 'Close button', 'close')}
    <div style="position:absolute; top:16px; right:16px; z-index:2">
        ${args->close_button:default('<img src="https://counter.personyze.com/images/close-buttons/black-16x16.png" style="width:16px; height:16px" class="$personyze_button_dont_show_again" data-action_id="${action_id}" data-n_sessions="0">'):input_type(dontshowagain):arg_name(Close button):arg_section(4, 1, 'Close button', 'close')}
    </div>
     <div class="$switch-elem" data-case="a" data-style="width:100%; height:100%; box-sizing:border-box; ${args->shading_style:html:default('background-color: rgba(175, 223, 182, 0.57);'):input_type(css):input_props('with_responsive=1'):arg_name(Shading):arg_section(0, 2, 'Box', 'th-large')}; ${args->send_confirm_style:html:default('padding:30px; font-family:Open Sans,san-serif; font-weight:normal; font-size:sel(18px, 14px); color:white; text-align:center'):input_type(css):input_props('with_responsive=1'):arg_name(Confirmation style):arg_section(6, 2, 'Email Box', 'envelope')}">
		<div data-case="a" class="$cform st_f" ontplsubmit="personyze.push(['Submit', '${action_id:html}', this._get_value_ex(), arguments[1], arguments[2]]); return true" ontplaftersubmit="this.parentNode._set_case('b', null, false, {template: 'animator_fade'}); var redir=this.dataset.redir, t=this.dataset.redirDelay; if (redir) setTimeout(function() {location.href=redir}, t*1000)" data-redir="${args->redir:html:arg_name(After submit redirect to this URL):arg_section(10, 1, 'After submit', 'check')}" data-redir-delay="${args->redir_delay:html:default(5):input_type(number):arg_name('Redirect delay, sec'):arg_section(10, 2, 'After submit', 'check')}" style="position:relative; width:100%; height:100%">
            <div data-style="${args->message_style:html:default('color: rgb(117, 97, 97);
font-family: Montserrat,san-serif;
font-weight: 700;
font-size: sel(16px, 22px);
line-height: 1;
text-align: center;
height: auto;
padding-top: 10px;
padding-right: 1px;
padding-bottom: 1px;
padding-left: 1px;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(1, 1, 'Call message', 'bars')}">
                ${args->message_text:default('<div style="text-align: center;"><span style="color:#000000;"><span style="font-size:16px;"><img src="https://static.personyze.com/upload/362/7d0a26d42b6f9a72.jpeg" style="width:0px" /><img src="https://static.personyze.com/upload/362/7d0a26d42b6f9a72.jpeg" style="width: 300px; float: center;" /><br />
<br />
ATTENTION!</span></span></div>

<table border="0" cellpadding="1" cellspacing="1" style="width: 100%;">
	<tbody>
		<tr>
			<td nowrap="nowrap" style="text-align: center;"><span style="color:#000000;"><span style="font-size:69px;">10%&nbsp;</span></span></td>
			<td>
			<p><span style="color:#000000;"><span style="font-size:25px;">ALL<br />
			GAMES&nbsp;</span></span></p>
			</td>
		</tr>
	</tbody>
</table>
<span style="font-size:14px;">UNLOCK THESE NOW</span>'):arg_name(Text):arg_section(1, 0, 'Call message', 'bars')}
            </div>
            <div data-style="${args->gift_style:html:default('margin-top:8px; color:white; font-family:Montserrat,san-serif; font-weight:400; font-size:sel(18px, 14px); line-height:1.25; text-align:left'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(2, 1, 'Gift', 'gift')}">
                ${args->gift_text:arg_name(Text):arg_section(2, 0, 'Gift', 'gift')}
            </div>
            <div>
                <div data-style="${args->content_style:html:default('margin-bottom:14px; color:white; font-family:Open Sans,san-serif; font-weight:400; font-size:sel(18px, 14px); line-height:1.25; text-align:left'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(3, 1, 'Info', 'bars')}">
                    ${args->content_text:arg_name(Text):arg_section(3, 0, 'Info', 'bars')}
                </div>

                <div data-style="${args->style7:html:default('text-align:center'):input_type(css):input_props('with_responsive=1'):arg_name(Fields area Style):arg_section(0, 3, 'Box', 'th-large')}">
					${block->with_f2:default(1):arg_name(With Name):arg_section(5, 0, 'Name Box', 'edit')}
					<div>
						<input form="st_f" name="Name" required="1" data-prop-column="${args->f2_db:html:default(first_name):input_type(select_social):input_props('with_empty=1'):arg_name(Name save to database):arg_section(5, 1, 'Name Box', 'edit')}" data-style="box-sizing:border-box; ${args->f1_style:html:default('margin-bottom:20px; padding:10px; font-family:Open Sans,san-serif; font-weight:600; font-size:selsel(20px, 5vw); width:100%; border:1px solid rgb(62,62,62); border-radius:4px; color:rgb(122,122,122); text-align:left'):input_type(css):input_props('with_responsive=1'):arg_name(Input style):arg_section(5, 3, 'Name Box', 'edit')}" placeholder="${args->f2:html:default(Name):arg_name(Name Placeholder Text):arg_section(5, 2, 'Name Box', 'edit')}">
					</div>
					<div>
						<input form="st_f" name="Email" pattern="^[^\s@]+@[^\s@\.]+\.[^\s@]+$" required="1" data-prop-column="${args->f3_db:html:default(email):input_type(select_social):input_props('with_empty=1'):arg_name(Email save to database):arg_section(6, 0, 'Email Box', 'envelope')}" data-style="box-sizing:border-box; ${args->f1_style:html:default('margin-bottom:20px; padding:10px; font-family:Open Sans,san-serif; font-weight:600; font-size:selsel(20px, 5vw); width:100%; border:1px solid rgb(62,62,62); border-radius:4px; color:rgb(122,122,122); text-align:left'):input_type(css):input_props('with_responsive=1'):arg_name(Input style):arg_section(5, 3, 'Name Box', 'edit')}" placeholder="${args->f3:html:default(E-Mail):arg_name(Email Placeholder Text):arg_section(6, 1, 'Email Box', 'envelope')}">
					</div>
					${block->with_f5:default(0):arg_name(With Details):arg_section(7, 0, 'Details Box', 'edit')}
					<div>
						<textarea form="st_f" name="Details" data-style="box-sizing:border-box; ${args->f5_style:html:input_type(css):input_props('with_responsive=1'):arg_name(Input style):arg_section(7, 2, 'Details Box', 'edit')}" placeholder="${args->f5:html:arg_name(Details Placeholder Text):arg_section(7, 1, 'Details Box', 'edit')}"></textarea>
					</div>
					${block->with_f4:default(0):arg_name(With Checkbox):arg_section(8, 0, 'Checkbox', 'edit')}
					<div data-style="${args->style9:html:input_type(css):input_props('with_responsive=1'):arg_name(Checkbox Style):arg_section(8, 1, 'Checkbox', 'edit')}">
						<label>
							<input form="st_f" name="Checkbox" type="checkbox" data-prop-column="${args->f4_db:html:input_type(select_social):input_props('with_empty=1'):arg_name(Checkbox save to database):arg_section(8, 2, 'Checkbox', 'edit')}" value="1">
							${args->text_9:arg_name(Text):arg_section(8, 3, 'Checkbox', 'edit')}
						</label>
					</div>
				</div>

                <button form="st_f" type="submit" class="$flat_btn" with_responsive="1" style="display:block; border:0; white-space:normal; box-sizing:border-box; ${args->button_style:html:default('display: block;
padding-top: 8px;
padding-right: 32px;
padding-bottom: 8px;
padding-left: 32px;
font-family: Open Sans,san-serif;
font-weight: normal;
font-size: sel(18px, 14px);
width: 100%;
min-height: 44px;
background-color: rgb(168, 26, 26);
color: white;
border-bottom: 2px solid rgba(168, 26, 26, 0.93);
border-radius: 4px;
text-transform: uppercase;'):input_type(css):arg_name(Style):arg_section(9, 1, 'Action button', 'check')}" hover_style="${args->button_h_style:html:default('background-color: rgb(101, 164, 119);
border-color: rgb(101, 164, 119);
color: rgb(249, 247, 247);'):input_type(css):arg_name(Hover Style):arg_section(9, 2, 'Action button', 'check')}">
					${args->button_caption:default(Get my secret deals):arg_name(Caption):arg_section(9, 0, 'Action button', 'check')}
                </button>
            </div>
        </div>
		<div data-case="b">
			${args->success:default('<div style="text-align: center;"><span style="color:#ffffff;">Thank you!<br />
In 5 seconds you will be redirect to the deal page, or you can click the link below&nbsp;</span><br />
<a href="http://apartmentsofmelbourne.com.au/secret"><span style="color:#ffffff;">Get your deal</span></a></div>
'):arg_name(Thank you text):arg_section(10, 0, 'After submit', 'check')}
		</div>
    </div>
</div>
```


## Form



```
<div class="$responsive" data-style="position:relative; background-image:url(${args->bgimage_url:html:default('https://static.personyze.com/upload/362/7d0a26d42b6f9a72.jpeg'):input_type(personyze_media_url):arg_name(URL):arg_section(0, 1, 'Box', 'th-large')}); overflow:hidden; ${args->style:html:default('width: sel(430px, auto);
height: auto;
background-size: cover;
background-position: center;
background-repeat: no-repeat;
box-sizing: border-box;
border: 1px solid #a6a6a6;
border-radius: 4px;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(0, 0, 'Box', 'th-large')}">
    <link href="https://fonts.googleapis.com/css?family=Montserrat:400,700|Open+Sans:400,600" rel="stylesheet">
    ${block->show_close_button:default(1):arg_name(Show close button):arg_section(4, 0, 'Close button', 'close')}
    <div style="position:absolute; top:16px; right:16px; z-index:2">
        ${args->close_button:default('<img src="https://counter.personyze.com/images/close-buttons/black-16x16.png" style="width:16px; height:16px" class="$personyze_button_dont_show_again" data-action_id="${action_id}" data-n_sessions="0">'):input_type(dontshowagain):arg_name(Close button):arg_section(4, 1, 'Close button', 'close')}
    </div>
     <div class="$switch-elem" data-case="a" data-style="width:100%; height:100%; box-sizing:border-box; ${args->shading_style:html:default('background-color: rgba(241, 43, 43, 0.84);'):input_type(css):input_props('with_responsive=1'):arg_name(Shading):arg_section(0, 2, 'Box', 'th-large')}; ${args->send_confirm_style:html:default('padding:30px; font-family:Open Sans,san-serif; font-weight:normal; font-size:sel(18px, 14px); color:white; text-align:center'):input_type(css):input_props('with_responsive=1'):arg_name(Confirmation style):arg_section(6, 2, 'Email Box', 'envelope')}">
		<div data-case="a" class="$cform st_f" ontplsubmit="personyze.push(['Submit', '${action_id:html}', this._get_value_ex(), arguments[1], arguments[2]]); return true" ontplaftersubmit="this.parentNode._set_case('b', null, false, {template: 'animator_fade'}); var redir=this.dataset.redir, t=this.dataset.redirDelay; if (redir) setTimeout(function() {location.href=redir}, t*1000)" data-redir="${args->redir:html:default():arg_name(After submit redirect to this URL):arg_section(10, 1, 'After submit', 'check')}" data-redir-delay="${args->redir_delay:html:default(5):input_type(number):arg_name('Redirect delay, sec'):arg_section(10, 2, 'After submit', 'check')}" style="position:relative; width:100%; height:100%">
            <div data-style="${args->message_style:html:default('color: white;
font-family: Montserrat,san-serif;
font-weight: 700;
font-size: sel(30px, 22px);
line-height: 1;
text-align: left;
height: auto;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(1, 1, 'Call message', 'bars')}">
                ${args->message_text:default('<span style="font-size:36px;">ATTENTION!</span>
<table border="0" cellpadding="1" cellspacing="1" style="width: 200px;">
	<tbody>
		<tr>
			<td nowrap="nowrap"><span style="font-size:130px;">6&nbsp;</span></td>
			<td>
			<p style="text-align: left;"><span style="font-size:45px;">SECRET</span><br />
			<span style="font-size: 45px;">DEALS</span><span style="font-size:45px;">&nbsp;</span></p>
			</td>
		</tr>
	</tbody>
</table>
<br />
UNLOCK THESE NOW'):arg_name(Text):arg_section(1, 0, 'Call message', 'bars')}
            </div>
            <div data-style="${args->gift_style:html:default('margin-top:8px; color:white; font-family:Montserrat,san-serif; font-weight:400; font-size:sel(18px, 14px); line-height:1.25; text-align:left'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(2, 1, 'Gift', 'gift')}">
                ${args->gift_text:default():arg_name(Text):arg_section(2, 0, 'Gift', 'gift')}
            </div>
            <div>
                <div data-style="${args->content_style:html:default('margin-bottom:14px; color:white; font-family:Open Sans,san-serif; font-weight:400; font-size:sel(18px, 14px); line-height:1.25; text-align:left'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(3, 1, 'Info', 'bars')}">
                    ${args->content_text:default():arg_name(Text):arg_section(3, 0, 'Info', 'bars')}
                </div>

                <div data-style="${args->style7:html:default('text-align:center'):input_type(css):input_props('with_responsive=1'):arg_name(Fields area Style):arg_section(0, 3, 'Box', 'th-large')}">
					${block->with_f2:default(1):arg_name(With Name):arg_section(5, 0, 'Name Box', 'edit')}
					<div>
						<input form="st_f" name="Name" required="1" data-prop-column="${args->f2_db:html:default(first_name):input_type(select_social):input_props('with_empty=1'):arg_name(Name save to database):arg_section(5, 1, 'Name Box', 'edit')}" data-style="box-sizing:border-box; ${args->f1_style:html:default('margin-bottom:20px; padding:10px; font-family:Open Sans,san-serif; font-weight:600; font-size:selsel(20px, 5vw); width:100%; border:1px solid rgb(62,62,62); border-radius:4px; color:rgb(122,122,122); text-align:left'):input_type(css):input_props('with_responsive=1'):arg_name(Input style):arg_section(5, 3, 'Name Box', 'edit')}" placeholder="${args->f2:html:default(Name):arg_name(Name Placeholder Text):arg_section(5, 2, 'Name Box', 'edit')}">
					</div>
					<div>
						<input form="st_f" name="Email" pattern="^[^\s@]+@[^\s@\.]+\.[^\s@]+$" required="1" data-prop-column="${args->f3_db:html:default(email):input_type(select_social):input_props('with_empty=1'):arg_name(Email save to database):arg_section(6, 0, 'Email Box', 'envelope')}" data-style="box-sizing:border-box; ${args->f1_style:html:default('margin-bottom:20px; padding:10px; font-family:Open Sans,san-serif; font-weight:600; font-size:selsel(20px, 5vw); width:100%; border:1px solid rgb(62,62,62); border-radius:4px; color:rgb(122,122,122); text-align:left'):input_type(css):input_props('with_responsive=1'):arg_name(Input style):arg_section(5, 3, 'Name Box', 'edit')}" placeholder="${args->f3:html:default(E-Mail):arg_name(Email Placeholder Text):arg_section(6, 1, 'Email Box', 'envelope')}">
					</div>
					${block->with_f5:default(0):arg_name(With Details):arg_section(7, 0, 'Details Box', 'edit')}
					<div>
						<textarea form="st_f" name="Details" data-style="box-sizing:border-box; ${args->f5_style:html:input_type(css):input_props('with_responsive=1'):arg_name(Input style):arg_section(7, 2, 'Details Box', 'edit')}" placeholder="${args->f5:html:arg_name(Details Placeholder Text):arg_section(7, 1, 'Details Box', 'edit')}"></textarea>
					</div>
					${block->with_f4:default(0):arg_name(With Checkbox):arg_section(8, 0, 'Checkbox', 'edit')}
					<div data-style="${args->style9:html:input_type(css):input_props('with_responsive=1'):arg_name(Checkbox Style):arg_section(8, 1, 'Checkbox', 'edit')}">
						<label>
							<input form="st_f" name="Checkbox" type="checkbox" data-prop-column="${args->f4_db:html:input_type(select_social):input_props('with_empty=1'):arg_name(Checkbox save to database):arg_section(8, 2, 'Checkbox', 'edit')}" value="1">
							${args->text_9:arg_name(Text):arg_section(8, 3, 'Checkbox', 'edit')}
						</label>
					</div>
				</div>

                <button form="st_f" type="submit" class="$flat_btn" with_responsive="1" style="display:block; border:0; white-space:normal; box-sizing:border-box; ${args->button_style:html:default('display:block; padding:8px 32px; font-family:Open Sans,san-serif; font-weight:normal; font-size:sel(18px, 14px); width:100%; min-height:44px; background-color:#5492dd; color:white; border-bottom:2px solid #3f75bd; border-radius:4px; text-transform:uppercase'):input_type(css):arg_name(Style):arg_section(9, 1, 'Action button', 'check')}" hover_style="${args->button_h_style:html:default('background-color: rgb(101, 164, 119);
border-color: rgb(101, 164, 119);
color: rgb(249, 247, 247);'):input_type(css):arg_name(Hover Style):arg_section(9, 2, 'Action button', 'check')}">
					${args->button_caption:default(Get my secret deals):arg_name(Caption):arg_section(9, 0, 'Action button', 'check')}
                </button>
            </div>
        </div>
		<div data-case="b">
			${args->success:default('<div style="text-align: center;"><span style="color:#ffffff;">Thank you!<br />
In 5 seconds you will be redirect to the deal page, or you can click the link below&nbsp;</span><br />
<a href="http://apartmentsofmelbourne.com.au/secret"><span style="color:#ffffff;">Get your deal</span></a></div>
'):arg_name(Thank you text):arg_section(10, 0, 'After submit', 'check')}
		</div>
    </div>
</div>
```


## Form with auto-populate email



```
<div class="$responsive" data-style="position:relative; background-image:url(${args->bgimage_url:html:input_type(personyze_media_url):arg_name(URL):arg_section(0, 1, 'Box', 'th-large')}); overflow:hidden; ${args->style:html:default('background-size: cover;
background-position: center;
background-repeat: no-repeat;
border-radius: 3px;
max-width: 450px;
width: sel(450px, 90%);
padding-top: 20px;
padding-right: sel(70px, 11px);
padding-bottom: 70px;
padding-left: sel(70px, 11px);
background-color: white;
box-shadow: 0 0 7px 5px rgba(189, 148, 148, 0.7);
margin-top: sel(1px, 5px);
margin-right: sel(auto, 5px);
margin-bottom: sel(1px, 5px);
margin-left: sel(auto, 5px);'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(0, 0, 'Box', 'th-large')}">
    <link href="https://fonts.googleapis.com/css?family=Montserrat:400,700|Open+Sans:400,600" rel="stylesheet">
    ${block->show_close_button:default(1):arg_name(Show close button):arg_section(4, 0, 'Close button', 'close')}
    <div style="position:absolute; top:16px; right:16px; z-index:2">
        ${args->close_button:default('<div onmouseenter="this.style.backgroundColor=this.style.outlineColor" onmouseleave="this.style.backgroundColor=this.style.textDecorationColor" style="display: inline-block; vertical-align: text-bottom; width: 28px; height: 28px; box-sizing: border-box; border-top-left-radius: 50%; border-top-right-radius: 50%; border-bottom-right-radius: 50%; border-bottom-left-radius: 50%; border: 0px solid; -webkit-box-shadow: rgba(255, 255, 255, 0.2) 0px 1px 0px inset, rgba(0, 0, 0, 0.2) 0px 1px 2px; padding: 2px; background-color: rgba(0, 0, 0, 0); text-decoration-color: rgba(0, 0, 0, 0); outline-color: rgba(206, 54, 54, 0); outline-width: 8px; color: rgb(131, 98, 98); cursor: pointer; transition: all 0.3s ease;" class="$personyze_button_dont_show_again" data-action_id="${action_id}"><div style="display: block; width: 100%; height: 100%; transition: all 0.3s ease 0s; border-top-left-radius: 50%; border-top-right-radius: 50%; border-bottom-right-radius: 50%; border-bottom-left-radius: 50%; background-image: linear-gradient(-45deg, transparent 0%, transparent 47%, currentcolor 47%, currentcolor 55%, transparent 55%, transparent 100%), linear-gradient(45deg, transparent 0%, transparent 47%, currentcolor 47%, currentcolor 55%, transparent 55%, transparent 100%);"></div></div>'):input_type(dontshowagain):arg_name(Close button):arg_section(4, 1, 'Close button', 'close')}
    </div>
     <div class="$switch-elem" id="st_sw" data-case="a" data-style="width:100%; height:100%; box-sizing:border-box; ${args->shading_style:html:default('background-color: rgb(256, 256, 256);'):input_type(css):input_props('with_responsive=1'):arg_name(Shading):arg_section(0, 2, 'Box', 'th-large')}; ${args->send_confirm_style:html:default('padding-top: 30px;
padding-right: sel(30px, 1vw);
padding-bottom: 30px;
padding-left: sel(30px, 1vw);
font-family: Open Sans,san-serif;
font-weight: normal;
font-size: sel(18px, 14px);
color: white;
text-align: center;'):input_type(css):input_props('with_responsive=1'):arg_name(Confirmation style):arg_section(7, 2, 'Email Box', 'envelope')}">
		<div data-case="a" class="$cform st_f" ontplsubmit="personyze.push(['Submit', ${action_id:json:html}, this._get_value_ex(), arguments[1], arguments[2]]); return true" ontplaftersubmit="var sw=this.parentNode; sw._set_case('b', null, false, {template: 'animator_fade'}); var js=this.dataset.customJs, redir=this.dataset.redir, t=this.dataset.redirDelay; if (js.trim()) new Function('action_id', 'by_id', 'data', 'report_error', js).call(this, ${action_id:json:html}, by_id, this._get_value()); if (redir) setTimeout(function() {location.href=redir}, t*1000)" data-custom-js="${args->customjs:html:input_type(textarea):arg_name(After submit execute this JavaScript):arg_section(11, 1, 'After submit', 'check')}" data-redir="${args->redir:html:arg_name(After submit redirect to this URL):arg_section(11, 3, 'After submit', 'check')}" data-redir-delay="${args->redir_delay:html:input_type(number):arg_name('Redirect delay, sec'):arg_section(11, 4, 'After submit', 'check')}" style="position:relative; width:100%; height:100%">
            <div data-style="${args->message_style:html:default('color: rgb(16, 9, 9);
font-family: Montserrat,san-serif;
font-weight: normal;
font-size: sel(24px, 22px);
line-height: 1;
text-align: left;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(1, 1, 'Call message', 'bars')}">
                ${args->message_text:arg_name(Text):arg_section(1, 0, 'Call message', 'bars')}
            </div>
            <div id="st_m" data-style="${args->gift_style:html:default('margin-top: 8px;
color: black;
font-family: Montserrat,san-serif;
font-weight: 600;
font-size: 20px;
line-height: 1.55;
text-align: left;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(2, 1, 'Gift', 'gift')}">
                ${args->gift_text:default(Hey! Do you want to know about our private sales? Get notified.):arg_name(Text):arg_section(2, 0, 'Gift', 'gift')}
            </div>
            <div>
                <div data-style="${args->content_style:html:default('color: rgb(25, 15, 15);
font-family: Open Sans,san-serif;
font-weight: 400;
font-size: 18px;
text-align: left;
padding-top: 15px;
padding-right: 1px;
padding-bottom: 19px;
padding-left: 1px;
line-height: 24px;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(3, 1, 'Info', 'bars')}">
                    ${args->content_text:arg_name(Text):arg_section(3, 0, 'Info', 'bars')}
                </div>

                <div data-style="${args->style7:html:default('text-align: left;
font-size: 18px;'):input_type(css):input_props('with_responsive=1'):arg_name(Fields area Style):arg_section(0, 3, 'Box', 'th-large')}">
					${block->with_f2:default(1):arg_name(With Name):arg_section(5, 0, 'Name Box', 'edit')}
					<div>
						<input form="st_f" name="Name" required="1" data-prop-column="${args->f2_db:html:default(first_name):input_type(select_social):input_props('with_empty=1'):arg_name(Name save to database):arg_section(5, 1, 'Name Box', 'edit')}" data-style="box-sizing:border-box; ${args->f1_style:html:default('margin-bottom: 20px;
padding: 15px;
font-family: Open Sans,san-serif;
font-weight: 300;
font-size: 14px;
width: sel(400px, 85%);
border: 1px solid rgb(62,62,62);
border-radius: 4px;
color: rgb(122,122,122);
text-align: left;
background-color: rgba(249, 247, 247, 0.8);'):input_type(css):input_props('with_responsive=1'):arg_name(Input style):arg_section(5, 3, 'Name Box', 'edit')}" placeholder="${args->f2:html:default(Your First Name):arg_name(Name Placeholder Text):arg_section(5, 2, 'Name Box', 'edit')}">
					</div>
					${block->with_f6:default(1):arg_name(With Telephone):arg_section(6, 0, 'Telephone Box', 'edit')}
					<div>
						<input form="st_f" name="Phone" type="tel" required="${args->f6_req:html:default(1):input_type(checkbox):arg_name(Telephone is required field):arg_section(6, 2, 'Telephone Box', 'edit')}" data-prop-column="${args->f6_db:html:input_type(select_social):input_props('with_empty=1'):arg_name(Telephone save to database):arg_section(6, 1, 'Telephone Box', 'edit')}" data-style="box-sizing:border-box; ${args->f1_style:html}" placeholder="${args->f6:html:default(Telephone):arg_name(Telephone Placeholder Text):arg_section(6, 3, 'Telephone Box', 'edit')}">
					</div>
					<div>
						<input form="st_f" name="Email" pattern="^[^\s@]+@[^\s@\.]+\.[^\s@]+$" required="1" data-prop-column="${args->f3_db:html:default(email):input_type(select_social):input_props('with_empty=1'):arg_name(Email save to database):arg_section(7, 0, 'Email Box', 'envelope')}" data-style="box-sizing:border-box; ${args->f1_style:html}" placeholder="${args->f3:html:default(Enter your email address):arg_name(Email Placeholder Text):arg_section(7, 1, 'Email Box', 'envelope')}" value="${email:html}" ontplready="this.value=this.value.trim()">
					</div>
					${block->with_f5:default(0):arg_name(With Details):arg_section(8, 0, 'Details Box', 'edit')}
					<div>
						<textarea form="st_f" name="Details" data-style="box-sizing:border-box; ${args->f5_style:html:input_type(css):input_props('with_responsive=1'):arg_name(Input style):arg_section(8, 2, 'Details Box', 'edit')}" placeholder="${args->f5:html:arg_name(Details Placeholder Text):arg_section(8, 1, 'Details Box', 'edit')}"></textarea>
					</div>
					${block->with_f4:default(0):arg_name(With Checkbox):arg_section(9, 0, 'Checkbox', 'edit')}
					<div data-style="${args->style9:html:default('color: rgb(199, 179, 179);
font-size: 12px;
text-align: left;'):input_type(css):input_props('with_responsive=1'):arg_name(Checkbox Style):arg_section(9, 1, 'Checkbox', 'edit')}">
						<label>
							<input form="st_f" name="Checkbox" type="checkbox" data-prop-column="${args->f4_db:html:input_type(select_social):input_props('with_empty=1'):arg_name(Checkbox save to database):arg_section(9, 2, 'Checkbox', 'edit')}" value="1">
							${args->text_9:arg_name(Text):arg_section(9, 3, 'Checkbox', 'edit')}
						</label>
					</div>
				</div>

                <button form="st_f" type="submit" class="$flat_btn" with_responsive="1" style="display:block; border:0; white-space:normal; box-sizing:border-box; ${args->button_style:html:default('display: block;
padding-top: 12px;
padding-right: 20px;
padding-bottom: 12px;
padding-left: 20px;
font-family: Open Sans,san-serif;
background-color: #a30001;
color: white;
border-radius: 50px;
text-transform: uppercase;
letter-spacing: 2px;
height: 45px;
width: 220px;
margin-top: 10px;
margin-right: 0px;
margin-bottom: 40px;
margin-left: 0px;'):input_type(css):arg_name(Style):arg_section(10, 1, 'Action button', 'check')}" hover_style="${args->button_h_style:html:default('display: block;
padding-top: 15px;
padding-right: 35px;
padding-bottom: 15px;
padding-left: 35px;
font-family: Open Sans,san-serif;
background-color: #111111;
color: #FFFFFF;
border-radius: 50px;
text-transform: uppercase;
letter-spacing: 2px;'):input_type(css):arg_name(Hover Style):arg_section(10, 2, 'Action button', 'check')}">
					${args->button_caption:default(Contact me):arg_name(Caption):arg_section(10, 0, 'Action button', 'check')}
                </button>
            </div>
			<div data-style="${args->style9:html}">
				${args->ds:default('We are GDPR compliant and will not spam you. By clicking the above button, you agree to our&nbsp;<b><a data-saferedirecturl="https://www.google.com/url?q=https://www.abbotsfordchrysler.com/privacy-policy/&amp;source=gmail&amp;ust=1559168237409000&amp;usg=AFQjCNHZwC-vxhrIxYb-rjytZTwobPcUrA" href="https://www.abbotsfordchrysler.com/privacy-policy/" target="_blank">Privacy Policy</a></b>.'):arg_name(No text):arg_section(2, 2, 'Gift', 'gift')}
			</div>
        </div>
		<div data-case="b" id="st_b" data-style="${args->style10:html:default('color: rgb(199, 179, 179);'):input_type(css):input_props('with_responsive=1'):arg_name(Thank you text Style):arg_section(11, 2, 'After submit', 'check')}">
			${args->success:default('<div style="text-align: center; font-size: 30px; ">Awesome! We will keep you posted.</div>
'):arg_name(Thank you text):arg_section(11, 0, 'After submit', 'check')}
		</div>
    </div>
</div>
```


## Form



```
<div class="$responsive" data-style="position:relative; background-image:url(${args->bgimage_url:html:default('https://www.abbotsfordchrysler.com/wp-content/uploads/2019/04/AC-RAM1500-Features-ComfortDriving.jpg'):input_type(personyze_media_url):arg_name(URL):arg_section(0, 1, 'Box', 'th-large')}); overflow:hidden; ${args->style:html:default('width: sel(600px, 90vw);
background-size: cover;
background-position: center;
background-repeat: no-repeat;
box-sizing: border-box;
border: 1px solid #a6a6a6;
border-radius: 4px;
background-color: rgba(0, 0, 0, 0.7);'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(0, 0, 'Box', 'th-large')}">
    <link href="https://fonts.googleapis.com/css?family=Montserrat:400,700|Open+Sans:400,600" rel="stylesheet">
    ${block->show_close_button:default(1):arg_name(Show close button):arg_section(4, 0, 'Close button', 'close')}
    <div style="position:absolute; top:16px; right:16px; z-index:2">
        ${args->close_button:default('<img src="https://counter.personyze.com/images/close-buttons/rect-white-orange-16x16.png" style="width:16px; height:16px" class="$personyze_button_dont_show_again" data-action_id="${action_id}" data-n_sessions="0">'):input_type(dontshowagain):arg_name(Close button):arg_section(4, 1, 'Close button', 'close')}
    </div>
     <div class="$switch-elem" data-case="a" data-style="width:100%; height:100%; box-sizing:border-box; ${args->shading_style:html:default('background-color: rgba(0, 0, 0, 0.07);'):input_type(css):input_props('with_responsive=1'):arg_name(Shading):arg_section(0, 2, 'Box', 'th-large')}; ${args->send_confirm_style:html:default('padding:30px; font-family:Open Sans,san-serif; font-weight:normal; font-size:sel(18px, 14px); color:white; text-align:center'):input_type(css):input_props('with_responsive=1'):arg_name(Confirmation style):arg_section(7, 2, 'Email Box', 'envelope')}">
		<div data-case="a" class="$cform st_f" ontplsubmit="personyze.push(['Submit', '${action_id:html}', this._get_value_ex(), arguments[1], arguments[2]]); return true" ontplaftersubmit="this.parentNode._set_case('b', null, false, {template: 'animator_fade'}); var redir=this.dataset.redir, t=this.dataset.redirDelay; if (redir) setTimeout(function() {location.href=redir}, t*1000)" data-redir="${args->redir:html:arg_name(After submit redirect to this URL):arg_section(11, 1, 'After submit', 'check')}" data-redir-delay="${args->redir_delay:html:input_type(number):arg_name('Redirect delay, sec'):arg_section(11, 2, 'After submit', 'check')}" style="position:relative; width:100%; height:100%">
            <div data-style="${args->message_style:html:default('color: white;
font-family: Montserrat,san-serif;
font-weight: 700;
font-size: sel(40px, 22px);
line-height: 1;
text-align: left;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(1, 1, 'Call message', 'bars')}">
                ${args->message_text:default(Title):arg_name(Text):arg_section(1, 0, 'Call message', 'bars')}
            </div>
            <div data-style="${args->gift_style:html:default('margin-top: 8px;
color: white;
font-family: Montserrat,san-serif;
font-weight: 900;
font-size: sel(18px, 14px);
line-height: 1.25;
text-align: left;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(2, 1, 'Gift', 'gift')}">
                ${args->gift_text:default(Sub Title):arg_name(Text):arg_section(2, 0, 'Gift', 'gift')}
            </div>
            <div>
                <div data-style="${args->content_style:html:default('margin-bottom: 14px;
color: white;
font-family: Open Sans,san-serif;
font-weight: 800;
font-size: sel(12px, 14px);
line-height: 1.25;
text-align: left;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(3, 1, 'Info', 'bars')}">
                    ${args->content_text:arg_name(Text):arg_section(3, 0, 'Info', 'bars')}
                </div>

                <div data-style="${args->style7:html:default('text-align: center;
font-size: 18px;'):input_type(css):input_props('with_responsive=1'):arg_name(Fields area Style):arg_section(0, 3, 'Box', 'th-large')}">
					${block->with_f2:default(1):arg_name(With Name):arg_section(5, 0, 'Name Box', 'edit')}
					<div>
						<input form="st_f" name="Name" required="1" data-prop-column="${args->f2_db:html:default(first_name):input_type(select_social):input_props('with_empty=1'):arg_name(Name save to database):arg_section(5, 1, 'Name Box', 'edit')}" data-style="box-sizing:border-box; ${args->f1_style:html:default('margin-bottom:20px; padding:10px; font-family:Open Sans,san-serif; font-weight:600; font-size:selsel(20px, 5vw); width:100%; border:1px solid rgb(62,62,62); border-radius:4px; color:rgb(122,122,122); text-align:left'):input_type(css):input_props('with_responsive=1'):arg_name(Input style):arg_section(5, 3, 'Name Box', 'edit')}" placeholder="${args->f2:html:default(Name):arg_name(Name Placeholder Text):arg_section(5, 2, 'Name Box', 'edit')}">
					</div>
					${block->with_f6:default(1):arg_name(With Telephone):arg_section(6, 0, 'Telephone Box', 'edit')}
					<div>
						<input form="st_f" name="Phone" type="tel" required="${args->f6_req:html:default(1):input_type(checkbox):arg_name(Telephone is required field):arg_section(6, 2, 'Telephone Box', 'edit')}" data-prop-column="${args->f6_db:html:default():input_type(select_social):input_props('with_empty=1'):arg_name(Telephone save to database):arg_section(6, 1, 'Telephone Box', 'edit')}" data-style="box-sizing:border-box; ${args->f1_style:html}" placeholder="${args->f6:html:default(Telephone):arg_name(Telephone Placeholder Text):arg_section(6, 3, 'Telephone Box', 'edit')}">
					</div>
					<div>
						<input form="st_f" name="Email" pattern="^[^\s@]+@[^\s@\.]+\.[^\s@]+$" required="1" data-prop-column="${args->f3_db:html:default(email):input_type(select_social):input_props('with_empty=1'):arg_name(Email save to database):arg_section(7, 0, 'Email Box', 'envelope')}" data-style="box-sizing:border-box; ${args->f1_style:html}" placeholder="${args->f3:html:default(E-Mail):arg_name(Email Placeholder Text):arg_section(7, 1, 'Email Box', 'envelope')}">
					</div>
					${block->with_f5:default(0):arg_name(With Details):arg_section(8, 0, 'Details Box', 'edit')}
					<div>
						<textarea form="st_f" name="Details" data-style="box-sizing:border-box; ${args->f5_style:html:input_type(css):input_props('with_responsive=1'):arg_name(Input style):arg_section(8, 2, 'Details Box', 'edit')}" placeholder="${args->f5:html:arg_name(Details Placeholder Text):arg_section(8, 1, 'Details Box', 'edit')}"></textarea>
					</div>
					${block->with_f4:default(0):arg_name(With Checkbox):arg_section(9, 0, 'Checkbox', 'edit')}
					<div data-style="${args->style9:html:input_type(css):input_props('with_responsive=1'):arg_name(Checkbox Style):arg_section(9, 1, 'Checkbox', 'edit')}">
						<label>
							<input form="st_f" name="Checkbox" type="checkbox" data-prop-column="${args->f4_db:html:input_type(select_social):input_props('with_empty=1'):arg_name(Checkbox save to database):arg_section(9, 2, 'Checkbox', 'edit')}" value="1">
							${args->text_9:arg_name(Text):arg_section(9, 3, 'Checkbox', 'edit')}
						</label>
					</div>
				</div>

                <button form="st_f" type="submit" class="$flat_btn" with_responsive="1" style="display:block; border:0; white-space:normal; box-sizing:border-box; ${args->button_style:html:default('display:block; padding:8px 32px; font-family:Open Sans,san-serif; font-weight:normal; font-size:sel(18px, 14px); width:100%; min-height:44px; background-color:#5492dd; color:white; border-bottom:2px solid #3f75bd; border-radius:4px; text-transform:uppercase'):input_type(css):arg_name(Style):arg_section(10, 1, 'Action button', 'check')}" hover_style="${args->button_h_style:html:default('background-color: #FFFFFF;
border-color: #5492dd;
color: #5492dd;'):input_type(css):arg_name(Hover Style):arg_section(10, 2, 'Action button', 'check')}">
					${args->button_caption:default(CONTACT ME):arg_name(Caption):arg_section(10, 0, 'Action button', 'check')}
                </button>
            </div>
        </div>
		<div data-case="b">
			${args->success:default('<div style="text-align: center; font-size:30px ;">Thank you! We will schedule you in.</div>
'):arg_name(Thank you text):arg_section(11, 0, 'After submit', 'check')}
		</div>
    </div>

    ${args->footer:default('<p style="color: #ffffff; padding: 35px; text-size: 10px;">We will try to meet your preferred date and time. We are GDPR compliant and will not spam you. By clicking the above button, you agree to our <a data-saferedirecturl="https://www.google.com/url?q=https://www.abbotsfordchrysler.com/privacy-policy/&amp;source=gmail&amp;ust=1559168237409000&amp;usg=AFQjCNHZwC-vxhrIxYb-rjytZTwobPcUrA" href="https://www.abbotsfordchrysler.com/privacy-policy/" style="color:#fff;" target="_blank"><b>Privacy Policy</b></a>.</p>
'):arg_name(Footer):arg_section(12, 0, 'Footer', 'bars')}

</div>
```


## Form survey



```
<div class="$responsive" data-style="position:relative; background-image:url(${args->bgimage_url:html:input_type(personyze_media_url):arg_name(URL):arg_section(0, 1, 'Box', 'th-large')}); ${args->style:html:default('width: sel(500px, auto);
background-position: bottom;
background-repeat: no-repeat;
background-color: white;
padding: 30px;
border-radius: 10px;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(0, 0, 'Box', 'th-large')}">
	${block->show_close_button:default(1):arg_name(Show close button):arg_section(8, 0, 'Close button', 'close')}
	<div style="position:absolute; top:16px; right:16px; z-index:1">
		${args->close_button:default('<a href="javascript:" style="font-size: 24px; color: rgba(0, 0, 0, 0.39); font-weight: bold; line-height: 1; text-decoration: none;" class="$personyze_button_dont_show_again" data-action_id="${action_id}">×</a>'):input_type(dontshowagain):arg_name(Close button):arg_section(8, 1, 'Close button', 'close')}
	</div>
	<div class="$switch-elem" data-case="a">
		<div data-case="a" class="$cform st_f" ontplsubmit="personyze.push(['Submit', '${action_id:html}', this._get_value_ex(), arguments[1], arguments[2]]); return true" ontplaftersubmit="this.parentNode._set_case('b', null, false, {template: 'animator_fade'}); var redir=this.dataset.redir, t=this.dataset.redirDelay; if (redir) setTimeout(function() {location.href=redir}, t*1000)" data-redir="${args->redir:html:arg_name(After submit redirect to this URL):arg_section(6, 2, 'After submit', 'check')}" data-redir-delay="${args->redir_delay:html:input_type(number):arg_name('Redirect delay, sec'):arg_section(6, 3, 'After submit', 'check')}">
			<div data-style="${args->title_style:html:default('padding-top: 1em;
padding-right: 0.5em;
padding-bottom: 1em;
padding-left: 0.5em;
font-family: Helvetica,san-serif;
font-size: sel(18px, 16px);
color: rgba(0, 0, 0, 0.89);'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(1, 1, 'Title', 'bars')}">${args->title_text:default('<div style="text-align: center;"><span style="font-size:22px;">Tell us how we can improve?</span></div>
'):arg_name(Text):arg_section(1, 0, 'Title', 'bars')}</div>

			${block->with_rating:default(1):arg_name(With Rating):arg_section(2, 0, 'Rating', 'star')}
			<div data-style="${args->rating_style:html:default('font-size: 22px;
padding: 10;
margin-top: 1px;
margin-right: 1px;
margin-bottom: 13px;
margin-left: 1px;
color: rgb(214, 225, 221);'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(2, 2, 'Rating', 'star')}">
				<input form="st_f" name="rating" type="hidden" value="0" data-prop-column="${args->rating_db:html:default(account_lifetime_value):input_type(select_social):input_props('with_empty=1'):arg_name(Rating save to database):arg_section(2, 1, 'Rating', 'star')}">
				<span class="$repeat-elem" data-length="5">
					<b onmouseover="var p = this.parentNode, c = Array.prototype.slice.call(p.parentNode.children); i = c.indexOf(p); c.map(function (item, j) { if (j) item.style.color = i >= j ? '${args->check_star_color:html:default('#ffe085'):input_type(color):arg_name(Check star color):arg_section(2, 3, 'Rating', 'star')}' : 'inherit' });" onclick="var p = this.parentNode; p.parentNode.children[0].value = Array.prototype.indexOf.call(p.parentNode.children, p);" onmouseout="var p = this.parentNode.parentNode.children, c = Array.prototype.slice.call(p); i = p[0].value; c.map(function (item, j) { if (j) item.style.color = i >= j ? '${args->check_star_color:html}' : 'inherit' });" style="cursor:pointer">${args->star:default('★'):arg_name(Star Glyph):arg_section(2, 4, 'Rating', 'star')}</b>
				</span>
			</div>

			${block->with_email:default(1):arg_name(With Email Box):arg_section(3, 0, 'Email Box', 'envelope')}
			<div data-style="${args->email_place:html:default('margin-top: 0px;
margin-right: 0px;
margin-bottom: 0.6em;
margin-left: 0px;'):input_type(css):input_props('with_responsive=1'):arg_name(Placement):arg_section(3, 3, 'Email Box', 'envelope')}">
				<input form="st_f" name="Email" pattern="^[^\s@]+@[^\s@\.]+\.[^\s@]+|$" ${args->email_req:default('required="1"'):input_type(checkbox):input_props('value_on=required="1"','value_off='):arg_name(Email is required field):arg_section(3, 4, 'Email Box', 'envelope')} data-prop-column="${args->email_db:html:default(email):input_type(select_social):input_props('with_empty=1'):arg_name(Email save to database):arg_section(3, 1, 'Email Box', 'envelope')}" data-style="box-sizing:border-box; ${args->input_style:html:default('padding: 15px;
font-family: Open Sans,san-serif;
font-weight: 300;
font-size: 14px;
width: 100%;
border: 1px solid rgb(62,62,62);
border-radius: 4px;
color: rgb(122,122,122);
text-align: left;
background-color: rgba(249, 247, 247, 0.8);'):input_type(css):input_props('with_responsive=1'):arg_name(Input style):arg_section(0, 3, 'Box', 'th-large')}" placeholder="${args->email:html:default(Enter your email address):arg_name(Email Placeholder Text):arg_section(3, 2, 'Email Box', 'envelope')}" value="${email:html}" ontplready="this.value=this.value.trim()">
			</div>

			${block->with_textarea:default(1):arg_name(With Textarea):arg_section(4, 0, 'Text area', 'bars')}
			<div data-style="${args->textarea_place:html:input_type(css):input_props('with_responsive=1'):arg_name(Placement):arg_section(4, 4, 'Text area', 'bars')}">
				<textarea form="st_f" name="feedback" ${args->textarea_req:default('required="1"'):input_type(checkbox):input_props('value_on=required="1"','value_off='):arg_name(Textarea is required field):arg_section(4, 6, 'Text area', 'bars')} rows="${args->textarea_rows:html:default(5):input_type(number):arg_name(Rows):arg_section(4, 3, 'Text area', 'bars')}" data-style="max-width:100%; box-sizing:border-box; ${args->input_style:html}; ${args->textarea_style:html:input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(4, 5, 'Text area', 'bars')}" placeholder="${args->textarea_placeholder:html:default(How can we improve?):arg_name(Placeholder):arg_section(4, 2, 'Text area', 'bars')}" data-prop-column="${args->feedback_db:html:default(account_lifetime_value):input_type(select_social):input_props('with_empty=1'):arg_name(Feedback save to database):arg_section(4, 1, 'Text area', 'bars')}"></textarea>
			</div>
			<div style="display:flex; align-items:center; ${args->button_box_style:html:default('justify-content: center;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(0, 2, 'Box', 'th-large')}">
				<button class="$flat_btn" with_responsive="1" data-style="${args->cancel_style:html:default('margin:1em; padding:.5em 1em; font-family:Helvetica,san-serif; font-size:12px; background-color:white; color:gray; border:none'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(7, 1, 'Cancel button', 'times')}" hover_style="${args->cancel_h_style:html:default('background-color:gray; color:white'):input_type(css):arg_name(Hover Style):arg_section(7, 2, 'Cancel button', 'times')}" onclick="_S_T.dismiss_action(${action_id:html});">${args->cancel_text:default(Cancel):arg_name(Text):arg_section(7, 0, 'Cancel button', 'times')}</button>
				<button form="st_f" type="submit" class="$flat_btn" with_responsive="1" data-style="${args->submit_style:html:default('margin:1em; padding-top: .5em;
padding-right: 1em;
padding-bottom: .5em;
padding-left: 1em;
font-family: Helvetica,san-serif;
font-size: 12px;
background-color: #12ae64;
color: white;
border: none;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(5, 1, 'Submit button', 'check')}" hover_style="${args->submit_h_style:html:default('background-color:#189110; color:white'):input_type(css):arg_name(Hover Style):arg_section(5, 2, 'Submit button', 'check')}">${args->submit_text:default(Submit):arg_name(Text):arg_section(5, 0, 'Submit button', 'check')}</button>
			</div>
		</div>
		<div data-case="b">
			<div data-style="${args->after_submit_style:html:default('padding:1em; font-family:Helvetica,san-serif; font-size:sel(18px, 16px); text-align:center; color:black'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(6, 1, 'After submit', 'check')}">
				${args->success:default(Thank you!):arg_name(Thank you text):arg_section(6, 0, 'After submit', 'check')}
			</div>
		</div>
	</div>
</div>
```


## Form



```
<div class="$responsive" data-style="${args->style:html:default('width: sel(380px, auto);
font-family: sans-serif;
background-color: white;
font-size: sel(26px, 5vw);'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(0, 0, 'Box', 'th-large')}">
	<table data-style="border-collapse:collapse; width:100%; ${args->style2:html:default('background-color: rgb(113, 164, 107);
color: white;
text-align: center;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(1, 0, 'Title bar', 'bookmark')}">
		<tr>
			<td data-style="width:99%; ${args->style4:html:default('font-size: 115%;
padding: 0.3em;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(1, 1, 'Title bar', 'bookmark')}">
				${block->logo:default(1):arg_name(With logo):arg_section(1, 2, 'Title bar', 'bookmark')}
				<img src="${args->logo_src:html:default('https://cdn.personyze.com/upload/362/185f3236b1b4ab52.png'):input_type(personyze_media_url):arg_name(Logo URL):arg_section(1, 3, 'Title bar', 'bookmark')}" data-style="vertical-align:middle; ${args->image_style:html:default('width:auto; height:auto; max-height:sel(30px, 8vw); border:none; margin:0 0.2em'):input_type(css):input_props('with_responsive=1'):arg_name(Logo size):arg_section(1, 4, 'Title bar', 'bookmark')}">
				${block->title:default(0):arg_name(With Title Text):arg_section(1, 5, 'Title bar', 'bookmark')}
				<span>
					${args->title:arg_name(Text):arg_section(1, 6, 'Title bar', 'bookmark')}
				</span>
			</td>
			${block->x:default(1):arg_name('With [x]'):arg_section(1, 7, 'Title bar', 'bookmark')}
			<td style="padding:0">
				<a href="javascript:" class="$personyze_button_dont_show_again" data-action_id="${action_id:html}" data-style="cursor:pointer; border:2px solid; border-radius:50%; line-height:1; width:1em; float:right; color:inherit; text-decoration:none; ${args->x_style:html:default('text-decoration: none;
margin-top: 0;
margin-right: 0.6em;
margin-bottom: 0;
margin-left: 0;
line-height: 0.9em;
height: 1em;
width: 1em;'):input_type(css):input_props('with_responsive=1'):arg_name('[x] position'):arg_section(1, 8, 'Title bar', 'bookmark')}">×</a>
			</td>
		</tr>
	</table>
	 <div class="$switch-elem" data-case="a">
		<div data-case="a" class="$cform st_f" ontplsubmit="personyze.push(['Submit', '${action_id:html}', this._get_value_ex(), arguments[1], arguments[2]]); return true" ontplaftersubmit="this.parentNode._set_case('b', null, false, {template: 'animator_fade'}); var redir=this.dataset.redir, t=this.dataset.redirDelay; if (redir) setTimeout(function() {location.href=redir}, t*1000)" data-redir="${args->redir:html:arg_name(After submit redirect to this URL):arg_section(8, 1, 'After submit', 'check')}" data-redir-delay="${args->redir_delay:html:input_type(number):arg_name('Redirect delay, sec'):arg_section(8, 2, 'After submit', 'check')}">
			<div data-style="${args->style3:html:default('margin:1.7em'):input_type(css):input_props('with_responsive=1'):arg_name(Box Style):arg_section(2, 0, 'Content Box', 'bars')}">
				${block->line_1:default(1):arg_name(With Line 1):arg_section(2, 1, 'Content Box', 'bars')}
				<div data-style="${args->style5:html:default('font-size:125%; text-align:center'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(2, 2, 'Content Box', 'bars')}">
					${args->text_2:default(Title Goes Here):arg_name(Text):arg_section(2, 3, 'Content Box', 'bars')}
				</div>
				<div data-style="${args->style6:html:default('text-align: center;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(2, 4, 'Content Box', 'bars')}">
					${args->text_3:default(Your description goes here Your description goes here):arg_name(Text):arg_section(2, 5, 'Content Box', 'bars')}
				</div>
			</div>
			<div data-style="${args->style7:html:default('margin-top: 1em;
margin-right: 1em;
margin-bottom: 0em;
margin-left: 1em;
text-align: left;
max-width: 90%;'):input_type(css):input_props('with_responsive=1'):arg_name(Fields area Style):arg_section(2, 6, 'Content Box', 'bars')}">
				${block->with_f2:default(1):arg_name(With Name):arg_section(3, 0, 'Name Box', 'edit')}
				<div>
					<input form="st_f" name="Name" required="1" data-prop-column="${args->f2_db:html:default(first_name):input_type(select_social):input_props('with_empty=1'):arg_name(Name save to database):arg_section(3, 1, 'Name Box', 'edit')}" data-style="${args->f1_style:html:default('margin-bottom: 0.5em;
width: auto;
padding: 0.5em;
text-align: left;
font-size: sel(20px, 5vw);
background-color: rgb(249, 241, 241);
border-radius: 3px;
border-style: ridge;'):input_type(css):input_props('with_responsive=1'):arg_name(Input style):arg_section(3, 3, 'Name Box', 'edit')}" placeholder="${args->f2:html:default(Name):arg_name(Name Placeholder Text):arg_section(3, 2, 'Name Box', 'edit')}">
				</div>
				<div>
					<input form="st_f" name="Email" pattern="^[^\s@]+@[^\s@\.]+\.[^\s@]+$" required="1" data-prop-column="${args->f3_db:html:default(email):input_type(select_social):input_props('with_empty=1'):arg_name(Email save to database):arg_section(4, 0, 'Email Box', 'edit')}" data-style="${args->f1_style:html}" placeholder="${args->f3:html:default(E-Mail):arg_name(Email Placeholder Text):arg_section(4, 1, 'Email Box', 'edit')}">
				</div>
				${block->with_f5:default(1):arg_name(With Details):arg_section(6, 0, 'Details Box', 'edit')}
				<div>
					<textarea form="st_f" name="Details" data-style="${args->f5_style:html:default('margin-bottom: 0.5em;
width: auto;
padding: 0.5em;
text-align: left;
font-size: sel(20px, 5vw);
background-color: rgb(249, 241, 241);
border-radius: 3px;
border-style: ridge;'):input_type(css):input_props('with_responsive=1'):arg_name(Input style):arg_section(6, 2, 'Details Box', 'edit')}" placeholder="${args->f5:html:default(Details):arg_name(Details Placeholder Text):arg_section(6, 1, 'Details Box', 'edit')}"></textarea>
				</div>
				${block->with_f4:default(0):arg_name(With Checkbox):arg_section(5, 0, 'Checkbox', 'edit')}
				<div data-style="${args->style9:html:input_type(css):input_props('with_responsive=1'):arg_name(Checkbox Style):arg_section(5, 1, 'Checkbox', 'edit')}">
					<label>
						<input form="st_f" name="Checkbox" type="checkbox" data-prop-column="${args->f4_db:html:input_type(select_social):input_props('with_empty=1'):arg_name(Checkbox save to database):arg_section(5, 2, 'Checkbox', 'edit')}" value="1">
						${args->text_9:arg_name(Text):arg_section(5, 3, 'Checkbox', 'edit')}
					</label>
				</div>
			</div>
			<div data-style="text-align:center; ${args->style8:html:default('padding-top: 0;
padding-right: 0;
padding-bottom: 1em;
padding-left: 0;
width: 100%;
font-size: 17px;
color: rgb(255, 256, 256);'):input_type(css):input_props('with_responsive=1'):arg_name(Buttons Box Style):arg_section(7, 0, 'Buttons', 'hand-o-up')}">
				<span>
					<button form="st_f" type="submit" class="$flat_btn" with_responsive="1" href="${args->href_2:html:default('#'):arg_name(Button 1 URL):arg_section(7, 9, 'Buttons', 'hand-o-up')}" target="${args->target_2:html:default(_self):input_type(a_target):arg_name(Button 1 Open link in):arg_section(7, 10, 'Buttons', 'hand-o-up')}" data-style="font-size:inherit; width:${args->button_width:html:default(0px):input_type(css_length):input_props('with_responsive=1'):arg_name(Button Width):arg_section(7, 7, 'Buttons', 'hand-o-up')}; line-height:1; padding:${args->button_padding:html:default(10px):input_type(css_length):input_props('with_responsive=1'):arg_name(Button Height):arg_section(7, 8, 'Buttons', 'hand-o-up')}; ${args->yes_style:html:default('box-shadow: 0 2px 10px 0 rgba(0,0,0,0.15);
font-family: "Product Sans",Arial,sans-serif;
font-size: 16px;
font-weight: 500;
height: auto;
line-height: 16px;
min-width: 76px;
padding-top: 10px;
padding-right: 24px;
padding-bottom: 10px;
padding-left: 24px;
text-transform: none;
background-color: #448aff;
color: rgb(252, 244, 244);'):input_type(css):arg_name(Yes Button Style):arg_section(7, 2, 'Buttons', 'hand-o-up')}" hover_style="${args->yes_h_style:html:default('box-shadow: 0 2px 10px 0 rgba(0,0,0,0.15);
font-family: "Product Sans",Arial,sans-serif;
font-size: 16px;
font-weight: 500;
height: auto;
line-height: 16px;
min-width: 76px;
padding-top: 10px;
padding-right: 24px;
padding-bottom: 10px;
padding-left: 24px;
text-transform: none;
background-color: rgb(41, 199, 51);'):input_type(css):arg_name(Yes Button Hover Style):arg_section(7, 3, 'Buttons', 'hand-o-up')}">
						${args->yes_1:default(SUBMIT):arg_name(Yes button text):arg_section(7, 1, 'Buttons', 'hand-o-up')}
					</button>
				</span>
				${block->button_2:default(0):arg_name(With Second Button):arg_section(7, 4, 'Buttons', 'hand-o-up')}
				<span>
					<a class="$flat_btn $personyze_button_dont_show_again" data-disabled="1" href="javascript:" data-action_id="${action_id:html}" data-style="display:inline-block; vertical-align:middle; width:${args->button_width:html}; line-height:1; padding:${args->button_padding:html}; text-decoration:none; ${args->no_style:html:input_type(css):arg_name(No Button Style):arg_section(7, 6, 'Buttons', 'hand-o-up')}">
						${args->no_1:arg_name(No button text):arg_section(7, 5, 'Buttons', 'hand-o-up')}
					</a>
				</span>
			</div>
		</div>
		<div data-case="b">
			${args->success:default(Thank you!):arg_name(Thank you text):arg_section(8, 0, 'After submit', 'check')}
		</div>
	</div>
</div>
```


## Form



```
<table class="$responsive" style="background-color:transparent; border-collapse:separate; border-spacing:${args->gap:html:default(0.4em):input_type(css_length):input_props('with_responsive=1'):arg_name(Margin):arg_section(0, 1, 'Box', 'th-large')}" onupdate="var i, a=ns.joyquery('child::*>*>td>button', this).get(); for (i=0; i!=a.length; i++) a[i].style.borderRadius=by_id.div.style.borderRadius">
	<tbody class="$cform st_f" ontplsubmit="personyze.push(['Submit', '${action_id:html}', this._get_value_ex(), arguments[1], arguments[2]]); return true" ontplaftersubmit="
		for (var e, i=_S_T.joyquery('.st_f1, child::tr:from(2)', this); e=i();) e.style.display='none';
		_S_T.joyquery('.st_f2', this).get(0).style.display='';
		var redir=this.dataset.redir, t=this.dataset.redirDelay;
		if (redir) setTimeout(function() {location.href=redir}, t*1000);
	" data-redir="${args->redir:html:arg_name(After submit redirect to this URL):arg_section(7, 0)}" data-redir-delay="${args->redir_delay:html:input_type(number):arg_name('Redirect delay, sec'):arg_section(7, 1)}">
		<tr>
			<td>
				<input form="st_f" class="st_f0" type="hidden" name="Field" data-prop-column="${args->field_name:html:default():input_type(select_social):input_props('with_empty=1'):arg_name(Save to database):arg_section(0, 0, 'Box', 'th-large')}">
				<div id="div" data-style="${args->div_style:html:default('border-radius:8px; min-width:300px; max-width:600px; background-color:#484745; color:white; text-align:center; padding:0.6em 1.2em'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(1, 1, 'Text', 'bars')}">
					<img src="${args->image_src:html:default('https://cdn.personyze.com/upload/362/185f3236b1b4ab52.png'):input_type(personyze_media_url):arg_name(Logo):arg_section(0, 2, 'Box', 'th-large')}" data-style="${args->image_style:html:default('width:auto; height:auto'):input_type(css):input_props('with_responsive=1'):arg_name(Logo size):arg_section(0, 3, 'Box', 'th-large')}">
					<div>
					<div class="st_f1">
						${args->div_text:default(Did you find this helpfull ?):arg_name(Text):arg_section(1, 0, 'Text', 'bars')}
					</div>
					<center class="st_f2" style="display:none">
						<button class="$btn" onclick="_S_T.dismiss_action(${action_id:html})" data-style="${args->close_style:html:default('background-color:#5F8F55; color:white; margin:0.6em'):input_type(css):input_props('with_responsive=1'):arg_name(Close Button Style):arg_section(0, 5, 'Box', 'th-large')}">
							${args->close_text:default(Close):arg_name(Close Button Text):arg_section(0, 4, 'Box', 'th-large')}
						</button>
					</center>
				</div>
			</td>
		</tr>
		<tr>
			<td>
				<button form="st_f" type="submit" class="$flat_btn" with_responsive="1" data-style="width:100%; box-sizing:border-box; ${args->a1_style:html:default('background-color:#5F8F55; color:white; text-decoration:none; text-align:center; padding:0.4em'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(2, 1, 'Button 1', 'mouse-pointer')}" hover_style="${args->a1_h_style:html:default('background-color: #e7e719; color: rgb(40, 45, 87);'):input_type(css):arg_name(Hover Style):arg_section(2, 2, 'Button 1', 'mouse-pointer')}" data-v="${args->a1_value:html:default(Yes):arg_name(Save value):arg_section(2, 3, 'Button 1', 'mouse-pointer')}" onclick="_S_T.joyquery('ancestor::tbody:limit(1) .st_f0', this).get(0).value=this.getAttribute('data-v')">
					${args->a1_text:default(Yes):arg_name(Text):arg_section(2, 0, 'Button 1', 'mouse-pointer')}
				</button>
			</td>
		</tr>
		<tr>
			<td>
				<button form="st_f" type="submit" class="$flat_btn" with_responsive="1" data-style="width:100%; box-sizing:border-box; ${args->a2_style:html:default('background-color:#5F8F55; color:white; text-decoration:none; text-align:center; padding:0.4em'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(3, 1, 'Button 2', 'mouse-pointer')}" hover_style="${args->a2_h_style:html:default('background-color: #e7e719; color: rgb(40, 45, 87);'):input_type(css):arg_name(Hover Style):arg_section(3, 2, 'Button 2', 'mouse-pointer')}" data-v="${args->a2_value:html:default(No):arg_name(Save value):arg_section(3, 3, 'Button 2', 'mouse-pointer')}" onclick="_S_T.joyquery('ancestor::tbody:limit(1) .st_f0', this).get(0).value=this.getAttribute('data-v')">
					${args->a2_text:default(No):arg_name(Text):arg_section(3, 0, 'Button 2', 'mouse-pointer')}
				</button>
			</td>
		</tr>
		${block->with_a3:default(0):arg_name(With Button 3):arg_section(4, 0, 'Button 3', 'mouse-pointer')}
		<tr>
			<td>
				<button form="st_f" type="submit" class="$flat_btn" with_responsive="1" data-style="width:100%; box-sizing:border-box; ${args->a3_style:html:input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(4, 2, 'Button 3', 'mouse-pointer')}" hover_style="${args->a3_h_style:html:input_type(css):arg_name(Hover Style):arg_section(4, 3, 'Button 3', 'mouse-pointer')}" data-v="${args->a3_value:html:arg_name(Save value):arg_section(4, 4, 'Button 3', 'mouse-pointer')}" onclick="_S_T.joyquery('ancestor::tbody:limit(1) .st_f0', this).get(0).value=this.getAttribute('data-v')">
					${args->a3_text:arg_name(Text):arg_section(4, 1, 'Button 3', 'mouse-pointer')}
				</button>
			</td>
		</tr>
		${block->with_a4:default(0):arg_name(With Button 4):arg_section(5, 0, 'Button 4', 'mouse-pointer')}
		<tr>
			<td>
				<button form="st_f" type="submit" class="$flat_btn" with_responsive="1" data-style="width:100%; box-sizing:border-box; ${args->a4_style:html:input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(5, 2, 'Button 4', 'mouse-pointer')}" hover_style="${args->a4_h_style:html:input_type(css):arg_name(Hover Style):arg_section(5, 3, 'Button 4', 'mouse-pointer')}" data-v="${args->a4_value:html:arg_name(Save value):arg_section(5, 4, 'Button 4', 'mouse-pointer')}" onclick="_S_T.joyquery('ancestor::tbody:limit(1) .st_f0', this).get(0).value=this.getAttribute('data-v')">
					${args->a4_text:arg_name(Text):arg_section(5, 1, 'Button 4', 'mouse-pointer')}
				</button>
			</td>
		</tr>
		${block->with_a5:default(0):arg_name(With Button 5):arg_section(6, 0, 'Button 5', 'mouse-pointer')}
		<tr>
			<td>
				<button form="st_f" type="submit" class="$flat_btn" with_responsive="1" data-style="width:100%; box-sizing:border-box; ${args->a5_style:html:input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(6, 2, 'Button 5', 'mouse-pointer')}" hover_style="${args->a5_h_style:html:input_type(css):arg_name(Hover Style):arg_section(6, 3, 'Button 5', 'mouse-pointer')}" data-v="${args->a5_value:html:arg_name(Save value):arg_section(6, 4, 'Button 5', 'mouse-pointer')}" onclick="_S_T.joyquery('ancestor::tbody:limit(1) .st_f0', this).get(0).value=this.getAttribute('data-v')">
					${args->a5_text:arg_name(Text):arg_section(6, 1, 'Button 5', 'mouse-pointer')}
				</button>
			</td>
		</tr>
	</tbody>
</table>
```


## Fullscreen two steps popup



```
<table class="$responsive" data-style="border-collapse:collapse; ${args->style:html:default('width: sel(100%, auto);
height: sel(100%, auto);
background-image: url(''http://www.personyze.com/wp-content/uploads/2018/05/shutterstock_587601533.jpg'');
background-size: cover;
background-color: white;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(0, 0, 'Box', 'th-large')}">
	<tr>
		<td data-style="position:relative; ${args->style_2:html:default('background-color: rgb(70, 62, 106);
color: rgb(256, 256, 256);
text-align: center;
vertical-align: middle;
padding-top: 10%;
padding-right: sel(10%, 10px);
padding-bottom: 10%;
padding-left: sel(10%, 10px);'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(0, 1, 'Box', 'th-large')}">
			<img src="${args->image_src:html:default('https://cdn.personyze.com/upload/362/185f3236b1b4ab52.png'):input_type(personyze_media_url):arg_name(URL):arg_section(1, 0, 'Logo', 'image')}" style="${args->image_style:html:default('width:auto; height:auto; border:none'):input_type(css):input_props('with_responsive=1'):arg_name(Image style):arg_section(1, 1, 'Logo', 'image')}">
			<div id="sw" class="$switch-elem" data-case="0">
				<div data-case="0">
					<div data-style="margin:${args->margin:html:default('sel(18px, 8px)'):input_type(css_length):input_props('with_responsive=1'):arg_name(Paragraph spacing):arg_section(0, 2, 'Box', 'th-large')} 0; ${args->style_t1:html:default('color: white;
font-size: sel(28px, 5vw);
font-weight: 300;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(2, 0, 'Step 1', 'bars')}">
						${args->text_1:default(Text):arg_name(Line 1):arg_section(2, 2, 'Step 1', 'bars')}
					</div>
					<div data-style="margin:${args->margin:html} 0; ${args->style_t2:html:default('color: rgb(252, 244, 244);
font-size: sel(25px, 4vw);
text-transform: none;
padding-top: 15px;
padding-right: 15px;
padding-bottom: 0px;
padding-left: 15px;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(2, 1, 'Step 1', 'bars')}">
						${args->text_2:default('<strong>Would you like to shoot us a quick question?</strong>'):arg_name(Line 1):arg_section(2, 3, 'Step 1', 'bars')}
					</div>
					<div data-style="margin:${args->margin:html} 0">
						${settings->a:onclick('by_id.sw._set_case(1, null, false, {template: ''animator_fade''})')}
						<a class="$flat_btn" with_responsive="1" onclick="by_id.sw._set_case(1, null, false, {template: 'animator_fade'})" data-style="display:inline-block; width:${args->button_width:html:default('sel(110px, 33vw)'):input_type(css_length):input_props('with_responsive=1'):arg_name(Button Width):arg_section(0, 4, 'Box', 'th-large')}; height:${args->button_height:html:default(30px):input_type(css_length):input_props('with_responsive=1'):arg_name(Button Height):arg_section(0, 5, 'Box', 'th-large')}; line-height:${args->button_height:html}; ${args->yes_style:html:default('background-color: red;
color: white;
margin-top: 30px;
margin-right: 10px;
margin-bottom: 10px;
margin-left: 10px;'):input_type(css):arg_name(Yes Button Style):arg_section(2, 5, 'Step 1', 'bars')}" hover_style="${args->yes_h_style:html:default('background-color: rgb(83, 141, 94);
color: rgb(253, 253, 253);'):input_type(css):arg_name(Yes Button Hover Style):arg_section(2, 6, 'Step 1', 'bars')}">
							${args->yes_1:default(Yes):arg_name(Yes button text):arg_section(2, 4, 'Step 1', 'bars')}
						</a>
						<a href="javascript:" class="$personyze_button_dont_show_again" data-action_id="${action_id:html}" data-style="display:inline-block; width:${args->button_width:html}; height:${args->button_height:html}; line-height:${args->button_height:html}; text-decoration:none; ${args->no_style:html:default('color:white; border:solid 1px'):input_type(css):arg_name(No Button Style):arg_section(2, 8, 'Step 1', 'bars')}">
							${args->no_1:default(No):arg_name(No button text):arg_section(2, 7, 'Step 1', 'bars')}
						</a>
					</div>
				</div>

				<div data-case="1" class="$cform st_f" ontplsubmit="personyze.push(['Submit', '${action_id:html}', this._get_value_ex(), arguments[1], arguments[2]]); return true" ontplaftersubmit="this.parentNode._set_case('2', null, false, {template: 'animator_fade'}); var redir=this.dataset.redir, t=this.dataset.redirDelay; if (redir) setTimeout(function() {location.href=redir}, t*1000)" data-redir="${args->redir:html:arg_name(After submit redirect to this URL):arg_section(4, 2, 'Step 3', 'bars')}" data-redir-delay="${args->redir_delay:html:input_type(number):arg_name('Redirect delay, sec'):arg_section(4, 4, 'Step 3', 'bars')}">
					<div data-style="margin:${args->margin:html} 0">
						${args->text_3:default('Please leave your email, and our experts will answer your question shortly.'):arg_name(Line 1):arg_section(3, 0, 'Step 2', 'bars')}
					</div>
					<div data-style="margin:${args->margin:html} 0">
						<input form="st_f" name="Field 1" data-prop-column="${args->f1_db:html:default(first_name):input_type(select_social):input_props('with_empty=1'):arg_name('Field #1 save to database'):arg_section(3, 1, 'Step 2', 'bars')}" data-style="${args->f1_style:html:default('width: sel(22em, auto);
padding: 0.3em;
text-align: center;
font-size: sel(14px, 4vw);
color: rgb(55, 11, 11);'):input_type(css):input_props('with_responsive=1'):arg_name(Input style):arg_section(3, 12, 'Step 2', 'bars')}" placeholder="${args->f1:html:default(First Name):arg_name('Field #1 Placeholder Text'):arg_section(3, 2, 'Step 2', 'bars')}" ontplready="${args->f1_required:html:default('this.required=1'):input_type(checkbox):input_props('value_off=','value_on=this.required=1'):arg_name('Field #1 is required'):arg_section(3, 3, 'Step 2', 'bars')}">
					</div>
					<div data-style="margin:${args->margin:html} 0">
						<input form="st_f" name="Field 2" data-prop-column="${args->f2_db:html:default(last_name):input_type(select_social):input_props('with_empty=1'):arg_name('Field #2 save to database'):arg_section(3, 4, 'Step 2', 'bars')}" data-style="${args->f1_style:html}" placeholder="${args->f2:html:default(Last Name):arg_name('Field #2 Placeholder Text'):arg_section(3, 13, 'Step 2', 'bars')}" ontplready="${args->f2_required:html:input_type(checkbox):input_props('value_off=','value_on=this.required=1'):arg_name('Field #2 is required'):arg_section(3, 5, 'Step 2', 'bars')}">
					</div>
					<div data-style="margin:${args->margin:html} 0">
						<input form="st_f" name="Email" data-prop-column="${args->f3_db:html:default(email):input_type(select_social):input_props('with_empty=1'):arg_name(Email save to database):arg_section(3, 6, 'Step 2', 'bars')}" data-style="${args->f1_style:html}" placeholder="${args->f3:html:default(Email):arg_name(Email Placeholder Text):arg_section(3, 9, 'Step 2', 'bars')}" required="1" pattern="^[^\s@]+@[^\s@\.]+\.[^\s@]+$">
					</div>
					<div data-style="margin:${args->margin:html} 0">
						<textarea form="st_f" name="Field 4" data-prop-column="${args->f4_db:html:default(custom_t_1):input_type(select_social):input_props('with_empty=1'):arg_name(Comments save to database):arg_section(3, 7, 'Step 2', 'bars')}" data-style="height:${args->textarea_height:html:default(4em):input_type(css_length):input_props('with_responsive=1'):arg_name(Textarea height):arg_section(0, 3, 'Box', 'th-large')}; ${args->f1_style:html}" placeholder="${args->f4:html:default(Ask away!):arg_name(Comments Placeholder Text):arg_section(3, 14, 'Step 2', 'bars')}" ontplready="${args->f4_required:html:input_type(checkbox):input_props('value_off=','value_on=this.required=1'):arg_name(Comments is required):arg_section(3, 8, 'Step 2', 'bars')}"></textarea>
					</div>
					<div data-style="margin:${args->margin:html} 0">
						${settings->b:onclick('by_id.sw._set_case(2, null, false, {template: ''animator_fade''})')}
						<button form="st_f" type="submit" class="$flat_btn" with_responsive="1" data-style="display:inline-block; width:${args->button_width:html}; height:${args->button_height:html}; line-height:${args->button_height:html}; ${args->yes_style:html}" hover_style="${args->yes_h_style:html}" ontplready="this._by_id=by_id" data-onsubmit="this._by_id.sw._set_case(2, null, false, {template: 'animator_fade'})">
							${args->button_tex:default(SUBMIT):arg_name(Submit button):arg_section(3, 10, 'Step 2', 'bars')}
						</button>
					</div>
					<div data-style="margin:${args->margin:html} 0">
						<a href="javascript:" class="$personyze_button_dont_show_again" data-action_id="${action_id:html}" data-style="color:inherit; text-decoration:inherit">
							${args->cancel:default('<span style="color:white;">No, I&#39;m not interested</span>'):arg_name(Cancel link):arg_section(3, 11, 'Step 2', 'bars')}
						</a>
					</div>
				</div>

				<div data-case="2">
					<div data-style="margin:${args->margin:html} 0; ${args->style_t4:html:default('color:white; font-size:sel(25px, 5vw)'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(4, 1, 'Step 3', 'bars')}">
						${args->text_4:default(Thank you!):arg_name(Line 1):arg_section(4, 0, 'Step 3', 'bars')}
					</div>
					<div data-style="margin:${args->margin:html} 0">
						<a class="$flat_btn" with_responsive="1" onclick="_S_T.dismiss_action(${action_id:html})" data-style="display:inline-block; width:${args->button_width:html}; height:${args->button_height:html}; line-height:${args->button_height:html}; ${args->yes_style:html}" hover_style="${args->yes_h_style:html}">
							${args->close_1:default(Close):arg_name(Close button text):arg_section(4, 3, 'Step 3', 'bars')}
						</a>
					</div>
				</div>
			</div>
			${block->show_close_button:default(1):arg_name(Show close button):arg_section(5, 0, 'Close Button', 'times-circle')}
			<div data-style="position:absolute; cursor:pointer; ${args->close_button_style:html:default('top:8px; right:8px;z-index:9999'):input_type(css):input_props('with_responsive=1'):arg_name(Close Button Style):arg_section(5, 1, 'Close Button', 'times-circle')}">
				${args->close_button:default('<div onmouseenter="this.style.backgroundColor=this.style.outlineColor" onmouseleave="this.style.backgroundColor=this.style.textDecorationColor" style="display: inline-block; vertical-align: text-bottom; width: 24px; height: 24px; box-sizing: border-box; border-top-left-radius: 50%; border-top-right-radius: 50%; border-bottom-right-radius: 50%; border-bottom-left-radius: 50%; border: 0px solid; -webkit-box-shadow: rgba(255, 255, 255, 0.2) 0px 1px 0px inset, rgba(0, 0, 0, 0.2) 0px 1px 2px; padding: 2px; background-color: rgba(0, 0, 0, 0); text-decoration-color: rgba(0, 0, 0, 0); outline-color: rgb(206, 54, 64); outline-width: 15px; color: rgb(248, 247, 247); cursor: pointer; transition: all 0.3s ease;" class="$personyze_button_dont_show_again" data-action_id="${action_id}"><div style="display: block; width: 100%; height: 100%; transition: all 0.3s ease 0s; border-top-left-radius: 50%; border-top-right-radius: 50%; border-bottom-right-radius: 50%; border-bottom-left-radius: 50%; background-image: linear-gradient(-45deg, transparent 0%, transparent 43%, currentcolor 43%, currentcolor 59%, transparent 59%, transparent 100%), linear-gradient(45deg, transparent 0%, transparent 43%, currentcolor 43%, currentcolor 59%, transparent 59%, transparent 100%);"></div></div>'):input_type(dontshowagain):arg_name(Close button):arg_section(5, 2, 'Close Button', 'times-circle')}
			</div>
		</td>
	</tr>
</table>
```


## Form



```
<div class="$responsive" data-style="position:relative; overflow:hidden; ${args->box_style:html:default('max-width:700px; border:solid #979797 1px; background-color:white'):input_type(css):input_props('with_responsive=1'):arg_name(Box style):arg_section(0, 0, 'Box', 'th-large')}" >
	<table style="border-collapse:collapse; border:none">
		<tr style="border:none">
			<td style="border:none; background-image:url('${args->image_src:html:default('//counter.personyze.com/images/html_customizer/banner-2.png'):input_type(personyze_media_url):arg_name(Picture URL):arg_section(1, 0, 'Picture', 'image')}'); background-repeat:no-repeat; background-size:100% 100%; background-position:center">
				<div data-style="width:${args->image_width:html:default('sel(300px, 40vw)'):input_type(css_length):input_props('with_responsive=1'):arg_name(Image width):arg_section(1, 1, 'Picture', 'image')}; height:${args->image_height:html:default('sel(300px, 40vw)'):input_type(css_length):input_props('with_responsive=1'):arg_name(Image height):arg_section(1, 2, 'Picture', 'image')}"></div>
			</td>
			<td style="border:none; padding:0 1em">
				<div class="$switch-elem" data-case="a">
					<div data-case="a" class="$cform st_f" ontplsubmit="personyze.push(['Submit', '${action_id:html}', this._get_value_ex(), arguments[1], arguments[2]]); return true" ontplaftersubmit="this.parentNode._set_case('b', null, false, {template: 'animator_fade'}); var redir=this.dataset.redir, t=this.dataset.redirDelay|0; if (redir) setTimeout(function() {location.href=redir}, t*1000)" data-redir="${args->redir:html:arg_name(After submit redirect to this URL):arg_section(6, 1, 'After submit', 'check')}" data-redir-delay="${args->redir_delay:html:input_type(number):arg_name('Redirect delay, sec'):arg_section(6, 2, 'After submit', 'check')}" style="margin:8px 0 10px">
						<div data-style="max-height:${args->image_height:html}">
							<div data-style="outline:0; ${args->title_style:html:default('text-align:center; color:black; font-size:sel(32px, 4vw); font-weight:bold'):input_type(css):input_props('with_responsive=1'):arg_name(Title style):arg_section(2, 1, 'Content', 'bars')}">
								${args->title:default(Your title goes here):arg_name(Title):arg_section(2, 0, 'Content', 'bars')}
							</div>
							<div data-style="outline:0; ${args->text_style:html:default('text-align:center; color:black; font-size:sel(14px, 4vw)'):input_type(css):input_props('with_responsive=1'):arg_name(Title style):arg_section(2, 3, 'Content', 'bars')}">
								${args->text:default('Sign up to our newsletter to get £10 off your first order and news of our latest deals and product releases.'):arg_name(Text):arg_section(2, 2, 'Content', 'bars')}
							</div>
							<div style="text-align:center">
								<input form="st_f" name="email" data-prop-column="email" pattern="^[^\s@]+@[^\s@\.]+\.[^\s@]+$" required="1" placeholder="Enter email" data-style="${args->email_input_style:html:default('width:sel(315px, 40vw); padding:sel(11px, 2px); margin:sel(8px, 6px) 0 sel(20px, 6px) 0; font-size:sel(14px, 4vw); color: #666666; background-color:white; border:solid #dadadc 1px; border-radius:0'):input_type(css):input_props('with_responsive=1'):arg_name(Email box style):arg_section(3, 0, 'Email box', 'envelope')}">
							</div>
							<div style="text-align:center">
								<button  form="st_f" type="submit" class="$btn" data-style="outline:0; ${args->button_style:html:default('background-color: rgb(67, 121, 89);
text-align: center;
border: solid rgb(65, 169, 95) 1px;
padding-top: 6px;
padding-right: 22px;
padding-bottom: 6px;
padding-left: 22px;
color: rgb(256, 256, 256);
cursor: pointer;
margin-bottom: 1em;'):input_type(css):input_props('with_responsive=1'):arg_name(Button style):arg_section(4, 1, 'Button', 'hand-o-up')}">
									${args->button_tex:default(SUBSCRIBE):arg_name(Text button):arg_section(4, 0, 'Button', 'hand-o-up')}
								</button>
							</div>
						</div>
					</div>
					<div data-case="b">
						${args->success:default(Thank you!):arg_name(Thank you text):arg_section(6, 0, 'After submit', 'check')}
					</div>
				</div>
			</td>
		</tr>
	</table>
	${block->show_close_button:default(1):arg_name(Show close button):arg_section(5, 0, 'Close Button', 'times-circle')}
	<div data-style="position:absolute; cursor:pointer; ${args->close_button_style:html:default('top:8px; right:8px;z-index:9999'):input_type(css):input_props('with_responsive=1'):arg_name(Close Button Style):arg_section(5, 1, 'Close Button', 'times-circle')}">
		${args->close_button:default('<img src="//counter.personyze.com/images/close-buttons/black-16x16.png" class="$personyze_button_dont_show_again" data-action_id="${action_id}">'):input_type(dontshowagain):arg_name(Close button):arg_section(5, 2, 'Close Button', 'times-circle')}
	</div>
</div>
```


## Form with select box



```
<div class="$responsive" data-style="position:relative; background-image:url(${args->bgimage_url:html:default('https://cdn.personyze.com/upload/362/2ced8f83fce5a056.png')}); overflow:hidden; ${args->style:html:default('background-size: contain;
background-position: bottom;
background-repeat: no-repeat;
border-radius: 3px;
background-color: rgba(89, 151, 84, 0);
box-shadow: 0 0 7px 5px rgba(189, 148, 148, 0.7);
width: 380px;
')}">
    <link href="https://fonts.googleapis.com/css?family=Montserrat:400,700|Open+Sans:400,600" rel="stylesheet">
    ${block->show_close_button:default(1)}
    <div style="position:absolute; top:16px; right:16px; z-index:2">
        ${args->close_button:default('<div onmouseenter="this.style.backgroundColor=this.style.outlineColor" onmouseleave="this.style.backgroundColor=this.style.textDecorationColor" style="display: inline-block; vertical-align: text-bottom; width: 24px; height: 24px; box-sizing: border-box; border-top-left-radius: 50%; border-top-right-radius: 50%; border-bottom-right-radius: 50%; border-bottom-left-radius: 50%; border: 2px solid; -webkit-box-shadow: rgba(255, 255, 255, 0.2) 0px 1px 0px inset, rgba(0, 0, 0, 0.2) 0px 1px 2px; padding: 3px; background-color: rgb(207, 120, 58); text-decoration-color: rgb(207, 120, 58); outline-color: rgb(206, 54, 64); outline-width: 10px; color: rgb(10, 4, 4); cursor: pointer; transition: all 0.3s ease;" class="$personyze_button_dont_show_again" data-action_id="${action_id}"><div style="display: block; width: 100%; height: 100%; transition: all 0.3s ease 0s; border-top-left-radius: 50%; border-top-right-radius: 50%; border-bottom-right-radius: 50%; border-bottom-left-radius: 50%; background-image: linear-gradient(-45deg, transparent 0%, transparent 46%, currentcolor 46%, currentcolor 56%, transparent 56%, transparent 100%), linear-gradient(45deg, transparent 0%, transparent 46%, currentcolor 46%, currentcolor 56%, transparent 56%, transparent 100%);"></div></div>')}
    </div>
     <div class="$switch-elem" id="st_sw" data-case="a" data-style="width:100%; height:100%; box-sizing:border-box; ${args->shading_style:html:default('background-color: rgba(31, 40, 55, 0.81);')}; ${args->send_confirm_style:html:default('padding-top: 30px;
padding-right: sel(30px, 1vw);
padding-bottom: 30px;
padding-left: sel(30px, 1vw);
font-family: Open Sans,san-serif;
font-weight: normal;
font-size: sel(18px, 14px);
color: white;
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
			style="position:relative; width:100%; height:100%"
		>
            <div data-style="${args->message_style:html:default('color: rgb(16, 9, 9);
font-family: Montserrat,san-serif;
font-weight: normal;
font-size: sel(24px, 22px);
line-height: 1;
text-align: left;
')}">
                ${args->message_text}
            </div>
            <div id="st_m" data-style="${args->gift_style:html:default('margin-top: 8px;
color: rgb(242, 239, 239);
font-family: Montserrat,san-serif;
font-weight: 600;
font-size: 20px;
line-height: 1.55;
text-align: left;
')}">
                ${args->gift_text:default(Title goes here....)}
            </div>
            <div>
                <div data-style="${args->content_style:html:default('color: rgb(244, 241, 241);
font-family: Open Sans,san-serif;
font-weight: 400;
font-size: 14px;
text-align: left;
padding-top: 15px;
padding-right: 1px;
padding-bottom: 19px;
padding-left: 1px;
line-height: 24px;
')}">
                    ${args->content_text:default(Description goes here)}
                </div>

                <div data-style="${args->style7:html:default('text-align: left;
font-size: 18px;
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
color: rgb(122,122,122);
text-align: left;
background-color: rgba(249, 247, 247, 0.88);
height: auto;
')}" placeholder="${args->f2:html:default(Your First Name)}">
					</div>
					${block->with_f6:default(0)}
					<div>
						<input form="st_f" name="Phone" type="tel" required="${args->f6_req:html}" data-prop-column="${args->f6_db:html}" data-style="box-sizing:border-box; ${args->f1_style:html}" placeholder="${args->f6:html}">
					</div>
					<div>
						<input form="st_f" name="Email" pattern="^[^\s@]+@[^\s@\.]+\.[^\s@]+$" required="1" data-prop-column="${args->f3_db:html:default(email)}" data-style="box-sizing:border-box; ${args->f1_style:html}" placeholder="${args->f3:html:default(Enter your email address)}" value="${email:html}" ontplready="this.value=this.value.trim()">
					</div>
					${block->with_f7:default(1)}
					<div>
						<input form="st_f" name="Line2" required="${args->f7_req:html}" data-prop-column="${args->f7_db:html}" data-style="box-sizing:border-box; ${args->f1_style:html}" placeholder="${args->f7:html:default(Free variable)}">
					</div>
					${block->with_f8:default(0)}
					<div>
						<input form="st_f" name="Line3" required="${args->f8_req:html}" data-prop-column="${args->f8_db:html}" data-style="box-sizing:border-box; ${args->f1_style:html}" placeholder="${args->f8:html}">
					</div>
					${block->with_f9:default(1)}
					<div>
						<select form="st_f" name="Dropdown" required="${args->f9_req:html}" data-prop-column="${args->f9_db:html}" data-style="box-sizing:border-box; ${args->f1_style:html}">
							${args->f9_options:default('<option value="">Please Select</option>
<option value="VIC">op</option>
<option value="NSW">NSW</option>
<option value="QLD">QLD</option>
<option value="SA">SA</option>
<option value="WA">WA</option>
<option value="TAS">TAS</option>
<option value="ACT">ACT</option>
')}
						</select>
					</div>
					${block->with_f5:default(0)}
					<div>
						<textarea form="st_f" name="Details" data-style="box-sizing:border-box; ${args->f5_style:html}" placeholder="${args->f5:html}"></textarea>
					</div>
					${block->with_f4:default(0)}
					<div data-style="${args->style9:html:default('color: rgb(199, 179, 179);
font-size: 12px;
text-align: left;
')}">
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
background-color: rgb(249, 247, 247);
color: rgb(3, 1, 1);
border-radius: 50px;
text-transform: uppercase;
letter-spacing: 2px;
height: 45px;
width: 220px;
margin-top: 10px;
margin-right: 0px;
margin-bottom: 40px;
margin-left: 0px;
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
					${args->button_caption:default(Contact Me)}
                </button>
            </div>
			<div data-style="${args->style9:html}">
				${args->ds:default(Free text goes here.......)}
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


## Form with 2 buttons



```
<div class="$responsive" data-style="position:relative; background-color:white; box-sizing:border-box; ${args->style:html:default('width:sel(500px, 90vw); padding:30px 40px'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(0, 0, 'Box', 'th-large')}" onupdate="var df=ns.joyquery('child::div', this).get(0).style, dl=ns.joyquery('child::div:last-child', this).get(0).style, fs=this.style; df.backgroundColor=fs.borderTopColor; df.border=fs.border; df.borderBottom='none'; df.borderTopLeftRadius=fs.borderTopLeftRadius; df.borderTopRightRadius=fs.borderTopRightRadius; dl.border=fs.border; dl.borderTop='none'; dl.borderBottomLeftRadius=fs.borderBottomLeftRadius; dl.borderBottomRightRadius=fs.borderBottomRightRadius; fs.borderRadius=0; fs.border='none'">
    <link href="https://fonts.googleapis.com/css?family=Fjalla+One" rel="stylesheet">
    ${block->show_close_button:default(1):arg_name(Show close button):arg_section(9, 0, 'Close button', 'close')}
    <div style="width:1px; vertical-align:middle" class="$copystyle" data-from="preceding-sibling::*" data-js="s.padding=fs.padding">
        ${args->close_button:default('<img src="http://counter.emarketer.com/images/close-buttons/black-16x16.png" style="position:absolute; top:16px; right:16px; width:16px; height:16px;" class="$emarketer_button_dont_show_again" data-action_id="${action_id}" data-n_sessions="0">'):input_type(dontshowagain):arg_name(Close button):arg_section(9, 1, 'Close button', 'close')}
    </div>
    <div class="$switch-elem" data-case="a">
		<div data-case="a" class="$cform st_f" ontplsubmit="emarketer.push(['Submit', '${action_id:html}', this._get_value_ex(), arguments[1], arguments[2]]); return true" ontplaftersubmit="this.parentNode._set_case('b', null, false, {template: 'animator_fade'}); var redir=this.dataset.redir, t=this.dataset.redirDelay; if (redir) setTimeout(function() {location.href=redir}, t*1000)" data-redir="${args->redir:html:arg_name(After submit redirect to this URL):arg_section(7, 1, 'After submit', 'check')}" data-redir-delay="${args->redir_delay:html:input_type(number):arg_name('Redirect delay, sec'):arg_section(7, 2, 'After submit', 'check')}" style="margin:8px 0 10px">
			<div data-style="vertical-align:middle; ${args->logo_style:html:default('text-align:center; padding:0 0 40px;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(1, 1, 'Logo', 'image')}">
				<img src="${args->logo_url:html:default('https://static.emarketer.com/upload/362/2ced8f83fce5a056.png'):input_type(emarketer_media_url):arg_name(URL):arg_section(1, 0, 'Logo', 'image')}">
			</div>
			<div data-style="vertical-align:middle; ${args->message_style:html:default('color:black; text-align:center; font-family:Helvetica,san-serif; font-weight:normal; font-size:15px; padding:10px 0; letter-spacing:1px'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(2, 1, 'Call message', 'bars')}">
				${args->message_text:default('Don&#39;t miss out'):arg_name(Text):arg_section(2, 0, 'Call message', 'bars')}
			</div>
			<div data-style="vertical-align:middle; ${args->content_style:html:default('color:black; text-align:center; font-family:Fjalla One,san-serif; font-weight:normal; font-size:28px; line-height:38px; padding:10px 40px; text-transform:uppercase; letter-spacing:2px'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(3, 1, 'Content', 'bars')}">
				${args->content_text:default('Exclusives, offers, and the latest from us'):arg_name(Text):arg_section(3, 0, 'Content', 'bars')}
			</div>
			<div>
				<span data-style="${args->email_field_label_style:html:default('font-family:Helvetica,san-serif; font-weight:normal; font-size:13px'):input_type(css):input_props('with_responsive=1'):arg_name(Label style):arg_section(4, 1, 'Email field', 'envelope')}">${args->email_field_label:default('Email Address*'):arg_name(Label):arg_section(4, 0, 'Email field', 'envelope')}</span>
				<div style="margin-top:4px">
					<input form="st_f" name="email" data-prop-column="email" pattern="^[^\s@]+@[^\s@\.]+\.[^\s@]+$" required="1" placeholder="${args->email_field_placeholder:html:default(Email Address):arg_name(Field placeholder):arg_section(4, 2, 'Email field', 'envelope')}" data-style="${args->email_field_style:html:default('font-family: Helvetica,san-serif;
font-weight: normal;
font-size: 13px;
width: 100%;
height: 40px;
padding: 10px;
box-sizing: border-box;
border: 1px solid rgb(196,196,196);
border-radius: 3px;
color: rgb(162,162,162);'):input_type(css):input_props('with_responsive=1'):arg_name(Field style):arg_section(4, 3, 'Email field', 'envelope')}">
				</div>
			</div>
			<div style="margin-top:20px; white-space:nowrap">
				<div style="display:inline-block; vertical-align:top; width:50%; box-sizing:border-box; padding-right:10px">
					<div class="$emarketer_button_dont_show_again" data-action_id="${action_id:html}" data-n_sessions="0" data-style="box-sizing:border-box; ${args->cancel_button_style:html:default('font-family:Fjalla One,san-serif; font-weight:normal; font-size:13px; width:100%; height:40px; line-height:40px; text-align:center; text-transform:uppercase; border:1px solid black; border-radius:3px; background-color:white; color:black; padding:0'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(8, 1, 'Cancel button', 'close')}">${args->cancel_button_label:default(No Thanks):arg_name(Label):arg_section(8, 0, 'Cancel button', 'close')}</div>
				</div><div style="display:inline-block; vertical-align:top; width:50%; box-sizing:border-box; padding-left:10px">
					<button form="st_f" type="submit" class="$flat_btn" data-style="display:inline-block; ${args->action_button_style:html:default('font-family:Fjalla One,san-serif; font-weight:normal; font-size:13px; width:100%; height:40px; line-height:40px; text-align:center; text-transform:uppercase; border:0; border-radius:3px; background-color:black; color:white; padding:0'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(6, 1, 'Action button', 'check')}">
						${args->action_button_label:default(Sign Up):arg_name(Label):arg_section(6, 0, 'Action button', 'check')}
					</button>
				</div>
			</div>
		</div>
		<div data-case="b">
			${args->success:default(Thank you!):arg_name(Thank you text):arg_section(7, 0, 'After submit', 'check')}
		</div>
	</div>
    <div data-style="${args->info_style:html:default('margin-top:55px; font-family:Helvetica,san-serif; font-weight:normal; font-size:11px; text-align:center; color:rgb(162,162,162)'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(5, 1, 'Info', 'info')}">${args->info_text:default('By signing up, you agree to our&nbsp;<a href="#" style="text-decoration:underline; cursor:pointer; color:inherit">Privacy Policy</a> and <a href="#" style="text-decoration:underline; cursor:pointer; color:inherit">Terms of Use</a>'):arg_name(Text):arg_section(5, 0, 'Info', 'info')}</div>
</div>
```


## Form with several fields



```
<div class="$responsive" data-style="${args->style:html:default('width:480px; font-size:15px'):input_type(css):input_props('with_responsive=1'):arg_name(Box style):arg_section(0, 0, 'Box', 'th-large')}" onupdate="var fs=ns.joyquery('child::span>span', this).get(0).style; for (var e,i=ns.joyquery('descendant::input', this); e=i();) e.style.cssText+=';'+fs.cssText">
	<span style="display:none"><span data-style="box-sizing:border-box; ${args->input_style:html:default('outline:none; border-top:none; border-left:none; border-right:none; border-bottom:solid gray 1px; margin:0.5em 0'):input_type(css):input_props('with_responsive=1'):arg_name(Input style):arg_section(6, 0, 'Inputs', 'th-large')}"></span></span>
	<div data-style="position:relative; ${args->title_box_style:html:default('background-color:#34194D; color:white; padding:1em 2em; border-radius:5px 5px 0 0'):input_type(css):input_props('with_responsive=1'):arg_name(Title box style):arg_section(1, 0, 'Title box', 'th-large')}">
		<div data-style="${args->title_1_style:html:default('font-size:135%'):input_type(css):input_props('with_responsive=1'):arg_name(Title line 1 style):arg_section(1, 2, 'Title box', 'th-large')}">
			${args->title_1:default(Title line 1):arg_name(Line 1):arg_section(1, 1, 'Title box', 'th-large')}
		</div>
		<div data-style="${args->title_2_style:html:default('font-size:100%'):input_type(css):input_props('with_responsive=1'):arg_name(Title line 1 style):arg_section(1, 4, 'Title box', 'th-large')}">
			${args->title_2:default(Title line 2):arg_name(Line 2):arg_section(1, 3, 'Title box', 'th-large')}
		</div>
		${block->show_close_button:default(1):arg_name(Show close button):arg_section(4, 0, 'Close Button', 'times-circle')}
		<div data-style="position:absolute; cursor:pointer; ${args->close_button_style:html:default('top:10px; right:10px; z-index:9999'):input_type(css):input_props('with_responsive=1'):arg_name(Close Button Style):arg_section(4, 1, 'Close Button', 'times-circle')}">
			${args->close_button:default('<img src="//counter.emarketer.com/images/close-buttons/rect-white-orange-16x16.png" class="$emarketer_button_dont_show_again" data-action_id="${action_id}">'):input_type(dontshowagain):arg_name(Close button):arg_section(4, 2, 'Close Button', 'times-circle')}
		</div>
	</div>
	<div class="$switch-elem" data-case="a">
		<div data-case="a" class="$cform st_f" ontplsubmit="emarketer.push(['Submit', '${action_id:html}', this._get_value_ex(), arguments[1], arguments[2]]); return true" ontplaftersubmit="this.parentNode._set_case('b', null, false, {template: 'animator_fade'}); var redir=this.dataset.redir, t=this.dataset.redirDelay; if (redir) setTimeout(function() {location.href=redir}, t*1000)" data-redir="${args->redir:html:arg_name(After submit redirect to this URL):arg_section(11, 1, 'After submit', 'check')}" data-redir-delay="${args->redir_delay:html:input_type(number):arg_name('Redirect delay, sec'):arg_section(11, 2, 'After submit', 'check')}" data-style="${args->content_box_style:html:default('background-color:white; color:black; padding:1em 2em; border:solid silver 1px'):input_type(css):input_props('with_responsive=1'):arg_name(Title box style):arg_section(5, 0, 'Content box', 'th-large')}">
			<div data-style="${args->content_style:html:default('font-size:120%'):input_type(css):input_props('with_responsive=1'):arg_name(Content style):arg_section(5, 2, 'Content box', 'th-large')}">
				${args->content:default(Content):arg_name(Content):arg_section(5, 1, 'Content box', 'th-large')}
			</div>

			${block->f1:default(1):arg_name('With field #1'):arg_section(7, 0, 'Field #1', 'th-large')}
			<input form="st_f" name="Field 1" data-prop-column="${args->f1_db:html:default(first_name):input_type(select_social):input_props('with_empty=1'):arg_name('Field #1 save to database'):arg_section(7, 4, 'Field #1', 'th-large')}" data-style="${args->f1_style:html:default('width:45%; float:left'):input_type(css):input_props('with_responsive=1'):arg_name(Input style):arg_section(7, 2, 'Field #1', 'th-large')}" placeholder="${args->f1:html:default(First name):arg_name('Field #1 placeholder text'):arg_section(7, 1, 'Field #1', 'th-large')}" ontplready="${args->f1_required:html:input_type(checkbox):input_props('value_off=','value_on=this.required=1'):arg_name('Field #1 is required'):arg_section(7, 3, 'Field #1', 'th-large')}">

			${block->f2:default(1):arg_name('With field #2'):arg_section(8, 0, 'Field #2', 'th-large')}
			<input form="st_f" name="Field 2" data-prop-column="${args->f2_db:html:default(last_name):input_type(select_social):input_props('with_empty=1'):arg_name('Field #2 save to database'):arg_section(8, 4, 'Field #2', 'th-large')}" data-style="${args->f2_style:html:default('width:45%; float:right'):input_type(css):input_props('with_responsive=1'):arg_name(Input style):arg_section(8, 2, 'Field #2', 'th-large')}" placeholder="${args->f2:html:default(Last name):arg_name('Field #2 placeholder text'):arg_section(8, 1, 'Field #2', 'th-large')}" ontplready="${args->f2_required:html:input_type(checkbox):input_props('value_off=','value_on=this.required=1'):arg_name('Field #2 is required'):arg_section(8, 3, 'Field #2', 'th-large')}">

			${block->f3:default(1):arg_name('With field #3'):arg_section(9, 0, 'Field #3', 'th-large')}
			<input form="st_f" name="Field 3" data-prop-column="${args->f3_db:html:default(email):input_type(select_social):input_props('with_empty=1'):arg_name('Field #3 save to database'):arg_section(9, 4, 'Field #3', 'th-large')}" data-style="${args->f3_style:html:default('width:100%; float:left'):input_type(css):input_props('with_responsive=1'):arg_name(Input style):arg_section(9, 2, 'Field #3', 'th-large')}" placeholder="${args->f3:html:default(Email):arg_name('Field #3 placeholder text'):arg_section(9, 1, 'Field #3', 'th-large')}" ontplready="${args->f3_required:html:default('this.required=1'):input_type(checkbox):input_props('value_off=','value_on=this.required=1'):arg_name('Field #3 is required'):arg_section(9, 3, 'Field #3', 'th-large')}">

			${block->f4:default(1):arg_name('With field #4'):arg_section(10, 0, 'Field #4', 'th-large')}
			<input form="st_f" name="Field 4" data-prop-column="${args->f4_db:html:input_type(select_social):input_props('with_empty=1'):arg_name('Field #4 save to database'):arg_section(10, 4, 'Field #4', 'th-large')}" data-style="${args->f4_style:html:default('width:45%; float:left'):input_type(css):input_props('with_responsive=1'):arg_name(Input style):arg_section(10, 2, 'Field #4', 'th-large')}" placeholder="${args->f4:html:default(Custom field 1):arg_name('Field #4 placeholder text'):arg_section(10, 1, 'Field #4', 'th-large')}" ontplready="${args->f4_required:html:input_type(checkbox):input_props('value_off=','value_on=this.required=1'):arg_name('Field #4 is required'):arg_section(10, 3, 'Field #4', 'th-large')}">

			${block->f5:default(1):arg_name('With field #5'):arg_section(12, 0, 'Field #5', 'th-large')}
			<input form="st_f" name="Field 5" data-prop-column="${args->f5_db:html:input_type(select_social):input_props('with_empty=1'):arg_name('Field #5 save to database'):arg_section(12, 4, 'Field #5', 'th-large')}" data-style="${args->f5_style:html:default('width:45%; float:right'):input_type(css):input_props('with_responsive=1'):arg_name(Input style):arg_section(12, 2, 'Field #5', 'th-large')}" placeholder="${args->f5:html:default(Custom field 2):arg_name('Field #5 placeholder text'):arg_section(12, 1, 'Field #5', 'th-large')}" ontplready="${args->f5_required:html:input_type(checkbox):input_props('value_off=','value_on=this.required=1'):arg_name('Field #5 is required'):arg_section(12, 3, 'Field #5', 'th-large')}">

			${block->f6:default(1):arg_name('With field #6'):arg_section(13, 0, 'Field #6', 'th-large')}
			<input form="st_f" name="Field 6" data-prop-column="${args->f6_db:html:input_type(select_social):input_props('with_empty=1'):arg_name('Field #6 save to database'):arg_section(13, 4, 'Field #6', 'th-large')}" data-style="${args->f6_style:html:default('width:100%; float:left'):input_type(css):input_props('with_responsive=1'):arg_name(Input style):arg_section(13, 2, 'Field #6', 'th-large')}" placeholder="${args->f6:html:default(Custom field 3):arg_name('Field #6 placeholder text'):arg_section(13, 1, 'Field #6', 'th-large')}" ontplready="${args->f6_required:html:input_type(checkbox):input_props('value_off=','value_on=this.required=1'):arg_name('Field #6 is required'):arg_section(13, 3, 'Field #6', 'th-large')}">

			${block->f7:default(1):arg_name('With field #7'):arg_section(14, 0, 'Field #7', 'th-large')}
			<input form="st_f" name="Field 7" data-prop-column="${args->f7_db:html:input_type(select_social):input_props('with_empty=1'):arg_name('Field #7 save to database'):arg_section(14, 4, 'Field #7', 'th-large')}" data-style="${args->f7_style:html:default('width:45%; float:left'):input_type(css):input_props('with_responsive=1'):arg_name(Input style):arg_section(14, 2, 'Field #7', 'th-large')}" placeholder="${args->f7:html:default(Custom field 4):arg_name('Field #7 placeholder text'):arg_section(14, 1, 'Field #7', 'th-large')}" ontplready="${args->f7_required:html:input_type(checkbox):input_props('value_off=','value_on=this.required=1'):arg_name('Field #7 is required'):arg_section(14, 3, 'Field #7', 'th-large')}">

			${block->f8:default(1):arg_name('With field #8'):arg_section(15, 0, 'Field #8', 'th-large')}
			<input form="st_f" name="Field 8" data-prop-column="${args->f8_db:html:input_type(select_social):input_props('with_empty=1'):arg_name('Field #8 save to database'):arg_section(15, 4, 'Field #8', 'th-large')}" data-style="${args->f8_style:html:default('width:45%; float:right'):input_type(css):input_props('with_responsive=1'):arg_name(Input style):arg_section(15, 2, 'Field #8', 'th-large')}" placeholder="${args->f8:html:default(Custom field 5):arg_name('Field #8 placeholder text'):arg_section(15, 1, 'Field #8', 'th-large')}" ontplready="${args->f8_required:html:input_type(checkbox):input_props('value_off=','value_on=this.required=1'):arg_name('Field #8 is required'):arg_section(15, 3, 'Field #8', 'th-large')}">

			${block->f9:default(1):arg_name('With field #9'):arg_section(2, 0, 'Field #9', 'th-large')}
			<input form="st_f" name="Field 9" data-prop-column="${args->f9_db:html:input_type(select_social):input_props('with_empty=1'):arg_name('Field #9 save to database'):arg_section(2, 4, 'Field #9', 'th-large')}" data-style="${args->f9_style:html:default('width:100%; float:left'):input_type(css):input_props('with_responsive=1'):arg_name(Input style):arg_section(2, 2, 'Field #9', 'th-large')}" placeholder="${args->f9:html:default(Custom field 6):arg_name('Field #9 placeholder text'):arg_section(2, 1, 'Field #9', 'th-large')}" ontplready="${args->f9_required:html:input_type(checkbox):input_props('value_off=','value_on=this.required=1'):arg_name('Field #9 is required'):arg_section(2, 3, 'Field #9', 'th-large')}">

			<div style="clear:both"></div>

			<div style="text-align:center">
				<button form="st_f" type="submit" class="$flat_btn" data-style="outline:0; border:none;
					${args->button_style:html:default('
					padding: 5px;
					line-height: 1.3;
					background-color: #ac9166;
					color: white'):input_type(css):input_props('with_responsive=1'):arg_name(Submit Button style):arg_section(3, 1, 'Submit Button', 'th-large')}">
					${args->button_text:default(Submit):arg_name(Submit Button Text):arg_section(3, 0, 'Submit Button', 'th-large')}
				</button>
			</div>
		</div>
		<div data-case="b">
			${args->success:default(Thank you!):arg_name(Thank you text):arg_section(11, 0, 'After submit', 'check')}
		</div>
	</div>
</div>
```


## Hotel



```
<div class="$responsive" data-style="box-sizing:border-box; position:relative; overflow:hidden; background-image: url(${args->image_bg:html:default('//counter.emarketer.com/images/html_customizer/Hotel.jpg'):input_type(emarketer_media_url):arg_name(bg image):arg_section(0, 1, 'Box', 'th-large')});
background-repeat:no-repeat; ${args->style:html:default('width: 480px; height: 180px; border: 1px solid #0c0c0e; background-position: 0 50%'):input_type(css):input_props('with_responsive=1'):arg_name(Box style):arg_section(0, 0, 'Box', 'th-large')}">
	${block->show_close_button:default(1):arg_name(Show close button):arg_section(4, 0, 'Close Button', 'times-circle')}
	<div data-style="position:absolute; cursor:pointer; ${args->close_button_style:html:default('top:5px; right:5px;z-index:9999'):input_type(css):input_props('with_responsive=1'):arg_name(Close_btn_Style):arg_section(4, 1, 'Close Button', 'times-circle')}">
		${args->close_button:default('<img src="//counter.emarketer.com/images/close-buttons/rect-white-orange-24x24.png" class="$emarketer_button_dont_show_again" data-action_id="${action_id}">'):input_type(dontshowagain):arg_name(Close button):arg_section(4, 2, 'Close Button', 'times-circle')}
	</div>

	<div data-style="position: absolute;
	${args->title_block:html:default('
	top: 10px;
	left: 10px;
	width: 280px;
	height: 160px'):input_type(css):input_props('with_responsive=1'):arg_name(Block position):arg_section(1, 0, 'Main block', 'list-alt')}">

		<div data-style="width: 100%;
		height: 100%;
		${args->main_block_style:html:default('
			background-color: #2d383a;
		opacity: 0.8;
		filter: blur(1px) grayscale(20%)'):input_type(css):input_props('with_responsive=1'):arg_name(Main style):arg_section(1, 1, 'Main block', 'list-alt')}">
		</div>

		<div class="$switch-elem" data-case="a" data-style="position: absolute; color:white;
		${args->main_title_position:html:default('
		left: 10px;
		top: 10px'):input_type(css):input_props('with_responsive=1'):arg_name(Title position):arg_section(2, 0, 'Title', 'bookmark')}">
			<div data-case="a" class="$cform st_f" ontplsubmit="emarketer.push(['Submit', '${action_id:html}', this._get_value_ex(), arguments[1], arguments[2]]); return true" ontplaftersubmit="this.parentNode._set_case('b', null, false, {template: 'animator_fade'}); var redir=this.dataset.redir, t=this.dataset.redirDelay; if (redir) setTimeout(function() {location.href=redir}, t*1000)" data-redir="${args->redir:html:arg_name(After submit redirect to this URL):arg_section(5, 1, 'After submit', 'check')}" data-redir-delay="${args->redir_delay:html:input_type(number):arg_name('Redirect delay, sec'):arg_section(5, 2, 'After submit', 'check')}">
				<span data-style="${args->title_text1_style:html:default('font-size: 20px;
				color: white;
				font-family: Oxygen, sans-serif;
				line-height: 1;
				font-weight: 300'):input_type(css):input_props('with_responsive=1'):arg_name(Text1 style):arg_section(2, 2, 'Title', 'bookmark')}">
					${args->title1:default('Subscribe &'):arg_name(Text1):arg_section(2, 1, 'Title', 'bookmark')}
				</span>

				<div data-style="
				${args->title_text2_style:html:default('
				color: white;
				font-family: Oxygen, sans-serif;
				font-size: 40px;
				line-height: 1;
				font-weight: 700'):input_type(css):input_props('with_responsive=1'):arg_name(Text2 style):arg_section(2, 4, 'Title', 'bookmark')}">
					${args->title2:default(GET 10% OFF):arg_name(Text2):arg_section(2, 3, 'Title', 'bookmark')}
				</div>
				<div data-style="
				${args->title_text3_style:html:default('
				color: white;
				font-family: Oxygen, sans-serif;
				font-size: 20px;
				line-height: 1;
				font-weight: 300'):input_type(css):input_props('with_responsive=1'):arg_name(Text3 style):arg_section(2, 6, 'Title', 'bookmark')}">
					${args->title3:default(for your next trip):arg_name(Text3):arg_section(2, 5, 'Title', 'bookmark')}
				</div>

				<div style="${args->email_block_position:html:default('margin-top:14px; background-color:white'):input_type(css):input_props('with_responsive=1'):arg_name(Email block position):arg_section(3, 1, 'Email block', 'envelope')}">
					<input form="st_f" name="email" data-prop-column="email" pattern="^[^\s@]+@[^\s@\.]+\.[^\s@]+$" required="1" placeholder="${args->email_text:html:default(Enter your email id here):arg_name(Email Text):arg_section(3, 0, 'Email block', 'envelope')}"
					data-style="outline: 0;
					border: none;
					text-align: center;
					${args->email_block_text_position:html:default('
					font-family: Oxygen, sans-serif;
					width: 186px;
					font-size: 12px;
					color: #282c2d'):input_type(css):input_props('with_responsive=1'):arg_name(Email block style):arg_section(3, 2, 'Email block', 'envelope')}">
					<button form="st_f" type="submit" class="$flat_btn"  data-style="
					cursor: pointer;
					outline:0;
					border: none;
					${args->email_button_style:html:default('
					font-family: Oxygen, sans-serif;
					font-size: 14px;
					padding: 5px;
					line-height: 1.3;
					background-color: #ac9166;
					color: white'):input_type(css):input_props('with_responsive=1'):arg_name(Email Button style):arg_section(3, 4, 'Email block', 'envelope')}">
						${args->button_text:default(Submit):arg_name(Button Text):arg_section(3, 3, 'Email block', 'envelope')}
					</button>
				</div>
			</div>

			<div data-case="b">
				${args->success:default(Thank you!):arg_name(Thank you text):arg_section(5, 0, 'After submit', 'check')}
			</div>
		</div>
	</div>
	<link href="https://fonts.googleapis.com/css?family=Oxygen:300,400,700" rel="stylesheet">
</div>
```


## Coupon



```
<div class="$responsive" data-style="box-sizing: border-box;
position: relative;
overflow: hidden;
${args->style:html:default('width: 500px;
height: 250px;
background-color: #10bfd2;
border: 4px dashed white'):input_type(css):input_props('with_responsive=1'):arg_name(Box style):arg_section(0, 0, 'Box', 'th-large')}">

	${block->show_close_button:default(1):arg_name(Show close button):arg_section(5, 0, 'Close Button', 'times-circle')}
	<div data-style="position:absolute; cursor:pointer; ${args->close_button_style:html:default('top:5px; right:5px;z-index:9999'):input_type(css):input_props('with_responsive=1'):arg_name(Close Button Style):arg_section(5, 1, 'Close Button', 'times-circle')}">
		${args->close_button:default('<img src="//counter.emarketer.com/images/close-buttons/rect-white-orange-24x24.png" class="$emarketer_button_dont_show_again" data-action_id="${action_id}">'):input_type(dontshowagain):arg_name(Close button):arg_section(5, 2, 'Close Button', 'times-circle')}
	</div>

	<div class="$switch-elem" data-case="a">
		<div data-case="a" class="$cform st_f" ontplsubmit="emarketer.push(['Submit', '${action_id:html}', this._get_value_ex(), arguments[1], arguments[2]]); return true" ontplaftersubmit="this.parentNode._set_case('b', null, false, {template: 'animator_fade'}); var redir=this.dataset.redir, t=this.dataset.redirDelay; if (redir) setTimeout(function() {location.href=redir}, t*1000)" data-redir="${args->redir:html:arg_name(After submit redirect to this URL):arg_section(6, 1, 'After submit', 'check')}" data-redir-delay="${args->redir_delay:html:input_type(number):arg_name('Redirect delay, sec'):arg_section(6, 2, 'After submit', 'check')}" style="position:absolute; width:100%; height:100%">

			<div data-style="position: absolute;
			${args->title1_position:html:default('
			top: 5px;
			width: 100%;
			text-align: center'):input_type(css):input_props('with_responsive=1'):arg_name(Title1 position):arg_section(1, 1, 'Title', 'bookmark')}">
				<span data-style="
				${args->title1_text_style:html:default('
				font-size: 14px;
				color: white;
				font-style: italic;
				background-color: #06474d;
				padding: 5px 10px;
				line-height: 2;
				box-shadow: 3px 1px 4px 2px rgba(59,73,74,0.5)'):input_type(css):input_props('with_responsive=1'):arg_name(Title1 text style):arg_section(1, 2, 'Title', 'bookmark')}">${args->title1:default(Want access to exclusive discounts):arg_name(Text1):arg_section(1, 0, 'Title', 'bookmark')}</span>
			</div>

			<div data-style="position: absolute;
			width: 100%;
			${args->title_position:html:default('
			top: 35px;
			text-align: center'):input_type(css):input_props('with_responsive=1'):arg_name(Title position):arg_section(2, 3, 'Title2', 'bookmark')}">
				<div data-style="${args->title2_rotation:html:default('
				position: absolute;
				top: -10px;
				left: 10px;
				-moz-transform: rotate(-25deg);
				-ms-transform: rotate(-25deg);
				-webkit-transform: rotate(-25deg);
				-o-transform: rotate(-25deg);
				transform: rotate(-25deg)'):input_type(css):input_props('with_responsive=1'):arg_name(Title2 rotation):arg_section(2, 4, 'Title2', 'bookmark')}">
					<span data-style="font-weight: 600;
					font-style: normal;
					${args->title2_style:html:default('
					font-family: Lemonada, cursive;
					font-size: 30px;
					letter-spacing: 0;
					line-height: 1;
					color: white;
					text-shadow: 2px 2px 4px #000000'):input_type(css):input_props('with_responsive=1'):arg_name(Title2 text style):arg_section(2, 5, 'Title2', 'bookmark')}">${args->title2:default(up to):arg_name(Text2):arg_section(2, 0, 'Title2', 'bookmark')}</span>
				</div>

				<span data-style="font-weight: 600;
				font-style: normal;
				${args->title3_style:html:default('
				font-size: 70px;
				letter-spacing: 10px;
				line-height: 1;
				font-family: Luckiest Guy, cursive;
				color: white;
				text-shadow: 2px 2px 4px #000000'):input_type(css):input_props('with_responsive=1'):arg_name(Title3 text style):arg_section(2, 2, 'Title2', 'bookmark')}">${args->title3:default(70% off?):arg_name(Text3):arg_section(2, 1, 'Title2', 'bookmark')}</span>
			</div>


			<div data-style="position: absolute;
			${args->email_block_position:html:default('
			bottom: 10px;
			width: 100%;
			text-align: center'):input_type(css):input_props('with_responsive=1'):arg_name(Email block position):arg_section(3, 1, 'Email block', 'envelope')}">
				<span data-style="
				${args->email_block_text_style:html:default('
				color: #000;
				font-style: italic;
				font-size: 12px'):input_type(css):input_props('with_responsive=1'):arg_name(Email block text style):arg_section(3, 2, 'Email block', 'envelope')}">${args->email_title1:default(Enter your email below to get access to these deals):arg_name(Title1):arg_section(3, 0, 'Email block', 'envelope')}</span><br>
				<input form="st_f" name="email" data-prop-column="email" pattern="^[^\s@]+@[^\s@\.]+\.[^\s@]+$" required="1" placeholder="Enter your email here" data-style="
				outline: 0;
				border: none;
				padding: 5px 0;
				${args->email_input_style:html:default(' width: 400px;
				text-align: center;
				color:#0c0c0c'):input_type(css):input_props('with_responsive=1'):arg_name(Email block text style):arg_section(3, 3, 'Email block', 'envelope')}">
				<div><input form="st_f" type="submit" value="${args->button_tex:html:default(i want crazy deals!):arg_name(Text button):arg_section(4, 0, 'Button', 'hand-o-up')}"  data-style="cursor: pointer;
				outline:0;margin-top: 5px; padding: 15px;border: none;
				${args->button_style:html:default('
				font-size: 25px;
				width: 400px;
				background-color: #b80003;
				text-transform: uppercase;
				color: white'):input_type(css):input_props('with_responsive=1'):arg_name(Button style):arg_section(4, 1, 'Button', 'hand-o-up')}"></div>
				<a href="javascript:" data-style="${args->button_not_action_style:html:default('color: white;
				font-style: italic;
				font-size: 12px;
				text-decoration: underline'):input_type(css):input_props('with_responsive=1'):arg_name(Button not action style):arg_section(4, 2, 'Button', 'hand-o-up')}"
				class="$emarketer_button_dont_show_again" data-action_id="${action_id:html}">
				${args->button_not_action_text:default('No thanks, I''d like paying full price'):arg_name(Text):arg_section(4, 3, 'Button', 'hand-o-up')}
				</a>
			</div>

		</div>

		<div data-case="b">
			${args->success:default(Thank you!):arg_name(Thank you text):arg_section(6, 0, 'After submit', 'check')}
		</div>
	</div>

	<link href="https://fonts.googleapis.com/css?family=Lemonada:600,700|Luckiest+Guy" rel="stylesheet">
</div>
```


## Survey



```
<div class="$responsive" data-style="position:relative; background-image:url(${args->bgimage_url:html:default('https://static.emarketer.com/upload/4241/3c0dd06f655c428d.jpeg'):input_type(emarketer_media_url):arg_name(URL):arg_section(0, 1, 'Box', 'th-large')}); ${args->style:html:default('width: sel(500px, auto);
background-size: cover;
background-position: bottom;
background-repeat: no-repeat;
box-sizing: border-box;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(0, 0, 'Box', 'th-large')}">
    <link rel="stylesheet" href="https://use.fontawesome.com/releases/v5.0.9/css/solid.css" integrity="sha384-29Ax2Ao1SMo9Pz5CxU1KMYy+aRLHmOu6hJKgWiViCYpz3f9egAJNwjnKGgr+BXDN" crossorigin="anonymous">
    <link rel="stylesheet" href="https://use.fontawesome.com/releases/v5.0.9/css/all.css" integrity="sha384-5SOiIsAziJl6AWe0HWRKTXlfcSHKmYV4RBF18PPJ173Kzn7jzMyFuTtk8JA7QQG1" crossorigin="anonymous">
    ${block->show_close_button:default(1):arg_name(Show close button):arg_section(7, 0, 'Close button', 'close')}
    <div style="position:absolute; top:16px; right:16px; z-index:1">
        ${args->close_button:default('<img src="http://counter.emarketer.com/images/close-buttons/black-16x16.png" class="$emarketer_button_dont_show_again" data-action_id="${action_id}" data-n_sessions="0">'):input_type(dontshowagain):arg_name(Close button):arg_section(7, 1, 'Close button', 'close')}
    </div>
    <div class="$switch-elem" data-case="a">
        <div data-case="a" class="$cform st_f" ontplsubmit="emarketer.push(['Submit', '${action_id:html}', this._get_value_ex(), arguments[1], arguments[2]]); return true" ontplaftersubmit="this.parentNode._set_case('b', null, false, {template: 'animator_fade'}); var redir=this.dataset.redir, t=this.dataset.redirDelay; if (redir) setTimeout(function() {location.href=redir}, t*1000)" data-redir="${args->redir:html:arg_name(After submit redirect to this URL):arg_section(5, 2, 'After submit', 'check')}" data-redir-delay="${args->redir_delay:html:input_type(number):arg_name('Redirect delay, sec'):arg_section(5, 3, 'After submit', 'check')}">
            <div data-style="${args->title_style:html:default('padding-top: 1em;
padding-right: 0.5em;
padding-bottom: 1em;
padding-left: 0.5em;
font-family: Helvetica,san-serif;
font-size: sel(18px, 16px);
background-color: rgba(255,255,255,.5);
color: black;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(1, 1, 'Title', 'bars')}">${args->title_text:default(Have a minute? We LOVE feedbacks!):arg_name(Text):arg_section(1, 0, 'Title', 'bars')}</div>
            <div data-style="${args->rating_style:html:default('padding:.5em .5em 0; font-size:sel(48px,32px); color:white; text-shadow:0px 6px 6px rgba(0, 0, 0, 0.5)'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(2, 1, 'Rating', 'star')}">
                <input form="st_f" name="rating" type="hidden" value="0" data-prop-column="${args->rating_db:html:default(custom_i_1):input_type(select_social):input_props('with_empty=1'):arg_name(Rating save to database):arg_section(2, 0, 'Rating', 'star')}">
                <span class="$repeat-elem" data-length="5">
                    <i class="fas fa-star" onmouseover="var p = this.parentNode, c = Array.prototype.slice.call(p.parentNode.children); i = c.indexOf(p); c.map(function (item, j) { if (j) item.style.color = i >= j ? '${args->check_star_color:html:default('#ffe085'):input_type(color):arg_name(Check star color):arg_section(2, 2, 'Rating', 'star')}' : 'inherit' });" onclick="var p = this.parentNode; p.parentNode.children[0].value = Array.prototype.indexOf.call(p.parentNode.children, p);" onmouseout="var p = this.parentNode.parentNode.children, c = Array.prototype.slice.call(p); i = p[0].value; c.map(function (item, j) { if (j) item.style.color = i >= j ? '${args->check_star_color:html:default('#ffe085'):input_type(color):arg_name(Check star color):arg_section(2, 2, 'Rating', 'star')}' : 'inherit' });" style="cursor:pointer"></i>
                </span>
            </div>
            <div data-style="${args->textarea_place:html:default('padding:1em 1em 0'):input_type(css):input_props('with_responsive=1'):arg_name(Placement):arg_section(3, 3, 'Text area', 'bars')}">
                <textarea form="st_f" name="feedback" required="1" rows="${args->textarea_rows:html:default(5):input_type(number):arg_name(Rows):arg_section(3, 2, 'Text area', 'bars')}" data-style="max-width:100%; ${args->textarea_style:html:default('width:100%; font-family:Helvetica,san-serif; font-size:12px; background-color:rgba(255, 255, 255, .8); box-sizing:border-box'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(3, 4, 'Text area', 'bars')}" placeholder="${args->textarea_placeholder:html:default(How can we improve?):arg_name(Placeholder):arg_section(3, 1, 'Text area', 'bars')}" data-prop-column="${args->feedback_db:html:default(custom_t_2):input_type(select_social):input_props('with_empty=1'):arg_name(Feedback save to database):arg_section(3, 0, 'Text area', 'bars')}"></textarea>
            </div>
            <div style="white-space:nowrap">
                <div style="display:inline-block; vertical-align:top; width:50%; padding:1em; box-sizing:border-box; text-align:left">
                    <button class="$flat_btn" with_responsive="1" data-style="${args->cancel_style:html:default('padding:.5em 1em; font-family:Helvetica,san-serif; font-size:12px; background-color:white; color:gray; border:none'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(6, 1, 'Cancel button', 'times')}" hover_style="${args->cancel_h_style:html:default('background-color:gray; color:white'):input_type(css):arg_name(Hover Style):arg_section(6, 2, 'Cancel button', 'times')}" onclick="_S_T.dismiss_action(${action_id:html});">${args->cancel_text:default(Cancel):arg_name(Text):arg_section(6, 0, 'Cancel button', 'times')}</button>
                </div><div style="display:inline-block; vertical-align:top; width:50%; padding:1em; box-sizing:border-box; text-align:right">
                    <button form="st_f" type="submit" class="$flat_btn" with_responsive="1" data-style="${args->submit_style:html:default('padding:.5em 1em; font-family:Helvetica,san-serif; font-size:12px; background-color:#12ae64; color:white; border:none'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(4, 1, 'Submit button', 'check')}" hover_style="${args->submit_h_style:html:default('background-color:#189110; color:white'):input_type(css):arg_name(Hover Style):arg_section(4, 2, 'Submit button', 'check')}">${args->submit_text:default(Submit):arg_name(Text):arg_section(4, 0, 'Submit button', 'check')}</button>
                </div>
            </div>
        </div>
        <div data-case="b">
            <div data-style="${args->after_submit_style:html:default('padding:1em; font-family:Helvetica,san-serif; font-size:sel(18px, 16px); text-align:center; color:white'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(5, 1, 'After submit', 'check')}">
                ${args->success:default(Thank you!):arg_name(Thank you text):arg_section(5, 0, 'After submit', 'check')}
            </div>
        </div>
    </div>
</div>
```


## Form



```
<div class="$responsive" data-style="position:relative; background-image:url(${args->bgimage_url:html:default('https://static.emarketer.com/upload/4035/73df51e772d27739.png'):input_type(emarketer_media_url):arg_name(URL):arg_section(0, 1, 'Box', 'th-large')}); overflow:hidden; ${args->style:html:default('width:sel(500px, 90vw); background-size:cover; background-position:center; background-repeat:no-repeat; box-sizing:border-box; border:1px solid #a6a6a6; border-radius:4px'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(0, 0, 'Box', 'th-large')}">
    <link href="https://fonts.googleapis.com/css?family=Montserrat:400,700|Open+Sans:400,600" rel="stylesheet">
    ${block->show_close_button:default(1):arg_name(Show close button):arg_section(4, 0, 'Close button', 'close')}
    <div style="position:absolute; top:16px; right:16px; z-index:2">
        ${args->close_button:default('<img src="https://counter.emarketer.com/images/close-buttons/rect-white-orange-16x16.png" style="width:16px; height:16px" class="$emarketer_button_dont_show_again" data-action_id="${action_id}" data-n_sessions="0">'):input_type(dontshowagain):arg_name(Close button):arg_section(4, 1, 'Close button', 'close')}
    </div>
     <div class="$switch-elem" data-case="a" data-style="width:100%; height:100%; box-sizing:border-box; ${args->shading_style:html:default('background-color: rgba(0, 0, 0, 0.07);'):input_type(css):input_props('with_responsive=1'):arg_name(Shading):arg_section(0, 2, 'Box', 'th-large')}; ${args->send_confirm_style:html:default('padding:30px; font-family:Open Sans,san-serif; font-weight:normal; font-size:sel(18px, 14px); color:white; text-align:center'):input_type(css):input_props('with_responsive=1'):arg_name(Confirmation style):arg_section(6, 2, 'Email Box', 'envelope')}">
		<div data-case="a" class="$cform st_f" ontplsubmit="emarketer.push(['Submit', '${action_id:html}', this._get_value_ex(), arguments[1], arguments[2]]); return true" ontplaftersubmit="this.parentNode._set_case('b', null, false, {template: 'animator_fade'}); var redir=this.dataset.redir, t=this.dataset.redirDelay; if (redir) setTimeout(function() {location.href=redir}, t*1000)" data-redir="${args->redir:html:default():arg_name(After submit redirect to this URL):arg_section(10, 1, 'After submit', 'check')}" data-redir-delay="${args->redir_delay:html:default():input_type(number):arg_name('Redirect delay, sec'):arg_section(10, 2, 'After submit', 'check')}" style="position:relative; width:100%; height:100%">
            <div data-style="${args->message_style:html:default('color: white;
font-family: Montserrat,san-serif;
font-weight: 700;
font-size: sel(40px, 22px);
line-height: 1;
text-align: left;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(1, 1, 'Call message', 'bars')}">
                ${args->message_text:default('Subscribe &amp; Save'):arg_name(Text):arg_section(1, 0, 'Call message', 'bars')}
            </div>
            <div data-style="${args->gift_style:html:default('margin-top:8px; color:white; font-family:Montserrat,san-serif; font-weight:400; font-size:sel(18px, 14px); line-height:1.25; text-align:left'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(2, 1, 'Gift', 'gift')}">
                ${args->gift_text:default(Save 15% OFF Your First Order):arg_name(Text):arg_section(2, 0, 'Gift', 'gift')}
            </div>
            <div>
                <div data-style="${args->content_style:html:default('margin-bottom:14px; color:white; font-family:Open Sans,san-serif; font-weight:400; font-size:sel(18px, 14px); line-height:1.25; text-align:left'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(3, 1, 'Info', 'bars')}">
                    ${args->content_text:default('Get promotions, discounts &amp; special offers'):arg_name(Text):arg_section(3, 0, 'Info', 'bars')}
                </div>

                <div data-style="${args->style7:html:default('text-align: center;
font-size: 18px;'):input_type(css):input_props('with_responsive=1'):arg_name(Fields area Style):arg_section(0, 3, 'Box', 'th-large')}">
					${block->with_f2:default(1):arg_name(With Name):arg_section(5, 0, 'Name Box', 'edit')}
					<div>
						<input form="st_f" name="Name" required="1" data-prop-column="${args->f2_db:html:default(first_name):input_type(select_social):input_props('with_empty=1'):arg_name(Name save to database):arg_section(5, 1, 'Name Box', 'edit')}" data-style="box-sizing:border-box; ${args->f1_style:html:default('margin-bottom:20px; padding:10px; font-family:Open Sans,san-serif; font-weight:600; font-size:selsel(20px, 5vw); width:100%; border:1px solid rgb(62,62,62); border-radius:4px; color:rgb(122,122,122); text-align:left'):input_type(css):input_props('with_responsive=1'):arg_name(Input style):arg_section(5, 3, 'Name Box', 'edit')}" placeholder="${args->f2:html:default(Name):arg_name(Name Placeholder Text):arg_section(5, 2, 'Name Box', 'edit')}">
					</div>
					<div>
						<input form="st_f" name="Email" pattern="^[^\s@]+@[^\s@\.]+\.[^\s@]+$" required="1" data-prop-column="${args->f3_db:html:default(email):input_type(select_social):input_props('with_empty=1'):arg_name(Email save to database):arg_section(6, 0, 'Email Box', 'envelope')}" data-style="box-sizing:border-box; ${args->f1_style:html:default('margin-bottom:20px; padding:10px; font-family:Open Sans,san-serif; font-weight:600; font-size:selsel(20px, 5vw); width:100%; border:1px solid rgb(62,62,62); border-radius:4px; color:rgb(122,122,122); text-align:left'):input_type(css):input_props('with_responsive=1'):arg_name(Input style):arg_section(5, 3, 'Name Box', 'edit')}" placeholder="${args->f3:html:default(E-Mail):arg_name(Email Placeholder Text):arg_section(6, 1, 'Email Box', 'envelope')}">
					</div>
					${block->with_f5:default(1):arg_name(With Details):arg_section(7, 0, 'Details Box', 'edit')}
					<div>
						<textarea form="st_f" name="Details" data-style="box-sizing:border-box; ${args->f5_style:html:default('margin-bottom: 20px;
padding: 10px;
font-family: Open Sans,san-serif;
font-weight: bolder;
font-size: selsel(20px, 5vw);
width: 100%;
border: 1px solid rgb(62,62,62);
border-radius: 4px;
color: rgb(122,122,122);
text-align: left;
font-size: 12px;'):input_type(css):input_props('with_responsive=1'):arg_name(Input style):arg_section(7, 2, 'Details Box', 'edit')}" placeholder="${args->f5:html:default(Details):arg_name(Details Placeholder Text):arg_section(7, 1, 'Details Box', 'edit')}"></textarea>
					</div>
					${block->with_f4:default(1):arg_name(With Checkbox):arg_section(8, 0, 'Checkbox', 'edit')}
					<div data-style="${args->style9:html:default('margin:1em 0; text-align:left; font-size:sel(14px, 4vw)'):input_type(css):input_props('with_responsive=1'):arg_name(Checkbox Style):arg_section(8, 1, 'Checkbox', 'edit')}">
						<label>
							<input form="st_f" name="Checkbox" type="checkbox" data-prop-column="${args->f4_db:html:default(custom_i_2):input_type(select_social):input_props('with_empty=1'):arg_name(Checkbox save to database):arg_section(8, 2, 'Checkbox', 'edit')}" value="1">
							${args->text_9:default(Send me newsletter):arg_name(Text):arg_section(8, 3, 'Checkbox', 'edit')}
						</label>
					</div>
				</div>

                <button form="st_f" type="submit" class="$flat_btn" with_responsive="1" style="display:block; border:0; white-space:normal; box-sizing:border-box; ${args->button_style:html:default('display:block; padding:8px 32px; font-family:Open Sans,san-serif; font-weight:normal; font-size:sel(18px, 14px); width:100%; min-height:44px; background-color:#5492dd; color:white; border-bottom:2px solid #3f75bd; border-radius:4px; text-transform:uppercase'):input_type(css):arg_name(Style):arg_section(9, 1, 'Action button', 'check')}" hover_style="${args->button_h_style:html:default('background-color:#E6E62A; border-color:#9c9c12; color:black'):input_type(css):arg_name(Hover Style):arg_section(9, 2, 'Action button', 'check')}">
					${args->button_caption:default(Get my exclusive coupon code):arg_name(Caption):arg_section(9, 0, 'Action button', 'check')}
                </button>
            </div>
        </div>
		<div data-case="b">
			${args->success:default(Thank you!):arg_name(Thank you text):arg_section(10, 0, 'After submit', 'check')}
		</div>
    </div>
</div>
```


## Form



```
<div class="$responsive" data-style="position:relative; background-image:url(${args->bgimage_url:html:input_type(emarketer_media_url):arg_name(URL):arg_section(0, 1, 'Box', 'th-large')}); overflow:hidden; ${args->style:html:default('width: sel(350px, auto);
height: auto;
background-size: contain;
background-position: center;
background-repeat: no-repeat;
box-sizing: border-box;
border: 1px solid #a6a6a6;
border-radius: 4px;
background-color: rgb(253, 253, 253);
box-shadow: 0 0 3px rgb(208, 181, 181);'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(0, 0, 'Box', 'th-large')}">
    <link href="https://fonts.googleapis.com/css?family=Montserrat:400,700|Open+Sans:400,600" rel="stylesheet">
    ${block->show_close_button:default(1):arg_name(Show close button):arg_section(4, 0, 'Close button', 'close')}
    <div style="position:absolute; top:16px; right:16px; z-index:2">
        ${args->close_button:default('<img src="https://counter.emarketer.com/images/close-buttons/black-16x16.png" style="width:16px; height:16px" class="$emarketer_button_dont_show_again" data-action_id="${action_id}" data-n_sessions="0">'):input_type(dontshowagain):arg_name(Close button):arg_section(4, 1, 'Close button', 'close')}
    </div>
     <div class="$switch-elem" data-case="a" data-style="width:100%; height:100%; box-sizing:border-box; ${args->shading_style:html:default('background-color: rgba(175, 223, 182, 0.57);'):input_type(css):input_props('with_responsive=1'):arg_name(Shading):arg_section(0, 2, 'Box', 'th-large')}; ${args->send_confirm_style:html:default('padding:30px; font-family:Open Sans,san-serif; font-weight:normal; font-size:sel(18px, 14px); color:white; text-align:center'):input_type(css):input_props('with_responsive=1'):arg_name(Confirmation style):arg_section(6, 2, 'Email Box', 'envelope')}">
		<div data-case="a" class="$cform st_f" ontplsubmit="emarketer.push(['Submit', '${action_id:html}', this._get_value_ex(), arguments[1], arguments[2]]); return true" ontplaftersubmit="this.parentNode._set_case('b', null, false, {template: 'animator_fade'}); var redir=this.dataset.redir, t=this.dataset.redirDelay; if (redir) setTimeout(function() {location.href=redir}, t*1000)" data-redir="${args->redir:html:arg_name(After submit redirect to this URL):arg_section(10, 1, 'After submit', 'check')}" data-redir-delay="${args->redir_delay:html:default(5):input_type(number):arg_name('Redirect delay, sec'):arg_section(10, 2, 'After submit', 'check')}" style="position:relative; width:100%; height:100%">
            <div data-style="${args->message_style:html:default('color: rgb(117, 97, 97);
font-family: Montserrat,san-serif;
font-weight: 700;
font-size: sel(16px, 22px);
line-height: 1;
text-align: center;
height: auto;
padding-top: 10px;
padding-right: 1px;
padding-bottom: 1px;
padding-left: 1px;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(1, 1, 'Call message', 'bars')}">
                ${args->message_text:default('<div style="text-align: center;"><span style="color:#000000;"><span style="font-size:16px;"><img src="https://static.emarketer.com/upload/362/7d0a26d42b6f9a72.jpeg" style="width:0px" /><img src="https://static.emarketer.com/upload/362/7d0a26d42b6f9a72.jpeg" style="width: 300px; float: center;" /><br />
<br />
ATTENTION!</span></span></div>

<table border="0" cellpadding="1" cellspacing="1" style="width: 100%;">
	<tbody>
		<tr>
			<td nowrap="nowrap" style="text-align: center;"><span style="color:#000000;"><span style="font-size:69px;">10%&nbsp;</span></span></td>
			<td>
			<p><span style="color:#000000;"><span style="font-size:25px;">ALL<br />
			GAMES&nbsp;</span></span></p>
			</td>
		</tr>
	</tbody>
</table>
<span style="font-size:14px;">UNLOCK THESE NOW</span>'):arg_name(Text):arg_section(1, 0, 'Call message', 'bars')}
            </div>
            <div data-style="${args->gift_style:html:default('margin-top:8px; color:white; font-family:Montserrat,san-serif; font-weight:400; font-size:sel(18px, 14px); line-height:1.25; text-align:left'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(2, 1, 'Gift', 'gift')}">
                ${args->gift_text:arg_name(Text):arg_section(2, 0, 'Gift', 'gift')}
            </div>
            <div>
                <div data-style="${args->content_style:html:default('margin-bottom:14px; color:white; font-family:Open Sans,san-serif; font-weight:400; font-size:sel(18px, 14px); line-height:1.25; text-align:left'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(3, 1, 'Info', 'bars')}">
                    ${args->content_text:arg_name(Text):arg_section(3, 0, 'Info', 'bars')}
                </div>

                <div data-style="${args->style7:html:default('text-align:center'):input_type(css):input_props('with_responsive=1'):arg_name(Fields area Style):arg_section(0, 3, 'Box', 'th-large')}">
					${block->with_f2:default(1):arg_name(With Name):arg_section(5, 0, 'Name Box', 'edit')}
					<div>
						<input form="st_f" name="Name" required="1" data-prop-column="${args->f2_db:html:default(first_name):input_type(select_social):input_props('with_empty=1'):arg_name(Name save to database):arg_section(5, 1, 'Name Box', 'edit')}" data-style="box-sizing:border-box; ${args->f1_style:html:default('margin-bottom:20px; padding:10px; font-family:Open Sans,san-serif; font-weight:600; font-size:selsel(20px, 5vw); width:100%; border:1px solid rgb(62,62,62); border-radius:4px; color:rgb(122,122,122); text-align:left'):input_type(css):input_props('with_responsive=1'):arg_name(Input style):arg_section(5, 3, 'Name Box', 'edit')}" placeholder="${args->f2:html:default(Name):arg_name(Name Placeholder Text):arg_section(5, 2, 'Name Box', 'edit')}">
					</div>
					<div>
						<input form="st_f" name="Email" pattern="^[^\s@]+@[^\s@\.]+\.[^\s@]+$" required="1" data-prop-column="${args->f3_db:html:default(email):input_type(select_social):input_props('with_empty=1'):arg_name(Email save to database):arg_section(6, 0, 'Email Box', 'envelope')}" data-style="box-sizing:border-box; ${args->f1_style:html:default('margin-bottom:20px; padding:10px; font-family:Open Sans,san-serif; font-weight:600; font-size:selsel(20px, 5vw); width:100%; border:1px solid rgb(62,62,62); border-radius:4px; color:rgb(122,122,122); text-align:left'):input_type(css):input_props('with_responsive=1'):arg_name(Input style):arg_section(5, 3, 'Name Box', 'edit')}" placeholder="${args->f3:html:default(E-Mail):arg_name(Email Placeholder Text):arg_section(6, 1, 'Email Box', 'envelope')}">
					</div>
					${block->with_f5:default(0):arg_name(With Details):arg_section(7, 0, 'Details Box', 'edit')}
					<div>
						<textarea form="st_f" name="Details" data-style="box-sizing:border-box; ${args->f5_style:html:input_type(css):input_props('with_responsive=1'):arg_name(Input style):arg_section(7, 2, 'Details Box', 'edit')}" placeholder="${args->f5:html:arg_name(Details Placeholder Text):arg_section(7, 1, 'Details Box', 'edit')}"></textarea>
					</div>
					${block->with_f4:default(0):arg_name(With Checkbox):arg_section(8, 0, 'Checkbox', 'edit')}
					<div data-style="${args->style9:html:input_type(css):input_props('with_responsive=1'):arg_name(Checkbox Style):arg_section(8, 1, 'Checkbox', 'edit')}">
						<label>
							<input form="st_f" name="Checkbox" type="checkbox" data-prop-column="${args->f4_db:html:input_type(select_social):input_props('with_empty=1'):arg_name(Checkbox save to database):arg_section(8, 2, 'Checkbox', 'edit')}" value="1">
							${args->text_9:arg_name(Text):arg_section(8, 3, 'Checkbox', 'edit')}
						</label>
					</div>
				</div>

                <button form="st_f" type="submit" class="$flat_btn" with_responsive="1" style="display:block; border:0; white-space:normal; box-sizing:border-box; ${args->button_style:html:default('display: block;
padding-top: 8px;
padding-right: 32px;
padding-bottom: 8px;
padding-left: 32px;
font-family: Open Sans,san-serif;
font-weight: normal;
font-size: sel(18px, 14px);
width: 100%;
min-height: 44px;
background-color: rgb(168, 26, 26);
color: white;
border-bottom: 2px solid rgba(168, 26, 26, 0.93);
border-radius: 4px;
text-transform: uppercase;'):input_type(css):arg_name(Style):arg_section(9, 1, 'Action button', 'check')}" hover_style="${args->button_h_style:html:default('background-color: rgb(101, 164, 119);
border-color: rgb(101, 164, 119);
color: rgb(249, 247, 247);'):input_type(css):arg_name(Hover Style):arg_section(9, 2, 'Action button', 'check')}">
					${args->button_caption:default(Get my secret deals):arg_name(Caption):arg_section(9, 0, 'Action button', 'check')}
                </button>
            </div>
        </div>
		<div data-case="b">
			${args->success:default('<div style="text-align: center;"><span style="color:#ffffff;">Thank you!<br />
In 5 seconds you will be redirect to the deal page, or you can click the link below&nbsp;</span><br />
<a href="http://apartmentsofmelbourne.com.au/secret"><span style="color:#ffffff;">Get your deal</span></a></div>
'):arg_name(Thank you text):arg_section(10, 0, 'After submit', 'check')}
		</div>
    </div>
</div>
```


## Form



```
<div class="$responsive" data-style="position:relative; background-image:url(${args->bgimage_url:html:default('https://static.emarketer.com/upload/362/7d0a26d42b6f9a72.jpeg'):input_type(emarketer_media_url):arg_name(URL):arg_section(0, 1, 'Box', 'th-large')}); overflow:hidden; ${args->style:html:default('width: sel(430px, auto);
height: auto;
background-size: cover;
background-position: center;
background-repeat: no-repeat;
box-sizing: border-box;
border: 1px solid #a6a6a6;
border-radius: 4px;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(0, 0, 'Box', 'th-large')}">
    <link href="https://fonts.googleapis.com/css?family=Montserrat:400,700|Open+Sans:400,600" rel="stylesheet">
    ${block->show_close_button:default(1):arg_name(Show close button):arg_section(4, 0, 'Close button', 'close')}
    <div style="position:absolute; top:16px; right:16px; z-index:2">
        ${args->close_button:default('<img src="https://counter.emarketer.com/images/close-buttons/black-16x16.png" style="width:16px; height:16px" class="$emarketer_button_dont_show_again" data-action_id="${action_id}" data-n_sessions="0">'):input_type(dontshowagain):arg_name(Close button):arg_section(4, 1, 'Close button', 'close')}
    </div>
     <div class="$switch-elem" data-case="a" data-style="width:100%; height:100%; box-sizing:border-box; ${args->shading_style:html:default('background-color: rgba(241, 43, 43, 0.84);'):input_type(css):input_props('with_responsive=1'):arg_name(Shading):arg_section(0, 2, 'Box', 'th-large')}; ${args->send_confirm_style:html:default('padding:30px; font-family:Open Sans,san-serif; font-weight:normal; font-size:sel(18px, 14px); color:white; text-align:center'):input_type(css):input_props('with_responsive=1'):arg_name(Confirmation style):arg_section(6, 2, 'Email Box', 'envelope')}">
		<div data-case="a" class="$cform st_f" ontplsubmit="emarketer.push(['Submit', '${action_id:html}', this._get_value_ex(), arguments[1], arguments[2]]); return true" ontplaftersubmit="this.parentNode._set_case('b', null, false, {template: 'animator_fade'}); var redir=this.dataset.redir, t=this.dataset.redirDelay; if (redir) setTimeout(function() {location.href=redir}, t*1000)" data-redir="${args->redir:html:default():arg_name(After submit redirect to this URL):arg_section(10, 1, 'After submit', 'check')}" data-redir-delay="${args->redir_delay:html:default(5):input_type(number):arg_name('Redirect delay, sec'):arg_section(10, 2, 'After submit', 'check')}" style="position:relative; width:100%; height:100%">
            <div data-style="${args->message_style:html:default('color: white;
font-family: Montserrat,san-serif;
font-weight: 700;
font-size: sel(30px, 22px);
line-height: 1;
text-align: left;
height: auto;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(1, 1, 'Call message', 'bars')}">
                ${args->message_text:default('<span style="font-size:36px;">ATTENTION!</span>
<table border="0" cellpadding="1" cellspacing="1" style="width: 200px;">
	<tbody>
		<tr>
			<td nowrap="nowrap"><span style="font-size:130px;">6&nbsp;</span></td>
			<td>
			<p style="text-align: left;"><span style="font-size:45px;">SECRET</span><br />
			<span style="font-size: 45px;">DEALS</span><span style="font-size:45px;">&nbsp;</span></p>
			</td>
		</tr>
	</tbody>
</table>
<br />
UNLOCK THESE NOW'):arg_name(Text):arg_section(1, 0, 'Call message', 'bars')}
            </div>
            <div data-style="${args->gift_style:html:default('margin-top:8px; color:white; font-family:Montserrat,san-serif; font-weight:400; font-size:sel(18px, 14px); line-height:1.25; text-align:left'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(2, 1, 'Gift', 'gift')}">
                ${args->gift_text:default():arg_name(Text):arg_section(2, 0, 'Gift', 'gift')}
            </div>
            <div>
                <div data-style="${args->content_style:html:default('margin-bottom:14px; color:white; font-family:Open Sans,san-serif; font-weight:400; font-size:sel(18px, 14px); line-height:1.25; text-align:left'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(3, 1, 'Info', 'bars')}">
                    ${args->content_text:default():arg_name(Text):arg_section(3, 0, 'Info', 'bars')}
                </div>

                <div data-style="${args->style7:html:default('text-align:center'):input_type(css):input_props('with_responsive=1'):arg_name(Fields area Style):arg_section(0, 3, 'Box', 'th-large')}">
					${block->with_f2:default(1):arg_name(With Name):arg_section(5, 0, 'Name Box', 'edit')}
					<div>
						<input form="st_f" name="Name" required="1" data-prop-column="${args->f2_db:html:default(first_name):input_type(select_social):input_props('with_empty=1'):arg_name(Name save to database):arg_section(5, 1, 'Name Box', 'edit')}" data-style="box-sizing:border-box; ${args->f1_style:html:default('margin-bottom:20px; padding:10px; font-family:Open Sans,san-serif; font-weight:600; font-size:selsel(20px, 5vw); width:100%; border:1px solid rgb(62,62,62); border-radius:4px; color:rgb(122,122,122); text-align:left'):input_type(css):input_props('with_responsive=1'):arg_name(Input style):arg_section(5, 3, 'Name Box', 'edit')}" placeholder="${args->f2:html:default(Name):arg_name(Name Placeholder Text):arg_section(5, 2, 'Name Box', 'edit')}">
					</div>
					<div>
						<input form="st_f" name="Email" pattern="^[^\s@]+@[^\s@\.]+\.[^\s@]+$" required="1" data-prop-column="${args->f3_db:html:default(email):input_type(select_social):input_props('with_empty=1'):arg_name(Email save to database):arg_section(6, 0, 'Email Box', 'envelope')}" data-style="box-sizing:border-box; ${args->f1_style:html:default('margin-bottom:20px; padding:10px; font-family:Open Sans,san-serif; font-weight:600; font-size:selsel(20px, 5vw); width:100%; border:1px solid rgb(62,62,62); border-radius:4px; color:rgb(122,122,122); text-align:left'):input_type(css):input_props('with_responsive=1'):arg_name(Input style):arg_section(5, 3, 'Name Box', 'edit')}" placeholder="${args->f3:html:default(E-Mail):arg_name(Email Placeholder Text):arg_section(6, 1, 'Email Box', 'envelope')}">
					</div>
					${block->with_f5:default(0):arg_name(With Details):arg_section(7, 0, 'Details Box', 'edit')}
					<div>
						<textarea form="st_f" name="Details" data-style="box-sizing:border-box; ${args->f5_style:html:input_type(css):input_props('with_responsive=1'):arg_name(Input style):arg_section(7, 2, 'Details Box', 'edit')}" placeholder="${args->f5:html:arg_name(Details Placeholder Text):arg_section(7, 1, 'Details Box', 'edit')}"></textarea>
					</div>
					${block->with_f4:default(0):arg_name(With Checkbox):arg_section(8, 0, 'Checkbox', 'edit')}
					<div data-style="${args->style9:html:input_type(css):input_props('with_responsive=1'):arg_name(Checkbox Style):arg_section(8, 1, 'Checkbox', 'edit')}">
						<label>
							<input form="st_f" name="Checkbox" type="checkbox" data-prop-column="${args->f4_db:html:input_type(select_social):input_props('with_empty=1'):arg_name(Checkbox save to database):arg_section(8, 2, 'Checkbox', 'edit')}" value="1">
							${args->text_9:arg_name(Text):arg_section(8, 3, 'Checkbox', 'edit')}
						</label>
					</div>
				</div>

                <button form="st_f" type="submit" class="$flat_btn" with_responsive="1" style="display:block; border:0; white-space:normal; box-sizing:border-box; ${args->button_style:html:default('display:block; padding:8px 32px; font-family:Open Sans,san-serif; font-weight:normal; font-size:sel(18px, 14px); width:100%; min-height:44px; background-color:#5492dd; color:white; border-bottom:2px solid #3f75bd; border-radius:4px; text-transform:uppercase'):input_type(css):arg_name(Style):arg_section(9, 1, 'Action button', 'check')}" hover_style="${args->button_h_style:html:default('background-color: rgb(101, 164, 119);
border-color: rgb(101, 164, 119);
color: rgb(249, 247, 247);'):input_type(css):arg_name(Hover Style):arg_section(9, 2, 'Action button', 'check')}">
					${args->button_caption:default(Get my secret deals):arg_name(Caption):arg_section(9, 0, 'Action button', 'check')}
                </button>
            </div>
        </div>
		<div data-case="b">
			${args->success:default('<div style="text-align: center;"><span style="color:#ffffff;">Thank you!<br />
In 5 seconds you will be redirect to the deal page, or you can click the link below&nbsp;</span><br />
<a href="http://apartmentsofmelbourne.com.au/secret"><span style="color:#ffffff;">Get your deal</span></a></div>
'):arg_name(Thank you text):arg_section(10, 0, 'After submit', 'check')}
		</div>
    </div>
</div>
```


## Form with auto-populate email



```
<div class="$responsive" data-style="position:relative; background-image:url(${args->bgimage_url:html:input_type(emarketer_media_url):arg_name(URL):arg_section(0, 1, 'Box', 'th-large')}); overflow:hidden; ${args->style:html:default('background-size: cover;
background-position: center;
background-repeat: no-repeat;
border-radius: 3px;
max-width: 450px;
width: sel(450px, 90%);
padding-top: 20px;
padding-right: sel(70px, 11px);
padding-bottom: 70px;
padding-left: sel(70px, 11px);
background-color: white;
box-shadow: 0 0 7px 5px rgba(189, 148, 148, 0.7);
margin-top: sel(1px, 5px);
margin-right: sel(auto, 5px);
margin-bottom: sel(1px, 5px);
margin-left: sel(auto, 5px);'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(0, 0, 'Box', 'th-large')}">
    <link href="https://fonts.googleapis.com/css?family=Montserrat:400,700|Open+Sans:400,600" rel="stylesheet">
    ${block->show_close_button:default(1):arg_name(Show close button):arg_section(4, 0, 'Close button', 'close')}
    <div style="position:absolute; top:16px; right:16px; z-index:2">
        ${args->close_button:default('<div onmouseenter="this.style.backgroundColor=this.style.outlineColor" onmouseleave="this.style.backgroundColor=this.style.textDecorationColor" style="display: inline-block; vertical-align: text-bottom; width: 28px; height: 28px; box-sizing: border-box; border-top-left-radius: 50%; border-top-right-radius: 50%; border-bottom-right-radius: 50%; border-bottom-left-radius: 50%; border: 0px solid; -webkit-box-shadow: rgba(255, 255, 255, 0.2) 0px 1px 0px inset, rgba(0, 0, 0, 0.2) 0px 1px 2px; padding: 2px; background-color: rgba(0, 0, 0, 0); text-decoration-color: rgba(0, 0, 0, 0); outline-color: rgba(206, 54, 54, 0); outline-width: 8px; color: rgb(131, 98, 98); cursor: pointer; transition: all 0.3s ease;" class="$emarketer_button_dont_show_again" data-action_id="${action_id}"><div style="display: block; width: 100%; height: 100%; transition: all 0.3s ease 0s; border-top-left-radius: 50%; border-top-right-radius: 50%; border-bottom-right-radius: 50%; border-bottom-left-radius: 50%; background-image: linear-gradient(-45deg, transparent 0%, transparent 47%, currentcolor 47%, currentcolor 55%, transparent 55%, transparent 100%), linear-gradient(45deg, transparent 0%, transparent 47%, currentcolor 47%, currentcolor 55%, transparent 55%, transparent 100%);"></div></div>'):input_type(dontshowagain):arg_name(Close button):arg_section(4, 1, 'Close button', 'close')}
    </div>
     <div class="$switch-elem" id="st_sw" data-case="a" data-style="width:100%; height:100%; box-sizing:border-box; ${args->shading_style:html:default('background-color: rgb(256, 256, 256);'):input_type(css):input_props('with_responsive=1'):arg_name(Shading):arg_section(0, 2, 'Box', 'th-large')}; ${args->send_confirm_style:html:default('padding-top: 30px;
padding-right: sel(30px, 1vw);
padding-bottom: 30px;
padding-left: sel(30px, 1vw);
font-family: Open Sans,san-serif;
font-weight: normal;
font-size: sel(18px, 14px);
color: white;
text-align: center;'):input_type(css):input_props('with_responsive=1'):arg_name(Confirmation style):arg_section(7, 2, 'Email Box', 'envelope')}">
		<div data-case="a" class="$cform st_f" ontplsubmit="emarketer.push(['Submit', ${action_id:json:html}, this._get_value_ex(), arguments[1], arguments[2]]); return true" ontplaftersubmit="var sw=this.parentNode; sw._set_case('b', null, false, {template: 'animator_fade'}); var js=this.dataset.customJs, redir=this.dataset.redir, t=this.dataset.redirDelay; if (js.trim()) new Function('action_id', 'by_id', 'data', 'report_error', js).call(this, ${action_id:json:html}, by_id, this._get_value()); if (redir) setTimeout(function() {location.href=redir}, t*1000)" data-custom-js="${args->customjs:html:input_type(textarea):arg_name(After submit execute this JavaScript):arg_section(11, 1, 'After submit', 'check')}" data-redir="${args->redir:html:arg_name(After submit redirect to this URL):arg_section(11, 3, 'After submit', 'check')}" data-redir-delay="${args->redir_delay:html:input_type(number):arg_name('Redirect delay, sec'):arg_section(11, 4, 'After submit', 'check')}" style="position:relative; width:100%; height:100%">
            <div data-style="${args->message_style:html:default('color: rgb(16, 9, 9);
font-family: Montserrat,san-serif;
font-weight: normal;
font-size: sel(24px, 22px);
line-height: 1;
text-align: left;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(1, 1, 'Call message', 'bars')}">
                ${args->message_text:arg_name(Text):arg_section(1, 0, 'Call message', 'bars')}
            </div>
            <div id="st_m" data-style="${args->gift_style:html:default('margin-top: 8px;
color: black;
font-family: Montserrat,san-serif;
font-weight: 600;
font-size: 20px;
line-height: 1.55;
text-align: left;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(2, 1, 'Gift', 'gift')}">
                ${args->gift_text:default(Hey! Do you want to know about our private sales? Get notified.):arg_name(Text):arg_section(2, 0, 'Gift', 'gift')}
            </div>
            <div>
                <div data-style="${args->content_style:html:default('color: rgb(25, 15, 15);
font-family: Open Sans,san-serif;
font-weight: 400;
font-size: 18px;
text-align: left;
padding-top: 15px;
padding-right: 1px;
padding-bottom: 19px;
padding-left: 1px;
line-height: 24px;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(3, 1, 'Info', 'bars')}">
                    ${args->content_text:arg_name(Text):arg_section(3, 0, 'Info', 'bars')}
                </div>

                <div data-style="${args->style7:html:default('text-align: left;
font-size: 18px;'):input_type(css):input_props('with_responsive=1'):arg_name(Fields area Style):arg_section(0, 3, 'Box', 'th-large')}">
					${block->with_f2:default(1):arg_name(With Name):arg_section(5, 0, 'Name Box', 'edit')}
					<div>
						<input form="st_f" name="Name" required="1" data-prop-column="${args->f2_db:html:default(first_name):input_type(select_social):input_props('with_empty=1'):arg_name(Name save to database):arg_section(5, 1, 'Name Box', 'edit')}" data-style="box-sizing:border-box; ${args->f1_style:html:default('margin-bottom: 20px;
padding: 15px;
font-family: Open Sans,san-serif;
font-weight: 300;
font-size: 14px;
width: sel(400px, 85%);
border: 1px solid rgb(62,62,62);
border-radius: 4px;
color: rgb(122,122,122);
text-align: left;
background-color: rgba(249, 247, 247, 0.8);'):input_type(css):input_props('with_responsive=1'):arg_name(Input style):arg_section(5, 3, 'Name Box', 'edit')}" placeholder="${args->f2:html:default(Your First Name):arg_name(Name Placeholder Text):arg_section(5, 2, 'Name Box', 'edit')}">
					</div>
					${block->with_f6:default(1):arg_name(With Telephone):arg_section(6, 0, 'Telephone Box', 'edit')}
					<div>
						<input form="st_f" name="Phone" type="tel" required="${args->f6_req:html:default(1):input_type(checkbox):arg_name(Telephone is required field):arg_section(6, 2, 'Telephone Box', 'edit')}" data-prop-column="${args->f6_db:html:input_type(select_social):input_props('with_empty=1'):arg_name(Telephone save to database):arg_section(6, 1, 'Telephone Box', 'edit')}" data-style="box-sizing:border-box; ${args->f1_style:html}" placeholder="${args->f6:html:default(Telephone):arg_name(Telephone Placeholder Text):arg_section(6, 3, 'Telephone Box', 'edit')}">
					</div>
					<div>
						<input form="st_f" name="Email" pattern="^[^\s@]+@[^\s@\.]+\.[^\s@]+$" required="1" data-prop-column="${args->f3_db:html:default(email):input_type(select_social):input_props('with_empty=1'):arg_name(Email save to database):arg_section(7, 0, 'Email Box', 'envelope')}" data-style="box-sizing:border-box; ${args->f1_style:html}" placeholder="${args->f3:html:default(Enter your email address):arg_name(Email Placeholder Text):arg_section(7, 1, 'Email Box', 'envelope')}" value="${email:html}" ontplready="this.value=this.value.trim()">
					</div>
					${block->with_f5:default(0):arg_name(With Details):arg_section(8, 0, 'Details Box', 'edit')}
					<div>
						<textarea form="st_f" name="Details" data-style="box-sizing:border-box; ${args->f5_style:html:input_type(css):input_props('with_responsive=1'):arg_name(Input style):arg_section(8, 2, 'Details Box', 'edit')}" placeholder="${args->f5:html:arg_name(Details Placeholder Text):arg_section(8, 1, 'Details Box', 'edit')}"></textarea>
					</div>
					${block->with_f4:default(0):arg_name(With Checkbox):arg_section(9, 0, 'Checkbox', 'edit')}
					<div data-style="${args->style9:html:default('color: rgb(199, 179, 179);
font-size: 12px;
text-align: left;'):input_type(css):input_props('with_responsive=1'):arg_name(Checkbox Style):arg_section(9, 1, 'Checkbox', 'edit')}">
						<label>
							<input form="st_f" name="Checkbox" type="checkbox" data-prop-column="${args->f4_db:html:input_type(select_social):input_props('with_empty=1'):arg_name(Checkbox save to database):arg_section(9, 2, 'Checkbox', 'edit')}" value="1">
							${args->text_9:arg_name(Text):arg_section(9, 3, 'Checkbox', 'edit')}
						</label>
					</div>
				</div>

                <button form="st_f" type="submit" class="$flat_btn" with_responsive="1" style="display:block; border:0; white-space:normal; box-sizing:border-box; ${args->button_style:html:default('display: block;
padding-top: 12px;
padding-right: 20px;
padding-bottom: 12px;
padding-left: 20px;
font-family: Open Sans,san-serif;
background-color: #a30001;
color: white;
border-radius: 50px;
text-transform: uppercase;
letter-spacing: 2px;
height: 45px;
width: 220px;
margin-top: 10px;
margin-right: 0px;
margin-bottom: 40px;
margin-left: 0px;'):input_type(css):arg_name(Style):arg_section(10, 1, 'Action button', 'check')}" hover_style="${args->button_h_style:html:default('display: block;
padding-top: 15px;
padding-right: 35px;
padding-bottom: 15px;
padding-left: 35px;
font-family: Open Sans,san-serif;
background-color: #111111;
color: #FFFFFF;
border-radius: 50px;
text-transform: uppercase;
letter-spacing: 2px;'):input_type(css):arg_name(Hover Style):arg_section(10, 2, 'Action button', 'check')}">
					${args->button_caption:default(Contact me):arg_name(Caption):arg_section(10, 0, 'Action button', 'check')}
                </button>
            </div>
			<div data-style="${args->style9:html}">
				${args->ds:default('We are GDPR compliant and will not spam you. By clicking the above button, you agree to our&nbsp;<b><a data-saferedirecturl="https://www.google.com/url?q=https://www.abbotsfordchrysler.com/privacy-policy/&amp;source=gmail&amp;ust=1559168237409000&amp;usg=AFQjCNHZwC-vxhrIxYb-rjytZTwobPcUrA" href="https://www.abbotsfordchrysler.com/privacy-policy/" target="_blank">Privacy Policy</a></b>.'):arg_name(No text):arg_section(2, 2, 'Gift', 'gift')}
			</div>
        </div>
		<div data-case="b" id="st_b" data-style="${args->style10:html:default('color: rgb(199, 179, 179);'):input_type(css):input_props('with_responsive=1'):arg_name(Thank you text Style):arg_section(11, 2, 'After submit', 'check')}">
			${args->success:default('<div style="text-align: center; font-size: 30px; ">Awesome! We will keep you posted.</div>
'):arg_name(Thank you text):arg_section(11, 0, 'After submit', 'check')}
		</div>
    </div>
</div>
```


## Form



```
<div class="$responsive" data-style="position:relative; background-image:url(${args->bgimage_url:html:default('https://www.abbotsfordchrysler.com/wp-content/uploads/2019/04/AC-RAM1500-Features-ComfortDriving.jpg'):input_type(emarketer_media_url):arg_name(URL):arg_section(0, 1, 'Box', 'th-large')}); overflow:hidden; ${args->style:html:default('width: sel(600px, 90vw);
background-size: cover;
background-position: center;
background-repeat: no-repeat;
box-sizing: border-box;
border: 1px solid #a6a6a6;
border-radius: 4px;
background-color: rgba(0, 0, 0, 0.7);'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(0, 0, 'Box', 'th-large')}">
    <link href="https://fonts.googleapis.com/css?family=Montserrat:400,700|Open+Sans:400,600" rel="stylesheet">
    ${block->show_close_button:default(1):arg_name(Show close button):arg_section(4, 0, 'Close button', 'close')}
    <div style="position:absolute; top:16px; right:16px; z-index:2">
        ${args->close_button:default('<img src="https://counter.emarketer.com/images/close-buttons/rect-white-orange-16x16.png" style="width:16px; height:16px" class="$emarketer_button_dont_show_again" data-action_id="${action_id}" data-n_sessions="0">'):input_type(dontshowagain):arg_name(Close button):arg_section(4, 1, 'Close button', 'close')}
    </div>
     <div class="$switch-elem" data-case="a" data-style="width:100%; height:100%; box-sizing:border-box; ${args->shading_style:html:default('background-color: rgba(0, 0, 0, 0.07);'):input_type(css):input_props('with_responsive=1'):arg_name(Shading):arg_section(0, 2, 'Box', 'th-large')}; ${args->send_confirm_style:html:default('padding:30px; font-family:Open Sans,san-serif; font-weight:normal; font-size:sel(18px, 14px); color:white; text-align:center'):input_type(css):input_props('with_responsive=1'):arg_name(Confirmation style):arg_section(7, 2, 'Email Box', 'envelope')}">
		<div data-case="a" class="$cform st_f" ontplsubmit="emarketer.push(['Submit', '${action_id:html}', this._get_value_ex(), arguments[1], arguments[2]]); return true" ontplaftersubmit="this.parentNode._set_case('b', null, false, {template: 'animator_fade'}); var redir=this.dataset.redir, t=this.dataset.redirDelay; if (redir) setTimeout(function() {location.href=redir}, t*1000)" data-redir="${args->redir:html:arg_name(After submit redirect to this URL):arg_section(11, 1, 'After submit', 'check')}" data-redir-delay="${args->redir_delay:html:input_type(number):arg_name('Redirect delay, sec'):arg_section(11, 2, 'After submit', 'check')}" style="position:relative; width:100%; height:100%">
            <div data-style="${args->message_style:html:default('color: white;
font-family: Montserrat,san-serif;
font-weight: 700;
font-size: sel(40px, 22px);
line-height: 1;
text-align: left;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(1, 1, 'Call message', 'bars')}">
                ${args->message_text:default(Title):arg_name(Text):arg_section(1, 0, 'Call message', 'bars')}
            </div>
            <div data-style="${args->gift_style:html:default('margin-top: 8px;
color: white;
font-family: Montserrat,san-serif;
font-weight: 900;
font-size: sel(18px, 14px);
line-height: 1.25;
text-align: left;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(2, 1, 'Gift', 'gift')}">
                ${args->gift_text:default(Sub Title):arg_name(Text):arg_section(2, 0, 'Gift', 'gift')}
            </div>
            <div>
                <div data-style="${args->content_style:html:default('margin-bottom: 14px;
color: white;
font-family: Open Sans,san-serif;
font-weight: 800;
font-size: sel(12px, 14px);
line-height: 1.25;
text-align: left;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(3, 1, 'Info', 'bars')}">
                    ${args->content_text:arg_name(Text):arg_section(3, 0, 'Info', 'bars')}
                </div>

                <div data-style="${args->style7:html:default('text-align: center;
font-size: 18px;'):input_type(css):input_props('with_responsive=1'):arg_name(Fields area Style):arg_section(0, 3, 'Box', 'th-large')}">
					${block->with_f2:default(1):arg_name(With Name):arg_section(5, 0, 'Name Box', 'edit')}
					<div>
						<input form="st_f" name="Name" required="1" data-prop-column="${args->f2_db:html:default(first_name):input_type(select_social):input_props('with_empty=1'):arg_name(Name save to database):arg_section(5, 1, 'Name Box', 'edit')}" data-style="box-sizing:border-box; ${args->f1_style:html:default('margin-bottom:20px; padding:10px; font-family:Open Sans,san-serif; font-weight:600; font-size:selsel(20px, 5vw); width:100%; border:1px solid rgb(62,62,62); border-radius:4px; color:rgb(122,122,122); text-align:left'):input_type(css):input_props('with_responsive=1'):arg_name(Input style):arg_section(5, 3, 'Name Box', 'edit')}" placeholder="${args->f2:html:default(Name):arg_name(Name Placeholder Text):arg_section(5, 2, 'Name Box', 'edit')}">
					</div>
					${block->with_f6:default(1):arg_name(With Telephone):arg_section(6, 0, 'Telephone Box', 'edit')}
					<div>
						<input form="st_f" name="Phone" type="tel" required="${args->f6_req:html:default(1):input_type(checkbox):arg_name(Telephone is required field):arg_section(6, 2, 'Telephone Box', 'edit')}" data-prop-column="${args->f6_db:html:default():input_type(select_social):input_props('with_empty=1'):arg_name(Telephone save to database):arg_section(6, 1, 'Telephone Box', 'edit')}" data-style="box-sizing:border-box; ${args->f1_style:html}" placeholder="${args->f6:html:default(Telephone):arg_name(Telephone Placeholder Text):arg_section(6, 3, 'Telephone Box', 'edit')}">
					</div>
					<div>
						<input form="st_f" name="Email" pattern="^[^\s@]+@[^\s@\.]+\.[^\s@]+$" required="1" data-prop-column="${args->f3_db:html:default(email):input_type(select_social):input_props('with_empty=1'):arg_name(Email save to database):arg_section(7, 0, 'Email Box', 'envelope')}" data-style="box-sizing:border-box; ${args->f1_style:html}" placeholder="${args->f3:html:default(E-Mail):arg_name(Email Placeholder Text):arg_section(7, 1, 'Email Box', 'envelope')}">
					</div>
					${block->with_f5:default(0):arg_name(With Details):arg_section(8, 0, 'Details Box', 'edit')}
					<div>
						<textarea form="st_f" name="Details" data-style="box-sizing:border-box; ${args->f5_style:html:input_type(css):input_props('with_responsive=1'):arg_name(Input style):arg_section(8, 2, 'Details Box', 'edit')}" placeholder="${args->f5:html:arg_name(Details Placeholder Text):arg_section(8, 1, 'Details Box', 'edit')}"></textarea>
					</div>
					${block->with_f4:default(0):arg_name(With Checkbox):arg_section(9, 0, 'Checkbox', 'edit')}
					<div data-style="${args->style9:html:input_type(css):input_props('with_responsive=1'):arg_name(Checkbox Style):arg_section(9, 1, 'Checkbox', 'edit')}">
						<label>
							<input form="st_f" name="Checkbox" type="checkbox" data-prop-column="${args->f4_db:html:input_type(select_social):input_props('with_empty=1'):arg_name(Checkbox save to database):arg_section(9, 2, 'Checkbox', 'edit')}" value="1">
							${args->text_9:arg_name(Text):arg_section(9, 3, 'Checkbox', 'edit')}
						</label>
					</div>
				</div>

                <button form="st_f" type="submit" class="$flat_btn" with_responsive="1" style="display:block; border:0; white-space:normal; box-sizing:border-box; ${args->button_style:html:default('display:block; padding:8px 32px; font-family:Open Sans,san-serif; font-weight:normal; font-size:sel(18px, 14px); width:100%; min-height:44px; background-color:#5492dd; color:white; border-bottom:2px solid #3f75bd; border-radius:4px; text-transform:uppercase'):input_type(css):arg_name(Style):arg_section(10, 1, 'Action button', 'check')}" hover_style="${args->button_h_style:html:default('background-color: #FFFFFF;
border-color: #5492dd;
color: #5492dd;'):input_type(css):arg_name(Hover Style):arg_section(10, 2, 'Action button', 'check')}">
					${args->button_caption:default(CONTACT ME):arg_name(Caption):arg_section(10, 0, 'Action button', 'check')}
                </button>
            </div>
        </div>
		<div data-case="b">
			${args->success:default('<div style="text-align: center; font-size:30px ;">Thank you! We will schedule you in.</div>
'):arg_name(Thank you text):arg_section(11, 0, 'After submit', 'check')}
		</div>
    </div>

    ${args->footer:default('<p style="color: #ffffff; padding: 35px; text-size: 10px;">We will try to meet your preferred date and time. We are GDPR compliant and will not spam you. By clicking the above button, you agree to our <a data-saferedirecturl="https://www.google.com/url?q=https://www.abbotsfordchrysler.com/privacy-policy/&amp;source=gmail&amp;ust=1559168237409000&amp;usg=AFQjCNHZwC-vxhrIxYb-rjytZTwobPcUrA" href="https://www.abbotsfordchrysler.com/privacy-policy/" style="color:#fff;" target="_blank"><b>Privacy Policy</b></a>.</p>
'):arg_name(Footer):arg_section(12, 0, 'Footer', 'bars')}

</div>
```


## Form survey



```
<div class="$responsive" data-style="position:relative; background-image:url(${args->bgimage_url:html:input_type(emarketer_media_url):arg_name(URL):arg_section(0, 1, 'Box', 'th-large')}); ${args->style:html:default('width: sel(500px, auto);
background-position: bottom;
background-repeat: no-repeat;
background-color: white;
padding: 30px;
border-radius: 10px;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(0, 0, 'Box', 'th-large')}">
	${block->show_close_button:default(1):arg_name(Show close button):arg_section(8, 0, 'Close button', 'close')}
	<div style="position:absolute; top:16px; right:16px; z-index:1">
		${args->close_button:default('<a href="javascript:" style="font-size: 24px; color: rgba(0, 0, 0, 0.39); font-weight: bold; line-height: 1; text-decoration: none;" class="$emarketer_button_dont_show_again" data-action_id="${action_id}">×</a>'):input_type(dontshowagain):arg_name(Close button):arg_section(8, 1, 'Close button', 'close')}
	</div>
	<div class="$switch-elem" data-case="a">
		<div data-case="a" class="$cform st_f" ontplsubmit="emarketer.push(['Submit', '${action_id:html}', this._get_value_ex(), arguments[1], arguments[2]]); return true" ontplaftersubmit="this.parentNode._set_case('b', null, false, {template: 'animator_fade'}); var redir=this.dataset.redir, t=this.dataset.redirDelay; if (redir) setTimeout(function() {location.href=redir}, t*1000)" data-redir="${args->redir:html:arg_name(After submit redirect to this URL):arg_section(6, 2, 'After submit', 'check')}" data-redir-delay="${args->redir_delay:html:input_type(number):arg_name('Redirect delay, sec'):arg_section(6, 3, 'After submit', 'check')}">
			<div data-style="${args->title_style:html:default('padding-top: 1em;
padding-right: 0.5em;
padding-bottom: 1em;
padding-left: 0.5em;
font-family: Helvetica,san-serif;
font-size: sel(18px, 16px);
color: rgba(0, 0, 0, 0.89);'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(1, 1, 'Title', 'bars')}">${args->title_text:default('<div style="text-align: center;"><span style="font-size:22px;">Tell us how we can improve?</span></div>
'):arg_name(Text):arg_section(1, 0, 'Title', 'bars')}</div>

			${block->with_rating:default(1):arg_name(With Rating):arg_section(2, 0, 'Rating', 'star')}
			<div data-style="${args->rating_style:html:default('font-size: 22px;
padding: 10;
margin-top: 1px;
margin-right: 1px;
margin-bottom: 13px;
margin-left: 1px;
color: rgb(214, 225, 221);'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(2, 2, 'Rating', 'star')}">
				<input form="st_f" name="rating" type="hidden" value="0" data-prop-column="${args->rating_db:html:default(account_lifetime_value):input_type(select_social):input_props('with_empty=1'):arg_name(Rating save to database):arg_section(2, 1, 'Rating', 'star')}">
				<span class="$repeat-elem" data-length="5">
					<b onmouseover="var p = this.parentNode, c = Array.prototype.slice.call(p.parentNode.children); i = c.indexOf(p); c.map(function (item, j) { if (j) item.style.color = i >= j ? '${args->check_star_color:html:default('#ffe085'):input_type(color):arg_name(Check star color):arg_section(2, 3, 'Rating', 'star')}' : 'inherit' });" onclick="var p = this.parentNode; p.parentNode.children[0].value = Array.prototype.indexOf.call(p.parentNode.children, p);" onmouseout="var p = this.parentNode.parentNode.children, c = Array.prototype.slice.call(p); i = p[0].value; c.map(function (item, j) { if (j) item.style.color = i >= j ? '${args->check_star_color:html}' : 'inherit' });" style="cursor:pointer">${args->star:default('★'):arg_name(Star Glyph):arg_section(2, 4, 'Rating', 'star')}</b>
				</span>
			</div>

			${block->with_email:default(1):arg_name(With Email Box):arg_section(3, 0, 'Email Box', 'envelope')}
			<div data-style="${args->email_place:html:default('margin-top: 0px;
margin-right: 0px;
margin-bottom: 0.6em;
margin-left: 0px;'):input_type(css):input_props('with_responsive=1'):arg_name(Placement):arg_section(3, 3, 'Email Box', 'envelope')}">
				<input form="st_f" name="Email" pattern="^[^\s@]+@[^\s@\.]+\.[^\s@]+|$" ${args->email_req:default('required="1"'):input_type(checkbox):input_props('value_on=required="1"','value_off='):arg_name(Email is required field):arg_section(3, 4, 'Email Box', 'envelope')} data-prop-column="${args->email_db:html:default(email):input_type(select_social):input_props('with_empty=1'):arg_name(Email save to database):arg_section(3, 1, 'Email Box', 'envelope')}" data-style="box-sizing:border-box; ${args->input_style:html:default('padding: 15px;
font-family: Open Sans,san-serif;
font-weight: 300;
font-size: 14px;
width: 100%;
border: 1px solid rgb(62,62,62);
border-radius: 4px;
color: rgb(122,122,122);
text-align: left;
background-color: rgba(249, 247, 247, 0.8);'):input_type(css):input_props('with_responsive=1'):arg_name(Input style):arg_section(0, 3, 'Box', 'th-large')}" placeholder="${args->email:html:default(Enter your email address):arg_name(Email Placeholder Text):arg_section(3, 2, 'Email Box', 'envelope')}" value="${email:html}" ontplready="this.value=this.value.trim()">
			</div>

			${block->with_textarea:default(1):arg_name(With Textarea):arg_section(4, 0, 'Text area', 'bars')}
			<div data-style="${args->textarea_place:html:input_type(css):input_props('with_responsive=1'):arg_name(Placement):arg_section(4, 4, 'Text area', 'bars')}">
				<textarea form="st_f" name="feedback" ${args->textarea_req:default('required="1"'):input_type(checkbox):input_props('value_on=required="1"','value_off='):arg_name(Textarea is required field):arg_section(4, 6, 'Text area', 'bars')} rows="${args->textarea_rows:html:default(5):input_type(number):arg_name(Rows):arg_section(4, 3, 'Text area', 'bars')}" data-style="max-width:100%; box-sizing:border-box; ${args->input_style:html}; ${args->textarea_style:html:input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(4, 5, 'Text area', 'bars')}" placeholder="${args->textarea_placeholder:html:default(How can we improve?):arg_name(Placeholder):arg_section(4, 2, 'Text area', 'bars')}" data-prop-column="${args->feedback_db:html:default(account_lifetime_value):input_type(select_social):input_props('with_empty=1'):arg_name(Feedback save to database):arg_section(4, 1, 'Text area', 'bars')}"></textarea>
			</div>
			<div style="display:flex; align-items:center; ${args->button_box_style:html:default('justify-content: center;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(0, 2, 'Box', 'th-large')}">
				<button class="$flat_btn" with_responsive="1" data-style="${args->cancel_style:html:default('margin:1em; padding:.5em 1em; font-family:Helvetica,san-serif; font-size:12px; background-color:white; color:gray; border:none'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(7, 1, 'Cancel button', 'times')}" hover_style="${args->cancel_h_style:html:default('background-color:gray; color:white'):input_type(css):arg_name(Hover Style):arg_section(7, 2, 'Cancel button', 'times')}" onclick="_S_T.dismiss_action(${action_id:html});">${args->cancel_text:default(Cancel):arg_name(Text):arg_section(7, 0, 'Cancel button', 'times')}</button>
				<button form="st_f" type="submit" class="$flat_btn" with_responsive="1" data-style="${args->submit_style:html:default('margin:1em; padding-top: .5em;
padding-right: 1em;
padding-bottom: .5em;
padding-left: 1em;
font-family: Helvetica,san-serif;
font-size: 12px;
background-color: #12ae64;
color: white;
border: none;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(5, 1, 'Submit button', 'check')}" hover_style="${args->submit_h_style:html:default('background-color:#189110; color:white'):input_type(css):arg_name(Hover Style):arg_section(5, 2, 'Submit button', 'check')}">${args->submit_text:default(Submit):arg_name(Text):arg_section(5, 0, 'Submit button', 'check')}</button>
			</div>
		</div>
		<div data-case="b">
			<div data-style="${args->after_submit_style:html:default('padding:1em; font-family:Helvetica,san-serif; font-size:sel(18px, 16px); text-align:center; color:black'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(6, 1, 'After submit', 'check')}">
				${args->success:default(Thank you!):arg_name(Thank you text):arg_section(6, 0, 'After submit', 'check')}
			</div>
		</div>
	</div>
</div>
```


## Form



```
<div class="$responsive" data-style="${args->style:html:default('width: sel(380px, auto);
font-family: sans-serif;
background-color: white;
font-size: sel(26px, 5vw);'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(0, 0, 'Box', 'th-large')}">
	<table data-style="border-collapse:collapse; width:100%; ${args->style2:html:default('background-color: rgb(113, 164, 107);
color: white;
text-align: center;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(1, 0, 'Title bar', 'bookmark')}">
		<tr>
			<td data-style="width:99%; ${args->style4:html:default('font-size: 115%;
padding: 0.3em;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(1, 1, 'Title bar', 'bookmark')}">
				${block->logo:default(1):arg_name(With logo):arg_section(1, 2, 'Title bar', 'bookmark')}
				<img src="${args->logo_src:html:default('https://cdn.e-marketer.io/upload/362/185f3236b1b4ab52.png'):input_type(emarketer_media_url):arg_name(Logo URL):arg_section(1, 3, 'Title bar', 'bookmark')}" data-style="vertical-align:middle; ${args->image_style:html:default('width:auto; height:auto; max-height:sel(30px, 8vw); border:none; margin:0 0.2em'):input_type(css):input_props('with_responsive=1'):arg_name(Logo size):arg_section(1, 4, 'Title bar', 'bookmark')}">
				${block->title:default(0):arg_name(With Title Text):arg_section(1, 5, 'Title bar', 'bookmark')}
				<span>
					${args->title:arg_name(Text):arg_section(1, 6, 'Title bar', 'bookmark')}
				</span>
			</td>
			${block->x:default(1):arg_name('With [x]'):arg_section(1, 7, 'Title bar', 'bookmark')}
			<td style="padding:0">
				<a href="javascript:" class="$emarketer_button_dont_show_again" data-action_id="${action_id:html}" data-style="cursor:pointer; border:2px solid; border-radius:50%; line-height:1; width:1em; float:right; color:inherit; text-decoration:none; ${args->x_style:html:default('text-decoration: none;
margin-top: 0;
margin-right: 0.6em;
margin-bottom: 0;
margin-left: 0;
line-height: 0.9em;
height: 1em;
width: 1em;'):input_type(css):input_props('with_responsive=1'):arg_name('[x] position'):arg_section(1, 8, 'Title bar', 'bookmark')}">×</a>
			</td>
		</tr>
	</table>
	 <div class="$switch-elem" data-case="a">
		<div data-case="a" class="$cform st_f" ontplsubmit="emarketer.push(['Submit', '${action_id:html}', this._get_value_ex(), arguments[1], arguments[2]]); return true" ontplaftersubmit="this.parentNode._set_case('b', null, false, {template: 'animator_fade'}); var redir=this.dataset.redir, t=this.dataset.redirDelay; if (redir) setTimeout(function() {location.href=redir}, t*1000)" data-redir="${args->redir:html:arg_name(After submit redirect to this URL):arg_section(8, 1, 'After submit', 'check')}" data-redir-delay="${args->redir_delay:html:input_type(number):arg_name('Redirect delay, sec'):arg_section(8, 2, 'After submit', 'check')}">
			<div data-style="${args->style3:html:default('margin:1.7em'):input_type(css):input_props('with_responsive=1'):arg_name(Box Style):arg_section(2, 0, 'Content Box', 'bars')}">
				${block->line_1:default(1):arg_name(With Line 1):arg_section(2, 1, 'Content Box', 'bars')}
				<div data-style="${args->style5:html:default('font-size:125%; text-align:center'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(2, 2, 'Content Box', 'bars')}">
					${args->text_2:default(Title Goes Here):arg_name(Text):arg_section(2, 3, 'Content Box', 'bars')}
				</div>
				<div data-style="${args->style6:html:default('text-align: center;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(2, 4, 'Content Box', 'bars')}">
					${args->text_3:default(Your description goes here Your description goes here):arg_name(Text):arg_section(2, 5, 'Content Box', 'bars')}
				</div>
			</div>
			<div data-style="${args->style7:html:default('margin-top: 1em;
margin-right: 1em;
margin-bottom: 0em;
margin-left: 1em;
text-align: left;
max-width: 90%;'):input_type(css):input_props('with_responsive=1'):arg_name(Fields area Style):arg_section(2, 6, 'Content Box', 'bars')}">
				${block->with_f2:default(1):arg_name(With Name):arg_section(3, 0, 'Name Box', 'edit')}
				<div>
					<input form="st_f" name="Name" required="1" data-prop-column="${args->f2_db:html:default(first_name):input_type(select_social):input_props('with_empty=1'):arg_name(Name save to database):arg_section(3, 1, 'Name Box', 'edit')}" data-style="${args->f1_style:html:default('margin-bottom: 0.5em;
width: auto;
padding: 0.5em;
text-align: left;
font-size: sel(20px, 5vw);
background-color: rgb(249, 241, 241);
border-radius: 3px;
border-style: ridge;'):input_type(css):input_props('with_responsive=1'):arg_name(Input style):arg_section(3, 3, 'Name Box', 'edit')}" placeholder="${args->f2:html:default(Name):arg_name(Name Placeholder Text):arg_section(3, 2, 'Name Box', 'edit')}">
				</div>
				<div>
					<input form="st_f" name="Email" pattern="^[^\s@]+@[^\s@\.]+\.[^\s@]+$" required="1" data-prop-column="${args->f3_db:html:default(email):input_type(select_social):input_props('with_empty=1'):arg_name(Email save to database):arg_section(4, 0, 'Email Box', 'edit')}" data-style="${args->f1_style:html}" placeholder="${args->f3:html:default(E-Mail):arg_name(Email Placeholder Text):arg_section(4, 1, 'Email Box', 'edit')}">
				</div>
				${block->with_f5:default(1):arg_name(With Details):arg_section(6, 0, 'Details Box', 'edit')}
				<div>
					<textarea form="st_f" name="Details" data-style="${args->f5_style:html:default('margin-bottom: 0.5em;
width: auto;
padding: 0.5em;
text-align: left;
font-size: sel(20px, 5vw);
background-color: rgb(249, 241, 241);
border-radius: 3px;
border-style: ridge;'):input_type(css):input_props('with_responsive=1'):arg_name(Input style):arg_section(6, 2, 'Details Box', 'edit')}" placeholder="${args->f5:html:default(Details):arg_name(Details Placeholder Text):arg_section(6, 1, 'Details Box', 'edit')}"></textarea>
				</div>
				${block->with_f4:default(0):arg_name(With Checkbox):arg_section(5, 0, 'Checkbox', 'edit')}
				<div data-style="${args->style9:html:input_type(css):input_props('with_responsive=1'):arg_name(Checkbox Style):arg_section(5, 1, 'Checkbox', 'edit')}">
					<label>
						<input form="st_f" name="Checkbox" type="checkbox" data-prop-column="${args->f4_db:html:input_type(select_social):input_props('with_empty=1'):arg_name(Checkbox save to database):arg_section(5, 2, 'Checkbox', 'edit')}" value="1">
						${args->text_9:arg_name(Text):arg_section(5, 3, 'Checkbox', 'edit')}
					</label>
				</div>
			</div>
			<div data-style="text-align:center; ${args->style8:html:default('padding-top: 0;
padding-right: 0;
padding-bottom: 1em;
padding-left: 0;
width: 100%;
font-size: 17px;
color: rgb(255, 256, 256);'):input_type(css):input_props('with_responsive=1'):arg_name(Buttons Box Style):arg_section(7, 0, 'Buttons', 'hand-o-up')}">
				<span>
					<button form="st_f" type="submit" class="$flat_btn" with_responsive="1" href="${args->href_2:html:default('#'):arg_name(Button 1 URL):arg_section(7, 9, 'Buttons', 'hand-o-up')}" target="${args->target_2:html:default(_self):input_type(a_target):arg_name(Button 1 Open link in):arg_section(7, 10, 'Buttons', 'hand-o-up')}" data-style="font-size:inherit; width:${args->button_width:html:default(0px):input_type(css_length):input_props('with_responsive=1'):arg_name(Button Width):arg_section(7, 7, 'Buttons', 'hand-o-up')}; line-height:1; padding:${args->button_padding:html:default(10px):input_type(css_length):input_props('with_responsive=1'):arg_name(Button Height):arg_section(7, 8, 'Buttons', 'hand-o-up')}; ${args->yes_style:html:default('box-shadow: 0 2px 10px 0 rgba(0,0,0,0.15);
font-family: "Product Sans",Arial,sans-serif;
font-size: 16px;
font-weight: 500;
height: auto;
line-height: 16px;
min-width: 76px;
padding-top: 10px;
padding-right: 24px;
padding-bottom: 10px;
padding-left: 24px;
text-transform: none;
background-color: #448aff;
color: rgb(252, 244, 244);'):input_type(css):arg_name(Yes Button Style):arg_section(7, 2, 'Buttons', 'hand-o-up')}" hover_style="${args->yes_h_style:html:default('box-shadow: 0 2px 10px 0 rgba(0,0,0,0.15);
font-family: "Product Sans",Arial,sans-serif;
font-size: 16px;
font-weight: 500;
height: auto;
line-height: 16px;
min-width: 76px;
padding-top: 10px;
padding-right: 24px;
padding-bottom: 10px;
padding-left: 24px;
text-transform: none;
background-color: rgb(41, 199, 51);'):input_type(css):arg_name(Yes Button Hover Style):arg_section(7, 3, 'Buttons', 'hand-o-up')}">
						${args->yes_1:default(SUBMIT):arg_name(Yes button text):arg_section(7, 1, 'Buttons', 'hand-o-up')}
					</button>
				</span>
				${block->button_2:default(0):arg_name(With Second Button):arg_section(7, 4, 'Buttons', 'hand-o-up')}
				<span>
					<a class="$flat_btn $emarketer_button_dont_show_again" data-disabled="1" href="javascript:" data-action_id="${action_id:html}" data-style="display:inline-block; vertical-align:middle; width:${args->button_width:html}; line-height:1; padding:${args->button_padding:html}; text-decoration:none; ${args->no_style:html:input_type(css):arg_name(No Button Style):arg_section(7, 6, 'Buttons', 'hand-o-up')}">
						${args->no_1:arg_name(No button text):arg_section(7, 5, 'Buttons', 'hand-o-up')}
					</a>
				</span>
			</div>
		</div>
		<div data-case="b">
			${args->success:default(Thank you!):arg_name(Thank you text):arg_section(8, 0, 'After submit', 'check')}
		</div>
	</div>
</div>
```


## Form



```
<table class="$responsive" style="background-color:transparent; border-collapse:separate; border-spacing:${args->gap:html:default(0.4em):input_type(css_length):input_props('with_responsive=1'):arg_name(Margin):arg_section(0, 1, 'Box', 'th-large')}" onupdate="var i, a=ns.joyquery('child::*>*>td>button', this).get(); for (i=0; i!=a.length; i++) a[i].style.borderRadius=by_id.div.style.borderRadius">
	<tbody class="$cform st_f" ontplsubmit="emarketer.push(['Submit', '${action_id:html}', this._get_value_ex(), arguments[1], arguments[2]]); return true" ontplaftersubmit="
		for (var e, i=_S_T.joyquery('.st_f1, child::tr:from(2)', this); e=i();) e.style.display='none';
		_S_T.joyquery('.st_f2', this).get(0).style.display='';
		var redir=this.dataset.redir, t=this.dataset.redirDelay;
		if (redir) setTimeout(function() {location.href=redir}, t*1000);
	" data-redir="${args->redir:html:arg_name(After submit redirect to this URL):arg_section(7, 0)}" data-redir-delay="${args->redir_delay:html:input_type(number):arg_name('Redirect delay, sec'):arg_section(7, 1)}">
		<tr>
			<td>
				<input form="st_f" class="st_f0" type="hidden" name="Field" data-prop-column="${args->field_name:html:default():input_type(select_social):input_props('with_empty=1'):arg_name(Save to database):arg_section(0, 0, 'Box', 'th-large')}">
				<div id="div" data-style="${args->div_style:html:default('border-radius:8px; min-width:300px; max-width:600px; background-color:#484745; color:white; text-align:center; padding:0.6em 1.2em'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(1, 1, 'Text', 'bars')}">
					<img src="${args->image_src:html:default('https://cdn.e-marketer.io/upload/362/185f3236b1b4ab52.png'):input_type(emarketer_media_url):arg_name(Logo):arg_section(0, 2, 'Box', 'th-large')}" data-style="${args->image_style:html:default('width:auto; height:auto'):input_type(css):input_props('with_responsive=1'):arg_name(Logo size):arg_section(0, 3, 'Box', 'th-large')}">
					<div>
					<div class="st_f1">
						${args->div_text:default(Did you find this helpfull ?):arg_name(Text):arg_section(1, 0, 'Text', 'bars')}
					</div>
					<center class="st_f2" style="display:none">
						<button class="$btn" onclick="_S_T.dismiss_action(${action_id:html})" data-style="${args->close_style:html:default('background-color:#5F8F55; color:white; margin:0.6em'):input_type(css):input_props('with_responsive=1'):arg_name(Close Button Style):arg_section(0, 5, 'Box', 'th-large')}">
							${args->close_text:default(Close):arg_name(Close Button Text):arg_section(0, 4, 'Box', 'th-large')}
						</button>
					</center>
				</div>
			</td>
		</tr>
		<tr>
			<td>
				<button form="st_f" type="submit" class="$flat_btn" with_responsive="1" data-style="width:100%; box-sizing:border-box; ${args->a1_style:html:default('background-color:#5F8F55; color:white; text-decoration:none; text-align:center; padding:0.4em'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(2, 1, 'Button 1', 'mouse-pointer')}" hover_style="${args->a1_h_style:html:default('background-color: #e7e719; color: rgb(40, 45, 87);'):input_type(css):arg_name(Hover Style):arg_section(2, 2, 'Button 1', 'mouse-pointer')}" data-v="${args->a1_value:html:default(Yes):arg_name(Save value):arg_section(2, 3, 'Button 1', 'mouse-pointer')}" onclick="_S_T.joyquery('ancestor::tbody:limit(1) .st_f0', this).get(0).value=this.getAttribute('data-v')">
					${args->a1_text:default(Yes):arg_name(Text):arg_section(2, 0, 'Button 1', 'mouse-pointer')}
				</button>
			</td>
		</tr>
		<tr>
			<td>
				<button form="st_f" type="submit" class="$flat_btn" with_responsive="1" data-style="width:100%; box-sizing:border-box; ${args->a2_style:html:default('background-color:#5F8F55; color:white; text-decoration:none; text-align:center; padding:0.4em'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(3, 1, 'Button 2', 'mouse-pointer')}" hover_style="${args->a2_h_style:html:default('background-color: #e7e719; color: rgb(40, 45, 87);'):input_type(css):arg_name(Hover Style):arg_section(3, 2, 'Button 2', 'mouse-pointer')}" data-v="${args->a2_value:html:default(No):arg_name(Save value):arg_section(3, 3, 'Button 2', 'mouse-pointer')}" onclick="_S_T.joyquery('ancestor::tbody:limit(1) .st_f0', this).get(0).value=this.getAttribute('data-v')">
					${args->a2_text:default(No):arg_name(Text):arg_section(3, 0, 'Button 2', 'mouse-pointer')}
				</button>
			</td>
		</tr>
		${block->with_a3:default(0):arg_name(With Button 3):arg_section(4, 0, 'Button 3', 'mouse-pointer')}
		<tr>
			<td>
				<button form="st_f" type="submit" class="$flat_btn" with_responsive="1" data-style="width:100%; box-sizing:border-box; ${args->a3_style:html:input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(4, 2, 'Button 3', 'mouse-pointer')}" hover_style="${args->a3_h_style:html:input_type(css):arg_name(Hover Style):arg_section(4, 3, 'Button 3', 'mouse-pointer')}" data-v="${args->a3_value:html:arg_name(Save value):arg_section(4, 4, 'Button 3', 'mouse-pointer')}" onclick="_S_T.joyquery('ancestor::tbody:limit(1) .st_f0', this).get(0).value=this.getAttribute('data-v')">
					${args->a3_text:arg_name(Text):arg_section(4, 1, 'Button 3', 'mouse-pointer')}
				</button>
			</td>
		</tr>
		${block->with_a4:default(0):arg_name(With Button 4):arg_section(5, 0, 'Button 4', 'mouse-pointer')}
		<tr>
			<td>
				<button form="st_f" type="submit" class="$flat_btn" with_responsive="1" data-style="width:100%; box-sizing:border-box; ${args->a4_style:html:input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(5, 2, 'Button 4', 'mouse-pointer')}" hover_style="${args->a4_h_style:html:input_type(css):arg_name(Hover Style):arg_section(5, 3, 'Button 4', 'mouse-pointer')}" data-v="${args->a4_value:html:arg_name(Save value):arg_section(5, 4, 'Button 4', 'mouse-pointer')}" onclick="_S_T.joyquery('ancestor::tbody:limit(1) .st_f0', this).get(0).value=this.getAttribute('data-v')">
					${args->a4_text:arg_name(Text):arg_section(5, 1, 'Button 4', 'mouse-pointer')}
				</button>
			</td>
		</tr>
		${block->with_a5:default(0):arg_name(With Button 5):arg_section(6, 0, 'Button 5', 'mouse-pointer')}
		<tr>
			<td>
				<button form="st_f" type="submit" class="$flat_btn" with_responsive="1" data-style="width:100%; box-sizing:border-box; ${args->a5_style:html:input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(6, 2, 'Button 5', 'mouse-pointer')}" hover_style="${args->a5_h_style:html:input_type(css):arg_name(Hover Style):arg_section(6, 3, 'Button 5', 'mouse-pointer')}" data-v="${args->a5_value:html:arg_name(Save value):arg_section(6, 4, 'Button 5', 'mouse-pointer')}" onclick="_S_T.joyquery('ancestor::tbody:limit(1) .st_f0', this).get(0).value=this.getAttribute('data-v')">
					${args->a5_text:arg_name(Text):arg_section(6, 1, 'Button 5', 'mouse-pointer')}
				</button>
			</td>
		</tr>
	</tbody>
</table>
```


## Fullscreen two steps popup



```
<table class="$responsive" data-style="border-collapse:collapse; ${args->style:html:default('width: sel(100%, auto);
height: sel(100%, auto);
background-image: url(''http://www.emarketer.com/wp-content/uploads/2018/05/shutterstock_587601533.jpg'');
background-size: cover;
background-color: white;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(0, 0, 'Box', 'th-large')}">
	<tr>
		<td data-style="position:relative; ${args->style_2:html:default('background-color: rgb(70, 62, 106);
color: rgb(256, 256, 256);
text-align: center;
vertical-align: middle;
padding-top: 10%;
padding-right: sel(10%, 10px);
padding-bottom: 10%;
padding-left: sel(10%, 10px);'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(0, 1, 'Box', 'th-large')}">
			<img src="${args->image_src:html:default('https://cdn.e-marketer.io/upload/362/185f3236b1b4ab52.png'):input_type(emarketer_media_url):arg_name(URL):arg_section(1, 0, 'Logo', 'image')}" style="${args->image_style:html:default('width:auto; height:auto; border:none'):input_type(css):input_props('with_responsive=1'):arg_name(Image style):arg_section(1, 1, 'Logo', 'image')}">
			<div id="sw" class="$switch-elem" data-case="0">
				<div data-case="0">
					<div data-style="margin:${args->margin:html:default('sel(18px, 8px)'):input_type(css_length):input_props('with_responsive=1'):arg_name(Paragraph spacing):arg_section(0, 2, 'Box', 'th-large')} 0; ${args->style_t1:html:default('color: white;
font-size: sel(28px, 5vw);
font-weight: 300;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(2, 0, 'Step 1', 'bars')}">
						${args->text_1:default(Text):arg_name(Line 1):arg_section(2, 2, 'Step 1', 'bars')}
					</div>
					<div data-style="margin:${args->margin:html} 0; ${args->style_t2:html:default('color: rgb(252, 244, 244);
font-size: sel(25px, 4vw);
text-transform: none;
padding-top: 15px;
padding-right: 15px;
padding-bottom: 0px;
padding-left: 15px;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(2, 1, 'Step 1', 'bars')}">
						${args->text_2:default('<strong>Would you like to shoot us a quick question?</strong>'):arg_name(Line 1):arg_section(2, 3, 'Step 1', 'bars')}
					</div>
					<div data-style="margin:${args->margin:html} 0">
						${settings->a:onclick('by_id.sw._set_case(1, null, false, {template: ''animator_fade''})')}
						<a class="$flat_btn" with_responsive="1" onclick="by_id.sw._set_case(1, null, false, {template: 'animator_fade'})" data-style="display:inline-block; width:${args->button_width:html:default('sel(110px, 33vw)'):input_type(css_length):input_props('with_responsive=1'):arg_name(Button Width):arg_section(0, 4, 'Box', 'th-large')}; height:${args->button_height:html:default(30px):input_type(css_length):input_props('with_responsive=1'):arg_name(Button Height):arg_section(0, 5, 'Box', 'th-large')}; line-height:${args->button_height:html}; ${args->yes_style:html:default('background-color: red;
color: white;
margin-top: 30px;
margin-right: 10px;
margin-bottom: 10px;
margin-left: 10px;'):input_type(css):arg_name(Yes Button Style):arg_section(2, 5, 'Step 1', 'bars')}" hover_style="${args->yes_h_style:html:default('background-color: rgb(83, 141, 94);
color: rgb(253, 253, 253);'):input_type(css):arg_name(Yes Button Hover Style):arg_section(2, 6, 'Step 1', 'bars')}">
							${args->yes_1:default(Yes):arg_name(Yes button text):arg_section(2, 4, 'Step 1', 'bars')}
						</a>
						<a href="javascript:" class="$emarketer_button_dont_show_again" data-action_id="${action_id:html}" data-style="display:inline-block; width:${args->button_width:html}; height:${args->button_height:html}; line-height:${args->button_height:html}; text-decoration:none; ${args->no_style:html:default('color:white; border:solid 1px'):input_type(css):arg_name(No Button Style):arg_section(2, 8, 'Step 1', 'bars')}">
							${args->no_1:default(No):arg_name(No button text):arg_section(2, 7, 'Step 1', 'bars')}
						</a>
					</div>
				</div>

				<div data-case="1" class="$cform st_f" ontplsubmit="emarketer.push(['Submit', '${action_id:html}', this._get_value_ex(), arguments[1], arguments[2]]); return true" ontplaftersubmit="this.parentNode._set_case('2', null, false, {template: 'animator_fade'}); var redir=this.dataset.redir, t=this.dataset.redirDelay; if (redir) setTimeout(function() {location.href=redir}, t*1000)" data-redir="${args->redir:html:arg_name(After submit redirect to this URL):arg_section(4, 2, 'Step 3', 'bars')}" data-redir-delay="${args->redir_delay:html:input_type(number):arg_name('Redirect delay, sec'):arg_section(4, 4, 'Step 3', 'bars')}">
					<div data-style="margin:${args->margin:html} 0">
						${args->text_3:default('Please leave your email, and our experts will answer your question shortly.'):arg_name(Line 1):arg_section(3, 0, 'Step 2', 'bars')}
					</div>
					<div data-style="margin:${args->margin:html} 0">
						<input form="st_f" name="Field 1" data-prop-column="${args->f1_db:html:default(first_name):input_type(select_social):input_props('with_empty=1'):arg_name('Field #1 save to database'):arg_section(3, 1, 'Step 2', 'bars')}" data-style="${args->f1_style:html:default('width: sel(22em, auto);
padding: 0.3em;
text-align: center;
font-size: sel(14px, 4vw);
color: rgb(55, 11, 11);'):input_type(css):input_props('with_responsive=1'):arg_name(Input style):arg_section(3, 12, 'Step 2', 'bars')}" placeholder="${args->f1:html:default(First Name):arg_name('Field #1 Placeholder Text'):arg_section(3, 2, 'Step 2', 'bars')}" ontplready="${args->f1_required:html:default('this.required=1'):input_type(checkbox):input_props('value_off=','value_on=this.required=1'):arg_name('Field #1 is required'):arg_section(3, 3, 'Step 2', 'bars')}">
					</div>
					<div data-style="margin:${args->margin:html} 0">
						<input form="st_f" name="Field 2" data-prop-column="${args->f2_db:html:default(last_name):input_type(select_social):input_props('with_empty=1'):arg_name('Field #2 save to database'):arg_section(3, 4, 'Step 2', 'bars')}" data-style="${args->f1_style:html}" placeholder="${args->f2:html:default(Last Name):arg_name('Field #2 Placeholder Text'):arg_section(3, 13, 'Step 2', 'bars')}" ontplready="${args->f2_required:html:input_type(checkbox):input_props('value_off=','value_on=this.required=1'):arg_name('Field #2 is required'):arg_section(3, 5, 'Step 2', 'bars')}">
					</div>
					<div data-style="margin:${args->margin:html} 0">
						<input form="st_f" name="Email" data-prop-column="${args->f3_db:html:default(email):input_type(select_social):input_props('with_empty=1'):arg_name(Email save to database):arg_section(3, 6, 'Step 2', 'bars')}" data-style="${args->f1_style:html}" placeholder="${args->f3:html:default(Email):arg_name(Email Placeholder Text):arg_section(3, 9, 'Step 2', 'bars')}" required="1" pattern="^[^\s@]+@[^\s@\.]+\.[^\s@]+$">
					</div>
					<div data-style="margin:${args->margin:html} 0">
						<textarea form="st_f" name="Field 4" data-prop-column="${args->f4_db:html:default(custom_t_1):input_type(select_social):input_props('with_empty=1'):arg_name(Comments save to database):arg_section(3, 7, 'Step 2', 'bars')}" data-style="height:${args->textarea_height:html:default(4em):input_type(css_length):input_props('with_responsive=1'):arg_name(Textarea height):arg_section(0, 3, 'Box', 'th-large')}; ${args->f1_style:html}" placeholder="${args->f4:html:default(Ask away!):arg_name(Comments Placeholder Text):arg_section(3, 14, 'Step 2', 'bars')}" ontplready="${args->f4_required:html:input_type(checkbox):input_props('value_off=','value_on=this.required=1'):arg_name(Comments is required):arg_section(3, 8, 'Step 2', 'bars')}"></textarea>
					</div>
					<div data-style="margin:${args->margin:html} 0">
						${settings->b:onclick('by_id.sw._set_case(2, null, false, {template: ''animator_fade''})')}
						<button form="st_f" type="submit" class="$flat_btn" with_responsive="1" data-style="display:inline-block; width:${args->button_width:html}; height:${args->button_height:html}; line-height:${args->button_height:html}; ${args->yes_style:html}" hover_style="${args->yes_h_style:html}" ontplready="this._by_id=by_id" data-onsubmit="this._by_id.sw._set_case(2, null, false, {template: 'animator_fade'})">
							${args->button_tex:default(SUBMIT):arg_name(Submit button):arg_section(3, 10, 'Step 2', 'bars')}
						</button>
					</div>
					<div data-style="margin:${args->margin:html} 0">
						<a href="javascript:" class="$emarketer_button_dont_show_again" data-action_id="${action_id:html}" data-style="color:inherit; text-decoration:inherit">
							${args->cancel:default('<span style="color:white;">No, I&#39;m not interested</span>'):arg_name(Cancel link):arg_section(3, 11, 'Step 2', 'bars')}
						</a>
					</div>
				</div>

				<div data-case="2">
					<div data-style="margin:${args->margin:html} 0; ${args->style_t4:html:default('color:white; font-size:sel(25px, 5vw)'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(4, 1, 'Step 3', 'bars')}">
						${args->text_4:default(Thank you!):arg_name(Line 1):arg_section(4, 0, 'Step 3', 'bars')}
					</div>
					<div data-style="margin:${args->margin:html} 0">
						<a class="$flat_btn" with_responsive="1" onclick="_S_T.dismiss_action(${action_id:html})" data-style="display:inline-block; width:${args->button_width:html}; height:${args->button_height:html}; line-height:${args->button_height:html}; ${args->yes_style:html}" hover_style="${args->yes_h_style:html}">
							${args->close_1:default(Close):arg_name(Close button text):arg_section(4, 3, 'Step 3', 'bars')}
						</a>
					</div>
				</div>
			</div>
			${block->show_close_button:default(1):arg_name(Show close button):arg_section(5, 0, 'Close Button', 'times-circle')}
			<div data-style="position:absolute; cursor:pointer; ${args->close_button_style:html:default('top:8px; right:8px;z-index:9999'):input_type(css):input_props('with_responsive=1'):arg_name(Close Button Style):arg_section(5, 1, 'Close Button', 'times-circle')}">
				${args->close_button:default('<div onmouseenter="this.style.backgroundColor=this.style.outlineColor" onmouseleave="this.style.backgroundColor=this.style.textDecorationColor" style="display: inline-block; vertical-align: text-bottom; width: 24px; height: 24px; box-sizing: border-box; border-top-left-radius: 50%; border-top-right-radius: 50%; border-bottom-right-radius: 50%; border-bottom-left-radius: 50%; border: 0px solid; -webkit-box-shadow: rgba(255, 255, 255, 0.2) 0px 1px 0px inset, rgba(0, 0, 0, 0.2) 0px 1px 2px; padding: 2px; background-color: rgba(0, 0, 0, 0); text-decoration-color: rgba(0, 0, 0, 0); outline-color: rgb(206, 54, 64); outline-width: 15px; color: rgb(248, 247, 247); cursor: pointer; transition: all 0.3s ease;" class="$emarketer_button_dont_show_again" data-action_id="${action_id}"><div style="display: block; width: 100%; height: 100%; transition: all 0.3s ease 0s; border-top-left-radius: 50%; border-top-right-radius: 50%; border-bottom-right-radius: 50%; border-bottom-left-radius: 50%; background-image: linear-gradient(-45deg, transparent 0%, transparent 43%, currentcolor 43%, currentcolor 59%, transparent 59%, transparent 100%), linear-gradient(45deg, transparent 0%, transparent 43%, currentcolor 43%, currentcolor 59%, transparent 59%, transparent 100%);"></div></div>'):input_type(dontshowagain):arg_name(Close button):arg_section(5, 2, 'Close Button', 'times-circle')}
			</div>
		</td>
	</tr>
</table>
```


## Form



```
<div class="$responsive" data-style="position:relative; overflow:hidden; ${args->box_style:html:default('max-width:700px; border:solid #979797 1px; background-color:white'):input_type(css):input_props('with_responsive=1'):arg_name(Box style):arg_section(0, 0, 'Box', 'th-large')}" >
	<table style="border-collapse:collapse; border:none">
		<tr style="border:none">
			<td style="border:none; background-image:url('${args->image_src:html:default('//counter.emarketer.com/images/html_customizer/banner-2.png'):input_type(emarketer_media_url):arg_name(Picture URL):arg_section(1, 0, 'Picture', 'image')}'); background-repeat:no-repeat; background-size:100% 100%; background-position:center">
				<div data-style="width:${args->image_width:html:default('sel(300px, 40vw)'):input_type(css_length):input_props('with_responsive=1'):arg_name(Image width):arg_section(1, 1, 'Picture', 'image')}; height:${args->image_height:html:default('sel(300px, 40vw)'):input_type(css_length):input_props('with_responsive=1'):arg_name(Image height):arg_section(1, 2, 'Picture', 'image')}"></div>
			</td>
			<td style="border:none; padding:0 1em">
				<div class="$switch-elem" data-case="a">
					<div data-case="a" class="$cform st_f" ontplsubmit="emarketer.push(['Submit', '${action_id:html}', this._get_value_ex(), arguments[1], arguments[2]]); return true" ontplaftersubmit="this.parentNode._set_case('b', null, false, {template: 'animator_fade'}); var redir=this.dataset.redir, t=this.dataset.redirDelay|0; if (redir) setTimeout(function() {location.href=redir}, t*1000)" data-redir="${args->redir:html:arg_name(After submit redirect to this URL):arg_section(6, 1, 'After submit', 'check')}" data-redir-delay="${args->redir_delay:html:input_type(number):arg_name('Redirect delay, sec'):arg_section(6, 2, 'After submit', 'check')}" style="margin:8px 0 10px">
						<div data-style="max-height:${args->image_height:html}">
							<div data-style="outline:0; ${args->title_style:html:default('text-align:center; color:black; font-size:sel(32px, 4vw); font-weight:bold'):input_type(css):input_props('with_responsive=1'):arg_name(Title style):arg_section(2, 1, 'Content', 'bars')}">
								${args->title:default(Your title goes here):arg_name(Title):arg_section(2, 0, 'Content', 'bars')}
							</div>
							<div data-style="outline:0; ${args->text_style:html:default('text-align:center; color:black; font-size:sel(14px, 4vw)'):input_type(css):input_props('with_responsive=1'):arg_name(Title style):arg_section(2, 3, 'Content', 'bars')}">
								${args->text:default('Sign up to our newsletter to get £10 off your first order and news of our latest deals and product releases.'):arg_name(Text):arg_section(2, 2, 'Content', 'bars')}
							</div>
							<div style="text-align:center">
								<input form="st_f" name="email" data-prop-column="email" pattern="^[^\s@]+@[^\s@\.]+\.[^\s@]+$" required="1" placeholder="Enter email" data-style="${args->email_input_style:html:default('width:sel(315px, 40vw); padding:sel(11px, 2px); margin:sel(8px, 6px) 0 sel(20px, 6px) 0; font-size:sel(14px, 4vw); color: #666666; background-color:white; border:solid #dadadc 1px; border-radius:0'):input_type(css):input_props('with_responsive=1'):arg_name(Email box style):arg_section(3, 0, 'Email box', 'envelope')}">
							</div>
							<div style="text-align:center">
								<button  form="st_f" type="submit" class="$btn" data-style="outline:0; ${args->button_style:html:default('background-color: rgb(67, 121, 89);
text-align: center;
border: solid rgb(65, 169, 95) 1px;
padding-top: 6px;
padding-right: 22px;
padding-bottom: 6px;
padding-left: 22px;
color: rgb(256, 256, 256);
cursor: pointer;
margin-bottom: 1em;'):input_type(css):input_props('with_responsive=1'):arg_name(Button style):arg_section(4, 1, 'Button', 'hand-o-up')}">
									${args->button_tex:default(SUBSCRIBE):arg_name(Text button):arg_section(4, 0, 'Button', 'hand-o-up')}
								</button>
							</div>
						</div>
					</div>
					<div data-case="b">
						${args->success:default(Thank you!):arg_name(Thank you text):arg_section(6, 0, 'After submit', 'check')}
					</div>
				</div>
			</td>
		</tr>
	</table>
	${block->show_close_button:default(1):arg_name(Show close button):arg_section(5, 0, 'Close Button', 'times-circle')}
	<div data-style="position:absolute; cursor:pointer; ${args->close_button_style:html:default('top:8px; right:8px;z-index:9999'):input_type(css):input_props('with_responsive=1'):arg_name(Close Button Style):arg_section(5, 1, 'Close Button', 'times-circle')}">
		${args->close_button:default('<img src="//counter.emarketer.com/images/close-buttons/black-16x16.png" class="$emarketer_button_dont_show_again" data-action_id="${action_id}">'):input_type(dontshowagain):arg_name(Close button):arg_section(5, 2, 'Close Button', 'times-circle')}
	</div>
</div>
```


## Form with select box



```
<div class="$responsive" data-style="position:relative; background-image:url(${args->bgimage_url:html:default('https://cdn.e-marketer.io/upload/362/2ced8f83fce5a056.png'):input_type(emarketer_media_url):arg_name(URL):arg_section(0, 1, 'Box', 'th-large')}); overflow:hidden; ${args->style:html:default('background-size: contain;
background-position: bottom;
background-repeat: no-repeat;
border-radius: 3px;
background-color: rgba(89, 151, 84, 0);
box-shadow: 0 0 7px 5px rgba(189, 148, 148, 0.7);
width: 380px;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(0, 0, 'Box', 'th-large')}">
    <link href="https://fonts.googleapis.com/css?family=Montserrat:400,700|Open+Sans:400,600" rel="stylesheet">
    ${block->show_close_button:default(1):arg_name(Show close button):arg_section(4, 0, 'Close button', 'close')}
    <div style="position:absolute; top:16px; right:16px; z-index:2">
        ${args->close_button:default('<div onmouseenter="this.style.backgroundColor=this.style.outlineColor" onmouseleave="this.style.backgroundColor=this.style.textDecorationColor" style="display: inline-block; vertical-align: text-bottom; width: 24px; height: 24px; box-sizing: border-box; border-top-left-radius: 50%; border-top-right-radius: 50%; border-bottom-right-radius: 50%; border-bottom-left-radius: 50%; border: 2px solid; -webkit-box-shadow: rgba(255, 255, 255, 0.2) 0px 1px 0px inset, rgba(0, 0, 0, 0.2) 0px 1px 2px; padding: 3px; background-color: rgb(207, 120, 58); text-decoration-color: rgb(207, 120, 58); outline-color: rgb(206, 54, 64); outline-width: 10px; color: rgb(10, 4, 4); cursor: pointer; transition: all 0.3s ease;" class="$emarketer_button_dont_show_again" data-action_id="${action_id}"><div style="display: block; width: 100%; height: 100%; transition: all 0.3s ease 0s; border-top-left-radius: 50%; border-top-right-radius: 50%; border-bottom-right-radius: 50%; border-bottom-left-radius: 50%; background-image: linear-gradient(-45deg, transparent 0%, transparent 46%, currentcolor 46%, currentcolor 56%, transparent 56%, transparent 100%), linear-gradient(45deg, transparent 0%, transparent 46%, currentcolor 46%, currentcolor 56%, transparent 56%, transparent 100%);"></div></div>'):input_type(dontshowagain):arg_name(Close button):arg_section(4, 1, 'Close button', 'close')}
    </div>
     <div class="$switch-elem" id="st_sw" data-case="a" data-style="width:100%; height:100%; box-sizing:border-box; ${args->shading_style:html:default('background-color: rgba(31, 40, 55, 0.81);'):input_type(css):input_props('with_responsive=1'):arg_name(Shading):arg_section(0, 2, 'Box', 'th-large')}; ${args->send_confirm_style:html:default('padding-top: 30px;
padding-right: sel(30px, 1vw);
padding-bottom: 30px;
padding-left: sel(30px, 1vw);
font-family: Open Sans,san-serif;
font-weight: normal;
font-size: sel(18px, 14px);
color: white;
text-align: center;'):input_type(css):input_props('with_responsive=1'):arg_name(Confirmation style):arg_section(7, 2, 'Email Box', 'envelope')}">
		<div data-case="a" class="$cform st_f" ontplsubmit="emarketer.push(['Submit', ${action_id:json:html}, this._get_value_ex(), arguments[1], arguments[2]]); return true" ontplaftersubmit="var sw=this.parentNode; sw._set_case('b', null, false, {template: 'animator_fade'}); var js=this.dataset.customJs, redir=this.dataset.redir, t=this.dataset.redirDelay; if (js.trim()) new Function('action_id', 'by_id', 'data', 'report_error', js).call(this, ${action_id:json:html}, by_id, this._get_value()); if (redir) setTimeout(function() {location.href=redir}, t*1000)" data-custom-js="${args->customjs:html:input_type(textarea):arg_name(After submit execute this JavaScript):arg_section(14, 1, 'After submit', 'check')}" data-redir="${args->redir:html:arg_name(After submit redirect to this URL):arg_section(14, 3, 'After submit', 'check')}" data-redir-delay="${args->redir_delay:html:input_type(number):arg_name('Redirect delay, sec'):arg_section(14, 4, 'After submit', 'check')}" style="position:relative; width:100%; height:100%">
            <div data-style="${args->message_style:html:default('color: rgb(16, 9, 9);
font-family: Montserrat,san-serif;
font-weight: normal;
font-size: sel(24px, 22px);
line-height: 1;
text-align: left;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(1, 1, 'Call message', 'bars')}">
                ${args->message_text:arg_name(Text):arg_section(1, 0, 'Call message', 'bars')}
            </div>
            <div id="st_m" data-style="${args->gift_style:html:default('margin-top: 8px;
color: rgb(242, 239, 239);
font-family: Montserrat,san-serif;
font-weight: 600;
font-size: 20px;
line-height: 1.55;
text-align: left;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(2, 1, 'Gift', 'gift')}">
                ${args->gift_text:default(Title goes here....):arg_name(Text):arg_section(2, 0, 'Gift', 'gift')}
            </div>
            <div>
                <div data-style="${args->content_style:html:default('color: rgb(244, 241, 241);
font-family: Open Sans,san-serif;
font-weight: 400;
font-size: 14px;
text-align: left;
padding-top: 15px;
padding-right: 1px;
padding-bottom: 19px;
padding-left: 1px;
line-height: 24px;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(3, 1, 'Info', 'bars')}">
                    ${args->content_text:default(Description goes here):arg_name(Text):arg_section(3, 0, 'Info', 'bars')}
                </div>

                <div data-style="${args->style7:html:default('text-align: left;
font-size: 18px;'):input_type(css):input_props('with_responsive=1'):arg_name(Fields area Style):arg_section(0, 3, 'Box', 'th-large')}">
					${block->with_f2:default(1):arg_name(With Name):arg_section(5, 0, 'Name Box', 'edit')}
					<div>
						<input form="st_f" name="Name" required="1" data-prop-column="${args->f2_db:html:default(first_name):input_type(select_social):input_props('with_empty=1'):arg_name(Name save to database):arg_section(5, 1, 'Name Box', 'edit')}" data-style="box-sizing:border-box; ${args->f1_style:html:default('margin-bottom: 20px;
padding: 15px;
font-family: Open Sans,san-serif;
font-weight: 300;
font-size: 14px;
width: sel(400px, 85%);
border: 1px solid rgb(62,62,62);
border-radius: 4px;
color: rgb(122,122,122);
text-align: left;
background-color: rgba(249, 247, 247, 0.88);
height: 40px;'):input_type(css):input_props('with_responsive=1'):arg_name(Input style):arg_section(5, 3, 'Name Box', 'edit')}" placeholder="${args->f2:html:default(Your First Name):arg_name(Name Placeholder Text):arg_section(5, 2, 'Name Box', 'edit')}">
					</div>
					${block->with_f6:default(0):arg_name(With Telephone):arg_section(6, 0, 'Telephone Box', 'edit')}
					<div>
						<input form="st_f" name="Phone" type="tel" required="${args->f6_req:html:input_type(checkbox):arg_name(Telephone is required field):arg_section(6, 2, 'Telephone Box', 'edit')}" data-prop-column="${args->f6_db:html:input_type(select_social):input_props('with_empty=1'):arg_name(Telephone save to database):arg_section(6, 1, 'Telephone Box', 'edit')}" data-style="box-sizing:border-box; ${args->f1_style:html}" placeholder="${args->f6:html:arg_name(Telephone Placeholder Text):arg_section(6, 3, 'Telephone Box', 'edit')}">
					</div>
					<div>
						<input form="st_f" name="Email" pattern="^[^\s@]+@[^\s@\.]+\.[^\s@]+$" required="1" data-prop-column="${args->f3_db:html:default(email):input_type(select_social):input_props('with_empty=1'):arg_name(Email save to database):arg_section(7, 0, 'Email Box', 'envelope')}" data-style="box-sizing:border-box; ${args->f1_style:html}" placeholder="${args->f3:html:default(Enter your email address):arg_name(Email Placeholder Text):arg_section(7, 1, 'Email Box', 'envelope')}" value="${email:html}" ontplready="this.value=this.value.trim()">
					</div>
					${block->with_f7:default(1):arg_name(With Line 2):arg_section(8, 0, 'Line 2 Box', 'edit')}
					<div>
						<input form="st_f" name="Line2" required="${args->f7_req:html:input_type(checkbox):arg_name(Line 2 is required field):arg_section(8, 2, 'Line 2 Box', 'edit')}" data-prop-column="${args->f7_db:html:default():input_type(select_social):input_props('with_empty=1'):arg_name(Line 2 save to database):arg_section(8, 1, 'Line 2 Box', 'edit')}" data-style="box-sizing:border-box; ${args->f1_style:html}" placeholder="${args->f7:html:default(Free variable):arg_name(Line 2 Placeholder Text):arg_section(8, 3, 'Line 2 Box', 'edit')}">
					</div>
					${block->with_f8:default(0):arg_name(With Line 3):arg_section(9, 0, 'Line 3 Box', 'edit')}
					<div>
						<input form="st_f" name="Line3" required="${args->f8_req:html:input_type(checkbox):arg_name(Line 3 is required field):arg_section(9, 2, 'Line 3 Box', 'edit')}" data-prop-column="${args->f8_db:html:input_type(select_social):input_props('with_empty=1'):arg_name(Line 3 save to database):arg_section(9, 1, 'Line 3 Box', 'edit')}" data-style="box-sizing:border-box; ${args->f1_style:html}" placeholder="${args->f8:html:arg_name(Line 3 Placeholder Text):arg_section(9, 3, 'Line 3 Box', 'edit')}">
					</div>
					${block->with_f9:default(1):arg_name(With Dropdown List):arg_section(10, 0, 'Dropdown List Box', 'edit')}
					<div>
						<select form="st_f" name="Dropdown" required="${args->f9_req:html:input_type(checkbox):arg_name(Dropdown List is required field):arg_section(10, 2, 'Dropdown List Box', 'edit')}" data-prop-column="${args->f9_db:html:default(size):input_type(select_social):input_props('with_empty=1'):arg_name(Dropdown List save to database):arg_section(10, 1, 'Dropdown List Box', 'edit')}" data-style="box-sizing:border-box; ${args->f1_style:html}">
							${args->f9_options:default('<option value="">Please Select</option>
<option value="VIC">VIC</option>
<option value="NSW">NSW</option>
<option value="QLD">QLD</option>
<option value="SA">SA</option>
<option value="WA">WA</option>
<option value="TAS">TAS</option>
<option value="ACT">ACT</option>
'):input_type(select_options):arg_name(Options):arg_section(10, 3, 'Dropdown List Box', 'edit')}
						</select>
					</div>
					${block->with_f5:default(0):arg_name(With Details):arg_section(11, 0, 'Details Box', 'edit')}
					<div>
						<textarea form="st_f" name="Details" data-style="box-sizing:border-box; ${args->f5_style:html:input_type(css):input_props('with_responsive=1'):arg_name(Input style):arg_section(11, 2, 'Details Box', 'edit')}" placeholder="${args->f5:html:arg_name(Details Placeholder Text):arg_section(11, 1, 'Details Box', 'edit')}"></textarea>
					</div>
					${block->with_f4:default(0):arg_name(With Checkbox):arg_section(12, 0, 'Checkbox', 'edit')}
					<div data-style="${args->style9:html:default('color: rgb(199, 179, 179);
font-size: 12px;
text-align: left;'):input_type(css):input_props('with_responsive=1'):arg_name(Checkbox Style):arg_section(12, 1, 'Checkbox', 'edit')}">
						<label>
							<input form="st_f" name="Checkbox" type="checkbox" data-prop-column="${args->f4_db:html:input_type(select_social):input_props('with_empty=1'):arg_name(Checkbox save to database):arg_section(12, 2, 'Checkbox', 'edit')}" value="1">
							${args->text_9:arg_name(Text):arg_section(12, 3, 'Checkbox', 'edit')}
						</label>
					</div>
				</div>

                <button form="st_f" type="submit" class="$flat_btn" with_responsive="1" style="display:block; border:0; white-space:normal; box-sizing:border-box; ${args->button_style:html:default('display: block;
padding-top: 12px;
padding-right: 20px;
padding-bottom: 12px;
padding-left: 20px;
font-family: Open Sans,san-serif;
background-color: rgb(249, 247, 247);
color: rgb(3, 1, 1);
border-radius: 50px;
text-transform: uppercase;
letter-spacing: 2px;
height: 45px;
width: 220px;
margin-top: 10px;
margin-right: 0px;
margin-bottom: 40px;
margin-left: 0px;'):input_type(css):arg_name(Style):arg_section(13, 1, 'Action button', 'check')}" hover_style="${args->button_h_style:html:default('display: block;
padding-top: 15px;
padding-right: 35px;
padding-bottom: 15px;
padding-left: 35px;
font-family: Open Sans,san-serif;
background-color: #111111;
color: #FFFFFF;
border-radius: 50px;
text-transform: uppercase;
letter-spacing: 2px;'):input_type(css):arg_name(Hover Style):arg_section(13, 2, 'Action button', 'check')}">
					${args->button_caption:default(Contact Me):arg_name(Caption):arg_section(13, 0, 'Action button', 'check')}
                </button>
            </div>
			<div data-style="${args->style9:html}">
				${args->ds:default(Free text goes here.......):arg_name(No text):arg_section(2, 2, 'Gift', 'gift')}
			</div>
        </div>
		<div data-case="b" id="st_b" data-style="${args->style10:html:default('color: rgb(199, 179, 179);'):input_type(css):input_props('with_responsive=1'):arg_name(Thank you text Style):arg_section(14, 2, 'After submit', 'check')}">
			${args->success:default('<div style="text-align: center; font-size: 30px; ">Awesome! We Will Keep You Posted.</div>
'):arg_name(Thank you text):arg_section(14, 0, 'After submit', 'check')}
		</div>
    </div>
</div>
```


## Form



```
<div class="$responsive" data-style="position:relative; background-image:url(${args->bgimage_url:html:input_type(emarketer_media_url):arg_name(URL):arg_section(0, 1, 'Box', 'th-large')}); overflow:hidden; ${args->style:html:default('background-size: contain;
background-position: bottom;
background-repeat: no-repeat;
border-radius: 3px;
background-color: rgb(151, 84, 84);
box-shadow: 0 0 7px 5px rgba(189, 148, 148, 0.7);
width: 380px;
color: rgba(42, 24, 24, 0.9);'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(0, 0, 'Box', 'th-large')}">
    <link href="https://fonts.googleapis.com/css?family=Montserrat:400,700|Open+Sans:400,600" rel="stylesheet">
    ${block->show_close_button:default(1):arg_name(Show close button):arg_section(4, 0, 'Close button', 'close')}
    <div style="position:absolute; top:16px; right:16px; z-index:2">
        ${args->close_button:default('<div onmouseenter="this.style.backgroundColor=this.style.outlineColor" onmouseleave="this.style.backgroundColor=this.style.textDecorationColor" style="display: inline-block; vertical-align: text-bottom; width: 24px; height: 24px; box-sizing: border-box; border-top-left-radius: 50%; border-top-right-radius: 50%; border-bottom-right-radius: 50%; border-bottom-left-radius: 50%; border: 2px solid; -webkit-box-shadow: rgba(255, 255, 255, 0.2) 0px 1px 0px inset, rgba(0, 0, 0, 0.2) 0px 1px 2px; padding: 3px; background-color: rgb(207, 120, 58); text-decoration-color: rgb(207, 120, 58); outline-color: rgb(206, 54, 64); outline-width: 10px; color: rgb(10, 4, 4); cursor: pointer; transition: all 0.3s ease;" class="$emarketer_button_dont_show_again" data-action_id="${action_id}"><div style="display: block; width: 100%; height: 100%; transition: all 0.3s ease 0s; border-top-left-radius: 50%; border-top-right-radius: 50%; border-bottom-right-radius: 50%; border-bottom-left-radius: 50%; background-image: linear-gradient(-45deg, transparent 0%, transparent 46%, currentcolor 46%, currentcolor 56%, transparent 56%, transparent 100%), linear-gradient(45deg, transparent 0%, transparent 46%, currentcolor 46%, currentcolor 56%, transparent 56%, transparent 100%);"></div></div>'):input_type(dontshowagain):arg_name(Close button):arg_section(4, 1, 'Close button', 'close')}
    </div>
	<style data-pc="${args->pc:html:default('rgb(127, 130, 154)'):input_type(color):arg_name(Input placeholder color):arg_section(5, 3, 'Name Box', 'edit')}" ontplready="var v=['::-webkit-input-placeholder', '::-moz-placeholder', ':-moz-placeholder', ':-ms-input-placeholder'], t='', i; for (i=0; i&lt;v.length; i++) t += '.st_sw '+v[i]+' {color: '+this.dataset.pc+' !important}'; if (this.styleSheet) this.styleSheet.cssText = t; else this.textContent = t;"></style>
     <div class="$switch-elem st_sw" id="st_sw" data-case="a" data-style="width:100%; height:100%; box-sizing:border-box; ${args->shading_style:html:default('background-color: rgb(256, 256, 256);'):input_type(css):input_props('with_responsive=1'):arg_name(Shading):arg_section(0, 2, 'Box', 'th-large')}; ${args->send_confirm_style:html:default('padding-top: 30px;
padding-right: sel(30px, 1vw);
padding-bottom: 30px;
padding-left: sel(30px, 1vw);
font-family: Open Sans,san-serif;
font-weight: normal;
font-size: sel(18px, 14px);
color: rgb(42, 24, 24);
text-align: center;'):input_type(css):input_props('with_responsive=1'):arg_name(Confirmation style):arg_section(7, 2, 'Email Box', 'envelope')}">
		<div data-case="a" class="$cform st_f" ontplsubmit="emarketer.push(['Submit', ${action_id:json:html}, this._get_value_ex(), arguments[1], arguments[2]]); return true" ontplaftersubmit="var sw=this.parentNode; sw._set_case('b', null, false, {template: 'animator_fade'}); var js=this.dataset.customJs, redir=this.dataset.redir, t=this.dataset.redirDelay; if (js.trim()) new Function('action_id', 'by_id', 'data', 'report_error', js).call(this, ${action_id:json:html}, by_id, this._get_value()); if (redir) setTimeout(function() {location.href=redir}, t*1000)" data-custom-js="${args->customjs:html:input_type(textarea):arg_name(After submit execute this JavaScript):arg_section(14, 1, 'After submit', 'check')}" data-redir="${args->redir:html:arg_name(After submit redirect to this URL):arg_section(14, 3, 'After submit', 'check')}" data-redir-delay="${args->redir_delay:html:input_type(number):arg_name('Redirect delay, sec'):arg_section(14, 4, 'After submit', 'check')}" style="position:relative; width:100%; height:100%">
            <div data-style="${args->message_style:html:default('color: rgb(16, 9, 9);
font-family: Montserrat,san-serif;
font-weight: normal;
font-size: sel(24px, 22px);
line-height: 1;
text-align: left;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(1, 1, 'Call message', 'bars')}">
                ${args->message_text:arg_name(Text):arg_section(1, 0, 'Call message', 'bars')}
            </div>
            <div id="st_m" data-style="${args->gift_style:html:default('margin-top: 8px;
color: rgb(9, 5, 5);
font-family: Montserrat,san-serif;
font-weight: 600;
font-size: 20px;
line-height: 1.55;
text-align: left;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(2, 1, 'Gift', 'gift')}">
                ${args->gift_text:default(Title):arg_name(Text):arg_section(2, 0, 'Gift', 'gift')}
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
line-height: 24px;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(3, 1, 'Info', 'bars')}">
                    ${args->content_text:default(Sub title):arg_name(Text):arg_section(3, 0, 'Info', 'bars')}
                </div>

                <div data-style="${args->style7:html:default('text-align: left;
font-size: 18px;
color: rgb(9, 5, 5);'):input_type(css):input_props('with_responsive=1'):arg_name(Fields area Style):arg_section(0, 3, 'Box', 'th-large')}">
					${block->with_f2:default(1):arg_name(With Name):arg_section(5, 0, 'Name Box', 'edit')}
					<div>
						<input form="st_f" name="Name" required="1" data-prop-column="${args->f2_db:html:default(first_name):input_type(select_social):input_props('with_empty=1'):arg_name(Name save to database):arg_section(5, 1, 'Name Box', 'edit')}" data-style="box-sizing:border-box; ${args->f1_style:html:default('margin-bottom: 20px;
padding: 15px;
font-family: Open Sans,san-serif;
font-weight: 300;
font-size: 14px;
width: sel(400px, 85%);
border: 1px solid rgb(62,62,62);
border-radius: 4px;
color: rgb(42, 24, 24);
text-align: left;
background-color: rgba(253, 253, 253, 0);
height: 40px;
color: rgb(13, 7, 7);'):input_type(css):input_props('with_responsive=1'):arg_name(Input style):arg_section(5, 4, 'Name Box', 'edit')}" placeholder="${args->f2:html:default(Name):arg_name(Name Placeholder Text):arg_section(5, 2, 'Name Box', 'edit')}">
					</div>
					${block->with_f6:default(0):arg_name(With Telephone):arg_section(6, 0, 'Telephone Box', 'edit')}
					<div>
						<input form="st_f" name="Phone" type="tel" required="${args->f6_req:html:input_type(checkbox):arg_name(Telephone is required field):arg_section(6, 2, 'Telephone Box', 'edit')}" data-prop-column="${args->f6_db:html:input_type(select_social):input_props('with_empty=1'):arg_name(Telephone save to database):arg_section(6, 1, 'Telephone Box', 'edit')}" data-style="box-sizing:border-box; ${args->f1_style:html}" placeholder="${args->f6:html:arg_name(Telephone Placeholder Text):arg_section(6, 3, 'Telephone Box', 'edit')}">
					</div>
					<div>
						<input form="st_f" name="Email" pattern="^[^\s@]+@[^\s@\.]+\.[^\s@]+$" required="1" data-prop-column="${args->f3_db:html:default(email):input_type(select_social):input_props('with_empty=1'):arg_name(Email save to database):arg_section(7, 0, 'Email Box', 'envelope')}" data-style="box-sizing:border-box; ${args->f1_style:html}" placeholder="${args->f3:html:default(E-mail):arg_name(Email Placeholder Text):arg_section(7, 1, 'Email Box', 'envelope')}" value="${email:html}" ontplready="this.value=this.value.trim()">
					</div>
					${block->with_f7:default(1):arg_name(With Line 2):arg_section(8, 0, 'Line 2 Box', 'edit')}
					<div>
						<input form="st_f" name="Line2" required="${args->f7_req:html:input_type(checkbox):arg_name(Line 2 is required field):arg_section(8, 2, 'Line 2 Box', 'edit')}" data-prop-column="${args->f7_db:html:default(phone):input_type(select_social):input_props('with_empty=1'):arg_name(Line 2 save to database):arg_section(8, 1, 'Line 2 Box', 'edit')}" data-style="box-sizing:border-box; ${args->f1_style:html}" placeholder="${args->f7:html:default(Phone):arg_name(Line 2 Placeholder Text):arg_section(8, 3, 'Line 2 Box', 'edit')}">
					</div>
					${block->with_f8:default(1):arg_name(With Line 3):arg_section(9, 0, 'Line 3 Box', 'edit')}
					<div>
						<input form="st_f" name="Line3" required="${args->f8_req:html:input_type(checkbox):arg_name(Line 3 is required field):arg_section(9, 2, 'Line 3 Box', 'edit')}" data-prop-column="${args->f8_db:html:default():input_type(select_social):input_props('with_empty=1'):arg_name(Line 3 save to database):arg_section(9, 1, 'Line 3 Box', 'edit')}" data-style="box-sizing:border-box; ${args->f1_style:html}" placeholder="${args->f8:html:default(Company):arg_name(Line 3 Placeholder Text):arg_section(9, 3, 'Line 3 Box', 'edit')}">
					</div>
					${block->with_f9:default(0):arg_name(With Dropdown List):arg_section(10, 0, 'Dropdown List Box', 'edit')}
					<div>
						<select form="st_f" name="Dropdown" required="${args->f9_req:html:input_type(checkbox):arg_name(Dropdown List is required field):arg_section(10, 2, 'Dropdown List Box', 'edit')}" data-prop-column="${args->f9_db:html:input_type(select_social):input_props('with_empty=1'):arg_name(Dropdown List save to database):arg_section(10, 1, 'Dropdown List Box', 'edit')}" data-style="box-sizing:border-box; ${args->f1_style:html}">
							${args->f9_options:input_type(select_options):arg_name(Options):arg_section(10, 3, 'Dropdown List Box', 'edit')}
						</select>
					</div>
					${block->with_f5:default(0):arg_name(With Details):arg_section(11, 0, 'Details Box', 'edit')}
					<div>
						<textarea form="st_f" name="Details" data-style="box-sizing:border-box; ${args->f5_style:html:input_type(css):input_props('with_responsive=1'):arg_name(Input style):arg_section(11, 2, 'Details Box', 'edit')}" placeholder="${args->f5:html:arg_name(Details Placeholder Text):arg_section(11, 1, 'Details Box', 'edit')}"></textarea>
					</div>
					${block->with_f4:default(0):arg_name(With Checkbox):arg_section(12, 0, 'Checkbox', 'edit')}
					<div data-style="${args->style9:html:default('color: rgb(9, 5, 5);
font-size: 12px;
text-align: left;'):input_type(css):input_props('with_responsive=1'):arg_name(Checkbox Style):arg_section(12, 1, 'Checkbox', 'edit')}">
						<label>
							<input form="st_f" name="Checkbox" type="checkbox" data-prop-column="${args->f4_db:html:input_type(select_social):input_props('with_empty=1'):arg_name(Checkbox save to database):arg_section(12, 2, 'Checkbox', 'edit')}" value="1">
							${args->text_9:arg_name(Text):arg_section(12, 3, 'Checkbox', 'edit')}
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
margin-right: 0px;
margin-bottom: 40px;
margin-left: 0px;'):input_type(css):arg_name(Style):arg_section(13, 1, 'Action button', 'check')}" hover_style="${args->button_h_style:html:default('display: block;
padding-top: 15px;
padding-right: 35px;
padding-bottom: 15px;
padding-left: 35px;
font-family: Open Sans,san-serif;
background-color: #111111;
color: #FFFFFF;
border-radius: 50px;
text-transform: uppercase;
letter-spacing: 2px;'):input_type(css):arg_name(Hover Style):arg_section(13, 2, 'Action button', 'check')}">
					${args->button_caption:default(Submit):arg_name(Caption):arg_section(13, 0, 'Action button', 'check')}
                </button>
            </div>
			<div data-style="${args->style9:html}">
				${args->ds:default(Fre text):arg_name(No text):arg_section(2, 2, 'Gift', 'gift')}
			</div>
        </div>
		<div data-case="b" id="st_b" data-style="${args->style10:html:default('color: rgb(199, 179, 179);'):input_type(css):input_props('with_responsive=1'):arg_name(Thank you text Style):arg_section(14, 2, 'After submit', 'check')}">
			${args->success:default('<div style="text-align: center; font-size: 30px; ">Awesome! We Will Keep You Posted.</div>
'):arg_name(Thank you text):arg_section(14, 0, 'After submit', 'check')}
		</div>
    </div>
</div>
```


## Collapsed sidebar with forms



```
<div class="$sidebar $a_add_params" action_id="${action_id:html}" row_height_px="${args->row_height_px:html:default(57):input_type(number):arg_name('Row height, px'):arg_section(0, 1, 'Frame', 'th-large')}" content_width="${args->content_width:html:default(300px):input_type(css_length):arg_name(Content width):arg_section(0, 2, 'Frame', 'th-large')}" button_style="${args->button_style:html:default('padding: 5px; background-color: black; border-radius: 50% 0 0 50%; cursor: pointer;'):input_type(css):arg_name(Show button style):arg_section(4, 0, 'Show/hide button', 'th-large')}" button_icon_url="${args->button_icon_url:html:default('https://cdn.personyze.com/upload/4241/76b9c172d72d5f5b.svg'):input_type(personyze_media_url):arg_name(Icon URL):arg_section(4, 1, 'Show/hide button', 'th-large')}" button_icon_style="display: block; ${args->button_icon_style:html:default('width: 16px; height: 16px; padding: 5px; font-size: 14px; line-height: 21px; background-color: #fff021; color: black; border-radius: 50%;'):input_type(css):arg_name(Show button icon style):arg_section(4, 2, 'Show/hide button', 'th-large')}" style="${args->style:html:default('font-family: OpenSans-Regular,Arial,sans-serif,monospace;
font-style: normal;
font-weight: 400;
font-size: 14px;
line-height: 23px;
letter-spacing: .03em;
color: #333;
height: 200px;'):input_type(css):arg_name(Style):arg_section(0, 0, 'Frame', 'th-large')}" data-json-params="${args->url_params:html:input_type(external_media_url_params):arg_name(URL additional parameters):arg_section(0, 3, 'Frame', 'th-large')}">
    ${block->item1:default(1):arg_name(With item 1):arg_section(1, 0, 'Item 1', 'th-large')}
    <div>
        <label label_style="${args->label1_style:html:default('padding: 5px; background-color: black; border-radius: 50% 0 0 50%;'):input_type(css):arg_name(Label style):arg_section(1, 1, 'Item 1', 'th-large')}" label_icon_url="${args->label1_icon_url:html:default('https://cdn.personyze.com/upload/4241/dac1c4cc20eb70fa.svg'):input_type(personyze_media_url):arg_name(Icon URL):arg_section(1, 2, 'Item 1', 'th-large')}" label_icon_style="${args->label1_icon_style:html:default('width: 26px; height: 26px; padding: 7px; background-color: #fff021; color: black; border-radius: 50%;'):input_type(css):arg_name(Icon style):arg_section(1, 3, 'Item 1', 'th-large')}" label_active_icon_style="${args->label1_active_icon_style:html:default('width: 26px; height: 26px; padding: 7px; background-color: #4194e4; color: white; border-radius: 50%;'):input_type(css):arg_name(Active icon style):arg_section(1, 4, 'Item 1', 'th-large')}" title_style="${args->title1_style:html:default('background-color: black; color: white; text-align: center; font-weight: 600;'):input_type(css):arg_name(Title style):arg_section(1, 6, 'Item 1', 'th-large')}">
            ${args->title1:default('<p>Interested in our offers?</p>
'):arg_name(Title):arg_section(1, 5, 'Item 1', 'th-large')}
        </label>
        <div content_style="${args->content1_1_style:html:default('height: 464px; padding: 6px; background-color: white;'):input_type(css):arg_name(Content style):arg_section(1, 8, 'Item 1', 'th-large')}">
            ${args->content1_1:default('<p style="margin: 0; text-align: center; font-size: 1.5rem;">Sign up for our newsletter and get a discount of $ 10 *!</p>

<form>
<div style="white-space: nowrap; margin-bottom: 25px;">
<div style="display: inline-block; width: 50%; vertical-align: top; padding-right: 10px; box-sizing: border-box;"><select data-prop-column="greeting" name="CustomFields[20]" style="width: 100%; box-sizing: border-box;"><option value="Greeting">Greeting</option><option value="Mr.">Mr.</option><option value="Mrs.">Mrs.</option><option value="Miss">Miss</option> </select></div>
<input data-prop-column="first_name" name="CustomFields[2]" placeholder="First name" required="1" style="width: 50%; box-sizing: border-box;" type="text" /></div>

<div style="margin-bottom: 25px;"><input data-prop-column="last_name" name="CustomFields[4]" placeholder="Last name" required="1" style="width: 100%; box-sizing: border-box;" type="text" /></div>

<div style="margin-bottom: 25px;"><input data-prop-column="email" name="email" pattern="^[^\s@]+@[^\s@\.]+\.[^\s@]+$" placeholder="E-mail" required="1" style="width: 100%; box-sizing: border-box;" type="text" /></div>

<div><label><input checked="checked" data-prop-column="check_1" name="CustomFields[18][]" required="1" style="display: none;" type="checkbox" value="Yes, I would like to receive newsletters" /> <span>Yes, I would like to receive newsletters</span> </label></div>

<div><label><input checked="checked" data-prop-column="check_2" name="CustomFields[19][]" required="1" style="display: none;" type="checkbox" value="Ja, stuur mij relevante deals afgestemd op mijn interesses" /> <span>Yes, send me relevant offers according to my interests</span> </label></div>

<div><input data-prop-column="format" name="format" type="hidden" value="h" /><button style="width: 100%; height: 40px; padding-left: 16px; padding-right: 16px; letter-spacing: 1px; font-family: inherit; font-weight: 600; font-size: 1.5rem; background-color: #fff021; color: #000; border-color: transparent; border-width: 2px; box-sizing: border-box; text-align: center; white-space: nowrap; cursor: pointer;" type="submit">Send</button></div>
</form>

<div>
<div>
<p style="padding: 6px 12px; margin: 10px -6px -6px; background-color: #fff787; text-align: center;">* For use with a minimum purchase of $ 299,- <a href="/terms" onclick="window.open(&quot;/terms&quot;,&quot;popup&quot;,&quot;width=600,height=600&quot;); return false;" style="color: #428bca; text-decoration: none;" target="popup">Read the full terms of the promotion here</a></p>
</div>
</div>
'):arg_name(Content):arg_section(1, 7, 'Item 1', 'th-large')}
        </div>
        <div content_style="${args->content1_2_style:html:default('height: 464px; padding: 20px; background-color: white; display: -webkit-box; display: -ms-flexbox; display: flex; -webkit-box-align: center; -ms-flex-align: center; align-items: center; -webkit-box-pack: center; -ms-flex-pack: center; justify-content: center; -webkit-box-orient: vertical; -ms-flex-direction: column; flex-direction: column; text-align: center;'):input_type(css):arg_name(After submit content style):arg_section(1, 10, 'Item 1', 'th-large')}">
            ${args->content1_2:default('<div style="font-size: 1.5rem; font-weight: 600;">Thank you for registering.<br />
<br />
Your promo code:</div>
<input style="display: none;" type="text" value="PROMOCODE10" /><button onclick="var input = this.previousElementSibling; input.focus(); input.select(); document.execCommand(&quot;copy&quot;); return false;" style="width: 100%; height: 40px; padding-left: 16px; padding-right: 16px; letter-spacing: 1px; font-family: inherit; font-weight: 600; font-size: 1.5rem; background-color: #fff021; color: #000; border-color: transparent; border-width: 2px; box-sizing: border-box; text-align: center; white-space: nowrap; cursor: pointer; margin-top: 25px;">PROMOCODE10 <img src="data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHdpZHRoPSIyNCIgaGVpZ2h0PSIyNCIgdmlld0JveD0iMCAwIDI0IDI0Ij4gICAgPHBhdGggZD0iTTAgMGgyNHYyNEgweiIgZmlsbD0ibm9uZSIvPiAgICA8cGF0aCBkPSJNMyA1SDF2MTZjMCAxLjEuOSAyIDIgMmgxNnYtMkgzVjV6bTE4LTRIN2MtMS4xIDAtMiAuOS0yIDJ2MTRjMCAxLjEuOSAyIDIgMmgxNGMxLjEgMCAyLS45IDItMlYzYzAtMS4xLS45LTItMi0yem0wIDE2SDdWM2gxNHYxNHoiLz48L3N2Zz4=" style="width: 16px; height: 16px; margin-bottom: -2px;" /></button>'):arg_name(After submit content):arg_section(1, 9, 'Item 1', 'th-large')}
        </div>
    </div>
    ${block->item2:default(1):arg_name(With item 2):arg_section(2, 0, 'Item 2', 'th-large')}
    <div>
        <label label_style="${args->label2_style:html:default('padding: 5px; background-color: black; border-radius: 50% 0 0 50%;'):input_type(css):arg_name(Label style):arg_section(2, 1, 'Item 2', 'th-large')}" label_icon_url="${args->label2_icon_url:html:default('https://cdn.personyze.com/upload/4241/801faecb744237f5.svg'):input_type(personyze_media_url):arg_name(Icon URL):arg_section(2, 2, 'Item 2', 'th-large')}" label_icon_style="${args->label2_icon_style:html:default('width: 26px; height: 26px; padding: 7px; background-color: #fff021; color: black; border-radius: 50%;'):input_type(css):arg_name(Icon style):arg_section(2, 3, 'Item 2', 'th-large')}" label_active_icon_style="${args->label2_active_icon_style:html:default('width: 26px; height: 26px; padding: 7px; background-color: #4194e4; color: white; border-radius: 50%;'):input_type(css):arg_name(Active icon style):arg_section(2, 4, 'Item 2', 'th-large')}" title_style="${args->title2_style:html:default('background-color: black; color: white; text-align: center; font-weight: 600;'):input_type(css):arg_name(Title style):arg_section(2, 6, 'Item 2', 'th-large')}">
            ${args->title2:default('<p>Can we help you?</p>
'):arg_name(Title):arg_section(2, 5, 'Item 2', 'th-large')}
        </label>
        <div content_style="${args->content2_1_style:html:default('height: 220px; padding: 6px; background-color: white;'):input_type(css):arg_name(Content style):arg_section(2, 8, 'Item 2', 'th-large')}">
            ${args->content2_1:default('<p style="margin: 0; text-align: center; font-size: 1.5rem;">We are happy to call you back!</p>

<form>
<div style="margin-bottom: 25px;"><input name="telephone_number" placeholder="Phone number" style="width: 100%; box-sizing: border-box;" type="text" /></div>

<div style="margin-bottom: 25px;"><input name="name" placeholder="Name" style="width: 100%; box-sizing: border-box;" type="text" /></div>

<div><button style="width: 100%; height: 40px; padding-left: 16px; padding-right: 16px; letter-spacing: 1px; font-family: inherit; font-weight: 600; font-size: 1.5rem; background-color: #fff021; color: #000; border-color: transparent; border-width: 2px; box-sizing: border-box; text-align: center; white-space: nowrap; cursor: pointer;" type="submit">Send</button></div>
</form>
'):arg_name(Content):arg_section(2, 7, 'Item 2', 'th-large')}
        </div>
        <div content_style="${args->content2_2_style:html:default('height: 220px; padding: 20px; background-color: white; display: -webkit-box; display: -ms-flexbox; display: flex; -webkit-box-align: center; -ms-flex-align: center; align-items: center; -webkit-box-pack: center; -ms-flex-pack: center; justify-content: center; -webkit-box-orient: vertical; -ms-flex-direction: column; flex-direction: column; text-align: center;'):input_type(css):arg_name(After submit content style):arg_section(2, 10, 'Item 2', 'th-large')}">
            ${args->content2_2:default('<div style="font-size: 1.5rem; font-weight: 600;">We will call you back within 24 hours on business days.</div>
'):arg_name(After submit content):arg_section(2, 9, 'Item 2', 'th-large')}
        </div>
    </div>
    ${block->item3:default(1):arg_name(With item 3):arg_section(3, 0, 'Item 3', 'th-large')}
    <div>
        <label label_style="${args->label3_style:html:default('padding: 5px; background-color: black; border-radius: 50% 0 0 50%;'):input_type(css):arg_name(Label style):arg_section(3, 1, 'Item 3', 'th-large')}" label_icon_url="${args->label3_icon_url:html:default('https://cdn.personyze.com/upload/4241/41c15dad75c0b966.svg'):input_type(personyze_media_url):arg_name(Icon URL):arg_section(3, 2, 'Item 3', 'th-large')}" label_icon_style="${args->label3_icon_style:html:default('width: 23px; height: 26px; padding: 7px 9px 7px 8px; background-color: #fff021; color: black; border-radius: 50%;'):input_type(css):arg_name(Icon style):arg_section(3, 3, 'Item 3', 'th-large')}" label_active_icon_style="${args->label3_active_icon_style:html:default('width: 23px; height: 26px; padding: 7px 9px 7px 8px; background-color: #4194e4; color: white; border-radius: 50%;'):input_type(css):arg_name(Active icon style):arg_section(3, 4, 'Item 3', 'th-large')}" title_style="${args->title3_style:html:default('background-color: black; color: white; text-align: center; font-weight: 600;'):input_type(css):arg_name(Title style):arg_section(3, 6, 'Item 3', 'th-large')}">
            ${args->title3:default('<p>Additional info</p>
'):arg_name(Title):arg_section(3, 5, 'Item 3', 'th-large')}
        </label>
        <div content_style="${args->content3_1_style:html:default('padding: 6px; background-color: white; font-size: 1.5rem;'):input_type(css):arg_name(Content style):arg_section(3, 8, 'Item 3', 'th-large')}">
            ${args->content3_1:default('<p style="margin: 0; text-align: center;">You can get more information about our products.</p>

<p style="text-align: center;"><img src="/images/image.jpg" /></p>
<a href="/products" style="display: block; width: 100%; height: 40px; padding-left: 16px; padding-right: 16px; letter-spacing: 1px; font-family: inherit; font-weight: 600; background-color: #fff021; color: #000; border-color: transparent; border-width: 2px; box-sizing: border-box; text-align: center; white-space: nowrap; cursor: pointer; line-height: 40px; text-decoration: none;">Look here </a>'):arg_name(Content):arg_section(3, 7, 'Item 3', 'th-large')}
        </div>
    </div>
</div>
```


## Form with timer



```
<div class="$responsive" data-style="position:relative; background-image:url(${args->bgimage_url:html}); overflow:hidden; ${args->style:html:default('background-size: contain;
background-position: bottom;
background-repeat: no-repeat;
border-radius: 3px;
background-color: rgba(89, 151, 84, 0);
box-shadow: 0 0 7px 5px rgba(189, 148, 148, 0.7);
width: 520px;
background-image: url(''https://cdn.personyze.com/upload/362/2ced8f83fce5a056.png'');
background-size: cover;')}">
    <link href="https://fonts.googleapis.com/css?family=Montserrat:400,700|Open+Sans:400,600" rel="stylesheet">
    <link href="https://fonts.googleapis.com/css?family=Arimo:400,700&display=swap" rel="stylesheet">
    ${block->show_close_button:default(1)}
    <div style="position:absolute; top:16px; right:16px; z-index:2">
        ${args->close_button:default('<div onmouseenter="this.style.backgroundColor=this.style.outlineColor" onmouseleave="this.style.backgroundColor=this.style.textDecorationColor" style="display: inline-block; vertical-align: text-bottom; width: 24px; height: 24px; box-sizing: border-box; border-top-left-radius: 50%; border-top-right-radius: 50%; border-bottom-right-radius: 50%; border-bottom-left-radius: 50%; border: 2px solid; -webkit-box-shadow: rgba(255, 255, 255, 0.2) 0px 1px 0px inset, rgba(0, 0, 0, 0.2) 0px 1px 2px; padding: 3px; background-color: rgb(207, 120, 58); text-decoration-color: rgb(207, 120, 58); outline-color: rgb(206, 54, 64); outline-width: 10px; color: rgb(10, 4, 4); cursor: pointer; transition: all 0.3s ease;" class="$personyze_button_dont_show_again" data-action_id="${action_id}"><div style="display: block; width: 100%; height: 100%; transition: all 0.3s ease 0s; border-top-left-radius: 50%; border-top-right-radius: 50%; border-bottom-right-radius: 50%; border-bottom-left-radius: 50%; background-image: linear-gradient(-45deg, transparent 0%, transparent 46%, currentcolor 46%, currentcolor 56%, transparent 56%, transparent 100%), linear-gradient(45deg, transparent 0%, transparent 46%, currentcolor 46%, currentcolor 56%, transparent 56%, transparent 100%);"></div></div>')}
    </div>
     <div class="$switch-elem" id="st_sw" data-case="a" data-style="width:100%; height:100%; box-sizing:border-box; ${args->shading_style:html:default('background-color: rgba(31, 40, 55, 0.81);')}; ${args->send_confirm_style:html:default('padding-top: 30px;
padding-right: sel(30px, 1vw);
padding-bottom: 30px;
padding-left: sel(30px, 1vw);
font-family: Open Sans,san-serif;
font-weight: normal;
font-size: sel(18px, 14px);
color: white;
text-align: center;')}">
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
			style="position:relative; width:100%; height:100%"
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
color: rgb(242, 239, 239);
font-family: Montserrat,san-serif;
font-weight: 600;
font-size: 20px;
line-height: 1.55;
text-align: left;')}">
                ${args->gift_text}
            </div>

            <!-- Timer -->
            <div style="margin:auto">
				${block->title:default(1)}
					<div data-style="${args->title_style:html:default('padding-top: 10px; color: white; font-size: 24px; text-align: center;')}">
						${args->title_text:default(TITLE GOES HERE)}
					</div>
				<div class="$timer_custom" data-value="{
					&quot;start&quot;:${args->value:html:default('{"type":"cookie_based","fixed_date_date":"","fixed_date_timezone":"","fixed_date_time":"","cookie_based_days":0,"cookie_based_hours":"","cookie_based_minutes":5,"cookie_based_restart":0,"cookie_based_restart_after":"hours","cookie_based_restart_after_hours":"1","cookie_based_restart_after_weekday":0,"restart_everytime_days":0,"restart_everytime_hours":"","restart_everytime_minutes":"","demo":1}')},
					&quot;design&quot;:{
						&quot;timer_background_style&quot;:${args->timer_background_style:json:html:default('white-space: nowrap;
vertical-align: middle;
text-align: center;
')},
						&quot;timer_box_style&quot;:${args->timer_box_style:json:html:default('display: inline-block;
text-align: center;
margin-top: 0;
margin-right: 4px;
margin-bottom: 0;
margin-left: 6px;
max-width: 100vw;
')},
						&quot;timer_caption_days&quot;:${args->timer_caption_days:json:html:default('Day(s)')},
						&quot;timer_caption_hours&quot;:${args->timer_caption_hours:json:html:default('Hour(s)')},
						&quot;timer_caption_minutes&quot;:${args->timer_caption_minutes:json:html:default('Minute(s)')},
						&quot;timer_caption_seconds&quot;:${args->timer_caption_seconds:json:html:default('Second(s)')},
						&quot;timer_caption_style&quot;:${args->timer_caption_style:json:html:default('color: white;
font-size: 8pt;
font-family: font-family: ''Arimo'', sans-serif;
font-weight: normal;
text-transform: uppercase;
margin-top: 3px;
margin-right: 0px;
margin-bottom: 0px;
margin-left: 0px;
')},
						&quot;timer_number_style&quot;:${args->timer_number_style:json:html:default('color: white;
font-size: 38pt;
font-family: font-family: ''Arimo'', sans-serif;
font-weight: bold;
line-height: 1em;
background-color: black;
padding-top: 4px;
padding-right: 4px;
padding-bottom: 8px;
padding-left: 14px;
min-width: 95px;
box-sizing: border-box;
border-radius: 5px;
letter-spacing: 10px;
')}
					}
				}" data-style="${args->timersubstrate_style:html:default('margin: 10px 20px;')}">
				</div>
				${block->content:default(1)}
					<div data-style="${args->content_style:html:default('padding-bottom:10px; color: white; font-size: 16px; text-align: center;')}">
						${args->content_text}
					</div>
				${block->button:default(0)}
					<a href="${args->href:html}" data-style="display:inline-block; ${args->tm_button_style:html}">
						${args->button_text}
					</a>
            </div>

            <div>
                <div data-style="${args->content_style:html}">
                    ${args->content_text}
                </div>

                <div data-style="${args->style7:html:default('text-align: left;
font-size: 18px;')}">
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
color: rgb(122,122,122);
text-align: left;
background-color: rgba(249, 247, 247, 0.88);
height: 40px;')}" placeholder="${args->f2:html:default(Your First Name)}">
					</div>
					${block->with_f6:default(0)}
					<div>
						<input form="st_f" name="Phone" type="tel" required="${args->f6_req:html}" data-prop-column="${args->f6_db:html}" data-style="box-sizing:border-box; ${args->f1_style:html}" placeholder="${args->f6:html}">
					</div>
					<div>
						<input form="st_f" name="Email" pattern="^[^\s@]+@[^\s@\.]+\.[^\s@]+$" required="1" data-prop-column="${args->f3_db:html:default(email)}" data-style="box-sizing:border-box; ${args->f1_style:html}" placeholder="${args->f3:html:default(Enter your email address)}" value="${email:html}" ontplready="this.value=this.value.trim()">
					</div>
					${block->with_f7:default(1)}
					<div>
						<input form="st_f" name="Line2" required="${args->f7_req:html}" data-prop-column="${args->f7_db:html:default(phone)}" data-style="box-sizing:border-box; ${args->f1_style:html}" placeholder="${args->f7:html:default(Phone)}">
					</div>
					${block->with_f8:default(0)}
					<div>
						<input form="st_f" name="Line3" required="${args->f8_req:html}" data-prop-column="${args->f8_db:html}" data-style="box-sizing:border-box; ${args->f1_style:html}" placeholder="${args->f8:html}">
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
					<div data-style="${args->style9:html:default('color: rgb(199, 179, 179);
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
background-color: rgb(249, 247, 247);
color: rgb(3, 1, 1);
border-radius: 50px;
text-transform: uppercase;
letter-spacing: 2px;
height: 45px;
width: 220px;
margin-top: 10px;
margin-right: 0px;
margin-bottom: 40px;
margin-left: 0px;')}" hover_style="${args->button_h_style:html:default('display: block;
padding-top: 15px;
padding-right: 35px;
padding-bottom: 15px;
padding-left: 35px;
font-family: Open Sans,san-serif;
background-color: #111111;
color: #FFFFFF;
border-radius: 50px;
text-transform: uppercase;
letter-spacing: 2px;')}">
					${args->button_caption:default(Submit)}
                </button>
            </div>
			<div data-style="${args->style9:html}">
				${args->ds:default(Free text goes here.......)}
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
${menu name='Timer start', icon='clock-o'}
	${menu args->value name='Type', type='timer_custom_params'}
${menu name='Timer design', icon='clock-o'}
	${menu args->timersubstrate_style name='Substrate', type='css', param='with_responsive=1'}
	${menu args->timer_background_style name='Background style', type='css', param='with_responsive=1'}
	${menu args->timer_box_style name='Box style', type='css', param='with_responsive=1'}
	${menu args->timer_caption_days name='Caption days'}
	${menu args->timer_caption_hours name='Caption days'}
	${menu args->timer_caption_minutes name='Caption days'}
	${menu args->timer_caption_seconds name='Caption days'}
	${menu args->timer_caption_style name='Caption style', type='css', param='with_responsive=1'}
	${menu args->timer_number_style name='Number style', type='css', param='with_responsive=1'}
${menu name='Timer Title', icon='align-left'}
	${menu block->title name='With header'}
	${menu args->title_text name='Text'}
	${menu args->title_style name='Style', type='css', param='with_responsive=1'}
${menu name='Timer Content', icon='align-left'}
	${menu block->content name='With сontent'}
	${menu args->content_text name='Text'}
	${menu args->content_style name='Style', type='css', param='with_responsive=1'}
${menu name='Timer Button', icon='hand-o-up'}
	${menu block->button name='With action button'}
	${menu args->button_text name='Text'}
	${menu args->href name='URL', type='a_attrs'}
	${menu args->tm_button_style name='Style', type='css', param='with_responsive=1'}
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


## Form with image

Image on the left on desktop and on bottom on mobile

```
<div class="$responsive" data-style="position:relative; overflow:hidden; ${args->box_style:html:default('max-width: 700px;
border: solid #979797 0px;
background-color: white;
height: 505.562px;
')}" >
	<style>
		.st-fl
		{	display: inline-flex;
			align-items: stretch;
		}
		.st-im
		{	width: ${args->image_width:default(320px)};
			height: ${args->image_height:default(420px)};
		}
		.st-cn
		{	min-height: ${args->image_height};
		}
		@media (max-width: 599px)
		{	.st-fl
			{	flex-direction: column-reverse;
			}
			.st-im
			{	width: ${args->image_width_mob:default(150px)};
				height: ${args->image_height_mob:default(180px)};
			}
			.st-cn
			{	min-height: auto;
				min-width: ${args->image_width_mob};
			}
		}
	</style>
	<div class="st-fl">
		<div style="border:none; background-image:url('${args->image_src:html:default('https://cdn.personyze.com/upload/6087/863d53883ece031b.jpeg')}'); background-repeat:no-repeat; background-size:cover; background-position:center">
			<div class="st-im"></div>
		</div>
		<div style="border:none; padding:0 1em">
			<div class="$switch-elem" data-case="a">
				<div
					data-case="a"
					class="$cform st_f"
					ontplsubmit="personyze.push(['Submit', '${action_id:html}', this._get_value_ex(), arguments[1], arguments[2]]); return true"
					ontplaftersubmit="this.parentNode._set_case('b', null, false, {template: 'animator_fade'}); var redir=this.dataset.redir, t=this.dataset.redirDelay|0; if (redir) setTimeout(function() {location.href=redir}, t*1000)"
					data-redir="${args->redir:html}"
					data-redir-delay="${args->redir_delay:html}"
					data-required_field_message="${args->required_field_message:html:default(Please fill out this field)}"
					data-invalid_value_message="${args->invalid_value_message:html:default(Invalid value for this input)}"
					style="margin:8px 0 10px"
				>
					<div class="st-cn">
						<div data-style="outline:0; ${args->title_style:html:default('text-align: center;
color: black;
font-size: sel(32px, 4vw);
font-weight: bold;
margin-top: 20px;
margin-right: 0px;
margin-bottom: 20px;
margin-left: 0px;
width: auto;
')}">
							${args->title:default('<img src="https://cdn.personyze.com/upload/362/4c53a78c4a0882c4.png" style="width:200px" /><br />
Your title')}
						</div>
						<div data-style="outline:0; ${args->text_style:html:default('text-align: center;
color: black;
font-size: sel(14px, 4vw);
margin-top: 0px;
margin-right: 0px;
margin-bottom: 20px;
margin-left: 0px;
')}">
							${args->text:default(Free text)}
						</div>
						${block->with_first_name:default(1)}
						<div style="text-align:center">
							<input form="st_f" name="first_name" data-prop-column="first_name" required="${args->first_name_required:html:default(1)}" placeholder="${args->first_name_placeholder:html:default(First Name)}" data-style="${args->first_name_input_style:html:default('width: sel(315px, 40vw);
padding: sel(11px, 2px);
margin-top: sel(8px, 6px);
margin-right: 0;
margin-bottom: sel(20px, 6px);
margin-left: 0;
font-size: sel(14px, 4vw);
color: #666666;
background-color: white;
border: solid #dadadc 1px;
border-radius: 0;
')}">
						</div>
						<div style="text-align:center">
							<input form="st_f" name="email" data-prop-column="email" pattern="^[^\s@]+@[^\s@\.]+\.[^\s@]+$" required="1" placeholder="${args->email_placeholder:html:default(Email)}" data-style="${args->email_input_style:html:default('width: sel(315px, 40vw);
padding: sel(11px, 2px);
margin-top: sel(8px, 6px);
margin-right: 0;
margin-bottom: sel(20px, 6px);
margin-left: 0;
font-size: sel(14px, 4vw);
color: #666666;
background-color: white;
border: solid #dadadc 1px;
border-radius: 0;
')}">
						</div>
						<div style="text-align:center">
							<button form="st_f" type="submit" class="$btn" data-style="outline:0; ${args->button_style:html:default('line-height: 1.42;
text-decoration: none;
text-align: center;
white-space: normal;
font-weight: 700;
text-transform: uppercase;
letter-spacing: .3em;
display: inline-block;
padding-top: 11px;
padding-right: 20px;
padding-bottom: 11px;
padding-left: 20px;
margin: 15px;
width: 320px;
min-width: 90px;
vertical-align: middle;
cursor: pointer;
border: 1px solid transparent;
background-color: #111111;
')}">
								${args->button_tex:default(SUBSCRIBE)}
							</button>
						</div>
						${block->with_terms:default(1)}
						<div data-style="${args->terms_style:html:default('text-align: center;
height: 30px;
margin-top: 0px;
margin-right: 0px;
margin-bottom: 11px;
margin-left: 0px;
')}">
							${args->terms:default('By signing up to our newsletter, you agree to our Terms &amp; Conditions.')}
						</div>
					</div>
				</div>
				<div data-case="b">
					${args->success:default(Thank you!)}
				</div>
			</div>
		</div>
	</div>
	${block->show_close_button:default(1)}
	<div data-style="position:absolute; cursor:pointer; ${args->close_button_style:html:default('top: 8px;
right: 8px;
z-index: 9999;
')}">
		${args->close_button:default('<div onmouseenter="this.style.backgroundColor=this.style.outlineColor" onmouseleave="this.style.backgroundColor=this.style.textDecorationColor" style="display: inline-block; vertical-align: text-bottom; width: 24px; height: 24px; box-sizing: border-box; border-radius: 50%; border: 0px solid; box-shadow: none; padding: 2px; background-color: rgba(0, 0, 0, 0); text-decoration-color: rgba(0, 0, 0, 0); outline-color: rgb(206, 54, 64); outline-width: 15px; color: rgb(10, 4, 4); cursor: pointer; transition: all 0.3s ease 0s;" class="$personyze_button_dont_show_again" data-action_id="${action_id}"><div style="display: block; width: 100%; height: 100%; transition: all 0.3s ease 0s; border-radius: 50%; background-image: linear-gradient(-45deg, transparent 0%, transparent 43%, currentcolor 43%, currentcolor 59%, transparent 59%, transparent 100%), linear-gradient(45deg, transparent 0%, transparent 43%, currentcolor 43%, currentcolor 59%, transparent 59%, transparent 100%);"></div></div>')}
	</div>
</div>

${menu name='Box', icon='th-large'}
	${menu args->box_style name='Box style', type='css', param='with_responsive=1'}
${menu name='Picture', icon='image'}
	${menu args->image_src name='Picture URL', type='personyze_media_url'}
	${menu args->image_width name='Image width', type='css_length'}
	${menu args->image_width_mob name='Image width - mobile', type='css_length'}
	${menu args->image_height name='Image height', type='css_length'}
	${menu args->image_height_mob name='Image height - mobile', type='css_length'}
${menu name='Content', icon='bars'}
	${menu args->title name='Title'}
	${menu args->title_style name='Title style', type='css', param='with_responsive=1'}
	${menu args->text name='Text'}
	${menu args->text_style name='Title style', type='css', param='with_responsive=1'}
${menu name='First name box', icon='user'}
	${menu block->with_first_name name='With First name'}
	${menu args->first_name_required name='First name is required', type='checkbox', param='value_on=1', param='value_off='}
	${menu args->first_name_placeholder name='First name placeholder text', type='text'}
	${menu args->first_name_input_style name='First name box style', type='css', param='with_responsive=1'}
${menu name='Email box', icon='envelope'}
	${menu args->email_placeholder name='Email placeholder text', type='text'}
	${menu args->email_input_style name='Email box style', type='css', param='with_responsive=1'}
${menu name='Button', icon='hand-o-up'}
	${menu args->button_tex name='Text button'}
	${menu args->button_style name='Button style', type='css', param='with_responsive=1'}
${menu name='Close Button', icon='times-circle'}
	${menu block->show_close_button name='Show close button'}
	${menu args->close_button_style name='Close Button Style', type='css', param='with_responsive=1'}
	${menu args->close_button name='Close button', type='dontshowagain'}
${menu name='Terms box', icon='user'}
	${menu block->with_terms name='With terms'}
	${menu args->terms name='Terms text', type='text'}
	${menu args->terms_style name='Terms style', type='css', param='with_responsive=1'}
${menu name='After submit', icon='check'}
	${menu args->success name='Thank you text'}
	${menu args->redir name='After submit redirect to this URL'}
	${menu args->redir_delay name='Redirect delay, sec', type='number'}
${menu name='Other', icon='sliders'}
	${menu args->required_field_message name='Required field message'}
	${menu args->invalid_value_message name='Invalid value message'}
```
