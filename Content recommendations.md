## Content recommendation: Default vertical



```
<div style="${args->style:html:default('border:none'):input_type(css):arg_name(Style):arg_section(0, 0, 'Frame', 'th-large')}">
	${block->title:default(0):arg_name(With title bar):arg_section(1, 0, 'Title', 'bookmark')}
	<div style="${args->title_style:html:default('color:black; background-color:#E6E6E6; font-weight:bold; text-align:center; padding:0.2em'):input_type(css):arg_name(Style):arg_section(1, 2, 'Title', 'bookmark')}">
		${block->x:default(1):arg_name(With close button):arg_section(2, 0, 'Close button', 'close')}
		<div style="float:right; cursor:pointer; margin:0 0 .3em .3em">
			${args->x:default('<img src="https://counter.personyze.com/images/close-buttons/round-transparent-black-2-16x16.png" style="width:16px" class="$personyze_button_dont_show_again" data-action_id="${action_id}">'):input_type(dontshowagain):arg_name(Close button):arg_section(2, 1, 'Close button', 'close')}
		</div>
		${args->title:default(Articles selection):arg_name(Text):arg_section(1, 1, 'Title', 'bookmark')}
		<div style="clear:both"></div>
	</div>
	<table style="border-collapse:separate; border-spacing:2px">
		${foreach sum_articles_week as p order by p->n_viewed desc limit 5}
			<tr>
				<td style="vertical-align:middle">
					<a href="${p->content_url:html:arg_name(Link target URL):arg_section(4, 0, 'Link target URL', 'link'):column_tags('url','custom text')}" target="_blank">
						<img src="${p->image_big_url:html:arg_name(Item image):arg_section(3, 0, 'Image', 'image'):column_tags(image)}" style="display:block; ${args->img_css:html:default('width:auto; height:auto; max-width:70px; max-height:70px; border:double white 5px'):input_type(css):arg_name(Image properties):arg_section(3, 1, 'Image', 'image')}">
					</a>
				</td>
				<td style="vertical-align:middle">
					<a href="${p->content_url:html:arg_name(Link target URL):arg_section(4, 0, 'Link target URL', 'link'):column_tags('url','custom text')}" target="_blank">
						${p->title:arg_name(Item text):arg_section(3, 2, 'Image', 'image')}
					</a>
				</td>
			</tr>
		${end}
	</table>
</div>
```


## Content recommendation: with background, vertical



```
<div style="${args->style:html:default('border:none'):input_type(css):arg_name(Style):arg_section(0, 0, 'Frame', 'th-large')}">
	${block->title:default(0):arg_name(With title bar):arg_section(1, 0, 'Title', 'bookmark')}
	<div style="${args->title_style:html:default('color:black; background-color:#E6E6E6; font-weight:bold; text-align:center; padding:0.2em'):input_type(css):arg_name(Style):arg_section(1, 2, 'Title', 'bookmark')}">
		${block->x:default(1):arg_name(With close button):arg_section(2, 0, 'Close button', 'close')}
		<div style="float:right; cursor:pointer; margin:0 0 .3em .3em">
			${args->x:default('<img src="https://counter.personyze.com/images/close-buttons/round-transparent-black-2-16x16.png" style="width:16px" class="$personyze_button_dont_show_again" data-action_id="${action_id}">'):input_type(dontshowagain):arg_name(Close button):arg_section(2, 1, 'Close button', 'close')}
		</div>
		${args->title:default(Articles selection):arg_name(Text):arg_section(1, 1, 'Title', 'bookmark')}
		<div style="clear:both"></div>
	</div>
	<table style="border-collapse:separate; border-spacing:5px">
		${foreach ar as p}
			<tr>
				<td style="vertical-align:middle; padding:0">
					<a href="${p->content_url:html:arg_name(Link target URL):arg_section(5, 0, 'Link target URL', 'link'):column_tags('url','custom text')}" target="_blank">
						<img src="${p->image_big_url:html:arg_name(Item image):arg_section(3, 0, 'Image', 'image'):column_tags(image)}" style="display:block; ${args->width_1:html:default('width:auto; height:auto; max-width:70px; max-height:70px; border:none'):input_type(css):arg_name(Item image style):arg_section(3, 1, 'Image', 'image')}">
					</a>
				</td>
				<td style="vertical-align:middle; padding:0 0 0 8px">
					<table style="width:100%; height:${args->height_1:html:default(70px):input_type(css_length):input_props('with_options=auto')}; ${args->td_css:html:default('background-color:silver'):input_type(css):arg_name(Text background):arg_section(4, 2, 'Text', 'align-justify')}">
						<tr>
							<td style="vertical-align:middle; padding:4px">
								<a href="${p->content_url:html:arg_name(Link target URL):arg_section(5, 0, 'Link target URL', 'link'):column_tags('url','custom text')}" target="_blank" style="${args->a_css:html:default('color:#6587AB'):input_type(css):arg_name(Text color):arg_section(4, 1, 'Text', 'align-justify')}">
									${p->title:arg_name(Item text):arg_section(4, 0, 'Text', 'align-justify')}
								</a>
							</td>
						</tr>
					</table>
				</td>
			</tr>
		${end}
	</table>
</div>
```


## Content Widget

First article image is bigger than the rest of articles

```
<div class="$responsive">
	<style>
		img.st-zoom {transition:transform ease 0.3s; transform: scale(1)}
		img.st-zoom:hover {transform: scale(calc(${args->img_zoom_on_hover:default(120)} / 100))}
	</style>
	${block->with_hover_image:default(0)}
	<style>
		img.st-zoom {transition-property:opacity; transform: scale(1); opacity: 1}
		img.st-zoom:hover {transform: scale(1); opacity: 0}

		img.st-zoom:last-child {transition:transform ease 0.3s; transform: scale(1)}
		img.st-zoom:last-child:hover {transform: scale(calc(${args->img_zoom_on_hover} / 100)); opacity: 1}

		img.st-zoom + div > img {transition:opacity ease 0.3s; opacity: 0}
		img.st-zoom + div > img:hover {opacity: 1}
	</style>
	<table style="${args->table_style:html:default('border-collapse: separate;
border-spacing: 2px;
max-width: 320px;
')}">
		<caption>
			${block->title:default(1)}
			<div style="display:flex; align-items:stretch; ${args->title_style:html:default('text-align: left;
font-size: 18px;
')}">
				<div style="flex-grow:1000">
					${args->title:default(See also)}
				</div>
				${block->x:default(1)}
				<div style="cursor:pointer; margin:0 0 .3em .3em">
					${args->x:default('<svg viewBox="0 0 24 24" width="22" height="22" enable-background="new 0 0 24 24" fill="#000" class="$personyze_button_dont_show_again" data-action_id="${action_id}"><path d="M12.0119629,2.0039062C6.491272,2.0006104,2.0131836,6.4733276,2.0098877,11.9940186S6.4793091,21.9927979,12,21.9960938c2.6522827,0.0043335,5.1970215-1.0482178,7.0712891-2.9248047c1.875-1.8734131,2.9291992-4.4147949,2.9307861-7.0653076C22.0053711,6.4852905,17.5326538,2.0072021,12.0119629,2.0039062z M12.0122681,20.9960938c-4.9684448,0.0033569-8.9988403-4.0215454-9.0022583-8.9899902C3.0066528,7.0377197,7.0316162,3.0072632,12,3.0039062c2.387085-0.0042725,4.6774292,0.9428711,6.3642578,2.6318359c1.687439,1.6858521,2.6363525,3.9728394,2.6379395,6.3581543C21.0056152,16.9622803,16.9806519,20.9926758,12.0122681,20.9960938z M12.7069702,12l3.1816406-3.1816406c0.1905518-0.194397,0.1905518-0.5054932,0-0.6998901c-0.1932373-0.1972046-0.5097656-0.2003784-0.7069702-0.0071411L12,11.2929688L8.8183594,8.1113892c-0.194397-0.1904907-0.5054932-0.1904907-0.6998901,0C7.9212646,8.3046265,7.9180908,8.6211548,8.1113281,8.8183594L11.2929688,12l-3.1816406,3.1816406c-0.09375,0.09375-0.1463623,0.2208862-0.1464233,0.3534546c0,0.276123,0.2238159,0.5,0.499939,0.500061c0.1326294,0.0001831,0.2598877-0.0525513,0.3535156-0.1464844L12,12.7070312l3.1816406,3.1816406c0.0936279,0.0939331,0.2208862,0.1466675,0.3535156,0.1464844v0.000061c0.1325684-0.000061,0.2596436-0.0527344,0.3533936-0.1464233c0.1953125-0.1952515,0.1953125-0.5118408,0.000061-0.7071533L12.7069702,12z"></path></svg>')}
				</div>
			</div>
		</caption>
		${foreach articles as p order by p->time_created desc limit 5}
			<tr>
				<td style="${args->td_align:html:default('vertical-align: top;
')}">
					<div style="position:relative">
						<a data-personyze-click-target="articles ${p->internal_id:html}" href="${p->content_url:html}" target="${args->target:html:default(_self)}" style="position:relative; display:inline-block; overflow:hidden; color:inherit; text-decoration:inherit">
							<img class="st-zoom" src="${p->image_big_url:html}" style="${args->img_css:html:default('width: auto;
height: auto;
max-width: 100px;
max-height: 100px;
border: none;
')}">

							${if p->image_medium_url <> ''}
								${block->with_hover_image:default(0)}
								<div style="position:absolute; left:0; top: 0; width:100%; height:100%">
									<img src="${p->image_medium_url:html}" style="${args->img_css:html}">
								</div>
							${end}
						</a>

						${block->with_new_badge:default(1)}
						<span>
							${if unix_timestamp() - p->time_created <= args->badge_if_newer:default(2851200)}
								<div data-style="position: absolute; ${args->new_badge_style:html:default('top: 0;
left: 48px;
font-size: 14px;
text-shadow: rgba(255,255,255,0.5) 0px 3px 3px;
background-color: rgb(50, 101, 219);
color: rgb(250, 246, 246);
display: flex;
justify-content: center;
align-items: center;
padding: 0.3em;
')}">
									<span data-style="${args->new_badge_text_style:html:default('font-size: 16px;
font-weight: 600;
')}">${args->new_badge_text:default(NEW)}</span>
								</div>
							${end}
						</span>

						${block->with_time_badge:default(0)}
						<span>
							${if p->custom_i_1 - unix_timestamp() >= 0}
								<div data-style="position: absolute; ${args->time_badge_style:html:default('top: 0;
left: 48px;
font-size: 14px;
text-shadow: rgba(255,255,255,0.5) 0px 3px 3px;
background-color: rgb(50, 101, 219);
color: rgb(250, 246, 246);
display: flex;
justify-content: center;
align-items: center;
padding: 0.3em;
')}">
								<span data-style="${args->time_badge_text_style:html:default('font-size: 16px;
font-weight: 600;
')}">${args->time_badge_text:default(Special offer till)}</span>
									${block->with_time_badge_countdown}
									<span data-end="${p->custom_i_1:html- unix_timestamp()}" data-d="${args->time_badge_days:html:default(days)}" data-h="${args->time_badge_hr:html:default(hr)}" data-m="${args->time_badge_min:html:default(min)}" data-s="${args->time_badge_sec:html:default(sec)}" ontplready="var t=this, end=t.dataset.end|0, d=t.dataset.d, h=t.dataset.h, m=t.dataset.m, s=t.dataset.s; (function p() {var r=end-new Date().getTime()/1000; t.parentNode.parentNode.style.display = r<=0 ? 'none' : ''; t.textContent = ns.sec_to_span(r - r%(r >= 3*24*60*60 ? 24*60*60 : r > 24*60*60 ? 60*60 : 1), s, m, h, d); if (r <= 24*60*60) setTimeout(p, 1000)})()"></span>
								</div>
							${end}
						</span>

						${block->with_wishlist_badge:default(0)}
						<span class="$switch-elem"
							data-case="${foreach articles_interactions as w where w->internal_id = p->internal_id and w->interaction_status = 'favorite' limit 1}on${end}"
							data-p="${p->internal_id:html}"
							data-style="position:absolute; transition: all 0.3s ease; ${args->wishlist_style:html:default('top: 5px;
right: 5px;
color: rgb(119, 181, 115);
font-size: 18px;
')}"
							onclick="var on=this._get_case(); _S_T.push([on ? 'Article Unliked' : 'Article Liked', this.dataset.p]); this._set_case(on ? '' : 'on'); event.stopPropagation(); event.preventDefault()"
						>
							<div data-case="" class="$hint" style="${args->wishlist_off_style:html}">
								<span data-content="1">${args->wishlist_add_text:default(Add to wishlist)}</span>
								<hr class="$icon heart-o">
							</div>
							<div data-case="on" class="$hint" style="${args->wishlist_on_style:html:default('background-color: rgba(177, 93, 93, 0);
')}">
								<span data-content="1">${args->wishlist_rm_text:html:default(Remove from wishlist)}</span>
								<hr class="$icon heart">
							</div>
						</span>

						${block->with_db_badge:default(0)}
						<span>
							<div data-style="position: absolute; ${args->db_badge_style:html:default('top: 0;
left: 0px;
font-size: 14px;
text-shadow: rgba(255,255,255,0.5) 0px 3px 3px;
background-color: rgb(50, 101, 219);
color: rgb(250, 246, 246);
display: flex;
justify-content: center;
align-items: center;
padding: 0.3em;
')}">
								${block->with_db_badge_icon}
								<hr class="$icon ${args->db_badge_text_icon:html:default(bookmark)}">
								<span data-style="${args->db_badge_text_style:html:default('font-size: 16px;
font-weight: 600;
')}">${args->db_badge_text:default('${p->custom_2}')}</span>
							</div>
						</span>
					</div>
				</td>
				<td style="${args->td_align:html}">
					<a data-personyze-click-target="articles ${p->internal_id:html}" href="${p->content_url:html}" target="${args->target:html}" style="display:block; position:relative; color:inherit; text-decoration:inherit">
						<div style="${args->name_style:html:default('border-left: solid #A20000 3px;
margin-top: 0;
margin-right: 0;
margin-bottom: 0;
margin-left: 10px;
padding-top: 0;
padding-right: 0;
padding-bottom: 0;
padding-left: 6px;
font-size: 14px;
color: #716363;
')}">
							${p->title}


							${block->with_date:default(1)}
							<div style="${args->date_column_style:html:default('padding-top: 0;
padding-right: 0;
padding-bottom: 1em;
padding-left: 0;
font-weight: 600;
')}" ontplready="this.innerHTML = window._S_T ? _S_T.ftime.strftime('${args->date_column_format:html:default('%B %d, %Y')}', ${args->date_column:html:default('${p->data_last_modified}')}) : '';"></div>



							${block->rating:default(0)}
							<span>
								<hr class="$rating" data-value="${p->rank:html:default(0)}" style="${args->rating_style:html:default('color: yellow;
--bgcolor: white;
--border-color: rgba(225, 214, 214, 0.87);
width: 10em;
height: 1.8em;
')}">
							</span>

							${block->stats_1day:default(1)}
                            <span>
                                ${foreach sum_products_1day as s where s->internal_id = p->internal_id limit 1}
                                    ${if s->n_viewed >= args->hide_no_view_1day:default(3)}
                                        ${if s->n_goal >= args->hide_no_goal_1day:default(1)}
                                            <div style="${args->text_style_1day:html:default('padding-top: 1em;
padding-right: 0;
padding-bottom: 1em;
padding-left: 0;
font-weight: 600;
')}">
                                                ${if s->n_viewed > 0}
                                                    ${args->n_viewed_1day:default('<div>This article has been popular today! ${s->n_viewed*1} views.</div>
')}
                                                ${end}
                                                ${if s->n_goal > 0}
                                                    ${args->n_goal_1day:default('<div>${s->n_goal*1}&nbsp; downloads today</div>
')}
                                                ${end}
                                            </div>
                                        ${end}
                                    ${end}
                                ${end}
                            </span>

                            ${block->stats_week:default(0)}
                            <span>
                                ${foreach sum_products_week as s where s->internal_id = p->internal_id limit 1}
                                    ${if s->n_viewed >= args->hide_no_view_week:default(3)}
                                        ${if s->n_goal >= args->hide_no_goal_week:default(1)}
                                            <div style="${args->text_style_week:html:default('padding-top: 1em;
padding-right: 0;
padding-bottom: 1em;
padding-left: 0;
font-weight: 600;
')}">
                                                ${if s->n_viewed > 0}
                                                    ${args->n_viewed_week:default('<div>This article has been popular in the last week! ${s->n_viewed*1} views this week.</div>
')}
                                                ${end}
                                                ${if s->n_goal > 0}
                                                    ${args->n_goal_week:default('<div>${s->n_goal*1}&nbsp; downloads this week</div>
')}
                                                ${end}
                                            </div>
                                        ${end}
                                    ${end}
                                ${end}
                            </span>
						</div>
						<div style="${args->desc_style:html:default('margin-top: 0;
margin-right: 10px;
margin-bottom: 10px;
margin-left: 0;
font-size: 18px;
')}">
							${p->description}
						</div>
					</a>
				</td>
			</tr>
			${block->with_separator:default(1)}
			<tr>
				<td colspan="2">
					<div style="${args->hr_style:html:default('height: 1px;
margin-top: 8px;
margin-right: 0;
margin-bottom: 8px;
margin-left: 0;
')}"></div>
				</td>
			</tr>
		${end}
	</table>
	${block->em:default(1)}
	<span ontplready="
		var tr = this.previousElementSibling.getElementsByTagName('tr')[0];
		if (tr && tr.children.length==2)
		{	var td0=tr.children[0], td1=tr.children[1], d0=td0.children[0], a0=d0.children[0], a1=td1.children[0], imgs=a0.getElementsByTagName('img'), name=a1.children[0], desc=a1.children[1];
			tr.removeChild(td1);
			td0.colSpan = 2;
			td0.insertBefore(a1, d0);
			td0.appendChild(desc);
			imgs[0].style.cssText += ';'+this.dataset.imgStyle;
			if (imgs[1]) imgs[1].style.cssText += ';'+this.dataset.imgStyle;
			name.style.cssText += ';'+this.dataset.nameStyle;
			desc.style.cssText += '; position:absolute; '+this.dataset.descStyle;
		}
" data-img-style="${args->em_img_css:html:default('width: auto;
height: auto;
max-width: 100%;
max-height: 200px;
border: none;
')}" data-name-style="${args->em_name_style:html:default('border-left: solid #A20000 8px;
margin-top: 0;
margin-right: 0;
margin-bottom: 18px;
margin-left: 0;
padding-top: 0;
padding-right: 0;
padding-bottom: 0;
padding-left: 6px;
font-size: 26px;
color: black;
background-color: #F5F5F5;
font-family: HelveticaNeueBold;
')}" data-desc-style="${args->em_desc_style:html:default('right:0; bottom:0; color:white; font-family: HelveticaNeueBold')}"></span>
</div>

${menu name='Frame', icon='th-large'}
	${menu args->table_style name='Table Style', type='css'}
	${menu block->with_separator name='With Separator'}
	${menu args->hr_style name='Separator Style', type='css'}
${menu name='Title', icon='bookmark'}
	${menu block->title name='With title bar'}
	${menu args->title name='Text'}
	${menu args->title_style name='Style', type='css'}
${menu name='Close button', icon='close'}
	${menu block->x name='With close button'}
	${menu args->x name='Close button', type='dontshowagain'}
${menu name='Image', icon='image'}
	${menu p->image_big_url name='Item image', column_tags='image'}
	${menu args->img_css name='Image Size', type='css'}
	${menu args->em_img_css name='Emphasized Image Size', type='css'}
${menu name='Zoom image on hover', icon='bars'}
	${menu args->img_zoom_on_hover name='Zoom on hover, %', type='number'}
${menu name='Hover alternative image', icon='image', description='On mouse hover, show additional item images when available on the article feed.'}
	${menu block->with_hover_image name='With hover image', onchange='block.with_zoom_image=block.with_hover_image^1||""'}
	${menu p->image_medium_url name='Hover image', column_tags='image'}
${menu name='New badge', icon='align-justify', description='Set "New" badge to appear for items debut recently.
You may choose a time frame for an article to be considered new. For new accounts/articles feed, all articles are new until the day setting condition has been met.'}
	${menu block->with_new_badge name='With new badge'}
	${menu args->badge_if_newer name='Show NEW badge if newer than', type='date', param='is_span=true', param='format=%0..999d days'}
	${menu args->new_badge_style name='Badge style', type='css', param='with_responsive=1'}
	${menu args->new_badge_text_style name='Badge text style', type='css', param='with_responsive=1'}
	${menu args->new_badge_text name='Text'}
${menu name='Time-based badge', icon='align-justify'}
	${menu block->with_time_badge name='With time-based badge'}
	${menu args->time_badge_style name='Badge style', type='css', param='with_responsive=1'}
	${menu args->time_badge_text_style name='Badge text style', type='css', param='with_responsive=1'}
	${menu args->time_badge_text name='Text'}
	${menu p->custom_i_1 name='Catalog field with end date', description='UNIX-timestamp'}
	${menu block->with_time_badge_countdown name='With days/time remaining'}
	${menu args->time_badge_days name='Time remaining: "days" text'}
	${menu args->time_badge_hr name='Time remaining: "hours" text'}
	${menu args->time_badge_min name='Time remaining: "minutes" text'}
	${menu args->time_badge_sec name='Time remaining: "seconds" text'}
${menu name='Add to wishlist', icon='bars', description='Show save to wishlist icon, on click item will be saved to Personyze wishlist. Items can be included in email/site widgets when using the wishlist algorithm. You can also set JS to report to your site when a visitor is saving an item to a wishlist.'}
	${menu block->with_wishlist_badge name='With add to wishlist'}
	${menu args->wishlist_style name='Style', type='css'}
	${menu args->wishlist_off_style name='Off icon style', type='css'}
	${menu args->wishlist_add_text name='Off tooltip (add to wishlist)'}
	${menu args->wishlist_on_style name='On icon style', type='css'}
	${menu args->wishlist_rm_text name='On tooltip (remove from wishlist)'}
${menu name='Icon or text badge', icon='star', description='Show text taken from catalog field'}
	${menu block->with_db_badge name='With db badge'}
	${menu args->db_badge_style name='Block style', type='css'}
	${menu block->with_db_badge_icon name='With icon'}
	${menu args->db_badge_text_icon name='Icon', type='icon'}
	${menu args->db_badge_text_style name='Icon style', type='css'}
	${menu args->db_badge_text name='Text'}
${menu name='Article Name', icon='bars'}
	${menu block->em name='Emphasize First Item'}
	${menu p->title name='Article Name'}
	${menu args->name_style name='Article Name Style', type='css'}
	${menu args->em_name_style name='Emphasized Name Style', type='css'}
	${menu p->description name='Article Description'}
	${menu args->desc_style name='Article Description Style', type='css'}
	${menu args->em_desc_style name='Emphasized Description Style', type='css'}
	${menu args->td_align name='Vertical Alignment', type='css'}
${menu name='Date', icon='calendar', description='Show date.'}
	${menu block->with_date name='With rating'}
	${menu args->date_column name='Date column'}
	${menu args->date_column_format name='Date format'}
	${menu args->date_column_style name='Style', type='css'}
${menu name='Link target URL', icon='link'}
	${menu p->content_url name='Link target URL', column_tags='url, custom text'}
	${menu args->target name='Open link in', type='a_target'}
${menu name='Rating', icon='star', description='Show article rating when available
This requires you to populate "Rank" on your article feed.'}
	${menu block->rating name='With rating'}
	${menu p->rank name='Rating'}
	${menu args->rating_style name='Colors', type='css', param='vars=--bgcolor:color; --border-color:color'}
${menu name='Site statistics: 1-day', icon='bar-chart', description='Show number of viewed or purchases in the last 24 hours for a given item as tracked by Personyze. You can set a condition not to show if the number of views/purchases is below X number.'}
	${menu block->stats_1day name='Site statistics: 1day'}
	${menu args->hide_no_view_1day name='Hide statistics if less views than', type='number', param='min=0'}
	${menu args->hide_no_goal_1day name='Hide statistics if less goals than', type='number', param='min=0'}
	${menu args->text_style_1day name='Style', type='css'}
	${menu args->n_viewed_1day name='Text'}
	${menu args->n_goal_1day name='Text'}
${menu name='Site statistics: week', icon='bar-chart', description='Show number of viewed or purchases in the last week for a given item as tracked by Personyze. You can set a condition not to show if the number of views/purchases is below X number.'}
	${menu block->stats_week name='Site statistics: week'}
	${menu args->hide_no_view_week name='Hide statistics if less views than', type='number', param='min=0'}
	${menu args->hide_no_goal_week name='Hide statistics if less goals than', type='number', param='min=0'}
	${menu args->text_style_week name='Style', type='css'}
	${menu args->n_viewed_week name='Text'}
	${menu args->n_goal_week name='Text'}
```


## Default Vertical List



```
<div style="${args->a_style3:html:default('color: #444;
font-family: arial,sans-serif;
font-size: 12px;
line-height: 18px;
max-width: 450px;'):input_type(css):arg_name(Style):arg_section(0, 0, 'Box', 'th-large')}">
	<div style="${args->a_style:html:default('text-align: left;
padding-top: 25px;
padding-right: 0;
padding-bottom: 25px;
padding-left: 15px;
font-family: "caecilla",serif;
color: rgb(106, 67, 67);
text-transform: uppercase;
font-weight: bold;
font-size: 22px;'):input_type(css):arg_name(Style):arg_section(1, 0, 'Title', 'bookmark')}">
		${args->line:default(Recommended For You):arg_name(Text):arg_section(1, 1, 'Title', 'bookmark')}
	</div>
	<div style="display:flex; flex-wrap:wrap; justify-content:space-between; align-items:stretch">
		${foreach recom_articles as p limit 4}
			<a data-personyze-click-target="products ${p->internal_id:html}" href="${p->content_url:html:default('p->content_url')}" style="display:block; position:relative; ${args->a_style4:html:default('margin-top: 0px;
margin-right: 21px;
margin-bottom: 20px;
margin-left: 21px;
border: -43px solid #bababa;
text-align: center;
width: 140px;
box-shadow: 0px 0px 20px rgba(0, 0, 0, 0.09);
text-decoration: none;'):input_type(css):arg_name(Cell):arg_section(2, 2, 'Cell', 'bars')}">
				<div style="margin-bottom:4em; ${args->a_style40:html:default('					padding:10px 15px
				'):input_type(css):arg_name(Cell):arg_section(2, 3, 'Cell', 'bars')}">
					<img src="${p->image_big_url:html:default('p->image_big_url')}" alt="${p->title:html}" title="${p->title:html}" style="width:auto; height:auto; ${args->a_style7:html:default('max-height: 100px;
margin-bottom: 10px;
border: none;
max-width: 120px;
height: auto;
width: auto;'):input_type(css):arg_name(Product image style):arg_section(2, 1, 'Cell', 'bars')}">
					<div style="${args->a_style5:html:default('color: #b72913;
font-size: 13px;
font-weight: bold;
text-align: center;'):input_type(css):arg_name(Product name):arg_section(2, 0, 'Cell', 'bars')}">
						${p->title}
					</div>
				</div>
				<div style="position:absolute; width:100%; bottom:10px; text-align:center">
					<div style="display:inline-block; ${args->a_style6:html:default('background-color: #a70050;
border-bottom: 0px solid #b4a600;
border-left: 0px solid #fff045;
border-right: 0px solid #d5c614;
border-top: 0px solid #fff045;
color: rgb(256, 256, 256);
font-size: 14px;
padding-top: 5px;
padding-right: 20px;
padding-bottom: 5px;
padding-left: 20px;
-webkit-appearance: none;'):input_type(css):arg_name(Style):arg_section(3, 1, 'Button', 'bars')}">
						${args->line3:default(View):arg_name(Text):arg_section(3, 0, 'Button', 'bars')}
					</div>
				</div>
			</a>
		${end}
	</div>
</div>
```


## With rating



```
<div class="$responsive" data-style="box-sizing:border-box; background-color:${args->bg:html:default('#41436e'):input_type(color):arg_name(Background color):arg_section(0, 0, 'Frame', 'th-large')}; ${args->style:html:default('max-width: 520px;
border: none;
line-height: 1.42857143;
color: white;
font-family: Roboto,Arial,sans-serif;
font-weight: 500;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(0, 1, 'Frame', 'th-large')}">
	${block->title:default(1):arg_name(With title bar):arg_section(1, 0, 'Title', 'bookmark')}
	<div data-style="${args->title_style:html:default('padding:16px; font-family: "Roboto Condensed","Arial Narrow",Arial,sans-serif; font-size:20px; font-weight:700'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(1, 2, 'Title', 'bookmark')}">
		${block->x:default(1):arg_name(With close button):arg_section(2, 0, 'Close button', 'close')}
		<div style="float:right; cursor:pointer; margin:0 0 .3em .3em">
			${args->x:default('<div class="$personyze_button_dont_show_again" data-action_id="${action_id}" style="display: inline-block; vertical-align: text-bottom; width: 24px; height: 24px; box-sizing: border-box; border-radius: 50%; border: 2px solid; box-shadow: rgba(255, 255, 255, 0.2) 0px 1px 0px inset, rgba(0, 0, 0, 0.2) 0px 1px 2px; padding: 3px; background-color: rgb(85, 85, 85); text-decoration-color: rgb(85, 85, 85); outline-color: rgb(206, 54, 64); outline-width: 10px; color: white; cursor: pointer; transition: all 0.3s ease 0s;">
<div style="display: block; width: 100%; height: 100%; transition: all 0.3s ease 0s; border-radius: 50%; background-image: linear-gradient(-45deg, transparent 0%, transparent 46%, currentcolor 46%, currentcolor 56%, transparent 56%, transparent 100%), linear-gradient(45deg, transparent 0%, transparent 46%, currentcolor 46%, currentcolor 56%, transparent 56%, transparent 100%);"><br />
</div>
</div>
'):input_type(dontshowagain):arg_name(Close button):arg_section(2, 1, 'Close button', 'close')}
		</div>
		${args->title:default(Articles selection):arg_name(Text):arg_section(1, 1, 'Title', 'bookmark')}
		<div style="clear:both"></div>
	</div>
	<div style="display:flex; flex-flow:row; flex-wrap:wrap">
		${foreach sum_last_viewed_categories_articles as p where p->for_period='week' order by p->n_viewed desc limit 5}
			<div style="box-sizing:border-box; width:${args->cell_width:html:default(260px):input_type(css_length):input_props('with_responsive=1'):arg_name(Cell width):arg_section(0, 2, 'Frame', 'th-large')}">
				<div data-style="display:flex; align-items:center; ${args->a_style:html:default('font-size: 16px;
margin: 5px;'):input_type(css):input_props('with_responsive=1'):arg_name(Cell style):arg_section(3, 1, 'Cell', 'bars')}" onmouseenter="this._s=this.style.cssText; this.style.cssText+=';'+this.dataset.hoverStyle" onmouseleave="if (this._s) this.style.cssText=this._s" data-hover-style="${args->a_hover_style:html:default('box-shadow: 0 0 10px #888;'):input_type(css):arg_name(Style):arg_section(3, 2, 'Cell', 'bars')}">
					<a href="${p->content_url:html}" data-style="flex-grow:100; color:inherit; text-decoration:none; padding:${args->a_padding:html:default(16px):input_type(css_length):input_props('with_responsive=1'):arg_name(Padding):arg_section(3, 3, 'Cell', 'bars')}">
						${p->title:arg_name(Item text):arg_section(3, 0, 'Cell', 'bars')}
						${block->rating:default(1):arg_name(With rating):arg_section(4, 0, 'Rating', 'star-half-empty')}
						<div data-style="${args->rating_style:html:default('color:#f2c71a'):input_type(css):input_props('with_responsive=1'):arg_name(Rating style):arg_section(4, 4, 'Rating', 'star-half-empty')}">
							<input class="$rating" value="${p->custom_1:html:default(0):arg_name(Rating):arg_section(4, 1, 'Rating', 'star-half-empty')}" max="${args->rank_max:html:default(5):input_type(number):arg_name(Maximum rating number that corresponds to 100%):arg_section(4, 3, 'Rating', 'star-half-empty')}" style="background-color:${args->bg:html}">
						</div>
						${block->rating_text:default(1):arg_name(With rating text):arg_section(4, 5, 'Rating', 'star-half-empty')}
						<div data-style="${args->rating_text_style:html:input_type(css):input_props('with_responsive=1'):arg_name(Rating text style):arg_section(4, 6, 'Rating', 'star-half-empty')}">
							${p->custom_1:html:default(0)}
							${args->of:default(out of):arg_name(Of):arg_section(4, 2, 'Rating', 'star-half-empty')}
							${args->rank_max:html}

							${block->rating_votes:default(1):arg_name(With no. of votes):arg_section(4, 7, 'Rating', 'star-half-empty')}
							<span>
								${args->votes_before:default('('):arg_name('No. of votes: text before'):arg_section(4, 8, 'Rating', 'star-half-empty')}${p->custom_i_1:html:default(0):arg_name(No. of votes):arg_section(4, 9, 'Rating', 'star-half-empty')}${args->votes_after:default(' Ratings)'):arg_name('No. of votes: text after'):arg_section(4, 10, 'Rating', 'star-half-empty')}
							</span>
						</div>
					</a>
					<div style="padding:${args->a_padding:html}; padding-left:0; padding-top:0; padding-bottom:0; text-align:right; ${args->arrow_style:html:default('font-size:22px;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(3, 4, 'Cell', 'bars')}">
						>
					</div>
				</div>
			</div>
		${end}
	</div>
</div>
```


## Content recommendations: Zoomed pictures



```
<div class="$responsive" data-style="display:inline-block; ${args->style:html:input_type(css):input_props('with_responsive=1'):default('border:none'):arg_name(Style):arg_section(1, 2, 'Frame', 'th-large')}">
	${block->title:default(0):arg_name(With title bar):arg_section(2, 0.1)}
	<table data-style="width:100%; border-collapse:collapse; border:none; ${args->title_bg:html:input_type(css):input_props('with_responsive=1'):default('background-color:#E6E6E6'):arg_name(Style):arg_section(2, 2, 'Title', 'bookmark')}">
		<tr>
			<td data-style="vertical-align:middle; ${args->title_style:html:input_type(css):input_props('with_responsive=1'):default('color:black; font-size:sel(16px,4vw); font-weight:bold; text-align:center; padding:0.2em'):arg_name(Title style):arg_section(2, 3)}">
				${args->title:arg_name(Text):arg_section(2, 1):default('Articles selection')}
			</td>
			${block->with_arrows:default(0):arg_name(With arrow buttons):arg_section(2.3, 0.1, 'With slider arrows', 'arrows-h')}
			<td style="width:1px; white-space:nowrap; vertical-align:middle">
				<a id="button_back" class="$flat_btn" style="${args->btn_style:html:input_type(css):default('color:black; background-color:#F5F5F5'):arg_name(Arrow button style):arg_section(2.3, 1)}" hover_style="${args->btn_hover_style:html:input_type(css):default('color:white; background-color:#E5007F'):arg_name(Arrow button style: hover):arg_section(2.3, 2)}"><</a>
				<a id="button_forward" class="$flat_btn" style="${args->btn_style:html:input_type(css):default('color:black; background-color:#F5F5F5'):arg_name(Arrow button style):arg_section(2.3, 1)}" hover_style="${args->btn_hover_style:html:input_type(css):default('color:white; background-color:#E5007F'):arg_name(Arrow button style: hover):arg_section(2.3, 2)}">></a>
			</td>
			${block->x:default(1):arg_name(With close button):arg_section(2.5, 0.1)}
			<td style="width:1px; white-space:nowrap; ${args->x_style:html:input_type(css):default('padding:.3em'):arg_name(Close button position):arg_section(2.5, 2)}">
				${args->x:input_type(dontshowagain):input_props('style=cursor:pointer; vertical-align:middle'):arg_name(Close button):arg_section(2.5, 1, 'Close button', 'close'):default('<img src="https://counter.emarketer.com/images/close-buttons/round-transparent-black-2-16x16.png" style="cursor:pointer; vertical-align:middle" class="$emarketer_button_dont_show_again" data-action_id="${action_id}">')}
			</td>
		</tr>
	</table>
	<table style="width:100%; border-collapse:separate; border-spacing:12px 0; margin-bottom:1.2em">
		<tr class="$table_slider" data-disabled="${args->with_slider:html:input_type(checkbox):input_props('value_off=1', 'value_on='):default('1'):onchange('block.with_arrows=args.with_slider!=1'):arg_name(Use slider widget):arg_section(1.5, 1, 'With slider', 'arrow-right')}" style="border:none; max-width:${args->width:html:input_type(css_length):input_props('with_options=none'):default('none'):arg_name(Widget maximum width):arg_section(1, 1)}" for_max_vw="${args->for_max_vw:html:visible_if(args.with_slider!=1):input_type(css_length):input_props('with_options=always'):default('always'):arg_name(Slider widget only if screen width is less than or equal to):arg_section(1.5, 3)}" eq_cell_height="1" arrow_back_img="${args->arrow_back_img:html:visible_if(args.with_slider!=1):input_type(emarketer_media_url):default('//counter.emarketer.com/images/icon_square_arrow_left.png'):arg_name(Left arrow image):arg_section(1.5, 4)}" arrow_forward_img="${args->arrow_forward_img:html:visible_if(args.with_slider!=1):input_type(emarketer_media_url):default('//counter.emarketer.com/images/icon_square_arrow_right.png'):arg_name(Right arrow image):arg_section(1.5, 4)}" arrow_back_id="button_back" arrow_forward_id="button_forward">
			${foreach ar as p}
				<td style="padding:0; text-align:center; background-color:white; border:solid ${args->border_color:html:default('#20b298'):input_type(color):arg_name(Border color):arg_section(1, 7)} 1px">
					<a href="${p->content_url:html:arg_name(Link target URL):arg_section(4.1, 2, 'Link target URL', 'link'):column_tags('url', 'custom text')}" target="_blank" data-style="display:block; width:${args->img_width:html:default('sel(250px, 26vw)'):input_type(css_length):input_props('with_responsive=1'):arg_name(Cell width):arg_section(1, 6)}">
						<div data-style="background-image:url('${p->image_small_url:html:arg_name(Item image):arg_section(3, 1, 'Image', 'image'):column_tags('image')}'); background-repeat:no-repeat; background-position:center; background-size:100% 100%; transition: background-size 0.7s ease; width:100%" data-z='${args->zoom:html:input_type('number'):arg_name('Image zoom on hover, %'):arg_section(3, 4):default(120)}' onmouseover="var z=this.getAttribute('data-z'); this.style.backgroundSize=z+'% '+z+'%'" onmouseout="this.style.backgroundSize='100% 100%'">
							<img src="${p->image_small_url:html:arg_name(Item image):arg_section(3, 1, 'Image', 'image'):column_tags('image')}" data-style="visibility:hidden; width:auto; height:auto; max-width:100%; max-height:${args->img_max_height:html:default('sel(300px, 30vw)'):input_type(css_length):input_props('with_responsive=1'):arg_name(Image maximum height):arg_section(1, 7)}">
						</div>
					</a>
					<div data-style="width:${args->img_width:html:default('sel(250px, 26vw)'):input_type(css_length):input_props('with_responsive=1'):arg_name(Cell width):arg_section(1, 6)}">
						<div data-style="display:inline-block; ${args->a_css:html:default('font-size:sel(16px, 5vw); padding:0.6em 0; text-transform:uppercase; color:rgb(51, 51, 51))'):input_type(css):input_props('with_responsive=1'):arg_name(Text color):arg_section(4, 2)}">
							${p->title:arg_name(Item text):arg_section(4, 1, 'Text', 'align-justify')}
						</div>
					</div>
					<div style="font-size:1px">
						<div data-style="display:inline-block; background-color:${args->border_color:html:default('#20b298'):input_type(color):arg_name(Border color):arg_section(1, 7)}; ${args->a_css_2:html:default('width:100px; height:3px; max-width:80%'):input_type(css):input_props('with_responsive=1'):arg_name(Ruler):arg_section(4, 3)}"></div>
					</div>
					<div data-style="width:${args->img_width:html:default('sel(250px, 26vw)'):input_type(css_length):input_props('with_responsive=1'):arg_name(Cell width):arg_section(1, 6)}">
						<div data-style="display:inline-block; ${args->a_css_3:html:default('font-size:sel(16px, 5vw); padding:0.6em 0; color:#777; font-style:italic; letter-spacing:1px; line-height:1.3'):input_type(css):input_props('with_responsive=1'):arg_name(Text color):arg_section(4, 2)}; padding-bottom:0">
							${p->description:arg_name(Item text):arg_section(4, 1, 'Text', 'align-justify')}
						</div>
					</div>
					<a href="${p->content_url:html:arg_name(Link target URL):arg_section(4.1, 2, 'Link target URL', 'link'):column_tags('url', 'custom text')}" target="_blank" data-style="display:inline-block; position:relative; top:1.3em; text-decoration:none; transition: font-size 0.3s ease; background-color:${args->border_color:html:default('#20b298'):input_type(color):arg_name(Border color):arg_section(1, 7)}; ${args->a_css_4:html:default('padding:0.2em; color:white; font-size:sel(16px, 4vw)'):input_type(css):input_props('with_responsive=1'):arg_name(Button style):arg_section(5, 2)}" onmouseenter="var t=this; s=t.style, f=s.fontSize, p=f.match(/^([\d\.]+)(\w+)$/); if (!t._b) t._b=[s.backgroundColor, s.color, f]; s.backgroundColor=t._b[1]; s.color=t._b[0]; if (p) if (!t._p) {s.fontSize=(p[1]*0.9)+p[2]; t._p=1; setTimeout(function() {s.fontSize=t._b[2]; t._p=0;}, 300)}" onmouseleave="var s=this.style, b=this._b; s.backgroundColor=b[0]; s.color=b[1]">
						<div data-style="border:solid 1px; ${args->a_css_5:html:default('padding-left:sel(1.8em, 2vw); padding-right:sel(1.8em, 2vw); padding-top:sel(0.4em, 1vw); padding-bottom:sel(0.4em, 1vw)'):input_type(css):input_props('with_responsive=1'):arg_name(Button style):arg_section(5, 3)}">
							${args->button_text:arg_name(Button text):arg_section(5, 1, 'Button', 'hand-pointer-o'):default(ACCESS)}
						</div>
					</a>
				</td>
			${end}
		</tr>
	</table>
</div>
```


## Content recommendation: Default vertical



```
<div style="${args->style:html:default('border:none'):input_type(css):arg_name(Style):arg_section(0, 0, 'Frame', 'th-large')}">
	${block->title:default(0):arg_name(With title bar):arg_section(1, 0, 'Title', 'bookmark')}
	<div style="${args->title_style:html:default('color:black; background-color:#E6E6E6; font-weight:bold; text-align:center; padding:0.2em'):input_type(css):arg_name(Style):arg_section(1, 2, 'Title', 'bookmark')}">
		${block->x:default(1):arg_name(With close button):arg_section(2, 0, 'Close button', 'close')}
		<div style="float:right; cursor:pointer; margin:0 0 .3em .3em">
			${args->x:default('<img src="https://counter.emarketer.com/images/close-buttons/round-transparent-black-2-16x16.png" style="width:16px" class="$emarketer_button_dont_show_again" data-action_id="${action_id}">'):input_type(dontshowagain):arg_name(Close button):arg_section(2, 1, 'Close button', 'close')}
		</div>
		${args->title:default(Articles selection):arg_name(Text):arg_section(1, 1, 'Title', 'bookmark')}
		<div style="clear:both"></div>
	</div>
	<table style="border-collapse:separate; border-spacing:2px">
		${foreach sum_articles_week as p order by p->n_viewed desc limit 5}
			<tr>
				<td style="vertical-align:middle">
					<a href="${p->content_url:html:arg_name(Link target URL):arg_section(4, 0, 'Link target URL', 'link'):column_tags('url','custom text')}" target="_blank">
						<img src="${p->image_big_url:html:arg_name(Item image):arg_section(3, 0, 'Image', 'image'):column_tags(image)}" style="display:block; ${args->img_css:html:default('width:auto; height:auto; max-width:70px; max-height:70px; border:double white 5px'):input_type(css):arg_name(Image properties):arg_section(3, 1, 'Image', 'image')}">
					</a>
				</td>
				<td style="vertical-align:middle">
					<a href="${p->content_url:html:arg_name(Link target URL):arg_section(4, 0, 'Link target URL', 'link'):column_tags('url','custom text')}" target="_blank">
						${p->title:arg_name(Item text):arg_section(3, 2, 'Image', 'image')}
					</a>
				</td>
			</tr>
		${end}
	</table>
</div>
```


## Content recommendation: with background, vertical



```
<div style="${args->style:html:default('border:none'):input_type(css):arg_name(Style):arg_section(0, 0, 'Frame', 'th-large')}">
	${block->title:default(0):arg_name(With title bar):arg_section(1, 0, 'Title', 'bookmark')}
	<div style="${args->title_style:html:default('color:black; background-color:#E6E6E6; font-weight:bold; text-align:center; padding:0.2em'):input_type(css):arg_name(Style):arg_section(1, 2, 'Title', 'bookmark')}">
		${block->x:default(1):arg_name(With close button):arg_section(2, 0, 'Close button', 'close')}
		<div style="float:right; cursor:pointer; margin:0 0 .3em .3em">
			${args->x:default('<img src="https://counter.emarketer.com/images/close-buttons/round-transparent-black-2-16x16.png" style="width:16px" class="$emarketer_button_dont_show_again" data-action_id="${action_id}">'):input_type(dontshowagain):arg_name(Close button):arg_section(2, 1, 'Close button', 'close')}
		</div>
		${args->title:default(Articles selection):arg_name(Text):arg_section(1, 1, 'Title', 'bookmark')}
		<div style="clear:both"></div>
	</div>
	<table style="border-collapse:separate; border-spacing:5px">
		${foreach ar as p}
			<tr>
				<td style="vertical-align:middle; padding:0">
					<a href="${p->content_url:html:arg_name(Link target URL):arg_section(5, 0, 'Link target URL', 'link'):column_tags('url','custom text')}" target="_blank">
						<img src="${p->image_big_url:html:arg_name(Item image):arg_section(3, 0, 'Image', 'image'):column_tags(image)}" style="display:block; ${args->width_1:html:default('width:auto; height:auto; max-width:70px; max-height:70px; border:none'):input_type(css):arg_name(Item image style):arg_section(3, 1, 'Image', 'image')}">
					</a>
				</td>
				<td style="vertical-align:middle; padding:0 0 0 8px">
					<table style="width:100%; height:${args->height_1:html:default(70px):input_type(css_length):input_props('with_options=auto')}; ${args->td_css:html:default('background-color:silver'):input_type(css):arg_name(Text background):arg_section(4, 2, 'Text', 'align-justify')}">
						<tr>
							<td style="vertical-align:middle; padding:4px">
								<a href="${p->content_url:html:arg_name(Link target URL):arg_section(5, 0, 'Link target URL', 'link'):column_tags('url','custom text')}" target="_blank" style="${args->a_css:html:default('color:#6587AB'):input_type(css):arg_name(Text color):arg_section(4, 1, 'Text', 'align-justify')}">
									${p->title:arg_name(Item text):arg_section(4, 0, 'Text', 'align-justify')}
								</a>
							</td>
						</tr>
					</table>
				</td>
			</tr>
		${end}
	</table>
</div>
```


## Zoom in



```
<div class="$responsive" data-style="display:inline-block; ${args->style:html:default('border: none;
background-color: rgba(0, 0, 0, 0);'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(0, 1, 'Frame', 'th-large')}">
	${block->title:default(0):arg_name(With title bar):arg_section(2, 0, 'Title', 'bookmark')}
	<table data-style="width:100%; border-collapse:collapse; border:none; ${args->title_bg:html:input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(2, 2, 'Title', 'bookmark')}">
		<tr>
			<td data-style="vertical-align:middle; ${args->title_style:html:input_type(css):input_props('with_responsive=1'):arg_name(Title style):arg_section(2, 3, 'Title', 'bookmark')}">
				${args->title:arg_name(Text):arg_section(2, 1, 'Title', 'bookmark')}
			</td>
			${block->with_arrows:arg_name(With arrow buttons):arg_section(3, 0, 'With slider arrows', 'arrows-h')}
			<td style="width:1px; white-space:nowrap; vertical-align:middle">
				<a id="button_back" class="$flat_btn" style="${args->btn_style:html:input_type(css):arg_name(Arrow button style):arg_section(3, 1, 'With slider arrows', 'arrows-h')}" hover_style="${args->btn_hover_style:html:input_type(css):arg_name('Arrow button style: hover'):arg_section(3, 2, 'With slider arrows', 'arrows-h')}"><</a>
				<a id="button_forward" class="$flat_btn" style="${args->btn_style:html:input_type(css):arg_name(Arrow button style):arg_section(3, 1, 'With slider arrows', 'arrows-h')}" hover_style="${args->btn_hover_style:html:input_type(css):arg_name('Arrow button style: hover'):arg_section(3, 2, 'With slider arrows', 'arrows-h')}">></a>
			</td>
			${block->x:arg_name(With close button):arg_section(4, 0, 'Close button', 'close')}
			<td style="width:1px; white-space:nowrap; ${args->x_style:html:input_type(css):arg_name(Close button position):arg_section(4, 2, 'Close button', 'close')}">
				${args->x:input_type(dontshowagain):input_props('style=cursor:pointer; vertical-align:middle'):arg_name(Close button):arg_section(4, 1, 'Close button', 'close')}
			</td>
		</tr>
	</table>
	<table style="width:100%; border-collapse:separate; border-spacing:12px 0; margin-bottom:1.2em">
		<tr class="$table_slider" data-disabled="${args->with_slider:html:default(1):input_type(checkbox):input_props('value_off=1','value_on='):arg_name(Use slider widget):arg_section(1, 0, 'With slider', 'arrow-right'):onchange('block.with_arrows=args.with_slider!=1')}" style="border:none; max-width:${args->width:html:default(none):input_type(css_length):input_props('with_options=none'):arg_name(Widget maximum width):arg_section(0, 0, 'Frame', 'th-large')}" for_max_vw="${args->for_max_vw:html:input_type(css_length):input_props('with_options=always'):arg_name(Slider widget only if screen width is less than or equal to):arg_section(1, 1, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" eq_cell_height="1" arrow_back_img="${args->arrow_back_img:html:input_type(emarketer_media_url):arg_name(Left arrow image):arg_section(1, 2, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" arrow_forward_img="${args->arrow_forward_img:html:input_type(emarketer_media_url):arg_name(Right arrow image):arg_section(1, 3, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" arrow_back_id="button_back" arrow_forward_id="button_forward">
			${foreach sum_interested_articles_week as p order by p->n_viewed desc limit 5}
				<td style="padding:0; text-align:center; background-color:white; border:solid ${args->border_color:html:default(red):input_type(color):arg_name(Border color):arg_section(0, 3, 'Frame', 'th-large')} 1px">
					<a href="${p->content_url:html:arg_name(Link target URL):arg_section(7, 0, 'Link target URL', 'link'):column_tags('url','custom text')}" target="_blank" data-style="display:block; width:${args->img_width:html:default('sel(250px, 26vw)'):input_type(css_length):input_props('with_responsive=1'):arg_name(Cell width):arg_section(0, 2, 'Frame', 'th-large')}">
						<div data-style="background-image:url('${p->image_big_url:html:arg_name(Item image):arg_section(5, 0, 'Image', 'image'):column_tags(image)}'); background-repeat:no-repeat; background-position:center; background-size:100% 100%; transition: background-size 0.7s ease; width:100%" data-z='${args->zoom:html:default(120):input_type(number):arg_name('Image zoom on hover, %'):arg_section(5, 1, 'Image', 'image')}' onmouseover="var z=this.getAttribute('data-z'); this.style.backgroundSize=z+'% '+z+'%'" onmouseout="this.style.backgroundSize='100% 100%'">
							<img src="${p->image_big_url:html:arg_name(Item image):arg_section(5, 0, 'Image', 'image'):column_tags(image)}" data-style="visibility:hidden; width:auto; height:auto; max-width:100%; max-height:${args->img_max_height:html:default('sel(300px, 30vw)'):input_type(css_length):input_props('with_responsive=1'):arg_name(Image maximum height):arg_section(0, 4, 'Frame', 'th-large')}">
						</div>
					</a>
					<div data-style="width:${args->img_width:html:default('sel(250px, 26vw)'):input_type(css_length):input_props('with_responsive=1'):arg_name(Cell width):arg_section(0, 2, 'Frame', 'th-large')}">
						<div data-style="display:inline-block; ${args->a_css:html:default('font-size: sel(16px, 5vw);
padding-top: 0.6em;
padding-right: 0;
padding-bottom: 0.6em;
padding-left: 0;
text-transform: capitalize;
color: rgba(0, 0, 0, 1);'):input_type(css):input_props('with_responsive=1'):arg_name(Text color):arg_section(6, 2, 'Text', 'align-justify')}">
							${p->title:arg_name(Item text):arg_section(6, 0, 'Text', 'align-justify')}
						</div>
					</div>
					<div style="font-size:1px">
						<div data-style="display:inline-block; background-color:${args->border_color:html:default(red):input_type(color):arg_name(Border color):arg_section(0, 3, 'Frame', 'th-large')}; ${args->a_css_2:html:default('width:100px; height:3px; max-width:80%'):input_type(css):input_props('with_responsive=1'):arg_name(Ruler):arg_section(6, 4, 'Text', 'align-justify')}"></div>
					</div>
					<div data-style="width:${args->img_width:html:default('sel(250px, 26vw)'):input_type(css_length):input_props('with_responsive=1'):arg_name(Cell width):arg_section(0, 2, 'Frame', 'th-large')}">
						<div data-style="display:inline-block; ${args->a_css_3:html:default('font-size:sel(16px, 5vw); padding:0.6em 0; color:#777; font-style:italic; letter-spacing:1px; line-height:1.3'):input_type(css):input_props('with_responsive=1'):arg_name(Text color):arg_section(6, 3, 'Text', 'align-justify')}; padding-bottom:0">
							${p->description:arg_name(Item text):arg_section(6, 1, 'Text', 'align-justify')}
						</div>
					</div>
					<a href="${p->content_url:html:arg_name(Link target URL):arg_section(7, 0, 'Link target URL', 'link'):column_tags('url','custom text')}" target="_blank" data-style="display:inline-block; position:relative; top:1.3em; text-decoration:none; transition: font-size 0.3s ease; background-color:${args->border_color:html:default(red):input_type(color):arg_name(Border color):arg_section(0, 3, 'Frame', 'th-large')}; ${args->a_css_4:html:default('padding:0.2em; color:white; font-size:sel(16px, 4vw)'):input_type(css):input_props('with_responsive=1'):arg_name(Button style):arg_section(8, 1, 'Button', 'hand-pointer-o')}" onmouseenter="var t=this; s=t.style, f=s.fontSize, p=f.match(/^([\d\.]+)(\w+)$/); if (!t._b) t._b=[s.backgroundColor, s.color, f]; s.backgroundColor=t._b[1]; s.color=t._b[0]; if (p) if (!t._p) {s.fontSize=(p[1]*0.9)+p[2]; t._p=1; setTimeout(function() {s.fontSize=t._b[2]; t._p=0;}, 300)}" onmouseleave="var s=this.style, b=this._b; s.backgroundColor=b[0]; s.color=b[1]">
						<div data-style="border:solid 1px; ${args->a_css_5:html:default('padding-left:sel(1.8em, 2vw); padding-right:sel(1.8em, 2vw); padding-top:sel(0.4em, 1vw); padding-bottom:sel(0.4em, 1vw)'):input_type(css):input_props('with_responsive=1'):arg_name(Button style):arg_section(8, 2, 'Button', 'hand-pointer-o')}">
							${args->button_text:default(ACCESS):arg_name(Button text):arg_section(8, 0, 'Button', 'hand-pointer-o')}
						</div>
					</a>
				</td>
			${end}
		</tr>
	</table>
</div>
```


## Zoom in



```
<div class="$responsive" data-style="display:inline-block; ${args->style:html:default('border: none;
background-color: rgba(0, 0, 0, 0);'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(0, 1, 'Frame', 'th-large')}">
	${block->title:default(1):arg_name(With title bar):arg_section(2, 0, 'Title', 'bookmark')}
	<table data-style="width:100%; border-collapse:collapse; border:none; ${args->title_bg:html:default('border-top-width: 0px;
border-right-width: 0px;
border-bottom-width: 3px;
border-left-width: 0px;
border-color: rgb(6, 3, 3);
border-style: solid;
margin-top: 5px;
margin-right: 5px;
margin-bottom: 10px;
margin-left: 5px;
padding: 5px;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(2, 2, 'Title', 'bookmark')}">
		<tr>
			<td data-style="vertical-align:middle; ${args->title_style:html:default('font-size: 20px;
line-height: 23px;
font-style: italic;
font-weight: 800;
text-transform: uppercase;
font-family: futura-pt,sans-serif;
color: #2a2a2a;'):input_type(css):input_props('with_responsive=1'):arg_name(Title style):arg_section(2, 3, 'Title', 'bookmark')}">
				${args->title:default(Recommended To You):arg_name(Text):arg_section(2, 1, 'Title', 'bookmark')}
			</td>
			${block->with_arrows:arg_name(With arrow buttons):arg_section(3, 0, 'With slider arrows', 'arrows-h')}
			<td style="width:1px; white-space:nowrap; vertical-align:middle">
				<a id="button_back" class="$flat_btn" style="${args->btn_style:html:input_type(css):arg_name(Arrow button style):arg_section(3, 1, 'With slider arrows', 'arrows-h')}" hover_style="${args->btn_hover_style:html:input_type(css):arg_name('Arrow button style: hover'):arg_section(3, 2, 'With slider arrows', 'arrows-h')}"><</a>
				<a id="button_forward" class="$flat_btn" style="${args->btn_style:html:input_type(css):arg_name(Arrow button style):arg_section(3, 1, 'With slider arrows', 'arrows-h')}" hover_style="${args->btn_hover_style:html:input_type(css):arg_name('Arrow button style: hover'):arg_section(3, 2, 'With slider arrows', 'arrows-h')}">></a>
			</td>
			${block->x:arg_name(With close button):arg_section(4, 0, 'Close button', 'close')}
			<td style="width:1px; white-space:nowrap; ${args->x_style:html:input_type(css):arg_name(Close button position):arg_section(4, 2, 'Close button', 'close')}">
				${args->x:input_type(dontshowagain):input_props('style=cursor:pointer; vertical-align:middle'):arg_name(Close button):arg_section(4, 1, 'Close button', 'close')}
			</td>
		</tr>
	</table>
	<table style="width:100%; border-collapse:separate; border-spacing:12px 0; margin-bottom:1.2em">
		<tr class="$table_slider" data-disabled="${args->with_slider:html:default(1):input_type(checkbox):input_props('value_off=1','value_on='):arg_name(Use slider widget):arg_section(1, 0, 'With slider', 'arrow-right'):onchange('block.with_arrows=args.with_slider!=1')}" style="border:none; max-width:${args->width:html:default(none):input_type(css_length):input_props('with_options=none'):arg_name(Widget maximum width):arg_section(0, 0, 'Frame', 'th-large')}" for_max_vw="${args->for_max_vw:html:input_type(css_length):input_props('with_options=always'):arg_name(Slider widget only if screen width is less than or equal to):arg_section(1, 1, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" eq_cell_height="1" arrow_back_img="${args->arrow_back_img:html:input_type(emarketer_media_url):arg_name(Left arrow image):arg_section(1, 2, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" arrow_forward_img="${args->arrow_forward_img:html:input_type(emarketer_media_url):arg_name(Right arrow image):arg_section(1, 3, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" arrow_back_id="button_back" arrow_forward_id="button_forward">
			${foreach sum_interested_articles_week as p order by p->n_viewed desc limit 5}
				<td style="padding:0; text-align:center; background-color:white; border:solid ${args->border_color:html:default('rgba(0, 0, 0, 1)'):input_type(color):arg_name(Border color):arg_section(0, 3, 'Frame', 'th-large')} 1px">
					<a href="${p->content_url:html:arg_name(Link target URL):arg_section(7, 0, 'Link target URL', 'link'):column_tags('url','custom text')}" target="_blank" data-style="display:block; width:${args->img_width:html:default('sel(250px, 26vw)'):input_type(css_length):input_props('with_responsive=1'):arg_name(Cell width):arg_section(0, 2, 'Frame', 'th-large')}">
						<div data-style="background-image:url('${p->image_big_url:html:arg_name(Item image):arg_section(5, 0, 'Image', 'image'):column_tags(image)}'); background-repeat:no-repeat; background-position:center; background-size:100% 100%; transition: background-size 0.7s ease; width:100%" data-z='${args->zoom:html:default(120):input_type(number):arg_name('Image zoom on hover, %'):arg_section(5, 1, 'Image', 'image')}' onmouseover="var z=this.getAttribute('data-z'); this.style.backgroundSize=z+'% '+z+'%'" onmouseout="this.style.backgroundSize='100% 100%'">
							<img src="${p->image_big_url:html:arg_name(Item image):arg_section(5, 0, 'Image', 'image'):column_tags(image)}" data-style="visibility:hidden; width:auto; height:auto; max-width:100%; max-height:${args->img_max_height:html:default('sel(300px, 30vw)'):input_type(css_length):input_props('with_responsive=1'):arg_name(Image maximum height):arg_section(0, 4, 'Frame', 'th-large')}">
						</div>
					</a>
					<div data-style="width:${args->img_width:html:default('sel(250px, 26vw)'):input_type(css_length):input_props('with_responsive=1'):arg_name(Cell width):arg_section(0, 2, 'Frame', 'th-large')}">
						<div data-style="display:inline-block; ${args->a_css:html:default('font-size: sel(16px, 5vw);
padding-top: 0.6em;
padding-right: 0;
padding-bottom: 0.6em;
padding-left: 0;
text-transform: capitalize;
color: rgba(0, 0, 0, 1);'):input_type(css):input_props('with_responsive=1'):arg_name(Text color):arg_section(6, 2, 'Text', 'align-justify')}">
							${p->title:arg_name(Item text):arg_section(6, 0, 'Text', 'align-justify')}
						</div>
					</div>
					<div style="font-size:1px">
						<div data-style="display:inline-block; background-color:${args->border_color:html:default('rgba(0, 0, 0, 1)'):input_type(color):arg_name(Border color):arg_section(0, 3, 'Frame', 'th-large')}; ${args->a_css_2:html:default('width: 100px;
height: 3px;
max-width: 0%;'):input_type(css):input_props('with_responsive=1'):arg_name(Ruler):arg_section(6, 4, 'Text', 'align-justify')}"></div>
					</div>
					<div data-style="width:${args->img_width:html:default('sel(250px, 26vw)'):input_type(css_length):input_props('with_responsive=1'):arg_name(Cell width):arg_section(0, 2, 'Frame', 'th-large')}">
						<div data-style="display:inline-block; ${args->a_css_3:html:default('font-size:sel(16px, 5vw); padding:0.6em 0; color:#777; font-style:italic; letter-spacing:1px; line-height:1.3'):input_type(css):input_props('with_responsive=1'):arg_name(Text color):arg_section(6, 3, 'Text', 'align-justify')}; padding-bottom:0">
							${p->description:arg_name(Item text):arg_section(6, 1, 'Text', 'align-justify')}
						</div>
					</div>
					<a href="${p->content_url:html:arg_name(Link target URL):arg_section(7, 0, 'Link target URL', 'link'):column_tags('url','custom text')}" target="_blank" data-style="display:inline-block; position:relative; top:1.3em; text-decoration:none; transition: font-size 0.3s ease; background-color:${args->border_color:html:default('rgba(0, 0, 0, 1)'):input_type(color):arg_name(Border color):arg_section(0, 3, 'Frame', 'th-large')}; ${args->a_css_4:html:default('padding: 0em;
color: white;
font-size: sel(16px, 4vw);'):input_type(css):input_props('with_responsive=1'):arg_name(Button style):arg_section(8, 1, 'Button', 'hand-pointer-o')}" onmouseenter="var t=this; s=t.style, f=s.fontSize, p=f.match(/^([\d\.]+)(\w+)$/); if (!t._b) t._b=[s.backgroundColor, s.color, f]; s.backgroundColor=t._b[1]; s.color=t._b[0]; if (p) if (!t._p) {s.fontSize=(p[1]*0.9)+p[2]; t._p=1; setTimeout(function() {s.fontSize=t._b[2]; t._p=0;}, 300)}" onmouseleave="var s=this.style, b=this._b; s.backgroundColor=b[0]; s.color=b[1]">
						<div data-style="border:solid 1px; ${args->a_css_5:html:default():input_type(css):input_props('with_responsive=1'):arg_name(Button style):arg_section(8, 2, 'Button', 'hand-pointer-o')}">
							${args->button_text:default():arg_name(Button text):arg_section(8, 0, 'Button', 'hand-pointer-o')}
						</div>
					</a>
				</td>
			${end}
		</tr>
	</table>
</div>
```


## Boxes



```
<div class="$responsive" data-style="display:inline-block; ${args->style:html:default('border: none;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(0, 1, 'Frame', 'th-large')}">
	${block->title:default(0):arg_name(With title bar):arg_section(2, 0, 'Title', 'bookmark')}
	<table data-style="width:100%; border-collapse:collapse; border:none; ${args->title_bg:html:input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(2, 2, 'Title', 'bookmark')}">
		<tr>
			<td data-style="vertical-align:middle; ${args->title_style:html:input_type(css):input_props('with_responsive=1'):arg_name(Title style):arg_section(2, 3, 'Title', 'bookmark')}">
				${args->title:arg_name(Text):arg_section(2, 1, 'Title', 'bookmark')}
			</td>
			${block->with_arrows:arg_name(With arrow buttons):arg_section(3, 0, 'With slider arrows', 'arrows-h')}
			<td style="width:1px; white-space:nowrap; vertical-align:middle">
				<a id="button_back" class="$flat_btn" style="${args->btn_style:html:input_type(css):arg_name(Arrow button style):arg_section(3, 1, 'With slider arrows', 'arrows-h')}" hover_style="${args->btn_hover_style:html:input_type(css):arg_name('Arrow button style: hover'):arg_section(3, 2, 'With slider arrows', 'arrows-h')}">&lt;</a>
				<a id="button_forward" class="$flat_btn" style="${args->btn_style:html:input_type(css):arg_name(Arrow button style):arg_section(3, 1, 'With slider arrows', 'arrows-h')}" hover_style="${args->btn_hover_style:html:input_type(css):arg_name('Arrow button style: hover'):arg_section(3, 2, 'With slider arrows', 'arrows-h')}">&gt;</a>
			</td>
			${block->x:arg_name(With close button):arg_section(4, 0, 'Close button', 'close')}
			<td style="width:1px; white-space:nowrap; ${args->x_style:html:input_type(css):arg_name(Close button position):arg_section(4, 2, 'Close button', 'close')}">
				${args->x:input_type(dontshowagain):input_props('style=cursor:pointer; vertical-align:middle'):arg_name(Close button):arg_section(4, 1, 'Close button', 'close')}
			</td>
		</tr>
	</table>
	<table style="width:100%; border-collapse:separate; border-spacing:12px">
		<tr class="$table_slider" data-disabled="${args->with_slider:html:default():input_type(checkbox):input_props('value_off=1','value_on='):arg_name(Use slider widget):arg_section(1, 0, 'With slider', 'arrow-right'):onchange('block.with_arrows=args.with_slider!=1')}" style="border:none; max-width:${args->width:html:default(600px):input_type(css_length):input_props('with_options=none'):arg_name(Widget maximum width):arg_section(0, 0, 'Frame', 'th-large')}" for_max_vw="${args->for_max_vw:html:default(0px):input_type(css_length):input_props('with_options=always'):arg_name(Slider widget only if screen width is less than or equal to):arg_section(1, 1, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" eq_cell_width="${args->eq_cell_width:html:default(1):input_type(checkbox):input_props('value_off=','value_on=1'):arg_name(Equal cell width):arg_section(0, 2, 'Frame', 'th-large')}" eq_cell_height="${args->eq_cell_height:html:default(1):input_type(checkbox):input_props('value_off=','value_on=1'):arg_name(Equal rows height):arg_section(0, 3, 'Frame', 'th-large')}" arrow_back_img="${args->arrow_back_img:html:default():input_type(emarketer_media_url):arg_name(Left arrow image):arg_section(1, 2, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" arrow_forward_img="${args->arrow_forward_img:html:default():input_type(emarketer_media_url):arg_name(Right arrow image):arg_section(1, 3, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" arrow_back_id="button_back" arrow_forward_id="button_forward">
			${foreach interested_articles as p order by p->time_created desc limit 5}
				<td data-style="padding:0; text-align:center; background-color:white; ${args->td_css:html:default('vertical-align: middle;
box-shadow: 4px 4px 1px 0px #8C8C8C;
max-width: 230px;
min-width: 120px;'):input_type(css):input_props('with_responsive=1'):arg_name(Cell style):arg_section(0, 4, 'Frame', 'th-large')}">
					<a href="${p->content_url:html:arg_name(Link target URL):arg_section(7, 0, 'Link target URL', 'link'):column_tags('url','custom text')}" target="_blank">
						<div data-style="${args->div_css:html:default('background-color: rgb(87, 74, 100);
padding: 4px;'):input_type(css):input_props('with_responsive=1'):arg_name(Image background):arg_section(5, 2, 'Image', 'image')}">
							<img src="${p->image_big_url:html:arg_name(Item image):arg_section(5, 0, 'Image', 'image'):column_tags(image)}" data-style="${args->img_css:html:default('width: sel(120px, auto);
height: sel(120px, auto);
border-radius: 50%;'):input_type(css):input_props('with_responsive=1'):arg_name(Image properties):arg_section(5, 1, 'Image', 'image')}">
						</div>
					</a>
					<a href="${p->content_url:html:arg_name(Link target URL):arg_section(7, 0, 'Link target URL', 'link'):column_tags('url','custom text')}" target="_blank">
						<div data-style="display:inline-block; text-align:left; text-align:start; ${args->a_css:html:default('color:#6587AB; font-size:sel(16px, 5vw); padding:5px'):input_type(css):input_props('with_responsive=1'):arg_name(Text color):arg_section(6, 1, 'Text', 'align-justify')}">
							${p->title:arg_name(Item text):arg_section(6, 0, 'Text', 'align-justify')}
						</div>
					</a>
				</td>
			${end}
		</tr>
	</table>
</div>
```


## With title bar



```
<div class="$responsive" data-style="display:inline-block; ${args->style:html:default('border: none;
background-color: rgb(248, 248, 248);
width: 100%;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(0, 1, 'Frame', 'th-large')}">
	${block->title:default(1):arg_name(With title bar):arg_section(2, 0, 'Title', 'bookmark')}
	<table data-style="width:100%; border-collapse:collapse; border:none; ${args->title_bg:html:default('text-align: center;
font-weight: 400;
font-size: 20px;
padding: 3px;
background-color: rgb(28, 211, 38);
max-width: 350px;
border-radius: 15px;
margin-top: 35px;
margin-right: auto;
margin-bottom: 35px;
margin-left: auto;
color: white;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(2, 2, 'Title', 'bookmark')}">
		<tr>
			<td data-style="vertical-align:middle; ${args->title_style:html:default('padding: 4px;'):input_type(css):input_props('with_responsive=1'):arg_name(Title style):arg_section(2, 3, 'Title', 'bookmark')}">
				${args->title:default(Recommended For you):arg_name(Text):arg_section(2, 1, 'Title', 'bookmark')}
			</td>
			${block->with_arrows:default(0):arg_name(With arrow buttons):arg_section(3, 0, 'With slider arrows', 'arrows-h')}
			<td style="width:1px; white-space:nowrap; vertical-align:middle">
				<a id="button_back" class="$flat_btn" style="${args->btn_style:html:input_type(css):arg_name(Arrow button style):arg_section(3, 1, 'With slider arrows', 'arrows-h')}" hover_style="${args->btn_hover_style:html:input_type(css):arg_name('Arrow button style: hover'):arg_section(3, 2, 'With slider arrows', 'arrows-h')}"><</a>
				<a id="button_forward" class="$flat_btn" style="${args->btn_style:html:input_type(css):arg_name(Arrow button style):arg_section(3, 1, 'With slider arrows', 'arrows-h')}" hover_style="${args->btn_hover_style:html:input_type(css):arg_name('Arrow button style: hover'):arg_section(3, 2, 'With slider arrows', 'arrows-h')}">></a>
			</td>
			${block->x:default(0):arg_name(With close button):arg_section(4, 0, 'Close button', 'close')}
			<td style="width:1px; white-space:nowrap; ${args->x_style:html:input_type(css):arg_name(Close button position):arg_section(4, 2, 'Close button', 'close')}">
				${args->x:input_type(dontshowagain):input_props('style=cursor:pointer; vertical-align:middle'):arg_name(Close button):arg_section(4, 1, 'Close button', 'close')}
			</td>
		</tr>
	</table>
	<table style="width:100%; border-collapse:separate; border-spacing:12px 0; margin-bottom:1.2em">
		<tr class="$table_slider" data-disabled="${args->with_slider:html:default(1):input_type(checkbox):input_props('value_off=1','value_on='):arg_name(Use slider widget):arg_section(1, 0, 'With slider', 'arrow-right'):onchange('block.with_arrows=args.with_slider!=1')}" style="border:none; max-width:${args->width:html:default(none):input_type(css_length):input_props('with_options=none'):arg_name(Widget maximum width):arg_section(0, 0, 'Frame', 'th-large')}" for_max_vw="${args->for_max_vw:html:input_type(css_length):input_props('with_options=always'):arg_name(Slider widget only if screen width is less than or equal to):arg_section(1, 1, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" eq_cell_height="1" arrow_back_img="${args->arrow_back_img:html:input_type(emarketer_media_url):arg_name(Left arrow image):arg_section(1, 2, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" arrow_forward_img="${args->arrow_forward_img:html:input_type(emarketer_media_url):arg_name(Right arrow image):arg_section(1, 3, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" arrow_back_id="button_back" arrow_forward_id="button_forward">
			${foreach sum_interested_articles_week as p order by p->n_viewed desc limit 4}
				<td style="padding:0; text-align:center; background-color:white; border:solid ${args->border_color:html:default('rgb(241, 240, 240)'):input_type(color):arg_name(Border color):arg_section(0, 3, 'Frame', 'th-large')} 1px">
					<a href="${p->content_url:html:arg_name(Link target URL):arg_section(7, 0, 'Link target URL', 'link'):column_tags('url','custom text')}" target="_blank" data-style="display:block; width:${args->img_width:html:default('sel(250px, 26vw)'):input_type(css_length):input_props('with_responsive=1'):arg_name(Cell width):arg_section(0, 2, 'Frame', 'th-large')}">
						<div data-style="background-image:url('${p->image_big_url:html:arg_name(Item image):arg_section(5, 0, 'Image', 'image'):column_tags(image)}'); background-repeat:no-repeat; background-position:center; background-size:100% 100%; transition: background-size 0.7s ease; width:100%" data-z='${args->zoom:html:default(120):input_type(number):arg_name('Image zoom on hover, %'):arg_section(5, 1, 'Image', 'image')}' onmouseover="var z=this.getAttribute('data-z'); this.style.backgroundSize=z+'% '+z+'%'" onmouseout="this.style.backgroundSize='100% 100%'">
							<img src="${p->image_big_url:html:arg_name(Item image):arg_section(5, 0, 'Image', 'image'):column_tags(image)}" data-style="visibility:hidden; width:auto; height:auto; max-width:100%; max-height:${args->img_max_height:html:default('sel(300px, 30vw)'):input_type(css_length):input_props('with_responsive=1'):arg_name(Image maximum height):arg_section(0, 4, 'Frame', 'th-large')}">
						</div>
					</a>
					<div data-style="width:${args->img_width:html:default('sel(250px, 26vw)'):input_type(css_length):input_props('with_responsive=1'):arg_name(Cell width):arg_section(0, 2, 'Frame', 'th-large')}">
						<div data-style="display:inline-block; ${args->a_css:html:default('font-size: sel(14px, 5vw);
padding-top: 0.6em;
padding-right: 0;
padding-bottom: 0.6em;
padding-left: 0;
text-transform: uppercase;
color: rgb(93, 75, 75);'):input_type(css):input_props('with_responsive=1'):arg_name(Text color):arg_section(6, 2, 'Text', 'align-justify')}">
							${p->title:arg_name(Item text):arg_section(6, 0, 'Text', 'align-justify')}
						</div>
					</div>
					<div style="font-size:1px">
						<div data-style="display:inline-block; background-color:${args->border_color:html:default('rgb(241, 240, 240)'):input_type(color):arg_name(Border color):arg_section(0, 3, 'Frame', 'th-large')}; ${args->a_css_2:html:default('width: 100px;
height: 3px;
max-width: 0%;'):input_type(css):input_props('with_responsive=1'):arg_name(Ruler):arg_section(6, 4, 'Text', 'align-justify')}"></div>
					</div>
					<div data-style="width:${args->img_width:html:default('sel(250px, 26vw)'):input_type(css_length):input_props('with_responsive=1'):arg_name(Cell width):arg_section(0, 2, 'Frame', 'th-large')}">
						<div data-style="display:inline-block; ${args->a_css_3:html:default('font-size:sel(16px, 5vw); padding:0.6em 0; color:#777; font-style:italic; letter-spacing:1px; line-height:1.3'):input_type(css):input_props('with_responsive=1'):arg_name(Text color):arg_section(6, 3, 'Text', 'align-justify')}; padding-bottom:0">
							${p->description:arg_name(Item text):arg_section(6, 1, 'Text', 'align-justify')}
						</div>
					</div>
					<a href="${p->content_url:html:arg_name(Link target URL):arg_section(7, 0, 'Link target URL', 'link'):column_tags('url','custom text')}" target="_blank" data-style="display:inline-block; position:relative; top:1.3em; text-decoration:none; transition: font-size 0.3s ease; background-color:${args->border_color:html:default('rgb(241, 240, 240)'):input_type(color):arg_name(Border color):arg_section(0, 3, 'Frame', 'th-large')}; ${args->a_css_4:html:default():input_type(css):input_props('with_responsive=1'):arg_name(Button style):arg_section(8, 0, 'Button', 'hand-pointer-o')}" onmouseenter="var t=this; s=t.style, f=s.fontSize, p=f.match(/^([\d\.]+)(\w+)$/); if (!t._b) t._b=[s.backgroundColor, s.color, f]; s.backgroundColor=t._b[1]; s.color=t._b[0]; if (p) if (!t._p) {s.fontSize=(p[1]*0.9)+p[2]; t._p=1; setTimeout(function() {s.fontSize=t._b[2]; t._p=0;}, 300)}" onmouseleave="var s=this.style, b=this._b; s.backgroundColor=b[0]; s.color=b[1]">

					</a>
				</td>
			${end}
		</tr>
	</table>
</div>
```


## Content widget



```
<div class="$responsive" data-style="display:inline-block; ${args->style:html:default('border: none;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(0, 1, 'Frame', 'th-large')}">
	${block->title:default(1):arg_name(With title bar):arg_section(2, 0, 'Title', 'bookmark')}
	<table data-style="width:100%; border-collapse:collapse; border:none; ${args->title_bg:html:input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(2, 2, 'Title', 'bookmark')}">
		<tr>
			<td data-style="vertical-align:middle; ${args->title_style:html:default('padding-top: 0px;
padding-right: 0px;
padding-bottom: 0px;
padding-left: 12px;
color: #4b4f59;
font-size: 14px;'):input_type(css):input_props('with_responsive=1'):arg_name(Title style):arg_section(2, 3, 'Title', 'bookmark')}">
				${args->title:default('<span style="font-size:18px;">YOU MAY ALSO LIKE</span>'):arg_name(Text):arg_section(2, 1, 'Title', 'bookmark')}
			</td>
			${block->with_arrows:default(true):arg_name(With arrow buttons):arg_section(3, 0, 'With slider arrows', 'arrows-h')}
			<td style="width:1px; white-space:nowrap; vertical-align:middle">
				<a id="button_back" class="$flat_btn" style="${args->btn_style:html:input_type(css):arg_name(Arrow button style):arg_section(3, 1, 'With slider arrows', 'arrows-h')}" hover_style="${args->btn_hover_style:html:input_type(css):arg_name('Arrow button style: hover'):arg_section(3, 2, 'With slider arrows', 'arrows-h')}">&lt;</a>
				<a id="button_forward" class="$flat_btn" style="${args->btn_style:html:input_type(css):arg_name(Arrow button style):arg_section(3, 1, 'With slider arrows', 'arrows-h')}" hover_style="${args->btn_hover_style:html:input_type(css):arg_name('Arrow button style: hover'):arg_section(3, 2, 'With slider arrows', 'arrows-h')}">&gt;</a>
			</td>
			${block->x:default(0):arg_name(With close button):arg_section(4, 0, 'Close button', 'close')}
			<td style="width:1px; white-space:nowrap; ${args->x_style:html:input_type(css):arg_name(Close button position):arg_section(4, 2, 'Close button', 'close')}">
				${args->x:input_type(dontshowagain):input_props('style=cursor:pointer; vertical-align:middle'):arg_name(Close button):arg_section(4, 1, 'Close button', 'close')}
			</td>
		</tr>
	</table>
	<table style="width:100%; border-collapse:separate; border-spacing:12px">
		<tr class="$table_slider" data-disabled="${args->with_slider:html:input_type(checkbox):input_props('value_off=1','value_on='):arg_name(Use slider widget):arg_section(1, 0, 'With slider', 'arrow-right'):onchange('block.with_arrows=args.with_slider!=1')}" style="border:none; max-width:${args->width:html:default(885px):input_type(css_length):input_props('with_options=none'):arg_name(Widget maximum width):arg_section(0, 0, 'Frame', 'th-large')}" for_max_vw="${args->for_max_vw:html:default(0px):input_type(css_length):input_props('with_options=always'):arg_name(Slider widget only if screen width is less than or equal to):arg_section(1, 1, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" eq_cell_width="${args->eq_cell_width:html:default(1):input_type(checkbox):input_props('value_off=','value_on=1'):arg_name(Equal cell width):arg_section(0, 2, 'Frame', 'th-large')}" eq_cell_height="${args->eq_cell_height:html:default(1):input_type(checkbox):input_props('value_off=','value_on=1'):arg_name(Equal rows height):arg_section(0, 3, 'Frame', 'th-large')}" arrow_back_img="${args->arrow_back_img:html:input_type(emarketer_media_url):arg_name(Left arrow image):arg_section(1, 2, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" arrow_forward_img="${args->arrow_forward_img:html:input_type(emarketer_media_url):arg_name(Right arrow image):arg_section(1, 3, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" arrow_back_id="button_back" arrow_forward_id="button_forward">
			${foreach recom_articles as p limit 5}
				<td data-style="padding:0; text-align:center; background-color:white; ${args->td_css:html:default('vertical-align: middle;
box-shadow: none;
max-width: 230px;
min-width: 0;'):input_type(css):input_props('with_responsive=1'):arg_name(Cell style):arg_section(0, 4, 'Frame', 'th-large')}">
					<a data-emarketer-click-target="articles ${p->internal_id:html}" href="${p->content_url:html:arg_name(Link target URL):arg_section(7, 0, 'Link target URL', 'link'):column_tags('url','custom text')}" target="_blank">
						<div data-style="${args->div_css:html:default('background-color: #ffffff;
padding: 4px;'):input_type(css):input_props('with_responsive=1'):arg_name(Image background):arg_section(5, 2, 'Image', 'image')}">
							<img src="${p->image_big_url:html:arg_name(Item image):arg_section(5, 0, 'Image', 'image'):column_tags(image)}" data-style="${args->img_css:html:default('width: auto;
height: auto;
max-width: 140px;
min-height: 100px;'):input_type(css):input_props('with_responsive=1'):arg_name(Image properties):arg_section(5, 1, 'Image', 'image')}">
						</div>
					</a>
					<a data-emarketer-click-target="articles ${p->internal_id:html}" href="${p->content_url:html:arg_name(Link target URL):arg_section(7, 0, 'Link target URL', 'link'):column_tags('url','custom text')}" target="_blank">
						<div data-style="display:inline-block; text-align:left; text-align:start; ${args->a_css:html:default('color: #6587AB;
font-size: sel(14px, 5vw);
padding-top: 0px;
padding-right: 5px;
padding-bottom: 0px;
padding-left: 5px;
text-align: center;'):input_type(css):input_props('with_responsive=1'):arg_name(Text color):arg_section(6, 1, 'Text', 'align-justify')}">
							${p->title:arg_name(Item text):arg_section(6, 0, 'Text', 'align-justify')}
						</div>
					</a>
				</td>
			${end}
		</tr>
	</table>
</div>
```


## Content Widget

First article image is bigger than the rest of articles

```
<div style="${args->style:html:default('border:none; direction:rtl; font-family:HelveticaNeueReg'):input_type(css):arg_name(Style):arg_section(0, 0, 'Frame', 'th-large')}">
	${block->title:default(0):arg_name(With title bar):arg_section(1, 0, 'Title', 'bookmark')}
	<div style="${args->title_style:html:input_type(css):arg_name(Style):arg_section(1, 2, 'Title', 'bookmark')}">
		${block->x:arg_name(With close button):arg_section(2, 0, 'Close button', 'close')}
		<div style="float:right; cursor:pointer; margin:0 0 .3em .3em">
			${args->x:input_type(dontshowagain):arg_name(Close button):arg_section(2, 1, 'Close button', 'close')}
		</div>
		${args->title:arg_name(Text):arg_section(1, 1, 'Title', 'bookmark')}
		<div style="clear:both"></div>
	</div>
	<table style="${args->table_style:html:default('border-collapse:separate; border-spacing:2px; max-width:320px'):input_type(css):arg_name(Table Style):arg_section(0, 1, 'Frame', 'th-large')}">
		${foreach sum_articles_week as p order by p->n_viewed desc limit 5}
			<tr>
				<td style="${args->td_align:html:default('vertical-align:top'):input_type(css):arg_name(Vertical Alignment):arg_section(4, 7, 'Article Name', 'bars')}">
					<a href="${p->content_url:html:arg_name(Link target URL):arg_section(5, 0, 'Link target URL', 'link'):column_tags('url','custom text')}" target="${args->target:html:default(_self):input_type(a_target):arg_name(Open link in):arg_section(5, 1, 'Link target URL', 'link')}" style="display:block; position:relative; color:inherit; text-decoration:inherit">
						<img src="${p->image_big_url:html:arg_name(Item image):arg_section(3, 0, 'Image', 'image'):column_tags(image)}" style="${args->img_css:html:default('width: auto;
height: auto;
max-width: 100px;
max-height: 100px;
border: none;'):input_type(css):arg_name(Image Size):arg_section(3, 1, 'Image', 'image')}">
					</a>
				</td>
				<td style="${args->td_align:html}">
					<a href="${p->content_url:html}" target="${args->target:html}" style="display:block; position:relative; color:inherit; text-decoration:inherit">
						<div style="${args->name_style:html:default('border-right:solid #A20000 3px; margin:0 10px 0 0; padding: 0 6px 0 0; font-size:14px; color: #716363'):input_type(css):arg_name(Article Name Style):arg_section(4, 2, 'Article Name', 'bars')}">
							${p->title:arg_name(Article Name):arg_section(4, 1, 'Article Name', 'bars')}
						</div>
						<div style="${args->desc_style:html:default('margin: 0 10px 10px 0; font-size:18px'):input_type(css):arg_name(Article Description Style):arg_section(4, 5, 'Article Name', 'bars')}">
							${p->description:arg_name(Article Description):arg_section(4, 4, 'Article Name', 'bars')}
						</div>
					</a>
				</td>
			</tr>
			${block->with_separator:default(1):arg_name(With Separator):arg_section(0, 2, 'Frame', 'th-large')}
			<tr>
				<td colspan="2">
					<div style="${args->hr_style:html:default('height:1px; margin:8px 0'):input_type(css):arg_name(Separator Style):arg_section(0, 3, 'Frame', 'th-large')}"></div>
				</td>
			</tr>
		${end}
	</table>
	${block->em:default(1):arg_name(Emphasize First Item):arg_section(4, 0, 'Article Name', 'bars')}
	<span ontplready="
		var tr = this.previousElementSibling.children[0].children[0];
		if (tr)
		{	var td0=tr.children[0], td1=tr.children[1], a0=td0.children[0], a1=td1.children[0], img=a0.children[0], name=a1.children[0], desc=a1.children[1];
			tr.removeChild(td1);
			td0.colSpan = 2;
			a0.parentNode.insertBefore(a1, a0);
			a0.appendChild(desc);
			img.style.cssText += ';'+this.dataset.imgStyle;
			name.style.cssText += ';'+this.dataset.nameStyle;
			desc.style.cssText += '; position:absolute; '+this.dataset.descStyle;
		}
	" data-img-style="${args->em_img_css:html:default('width: auto; height: auto; max-width: 100%; max-height: 200px; border: none;'):input_type(css):arg_name(Emphasized Image Size):arg_section(3, 2, 'Image', 'image')}" data-name-style="${args->em_name_style:html:default('border-right:solid #A20000 8px; margin:0 0 18px 0; padding: 0 6px 0 0; font-size:26px; color: black; background-color:#F5F5F5; font-family: HelveticaNeueBold'):input_type(css):arg_name(Emphasized Name Style):arg_section(4, 3, 'Article Name', 'bars')}" data-desc-style="${args->em_desc_style:html:default('right:0; bottom:0; color:white; font-family: HelveticaNeueBold'):input_type(css):arg_name(Emphasized Description Style):arg_section(4, 6, 'Article Name', 'bars')}"></span>
</div>
```


## Default Vertical List



```
<div style="${args->a_style3:html:default('color: #444;
font-family: arial,sans-serif;
font-size: 12px;
line-height: 18px;
max-width: 450px;'):input_type(css):arg_name(Style):arg_section(0, 0, 'Box', 'th-large')}">
	<div style="${args->a_style:html:default('text-align: left;
padding-top: 25px;
padding-right: 0;
padding-bottom: 25px;
padding-left: 15px;
font-family: "caecilla",serif;
color: rgb(106, 67, 67);
text-transform: uppercase;
font-weight: bold;
font-size: 22px;'):input_type(css):arg_name(Style):arg_section(1, 0, 'Title', 'bookmark')}">
		${args->line:default(Recommended For You):arg_name(Text):arg_section(1, 1, 'Title', 'bookmark')}
	</div>
	<div style="display:flex; flex-wrap:wrap; justify-content:space-between; align-items:stretch">
		${foreach recom_articles as p limit 4}
			<a data-emarketer-click-target="products ${p->internal_id:html}" href="${p->content_url:html:default('p->content_url')}" style="display:block; position:relative; ${args->a_style4:html:default('margin-top: 0px;
margin-right: 21px;
margin-bottom: 20px;
margin-left: 21px;
border: -43px solid #bababa;
text-align: center;
width: 140px;
box-shadow: 0px 0px 20px rgba(0, 0, 0, 0.09);
text-decoration: none;'):input_type(css):arg_name(Cell):arg_section(2, 2, 'Cell', 'bars')}">
				<div style="margin-bottom:4em; ${args->a_style40:html:default('					padding:10px 15px
				'):input_type(css):arg_name(Cell):arg_section(2, 3, 'Cell', 'bars')}">
					<img src="${p->image_big_url:html:default('p->image_big_url')}" alt="${p->title:html}" title="${p->title:html}" style="width:auto; height:auto; ${args->a_style7:html:default('max-height: 100px;
margin-bottom: 10px;
border: none;
max-width: 120px;
height: auto;
width: auto;'):input_type(css):arg_name(Product image style):arg_section(2, 1, 'Cell', 'bars')}">
					<div style="${args->a_style5:html:default('color: #b72913;
font-size: 13px;
font-weight: bold;
text-align: center;'):input_type(css):arg_name(Product name):arg_section(2, 0, 'Cell', 'bars')}">
						${p->title}
					</div>
				</div>
				<div style="position:absolute; width:100%; bottom:10px; text-align:center">
					<div style="display:inline-block; ${args->a_style6:html:default('background-color: #a70050;
border-bottom: 0px solid #b4a600;
border-left: 0px solid #fff045;
border-right: 0px solid #d5c614;
border-top: 0px solid #fff045;
color: rgb(256, 256, 256);
font-size: 14px;
padding-top: 5px;
padding-right: 20px;
padding-bottom: 5px;
padding-left: 20px;
-webkit-appearance: none;'):input_type(css):arg_name(Style):arg_section(3, 1, 'Button', 'bars')}">
						${args->line3:default(View):arg_name(Text):arg_section(3, 0, 'Button', 'bars')}
					</div>
				</div>
			</a>
		${end}
	</div>
</div>
```


## Image, Title, Arrows Widget



```
<div class="$responsive" data-style="${args->style:html:default('border: none;
width: 100%;
box-sizing: border-box;
padding: 0 10px;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(0, 1, 'Frame', 'th-large')}">
	${block->title:default(1):arg_name(With title bar):arg_section(2, 0, 'Title', 'bookmark')}
	<table data-style="width:100%; border-collapse:collapse; border:none; ${args->title_bg:html:default('background-color: rgba(170, 76, 76, 0);
margin-top: 3px;
margin-right: 0px;
margin-bottom: 7px;
margin-left: 13px;
padding-top: 10px;
border-top: 2px solid #f58233;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(2, 2, 'Title', 'bookmark')}">
		<tr>
			<td data-style="vertical-align:middle; ${args->title_style:html:default('background-color: #fff;
position: relative;
z-index: 1;
padding-top: 10px;
padding-right: 0em;
padding-bottom: 0px;
padding-left: 0em;
color: rgb(27, 117, 188);
font-weight: 700;
font-size: 20px;
text-align: left;
font-family: caecilla, serif;'):input_type(css):input_props('with_responsive=1'):arg_name(Title style):arg_section(2, 3, 'Title', 'bookmark')}">
				${args->title:default(Recommended for you):arg_name(Text):arg_section(2, 1, 'Title', 'bookmark')}
			</td>
			${block->with_arrows:default(false):arg_name(With arrow buttons):arg_section(3, 0, 'With slider arrows', 'arrows-h')}
			<td style="width:1px; white-space:nowrap; vertical-align:middle">
				<a id="button_back" class="$flat_btn" style="${args->btn_style:html:input_type(css):arg_name(Arrow button style):arg_section(3, 1, 'With slider arrows', 'arrows-h')}" hover_style="${args->btn_hover_style:html:input_type(css):arg_name('Arrow button style: hover'):arg_section(3, 2, 'With slider arrows', 'arrows-h')}">&lt;</a>
				<a id="button_forward" class="$flat_btn" style="${args->btn_style:html}" hover_style="${args->btn_hover_style:html}">&gt;</a>
			</td>
			${block->x:default(0):arg_name(With close button):arg_section(4, 0, 'Close button', 'close')}
			<td style="width:1px; white-space:nowrap; ${args->x_style:html:input_type(css):arg_name(Close button position):arg_section(4, 2, 'Close button', 'close')}">
				${args->x:input_type(dontshowagain):input_props('style=cursor:pointer; vertical-align:middle'):arg_name(Close button):arg_section(4, 1, 'Close button', 'close')}
			</td>
		</tr>
	</table>
	<table style="width:100%; border-collapse:separate; border-spacing:12px">
		<tr class="$table_slider" data-disabled="${args->with_slider:html:default(1):input_type(checkbox):input_props('value_off=1','value_on='):arg_name(Use slider widget):arg_section(1, 0, 'With slider', 'arrow-right'):onchange('block.with_arrows=args.with_slider!=1')}" style="border:none; max-width:${args->width:html:default(none):input_type(css_length):input_props('with_options=none'):arg_name(Widget maximum width):arg_section(0, 0, 'Frame', 'th-large')}" for_max_vw="${args->for_max_vw:html:input_type(css_length):input_props('with_options=always'):arg_name(Slider widget only if screen width is less than or equal to):arg_section(1, 1, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" eq_cell_width="${args->eq_cell_width:html:default(1):input_type(checkbox):input_props('value_off=','value_on=1'):arg_name(Equal cell width):arg_section(0, 2, 'Frame', 'th-large')}" eq_cell_height="${args->eq_cell_height:html:default(1):input_type(checkbox):input_props('value_off=','value_on=1'):arg_name(Equal rows height):arg_section(0, 3, 'Frame', 'th-large')}" arrow_back_img="${args->arrow_back_img:html:input_type(emarketer_media_url):arg_name(Left arrow image):arg_section(1, 2, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" arrow_forward_img="${args->arrow_forward_img:html:input_type(emarketer_media_url):arg_name(Right arrow image):arg_section(1, 3, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" arrow_back_id="button_back" arrow_forward_id="button_forward">
			${foreach recom_articles as p limit 5}
				<td data-style="padding:0; text-align:center; background-color:white; ${args->td_css:html:default('vertical-align: middle;
box-shadow: none;
max-width: 230px;
min-width: 0;'):input_type(css):input_props('with_responsive=1'):arg_name(Cell style):arg_section(0, 4, 'Frame', 'th-large')}">
					<a data-emarketer-click-target="articles ${p->internal_id:html}" href="${p->content_url:html:arg_name(Link target URL):arg_section(7, 0, 'Link target URL', 'link'):column_tags('url','custom text')}" target="_blank">
						<div data-style="${args->div_css:html:default('background-color: #ffffff;
padding: 4px;'):input_type(css):input_props('with_responsive=1'):arg_name(Image background):arg_section(5, 2, 'Image', 'image')}">
							<img src="${p->image_big_url:html:arg_name(Item image):arg_section(5, 0, 'Image', 'image'):column_tags(image)}" data-style="${args->img_css:html:default('width: auto;
height: auto;
max-width: 140px;
max-height: 100px;'):input_type(css):input_props('with_responsive=1'):arg_name(Image properties):arg_section(5, 1, 'Image', 'image')}">
						</div>
					</a>
					<a data-emarketer-click-target="articles ${p->internal_id:html}" href="${p->content_url:html}" target="_blank">
						<div data-style="display:inline-block; text-align:left; text-align:start; ${args->a_css:html:default('color: #1b75bc;
font-size: sel(14px, 5vw);
padding-top: 0px;
padding-right: 5px;
padding-bottom: 0px;
padding-left: 5px;
text-align: center;'):input_type(css):input_props('with_responsive=1'):arg_name(Text color):arg_section(6, 1, 'Text', 'align-justify')}">
							${p->title:arg_name(Item text):arg_section(6, 0, 'Text', 'align-justify')}
						</div>
					</a>
				</td>
			${end}
		</tr>
	</table>
</div>
```


## With rating



```
<div class="$responsive" data-style="box-sizing:border-box; background-color:${args->bg:html:default('#41436e'):input_type(color):arg_name(Background color):arg_section(0, 0, 'Frame', 'th-large')}; ${args->style:html:default('max-width: 520px;
border: none;
line-height: 1.42857143;
color: white;
font-family: Roboto,Arial,sans-serif;
font-weight: 500;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(0, 1, 'Frame', 'th-large')}">
	${block->title:default(1):arg_name(With title bar):arg_section(1, 0, 'Title', 'bookmark')}
	<div data-style="${args->title_style:html:default('padding:16px; font-family: "Roboto Condensed","Arial Narrow",Arial,sans-serif; font-size:20px; font-weight:700'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(1, 2, 'Title', 'bookmark')}">
		${block->x:default(1):arg_name(With close button):arg_section(2, 0, 'Close button', 'close')}
		<div style="float:right; cursor:pointer; margin:0 0 .3em .3em">
			${args->x:default('<div class="$emarketer_button_dont_show_again" data-action_id="${action_id}" style="display: inline-block; vertical-align: text-bottom; width: 24px; height: 24px; box-sizing: border-box; border-radius: 50%; border: 2px solid; box-shadow: rgba(255, 255, 255, 0.2) 0px 1px 0px inset, rgba(0, 0, 0, 0.2) 0px 1px 2px; padding: 3px; background-color: rgb(85, 85, 85); text-decoration-color: rgb(85, 85, 85); outline-color: rgb(206, 54, 64); outline-width: 10px; color: white; cursor: pointer; transition: all 0.3s ease 0s;">
<div style="display: block; width: 100%; height: 100%; transition: all 0.3s ease 0s; border-radius: 50%; background-image: linear-gradient(-45deg, transparent 0%, transparent 46%, currentcolor 46%, currentcolor 56%, transparent 56%, transparent 100%), linear-gradient(45deg, transparent 0%, transparent 46%, currentcolor 46%, currentcolor 56%, transparent 56%, transparent 100%);"><br />
</div>
</div>
'):input_type(dontshowagain):arg_name(Close button):arg_section(2, 1, 'Close button', 'close')}
		</div>
		${args->title:default(Articles selection):arg_name(Text):arg_section(1, 1, 'Title', 'bookmark')}
		<div style="clear:both"></div>
	</div>
	<div style="display:flex; flex-flow:row; flex-wrap:wrap">
		${foreach sum_last_viewed_categories_articles as p where p->for_period='week' order by p->n_viewed desc limit 5}
			<div style="box-sizing:border-box; width:${args->cell_width:html:default(260px):input_type(css_length):input_props('with_responsive=1'):arg_name(Cell width):arg_section(0, 2, 'Frame', 'th-large')}">
				<div data-style="display:flex; align-items:center; ${args->a_style:html:default('font-size: 16px;
margin: 5px;'):input_type(css):input_props('with_responsive=1'):arg_name(Cell style):arg_section(3, 1, 'Cell', 'bars')}" onmouseenter="this._s=this.style.cssText; this.style.cssText+=';'+this.dataset.hoverStyle" onmouseleave="if (this._s) this.style.cssText=this._s" data-hover-style="${args->a_hover_style:html:default('box-shadow: 0 0 10px #888;'):input_type(css):arg_name(Style):arg_section(3, 2, 'Cell', 'bars')}">
					<a href="${p->content_url:html}" data-style="flex-grow:100; color:inherit; text-decoration:none; padding:${args->a_padding:html:default(16px):input_type(css_length):input_props('with_responsive=1'):arg_name(Padding):arg_section(3, 3, 'Cell', 'bars')}">
						${p->title:arg_name(Item text):arg_section(3, 0, 'Cell', 'bars')}
						${block->rating:default(1):arg_name(With rating):arg_section(4, 0, 'Rating', 'star-half-empty')}
						<div data-style="${args->rating_style:html:default('color:#f2c71a'):input_type(css):input_props('with_responsive=1'):arg_name(Rating style):arg_section(4, 4, 'Rating', 'star-half-empty')}">
							<input class="$rating" value="${p->custom_1:html:default(0):arg_name(Rating):arg_section(4, 1, 'Rating', 'star-half-empty')}" max="${args->rank_max:html:default(5):input_type(number):arg_name(Maximum rating number that corresponds to 100%):arg_section(4, 3, 'Rating', 'star-half-empty')}" style="background-color:${args->bg:html}">
						</div>
						${block->rating_text:default(1):arg_name(With rating text):arg_section(4, 5, 'Rating', 'star-half-empty')}
						<div data-style="${args->rating_text_style:html:input_type(css):input_props('with_responsive=1'):arg_name(Rating text style):arg_section(4, 6, 'Rating', 'star-half-empty')}">
							${p->custom_1:html:default(0)}
							${args->of:default(out of):arg_name(Of):arg_section(4, 2, 'Rating', 'star-half-empty')}
							${args->rank_max:html}

							${block->rating_votes:default(1):arg_name(With no. of votes):arg_section(4, 7, 'Rating', 'star-half-empty')}
							<span>
								${args->votes_before:default('('):arg_name('No. of votes: text before'):arg_section(4, 8, 'Rating', 'star-half-empty')}${p->custom_i_1:html:default(0):arg_name(No. of votes):arg_section(4, 9, 'Rating', 'star-half-empty')}${args->votes_after:default(' Ratings)'):arg_name('No. of votes: text after'):arg_section(4, 10, 'Rating', 'star-half-empty')}
							</span>
						</div>
					</a>
					<div style="padding:${args->a_padding:html}; padding-left:0; padding-top:0; padding-bottom:0; text-align:right; ${args->arrow_style:html:default('font-size:22px;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(3, 4, 'Cell', 'bars')}">
						>
					</div>
				</div>
			</div>
		${end}
	</div>
</div>
```


## Widget one column



```
<div class="$responsive">
	<style>
		img.st-zoom {transition:transform ease 0.3s; transform: scale(1)}
		img.st-zoom:hover {transform: scale(calc(${args->img_zoom_on_hover:default(120)} / 100))}
	</style>
	${block->with_hover_image:default(0)}
	<style>
		img.st-zoom {transition-property:opacity; transform: scale(1); opacity: 1}
		img.st-zoom:hover {transform: scale(1); opacity: 0}

		img.st-zoom:last-child {transition:transform ease 0.3s; transform: scale(1)}
		img.st-zoom:last-child:hover {transform: scale(calc(${args->img_zoom_on_hover} / 100)); opacity: 1}

		img.st-zoom + div > img {transition:opacity ease 0.3s; opacity: 0}
		img.st-zoom + div > img:hover {opacity: 1}
	</style>
	<table style="${args->table_style:html:default('border-collapse: separate;
border-spacing: 2px;
max-width: 320px;
')}">
		<caption>
			${block->title:default(1)}
			<div style="display:flex; align-items:stretch; ${args->title_style:html:default('text-align: left;
font-size: 18px;
')}">
				<div style="flex-grow:1000">
					${args->title:default(See also)}
				</div>
				${block->x:default(1)}
				<div style="cursor:pointer; margin:0 0 .3em .3em">
					${args->x:default('<svg viewBox="0 0 24 24" width="22" height="22" enable-background="new 0 0 24 24" fill="#000" class="$personyze_button_dont_show_again" data-action_id="${action_id}"><path d="M12.0119629,2.0039062C6.491272,2.0006104,2.0131836,6.4733276,2.0098877,11.9940186S6.4793091,21.9927979,12,21.9960938c2.6522827,0.0043335,5.1970215-1.0482178,7.0712891-2.9248047c1.875-1.8734131,2.9291992-4.4147949,2.9307861-7.0653076C22.0053711,6.4852905,17.5326538,2.0072021,12.0119629,2.0039062z M12.0122681,20.9960938c-4.9684448,0.0033569-8.9988403-4.0215454-9.0022583-8.9899902C3.0066528,7.0377197,7.0316162,3.0072632,12,3.0039062c2.387085-0.0042725,4.6774292,0.9428711,6.3642578,2.6318359c1.687439,1.6858521,2.6363525,3.9728394,2.6379395,6.3581543C21.0056152,16.9622803,16.9806519,20.9926758,12.0122681,20.9960938z M12.7069702,12l3.1816406-3.1816406c0.1905518-0.194397,0.1905518-0.5054932,0-0.6998901c-0.1932373-0.1972046-0.5097656-0.2003784-0.7069702-0.0071411L12,11.2929688L8.8183594,8.1113892c-0.194397-0.1904907-0.5054932-0.1904907-0.6998901,0C7.9212646,8.3046265,7.9180908,8.6211548,8.1113281,8.8183594L11.2929688,12l-3.1816406,3.1816406c-0.09375,0.09375-0.1463623,0.2208862-0.1464233,0.3534546c0,0.276123,0.2238159,0.5,0.499939,0.500061c0.1326294,0.0001831,0.2598877-0.0525513,0.3535156-0.1464844L12,12.7070312l3.1816406,3.1816406c0.0936279,0.0939331,0.2208862,0.1466675,0.3535156,0.1464844v0.000061c0.1325684-0.000061,0.2596436-0.0527344,0.3533936-0.1464233c0.1953125-0.1952515,0.1953125-0.5118408,0.000061-0.7071533L12.7069702,12z"></path></svg>')}
				</div>
			</div>
		</caption>
		${foreach articles as p order by p->time_created desc limit 5}
			<tr>
				<td style="${args->td_align:html:default('vertical-align: top;
')}">
					<div style="position:relative">
						<a data-personyze-click-target="articles ${p->internal_id:html}" href="${p->content_url:html}" target="${args->target:html:default(_self)}" style="position:relative; display:inline-block; overflow:hidden; color:inherit; text-decoration:inherit">
							<img class="st-zoom" src="${p->image_big_url:html}" style="${args->img_css:html:default('width: auto;
height: auto;
max-width: 100px;
max-height: 100px;
border: none;
')}">

							${if p->image_medium_url <> ''}
								${block->with_hover_image:default(0)}
								<div style="position:absolute; left:0; top: 0; width:100%; height:100%">
									<img src="${p->image_medium_url:html}" style="${args->img_css:html}">
								</div>
							${end}
						</a>

						${block->with_new_badge:default(1)}
						<span>
							${if unix_timestamp() - p->time_created <= args->badge_if_newer:default(2851200)}
								<div data-style="position: absolute; ${args->new_badge_style:html:default('top: 0;
left: 48px;
font-size: 14px;
text-shadow: rgba(255,255,255,0.5) 0px 3px 3px;
background-color: rgb(50, 101, 219);
color: rgb(250, 246, 246);
display: flex;
justify-content: center;
align-items: center;
padding: 0.3em;
')}">
									<span data-style="${args->new_badge_text_style:html:default('font-size: 16px;
font-weight: 600;
')}">${args->new_badge_text:default(NEW)}</span>
								</div>
							${end}
						</span>

						${block->with_time_badge:default(0)}
						<span>
							${if p->custom_i_1 - unix_timestamp() >= 0}
								<div data-style="position: absolute; ${args->time_badge_style:html:default('top: 0;
left: 48px;
font-size: 14px;
text-shadow: rgba(255,255,255,0.5) 0px 3px 3px;
background-color: rgb(50, 101, 219);
color: rgb(250, 246, 246);
display: flex;
justify-content: center;
align-items: center;
padding: 0.3em;
')}">
								<span data-style="${args->time_badge_text_style:html:default('font-size: 16px;
font-weight: 600;
')}">${args->time_badge_text:default(Special offer till)}</span>
									${block->with_time_badge_countdown}
									<span data-end="${p->custom_i_1:html- unix_timestamp()}" data-d="${args->time_badge_days:html:default(days)}" data-h="${args->time_badge_hr:html:default(hr)}" data-m="${args->time_badge_min:html:default(min)}" data-s="${args->time_badge_sec:html:default(sec)}" ontplready="var t=this, end=t.dataset.end|0, d=t.dataset.d, h=t.dataset.h, m=t.dataset.m, s=t.dataset.s; (function p() {var r=end-new Date().getTime()/1000; t.parentNode.parentNode.style.display = r<=0 ? 'none' : ''; t.textContent = ns.sec_to_span(r - r%(r >= 3*24*60*60 ? 24*60*60 : r > 24*60*60 ? 60*60 : 1), s, m, h, d); if (r <= 24*60*60) setTimeout(p, 1000)})()"></span>
								</div>
							${end}
						</span>

						${block->with_wishlist_badge:default(0)}
						<span class="$switch-elem"
							data-case="${foreach articles_interactions as w where w->internal_id = p->internal_id and w->interaction_status = 'favorite' limit 1}on${end}"
							data-p="${p->internal_id:html}"
							data-style="position:absolute; transition: all 0.3s ease; ${args->wishlist_style:html:default('top: 5px;
right: 5px;
color: rgb(119, 181, 115);
font-size: 18px;
')}"
							onclick="var on=this._get_case(); _S_T.push([on ? 'Article Unliked' : 'Article Liked', this.dataset.p]); this._set_case(on ? '' : 'on'); event.stopPropagation(); event.preventDefault()"
						>
							<div data-case="" class="$hint" style="${args->wishlist_off_style:html}">
								<span data-content="1">${args->wishlist_add_text:default(Add to wishlist)}</span>
								<hr class="$icon heart-o">
							</div>
							<div data-case="on" class="$hint" style="${args->wishlist_on_style:html:default('background-color: rgba(177, 93, 93, 0);
')}">
								<span data-content="1">${args->wishlist_rm_text:html:default(Remove from wishlist)}</span>
								<hr class="$icon heart">
							</div>
						</span>

						${block->with_db_badge:default(0)}
						<span>
							<div data-style="position: absolute; ${args->db_badge_style:html:default('top: 0;
left: 0px;
font-size: 14px;
text-shadow: rgba(255,255,255,0.5) 0px 3px 3px;
background-color: rgb(50, 101, 219);
color: rgb(250, 246, 246);
display: flex;
justify-content: center;
align-items: center;
padding: 0.3em;
')}">
								${block->with_db_badge_icon}
								<hr class="$icon ${args->db_badge_text_icon:html:default(bookmark)}">
								<span data-style="${args->db_badge_text_style:html:default('font-size: 16px;
font-weight: 600;
')}">${args->db_badge_text:default('${p->custom_2}')}</span>
							</div>
						</span>
					</div>
				</td>
				<td style="${args->td_align:html}">
					<a data-personyze-click-target="articles ${p->internal_id:html}" href="${p->content_url:html}" target="${args->target:html}" style="display:block; position:relative; color:inherit; text-decoration:inherit">
						<div style="${args->name_style:html:default('border-left: solid #A20000 3px;
margin-top: 0;
margin-right: 0;
margin-bottom: 0;
margin-left: 10px;
padding-top: 0;
padding-right: 0;
padding-bottom: 0;
padding-left: 6px;
font-size: 14px;
color: #716363;
')}">
							${p->title}


							${block->with_date:default(1)}
							<div style="${args->date_column_style:html:default('padding-top: 0;
padding-right: 0;
padding-bottom: 1em;
padding-left: 0;
font-weight: 600;
')}" ontplready="this.innerHTML = window._S_T ? _S_T.ftime.strftime('${args->date_column_format:html:default('%B %d, %Y')}', ${args->date_column:html:default('${p->data_last_modified}')}) : '';"></div>



							${block->rating:default(0)}
							<span>
								<hr class="$rating" data-value="${p->rank:html:default(0)}" style="${args->rating_style:html:default('color: yellow;
--bgcolor: white;
--border-color: rgba(225, 214, 214, 0.87);
width: 10em;
height: 1.8em;
')}">
							</span>

							${block->stats_1day:default(1)}
                            <span>
                                ${foreach sum_products_1day as s where s->internal_id = p->internal_id limit 1}
                                    ${if s->n_viewed >= args->hide_no_view_1day:default(3)}
                                        ${if s->n_goal >= args->hide_no_goal_1day:default(1)}
                                            <div style="${args->text_style_1day:html:default('padding-top: 1em;
padding-right: 0;
padding-bottom: 1em;
padding-left: 0;
font-weight: 600;
')}">
                                                ${if s->n_viewed > 0}
                                                    ${args->n_viewed_1day:default('<div>This article has been popular today! ${s->n_viewed*1} views.</div>
')}
                                                ${end}
                                                ${if s->n_goal > 0}
                                                    ${args->n_goal_1day:default('<div>${s->n_goal*1}&nbsp; downloads today</div>
')}
                                                ${end}
                                            </div>
                                        ${end}
                                    ${end}
                                ${end}
                            </span>

                            ${block->stats_week:default(0)}
                            <span>
                                ${foreach sum_products_week as s where s->internal_id = p->internal_id limit 1}
                                    ${if s->n_viewed >= args->hide_no_view_week:default(3)}
                                        ${if s->n_goal >= args->hide_no_goal_week:default(1)}
                                            <div style="${args->text_style_week:html:default('padding-top: 1em;
padding-right: 0;
padding-bottom: 1em;
padding-left: 0;
font-weight: 600;
')}">
                                                ${if s->n_viewed > 0}
                                                    ${args->n_viewed_week:default('<div>This article has been popular in the last week! ${s->n_viewed*1} views this week.</div>
')}
                                                ${end}
                                                ${if s->n_goal > 0}
                                                    ${args->n_goal_week:default('<div>${s->n_goal*1}&nbsp; downloads this week</div>
')}
                                                ${end}
                                            </div>
                                        ${end}
                                    ${end}
                                ${end}
                            </span>
						</div>
						<div style="${args->desc_style:html:default('margin-top: 0;
margin-right: 10px;
margin-bottom: 10px;
margin-left: 0;
font-size: 18px;
')}">
							${p->description}
						</div>
					</a>
				</td>
			</tr>
			${block->with_separator:default(1)}
			<tr>
				<td colspan="2">
					<div style="${args->hr_style:html:default('height: 1px;
margin-top: 8px;
margin-right: 0;
margin-bottom: 8px;
margin-left: 0;
')}"></div>
				</td>
			</tr>
		${end}
	</table>
	${block->em:default(0)}
	<span ontplready="
		var tr = this.previousElementSibling.getElementsByTagName('tr')[0];
		if (tr && tr.children.length==2)
		{	var td0=tr.children[0], td1=tr.children[1], d0=td0.children[0], a0=d0.children[0], a1=td1.children[0], imgs=a0.getElementsByTagName('img'), name=a1.children[0], desc=a1.children[1];
			tr.removeChild(td1);
			td0.colSpan = 2;
			td0.insertBefore(a1, d0);
			td0.appendChild(desc);
			imgs[0].style.cssText += ';'+this.dataset.imgStyle;
			if (imgs[1]) imgs[1].style.cssText += ';'+this.dataset.imgStyle;
			name.style.cssText += ';'+this.dataset.nameStyle;
			desc.style.cssText += '; position:absolute; '+this.dataset.descStyle;
		}
" data-img-style="${args->em_img_css:html:default('width: auto;
height: auto;
max-width: 100%;
max-height: 200px;
border: none;
')}" data-name-style="${args->em_name_style:html:default('border-left: solid #A20000 8px;
margin-top: 0;
margin-right: 0;
margin-bottom: 18px;
margin-left: 0;
padding-top: 0;
padding-right: 0;
padding-bottom: 0;
padding-left: 6px;
font-size: 26px;
color: black;
background-color: #F5F5F5;
font-family: HelveticaNeueBold;
')}" data-desc-style="${args->em_desc_style:html:default('right:0; bottom:0; color:white; font-family: HelveticaNeueBold')}"></span>
</div>

${menu name='Frame', icon='th-large'}
	${menu args->table_style name='Table Style', type='css'}
	${menu block->with_separator name='With Separator'}
	${menu args->hr_style name='Separator Style', type='css'}
${menu name='Title', icon='bookmark'}
	${menu block->title name='With title bar'}
	${menu args->title name='Text'}
	${menu args->title_style name='Style', type='css'}
${menu name='Close button', icon='close'}
	${menu block->x name='With close button'}
	${menu args->x name='Close button', type='dontshowagain'}
${menu name='Image', icon='image'}
	${menu p->image_big_url name='Item image', column_tags='image'}
	${menu args->img_css name='Image Size', type='css'}
	${menu args->em_img_css name='Emphasized Image Size', type='css'}
${menu name='Zoom image on hover', icon='bars'}
	${menu args->img_zoom_on_hover name='Zoom on hover, %', type='number'}
${menu name='Hover alternative image', icon='image', description='On mouse hover, show additional item images when available on the article feed.'}
	${menu block->with_hover_image name='With hover image', onchange='block.with_zoom_image=block.with_hover_image^1||""'}
	${menu p->image_medium_url name='Hover image', column_tags='image'}
${menu name='New badge', icon='align-justify', description='Set "New" badge to appear for items debut recently.
You may choose a time frame for an article to be considered new. For new accounts/articles feed, all articles are new until the day setting condition has been met.'}
	${menu block->with_new_badge name='With new badge'}
	${menu args->badge_if_newer name='Show NEW badge if newer than', type='date', param='is_span=true', param='format=%0..999d days'}
	${menu args->new_badge_style name='Badge style', type='css', param='with_responsive=1'}
	${menu args->new_badge_text_style name='Badge text style', type='css', param='with_responsive=1'}
	${menu args->new_badge_text name='Text'}
${menu name='Time-based badge', icon='align-justify'}
	${menu block->with_time_badge name='With time-based badge'}
	${menu args->time_badge_style name='Badge style', type='css', param='with_responsive=1'}
	${menu args->time_badge_text_style name='Badge text style', type='css', param='with_responsive=1'}
	${menu args->time_badge_text name='Text'}
	${menu p->custom_i_1 name='Catalog field with end date', description='UNIX-timestamp'}
	${menu block->with_time_badge_countdown name='With days/time remaining'}
	${menu args->time_badge_days name='Time remaining: "days" text'}
	${menu args->time_badge_hr name='Time remaining: "hours" text'}
	${menu args->time_badge_min name='Time remaining: "minutes" text'}
	${menu args->time_badge_sec name='Time remaining: "seconds" text'}
${menu name='Add to wishlist', icon='bars', description='Show save to wishlist icon, on click item will be saved to Personyze wishlist. Items can be included in email/site widgets when using the wishlist algorithm. You can also set JS to report to your site when a visitor is saving an item to a wishlist.'}
	${menu block->with_wishlist_badge name='With add to wishlist'}
	${menu args->wishlist_style name='Style', type='css'}
	${menu args->wishlist_off_style name='Off icon style', type='css'}
	${menu args->wishlist_add_text name='Off tooltip (add to wishlist)'}
	${menu args->wishlist_on_style name='On icon style', type='css'}
	${menu args->wishlist_rm_text name='On tooltip (remove from wishlist)'}
${menu name='Icon or text badge', icon='star', description='Show text taken from catalog field'}
	${menu block->with_db_badge name='With db badge'}
	${menu args->db_badge_style name='Block style', type='css'}
	${menu block->with_db_badge_icon name='With icon'}
	${menu args->db_badge_text_icon name='Icon', type='icon'}
	${menu args->db_badge_text_style name='Icon style', type='css'}
	${menu args->db_badge_text name='Text'}
${menu name='Article Name', icon='bars'}
	${menu block->em name='Emphasize First Item'}
	${menu p->title name='Article Name'}
	${menu args->name_style name='Article Name Style', type='css'}
	${menu args->em_name_style name='Emphasized Name Style', type='css'}
	${menu p->description name='Article Description'}
	${menu args->desc_style name='Article Description Style', type='css'}
	${menu args->em_desc_style name='Emphasized Description Style', type='css'}
	${menu args->td_align name='Vertical Alignment', type='css'}
${menu name='Date', icon='calendar', description='Show date.'}
	${menu block->with_date name='With rating'}
	${menu args->date_column name='Date column'}
	${menu args->date_column_format name='Date format'}
	${menu args->date_column_style name='Style', type='css'}
${menu name='Link target URL', icon='link'}
	${menu p->content_url name='Link target URL', column_tags='url, custom text'}
	${menu args->target name='Open link in', type='a_target'}
${menu name='Rating', icon='star', description='Show article rating when available
This requires you to populate "Rank" on your article feed.'}
	${menu block->rating name='With rating'}
	${menu p->rank name='Rating'}
	${menu args->rating_style name='Colors', type='css', param='vars=--bgcolor:color; --border-color:color'}
${menu name='Site statistics: 1-day', icon='bar-chart', description='Show number of viewed or purchases in the last 24 hours for a given item as tracked by Personyze. You can set a condition not to show if the number of views/purchases is below X number.'}
	${menu block->stats_1day name='Site statistics: 1day'}
	${menu args->hide_no_view_1day name='Hide statistics if less views than', type='number', param='min=0'}
	${menu args->hide_no_goal_1day name='Hide statistics if less goals than', type='number', param='min=0'}
	${menu args->text_style_1day name='Style', type='css'}
	${menu args->n_viewed_1day name='Text'}
	${menu args->n_goal_1day name='Text'}
${menu name='Site statistics: week', icon='bar-chart', description='Show number of viewed or purchases in the last week for a given item as tracked by Personyze. You can set a condition not to show if the number of views/purchases is below X number.'}
	${menu block->stats_week name='Site statistics: week'}
	${menu args->hide_no_view_week name='Hide statistics if less views than', type='number', param='min=0'}
	${menu args->hide_no_goal_week name='Hide statistics if less goals than', type='number', param='min=0'}
	${menu args->text_style_week name='Style', type='css'}
	${menu args->n_viewed_week name='Text'}
	${menu args->n_goal_week name='Text'}
```


## With background image



```
<div class="$responsive" data-style="display:inline-block; position:relative; ${args->style:html:default('padding-right: 0px; padding-left: 0px; border: none; text-align: left; font-weight: bold; font-size: 17px; box-sizing: border-box; width: sel(auto, auto); font-family: Roboto,sans-serif; box-shadow: 0 0px 0px 0 rgba(0,0,0,0.08); background-color: rgba(0, 0, 0, 0); margin-top: 40px; margin-right: 0px; margin-bottom: 1px; margin-left: 0px; min-width: 98%; width: 98%;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(0, 1, 'Frame', 'th-large')}" onupdate="
	var i, d, a=ns.joyquery('parent::*>tr>td>*', by_id.ts).get();
	for (i=0; d=a[i]; i++) if (d.style.display!='inline-block') if (d._w) d.style.width=d._w;
	for (var d=by_id.ts; d.parentNode!=this; d=d.parentNode);
	var
		p=by_id.ts.parentNode.parentNode,
		w=d.offsetWidth-(parseFloat(p.style.marginLeft) || 0),
		b=parseFloat(p.style.borderSpacing),
		d=a[0].parentNode,
		t=d.offsetWidth,
		n=Math.round((w-b) / (t+b)),
		T=w/n-b-(parseFloat(d.style.borderLeftWidth) || 0)-(parseFloat(d.style.borderRightWidth) || 0);
	for (i=0; d=a[i]; i++) if (d.style.display!='inline-block') d._w=d._w||d.style.width, d.style.width=T+'px'
">
	<link href="https://fonts.googleapis.com/css?family=Montserrat&display=swap" rel="stylesheet">
	${block->title:default(1):arg_name(With title bar):arg_section(2, 0, 'Title', 'bookmark')}
	<table data-style="width:98%; margin-right: 1%; margin-left: 1%; border-collapse:collapse; border:none; ${args->title_bg:html:default('background-color: rgba(0, 0, 0, 0); margin-top: 0px; margin-right: 0; margin-bottom: 25px; padding-top: 0px; padding-right: 0; padding-bottom: 0px; padding-left: 0; border-bottom: none;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(2, 3, 'Title', 'bookmark')}">
		<tr>
			<td data-style="vertical-align:middle; ${args->title_style:html:default('text-align: center; font-family: "Montserrat", sans-serif; font-weight: 400; padding-top: 10px; padding-right: 0px; padding-bottom: 5px; padding-left: 15px; font-size: 32px; line-height: 20px; color: #333;'):input_type(css):input_props('with_responsive=1'):arg_name(Title style):arg_section(2, 4, 'Title', 'bookmark')}">
				${args->title:default(Your title):arg_name(Text):arg_section(2, 1, 'Title', 'bookmark')}
			</td>
			${block->with_arrows:default(0):arg_name(With arrow buttons):arg_section(1, 0, 'With slider', 'arrow-right')}
			<td rowspan="2" style="width:1px; white-space:nowrap; vertical-align:middle">
				<a id="button_back" class="$flat_btn" style="${args->btn_style:html:input_type(css):arg_name(Arrow button style):arg_section(1, 1, 'With slider', 'arrow-right')}" hover_style="${args->btn_hover_style:html:input_type(css):arg_name('Arrow button style: hover'):arg_section(1, 2, 'With slider', 'arrow-right')}"><</a>
				<a id="button_forward" class="$flat_btn" style="${args->btn_style:html}" hover_style="${args->btn_hover_style:html}">></a>
			</td>
			${block->x:default(0):arg_name(With close button):arg_section(3, 0, 'Close button', 'close')}
			<td rowspan="2" style="width:1px; white-space:nowrap; ${args->x_style:html:input_type(css):arg_name(Close button position):arg_section(3, 2, 'Close button', 'close')}">
				${args->x:input_type(dontshowagain):input_props('style=cursor:pointer; vertical-align:middle'):arg_name(Close button):arg_section(3, 1, 'Close button', 'close')}
			</td>
		</tr>
		<tr>
			<td data-style="vertical-align:middle; ${args->titledescription_style:html:default('text-align: center; font-family: "Montserrat", sans-serif; font-weight: 400; padding-top: 16px; padding-right: 0px; padding-bottom: 5px; padding-left: 15px; font-size: 12px; line-height: 18px; color: #333;'):input_type(css):input_props('with_responsive=1'):arg_name(Description style):arg_section(2, 5, 'Title', 'bookmark')}">
				${args->titledescription:default(Your description):arg_name(Description text):arg_section(2, 2, 'Title', 'bookmark')}
			</td>
		</tr>
	</table>
	<table style="width:100%; border-collapse:separate; border-spacing:12px 0; margin:0 -12px">
		<tr id="ts" class="$table_slider" data-disabled="${args->with_slider:html:input_type(checkbox):input_props('value_off=1','value_on='):arg_name(Use slider widget):arg_section(1, 4, 'With slider', 'arrow-right'):onchange('if (args.with_slider==1) block.with_arrows = block.pagination = 0')}" style="width: 100%; padding: 0 1%; box-sizing: border-box; border:none; max-width:${args->width:html:default(none):input_type(css_length):input_props('with_options=none'):arg_name(Widget maximum width):arg_section(0, 0, 'Frame', 'th-large')}" for_max_vw="${args->for_max_vw:html:input_type(css_length):input_props('with_options=always'):arg_name(Slider widget only if screen width is less than or equal to):arg_section(1, 5, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" eq_cell_width="${args->eq_cell_width:html:default(1):input_type(checkbox):input_props('value_off=','value_on=1'):arg_name(Equal cell width):arg_section(0, 2, 'Frame', 'th-large')}" arrows_line="${args->arrows_line:html:default(-1):input_type(checkbox):input_props('value_off=-1','value_on=0'):arg_name(Arrows in the middle of images):arg_section(1, 9, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" arrow_back_img="${args->arrow_back_img:html:default('https://cdn.personyze.com/upload/4975/fb528ff235cc14c7.png'):input_type(personyze_media_url):arg_name(Left arrow image):arg_section(1, 6, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" arrow_style="${args->arrow_style:html:default('background-color: rgba(256, 256, 256, 0.63); box-shadow: 0px 1px 6px -1px rgba(0, 0, 0, .3); height: 24px; padding: 4px;'):input_type(css):arg_name(Arrows style):arg_section(1, 7, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" pagination_id="tsp" arrow_back_id="button_back" arrow_forward_id="button_forward" arrows_offset="${args->arrows_offset:html:input_type(number):arg_name(Slider arrows offset):arg_section(1, 8, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" hide_buttons="${args->hide_buttons:html:input_type(checkbox):input_props('value_off=','value_on=1'):arg_name(Hide arrow buttons when nothing to scroll):arg_section(1, 3, 'With slider', 'arrow-right'):visible_if('block.title-0 && block.with_arrows-0')}">
			${foreach sum_articles as p order by p->n_extra desc limit 12}
				<td style="position:relative; padding:0; text-align:center; background-color:white; vertical-align:middle; border:solid ${args->border_color:html:default('rgba(178, 32, 32, 0)'):input_type(color):arg_name(Border color):arg_section(0, 4, 'Frame', 'th-large')} 1px">
					<div data-style="width:${args->img_width:html:default('sel(280px, 45vw)'):input_type(css_length):input_props('with_responsive=1'):arg_name(Cell width):arg_section(0, 3, 'Frame', 'th-large')}">
						<img data-src="${p->image_big_url:html:arg_name(Item image):arg_section(4, 0, 'Image', 'image'):column_tags(image)}" data-style="display: inline-block; vertical-align: middle; width:auto; height:auto; max-width:100%; max-height:${args->img_max_height:html:default('sel(280px, 30vw)'):input_type(css_length):input_props('with_responsive=1'):arg_name(Image maximum height):arg_section(0, 5, 'Frame', 'th-large')}">
						${block->with_label:default(1):arg_name(Label):arg_section(5, 0, 'Label', 'align-justify')}
						<div style="position:absolute; top:0; left:0">
							<div data-style="display:inline-block; ${args->label_style:html:default('font-family: "Montserrat", sans-serif; font-weight: 400; font-size: 12px; margin: 0px; padding: 4px 8px; background-color: #191f32; color: white; border-radius: 3px'):input_type(css):input_props('with_responsive=1'):arg_name(Text style):arg_section(5, 2, 'Label', 'align-justify')}">
								${args->label:default('${p->time_created}&nbsp;-&nbsp;${p->data_last_modified}'):arg_name(Item text):arg_section(5, 1, 'Label', 'align-justify')}
							</div>
						</div>
						<div style="position:absolute; left:0; bottom:40px">
							<div data-style="box-sizing:border-box; ${args->product_title_style:html:default('font-family: "Montserrat", sans-serif; font-weight: 700; font-size: 16px; padding: 4px 12px; text-overflow: clip; overflow: hidden; text-align: left; line-height: 1.25; background-color: rgba(0, 0, 0, 0.5); color: white'):input_type(css):input_props('with_responsive=1'):arg_name(Text style):arg_section(6, 1, 'Text', 'align-justify')}">
								${p->title:arg_name(Item text):arg_section(6, 0, 'Text', 'align-justify')}
							</div>
						</div>
						<div style="position:absolute; left:0; bottom:0">
							<div data-style="display:inline-block; ${args->link_style:html:default('font-family: "Montserrat", sans-serif; font-weight: 700; font-size: 12px; padding: 4px 12px; text-overflow: clip; max-height: 20px; overflow: hidden; text-align: left; background-color: rgba(0, 0, 0, 0.5); color: white'):input_type(css):input_props('with_responsive=1'):arg_name(Link style):arg_section(7, 3, 'Link target URL', 'link')}">
								${args->link:default('Link text &gt;'):arg_name(Link text):arg_section(7, 2, 'Link target URL', 'link')}
							</div>
						</div>
						<a data-personyze-click-target="products ${p->internal_id:html}" href="${p->content_url:html:arg_name(Link target URL):arg_section(7, 0, 'Link target URL', 'link'):column_tags('url','custom text')}" target="${args->target:html:default(_self):input_type(a_target):arg_name(Open link in):arg_section(7, 1, 'Link target URL', 'link')}" style="position:absolute; left:0; top:0; right:0; bottom:0; text-decoration:none;">
						</a>
					</div>
				</td>
			${end}
		</tr>
	</table>
	${block->pagination:default(0):arg_name(With slider pagination):arg_section(1, 10, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}
	<div id="tsp" class="$table_slider_pagination" slider_id="ts" selected_color="${args->pagination_color_on:html:input_type(color):arg_name(Bullet Selected Color):arg_section(1, 11, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" style="${args->pagination_color:html:input_type(css):arg_name(Bullet style):arg_section(1, 12, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}"></div>
</div>
```


## Content widget with rotating image on hover



```
<div class="$responsive" data-style="display:inline-block; position:relative; ${args->style:html:default('border: solid 0px rgb(237, 223, 223);
text-align: left;
font-family: ''Roboto'',sans-serif;
margin-top: 15px;
margin-right: 1px;
margin-bottom: 15px;
margin-left: 1px;
overflow: hidden;
background-size: contain;
')}" onupdate="
	var i, d, a=ns.joyquery('parent::*>tr>td>*', by_id.ts).get();
	for (i=0; d=a[i]; i++) if (d.style.display!='inline-block') if (d._w) d.style.width=d._w;
	for (var d=by_id.ts; d.parentNode!=this; d=d.parentNode);
	var
		p=by_id.ts.parentNode.parentNode,
		w=d.offsetWidth-(parseFloat(p.style.marginLeft) || 0),
		b=parseFloat(p.style.borderSpacing),
		d=a[0].parentNode,
		t=d.offsetWidth,
		n=Math.round((w-b) / (t+b)),
		T=w/n-b-(parseFloat(d.style.borderLeftWidth) || 0)-(parseFloat(d.style.borderRightWidth) || 0);
	for (i=0; d=a[i]; i++) if (d.style.display!='inline-block') d._w=d._w||d.style.width, d.style.width=T+'px'
">
    <link rel="stylesheet" href="https://fonts.googleapis.com/css?family=Open+Sans:400,400i,500,500i,600,600i,700,700i">
	${block->title:default(1)}
	<table data-style="width:100%; border-collapse:collapse; border:none; ${args->title_bg:html}">
		<tr>
			<td data-style="vertical-align:middle; ${args->title_style:html:default('color: #34383c;
font-family: "Open Sans", Arial, sans-serif;
font-size: 3.4rem;
font-weight: normal;
line-height: 3.8rem;
letter-spacing: -0.03em;
padding-top: 22px;
padding-right: 1px;
padding-bottom: 22px;
padding-left: 1px;
')}">
				${args->title:default(Recommended for you)}
			</td>
			${block->with_arrows:default(0)}
			<td style="width:1px; white-space:nowrap; vertical-align:middle">
				<a id="button_back" class="$flat_btn" style="${args->btn_style:html}" hover_style="${args->btn_hover_style:html}"><</a>
				<a id="button_forward" class="$flat_btn" style="${args->btn_style:html}" hover_style="${args->btn_hover_style:html}">></a>
			</td>
			${block->x:default(0)}
			<td style="width:1px; white-space:nowrap; ${args->x_style:html}">
				${args->x}
			</td>
		</tr>
	</table>
	<table data-style="width:100%; border-collapse:separate; border-spacing:12px 8px; margin-bottom:1.2em; height:${args->height:html:default('sel(350px, 300px)')}">
		<tr id="ts" class="$table_slider" data-disabled="${args->with_slider:html}" style="height:100%; border:none; max-width:${args->width:html:default(1080px)}" for_max_vw="${args->for_max_vw:html:default(always)}" eq_cell_width="${args->eq_cell_width:html:default(1)}" arrows_line="${args->arrows_line:html:default(0)}" arrow_back_img="${args->arrow_back_img:html:default('https://static.personyze.com/upload/4545/96b6126f483ffd5a.png')}" arrow_style="${args->arrow_style:html:default('background-color: rgba(256, 256, 256, 0.87);
box-shadow: 0 6px 21px 0 rgba(0,0,0,.09);
')}" pagination_id="tsp" arrow_back_id="button_back" arrow_forward_id="button_forward" arrows_offset="${args->arrows_offset:html:default(0)}" hide_buttons="${args->hide_buttons:html}">
			${foreach recom_articles_viewed_viewed_for_last as p where (p->image_big_url IS NOT NULL AND p->image_big_url!='') limit 12}
				<td data-style="position:relative; height:${args->height:html}; width:${args->img_width:html:default(350px)}; padding:0; text-align:center; box-shadow: 0 0 4px rgba(0,0,0,0.3); background-color:white; border:solid ${args->border_color:html:default(white)} 1px; transition: all .3s ease-in-out" onmouseenter="var i=this.getElementsByTagName('a')[0].getElementsByTagName('img'); if (i[1]) {i[0].style.opacity=0; i[1].style.opacity=1}" onmouseleave="var i=this.getElementsByTagName('a')[0].getElementsByTagName('img'); if (i[1]) {i[0].style.opacity=1; i[1].style.opacity=0}">
					<div data-style="height:100%; width:${args->img_width:html};">
						<a data-personyze-click-target="products ${p->internal_id:html}" href="${args->itemlink:html:default('${p->content_url}')}" target="${args->itemtarget:html:default(_self)}" style="text-decoration: none;">
							<div data-style="position: relative; display: inline-block; height: ${args->img_max_height:html:default('sel(160px, 160px)')}; width: 100%; overflow: hidden;">
								<img data-src="${p->image_big_url:html}" alt="" data-style="position: absolute; left: 50%; top: 50%; height: 100%; opacity: 1; transition: opacity ease 0.4s; transform: translate(-50%,-50%);">
								${if p->image_medium_url != ''}
									${block->with_2_img:default(1)}
									<img data-src="${p->image_big_url:html}" data-style="position: absolute; left: 50%; top: 50%; height: 100%; opacity:0; transition:opacity ease 0.4s; transform: translate(-50%,-50%);">
								${end}
								${block->with_label:default(1)}
								<div data-style="${args->label_style:html:default('position: absolute;
top: 20px;
left: 20px;
padding-top: 2px;
padding-right: 12px;
padding-bottom: 2px;
padding-left: 12px;
height: 22px;
line-height: 22px;
letter-spacing: .025em;
display: inline-block;
font-family: Arial, sans-serif;
font-size: 12px;
text-transform: uppercase;
color: white;
border-radius: 0px;
')}; background-color: ${p->topic:html:replace('product', '#74AB38'):replace('corporate', '#006ec7'):html:default('#74AB38')}; ">${p->topic:replace('product', 'Product'):replace('corporate', 'Corporate'):default(Product)}
								</div>
							</div>
						</a>
						<div data-style="${args->text_style:html:default('max-height: 190px;
height: 190px;
padding-top: 16px;
padding-right: 25px;
padding-bottom: 20px;
padding-left: 25px;
')};">
							<a data-personyze-click-target="products ${p->internal_id:html}" href="${args->itemlink:html}" target="${args->itemtarget:html}" style="display: block; text-decoration: none;" onmouseenter="var t=this; s=t.children[0].style; if (!t._a) t._a=[s.color, '${args->titlemouseover_color:html:default('#006ec7')}']; s.color=t._a[1];" onmouseleave="var s=this.children[0].style, a=this._a; s.color=a[0];">
								<div data-style="${args->name_style:html:default('line-height: 22px;
font-family: ''Open Sans'', Arial, sans-serif;
font-size: 18px;
font-weight: 600;
color: #34383c;
text-align: left;
text-overflow: ellipsis;
overflow: hidden;
display: -webkit-box;
-moz-box-orient: vertical;
-webkit-line-clamp: 4;
-webkit-box-orient: vertical;
line-clamp: 4;
box-orient: vertical;
')}">
								${args->itemtitle:default('${p->title}')}
								</div>
							</a>
							${block->description:default(1)}
							<div data-style="margin:auto; box-sizing:border-box">
								<div data-style="display:inline-block; ${args->a_css_3:html:default('margin-top: 16px;
font-family: Arial, sans-serif;
font-size: 14px;
font-weight: 400;
color: #34383c;
text-align: left;
text-overflow: ellipsis;
overflow: hidden;
display: -webkit-box;
-moz-box-orient: vertical;
-webkit-line-clamp: 4;
-webkit-box-orient: vertical;
line-clamp: 4;
box-orient: vertical;
')}; padding-bottom:0">
									<span style="font-weight: 600" ontplready="this.innerHTML = window._S_T ? window._S_T.ftime.strftime('%B %d, %Y', ${p->publish_date:json:html:unix_timestamp:html}) : '';"></span>
									${args->itemdescription:default('${p->description}')}
								</div>
							</div>
						</div>
						${block->button:default(1)}
						<div>
							<hr style="margin: 0;">
							<a data-personyze-click-target="products ${p->internal_id:html}" href="${args->itemlink:html}" target="${args->itemtarget:html}" data-style="display: block; text-decoration:none; ${args->a_css_4:html:default('padding-top: 8px;
padding-right: 25px;
padding-bottom: 10px;
padding-left: 25px;
font-family: ''Open Sans'', Arial, sans-serif;
font-weight: 600;
font-size: 13px;
text-transform: uppercase;
text-align: right;
letter-spacing: 0.01em;
color: #006ec7;
')} background-color:${args->border_color:html};" onmouseenter="var t=this; s=t.style; if (!t._b) t._b=[s.color, '${args->buttonmouseover_color:html:default('#34383c')}']; s.color=t._b[1];" onmouseleave="var s=this.style, b=this._b; s.color=b[0];">
								${args->button_text:default('Read more&nbsp;&nbsp;<span style="font-size:18px;"><strong>&rsaquo;</strong></span>')}
							</a>
						</div>
					</div>
				</td>
			${end}
		</tr>
	</table>
	${block->pagination:default(0)}
	<div id="tsp" class="$table_slider_pagination" slider_id="ts" selected_color="${args->pagination_color_on:html:default('rgba(0, 0, 0, 1)')}" style="${args->pagination_color:html}"></div>
</div>

${menu name='Frame', icon='th-large'}
	${menu args->width name='Widget maximum width', type='css_length', param='with_options=none'}
	${menu args->height name='Widget maximum height', type='css_length', param='with_responsive=1'}
	${menu args->style name='Style', type='css', param='with_responsive=1'}
	${menu args->eq_cell_width name='Equal cell width', type='checkbox', param='value_off=', param='value_on=1'}
	${menu args->img_width name='Cell width', type='css_length', param='with_responsive=1'}
	${menu args->border_color name='Border color', type='color'}
	${menu args->img_max_height name='Image maximum height', type='css_length', param='with_responsive=1'}
	${menu block->with_2_img name='With 2 Pictures'}
	${menu block->with_label name='With Label'}
	${menu args->label_style name='Label style', type='css', param='with_responsive=1'}
${menu name='With slider', icon='arrow-right'}
	${menu block->with_arrows name='With arrow buttons'}
	${menu args->btn_style name='Arrow button style', type='css'}
	${menu args->btn_hover_style name='Arrow button style: hover', type='css'}
	${menu args->hide_buttons name='Hide arrow buttons when nothing to scroll', type='checkbox', param='value_off=', param='value_on=1', visible_if='block.title-0 && block.with_arrows-0'}
	${menu args->with_slider name='Use slider widget', type='checkbox', param='value_off=1', param='value_on=', onchange='if (args.with_slider==1) block.with_arrows = block.pagination = 0'}
	${menu args->for_max_vw name='Slider widget only if screen width is less than or equal to', type='css_length', param='with_options=always', visible_if='args.with_slider!=1'}
	${menu args->arrow_back_img name='Left arrow image', type='personyze_media_url', visible_if='args.with_slider!=1'}
	${menu args->arrow_style name='Arrows style', type='css', visible_if='args.with_slider!=1'}
	${menu args->arrows_offset name='Slider arrows offset', type='number', visible_if='args.with_slider!=1'}
	${menu args->arrows_line name='Arrows in the middle of images', type='checkbox', param='value_off=-1', param='value_on=0', visible_if='args.with_slider!=1'}
	${menu block->pagination name='With slider pagination', visible_if='args.with_slider!=1'}
	${menu args->pagination_color_on name='Bullet Selected Color', type='color', visible_if='args.with_slider!=1'}
	${menu args->pagination_color name='Bullet style', type='css', visible_if='args.with_slider!=1'}
${menu name='Title', icon='bookmark'}
	${menu block->title name='With title bar'}
	${menu args->title name='Text'}
	${menu args->title_bg name='Style', type='css', param='with_responsive=1'}
	${menu args->title_style name='Title style', type='css', param='with_responsive=1'}
${menu name='Close button', icon='close'}
	${menu block->x name='With close button'}
	${menu args->x name='Close button', type='dontshowagain', param='style=cursor:pointer; vertical-align:middle'}
	${menu args->x_style name='Close button position', type='css'}
${menu name='Text', icon='align-justify'}
	${menu args->text_style name='Block style', type='css', param='with_responsive=1'}
	${menu block->description name='With description'}
	${menu args->itemtitle name='Name text'}
	${menu args->name_style name='Name text style', type='css', param='with_responsive=1'}
	${menu args->titlemouseover_color name='Text color when mouse over', type='color'}
	${menu args->itemdescription name='Description text'}
	${menu args->a_css_3 name='Description style', type='css', param='with_responsive=1'}
${menu name='Link target URL', icon='link'}
	${menu args->itemlink name='Link target URL'}
	${menu args->itemtarget name='Open link in', type='a_target'}
${menu name='Second line', icon='text-height'}
	${menu block->button name='With button'}
	${menu args->button_text name='Button text'}
	${menu args->a_css_4 name='Button style', type='css', param='with_responsive=1'}
	${menu args->buttonmouseover_color name='Text color when mouse over', type='color'}
```


## Gallery view



```
<div class="$responsive $a_add_params" data-style="display:inline-block; position:relative; ${args->style:html:default('width: 100%;
margin-top: 40px;
margin-right: 0px;
margin-bottom: 1px;
margin-left: 0px;
padding: 0;
border: none;
text-align: left;
box-sizing: border-box;
box-shadow: 0 0px 0px 0 rgba(0,0,0,0.08);
background-color: rgba(255, 255, 255, 1);'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(0, 0, 'Frame', 'th-large')}; direction:${args->direction:html:default(ltr):input_type(select):input_props('options=[["Left to right","ltr"],["Right to left","rtl"]]'):arg_name(Localization settings):arg_section(0, 1, 'Frame', 'th-large')};" data-json-params="${args->url_params:html:default('[]'):input_type(external_media_url_params):arg_name(URL additional parameters):arg_section(0, 2, 'Frame', 'th-large')}">
	<link href="https://fonts.googleapis.com/css2?family=Poppins:ital,wght@0,400;0,600;0,700;1,400;1,600;1,700&display=swap" rel="stylesheet">
	<style>
		@media (max-width:599px) {
			.item {
				display: block;
			}
		}
	</style>
	${block->with_title:default(1):arg_name(With title):arg_section(1, 0, 'Title', 'bookmark')}
	<div data-style="border-width: 0 0 1px 0; border-style: solid; border-color: #e1e1e1;">
		<div data-style="${args->title_style:html:default('text-align: left; font-family: Poppins,Helvetica,Arial,sans-serif; font-size: 18px; font-weight: 700; text-transform: capitalize; color: rgb(0, 0, 0);'):input_type(css):input_props('with_responsive=1'):arg_name(Title style):arg_section(1, 3, 'Title', 'bookmark')}">
			${args->title:default(Your title):arg_name(Title text):arg_section(1, 1, 'Title', 'bookmark')}
		</div>
		<div data-style="${args->description_style:html:default('text-align: left; font-family: Poppins,Helvetica,Arial,sans-serif; font-size: 14px; font-weight: 400; color: rgb(0, 0, 0);'):input_type(css):input_props('with_responsive=1'):arg_name(Description style):arg_section(1, 4, 'Title', 'bookmark')}">
			${args->desription:default(Your description):arg_name(Description text):arg_section(1, 2, 'Title', 'bookmark')}
		</div>
	</div>

	${block->x:default(0):arg_name(With close button):arg_section(3, 0, 'Close button', 'close')}
	<div style="${args->x_style:html:input_type(css):arg_name(Close button position):arg_section(3, 2, 'Close button', 'close')}">
		${args->x:input_type(dontshowagain):input_props('style=cursor:pointer; vertical-align:middle'):arg_name(Close button):arg_section(3, 1, 'Close button', 'close')}
	</div>

	<table data-style="width: 100%; border: 0; border-collapse: collapse; margin-top: 3%;">
		<tr class="$to_some_columns" column_count="2">
			${foreach articles as p where (p->image_big_url IS NOT NULL AND p->image_big_url!='') order by p->time_created desc limit 6}
				<td data-style="display: sel(table-cell, block); ${if p->row_number % 2 = 0} width: sel(48%, 100%); ${end} ${if p->row_number % 2 != 0} width: sel(52%, 100%); padding-right: sel(4%, 0); ${end} padding-bottom: 3%; box-sizing: border-box;">
					<table style="width: 100%">
						<tr>
							<td data-style="${args->column1_style:html:default('width: 70%; vertical-align: top; padding-right: 5%;'):input_type(css):input_props('with_responsive=1'):arg_name(Column 1 style):arg_section(2, 0, 'Item', 'th-large')}">
								<a data-personyze-click-target="products ${p->internal_id:html}" href="${p->cart_url:html:arg_name(Link target URL):arg_section(2, 9, 'Item', 'th-large'):column_tags('url','custom text')}" target="${args->target:html:default(_self):input_type(a_target):arg_name(Open link in):arg_section(2, 10, 'Item', 'th-large')}" data-style="${args->itemtitle_style:html:default('display: block; margin: 10px 0; font-family: Poppins,Helvetica,Arial,sans-serif; font-size: 16px; font-weight: 700; line-height: 1.4em; text-transform: capitalize; text-decoration: none; color: rgb(0, 0, 0);'):input_type(css):input_props('with_responsive=1'):arg_name(Item title style):arg_section(2, 3, 'Item', 'th-large')}">
									${args->itemtitle_text:default('${p->title}'):arg_name(Item title):arg_section(2, 2, 'Item', 'th-large')}
								</a>
								${block->with_publishdate:default(1):arg_name(With publish date):arg_section(2, 4, 'Item', 'th-large')}
								<a data-personyze-click-target="products ${p->internal_id:html}" href="${p->cart_url:html}" target="${args->target:html}" data-style="${args->publishdate_style:html:default('display: block; margin-bottom: 10px; font-family: Poppins,Helvetica,Arial,sans-serif; font-size: 11px; font-weight: 600; text-transform: capitalize; text-decoration: none; color: rgb(0, 122, 255);'):input_type(css):input_props('with_responsive=1'):arg_name(Publish date style):arg_section(2, 5, 'Item', 'th-large')}" ontplready="this.innerHTML = '&#9716; ' + (window._S_T ? window._S_T.ftime.strftime('%B %d, %Y', ${p->publish_date:json:html:unix_timestamp}) : '');"></a>
							</td>
							<td data-style="position: relative; ${args->column2_style:html:default('width: 30%; padding-bottom: 30%; text-align: right; vertical-align: top;'):input_type(css):input_props('with_responsive=1'):arg_name(Column 2 style):arg_section(2, 1, 'Item', 'th-large')}" onmouseenter="var i=this.getElementsByTagName('a')[0].getElementsByClassName('image'); if (i[1]) {i[0].style.opacity=0; i[1].style.opacity=1}" onmouseleave="var i=this.getElementsByTagName('a')[0].getElementsByClassName('image'); if (i[1]) {i[0].style.opacity=1; i[1].style.opacity=0}">
								<a data-personyze-click-target="products ${p->internal_id:html}" href="${p->cart_url:html}" target="${args->target:html}" style="text-decoration: none;">
									<div class="image" data-style="position: absolute; top:0; left:0; width: 100%; height:100%; background-image: url(${p->image_big_url:html}); background-size: cover; background-position: center center; background-repeat: no-repeat; border-radius: 5px; opacity: 1; transition: opacity ease 0.4s;"></div>
									${if p->image_medium_url != ''}
										${block->with_2_img:default(1):arg_name(With 2 Pictures):arg_section(2, 6, 'Item', 'th-large')}
										<div class="image" data-style="position: absolute; top:0; left:0; width: 100%; height:100%; background-image: url(${p->image_medium_url:html}); background-size: cover; background-position: center center; background-repeat: no-repeat; border-radius: 5px; opacity: 0; transition: opacity ease 0.4s;"></div>
									${end}
									${if p->custom_1 != ''}
										${block->with_label:default(1):arg_name(With label):arg_section(2, 7, 'Item', 'th-large')}
										<div data-style="${args->label_style:html:default('position: absolute; left: 10%; top: 10%; width: 32px; height: 32px; line-height: 32px; text-align: center; border-radius: 50%; color: white;'):input_type(css):input_props('with_responsive=1'):arg_name(Label style):arg_section(2, 8, 'Item', 'th-large')}; background-color: ${p->custom_1:html:replace('light', '#007afe'):replace('fire', '#ff3b30'):default('rgba(0, 0, 0, 0)')};">
											${p->custom_1:replace('light', '&#9889;'):replace('fire', '&#128293;')}
										</div>
									${end}
								</a>
							</td>
						</tr>
					</table>
				</td>
			${end}
		</tr>
	</table>
</div>
```


## Slider



```
<div class="$responsive $a_add_params" data-style="display:inline-block; position:relative; ${args->style:html:default('padding: 0px;
border: none;
margin: auto;
width: 100%;
display: block;
')}; direction: ${args->direction:html:default(ltr)};" data-json-params="${args->url_params:html}">

    ${block->title:default(1)}
    <table data-style="border-collapse:collapse; border:none; width:100%; ${args->title_bg:html:default('margin: 22px;
')}">
        <tr>
            <td data-style="vertical-align:middle; ${args->title_style:html:default('text-align: center;
font-size: sel(22px, 18px);
font-weight: 700;
line-height: sel(18px, 18px);
color: #383838;
padding-top: 10px;
padding-right: sel(15px, 1px);
padding-bottom: 5px;
padding-left: 0px;
text-transform: uppercase;
max-width: 100%;
width: 100%;
')}">
                ${args->title:default('You may like&nbsp;')}
            </td>
            ${block->with_arrows:default(0)}
            <td style="width:1px; white-space:nowrap; vertical-align:middle">
                <a id="button_back" class="$flat_btn" href="javascript:" style="${args->btn_style:html}" hover_style="${args->btn_hover_style:html}"><</a>
                <a id="button_forward" class="$flat_btn" href="javascript:" style="${args->btn_style:html}" hover_style="${args->btn_hover_style:html}">></a>
            </td>
            ${block->x:default(0)}
            <td style="width:1px; white-space:nowrap; ${args->x_style:html}">
                ${args->x:default('<svg viewBox="0 0 24 24" width="32" height="32" enable-background="new 0 0 24 24" fill="#000" class="$personyze_button_dont_show_again" data-action_id="${action_id}"><path d="M12.0119629,2.0039062C6.491272,2.0006104,2.0131836,6.4733276,2.0098877,11.9940186S6.4793091,21.9927979,12,21.9960938c2.6522827,0.0043335,5.1970215-1.0482178,7.0712891-2.9248047c1.875-1.8734131,2.9291992-4.4147949,2.9307861-7.0653076C22.0053711,6.4852905,17.5326538,2.0072021,12.0119629,2.0039062z M12.0122681,20.9960938c-4.9684448,0.0033569-8.9988403-4.0215454-9.0022583-8.9899902C3.0066528,7.0377197,7.0316162,3.0072632,12,3.0039062c2.387085-0.0042725,4.6774292,0.9428711,6.3642578,2.6318359c1.687439,1.6858521,2.6363525,3.9728394,2.6379395,6.3581543C21.0056152,16.9622803,16.9806519,20.9926758,12.0122681,20.9960938z M12.7069702,12l3.1816406-3.1816406c0.1905518-0.194397,0.1905518-0.5054932,0-0.6998901c-0.1932373-0.1972046-0.5097656-0.2003784-0.7069702-0.0071411L12,11.2929688L8.8183594,8.1113892c-0.194397-0.1904907-0.5054932-0.1904907-0.6998901,0C7.9212646,8.3046265,7.9180908,8.6211548,8.1113281,8.8183594L11.2929688,12l-3.1816406,3.1816406c-0.09375,0.09375-0.1463623,0.2208862-0.1464233,0.3534546c0,0.276123,0.2238159,0.5,0.499939,0.500061c0.1326294,0.0001831,0.2598877-0.0525513,0.3535156-0.1464844L12,12.7070312l3.1816406,3.1816406c0.0936279,0.0939331,0.2208862,0.1466675,0.3535156,0.1464844v0.000061c0.1325684-0.000061,0.2596436-0.0527344,0.3533936-0.1464233c0.1953125-0.1952515,0.1953125-0.5118408,0.000061-0.7071533L12.7069702,12z"/></svg>')}
            </td>
        </tr>
    </table>
    <table data-style="height:10px; width:auto; border-collapse: separate; border-spacing: ${args->space_between_items:html:default(14px)} 0; margin:0 -${args->space_between_items:html}">
        <tr id="ts" class="$table_slider" data-disabled="${args->with_slider:html}" data-hover_add_class="st-td-hover" data-round="${args->round:html:default(1)}" data-with_scrollbar="${args->with_scrollbar:html}" data-scrollbar_style="${args->scrollbar_style:html:default('background-color: #D8D8D8;
color: #999999;
height: 12px;
')}" data-hide_scrollbar="${args->hide_scrollbar:html}" style="width: 100%; box-sizing: border-box; border:none" for_max_vw="${args->for_max_vw:html:default(always)}" eq_cell_width="${args->eq_cell_width:html:default(1)}" eq_cell_height="${args->eq_cell_height:html:default(1)}" arrows_line="${args->arrows_line:html:default(-1)}" arrow_back_img="${args->arrow_back_img:html:default('<svg viewBox="0 0 54 54" width="24" height="24"><path style="fill:#4FBA6F" d="M27,1L27,1c14.359,0,26,11.641,26,26v0c0,14.359-11.641,26-26,26h0C12.641,53,1,41.359,1,27v0 C1,12.641,12.641,1,27,1z"/><path style="fill:#4FBA6F" d="M27,54C12.112,54,0,41.888,0,27S12.112,0,27,0s27,12.112,27,27S41.888,54,27,54z M27,2 C13.215,2,2,13.215,2,27s11.215,25,25,25s25-11.215,25-25S40.785,2,27,2z"/><path style="fill:#FFFFFF" d="M31.706,40c-0.256,0-0.512-0.098-0.707-0.293L19.501,28.209c-0.667-0.667-0.667-1.751,0-2.418 l11.498-11.498c0.391-0.391,1.023-0.391,1.414,0s0.391,1.023,0,1.414L21.12,27l11.293,11.293c0.391,0.391,0.391,1.023,0,1.414 C32.218,39.902,31.962,40,31.706,40z"/></svg>')}" arrow_style="${args->arrow_style:html:default('background-color: rgba(219, 195, 195, 0);
max-height: none;
padding-top: 0px;
padding-right: 2px;
padding-bottom: 0px;
padding-left: 2px;
width: auto;
')}" pagination_id="tsp" arrow_back_id="button_back" arrow_forward_id="button_forward" arrows_offset="${args->arrows_offset:html:default(-8)}" hide_buttons="${args->hide_buttons:html}" buttons_always="${args->buttons_always:html:default(1)}">
            ${foreach articles as p where (p->image_big_url IS NOT NULL AND p->image_big_url!='') order by p->time_created desc union articles where (p->image_big_url IS NOT NULL AND p->image_big_url!='') order by p->time_created desc limit 10}
                <td style="position:relative; padding:0; text-align:center; background-color:white; vertical-align:top; border:solid ${args->border_color:html:default('#dddddd')} 1px">
                    <a data-personyze-click-target="articles ${p->internal_id:html}" href="${p->content_url:html}" target="${args->target:html:default(_self)}" data-style="position:relative; display:block; margin:auto; box-sizing:border-box; overflow: hidden; width:${args->img_width:html:default('sel(300px, 44vw)')}; padding: ${args->img_max_height:html:default('sel(209px, 120px)')} 0 0 0; text-decoration: none;">
                        <div data-style="position: absolute; left: 0; top: 0; right: 0; bottom: 0; margin: 8px; max-width: 100%; max-height: 100%; background-image:url('${p->image_big_url:html}'); background-repeat:no-repeat; background-position:center; background-size:contain; transition:background-size ease 0.3s">
                            ${block->with_zoom_image:default(0)}
                            <span data-z="${args->zoom:html:default(110)}" data-l="${args->landscape:html}" ontplready="var p=this.parentNode, n=this.dataset.l ? '100% auto' : 'auto 100%', y=n.replace('100%', this.dataset.z+'%'); p.style.backgroundSize=n; p.onmouseenter=function() {this.style.backgroundSize=y}; p.onmouseleave=function() {this.style.backgroundSize=n}"></span>
                        </div>

                        ${block->with_hover_image:default(1)}
                        <span>
                            ${if p->image_medium_url <> ''}
                                <div data-style="position: absolute; left: 0; top: 0; right: 0; bottom: 0; margin: 8px; max-width: 100%; max-height: 100%; background-image:url('${p->image_medium_url:html}'); background-repeat:no-repeat; background-position:center; background-size:contain; opacity:0; transition:opacity ease 0.3s" onmouseenter="this.style.opacity=1" onmouseleave="this.style.opacity=0">
                                </div>
                            ${end}
                        </span>

                        ${block->with_new_badge:default(1)}
                        <span>
                            ${if unix_timestamp() - p->time_created <= args->badge_if_newer:default(2851200)}
                                <div data-style="position: absolute; ${args->new_badge_style:html:default('top: 0;
left: 48px;
font-size: 14px;
text-shadow: rgba(255,255,255,0.5) 0px 3px 3px;
background-color: rgb(50, 101, 219);
color: rgb(250, 246, 246);
display: flex;
justify-content: center;
align-items: center;
padding: 0.3em;
')}">
                                    <span data-style="${args->new_badge_text_style:html:default('font-size: 16px;
font-weight: 600;
')}">${args->new_badge_text:default(NEW)}</span>
                                </div>
                            ${end}
                        </span>

                        ${block->with_time_badge:default(0)}
                        <span>
                            ${if p->custom_i_1 - unix_timestamp() >= 0}
                                <div data-style="position: absolute; ${args->time_badge_style:html:default('top: 0;
left: 48px;
font-size: 14px;
text-shadow: rgba(255,255,255,0.5) 0px 3px 3px;
background-color: rgb(50, 101, 219);
color: rgb(250, 246, 246);
display: flex;
justify-content: center;
align-items: center;
padding: 0.3em;
')}">
                                    <span data-style="${args->time_badge_text_style:html:default('font-size: 16px;
font-weight: 600;
')}">${args->time_badge_text:default(Special offer till)}</span>
                                    ${block->with_time_badge_countdown}
                                    <span data-end="${p->custom_i_1:html- unix_timestamp()}" data-d="${args->time_badge_days:html:default(days)}" data-h="${args->time_badge_hr:html:default(hr)}" data-m="${args->time_badge_min:html:default(min)}" data-s="${args->time_badge_sec:html:default(sec)}" ontplready="var t=this, end=t.dataset.end|0, d=t.dataset.d, h=t.dataset.h, m=t.dataset.m, s=t.dataset.s; (function p() {var r=end-new Date().getTime()/1000; t.parentNode.parentNode.style.display = r<=0 ? 'none' : ''; t.textContent = ns.sec_to_span(r - r%(r >= 3*24*60*60 ? 24*60*60 : r > 24*60*60 ? 60*60 : 1), s, m, h, d); if (r <= 24*60*60) setTimeout(p, 1000)})()"></span>
                                </div>
                            ${end}
                        </span>

                        ${block->with_wishlist_badge:default(0)}
                        <span class="$switch-elem"
                            data-case="${foreach articles_interactions as w where w->internal_id = p->internal_id and w->interaction_status = 'favorite' limit 1}on${end}"
                            data-p="${p->internal_id:html}"
                            data-style="position:absolute; transition: all 0.3s ease; ${args->wishlist_style:html:default('top: 5px;
right: 5px;
color: rgb(119, 181, 115);
font-size: 25px;
')}"
                            onclick="var on=this._get_case(); _S_T.push([on ? 'Article Unliked' : 'Article Liked', this.dataset.p]); this._set_case(on ? '' : 'on'); event.stopPropagation(); event.preventDefault()"
                        >
                            <div data-case="" class="$hint" style="${args->wishlist_off_style:html}">
                                <span data-content="1">${args->wishlist_add_text:default(Add to wishlist)}</span>
                                <hr class="$icon heart-o">
                            </div>
                            <div data-case="on" class="$hint" style="${args->wishlist_on_style:html:default('background-color: rgba(177, 93, 93, 0);
')}">
                                <span data-content="1">${args->wishlist_rm_text:html:default(Remove from wishlist)}</span>
                                <hr class="$icon heart">
                            </div>
                        </span>

						${block->with_db_badge:default(1)}
						<span>
							<div data-style="position: absolute; ${args->db_badge_style:html:default('top: 0;
left: 0px;
font-size: 14px;
text-shadow: rgba(255,255,255,0.5) 0px 3px 3px;
background-color: rgb(50, 101, 219);
color: rgb(250, 246, 246);
display: flex;
justify-content: center;
align-items: center;
padding: 0.3em;
')}">
								${block->with_db_badge_icon:default(1)}
								<hr class="$icon ${args->db_badge_text_icon:html:default(bookmark)}">
								<span data-style="${args->db_badge_text_style:html:default('font-size: 16px;
font-weight: 600;
')}">${args->db_badge_text:default('${p->topic}&nbsp;Select variable&nbsp;')}</span>
							</div>
						</span>
                    </a>
                    <a data-personyze-click-target="articles ${p->internal_id:html}" href="${p->content_url:html}" target="${args->target:html}" data-style="display:block; margin:auto; box-sizing:border-box; width:${args->img_width:html}; text-decoration:none">
                        <div data-style="${args->a_css:html:default('padding: 1px;
text-transform: none;
color: black;
font-weight: 400;
font-size: 18px;
margin: 10px;
text-align: center;
line-height: 1.3;
max-height: 5.2em;
overflow: hidden;
min-height: 3.5em;
')}; position:relative" data-max-lines="3" ontplready="
var that = this;
if (window.ResizeObserver) new ResizeObserver(function() {
    that.lastElementChild.style.display = that.scrollHeight>that.offsetHeight ? '' : 'none';
}).observe(this)" onmouseover="this.dataset.c = this.style.color; this.style.color = '${args->a_css_onhover:html:default('#F69442')}'" onmouseleave="this.style.color = this.dataset.c">
                            ${p->topic}
                            <div style="display:none; position:absolute; bottom:0; left:0; background-color:white">…</div>
                        </div>
                    </a>

					${block->with_date:default(1)}
					<div style="${args->date_column_style:html:default('padding-top: 0;
padding-right: 0;
padding-bottom: 1em;
padding-left: 0;
font-weight: 600;
')}" ontplready="this.innerHTML = window._S_T ? _S_T.ftime.strftime('${args->date_column_format:html:default('%B %d, %Y')}', ${args->date_column:html:default('${p->data_last_modified}')}) : '';"></div>

                    ${block->rating:default(0)}
                    <span>
                        <hr class="$rating" data-value="${p->rank:html:default(0)}" style="${args->rating_style:html:default('color: yellow;
--bgcolor: white;
--border-color: rgba(225, 214, 214, 0.87);
width: 10em;
height: 1.8em;
')}">
                    </span>

                    ${block->stats_1day:default(1)}
					<div style="${args->text_style_1day:html:default('padding-top: 1em;
padding-right: 0;
padding-bottom: 1em;
padding-left: 0;
font-weight: 600;
')}">
						${foreach sum_articles_1day as s where s->internal_id = p->internal_id limit 1}
							${args->n_viewed_1day:default('${s->n_viewed*1} viewed today ${if s-&gt;n_goal &gt; 0}
<div>${s->n_goal*1}&nbsp; downloads today</div>
${end}')}
							<span ontplready="this._v='${s->n_viewed:html}'|0; this._g='${s->n_goal:html}'|0"></span>
						${end}
						${block->hide_no_view_1day:default(1)}
						<span ontplready="var p=this.previousElementSibling||{}; if (ns==window._S_T) if ((p._v|0) < ('${args->hide_no_view_1day:html:default(3)}'|0) || (p._g|0) < ('${args->hide_no_goal_1day:html:default(1)}'|0)) this.parentNode.style.display='none'"></span>
					</div>

					${block->stats_week:default(0)}
					<div style="${args->text_style_week:html:default('padding:1em 0')}">
						${foreach sum_articles_week as s where s->internal_id = p->internal_id limit 1}
							${args->n_viewed_week:default('<span style="font-size:14px;">This article has been popular in the last week!</span><br />
&nbsp;
<div><span style="color:#fac200;"><strong>${s->n_viewed*1} viewed</strong></span></div>
${if s-&gt;n_goal &gt; 0}

<div><span style="color:#fac200;"><strong>${s->n_goal*1} downloads</strong></span></div>
${end}')}
							<span ontplready="this._v='${s->n_viewed:html}'|0; this._g='${s->n_goal:html}'|0"></span>
						${end}
						${block->hide_no_view_week}
						<span ontplready="var p=this.previousElementSibling||{}; if (ns==window._S_T) if ((p._v|0) < ('${args->hide_no_view_week:html}'|0) || (p._g|0) < ('${args->hide_no_goal_week:html}'|0)) this.parentNode.style.display='none'"></span>
					</div>

                    <div style="clear:left;"></div>
                    <div style="margin:auto; box-sizing:border-box; font-size:1px">
                        <div data-style="display:inline-block; background-color:${args->border_color:html}; ${args->a_css_2:html:default('width: 100px;
height: 0px;
max-width: 80%;
')}"></div>
                    </div>
                    ${block->description:default(0)}
                    <div data-style="margin:auto; box-sizing:border-box; width:${args->img_width:html}">
                        <div data-style="display:inline-block; ${args->a_css_3:html}; padding-bottom:0">
                            ${p->description}
                        </div>
                    </div>

                    ${block->with_link_button:default(1)}
                    <div data-style="box-sizing:border-box; ${args->link_button_box_style:html:default('text-align: center;
')}">
                        <a class="$flat_btn" href="${args->link_button_href:html:default('${p->content_url}')}" data-style="box-sizing:border-box; ${args->link_button_style:html:default('color: rgb(39, 36, 70);
padding-top: 9px;
padding-right: 13px;
padding-bottom: 9px;
padding-left: 13px;
font-size: 14px;
line-height: 14px;
font-weight: 700;
font-family: Lato;
margin: 15px;
background-color: rgba(245, 36, 36, 0);
width: auto;
')}" hover_style="${args->link_button_style_hover:html:default('color: rgb(7, 3, 3);
padding-top: 9px;
padding-right: 13px;
padding-bottom: 9px;
padding-left: 13px;
font-size: 14px;
line-height: 14px;
font-weight: 700;
font-family: Lato;
transition: none;
margin: 15px;
background-color: rgb(237, 238, 227);
width: auto;
')}">
                            ${args->link_button_text:default('Read more &gt;&gt;')}
                        </a>
                    </div>
                </td>
            ${end}
        </tr>
    </table>
    ${block->pagination:default(0)}
    <div id="tsp" class="$table_slider_pagination" slider_id="ts" selected_color="${args->pagination_color_on:html:default('rgba(0, 0, 0, 1)')}" style="${args->pagination_color:html}"></div>
</div>

${menu name='Frame', icon='th-large'}
	${menu args->style name='Style', type='css', param='with_responsive=1'}
	${menu args->round name='No cut cell', type='checkbox', param='value_off=', param='value_on=1'}
	${menu args->eq_cell_width name='Equal cell width', type='checkbox', param='value_off=', param='value_on=1'}
	${menu args->eq_cell_height name='Equal cell height', type='checkbox', param='value_off=', param='value_on=1'}
	${menu args->space_between_items name='Space between items', type='css_length', param='with_responsive=1'}
	${menu args->border_color name='Border color', type='color'}
	${menu args->direction name='Localization settings', type='select', param='options=[["Left to right","ltr"],["Right to left","rtl"]]'}
	${menu args->url_params name='URL additional parameters', type='external_media_url_params'}
${menu name='Slider options', icon='arrow-right'}
	${menu block->with_arrows name='With arrow buttons'}
	${menu args->btn_style name='Arrow button style', type='css'}
	${menu args->btn_hover_style name='Arrow button style: hover', type='css'}
	${menu args->hide_buttons name='Hide arrow buttons when nothing to scroll', type='checkbox', param='value_off=', param='value_on=1', visible_if='block.title-0 && block.with_arrows-0'}
	${menu args->buttons_always name='Show arrows even when mouse doesn''t hover', type='checkbox', param='value_off=', param='value_on=1', visible_if='!(block.with_arrows-0)'}
	${menu args->with_slider name='Use slider widget', type='checkbox', param='value_off=1', param='value_on=', onchange='if (args.with_slider==1) block.with_arrows = block.pagination = 0'}
	${menu args->with_scrollbar name='Slider with scrollbar', type='checkbox', param='value_off=', param='value_on=1', visible_if='args.with_slider!=1'}
	${menu args->hide_scrollbar name='Hide scrollbar', type='checkbox', param='value_off=', param='value_on=1', visible_if='args.with_slider!=1 && args.with_scrollbar==1'}
	${menu args->scrollbar_style name='Scrollbar style', type='css', visible_if='args.with_slider!=1 && args.with_scrollbar==1'}
	${menu args->for_max_vw name='Slider widget only if screen width is less than or equal to', type='css_length', param='with_options=always', visible_if='args.with_slider!=1'}
	${menu args->arrow_back_img name='Left arrow image', type='arrow', visible_if='args.with_slider!=1'}
	${menu args->arrow_style name='Arrows style', type='css', visible_if='args.with_slider!=1'}
	${menu args->arrows_offset name='Slider arrows offset', type='number', visible_if='args.with_slider!=1'}
	${menu args->arrows_line name='Arrows in the middle of images', type='checkbox', param='value_off=-1', param='value_on=0', visible_if='args.with_slider!=1'}
	${menu block->pagination name='With slider pagination', visible_if='args.with_slider!=1'}
	${menu args->pagination_color_on name='Bullet Selected Color', type='color', visible_if='args.with_slider!=1'}
	${menu args->pagination_color name='Bullet style', type='css', visible_if='args.with_slider!=1'}
${menu name='Widget title', icon='bookmark'}
	${menu block->title name='With title bar'}
	${menu args->title name='Text'}
	${menu args->title_bg name='Style', type='css', param='with_responsive=1'}
	${menu args->title_style name='Title style', type='css', param='with_responsive=1'}
${menu name='Close button', icon='close'}
	${menu block->x name='With close button'}
	${menu args->x name='Close button', type='dontshowagain', param='style=cursor:pointer; vertical-align:middle'}
	${menu args->x_style name='Close button position', type='css'}
${menu name='Image/Cell width', icon='image'}
	${menu args->img_width name='Cell width', type='css_length', param='with_responsive=1'}
	${menu args->img_max_height name='Image maximum height', type='css_length', param='with_responsive=1'}
	${menu p->image_big_url name='Item image', column_tags='image'}
${menu name='Zoom image on hover', icon='bars'}
	${menu block->with_zoom_image name='Zoom image on hover', onchange='block.with_hover_image=block.with_zoom_image^1||""'}
	${menu args->zoom name='Zoom %', type='number'}
	${menu args->landscape name='Orientation of each item image is landscape', type='checkbox', param='value_off=', param='value_on=1'}
${menu name='Hover alternative image', icon='image', description='On mouse hover, show additional item images when available on the article feed.'}
	${menu block->with_hover_image name='With hover image', onchange='block.with_zoom_image=block.with_hover_image^1||""'}
	${menu p->image_medium_url name='Hover image', column_tags='image'}
${menu name='New badge', icon='align-justify', description='Set "New" badge to appear for items debut recently.
You may choose a time frame for an article to be considered new. For new accounts/articles feed, all articles are new until the day setting condition has been met.'}
	${menu block->with_new_badge name='With new badge'}
	${menu args->badge_if_newer name='Show NEW badge if newer than', type='date', param='is_span=true', param='format=%0..999d days'}
	${menu args->new_badge_style name='Badge style', type='css', param='with_responsive=1'}
	${menu args->new_badge_text_style name='Badge text style', type='css', param='with_responsive=1'}
	${menu args->new_badge_text name='Text'}
${menu name='Time-based badge', icon='align-justify'}
	${menu block->with_time_badge name='With time-based badge'}
	${menu args->time_badge_style name='Badge style', type='css', param='with_responsive=1'}
	${menu args->time_badge_text_style name='Badge text style', type='css', param='with_responsive=1'}
	${menu args->time_badge_text name='Text'}
	${menu p->custom_i_1 name='Catalog field with end date', description='UNIX-timestamp'}
	${menu block->with_time_badge_countdown name='With days/time remaining'}
	${menu args->time_badge_days name='Time remaining: "days" text'}
	${menu args->time_badge_hr name='Time remaining: "hours" text'}
	${menu args->time_badge_min name='Time remaining: "minutes" text'}
	${menu args->time_badge_sec name='Time remaining: "seconds" text'}
${menu name='Add to wishlist', icon='bars', description='Show save to wishlist icon, on click item will be saved to Personyze wishlist. Items can be included in email/site widgets when using the wishlist algorithm. You can also set JS to report to your site when a visitor is saving an item to a wishlist.'}
	${menu block->with_wishlist_badge name='With add to wishlist'}
	${menu args->wishlist_style name='Style', type='css'}
	${menu args->wishlist_off_style name='Off icon style', type='css'}
	${menu args->wishlist_add_text name='Off tooltip (add to wishlist)'}
	${menu args->wishlist_on_style name='On icon style', type='css'}
	${menu args->wishlist_rm_text name='On tooltip (remove from wishlist)'}
${menu name='Icon or text badge', icon='star', description='Show text taken from catalog field'}
	${menu block->with_db_badge name='With db badge'}
	${menu args->db_badge_style name='Block style', type='css'}
	${menu block->with_db_badge_icon name='With icon'}
	${menu args->db_badge_text_icon name='Icon', type='icon'}
	${menu args->db_badge_text_style name='Icon style', type='css'}
	${menu args->db_badge_text name='Text'}
${menu name='Article text/desc', icon='align-justify'}
	${menu block->description name='With description'}
	${menu p->topic name='Item text'}
	${menu p->description name='Item text'}
	${menu args->a_css name='Text style', type='css', param='with_responsive=1'}
	${menu args->a_css_onhover name='Text on hover color', type='color', param='with_responsive=1'}
	${menu args->a_css_3 name='Text color', type='css', param='with_responsive=1'}
	${menu args->a_css_2 name='Ruler', type='css', param='with_responsive=1'}
${menu name='Link button', icon='mouse-pointer'}
	${menu block->with_link_button name='With link button'}
	${menu args->link_button_href name='Link target URL'}
	${menu args->link_button_text name='Button text'}
	${menu args->link_button_box_style name='Box style', type='css', param='with_responsive=1'}
	${menu args->link_button_style name='Button style', type='css'}
	${menu args->link_button_style_hover name='Button hover style', type='css'}
${menu name='Onclick target URL', icon='link'}
	${menu p->content_url name='Link target URL', column_tags='url, custom text'}
	${menu args->target name='Open link in', type='a_target'}
${menu name='Date', icon='calendar', description='Show date.'}
	${menu block->with_date name='With rating'}
	${menu args->date_column name='Date column'}
	${menu args->date_column_format name='Date format'}
	${menu args->date_column_style name='Style', type='css'}
${menu name='Rating', icon='star', description='Show article rating when available
This requires you to populate "Rank" on your article feed.'}
	${menu block->rating name='With rating'}
	${menu p->rank name='Rating'}
	${menu args->rating_style name='Colors', type='css', param='vars=--bgcolor:color; --border-color:color'}
${menu name='Site statistics: 1-day', icon='bar-chart', description='Show number of viewed or purchases in the last 24 hours for a given item as tracked by Personyze. You can set a condition not to show if the number of views/purchases is below X number.'}
	${menu block->stats_1day name='Site statistics: 1day'}
	${menu args->text_style_1day name='Style', type='css'}
	${menu args->n_viewed_1day name='Text'}
	${menu block->hide_no_view_1day name='Hide statistics if no views'}
	${menu args->hide_no_view_1day name='Hide statistics if less views than', type='number', param='min=0'}
	${menu args->hide_no_goal_1day name='Hide statistics if less purchases than', type='number', param='min=0'}
${menu name='Site statistics: week', icon='bar-chart', description='Show number of viewed or purchases in the last week for a given item as tracked by Personyze. You can set a condition not to show if the number of views/purchases is below X number.'}
	${menu block->stats_week name='Site statistics: week'}
	${menu args->text_style_week name='Style', type='css'}
	${menu args->n_viewed_week name='Text'}
	${menu block->hide_no_view_week name='Hide statistics if no views'}
	${menu args->hide_no_view_week name='Hide statistics if less views than', type='number', param='min=0'}
	${menu args->hide_no_goal_week name='Hide statistics if less purchases than', type='number', param='min=0'}
```


## Three items



```
<div class="$responsive $a_add_params" data-style="display:block; position:relative; ${args->style:html:default('max-width: 100vw; margin: 0 auto; box-sizing: border-box;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(0, 0, 'Frame', 'th-large')}" data-json-params="${args->url_params:html:input_type(external_media_url_params):arg_name(URL additional parameters):arg_section(0, 2, 'Frame', 'th-large')}">
    <link rel="stylesheet" href="https://fonts.googleapis.com/css?family=Open+Sans:400,400i,500,500i,600,600i,700,700i">
	<style>
		.-s-t-202007031-card {
			width: 100% !important;
			margin: 0 0 1.5rem !important;
		}

		@media (max-width: 785px) and (min-width: 512px) {
			.-s-t-202007031-card {
				width: 49% !important;
			    margin-right: 2% !important;
			    margin-bottom: 2% !important;
			}
		}

		@media (min-width: 786px) {
			.-s-t-202007031-card {
			    width: 32% !important;
			    margin-right: 2% !important;
			    margin-bottom: 2% !important;
			}
		}

		@media (min-width: 786px) {
			.-s-t-202007031-card:nth-of-type(3n+3) {
				margin-right: 0 !important;
			}
		}

		@media (max-width: 785px) and (min-width: 512px) {
			.-s-t-202007031-card:nth-of-type(2n+2) {
				margin-right: 0 !important;
			}
		}
	</style>
	${block->title:default(1):arg_name(With title bar):arg_section(3, 0, 'Title', 'bookmark')}
	<table data-style="border-collapse:collapse; border:none; ${args->title_bg:html:default('margin-top: 0;
margin-right: 0;
margin-bottom: 25px;
margin-left: 0;
background-color: rgba(0, 0, 0, 0);
padding-top: 0;
padding-right: 0;
padding-bottom: 0;
padding-left: 0;
border-bottom: none;
width: 100%;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(3, 2, 'Title', 'bookmark')}">
		<tr>
			<td data-style="vertical-align:middle; ${args->title_style:html:default('font-size: 36px;
letter-spacing: 0;
color: #335581;
text-align: center;
font-weight: 600;'):input_type(css):input_props('with_responsive=1'):arg_name(Title style):arg_section(3, 3, 'Title', 'bookmark')}">
				${args->title:default(Recommended For You):arg_name(Text):arg_section(3, 1, 'Title', 'bookmark')}
			</td>
			${block->x:default(0):arg_name(With close button):arg_section(4, 0, 'Close button', 'close')}
			<td style="width:1px; white-space:nowrap; ${args->x_style:html:input_type(css):arg_name(Close button position):arg_section(4, 2, 'Close button', 'close')}">
				${args->x:input_type(dontshowagain):input_props('style=cursor:pointer; vertical-align:middle'):arg_name(Close button):arg_section(4, 1, 'Close button', 'close')}
			</td>
		</tr>
	</table>
	${foreach articles as p where (p->image_big_url IS NOT NULL AND p->image_big_url!='') order by p->time_created desc limit 3}
		<div class="-s-t-202007031-card" data-style="display: inline-block; float: left; ${args->item_style:html:default('background-color: rgb(256, 256, 256);
border: 0px solid white;
font-family: &quot;
border-radius: 10px;'):input_type(css):input_props('with_responsive=1'):arg_name(Item style):arg_section(0, 1, 'Frame', 'th-large')}; box-sizing: border-box;">
			<a data-personyze-click-target="products ${p->internal_id:html}" href="${args->item_link_url:html:default('${p->content_url}'):arg_name(Link URL):arg_section(5, 0, 'Link target URL', 'link')}" target="${args->item_link_target:html:default(_self):input_type(a_target):arg_name(Open link in):arg_section(5, 1, 'Link target URL', 'link')}" data-style="display: block; ${args->item_image_style:html:default('max-height: 160px; margin: 0 0 1.6rem; overflow: hidden; color: #006ec7; text-decoration: none; cursor: pointer; outline: none;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(1, 1, 'Image', 'image')}; box-sizing: border-box;">
				<img src="${args->item_image_url:html:default('${p->image_big_url}'):arg_name(URL):arg_section(1, 0, 'Image', 'image')}" style="width: 100%; height: auto; border: 0;" />
			</a>
			<div data-style="${args->item_text_style:html:default('min-height: 6rem;
margin-top: 0;
margin-right: 25px;
margin-bottom: 0;
margin-left: 25px;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(2, 0, 'Text', 'align-justify')}; box-sizing: border-box;">
				<a data-personyze-click-target="products ${p->internal_id:html}" href="${args->item_link_url:html}" target="${args->item_link_target:html}" data-style="${args->item_title_style:html:default('font-size: 16px;
font-weight: 700;
text-transform: uppercase;
text-decoration: none !important;
color: #335581;
letter-spacing: 0.5px;
text-align: center;'):input_type(css):input_props('with_responsive=1'):arg_name(Title style):arg_section(2, 2, 'Text', 'align-justify')}; box-sizing: border-box;">${args->item_title:default('${p->title}'):arg_name(Title):arg_section(2, 1, 'Text', 'align-justify')}</a>
				<p data-style="${args->item_description_style:html:default('display: -webkit-box; -webkit-line-clamp: 4; -webkit-box-orient: vertical; margin: 0 0 1.6rem; font-size:14px; overflow: hidden; line-height: 22px; color: #4C5157;'):input_type(css):input_props('with_responsive=1'):arg_name(Description style):arg_section(2, 4, 'Text', 'align-justify')}; box-sizing: border-box;">${args->item_description:default('${p->description}'):arg_name(Description):arg_section(2, 3, 'Text', 'align-justify')}</p>
			</div>
			<a data-personyze-click-target="products ${p->internal_id:html}" href="${args->item_link_url:html}" target="${args->item_link_target:html}" data-style="display: block; ${args->item_link_style:html:default('cursor: pointer;
margin-top: 1px;
margin-right: auto;
margin-bottom: 1px;
margin-left: auto;
padding-top: 10px;
padding-right: 22px;
padding-bottom: 10px;
padding-left: 22px;
font-size: 14px;
text-align: center;
background-color: #335581;
color: #FFF;
font-weight: 500;
width: 77%;'):input_type(css):input_props('with_responsive=1'):arg_name(Link style):arg_section(5, 3, 'Link target URL', 'link')}; box-sizing: border-box;">${args->item_link_text:default(Recommended for you):arg_name(Link text):arg_section(5, 2, 'Link target URL', 'link')}</a>
		</div>
	${end}
</div>
```


## Content widget



```
<div class="$responsive $a_add_params" data-style="display:block; position:relative; ${args->style:html:default('max-width: 100vw; margin: 0 auto; box-sizing: border-box;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(0, 0, 'Frame', 'th-large')}" data-json-params="${args->url_params:html:input_type(external_media_url_params):arg_name(URL additional parameters):arg_section(0, 2, 'Frame', 'th-large')}">
    <link rel="stylesheet" href="https://fonts.googleapis.com/css?family=Open+Sans:400,400i,500,500i,600,600i,700,700i">
	<style>
		.-s-t-202007031-card {
			width: 100% !important;
			margin: 0 0 1.5rem !important;
		}

		@media (max-width: 785px) and (min-width: 512px) {
			.-s-t-202007031-card {
				width: 49% !important;
			    margin-right: 2% !important;
			    margin-bottom: 2% !important;
			}
		}

		@media (min-width: 786px) {
			.-s-t-202007031-card {
			    width: 32% !important;
			    margin-right: 2% !important;
			    margin-bottom: 2% !important;
			}
		}

		@media (min-width: 786px) {
			.-s-t-202007031-card:nth-of-type(3n+3) {
				margin-right: 0 !important;
			}
		}

		@media (max-width: 785px) and (min-width: 512px) {
			.-s-t-202007031-card:nth-of-type(2n+2) {
				margin-right: 0 !important;
			}
		}
	</style>
	${block->title:default(1):arg_name(With title bar):arg_section(3, 0, 'Title', 'bookmark')}
	<table data-style="border-collapse:collapse; border:none; ${args->title_bg:html:default('margin-top: 0;
margin-right: 0;
margin-bottom: 25px;
margin-left: 0;
background-color: rgba(0, 0, 0, 0);
padding-top: 0;
padding-right: 0;
padding-bottom: 0;
padding-left: 0;
border-bottom: none;
width: 100%;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(3, 2, 'Title', 'bookmark')}">
		<tr>
			<td data-style="vertical-align:middle; ${args->title_style:html:default('font-size: 18px;
letter-spacing: 0;
color: #21293c;
text-align: left;
font-weight: 600;'):input_type(css):input_props('with_responsive=1'):arg_name(Title style):arg_section(3, 3, 'Title', 'bookmark')}">
				${args->title:default(RECOMMENDATIONS):arg_name(Text):arg_section(3, 1, 'Title', 'bookmark')}
			</td>
			${block->x:default(0):arg_name(With close button):arg_section(4, 0, 'Close button', 'close')}
			<td style="width:1px; white-space:nowrap; ${args->x_style:html:input_type(css):arg_name(Close button position):arg_section(4, 2, 'Close button', 'close')}">
				${args->x:input_type(dontshowagain):input_props('style=cursor:pointer; vertical-align:middle'):arg_name(Close button):arg_section(4, 1, 'Close button', 'close')}
			</td>
		</tr>
	</table>
	${foreach articles as p where (p->image_big_url IS NOT NULL AND p->image_big_url!='') order by p->time_created desc limit 3}
		<div class="-s-t-202007031-card" data-style="display: inline-block; float: left; ${args->item_style:html:default('background-color: rgb(256, 256, 256);
border: 0px solid white;
font-family: &quot;
border-radius: 10px;'):input_type(css):input_props('with_responsive=1'):arg_name(Item style):arg_section(0, 1, 'Frame', 'th-large')}; box-sizing: border-box;">
			<a data-personyze-click-target="products ${p->internal_id:html}" href="${args->item_link_url:html:default('${p->content_url}'):arg_name(Link URL):arg_section(5, 0, 'Link target URL', 'link')}" target="${args->item_link_target:html:default(_self):input_type(a_target):arg_name(Open link in):arg_section(5, 1, 'Link target URL', 'link')}" data-style="display: block; ${args->item_image_style:html:default('max-height: 160px; margin: 0 0 1.6rem; overflow: hidden; color: #006ec7; text-decoration: none; cursor: pointer; outline: none;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(1, 1, 'Image', 'image')}; box-sizing: border-box;">
				<img src="${args->item_image_url:html:default('${p->image_big_url}'):arg_name(URL):arg_section(1, 0, 'Image', 'image')}" style="width: 100%; height: auto; border: 0;" />
			</a>
			<div data-style="${args->item_text_style:html:default('min-height: 6rem;
margin-top: 0;
margin-right: 25px;
margin-bottom: 0;
margin-left: 25px;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(2, 0, 'Text', 'align-justify')}; box-sizing: border-box;">
				<a data-personyze-click-target="products ${p->internal_id:html}" href="${args->item_link_url:html}" target="${args->item_link_target:html}" data-style="${args->item_title_style:html:default('font-size: 16px;
font-weight: 700;
text-transform: uppercase;
text-decoration: none !important;
color: #335581;
letter-spacing: 0.5px;
text-align: center;'):input_type(css):input_props('with_responsive=1'):arg_name(Title style):arg_section(2, 2, 'Text', 'align-justify')}; box-sizing: border-box;">${args->item_title:default('${p->title}'):arg_name(Title):arg_section(2, 1, 'Text', 'align-justify')}</a>
				<p data-style="${args->item_description_style:html:default('display: -webkit-box; -webkit-line-clamp: 4; -webkit-box-orient: vertical; margin: 0 0 1.6rem; font-size:14px; overflow: hidden; line-height: 22px; color: #4C5157;'):input_type(css):input_props('with_responsive=1'):arg_name(Description style):arg_section(2, 4, 'Text', 'align-justify')}; box-sizing: border-box;">${args->item_description:default('${p->description}'):arg_name(Description):arg_section(2, 3, 'Text', 'align-justify')}</p>
			</div>
			<a data-personyze-click-target="products ${p->internal_id:html}" href="${args->item_link_url:html}" target="${args->item_link_target:html}" data-style="display: block; ${args->item_link_style:html:default('cursor: pointer;
margin-top: 1px;
margin-right: auto;
margin-bottom: 1px;
margin-left: auto;
padding-top: 10px;
padding-right: 22px;
padding-bottom: 10px;
padding-left: 22px;
font-size: 14px;
text-align: center;
background-color: #335581;
color: #FFF;
font-weight: 500;
width: 77%;'):input_type(css):input_props('with_responsive=1'):arg_name(Link style):arg_section(5, 3, 'Link target URL', 'link')}; box-sizing: border-box;">${args->item_link_text:default(Recommended for you):arg_name(Link text):arg_section(5, 2, 'Link target URL', 'link')}</a>
		</div>
	${end}
</div>
```


## Paging recommendations



```
<div class="$responsive" style="width:100%; display:flex; justify-content:space-between; align-items:stretch; background-color:transparent; pointer-events:none">
	${foreach sum_articles as p where (p->image_big_url IS NOT NULL AND p->image_big_url!='') order by p->n_viewed desc limit 2}
		${if p->row_number = 1}
			<a id="trigger_${p->row_number:html}" href="${p->content_url:html}" style="${args->a_style:html:default('text-decoration: none;
color: inherit;
border: solid silver 1px;
background-color: white;
')}; display:flex; pointer-events:all">
				<div style="${args->a_style_2:html:default('display: flex;
flex-direction: column;
align-items: center;
min-width: 6em;
')}">
				${args->prev:default('<div>Prev</div>

<div>&laquo;</div>
')}
				</div>
				${block->with_thumbnail:default(1)}
				<img src="${p->image_big_url:html}" style="width:auto; height:auto; ${args->imgpv_style:html:default('max-width: 60px;
max-height: 40px;
')}">
			</a>
		${else}
			${block->with_bar:default(0)}
			<div style="${args->nav_style:html:default('background-color: white;
text-align: center;
')}; flex-grow:10000; pointer-events:all">
				${args->nav_text:default(Navigate)}
			</div>

			<a id="trigger_${p->row_number:html}" href="${p->content_url:html}" style="${args->a_style:html}; display:flex; pointer-events:all">
				${block->with_thumbnail:default(1)}
				<img src="${p->image_big_url:html}" style="width:auto; height:auto; ${args->imgpv_style:html}">
				<div style="${args->a_style_2:html}">
					${args->next:default('<div>Next</div>

<div>&raquo;</div>
')}
				</div>
			</a>
		${end}

		${block->with_popup:default(1)}
		<div class="$popup" data-trigger_id="trigger_${p->row_number:html}" data-trigger_onmouseover="1" data-json-trigger_transit='{"template": "animator_fade"}' data-design="hint" data-personyze-click-target="products ${p->internal_id:html}" style="${args->popup_style:html:default('text-align: center;
background-color: white;
width: 170px;
border: solid #52A2CB 2px;
')}">
			${block->with_image:default(1)}
			<a href="${p->content_url:html}" target="${args->target:html:default(_self)}" style="display:block; margin:auto; box-sizing:border-box">
				<img src="${p->image_big_url:html}" style="width:auto; height:auto; ${args->img_style:html:default('max-width: 100%;
max-height: 255px;
')}">
				${p->title}
			</a>
			${block->description:default(1)}
			<div style="display:inline-block; ${args->a_css_3:html}; padding-bottom:0">
				${p->description}
			</div>
		</div>
	${end}
</div>

${menu name='Popup', icon='window-restore'}
	${menu block->with_popup name='With popup'}
	${menu args->popup_style name='Popup style', type='css'}
	${menu p->image_big_url name='Item image', column_tags='image'}
${menu name='Middle bar', icon='minus'}
	${menu block->with_bar name='With middle bar'}
	${menu args->nav_style name='Navigation style', type='css'}
	${menu args->nav_text name='Navigation text'}
${menu name='Arrow buttons', icon='chevron-right'}
	${menu args->prev name='Previous button'}
	${menu args->next name='Next button'}
	${menu args->a_style name='Button style', type='css'}
${menu name='Thumbnail', icon='image'}
	${menu block->with_thumbnail name='With thumbnail'}
	${menu args->imgpv_style name='Thumbnail style', type='css'}
${menu name='Image in popup', icon='image'}
	${menu block->with_image name='With image in popup'}
	${menu args->img_style name='Image style', type='css'}
	${menu args->target name='Open link in', type='a_target'}
${menu name='Text', icon='bars'}
	${menu p->title name='Item text'}
	${menu p->content_url name='Link target URL', column_tags='url, custom text'}
${menu name='Description', icon='align-justify'}
	${menu block->description name='With description'}
	${menu p->description name='Description text'}
	${menu args->a_css_3 name='Description color', type='css'}
```


## Content widget



```
<div class="$responsive $a_add_params" data-style="display:inline-block; position:relative; display:flex; flex-direction:column; justify-content:stretch; ${args->style:html:default('padding: 0px;
border: none;
margin: auto;
width: 100%;
height: 100%;
background-color: rgba(0, 0, 0, 0);
')}; direction: ${args->direction:html:default(ltr)};" data-json-params="${args->url_params:html}">
	${block->with_logo:default(0)}
	<div style="${args->logo_block_style:html:default('text-align: center;
')}">
		<img src="${args->logo_src:html:default('https://counter-backend.personyze.com/upload/362/18a94c1299224ec8-th.jpeg')}">
		<div data-style="${args->logo_text_style:html}">
			${args->logo_text:default(Have a nice day!)}
		</div>
	</div>

	<div style="flex-grow:1000; display:flex; flex-direction:column; justify-content:center">
		<style>
			img.st-zoom {transition:transform ease 0.3s; transform: scale(1)}
			img.st-zoom:hover {transform: scale(calc(${args->img_zoom_on_hover:default(120)} / 100))}
		</style>

		${block->with_hover_image:default(0)}
		<style>
			img.st-zoom {transition-property:opacity; transform: scale(1); opacity: 1}
			img.st-zoom:hover {transform: scale(1); opacity: 0}

			img.st-zoom:last-child {transition:transform ease 0.3s; transform: scale(1)}
			img.st-zoom:last-child:hover {transform: scale(calc(${args->img_zoom_on_hover} / 100)); opacity: 1}

			img.st-zoom + div > img {transition:opacity ease 0.3s; opacity: 0}
			img.st-zoom + div > img:hover {opacity: 1}
		</style>

		<style>
			.st-tab-rnd > *:first-child > tr:first-child > *
			{	border-top-left-radius: ${args->round_border:default(8px)};
				border-top-right-radius: ${args->round_border};
				overflow: hidden;
			}

			.st-tab-rnd > *:last-child > tr:last-child > *
			{	border-bottom-left-radius: ${args->round_border};
				border-bottom-right-radius: ${args->round_border};
				overflow: hidden;
			}
		</style>

		${block->title:default(1)}
			<div data-style="display:flex; align-items:center; ${args->title_bg:html}">
				<div data-style="flex-grow:1000; ${args->title_style:html:default('text-align: left;
font-size: sel(18px, 18px);
font-weight: 500;
color: #383838;
padding-top: 10px;
padding-right: sel(15px, 1px);
padding-bottom: sel(10px, 5px);
padding-left: 0px;
text-transform: uppercase;
')}">
				${args->title:default(You may like)}
			</div>
			${block->with_arrows:default(0)}
			<div>
				<a id="button_back" class="$flat_btn" href="javascript:" style="${args->btn_style:html}" hover_style="${args->btn_hover_style:html}"><</a>
				<a id="button_forward" class="$flat_btn" href="javascript:" style="${args->btn_style:html}" hover_style="${args->btn_hover_style:html}">></a>
			</div>
			${block->x:default(0)}
			<div style="${args->x_style:html}">
				${args->x:default('<div onmouseenter="this.style.backgroundColor=this.style.outlineColor" onmouseleave="this.style.backgroundColor=this.style.textDecorationColor" style="display: inline-block; vertical-align: text-bottom; width: 24px; height: 24px; box-sizing: border-box; border-radius: 50%; border: 0px solid; -webkit-box-shadow: rgba(255, 255, 255, 0.2) 0px 1px 0px inset, rgba(0, 0, 0, 0.2) 0px 1px 2px; padding: 2px; background-color: rgba(0, 0, 0, 0); text-decoration-color: rgba(0, 0, 0, 0); outline-color: rgb(206, 54, 64); outline-width: 15px; color: rgb(10, 4, 4); cursor: pointer; transition: all 0.3s ease 0s;" class="$personyze_button_dont_show_again" data-action_id="${action_id}"><div style="display: block; width: 100%; height: 100%; transition: all 0.3s ease 0s; border-radius: 50%; background-image: linear-gradient(-45deg, transparent 0%, transparent 43%, currentcolor 43%, currentcolor 59%, transparent 59%, transparent 100%), linear-gradient(45deg, transparent 0%, transparent 43%, currentcolor 43%, currentcolor 59%, transparent 59%, transparent 100%);"></div></div>')}
			</div>
		</div>
		<div data-style="${args->content_padding:html:default('width: auto;
margin: auto;
')}">
			<table class="st-tab-rnd" data-style="height:10px; width:auto; border-collapse: separate; border-spacing: ${args->space_between_items:html:default(14px)} 0; margin:0 -${args->space_between_items:html}">
				<tr id="ts" class="$table_slider" data-disabled="${args->with_slider:html}" data-hover_add_class="st-td-hover" data-round="${args->round:html:default(1)}" data-with_scrollbar="${args->with_scrollbar:html:default(1)}" data-scrollbar_style="${args->scrollbar_style:html:default('background-color: #D8D8D8;
color: #999999;
height: 12px;
')}" data-hide_scrollbar="${args->hide_scrollbar:html}" style="width: 100%; box-sizing: border-box; border:none" for_max_vw="${args->for_max_vw:html:default(always)}" eq_cell_width="${args->eq_cell_width:html:default(1)}" eq_cell_height="${args->eq_cell_height:html:default(1)}" arrows_line="${args->arrows_line:html:default(-1)}" arrow_back_img="${args->arrow_back_img:html:default('<svg viewBox="0 0 54 54" width="24" height="24"><path style="fill:#4FBA6F" d="M27,1L27,1c14.359,0,26,11.641,26,26v0c0,14.359-11.641,26-26,26h0C12.641,53,1,41.359,1,27v0 C1,12.641,12.641,1,27,1z"/><path style="fill:#4FBA6F" d="M27,54C12.112,54,0,41.888,0,27S12.112,0,27,0s27,12.112,27,27S41.888,54,27,54z M27,2 C13.215,2,2,13.215,2,27s11.215,25,25,25s25-11.215,25-25S40.785,2,27,2z"/><path style="fill:#FFFFFF" d="M31.706,40c-0.256,0-0.512-0.098-0.707-0.293L19.501,28.209c-0.667-0.667-0.667-1.751,0-2.418 l11.498-11.498c0.391-0.391,1.023-0.391,1.414,0s0.391,1.023,0,1.414L21.12,27l11.293,11.293c0.391,0.391,0.391,1.023,0,1.414 C32.218,39.902,31.962,40,31.706,40z"/></svg>')}" arrow_style="${args->arrow_style:html:default('background-color: rgba(219, 195, 195, 0);
max-height: none;
padding-top: 0px;
padding-right: 2px;
padding-bottom: 0px;
padding-left: 2px;
width: auto;
')}" pagination_id="tsp" arrow_back_id="button_back" arrow_forward_id="button_forward" arrows_offset="${args->arrows_offset:html:default(-8)}" hide_buttons="${args->hide_buttons:html}" buttons_always="${args->buttons_always:html:default(1)}">
					${foreach articles as p where (p->image_big_url IS NOT NULL AND p->image_big_url!='') order by p->time_created desc union articles where (p->image_big_url IS NOT NULL AND p->image_big_url!='') order by p->time_created desc limit 10}
						<td style="position:relative; height:1px; padding:0; text-align:center; background-color:white; vertical-align:top; border:solid ${args->border_color:html:default('#dddddd')} 1px">
							<a data-personyze-click-target="articles ${p->internal_id:html}" href="${p->content_url:html}" target="${args->target:html:default(_self)}" data-style="position:relative; display:flex; height:100%; margin:auto; box-sizing:border-box; overflow: hidden; width:${args->img_width:html:default('sel(200px, 44vw)')}; text-decoration:none; ${args->img_alignment:html:default('align-items: center;
')}">
										<img class="st-zoom" src="${p->image_big_url:html}" data-style="width:auto; height:auto; max-width:100%; max-height:${args->img_max_height:html:default('sel(409px, 120px)')}; border:none">

										${if p->image_medium_url <> ''}
											${block->with_hover_image:default(0)}
											<div style="position:absolute; display:flex; left:0; top: 0; width:100%; height:100%; ${args->img_alignment:html}">
												<img src="${p->image_medium_url:html}" data-style="width:auto; height:auto; max-width:100%; max-height:${args->img_max_height:html}; border:none">
								</div>
										${end}

								${block->with_new_badge:default(1)}
								<span>
									${if unix_timestamp() - p->time_created <= args->badge_if_newer:default(2851200)}
										<div data-style="position: absolute; ${args->new_badge_style:html:default('top: 0;
left: 48px;
font-size: 14px;
text-shadow: rgba(255,255,255,0.5) 0px 3px 3px;
background-color: rgb(50, 101, 219);
color: rgb(250, 246, 246);
display: flex;
justify-content: center;
align-items: center;
padding: 0.3em;
')}">
											<span data-style="${args->new_badge_text_style:html:default('font-size: 16px;
font-weight: 600;
')}">${args->new_badge_text:default(NEW)}</span>
										</div>
									${end}
								</span>

								${block->with_time_badge:default(0)}
								<span>
									${if p->custom_i_1 - unix_timestamp() >= 0}
										<div data-style="position: absolute; ${args->time_badge_style:html:default('top: 0;
left: 48px;
font-size: 14px;
text-shadow: rgba(255,255,255,0.5) 0px 3px 3px;
background-color: rgb(50, 101, 219);
color: rgb(250, 246, 246);
display: flex;
justify-content: center;
align-items: center;
padding: 0.3em;
')}">
											<span data-style="${args->time_badge_text_style:html:default('font-size: 16px;
font-weight: 600;
')}">${args->time_badge_text:default(Special offer till)}</span>
											${block->with_time_badge_countdown}
											<span data-end="${p->custom_i_1:html- unix_timestamp()}" data-d="${args->time_badge_days:html:default(days)}" data-h="${args->time_badge_hr:html:default(hr)}" data-m="${args->time_badge_min:html:default(min)}" data-s="${args->time_badge_sec:html:default(sec)}" ontplready="var t=this, end=t.dataset.end|0, d=t.dataset.d, h=t.dataset.h, m=t.dataset.m, s=t.dataset.s; (function p() {var r=end-new Date().getTime()/1000; t.parentNode.parentNode.style.display = r<=0 ? 'none' : ''; t.textContent = ns.sec_to_span(r - r%(r >= 3*24*60*60 ? 24*60*60 : r > 24*60*60 ? 60*60 : 1), s, m, h, d); if (r <= 24*60*60) setTimeout(p, 1000)})()"></span>
										</div>
									${end}
								</span>

								${block->with_wishlist_badge:default(0)}
								<span class="$switch-elem"
									data-case="${foreach articles_interactions as w where w->internal_id = p->internal_id and w->interaction_status = 'favorite' limit 1}on${end}"
									data-p="${p->internal_id:html}"
									data-style="position:absolute; transition: all 0.3s ease; ${args->wishlist_style:html:default('top: 5px;
right: 5px;
color: rgb(119, 181, 115);
font-size: 25px;
')}"
									onclick="var on=this._get_case(); _S_T.push([on ? 'Article Unliked' : 'Article Liked', this.dataset.p]); this._set_case(on ? '' : 'on'); event.stopPropagation(); event.preventDefault()"
								>
									<div data-case="" class="$hint" style="${args->wishlist_off_style:html}">
										<span data-content="1">${args->wishlist_add_text:default(Add to wishlist)}</span>
										<hr class="$icon heart-o">
									</div>
									<div data-case="on" class="$hint" style="${args->wishlist_on_style:html:default('background-color: rgba(177, 93, 93, 0);
')}">
										<span data-content="1">${args->wishlist_rm_text:html:default(Remove from wishlist)}</span>
										<hr class="$icon heart">
									</div>
								</span>

								${block->with_db_badge:default(0)}
								<span>
									<div data-style="position: absolute; ${args->db_badge_style:html:default('top: 0;
left: 0px;
font-size: 14px;
text-shadow: rgba(255,255,255,0.5) 0px 3px 3px;
background-color: rgb(50, 101, 219);
color: rgb(250, 246, 246);
display: flex;
justify-content: center;
align-items: center;
padding: 0.3em;
')}">
										${block->with_db_badge_icon}
										<hr class="$icon ${args->db_badge_text_icon:html:default(bookmark)}">
										<span data-style="${args->db_badge_text_style:html:default('font-size: 16px;
font-weight: 600;
')}">${args->db_badge_text:default('${p->custom_2}')}</span>
									</div>
								</span>
							</a>
							<a data-personyze-click-target="articles ${p->internal_id:html}" href="${p->content_url:html}" target="${args->target:html}" data-style="display:block; margin:auto; box-sizing:border-box; width:${args->img_width:html}; text-decoration:none">
								<div data-style="${args->a_css:html:default('padding: 1px;
text-transform: none;
color: black;
font-weight: 400;
font-size: 18px;
margin: 10px;
text-align: center;
line-height: 1.3;
max-height: 5.2em;
overflow: hidden;
min-height: 4.5em;
')}; position:relative" data-max-lines="3" ontplready="
var that = this;
if (window.ResizeObserver) new ResizeObserver(function() {
	that.lastElementChild.style.display = that.scrollHeight>that.offsetHeight ? '' : 'none';
}).observe(this)" onmouseover="this.dataset.c = this.style.color; this.style.color = '${args->a_css_onhover:html:default('#F69442')}'" onmouseleave="this.style.color = this.dataset.c">
									${p->title}
									<div style="display:none; position:absolute; bottom:0; left:0; background-color:white">…</div>
								</div>
							</a>

							${block->with_date:default(1)}
							<div style="${args->date_column_style:html:default('padding-top: 0;
padding-right: 0;
padding-bottom: 1em;
padding-left: 0;
font-weight: 600;
')}" ontplready="this.innerHTML = window._S_T ? _S_T.ftime.strftime('${args->date_column_format:html:default('%B %d, %Y')}', ${args->date_column:html:default('${p->data_last_modified}')}) : '';"></div>

							${block->rating:default(1)}
							<span>
								<hr class="$rating" data-value="${p->rank:html:default(0)}" style="${args->rating_style:html:default('color: yellow;
--bgcolor: white;
--border-color: rgba(225, 214, 214, 0.87);
width: 10em;
height: 1.8em;
')}">
							</span>

							${block->stats_1day:default(1)}
							<div style="${args->text_style_1day:html:default('padding-top: 1em;
padding-right: 0;
padding-bottom: 1em;
padding-left: 0;
font-weight: 600;
')}">
								${foreach sum_articles_1day as s where s->internal_id = p->internal_id limit 1}
									${args->n_viewed_1day:default('${s->n_viewed*1} viewed today ${if s-&gt;n_goal &gt; 0}
<div>${s->n_goal*1}&nbsp; downloads today</div>
${end}')}
									<span ontplready="this._v='${s->n_viewed:html}'|0; this._g='${s->n_goal:html}'|0"></span>
								${end}
								${block->hide_no_view_1day:default(1)}
								<span ontplready="var p=this.previousElementSibling||{}; if (ns==window._S_T) if ((p._v|0) < ('${args->hide_no_view_1day:html:default(3)}'|0) || (p._g|0) < ('${args->hide_no_goal_1day:html:default(1)}'|0)) this.parentNode.style.display='none'"></span>
							</div>

							${block->stats_week:default(0)}
							<div style="${args->text_style_week:html:default('padding:1em 0')}">
								${foreach sum_articles_week as s where s->internal_id = p->internal_id limit 1}
									${args->n_viewed_week:default('<span style="font-size:14px;">This article has been popular in the last week!</span><br />
&nbsp;
<div><span style="color:#fac200;"><strong>${s->n_viewed*1} viewed</strong></span></div>
${if s-&gt;n_goal &gt; 0}

<div><span style="color:#fac200;"><strong>${s->n_goal*1} downloads</strong></span></div>
${end}')}
									<span ontplready="this._v='${s->n_viewed:html}'|0; this._g='${s->n_goal:html}'|0"></span>
								${end}
								${block->hide_no_view_week}
								<span ontplready="var p=this.previousElementSibling||{}; if (ns==window._S_T) if ((p._v|0) < ('${args->hide_no_view_week:html}'|0) || (p._g|0) < ('${args->hide_no_goal_week:html}'|0)) this.parentNode.style.display='none'"></span>
							</div>

							<div style="clear:left;"></div>
							<div style="margin:auto; box-sizing:border-box; font-size:1px">
								<div data-style="display:inline-block; background-color:${args->border_color:html}; ${args->a_css_2:html:default('width: 100px;
height: 0px;
max-width: 80%;
')}"></div>
							</div>
							${block->description:default(0)}
							<div data-style="margin:auto; box-sizing:border-box; width:${args->img_width:html}">
								<div data-style="display:inline-block; ${args->a_css_3:html}; padding-bottom:0">
									${p->description}
								</div>
							</div>

							${block->with_link_button:default(1)}
							<div data-style="box-sizing:border-box; ${args->link_button_box_style:html:default('text-align: center;
')}">
								<a class="$flat_btn" href="${args->link_button_href:html:default('${p->content_url}')}" data-style="box-sizing:border-box; ${args->link_button_style:html:default('color: rgb(39, 36, 70);
padding-top: 9px;
padding-right: 13px;
padding-bottom: 9px;
padding-left: 13px;
font-size: 14px;
line-height: 14px;
font-weight: 700;
font-family: Lato;
margin: 15px;
background-color: rgba(245, 36, 36, 0);
width: auto;
')}" hover_style="${args->link_button_style_hover:html:default('color: rgb(7, 3, 3);
padding-top: 9px;
padding-right: 13px;
padding-bottom: 9px;
padding-left: 13px;
font-size: 14px;
line-height: 14px;
font-weight: 700;
font-family: Lato;
transition: none;
margin: 15px;
background-color: rgb(237, 238, 227);
width: auto;
')}">
									${args->link_button_text:default(See details)}
								</a>
							</div>
						</td>
					${end}
				</tr>
			</table>
			${block->pagination:default(0)}
			<div id="tsp" class="$table_slider_pagination" slider_id="ts" selected_color="${args->pagination_color_on:html:default('rgba(0, 0, 0, 1)')}" style="${args->pagination_color:html}"></div>
		</div>
	</div>
</div>

${menu name='Frame', icon='th-large'}
	${menu args->style name='Style', type='css', param='with_responsive=1'}
	${menu args->content_padding name='Content box padding', type='css', param='with_responsive=1'}
	${menu args->round name='No cut cell', type='checkbox', param='value_off=', param='value_on=1'}
	${menu args->eq_cell_width name='Equal cell width', type='checkbox', param='value_off=', param='value_on=1'}
	${menu args->eq_cell_height name='Equal cell height', type='checkbox', param='value_off=', param='value_on=1'}
	${menu args->space_between_items name='Space between items', type='css_length', param='with_responsive=1'}
	${menu args->border_color name='Border color', type='color'}
	${menu args->round_border name='Round border', type='css_length'}
	${menu args->direction name='Localization settings', type='select', param='options=[["Left to right","ltr"],["Right to left","rtl"]]'}
	${menu args->url_params name='URL additional parameters', type='external_media_url_params'}
${menu name='Logo', icon='bars'}
	${menu block->with_logo name='With logo'}
	${menu args->logo_src name='Logo image', type='media_url'}
	${menu args->logo_block_style name='Logo block style', type='css'}
	${menu args->logo_text name='Text below logo'}
	${menu args->logo_text_style name='Text below logo - style', type='css'}
${menu name='Slider options', icon='arrow-right'}
	${menu block->with_arrows name='With arrow buttons'}
	${menu args->btn_style name='Arrow button style', type='css'}
	${menu args->btn_hover_style name='Arrow button style: hover', type='css'}
	${menu args->hide_buttons name='Hide arrow buttons when nothing to scroll', type='checkbox', param='value_off=', param='value_on=1', visible_if='block.title-0 && block.with_arrows-0'}
	${menu args->buttons_always name='Show arrows even when mouse doesn''t hover', type='checkbox', param='value_off=', param='value_on=1', visible_if='!(block.with_arrows-0)'}
	${menu args->with_slider name='Use slider widget', type='checkbox', param='value_off=1', param='value_on=', onchange='if (args.with_slider==1) block.with_arrows = block.pagination = 0'}
	${menu args->with_scrollbar name='Slider with scrollbar', type='checkbox', param='value_off=', param='value_on=1', visible_if='args.with_slider!=1'}
	${menu args->hide_scrollbar name='Hide scrollbar', type='checkbox', param='value_off=', param='value_on=1', visible_if='args.with_slider!=1 && args.with_scrollbar==1'}
	${menu args->scrollbar_style name='Scrollbar style', type='css', visible_if='args.with_slider!=1 && args.with_scrollbar==1'}
	${menu args->for_max_vw name='Slider widget only if screen width is less than or equal to', type='css_length', param='with_options=always', visible_if='args.with_slider!=1'}
	${menu args->arrow_back_img name='Left arrow image', type='arrow', visible_if='args.with_slider!=1'}
	${menu args->arrow_style name='Arrows style', type='css', visible_if='args.with_slider!=1'}
	${menu args->arrows_offset name='Slider arrows offset', type='number', visible_if='args.with_slider!=1'}
	${menu args->arrows_line name='Arrows in the middle of images', type='checkbox', param='value_off=-1', param='value_on=0', visible_if='args.with_slider!=1'}
	${menu block->pagination name='With slider pagination', visible_if='args.with_slider!=1'}
	${menu args->pagination_color_on name='Bullet Selected Color', type='color', visible_if='args.with_slider!=1'}
	${menu args->pagination_color name='Bullet style', type='css', visible_if='args.with_slider!=1'}
${menu name='Widget title', icon='bookmark'}
	${menu block->title name='With title bar'}
	${menu args->title name='Text'}
	${menu args->title_bg name='Style', type='css', param='with_responsive=1'}
	${menu args->title_style name='Title style', type='css', param='with_responsive=1'}
${menu name='Close button', icon='close'}
	${menu block->x name='With close button'}
	${menu args->x name='Close button', type='dontshowagain', param='style=cursor:pointer; vertical-align:middle'}
	${menu args->x_style name='Close button position', type='css'}
${menu name='Image/Cell width', icon='image'}
	${menu args->img_width name='Cell width', type='css_length', param='with_responsive=1'}
	${menu args->img_max_height name='Image maximum height', type='css_length', param='with_responsive=1'}
	${menu args->img_alignment name='Image alignment', type='css'}
	${menu p->image_big_url name='Item image', column_tags='image'}
${menu name='Zoom image on hover', icon='bars'}
	${menu args->img_zoom_on_hover name='Zoom %', type='number'}
${menu name='Hover alternative image', icon='image', description='On mouse hover, show additional product images when available on the product feed.'}
	${menu block->with_hover_image name='With hover image', onchange='block.with_zoom_image=block.with_hover_image^1||""'}
	${menu p->image_medium_url name='Hover image', column_tags='image'}
${menu name='New badge', icon='align-justify', description='Set "New" badge to appear for items debut recently.
You may choose a time frame for an article to be considered new. For new accounts/articles feed, all articles are new until the day setting condition has been met.'}
	${menu block->with_new_badge name='With new badge'}
	${menu args->badge_if_newer name='Show NEW badge if newer than', type='date', param='is_span=true', param='format=%0..999d days'}
	${menu args->new_badge_style name='Badge style', type='css', param='with_responsive=1'}
	${menu args->new_badge_text_style name='Badge text style', type='css', param='with_responsive=1'}
	${menu args->new_badge_text name='Text'}
${menu name='Time-based badge', icon='align-justify'}
	${menu block->with_time_badge name='With time-based badge'}
	${menu args->time_badge_style name='Badge style', type='css', param='with_responsive=1'}
	${menu args->time_badge_text_style name='Badge text style', type='css', param='with_responsive=1'}
	${menu args->time_badge_text name='Text'}
	${menu p->custom_i_1 name='Catalog field with end date', description='UNIX-timestamp'}
	${menu block->with_time_badge_countdown name='With days/time remaining'}
	${menu args->time_badge_days name='Time remaining: "days" text'}
	${menu args->time_badge_hr name='Time remaining: "hours" text'}
	${menu args->time_badge_min name='Time remaining: "minutes" text'}
	${menu args->time_badge_sec name='Time remaining: "seconds" text'}
${menu name='Add to wishlist', icon='bars', description='Show save to wishlist icon, on click item will be saved to Personyze wishlist. Items can be included in email/site widgets when using the wishlist algorithm. You can also set JS to report to your site when a visitor is saving an item to a wishlist.'}
	${menu block->with_wishlist_badge name='With add to wishlist'}
	${menu args->wishlist_style name='Style', type='css'}
	${menu args->wishlist_off_style name='Off icon style', type='css'}
	${menu args->wishlist_add_text name='Off tooltip (add to wishlist)'}
	${menu args->wishlist_on_style name='On icon style', type='css'}
	${menu args->wishlist_rm_text name='On tooltip (remove from wishlist)'}
${menu name='Icon or text badge', icon='star', description='Show text taken from catalog field'}
	${menu block->with_db_badge name='With db badge'}
	${menu args->db_badge_style name='Block style', type='css'}
	${menu block->with_db_badge_icon name='With icon'}
	${menu args->db_badge_text_icon name='Icon', type='icon'}
	${menu args->db_badge_text_style name='Icon style', type='css'}
	${menu args->db_badge_text name='Text'}
${menu name='Article text/desc', icon='align-justify'}
	${menu block->description name='With description'}
	${menu p->title name='Item text'}
	${menu p->description name='Item text'}
	${menu args->a_css name='Text style', type='css', param='with_responsive=1'}
	${menu args->a_css_onhover name='Text on hover color', type='color', param='with_responsive=1'}
	${menu args->a_css_3 name='Text color', type='css', param='with_responsive=1'}
	${menu args->a_css_2 name='Ruler', type='css', param='with_responsive=1'}
${menu name='Link button', icon='mouse-pointer'}
	${menu block->with_link_button name='With link button'}
	${menu args->link_button_href name='Link target URL'}
	${menu args->link_button_text name='Button text'}
	${menu args->link_button_box_style name='Box style', type='css', param='with_responsive=1'}
	${menu args->link_button_style name='Button style', type='css', param='with_responsive=1'}
	${menu args->link_button_style_hover name='Button hover style', type='css'}
${menu name='Onclick target URL', icon='link'}
	${menu p->content_url name='Link target URL', column_tags='url, custom text'}
	${menu args->target name='Open link in', type='a_target'}
${menu name='Date', icon='calendar', description='Show date.'}
	${menu block->with_date name='With rating'}
	${menu args->date_column name='Date column'}
	${menu args->date_column_format name='Date format'}
	${menu args->date_column_style name='Style', type='css'}
${menu name='Rating', icon='star', description='Show article rating when available
This requires you to populate "Rank" on your article feed.'}
	${menu block->rating name='With rating'}
	${menu p->rank name='Rating'}
	${menu args->rating_style name='Colors', type='css', param='vars=--bgcolor:color; --border-color:color'}
${menu name='Site statistics: 1-day', icon='bar-chart', description='Show number of viewed or purchases in the last 24 hours for a given item as tracked by Personyze. You can set a condition not to show if the number of views/purchases is below X number.'}
	${menu block->stats_1day name='Site statistics: 1day'}
	${menu args->text_style_1day name='Style', type='css'}
	${menu args->n_viewed_1day name='Text'}
	${menu block->hide_no_view_1day name='Hide statistics if no views'}
	${menu args->hide_no_view_1day name='Hide statistics if less views than', type='number', param='min=0'}
	${menu args->hide_no_goal_1day name='Hide statistics if less purchases than', type='number', param='min=0'}
${menu name='Site statistics: week', icon='bar-chart', description='Show number of viewed or purchases in the last week for a given item as tracked by Personyze. You can set a condition not to show if the number of views/purchases is below X number.'}
	${menu block->stats_week name='Site statistics: week'}
	${menu args->text_style_week name='Style', type='css'}
	${menu args->n_viewed_week name='Text'}
	${menu block->hide_no_view_week name='Hide statistics if no views'}
	${menu args->hide_no_view_week name='Hide statistics if less views than', type='number', param='min=0'}
	${menu args->hide_no_goal_week name='Hide statistics if less purchases than', type='number', param='min=0'}
```


## Vertical widget



```
<div class="$responsive $a_add_params" data-style="display:inline-block; position:relative; ${args->style:html:default('background-color: white;
color: #2E3234;
padding: 0px;
border: none;
margin: auto;
width: 300px;
display: block;
')}; direction: ${args->direction:html:default(ltr)};" data-json-params="${args->url_params:html}">
    ${block->title:default(1)}
    <table data-style="border-collapse:collapse; border:none; width:100%; ${args->title_bg:html}">
        <tr>
            <td data-style="vertical-align:middle; ${args->title_style:html:default('text-align: center;
font-size: sel(18px, 18px);
font-weight: 500;
line-height: sel(18px, 18px);
color: #383838;
padding-top: 10px;
padding-right: sel(15px, 1px);
padding-bottom: 5px;
padding-left: 0px;
text-transform: uppercase;
max-width: 100%;
width: 100%;
')}">
                ${args->title:default('You may like&nbsp;')}
            </td>
            ${block->x:default(0)}
            <td style="width:1px; white-space:nowrap; ${args->x_style:html}">
                ${args->x}
            </td>
        </tr>
    </table>
    <div class="st-holder-${action_id:html}" data-style="display:flex; flex-direction:column; align-items:stretch; ${args->holder_style:html:default('text-align: center;
')}">
		${foreach articles as p where (p->image_big_url IS NOT NULL AND p->image_big_url!='') order by p->time_created desc union articles where (p->image_big_url IS NOT NULL AND p->image_big_url!='') order by p->time_created desc limit 5}
			<div data-style="${args->item_style:html}">
				<a data-personyze-click-target="articles ${p->internal_id:html}" href="${p->content_url:html}" target="${args->target:html:default(_self)}" data-style="position:relative; display:block; margin:auto; box-sizing:border-box; overflow: hidden; width:${args->img_width:html:default('sel(200px, 44vw)')}; padding: ${args->img_max_height:html:default('sel(109px, 120px)')} 0 0 0; text-decoration: none;">
					<div data-style="position: absolute; left: 0; top: 0; right: 0; bottom: 0; margin: 8px; max-width: 100%; max-height: 100%; background-image:url('${p->image_big_url:html}'); background-repeat:no-repeat; background-position:center; background-size:contain; transition:background-size ease 0.3s">
						${block->with_zoom_image:default(0)}
						<span data-z="${args->zoom:html:default(110)}" data-l="${args->landscape:html}" ontplready="var p=this.parentNode, n=this.dataset.l ? '100% auto' : 'auto 100%', y=n.replace('100%', this.dataset.z+'%'); p.style.backgroundSize=n; p.onmouseenter=function() {this.style.backgroundSize=y}; p.onmouseleave=function() {this.style.backgroundSize=n}"></span>
					</div>

					${block->with_hover_image:default(1)}
					<span>
						${if p->image_medium_url <> ''}
							<div data-style="position: absolute; left: 0; top: 0; right: 0; bottom: 0; margin: 8px; max-width: 100%; max-height: 100%; background-image:url('${p->image_medium_url:html}'); background-repeat:no-repeat; background-position:center; background-size:contain; opacity:0; transition:opacity ease 0.3s" onmouseenter="this.style.opacity=1" onmouseleave="this.style.opacity=0">
							</div>
						${end}
					</span>

					${block->with_new_badge:default(1)}
					<span>
						${if unix_timestamp() - p->time_created <= args->badge_if_newer:default(2851200)}
							<div data-style="position: absolute; ${args->new_badge_style:html:default('top: 0;
left: 48px;
font-size: 14px;
text-shadow: rgba(255,255,255,0.5) 0px 3px 3px;
background-color: rgb(50, 101, 219);
color: rgb(250, 246, 246);
display: flex;
justify-content: center;
align-items: center;
padding: 0.3em;
')}">
								<span data-style="${args->new_badge_text_style:html:default('font-size: 16px;
font-weight: 600;
')}">${args->new_badge_text:default(NEW)}</span>
							</div>
						${end}
					</span>

					${block->with_time_badge:default(0)}
					<span>
						${if p->custom_i_1 - unix_timestamp() >= 0}
							<div data-style="position: absolute; ${args->time_badge_style:html:default('top: 0;
left: 48px;
font-size: 14px;
text-shadow: rgba(255,255,255,0.5) 0px 3px 3px;
background-color: rgb(50, 101, 219);
color: rgb(250, 246, 246);
display: flex;
justify-content: center;
align-items: center;
padding: 0.3em;
')}">
								<span data-style="${args->time_badge_text_style:html:default('font-size: 16px;
font-weight: 600;
')}">${args->time_badge_text:default(Special offer till)}</span>
								${block->with_time_badge_countdown}
								<span data-end="${p->custom_i_1:html- unix_timestamp()}" data-d="${args->time_badge_days:html:default(days)}" data-h="${args->time_badge_hr:html:default(hr)}" data-m="${args->time_badge_min:html:default(min)}" data-s="${args->time_badge_sec:html:default(sec)}" ontplready="var t=this, end=t.dataset.end|0, d=t.dataset.d, h=t.dataset.h, m=t.dataset.m, s=t.dataset.s; (function p() {var r=end-new Date().getTime()/1000; t.parentNode.parentNode.style.display = r<=0 ? 'none' : ''; t.textContent = ns.sec_to_span(r - r%(r >= 3*24*60*60 ? 24*60*60 : r > 24*60*60 ? 60*60 : 1), s, m, h, d); if (r <= 24*60*60) setTimeout(p, 1000)})()"></span>
							</div>
						${end}
					</span>

					${block->with_wishlist_badge:default(0)}
					<span class="$switch-elem"
						data-case="${foreach articles_interactions as w where w->internal_id = p->internal_id and w->interaction_status = 'favorite' limit 1}on${end}"
						data-p="${p->internal_id:html}"
						data-style="position:absolute; transition: all 0.3s ease; ${args->wishlist_style:html:default('top: 5px;
right: 5px;
color: rgb(119, 181, 115);
font-size: 25px;
')}"
						onclick="var on=this._get_case(); _S_T.push([on ? 'Article Unliked' : 'Article Liked', this.dataset.p]); this._set_case(on ? '' : 'on'); event.stopPropagation(); event.preventDefault()"
					>
						<div data-case="" class="$hint" style="${args->wishlist_off_style:html}">
							<span data-content="1">${args->wishlist_add_text:default(Add to wishlist)}</span>
							<hr class="$icon heart-o">
						</div>
						<div data-case="on" class="$hint" style="${args->wishlist_on_style:html:default('background-color: rgba(177, 93, 93, 0);
')}">
							<span data-content="1">${args->wishlist_rm_text:html:default(Remove from wishlist)}</span>
							<hr class="$icon heart">
						</div>
					</span>

					${block->with_db_badge:default(0)}
					<span>
						<div data-style="position: absolute; ${args->db_badge_style:html:default('top: 0;
left: 0px;
font-size: 14px;
text-shadow: rgba(255,255,255,0.5) 0px 3px 3px;
background-color: rgb(50, 101, 219);
color: rgb(250, 246, 246);
display: flex;
justify-content: center;
align-items: center;
padding: 0.3em;
')}">
							${block->with_db_badge_icon}
							<hr class="$icon ${args->db_badge_text_icon:html:default(bookmark)}">
							<span data-style="${args->db_badge_text_style:html:default('font-size: 16px;
font-weight: 600;
')}">${args->db_badge_text:default('${p->custom_2}')}</span>
						</div>
					</span>
				</a>
				<a data-personyze-click-target="articles ${p->internal_id:html}" href="${p->content_url:html}" target="${args->target:html}" data-style="display:block; margin:auto; box-sizing:border-box; width:${args->img_width:html}; text-decoration:none">
					<div data-style="${args->a_css:html:default('padding: 1px;
text-transform: none;
color: black;
font-weight: 400;
font-size: 18px;
margin: 10px;
text-align: center;
line-height: 1.3;
max-height: 5.2em;
overflow: hidden;
min-height: 4.5em;
')}; position:relative" data-max-lines="3" ontplready="
var that = this;
if (window.ResizeObserver) new ResizeObserver(function() {
that.lastElementChild.style.display = that.scrollHeight>that.offsetHeight ? '' : 'none';
}).observe(this)" onmouseover="this.dataset.c = this.style.color; this.style.color = '${args->a_css_onhover:html:default('#F69442')}'" onmouseleave="this.style.color = this.dataset.c">
						${p->title}
						<div style="display:none; position:absolute; bottom:0; left:0; background-color:white">…</div>
					</div>
				</a>

				${block->rating:default(1)}
				<span>
					<hr class="$rating" data-value="${p->rank:html:default(0)}" style="${args->rating_style:html:default('color: yellow;
--bgcolor: white;
--border-color: rgba(225, 214, 214, 0.87);
width: 10em;
height: 1.8em;
')}">
				</span>

				${block->stats_1day:default(1)}
				<div style="${args->text_style_1day:html:default('padding-top: 1em;
padding-right: 0;
padding-bottom: 1em;
padding-left: 0;
font-weight: 600;
')}">
					${foreach sum_articles_1day as s where s->internal_id = p->internal_id limit 1}
						${args->n_viewed_1day:default('${s->n_viewed*1} viewed today ${if s-&gt;n_goal &gt; 0}
<div>${s->n_goal*1}&nbsp; downloads today</div>
${end}')}
						<span ontplready="this._v='${s->n_viewed:html}'|0; this._g='${s->n_goal:html}'|0"></span>
					${end}
					${block->hide_no_view_1day:default(1)}
					<span ontplready="var p=this.previousElementSibling||{}; if (ns==window._S_T) if ((p._v|0) < ('${args->hide_no_view_1day:html:default(3)}'|0) || (p._g|0) < ('${args->hide_no_goal_1day:html:default(1)}'|0)) this.parentNode.style.display='none'"></span>
				</div>

				${block->stats_week:default(0)}
				<div style="${args->text_style_week:html:default('padding:1em 0')}">
					${foreach sum_articles_week as s where s->internal_id = p->internal_id limit 1}
						${args->n_viewed_week:default('<span style="font-size:14px;">This article has been popular in the last week!</span><br />
&nbsp;
<div><span style="color:#fac200;"><strong>${s->n_viewed*1} viewed</strong></span></div>
${if s-&gt;n_goal &gt; 0}

<div><span style="color:#fac200;"><strong>${s->n_goal*1} downloads</strong></span></div>
${end}')}
						<span ontplready="this._v='${s->n_viewed:html}'|0; this._g='${s->n_goal:html}'|0"></span>
					${end}
					${block->hide_no_view_week}
					<span ontplready="var p=this.previousElementSibling||{}; if (ns==window._S_T) if ((p._v|0) < ('${args->hide_no_view_week:html}'|0) || (p._g|0) < ('${args->hide_no_goal_week:html}'|0)) this.parentNode.style.display='none'"></span>
				</div>

				<div style="clear:left;"></div>

				${block->description:default(0)}
				<div data-style="margin:auto; box-sizing:border-box; width:${args->img_width:html}">
					<div data-style="display:inline-block; ${args->a_css_3:html}; padding-bottom:0">
						${p->description}
					</div>
				</div>

				${block->with_link_button:default(1)}
				<div>
					<a class="$flat_btn" href="${args->link_button_href:html:default('${p->custom_1}')}" data-style="box-sizing:border-box; ${args->link_button_style:html:default('color: rgb(39, 36, 70);
padding-top: 9px;
padding-right: 13px;
padding-bottom: 9px;
padding-left: 13px;
font-size: 14px;
line-height: 14px;
font-weight: 700;
font-family: Lato;
margin: 15px;
background-color: rgba(245, 36, 36, 0);
width: auto;
')}" hover_style="${args->link_button_style_hover:html:default('color: rgb(7, 3, 3);
padding-top: 9px;
padding-right: 13px;
padding-bottom: 9px;
padding-left: 13px;
font-size: 14px;
line-height: 14px;
font-weight: 700;
font-family: Lato;
transition: none;
margin: 15px;
background-color: rgb(237, 238, 227);
width: auto;
')}">
						${args->link_button_text:default(See details)}
					</a>
				</div>
			</div>
		${end}
		<div data-style="${args->more_box_style:html:default('background-color:white')}">
			<a href="javascript:" class="$btn" onclick="this.parentNode.parentNode.removeChild(this.parentNode)" data-n="${args->hide_from:json:html:default(3)}" ontplready="if (this.parentNode.parentNode.children.length <= this.dataset.n-0) this.parentNode.parentNode.removeChild(this.parentNode)" data-style="${args->more_style:html:default('background-color:orange')}">
				${args->more_text:default(See More)}
				<style>
					.st-holder-${action_id} > *:nth-child(n+${args->hide_from}) {display:none}
				</style>
			</a>
		</div>
    </div>
</div>

${menu name='Frame', icon='th-large'}
	${menu args->style name='Style', type='css', param='with_responsive=1'}
	${menu args->direction name='Localization settings', type='select', param='options=[["Left to right","ltr"],["Right to left","rtl"]]'}
	${menu args->url_params name='URL additional parameters', type='external_media_url_params'}
${menu name='Items', icon='th-large'}
	${menu args->holder_style name='Scrollbar style', type='css', param='with_responsive=1'}
	${menu args->item_style name='Hide scrollbar', type='css', param='with_responsive=1'}
	${menu args->hide_from name='Initially hide items from #'}
	${menu args->more_text name='More button text'}
	${menu args->more_style name='More button style', type='css', param='with_responsive=1'}
	${menu args->more_box_style name='More button style', type='css', param='with_responsive=1'}
${menu name='Widget title', icon='bookmark'}
	${menu block->title name='With title bar'}
	${menu args->title name='Text'}
	${menu args->title_bg name='Style', type='css', param='with_responsive=1'}
	${menu args->title_style name='Title style', type='css', param='with_responsive=1'}
${menu name='Close button', icon='close'}
	${menu block->x name='With close button'}
	${menu args->x name='Close button', type='dontshowagain', param='style=cursor:pointer; vertical-align:middle'}
	${menu args->x_style name='Close button position', type='css'}
${menu name='Image/Cell width', icon='image'}
	${menu args->img_width name='Cell width', type='css_length', param='with_responsive=1'}
	${menu args->img_max_height name='Image maximum height', type='css_length', param='with_responsive=1'}
	${menu p->image_big_url name='Item image', column_tags='image'}
${menu name='Zoom image on hover', icon='bars'}
	${menu block->with_zoom_image name='Zoom image on hover', onchange='block.with_hover_image=block.with_zoom_image^1||""'}
	${menu args->zoom name='Zoom %', type='number'}
	${menu args->landscape name='Orientation of each item image is landscape', type='checkbox', param='value_off=', param='value_on=1'}
${menu name='Hover alternative image', icon='image', description='On mouse hover, show additional item images when available on the article feed.'}
	${menu block->with_hover_image name='With hover image', onchange='block.with_zoom_image=block.with_hover_image^1||""'}
	${menu p->image_medium_url name='Hover image', column_tags='image'}
${menu name='New badge', icon='align-justify', description='Set "New" badge to appear for items debut recently.
You may choose a time frame for an article to be considered new. * For new accounts/articles feed, all articles are new until the day setting condition has been met.'}
	${menu block->with_new_badge name='With new badge'}
	${menu args->badge_if_newer name='Show NEW badge if newer than', type='date', param='is_span=true', param='format=%0..999d days'}
	${menu args->new_badge_style name='Badge style', type='css', param='with_responsive=1'}
	${menu args->new_badge_text_style name='Badge text style', type='css', param='with_responsive=1'}
	${menu args->new_badge_text name='Text'}
${menu name='Time-based badge', icon='align-justify'}
	${menu block->with_time_badge name='With time-based badge'}
	${menu args->time_badge_style name='Badge style', type='css', param='with_responsive=1'}
	${menu args->time_badge_text_style name='Badge text style', type='css', param='with_responsive=1'}
	${menu args->time_badge_text name='Text'}
	${menu p->custom_i_1 name='Catalog field with end date', description='UNIX-timestamp'}
	${menu block->with_time_badge_countdown name='With days/time remaining'}
	${menu args->time_badge_days name='Time remaining: "days" text'}
	${menu args->time_badge_hr name='Time remaining: "hours" text'}
	${menu args->time_badge_min name='Time remaining: "minutes" text'}
	${menu args->time_badge_sec name='Time remaining: "seconds" text'}
${menu name='Add to wishlist', icon='bars', description='Show save to wishlist icon, on click item will be saved to Personyze wishlist. Items can be included in email/site widgets when using the wishlist algorithm. You can also set JS to report to your site when a visitor is saving an item to a wishlist.'}
	${menu block->with_wishlist_badge name='With add to wishlist'}
	${menu args->wishlist_style name='Style', type='css'}
	${menu args->wishlist_off_style name='Off icon style', type='css'}
	${menu args->wishlist_add_text name='Off tooltip (add to wishlist)'}
	${menu args->wishlist_on_style name='On icon style', type='css'}
	${menu args->wishlist_rm_text name='On tooltip (remove from wishlist)'}
${menu name='Icon or text badge', icon='star', description='Show text taken from catalog field'}
	${menu block->with_db_badge name='With db badge'}
	${menu args->db_badge_style name='Block style', type='css'}
	${menu block->with_db_badge_icon name='With icon'}
	${menu args->db_badge_text_icon name='Icon', type='icon'}
	${menu args->db_badge_text_style name='Icon style', type='css'}
	${menu args->db_badge_text name='Text'}
${menu name='Article text/desc', icon='align-justify'}
	${menu block->description name='With description'}
	${menu p->title name='Item text'}
	${menu p->description name='Item text'}
	${menu args->a_css name='Text style', type='css', param='with_responsive=1'}
	${menu args->a_css_onhover name='Text on hover color', type='color', param='with_responsive=1'}
	${menu args->a_css_3 name='Text color', type='css', param='with_responsive=1'}
${menu name='Link button', icon='mouse-pointer'}
	${menu block->with_link_button name='With link button'}
	${menu args->link_button_href name='Link target URL'}
	${menu args->link_button_text name='Button text'}
	${menu args->link_button_style name='Button style', type='css'}
	${menu args->link_button_style_hover name='Button hover style', type='css'}
${menu name='Onclick target URL', icon='link'}
	${menu p->content_url name='Link target URL', column_tags='url, custom text'}
	${menu args->target name='Open link in', type='a_target'}
${menu name='Rating', icon='star', description='Show article rating when available
This requires you to populate "Rank" on your article feed   .'}
	${menu block->rating name='With rating'}
	${menu p->rank name='Rating'}
	${menu args->rating_style name='Colors', type='css', param='vars=--bgcolor:color; --border-color:color'}
${menu name='Site statistics: 1-day', icon='bar-chart', description='Show number of viewed or downloaded in the last 24 hours for a given item as tracked by Personyze. You can set a condition not to show if the number of views/goals is below X number.'}
	${menu block->stats_1day name='Site statistics: 1day'}
	${menu args->text_style_1day name='Style', type='css'}
	${menu args->n_viewed_1day name='Text'}
	${menu block->hide_no_view_1day name='Hide statistics if no views'}
	${menu args->hide_no_view_1day name='Hide statistics if less views than', type='number', param='min=0'}
	${menu args->hide_no_goal_1day name='Hide statistics if less goals than', type='number', param='min=0'}
${menu name='Site statistics: week', icon='bar-chart', description='Show number of viewed or downloaded in the last week for a given item as tracked by Personyze. You can set a condition not to show if the number of views/goals is below X number.'}
	${menu block->stats_week name='Site statistics: week'}
	${menu args->text_style_week name='Style', type='css'}
	${menu args->n_viewed_week name='Text'}
	${menu block->hide_no_view_week name='Hide statistics if no views'}
	${menu args->hide_no_view_week name='Hide statistics if less views than', type='number', param='min=0'}
	${menu args->hide_no_goal_week name='Hide statistics if less goals than', type='number', param='min=0'}
```


## Content with round images



```
<div class="$responsive $a_add_params" data-style="display:inline-block; position:relative; display:flex; flex-direction:column; justify-content:stretch; ${args->style:html:default('padding: 0px;
border: none;
margin: auto;
width: 100%;
height: 100%;
background-color: rgba(0, 0, 0, 0);
')}; direction: ${args->direction:html:default(ltr)};" data-json-params="${args->url_params:html}">
	${block->with_logo:default(0)}
	<div style="${args->logo_block_style:html:default('text-align: center;
')}">
		<img src="${args->logo_src:html:default('https://counter-backend.personyze.com/upload/362/18a94c1299224ec8-th.jpeg')}">
		<div data-style="${args->logo_text_style:html}">
			${args->logo_text:default(Have a nice day!)}
		</div>
	</div>

	<div style="flex-grow:1000; display:flex; flex-direction:column; justify-content:center">
		<style>
			img.st-zoom {transition:transform ease 0.3s; transform: scale(1)}
			img.st-zoom:hover {transform: scale(calc(${args->img_zoom_on_hover:default(120)} / 100))}

			.st-hov:hover {color: ${args->a_hover_color:html:default('#F69442')} !important}
		</style>

		${block->with_hover_image:default(0)}
		<style>
			img.st-zoom {transition-property:opacity; transform: scale(1); opacity: 1}
			img.st-zoom:hover {transform: scale(1); opacity: 0}

			img.st-zoom:last-child {transition:transform ease 0.3s; transform: scale(1)}
			img.st-zoom:last-child:hover {transform: scale(calc(${args->img_zoom_on_hover} / 100)); opacity: 1}

			img.st-zoom + div > img {transition:opacity ease 0.3s; opacity: 0}
			img.st-zoom + div > img:hover {opacity: 1}
		</style>

		<style>
			.st-tab-rnd > *:first-child > tr:first-child > *
			{	border-top-left-radius: ${args->round_border:default(8px)};
				border-top-right-radius: ${args->round_border};
				overflow: hidden;
			}

			.st-tab-rnd > *:last-child > tr:last-child > *
			{	border-bottom-left-radius: ${args->round_border};
				border-bottom-right-radius: ${args->round_border};
				overflow: hidden;
			}
		</style>

		${block->title:default(1)}
			<div data-style="display:flex; align-items:center; ${args->title_bg:html}">
				<div data-style="flex-grow:1000; ${args->title_style:html:default('text-align: left;
font-size: sel(18px, 18px);
font-weight: 500;
color: #383838;
padding-top: 10px;
padding-right: sel(15px, 1px);
padding-bottom: sel(10px, 5px);
padding-left: 0px;
text-transform: uppercase;
')}">
				${args->title:default(You may like)}
			</div>
			${block->with_arrows:default(0)}
			<div>
				<a id="button_back" class="$flat_btn" href="javascript:" style="${args->btn_style:html}" hover_style="${args->btn_hover_style:html}"><</a>
				<a id="button_forward" class="$flat_btn" href="javascript:" style="${args->btn_style:html}" hover_style="${args->btn_hover_style:html}">></a>
			</div>
			${block->x:default(0)}
			<div style="${args->x_style:html}">
				${args->x:default('<div onmouseenter="this.style.backgroundColor=this.style.outlineColor" onmouseleave="this.style.backgroundColor=this.style.textDecorationColor" style="display: inline-block; vertical-align: text-bottom; width: 24px; height: 24px; box-sizing: border-box; border-radius: 50%; border: 0px solid; -webkit-box-shadow: rgba(255, 255, 255, 0.2) 0px 1px 0px inset, rgba(0, 0, 0, 0.2) 0px 1px 2px; padding: 2px; background-color: rgba(0, 0, 0, 0); text-decoration-color: rgba(0, 0, 0, 0); outline-color: rgb(206, 54, 64); outline-width: 15px; color: rgb(10, 4, 4); cursor: pointer; transition: all 0.3s ease 0s;" class="$personyze_button_dont_show_again" data-action_id="${action_id}"><div style="display: block; width: 100%; height: 100%; transition: all 0.3s ease 0s; border-radius: 50%; background-image: linear-gradient(-45deg, transparent 0%, transparent 43%, currentcolor 43%, currentcolor 59%, transparent 59%, transparent 100%), linear-gradient(45deg, transparent 0%, transparent 43%, currentcolor 43%, currentcolor 59%, transparent 59%, transparent 100%);"></div></div>')}
			</div>
		</div>
		<div data-style="${args->content_padding:html:default('width: auto;
margin: auto;
')}">
			<table class="st-tab-rnd" data-style="height:10px; width:auto; border-collapse: separate; border-spacing: ${args->space_between_items:html:default(14px)} 0; margin:0 -${args->space_between_items:html}">
				<tr id="ts" class="$table_slider" data-disabled="${args->with_slider:html}" data-hover_add_class="st-td-hover" data-round="${args->round:html:default(1)}" data-with_scrollbar="${args->with_scrollbar:html:default(1)}" data-scrollbar_style="${args->scrollbar_style:html:default('background-color: #D8D8D8;
color: #999999;
height: 12px;
')}" data-hide_scrollbar="${args->hide_scrollbar:html}" style="width: 100%; box-sizing: border-box; border:none" for_max_vw="${args->for_max_vw:html:default(always)}" eq_cell_width="${args->eq_cell_width:html:default(1)}" eq_cell_height="${args->eq_cell_height:html:default(1)}" arrows_line="${args->arrows_line:html:default(-1)}" arrow_back_img="${args->arrow_back_img:html:default('<svg viewBox="0 0 54 54" width="24" height="24"><path style="fill:#4FBA6F" d="M27,1L27,1c14.359,0,26,11.641,26,26v0c0,14.359-11.641,26-26,26h0C12.641,53,1,41.359,1,27v0 C1,12.641,12.641,1,27,1z"/><path style="fill:#4FBA6F" d="M27,54C12.112,54,0,41.888,0,27S12.112,0,27,0s27,12.112,27,27S41.888,54,27,54z M27,2 C13.215,2,2,13.215,2,27s11.215,25,25,25s25-11.215,25-25S40.785,2,27,2z"/><path style="fill:#FFFFFF" d="M31.706,40c-0.256,0-0.512-0.098-0.707-0.293L19.501,28.209c-0.667-0.667-0.667-1.751,0-2.418 l11.498-11.498c0.391-0.391,1.023-0.391,1.414,0s0.391,1.023,0,1.414L21.12,27l11.293,11.293c0.391,0.391,0.391,1.023,0,1.414 C32.218,39.902,31.962,40,31.706,40z"/></svg>')}" arrow_style="${args->arrow_style:html:default('background-color: rgba(219, 195, 195, 0);
max-height: none;
padding-top: 0px;
padding-right: 2px;
padding-bottom: 0px;
padding-left: 2px;
width: auto;
')}" pagination_id="tsp" arrow_back_id="button_back" arrow_forward_id="button_forward" arrows_offset="${args->arrows_offset:html:default(-8)}" hide_buttons="${args->hide_buttons:html}" buttons_always="${args->buttons_always:html:default(1)}">
					${foreach articles as p where (p->image_big_url IS NOT NULL AND p->image_big_url!='') order by p->time_created desc union articles where (p->image_big_url IS NOT NULL AND p->image_big_url!='') order by p->time_created desc limit 10}
						<td style="position:relative; height:1px; padding:0; text-align:center; background-color:white; vertical-align:top; border:solid ${args->border_color:html:default('#dddddd')} 1px">
							<a data-personyze-click-target="articles ${p->internal_id:html}" href="${p->content_url:html}" target="${args->target:html:default(_self)}" data-style="position:relative; display:flex; height:100%; margin:auto; box-sizing:border-box; overflow: hidden; width:${args->img_width:html:default('sel(200px, 44vw)')}; text-decoration:none; ${args->img_alignment:html:default('align-items: center;
')}">
										<img class="st-zoom" src="${p->image_big_url:html}" data-style="width:auto; height:auto; max-width:100%; max-height:${args->img_max_height:html:default('sel(409px, 120px)')}; border:none">

										${if p->image_medium_url <> ''}
											${block->with_hover_image:default(0)}
											<div style="position:absolute; display:flex; left:0; top: 0; width:100%; height:100%; ${args->img_alignment:html}">
												<img src="${p->image_medium_url:html}" data-style="width:auto; height:auto; max-width:100%; max-height:${args->img_max_height:html}; border:none">
								</div>
										${end}

								${block->with_new_badge:default(1)}
								<span>
									${if unix_timestamp() - p->time_created <= args->badge_if_newer:default(2851200)}
										<div data-style="position: absolute; ${args->new_badge_style:html:default('top: 0;
left: 48px;
font-size: 14px;
text-shadow: rgba(255,255,255,0.5) 0px 3px 3px;
background-color: rgb(50, 101, 219);
color: rgb(250, 246, 246);
display: flex;
justify-content: center;
align-items: center;
padding: 0.3em;
')}">
											<span data-style="${args->new_badge_text_style:html:default('font-size: 16px;
font-weight: 600;
')}">${args->new_badge_text:default(NEW)}</span>
										</div>
									${end}
								</span>

								${block->with_time_badge:default(0)}
								<span>
									${if p->custom_i_1 - unix_timestamp() >= 0}
										<div data-style="position: absolute; ${args->time_badge_style:html:default('top: 0;
left: 48px;
font-size: 14px;
text-shadow: rgba(255,255,255,0.5) 0px 3px 3px;
background-color: rgb(50, 101, 219);
color: rgb(250, 246, 246);
display: flex;
justify-content: center;
align-items: center;
padding: 0.3em;
')}">
											<span data-style="${args->time_badge_text_style:html:default('font-size: 16px;
font-weight: 600;
')}">${args->time_badge_text:default(Special offer till)}</span>
											${block->with_time_badge_countdown}
											<span data-end="${p->custom_i_1:html- unix_timestamp()}" data-d="${args->time_badge_days:html:default(days)}" data-h="${args->time_badge_hr:html:default(hr)}" data-m="${args->time_badge_min:html:default(min)}" data-s="${args->time_badge_sec:html:default(sec)}" ontplready="var t=this, end=t.dataset.end|0, d=t.dataset.d, h=t.dataset.h, m=t.dataset.m, s=t.dataset.s; (function p() {var r=end-new Date().getTime()/1000; t.parentNode.parentNode.style.display = r<=0 ? 'none' : ''; t.textContent = ns.sec_to_span(r - r%(r >= 3*24*60*60 ? 24*60*60 : r > 24*60*60 ? 60*60 : 1), s, m, h, d); if (r <= 24*60*60) setTimeout(p, 1000)})()"></span>
										</div>
									${end}
								</span>

								${block->with_wishlist_badge:default(0)}
								<span class="$switch-elem"
									data-case="${foreach articles_interactions as w where w->internal_id = p->internal_id and w->interaction_status = 'favorite' limit 1}on${end}"
									data-p="${p->internal_id:html}"
									data-style="position:absolute; transition: all 0.3s ease; ${args->wishlist_style:html:default('top: 5px;
right: 5px;
color: rgb(119, 181, 115);
font-size: 25px;
')}"
									onclick="var on=this._get_case(); _S_T.push([on ? 'Article Unliked' : 'Article Liked', this.dataset.p]); this._set_case(on ? '' : 'on'); event.stopPropagation(); event.preventDefault()"
								>
									<div data-case="" class="$hint" style="${args->wishlist_off_style:html}">
										<span data-content="1">${args->wishlist_add_text:default(Add to wishlist)}</span>
										<hr class="$icon heart-o">
									</div>
									<div data-case="on" class="$hint" style="${args->wishlist_on_style:html:default('background-color: rgba(177, 93, 93, 0);
')}">
										<span data-content="1">${args->wishlist_rm_text:html:default(Remove from wishlist)}</span>
										<hr class="$icon heart">
									</div>
								</span>

								${block->with_db_badge:default(0)}
								<span>
									<div data-style="position: absolute; ${args->db_badge_style:html:default('top: 0;
left: 0px;
font-size: 14px;
text-shadow: rgba(255,255,255,0.5) 0px 3px 3px;
background-color: rgb(50, 101, 219);
color: rgb(250, 246, 246);
display: flex;
justify-content: center;
align-items: center;
padding: 0.3em;
')}">
										${block->with_db_badge_icon}
										<hr class="$icon ${args->db_badge_text_icon:html:default(bookmark)}">
										<span data-style="${args->db_badge_text_style:html:default('font-size: 16px;
font-weight: 600;
')}">${args->db_badge_text:default('${p->custom_2}')}</span>
									</div>
								</span>
							</a>
							<a data-personyze-click-target="articles ${p->internal_id:html}" href="${p->content_url:html}" target="${args->target:html}" data-style="display:block; margin:auto; box-sizing:border-box; width:${args->img_width:html}; text-decoration:none">
								<div class="st-hov" data-style="${args->a_css:html:default('padding: 1px;
text-transform: none;
color: black;
font-weight: 400;
font-size: 18px;
margin: 10px;
text-align: center;
line-height: 1.3;
')}; position:relative; overflow:hidden; text-overflow:ellipsis; display:-webkit-box; -webkit-box-orient:vertical; -webkit-line-clamp:${args->title_max_lines:html:default(3)}; line-clamp:${args->title_max_lines:html}">
									${p->title}
									<div style="display:none; position:absolute; bottom:0; left:0; background-color:white">…</div>
								</div>
							</a>

							${block->with_date:default(1)}
							<div style="${args->date_column_style:html:default('padding-top: 0;
padding-right: 0;
padding-bottom: 1em;
padding-left: 0;
font-weight: 600;
')}" ontplready="this.innerHTML = window._S_T ? _S_T.ftime.strftime('${args->date_column_format:html:default('%B %d, %Y')}', ${args->date_column:html:default('${p->data_last_modified}')}) : '';"></div>

							${block->rating:default(1)}
							<span>
								<hr class="$rating" data-value="${p->rank:html:default(0)}" style="${args->rating_style:html:default('color: yellow;
--bgcolor: white;
--border-color: rgba(225, 214, 214, 0.87);
width: 10em;
height: 1.8em;
')}">
							</span>

							${block->stats_1day:default(1)}
                            <span>
                                ${foreach sum_products_1day as s where s->internal_id = p->internal_id limit 1}
                                    ${if s->n_viewed >= args->hide_no_view_1day:default(3)}
                                        ${if s->n_goal >= args->hide_no_goal_1day:default(1)}
                                            <div style="${args->text_style_1day:html:default('padding-top: 1em;
padding-right: 0;
padding-bottom: 1em;
padding-left: 0;
font-weight: 600;
')}">
                                                ${if s->n_viewed > 0}
                                                    ${args->n_viewed_1day:default('<div>This article has been popular today! ${s->n_viewed*1} views.</div>
')}
                                                ${end}
                                                ${if s->n_goal > 0}
                                                    ${args->n_goal_1day:default('<div>${s->n_goal*1}&nbsp; downloads today</div>
')}
                                                ${end}
                                            </div>
                                        ${end}
                                    ${end}
                                ${end}
                            </span>

                            ${block->stats_week:default(0)}
                            <span>
                                ${foreach sum_products_week as s where s->internal_id = p->internal_id limit 1}
                                    ${if s->n_viewed >= args->hide_no_view_week:default(3)}
                                        ${if s->n_goal >= args->hide_no_goal_week:default(1)}
                                            <div style="${args->text_style_week:html:default('padding-top: 1em;
padding-right: 0;
padding-bottom: 1em;
padding-left: 0;
font-weight: 600;
')}">
                                                ${if s->n_viewed > 0}
                                                    ${args->n_viewed_week:default('<div>This article has been popular in the last week! ${s->n_viewed*1} views this week.</div>
')}
                                                ${end}
                                                ${if s->n_goal > 0}
                                                    ${args->n_goal_week:default('<div>${s->n_goal*1}&nbsp; downloads this week</div>
')}
                                                ${end}
                                            </div>
                                        ${end}
                                    ${end}
                                ${end}
                            </span>

							<div style="clear:left;"></div>
							<div style="margin:auto; box-sizing:border-box; font-size:1px">
								<div data-style="display:inline-block; background-color:${args->border_color:html}; ${args->a_css_2:html:default('width: 100px;
height: 0px;
max-width: 80%;
')}"></div>
							</div>
							${block->description:default(0)}
							<div data-style="margin:auto; box-sizing:border-box; width:${args->img_width:html}">
								<div data-style="display:inline-block; ${args->a_css_3:html}; padding-bottom:0">
									${p->description}
								</div>
							</div>

							${block->with_link_button:default(1)}
							<div data-style="box-sizing:border-box; ${args->link_button_box_style:html:default('text-align: center;
')}">
								<a class="$flat_btn" href="${args->link_button_href:html:default('${p->content_url}')}" data-style="box-sizing:border-box; ${args->link_button_style:html:default('color: rgb(39, 36, 70);
padding-top: 9px;
padding-right: 13px;
padding-bottom: 9px;
padding-left: 13px;
font-size: 14px;
line-height: 14px;
font-weight: 700;
font-family: Lato;
margin: 15px;
background-color: rgba(245, 36, 36, 0);
width: auto;
')}" hover_style="${args->link_button_style_hover:html:default('color: rgb(7, 3, 3);
padding-top: 9px;
padding-right: 13px;
padding-bottom: 9px;
padding-left: 13px;
font-size: 14px;
line-height: 14px;
font-weight: 700;
font-family: Lato;
transition: none;
margin: 15px;
background-color: rgb(237, 238, 227);
width: auto;
')}">
									${args->link_button_text:default(See details)}
								</a>
							</div>
						</td>
					${end}
				</tr>
			</table>
			${block->pagination:default(0)}
			<div id="tsp" class="$table_slider_pagination" slider_id="ts" selected_color="${args->pagination_color_on:html:default('rgba(0, 0, 0, 1)')}" style="${args->pagination_color:html}"></div>
		</div>
	</div>
</div>

${menu name='Frame', icon='th-large'}
	${menu args->style name='Style', type='css', param='with_responsive=1'}
	${menu args->content_padding name='Content box padding', type='css', param='with_responsive=1'}
	${menu args->round name='No cut cell', type='checkbox', param='value_off=', param='value_on=1'}
	${menu args->eq_cell_width name='Equal cell width', type='checkbox', param='value_off=', param='value_on=1'}
	${menu args->eq_cell_height name='Equal cell height', type='checkbox', param='value_off=', param='value_on=1'}
	${menu args->space_between_items name='Space between items', type='css_length', param='with_responsive=1'}
	${menu args->border_color name='Border color', type='color'}
	${menu args->round_border name='Round border', type='css_length'}
	${menu args->direction name='Localization settings', type='select', param='options=[["Left to right","ltr"],["Right to left","rtl"]]'}
	${menu args->url_params name='URL additional parameters', type='external_media_url_params'}
${menu name='Logo', icon='bars'}
	${menu block->with_logo name='With logo'}
	${menu args->logo_src name='Logo image', type='media_url'}
	${menu args->logo_block_style name='Logo block style', type='css'}
	${menu args->logo_text name='Text below logo'}
	${menu args->logo_text_style name='Text below logo - style', type='css'}
${menu name='Slider options', icon='arrow-right'}
	${menu block->with_arrows name='With arrow buttons'}
	${menu args->btn_style name='Arrow button style', type='css'}
	${menu args->btn_hover_style name='Arrow button style: hover', type='css'}
	${menu args->hide_buttons name='Hide arrow buttons when nothing to scroll', type='checkbox', param='value_off=', param='value_on=1', visible_if='block.title-0 && block.with_arrows-0'}
	${menu args->buttons_always name='Show arrows even when mouse doesn''t hover', type='checkbox', param='value_off=', param='value_on=1', visible_if='!(block.with_arrows-0)'}
	${menu args->with_slider name='Use slider widget', type='checkbox', param='value_off=1', param='value_on=', onchange='if (args.with_slider==1) block.with_arrows = block.pagination = 0'}
	${menu args->with_scrollbar name='Slider with scrollbar', type='checkbox', param='value_off=', param='value_on=1', visible_if='args.with_slider!=1'}
	${menu args->hide_scrollbar name='Hide scrollbar', type='checkbox', param='value_off=', param='value_on=1', visible_if='args.with_slider!=1 && args.with_scrollbar==1'}
	${menu args->scrollbar_style name='Scrollbar style', type='css', visible_if='args.with_slider!=1 && args.with_scrollbar==1'}
	${menu args->for_max_vw name='Slider widget only if screen width is less than or equal to', type='css_length', param='with_options=always', visible_if='args.with_slider!=1'}
	${menu args->arrow_back_img name='Left arrow image', type='arrow', visible_if='args.with_slider!=1'}
	${menu args->arrow_style name='Arrows style', type='css', visible_if='args.with_slider!=1'}
	${menu args->arrows_offset name='Slider arrows offset', type='number', visible_if='args.with_slider!=1'}
	${menu args->arrows_line name='Arrows in the middle of images', type='checkbox', param='value_off=-1', param='value_on=0', visible_if='args.with_slider!=1'}
	${menu block->pagination name='With slider pagination', visible_if='args.with_slider!=1'}
	${menu args->pagination_color_on name='Bullet Selected Color', type='color', visible_if='args.with_slider!=1'}
	${menu args->pagination_color name='Bullet style', type='css', visible_if='args.with_slider!=1'}
${menu name='Widget title', icon='bookmark'}
	${menu block->title name='With title bar'}
	${menu args->title name='Text'}
	${menu args->title_bg name='Style', type='css', param='with_responsive=1'}
	${menu args->title_style name='Title style', type='css', param='with_responsive=1'}
${menu name='Close button', icon='close'}
	${menu block->x name='With close button'}
	${menu args->x name='Close button', type='dontshowagain', param='style=cursor:pointer; vertical-align:middle'}
	${menu args->x_style name='Close button position', type='css'}
${menu name='Image/Cell width', icon='image'}
	${menu args->img_width name='Cell width', type='css_length', param='with_responsive=1'}
	${menu args->img_max_height name='Image maximum height', type='css_length', param='with_responsive=1'}
	${menu args->img_alignment name='Image alignment', type='css'}
	${menu p->image_big_url name='Item image', column_tags='image'}
${menu name='Zoom image on hover', icon='bars'}
	${menu args->img_zoom_on_hover name='Zoom %', type='number'}
${menu name='Hover alternative image', icon='image', description='On mouse hover, show additional product images when available on the product feed.'}
	${menu block->with_hover_image name='With hover image', onchange='block.with_zoom_image=block.with_hover_image^1||""'}
	${menu p->image_medium_url name='Hover image', column_tags='image'}
${menu name='New badge', icon='align-justify', description='Set "New" badge to appear for items debut recently.
You may choose a time frame for an article to be considered new. For new accounts/articles feed, all articles are new until the day setting condition has been met.'}
	${menu block->with_new_badge name='With new badge'}
	${menu args->badge_if_newer name='Show NEW badge if newer than', type='date', param='is_span=true', param='format=%0..999d days'}
	${menu args->new_badge_style name='Badge style', type='css', param='with_responsive=1'}
	${menu args->new_badge_text_style name='Badge text style', type='css', param='with_responsive=1'}
	${menu args->new_badge_text name='Text'}
${menu name='Time-based badge', icon='align-justify'}
	${menu block->with_time_badge name='With time-based badge'}
	${menu args->time_badge_style name='Badge style', type='css', param='with_responsive=1'}
	${menu args->time_badge_text_style name='Badge text style', type='css', param='with_responsive=1'}
	${menu args->time_badge_text name='Text'}
	${menu p->custom_i_1 name='Catalog field with end date', description='UNIX-timestamp'}
	${menu block->with_time_badge_countdown name='With days/time remaining'}
	${menu args->time_badge_days name='Time remaining: "days" text'}
	${menu args->time_badge_hr name='Time remaining: "hours" text'}
	${menu args->time_badge_min name='Time remaining: "minutes" text'}
	${menu args->time_badge_sec name='Time remaining: "seconds" text'}
${menu name='Add to wishlist', icon='bars', description='Show save to wishlist icon, on click item will be saved to Personyze wishlist. Items can be included in email/site widgets when using the wishlist algorithm. You can also set JS to report to your site when a visitor is saving an item to a wishlist.'}
	${menu block->with_wishlist_badge name='With add to wishlist'}
	${menu args->wishlist_style name='Style', type='css'}
	${menu args->wishlist_off_style name='Off icon style', type='css'}
	${menu args->wishlist_add_text name='Off tooltip (add to wishlist)'}
	${menu args->wishlist_on_style name='On icon style', type='css'}
	${menu args->wishlist_rm_text name='On tooltip (remove from wishlist)'}
${menu name='Icon or text badge', icon='star', description='Show text taken from catalog field'}
	${menu block->with_db_badge name='With db badge'}
	${menu args->db_badge_style name='Block style', type='css'}
	${menu block->with_db_badge_icon name='With icon'}
	${menu args->db_badge_text_icon name='Icon', type='icon'}
	${menu args->db_badge_text_style name='Icon style', type='css'}
	${menu args->db_badge_text name='Text'}
${menu name='Article text/desc', icon='align-justify'}
	${menu block->description name='With description'}
	${menu p->title name='Item text'}
	${menu args->title_max_lines name='Title max lines', type='number', param='min=1'}
	${menu p->description name='Item text'}
	${menu args->a_css name='Text style', type='css', param='with_responsive=1'}
	${menu args->a_hover_color name='Text on hover color', type='color'}
	${menu args->a_css_3 name='Text color', type='css', param='with_responsive=1'}
	${menu args->a_css_2 name='Ruler', type='css', param='with_responsive=1'}
${menu name='Link button', icon='mouse-pointer'}
	${menu block->with_link_button name='With link button'}
	${menu args->link_button_href name='Link target URL'}
	${menu args->link_button_text name='Button text'}
	${menu args->link_button_box_style name='Box style', type='css', param='with_responsive=1'}
	${menu args->link_button_style name='Button style', type='css', param='with_responsive=1'}
	${menu args->link_button_style_hover name='Button hover style', type='css'}
${menu name='Onclick target URL', icon='link'}
	${menu p->content_url name='Link target URL', column_tags='url, custom text'}
	${menu args->target name='Open link in', type='a_target'}
${menu name='Date', icon='calendar', description='Show date.'}
	${menu block->with_date name='With rating'}
	${menu args->date_column name='Date column'}
	${menu args->date_column_format name='Date format'}
	${menu args->date_column_style name='Style', type='css'}
${menu name='Rating', icon='star', description='Show article rating when available
This requires you to populate "Rank" on your article feed.'}
	${menu block->rating name='With rating'}
	${menu p->rank name='Rating'}
	${menu args->rating_style name='Colors', type='css', param='vars=--bgcolor:color; --border-color:color'}
${menu name='Site statistics: 1-day', icon='bar-chart', description='Show number of viewed or purchases in the last 24 hours for a given item as tracked by Personyze. You can set a condition not to show if the number of views/purchases is below X number.'}
	${menu block->stats_1day name='Site statistics: 1day'}
	${menu args->hide_no_view_1day name='Hide statistics if less views than', type='number', param='min=0'}
	${menu args->hide_no_goal_1day name='Hide statistics if less goals than', type='number', param='min=0'}
	${menu args->text_style_1day name='Style', type='css'}
	${menu args->n_viewed_1day name='Text'}
	${menu args->n_goal_1day name='Text'}
${menu name='Site statistics: week', icon='bar-chart', description='Show number of viewed or purchases in the last week for a given item as tracked by Personyze. You can set a condition not to show if the number of views/purchases is below X number.'}
	${menu block->stats_week name='Site statistics: week'}
	${menu args->hide_no_view_week name='Hide statistics if less views than', type='number', param='min=0'}
	${menu args->hide_no_goal_week name='Hide statistics if less goals than', type='number', param='min=0'}
	${menu args->text_style_week name='Style', type='css'}
	${menu args->n_viewed_week name='Text'}
	${menu args->n_goal_week name='Text'}
```


## Content widget



```
<div class="$responsive $a_add_params" data-style="display:inline-block; position:relative; display:flex; flex-direction:column; justify-content:stretch; ${args->style:html:default('padding: 0px;
border: none;
margin-top: 0;
margin-right: auto;
margin-bottom: 0;
margin-left: auto;
width: 97%;
height: auto;
background-color: rgba(132, 61, 61, 0);
max-width: 100vw;
display: inline-block;
')}; direction: ${args->direction:html:default(ltr)};" data-json-params="${args->url_params:html}">
	${block->with_logo:default(0)}
	<div style="${args->logo_block_style:html:default('text-align: center;
')}">
		<img src="${args->logo_src:html:default('https://counter-backend.personyze.com/upload/362/18a94c1299224ec8-th.jpeg')}">
		<div data-style="${args->logo_text_style:html}">
			${args->logo_text:default(Have a nice day!)}
		</div>
	</div>

	<div style="flex-grow:1000; display:flex; flex-direction:column; justify-content:center">
		<style>
			.st-zoom {transition:transform ease 0.3s; transform: scale(1)}
			.st-zoom:hover {transform: scale(calc(${args->img_zoom_on_hover:default(105)} / 100))}

            .st-hov:hover {color: ${args->a_hover_color:html:default('#F69442')} !important}
		</style>

		<style>
			.st-tab-rnd > *:first-child > tr:first-child > *
			{	border-top-left-radius: ${args->round_border:default(1px)};
				border-top-right-radius: ${args->round_border};
				overflow: hidden;
			}

			.st-tab-rnd > *:last-child > tr:last-child > *
			{	border-bottom-left-radius: ${args->round_border};
				border-bottom-right-radius: ${args->round_border};
				overflow: hidden;
			}
		</style>

		${block->title:default(1)}
			<div data-style="display:flex; align-items:center; ${args->title_bg:html:default('margin: 44px;
')}">
				<div data-style="flex-grow:1000; ${args->title_style:html:default('text-align: left;
padding-top: 10px;
padding-right: sel(15px, 1px);
padding-bottom: sel(22px, 11px);
padding-left: 0px;
text-transform: none;
Height: 42px;
')}">
				${args->title:default('<h2 class="c-newslist__related-posts-header u-h2 u-text-center">You might be also interested in</h2>
')}
			</div>
			${block->with_arrows:default(0)}
			<div>
				<a id="button_back" class="$flat_btn" href="javascript:" style="${args->btn_style:html}" hover_style="${args->btn_hover_style:html}"><</a>
				<a id="button_forward" class="$flat_btn" href="javascript:" style="${args->btn_style:html}" hover_style="${args->btn_hover_style:html}">></a>
			</div>
			${block->x:default(0)}
			<div style="${args->x_style:html}">
				${args->x:default('<div onmouseenter="this.style.backgroundColor=this.style.outlineColor" onmouseleave="this.style.backgroundColor=this.style.textDecorationColor" style="display: inline-block; vertical-align: text-bottom; width: 24px; height: 24px; box-sizing: border-box; border-radius: 50%; border: 0px solid; -webkit-box-shadow: rgba(255, 255, 255, 0.2) 0px 1px 0px inset, rgba(0, 0, 0, 0.2) 0px 1px 2px; padding: 2px; background-color: rgba(0, 0, 0, 0); text-decoration-color: rgba(0, 0, 0, 0); outline-color: rgb(206, 54, 64); outline-width: 15px; color: rgb(10, 4, 4); cursor: pointer; transition: all 0.3s ease 0s;" class="$personyze_button_dont_show_again" data-action_id="${action_id}"><div style="display: block; width: 100%; height: 100%; transition: all 0.3s ease 0s; border-radius: 50%; background-image: linear-gradient(-45deg, transparent 0%, transparent 43%, currentcolor 43%, currentcolor 59%, transparent 59%, transparent 100%), linear-gradient(45deg, transparent 0%, transparent 43%, currentcolor 43%, currentcolor 59%, transparent 59%, transparent 100%);"></div></div>')}
			</div>
		</div>
		<div data-style="${args->content_padding:html:default('width: 95%;
margin-top: 0;
margin-right: auto;
margin-bottom: 0;
margin-left: auto;
')}">
			<table class="st-tab-rnd" data-style="height:10px; width:auto; border-collapse: separate; border-spacing: ${args->space_between_items:html:default(22px)} 0; margin:0 -${args->space_between_items:html}">
				<tr id="ts" class="$table_slider" data-disabled="${args->with_slider:html}" data-hover_add_class="st-td-hover" data-round="${args->round:html:default(1)}" data-with_scrollbar="${args->with_scrollbar:html}" data-scrollbar_style="${args->scrollbar_style:html:default('background-color: #D8D8D8;
color: #999999;
height: 12px;
')}" data-hide_scrollbar="${args->hide_scrollbar:html:default(1)}" style="width: 100%; box-sizing: border-box; border:none" for_max_vw="${args->for_max_vw:html:default(always)}" eq_cell_width="${args->eq_cell_width:html:default(1)}" eq_cell_height="${args->eq_cell_height:html:default(1)}" arrows_line="${args->arrows_line:html:default(-1)}" arrow_back_img="${args->arrow_back_img:html:default('<svg viewBox="0 0 54 54" width="24" height="24"><path style="fill: rgb(119, 157, 213);" d="M27,1L27,1c14.359,0,26,11.641,26,26v0c0,14.359-11.641,26-26,26h0C12.641,53,1,41.359,1,27v0 C1,12.641,12.641,1,27,1z"></path><path style="fill:#4FBA6F" d="M27,54C12.112,54,0,41.888,0,27S12.112,0,27,0s27,12.112,27,27S41.888,54,27,54z M27,2 C13.215,2,2,13.215,2,27s11.215,25,25,25s25-11.215,25-25S40.785,2,27,2z"></path><path style="fill:#FFFFFF" d="M31.706,40c-0.256,0-0.512-0.098-0.707-0.293L19.501,28.209c-0.667-0.667-0.667-1.751,0-2.418 l11.498-11.498c0.391-0.391,1.023-0.391,1.414,0s0.391,1.023,0,1.414L21.12,27l11.293,11.293c0.391,0.391,0.391,1.023,0,1.414 C32.218,39.902,31.962,40,31.706,40z"></path></svg>')}" arrow_style="${args->arrow_style:html:default('background-color: rgba(219, 195, 195, 0);
max-height: none;
padding-top: 0px;
padding-right: 2px;
padding-bottom: 0px;
padding-left: 2px;
width: auto;
')}" pagination_id="tsp" arrow_back_id="button_back" arrow_forward_id="button_forward" arrows_offset="${args->arrows_offset:html:default(-35)}" hide_buttons="${args->hide_buttons:html}" buttons_always="${args->buttons_always:html:default(1)}">
					${foreach articles as p where (p->image_big_url IS NOT NULL AND p->image_big_url!='') order by p->time_created desc union sum_articles where p->for_period='recently' order by p->n_viewed desc limit 10}
						<td style="position:relative; height:1px; padding:0; text-align:center; background-color:white; vertical-align:top; border:solid ${args->border_color:html:default('#d6d6d6')} 1px">
							<a class="st-zoom" data-personyze-click-target="articles ${p->internal_id:html}" href="${p->content_url:html}" target="${args->target:html:default(_self)}" data-style="position:relative; display:flex; margin:auto; box-sizing:border-box; overflow: hidden; width:${args->img_width:html:default('sel(300px, 45vw)')}; text-decoration:none; background-image:url('${p->image_big_url:html}'); background-repeat:no-repeat; background-size:cover">
								<img src="${p->image_big_url:html}" data-style="visibility:hidden; width:auto; height:auto; max-width:100%; max-height:${args->img_max_height:html:default('sel(200px, 35vw)')}; border:none">

								${block->with_new_badge:default(1)}
								<span>
									${if unix_timestamp() - p->publish_date <= args->badge_if_newer:default(2851200)}
										<div data-style="position: absolute; ${args->new_badge_style:html:default('top: 0;
left: 48px;
font-size: 14px;
text-shadow: rgba(255,255,255,0.5) 0px 3px 3px;
background-color: rgb(50, 101, 219);
color: rgb(250, 246, 246);
display: flex;
justify-content: center;
align-items: center;
padding: 0.3em;
')}">
											<span data-style="${args->new_badge_text_style:html:default('font-size: 16px;
font-weight: 600;
')}">${args->new_badge_text:default(NEW)}</span>
										</div>
									${end}
								</span>

								${block->with_time_badge:default(0)}
								<span>
									${if p->custom_i_1 - unix_timestamp() >= 0}
										<div data-style="position: absolute; ${args->time_badge_style:html:default('top: 0;
left: 48px;
font-size: 14px;
text-shadow: rgba(255,255,255,0.5) 0px 3px 3px;
background-color: rgb(50, 101, 219);
color: rgb(250, 246, 246);
display: flex;
justify-content: center;
align-items: center;
padding: 0.3em;
')}">
											<span data-style="${args->time_badge_text_style:html:default('font-size: 16px;
font-weight: 600;
')}">${args->time_badge_text:default(Special offer till)}</span>
											${block->with_time_badge_countdown}
											<span data-end="${p->custom_i_1:html- unix_timestamp()}" data-d="${args->time_badge_days:html:default(days)}" data-h="${args->time_badge_hr:html:default(hr)}" data-m="${args->time_badge_min:html:default(min)}" data-s="${args->time_badge_sec:html:default(sec)}" ontplready="var t=this, end=t.dataset.end|0, d=t.dataset.d, h=t.dataset.h, m=t.dataset.m, s=t.dataset.s; (function p() {var r=end-new Date().getTime()/1000; t.parentNode.parentNode.style.display = r<=0 ? 'none' : ''; t.textContent = ns.sec_to_span(r - r%(r >= 3*24*60*60 ? 24*60*60 : r > 24*60*60 ? 60*60 : 1), s, m, h, d); if (r <= 24*60*60) setTimeout(p, 1000)})()"></span>
										</div>
									${end}
								</span>

								${block->with_wishlist_badge:default(0)}
								<span class="$switch-elem"
									data-case="${foreach articles_interactions as w where w->internal_id = p->internal_id and w->interaction_status = 'favorite' limit 1}on${end}"
									data-p="${p->internal_id:html}"
									data-style="position:absolute; transition: all 0.3s ease; ${args->wishlist_style:html:default('top: 5px;
right: 5px;
color: rgb(119, 181, 115);
font-size: 25px;
')}"
									onclick="var on=this._get_case(); _S_T.push([on ? 'Article Unliked' : 'Article Liked', this.dataset.p]); this._set_case(on ? '' : 'on'); event.stopPropagation(); event.preventDefault()"
								>
									<div data-case="" class="$hint" style="${args->wishlist_off_style:html}">
										<span data-content="1">${args->wishlist_add_text:default(Add to wishlist)}</span>
										<hr class="$icon heart-o">
									</div>
									<div data-case="on" class="$hint" style="${args->wishlist_on_style:html:default('background-color: rgba(177, 93, 93, 0);
')}">
										<span data-content="1">${args->wishlist_rm_text:html:default(Remove from wishlist)}</span>
										<hr class="$icon heart">
									</div>
								</span>

								${block->with_db_badge:default(0)}
								<span>
									<div data-style="position: absolute; ${args->db_badge_style:html:default('font-family: libre franklin;
font-weight: 400;
font-size: 20px;
color: #007CAD;
line-height: 30px;
background-color: rgba(219, 50, 50, 0);
bottom: nullpx;
')}">
										${block->with_db_badge_icon}
										<hr class="$icon ${args->db_badge_text_icon:html}">
										<span data-style="${args->db_badge_text_style:html:default('font-size: 16px;
font-weight: 600;
')}">${args->db_badge_text}</span>
									</div>
								</span>
							</a>

							${block->with_date:default(1)}
							<div style="box-sizing:border-box; ${args->date_column_style:html:default('text-align: left;
padding: 1em;
font-weight: 700;
font-size: 12px;
color: #9f9f9f;
line-height: 20px;
font-family: ''Libre Franklin'', sans-serif;
')}" ontplready="var t = ${args->date_column:json:html:default('${p->publish_date:unix_timestamp}')}|0; this.innerHTML = window._S_T && t ? _S_T.ftime.strftime('${args->date_column_format:html:default(%d %B %Y)}', t) : '';"></div>

							${block->with_custom_column:default(0)}
							<div>
								<div style="${args->custom_column_style:html:default('text-align: left;
padding: 1em;
font-weight: 700;
font-size: 12px;
color: #9f9f9f;
line-height: 20px;
font-family: ''Libre Franklin'', sans-serif;
')}">${args->custom_column:html:default('${p->custom_1}')}</div>
							</div>

							<a data-personyze-click-target="articles ${p->internal_id:html}" href="${p->content_url:html}" target="${args->target:html}" data-style="display:block; margin:auto; box-sizing:border-box; width:${args->img_width:html}; text-decoration:none">
								<div class="st-hov" data-style="${args->a_css:html:default('border-collapse: collapse;
text-align: left;
box-sizing: inherit;
margin-top: 0;
margin-right: 0;
margin-bottom: 16px;
margin-left: 0;
padding: 11px;
line-height: 1.4;
color: #2d2d2d;
font-size: sel(20px, 12px);
')}; position:relative" ontplready="
var that = this;
if (window.ResizeObserver) new ResizeObserver(function() {
	that.lastElementChild.style.display = that.scrollHeight>that.offsetHeight ? '' : 'none';
}).observe(this)">
									${args->p_description:default('${p->title}')}
									<div style="display:none; position:absolute; bottom:0; left:0; background-color:white">…</div>
								</div>
							</a>

							${block->rating:default(0)}
							<span>
								<hr class="$rating" data-value="${p->rank:html:default(0)}" style="${args->rating_style:html:default('color: yellow;
--bgcolor: white;
--border-color: rgba(225, 214, 214, 0.87);
width: 10em;
height: 1.8em;
')}">
							</span>

							${block->stats_1day:default(0)}
							<div style="${args->text_style_1day:html:default('padding-top: 1em;
padding-right: 0;
padding-bottom: 1em;
padding-left: 0;
font-weight: 600;
')}">
								${foreach sum_articles_1day as s where s->internal_id = p->internal_id limit 1}
									${args->n_viewed_1day:default('${s->n_viewed*1} viewed today ${if s-&gt;n_goal &gt; 0}
<div>${s->n_goal*1}&nbsp; downloads today</div>
${end}')}
									<span ontplready="this._v='${s->n_viewed:html}'|0; this._g='${s->n_goal:html}'|0"></span>
								${end}
								${block->hide_no_view_1day}
								<span ontplready="var p=this.previousElementSibling||{}; if (ns==window._S_T) if ((p._v|0) < ('${args->hide_no_view_1day:html:default(3)}'|0) || (p._g|0) < ('${args->hide_no_goal_1day:html:default(1)}'|0)) this.parentNode.style.display='none'"></span>
							</div>

							${block->stats_week:default(0)}
							<div style="${args->text_style_week:html:default('padding:1em 0')}">
								${foreach sum_articles_week as s where s->internal_id = p->internal_id limit 1}
									${args->n_viewed_week:default('<span style="font-size:14px;">This article has been popular in the last week!</span><br />
&nbsp;
<div><span style="color:#fac200;"><strong>${s->n_viewed*1} viewed</strong></span></div>
${if s-&gt;n_goal &gt; 0}

<div><span style="color:#fac200;"><strong>${s->n_goal*1} downloads</strong></span></div>
${end}')}
									<span ontplready="this._v='${s->n_viewed:html}'|0; this._g='${s->n_goal:html}'|0"></span>
								${end}
								${block->hide_no_view_week}
								<span ontplready="var p=this.previousElementSibling||{}; if (ns==window._S_T) if ((p._v|0) < ('${args->hide_no_view_week:html}'|0) || (p._g|0) < ('${args->hide_no_goal_week:html}'|0)) this.parentNode.style.display='none'"></span>
							</div>

							<div style="clear:left;"></div>
							<div style="margin:auto; box-sizing:border-box; font-size:1px">
								<div data-style="display:inline-block; background-color:${args->border_color:html}; ${args->a_css_2:html:default('width: 100px;
height: 0px;
max-width: 80%;
')}"></div>
							</div>
							${block->description:default(0)}
							<div data-style="margin:auto; box-sizing:border-box; width:${args->img_width:html}">
								<div data-style="display:inline-block; ${args->a_css_3:html:default('font-size: 16px;
color: #777777;
line-height: 24px;
text-align: left;
padding-top: 0px;
padding-right: 10px;
padding-bottom: 3px;
padding-left: 10px;
margin-top: 0px;
margin-right: 0px;
margin-bottom: 10px;
margin-left: 0px;
')}; padding-bottom:0">
									${p->description}
								</div>
							</div>

							${block->with_link_button:default(0)}
							<div data-style="box-sizing:border-box; ${args->link_button_box_style:html:default('text-align: left;
')}">
								<a class="$flat_btn" href="${args->link_button_href:html:default('${p->content_url}')}" data-style="box-sizing:border-box; ${args->link_button_style:html:default('color: rgb(39, 36, 70);
padding-top: 9px;
padding-right: 13px;
padding-bottom: 9px;
padding-left: 13px;
font-size: 14px;
line-height: 14px;
font-weight: 700;
font-family: Lato;
margin: 15px;
background-color: rgba(245, 36, 36, 0);
width: auto;
')}" hover_style="${args->link_button_style_hover:html:default('color: rgb(7, 3, 3);
padding-top: 9px;
padding-right: 13px;
padding-bottom: 9px;
padding-left: 13px;
font-size: 14px;
line-height: 14px;
font-weight: 700;
font-family: Lato;
transition: none;
margin: 15px;
background-color: rgb(237, 238, 227);
width: auto;
')}">
									${args->link_button_text:default(Read more)}
								</a>
							</div>
						</td>
					${end}
				</tr>
			</table>
			${block->pagination:default(0)}
			<div id="tsp" class="$table_slider_pagination" slider_id="ts" selected_color="${args->pagination_color_on:html:default('rgba(0, 0, 0, 1)')}" style="${args->pagination_color:html}"></div>
		</div>
	</div>
</div>

${menu name='Frame', icon='th-large'}
	${menu args->style name='Style', type='css', param='with_responsive=1'}
	${menu args->content_padding name='Content box padding', type='css', param='with_responsive=1'}
	${menu args->round name='No cut cell', type='checkbox', param='value_off=', param='value_on=1'}
	${menu args->eq_cell_width name='Equal cell width', type='checkbox', param='value_off=', param='value_on=1'}
	${menu args->eq_cell_height name='Equal cell height', type='checkbox', param='value_off=', param='value_on=1'}
	${menu args->space_between_items name='Space between items', type='css_length', param='with_responsive=1'}
	${menu args->border_color name='Border color', type='color'}
	${menu args->round_border name='Round border', type='css_length'}
	${menu args->direction name='Localization settings', type='select', param='options=[["Left to right","ltr"],["Right to left","rtl"]]'}
	${menu args->url_params name='URL additional parameters', type='external_media_url_params'}
${menu name='Logo', icon='bars'}
	${menu block->with_logo name='With logo'}
	${menu args->logo_src name='Logo image', type='media_url'}
	${menu args->logo_block_style name='Logo block style', type='css'}
	${menu args->logo_text name='Text below logo'}
	${menu args->logo_text_style name='Text below logo - style', type='css'}
${menu name='Slider options', icon='arrow-right'}
	${menu block->with_arrows name='With arrow buttons'}
	${menu args->btn_style name='Arrow button style', type='css'}
	${menu args->btn_hover_style name='Arrow button style: hover', type='css'}
	${menu args->hide_buttons name='Hide arrow buttons when nothing to scroll', type='checkbox', param='value_off=', param='value_on=1', visible_if='block.title-0 && block.with_arrows-0'}
	${menu args->buttons_always name='Show arrows even when mouse doesn''t hover', type='checkbox', param='value_off=', param='value_on=1', visible_if='!(block.with_arrows-0)'}
	${menu args->with_slider name='Use slider widget', type='checkbox', param='value_off=1', param='value_on=', onchange='if (args.with_slider==1) block.with_arrows = block.pagination = 0'}
	${menu args->with_scrollbar name='Slider with scrollbar', type='checkbox', param='value_off=', param='value_on=1', visible_if='args.with_slider!=1'}
	${menu args->hide_scrollbar name='Hide scrollbar', type='checkbox', param='value_off=', param='value_on=1', visible_if='args.with_slider!=1 && args.with_scrollbar==1'}
	${menu args->scrollbar_style name='Scrollbar style', type='css', visible_if='args.with_slider!=1 && args.with_scrollbar==1'}
	${menu args->for_max_vw name='Slider widget only if screen width is less than or equal to', type='css_length', param='with_options=always', visible_if='args.with_slider!=1'}
	${menu args->arrow_back_img name='Left arrow image', type='arrow', visible_if='args.with_slider!=1'}
	${menu args->arrow_style name='Arrows style', type='css', visible_if='args.with_slider!=1'}
	${menu args->arrows_offset name='Slider arrows offset', type='number', visible_if='args.with_slider!=1'}
	${menu args->arrows_line name='Arrows in the middle of images', type='checkbox', param='value_off=-1', param='value_on=0', visible_if='args.with_slider!=1'}
	${menu block->pagination name='With slider pagination', visible_if='args.with_slider!=1'}
	${menu args->pagination_color_on name='Bullet Selected Color', type='color', visible_if='args.with_slider!=1'}
	${menu args->pagination_color name='Bullet style', type='css', visible_if='args.with_slider!=1'}
${menu name='Widget title', icon='bookmark'}
	${menu block->title name='With title bar'}
	${menu args->title name='Text'}
	${menu args->title_bg name='Style', type='css', param='with_responsive=1'}
	${menu args->title_style name='Title style', type='css', param='with_responsive=1'}
${menu name='Close button', icon='close'}
	${menu block->x name='With close button'}
	${menu args->x name='Close button', type='dontshowagain', param='style=cursor:pointer; vertical-align:middle'}
	${menu args->x_style name='Close button position', type='css'}
${menu name='Image/Cell width', icon='image'}
	${menu args->img_width name='Cell width', type='css_length', param='with_responsive=1'}
	${menu args->img_max_height name='Image maximum height', type='css_length', param='with_responsive=1'}
	${menu p->image_big_url name='Item image', column_tags='image'}
${menu name='Zoom image on hover', icon='bars'}
	${menu args->img_zoom_on_hover name='Zoom %', type='number'}
${menu name='New badge', icon='align-justify', description='Set "New" badge to appear for items debut recently.
You may choose a time frame for an article to be considered new. For new accounts/articles feed, all articles are new until the day setting condition has been met.'}
	${menu block->with_new_badge name='With new badge'}
	${menu args->badge_if_newer name='Show NEW badge if newer than', type='date', param='is_span=true', param='format=%0..999d days'}
	${menu args->new_badge_style name='Badge style', type='css', param='with_responsive=1'}
	${menu args->new_badge_text_style name='Badge text style', type='css', param='with_responsive=1'}
	${menu args->new_badge_text name='Text'}
${menu name='Time-based badge', icon='align-justify'}
	${menu block->with_time_badge name='With time-based badge'}
	${menu args->time_badge_style name='Badge style', type='css', param='with_responsive=1'}
	${menu args->time_badge_text_style name='Badge text style', type='css', param='with_responsive=1'}
	${menu args->time_badge_text name='Text'}
	${menu p->custom_i_1 name='Catalog field with end date', description='UNIX-timestamp'}
	${menu block->with_time_badge_countdown name='With days/time remaining'}
	${menu args->time_badge_days name='Time remaining: "days" text'}
	${menu args->time_badge_hr name='Time remaining: "hours" text'}
	${menu args->time_badge_min name='Time remaining: "minutes" text'}
	${menu args->time_badge_sec name='Time remaining: "seconds" text'}
${menu name='Add to wishlist', icon='bars', description='Show save to wishlist icon, on click item will be saved to Personyze wishlist. Items can be included in email/site widgets when using the wishlist algorithm. You can also set JS to report to your site when a visitor is saving an item to a wishlist.'}
	${menu block->with_wishlist_badge name='With add to wishlist'}
	${menu args->wishlist_style name='Style', type='css'}
	${menu args->wishlist_off_style name='Off icon style', type='css'}
	${menu args->wishlist_add_text name='Off tooltip (add to wishlist)'}
	${menu args->wishlist_on_style name='On icon style', type='css'}
	${menu args->wishlist_rm_text name='On tooltip (remove from wishlist)'}
${menu name='Icon or text badge', icon='star', description='Show text taken from catalog field'}
	${menu block->with_db_badge name='With db badge'}
	${menu args->db_badge_style name='Block style', type='css'}
	${menu block->with_db_badge_icon name='With icon'}
	${menu args->db_badge_text_icon name='Icon', type='icon'}
	${menu args->db_badge_text_style name='Icon style', type='css'}
	${menu args->db_badge_text name='Text'}
${menu name='Custom column', icon='database', description='Select additional field to show.'}
	${menu block->with_custom_column name='With custom column'}
	${menu args->custom_column name='Date column'}
	${menu args->custom_column_style name='Style', type='css'}
${menu name='Article text/desc', icon='align-justify'}
	${menu block->description name='With description'}
	${menu args->p_description name='Item text'}
	${menu p->description name='Item text'}
	${menu args->a_css name='Text style', type='css', param='with_responsive=1'}
	${menu args->a_hover_color name='Text on hover color', type='color'}
	${menu args->a_css_3 name='Text color', type='css', param='with_responsive=1'}
	${menu args->a_css_2 name='Ruler', type='css', param='with_responsive=1'}
${menu name='Link button', icon='mouse-pointer'}
	${menu block->with_link_button name='With link button'}
	${menu args->link_button_href name='Link target URL'}
	${menu args->link_button_text name='Button text'}
	${menu args->link_button_box_style name='Box style', type='css', param='with_responsive=1'}
	${menu args->link_button_style name='Button style', type='css', param='with_responsive=1'}
	${menu args->link_button_style_hover name='Button hover style', type='css'}
${menu name='Onclick target URL', icon='link'}
	${menu p->content_url name='Link target URL', column_tags='url, custom text'}
	${menu args->target name='Open link in', type='a_target'}
${menu name='Date', icon='calendar', description='Show date.'}
	${menu block->with_date name='With date'}
	${menu args->date_column name='Date column'}
	${menu args->date_column_format name='Date format'}
	${menu args->date_column_style name='Style', type='css'}
${menu name='Rating', icon='star', description='Show article rating when available
This requires you to populate "Rank" on your article feed.'}
	${menu block->rating name='With rating'}
	${menu p->rank name='Rating'}
	${menu args->rating_style name='Colors', type='css', param='vars=--bgcolor:color; --border-color:color'}
${menu name='Site statistics: 1-day', icon='bar-chart', description='Show number of viewed or purchases in the last 24 hours for a given item as tracked by Personyze. You can set a condition not to show if the number of views/purchases is below X number.'}
	${menu block->stats_1day name='Site statistics: 1day'}
	${menu args->text_style_1day name='Style', type='css'}
	${menu args->n_viewed_1day name='Text'}
	${menu block->hide_no_view_1day name='Hide statistics if no views'}
	${menu args->hide_no_view_1day name='Hide statistics if less views than', type='number', param='min=0'}
	${menu args->hide_no_goal_1day name='Hide statistics if less purchases than', type='number', param='min=0'}
${menu name='Site statistics: week', icon='bar-chart', description='Show number of viewed or purchases in the last week for a given item as tracked by Personyze. You can set a condition not to show if the number of views/purchases is below X number.'}
	${menu block->stats_week name='Site statistics: week'}
	${menu args->text_style_week name='Style', type='css'}
	${menu args->n_viewed_week name='Text'}
	${menu block->hide_no_view_week name='Hide statistics if no views'}
	${menu args->hide_no_view_week name='Hide statistics if less views than', type='number', param='min=0'}
	${menu args->hide_no_goal_week name='Hide statistics if less purchases than', type='number', param='min=0'}
```


