## Text only



```
<div class="$responsive" data-style="text-align: center; display:inline-block; ${args->style:html:default('border: none;
font-family: Apercu, Arial, Helvetica, sans-serif;
margin-right: auto;
margin-left: auto;
display: block;
background-color: rgb(256, 256, 256);
width: auto;
')}">
	${block->title:default(1)}
	<table data-style="width:100%; border-collapse:collapse;border:none; margin: 0 auto; ${args->title_bg:html}">
		<tr>
			<td data-style="vertical-align:middle; ${args->title_style:html:default('padding-top: 7px;
padding-right: 0px;
padding-bottom: 0px;
padding-left: 12px;
color: black;
font-size: 14px;
text-align: center;
font-family: Apercu, Arial, Helvetica, sans-serif;
font-weight: 700;
line-height: 22px;
letter-spacing: normal;
')}">
				${args->title:default('<br />
<span style="font-size:28px;">TRENDING&nbsp; CATEGORIES</span><br />
&nbsp;')}
			</td>
			${block->with_arrows:default(0)}
			<td style="width:1px; white-space:nowrap; vertical-align:middle">
				<a id="button_back" class="$flat_btn" style="${args->btn_style:html}" hover_style="${args->btn_hover_style:html}">&lt;</a>
				<a id="button_forward" class="$flat_btn" style="${args->btn_style:html}" hover_style="${args->btn_hover_style:html}">&gt;</a>
			</td>
			${block->x:default(0)}
			<td style="width:1px; white-space:nowrap; ${args->x_style:html}">
				${args->x:default('<div onmouseenter="this.style.backgroundColor=this.style.outlineColor" onmouseleave="this.style.backgroundColor=this.style.textDecorationColor" style="display: inline-block; vertical-align: text-bottom; width: 24px; height: 24px; box-sizing: border-box; border-radius: 50%; border: 2px solid; -webkit-box-shadow: rgba(255, 255, 255, 0.2) 0px 1px 0px inset, rgba(0, 0, 0, 0.2) 0px 1px 2px; padding: 3px; background-color: rgb(207, 120, 58); text-decoration-color: rgb(207, 120, 58); outline-color: rgb(206, 54, 64); outline-width: 10px; color: rgb(10, 4, 4); cursor: pointer; transition: all 0.3s ease 0s;" class="$personyze_button_dont_show_again" data-action_id="${action_id}"><div style="display: block; width: 100%; height: 100%; transition: all 0.3s ease 0s; border-radius: 50%; background-image: linear-gradient(-45deg, transparent 0%, transparent 46%, currentcolor 46%, currentcolor 56%, transparent 56%, transparent 100%), linear-gradient(45deg, transparent 0%, transparent 46%, currentcolor 46%, currentcolor 56%, transparent 56%, transparent 100%);"></div></div>')}
			</td>
		</tr>
	</table>
<table style="width:auto; border-collapse:separate; border-spacing:${args->cell_spacing:html:default(20px)} 0; margin:0 -${args->cell_spacing:html}">
            <tr id="ts" class="$table_slider" data-disabled="${args->with_slider:html}" data-with_scrollbar="${args->with_scrollbar:html}" data-scrollbar_style="${args->scrollbar_style:html}" data-hide_scrollbar="${args->hide_scrollbar:html}" style="width: 74%; padding: 0; margin-left:auto; margin-right:auto; box-sizing: border-box; border:none; max-width:${args->width:html:default(1000px)}" for_max_vw="${args->for_max_vw:html:default(always)}" eq_cell_width="${args->eq_cell_width:html:default(1)}" eq_cell_height="${args->eq_cell_height:html:default(1)}" arrows_line="${args->arrows_line:html:default(0)}" arrow_back_img="${args->arrow_back_img:html:default('https://cdn.personyze.com/upload/4545/96b6126f483ffd5a.png')}" arrow_style="${args->arrow_style:html:default('background-color: rgb(256, 256, 256);
max-height: none;
padding-top: 58px;
padding-right: 2px;
padding-bottom: 7px;
padding-left: 2px;
width: 42px;
')}" pagination_id="tsp" arrow_back_id="button_back" arrow_forward_id="button_forward" arrows_offset="${args->arrows_offset:html:default(-10)}" hide_buttons="${args->hide_buttons:html}" buttons_always="${args->buttons_always:html}">
			${foreach categories_sum_products as p where p->for_period='recently' and (p->title IS NOT NULL AND p->title!='') order by p->n_viewed desc limit 5}
				<td data-style="padding:0; text-align:center; background-color:white; ${args->td_css:html:default('vertical-align: middle;
box-shadow: none;
max-width: 230px;
min-width: 0;
')}">
					<a href="${args->p_content_url:html:default('${p->content_url}')}">
						<div data-style="${args->div_css:html:default('background-color: #ffffff;
padding: 4px;')}">

						</div>
					</a>
					<a href="${args->p_content_url:html}" target="_blank">
						<div data-style="display:inline-block; text-align:left; text-align:start; ${args->a_css:html:default('color: BLACK;
font-size: sel(14px, 5vw);
padding-top: 0px;
padding-right: 0px;
padding-bottom: 15px;
padding-left: 0px;
text-align: center;
font-family: Apercu, Arial, Helvetica, sans-serif;
text-decoration: none;
line-height: 23px;
font-weight: 700;
width: 160px;
')}">
							${args->p_title:default('<span style="font-size:16px;"><span style="direction: ltr;
-webkit-box-direction: normal;
font-family: Apercu, Arial, Helvetica, sans-serif;
font-weight: lighter;
letter-spacing: 0.025em;
text-transform: capitalize;
text-align: left;
-webkit-tap-highlight-color: rgba(255,255,255,0);
box-sizing: border-box;
-webkit-font-smoothing: antialiased;
text-decoration: none;
color: rgb(0, 0, 0);
font-size:sel(24px,24px);">${p->title}</span></span><br />
<span style="font-size:14px;"><span style="direction: ltr;
-webkit-box-direction: normal;
font-family: Apercu, Arial, Helvetica, sans-serif;
font-weight: lighter;
letter-spacing: 0.025em;
text-transform: capitalize;
text-align: left;
-webkit-tap-highlight-color: rgba(255,255,255,0);
box-sizing: border-box;
-webkit-font-smoothing: antialiased;
text-decoration: none;
color: rgb(0, 0, 0);
font-size:sel(24px,24px);"><strong>${p->topic}</strong></span></span>')}
						</div>
					</a>
				</td>
			${end}
		</tr>
	</table>
</div>

${menu name='Frame', icon='th-large'}
	${menu args->width name='Widget maximum width', type='css_length', param='with_options=none'}
	${menu args->style name='Style', type='css', param='with_responsive=1'}
	${menu args->eq_cell_width name='Equal cell width', type='checkbox', param='value_off=', param='value_on=1'}
	${menu args->eq_cell_height name='Equal rows height', type='checkbox', param='value_off=', param='value_on=1'}
	${menu args->td_css name='Cell style', type='css', param='with_responsive=1'}
${menu name='With slider', icon='arrow-right'}
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
	${menu args->arrow_back_img name='Left arrow image', type='personyze_media_url', visible_if='args.with_slider!=1'}
	${menu args->arrow_style name='Arrows style', type='css', visible_if='args.with_slider!=1'}
	${menu args->arrows_offset name='Slider arrows offset', type='number', visible_if='args.with_slider!=1'}
	${menu args->arrows_line name='Arrows in the middle of images', type='checkbox', param='value_off=-1', param='value_on=0', visible_if='args.with_slider!=1'}
${menu name='Title', icon='bookmark'}
	${menu block->title name='With title bar'}
	${menu args->title name='Text'}
	${menu args->title_bg name='Style', type='css', param='with_responsive=1'}
	${menu args->title_style name='Title style', type='css', param='with_responsive=1'}
${menu name='With slider arrows', icon='arrows-h'}
	${menu block->with_arrows name='With arrow buttons'}
	${menu args->btn_style name='Arrow button style', type='css'}
	${menu args->btn_hover_style name='Arrow button style: hover', type='css'}
${menu name='Close button', icon='close'}
	${menu block->x name='With close button'}
	${menu args->x name='Close button', type='dontshowagain', param='style=cursor:pointer; vertical-align:middle'}
	${menu args->x_style name='Close button position', type='css'}
${menu name='Image', icon='image'}
	${menu args->div_css name='Image background', type='css', param='with_responsive=1'}
${menu name='Text', icon='align-justify'}
	${menu args->p_title name='Item text'}
	${menu args->a_css name='Text color', type='css', param='with_responsive=1'}
${menu name='Link target URL', icon='link'}
	${menu args->p_content_url name='Link target URL', column_tags='url, custom text'}
```


## With widget title on the left



```
<div class="$responsive" data-style="text-align: center; display:inline-block; ${args->style:html:default('border: none;
font-family: Apercu, Arial, Helvetica, sans-serif;
margin-right: auto;
margin-left: auto;
display: flex;
')}">
	${block->title:default(1)}
	<table data-style="width:100%; border-collapse:collapse;border:none; margin: 0 auto; ${args->title_bg:html}">
		<tr>
			<td data-style="vertical-align:middle; ${args->title_style:html:default('padding-top: 0px;
padding-right: 0px;
padding-bottom: 0px;
padding-left: 12px;
color: black;
font-size: 19px;
text-align: center;
font-family: Apercu, Arial, Helvetica, sans-serif;
font-weight: 700;
line-height: 40px;
letter-spacing: normal;
text-transform: uppercase;
')}">
				${args->title:default('<span style="font-size:18px;">TRENDING CATEGORIES&nbsp;</span>')}
			</td>
			${block->with_arrows:default(0)}
			<td style="width:1px; white-space:nowrap; vertical-align:middle">
				<a id="button_back" class="$flat_btn" style="${args->btn_style:html}" hover_style="${args->btn_hover_style:html}">&lt;</a>
				<a id="button_forward" class="$flat_btn" style="${args->btn_style:html}" hover_style="${args->btn_hover_style:html}">&gt;</a>
			</td>
			${block->x:default(0)}
			<td style="width:1px; white-space:nowrap; ${args->x_style:html}">
				${args->x}
			</td>
		</tr>
	</table>
<table style="width:auto; border-collapse:separate; border-spacing:${args->cell_spacing:html:default(20px)} 0; margin:0 -${args->cell_spacing:html}">
            <tr id="ts" class="$table_slider" data-disabled="${args->with_slider:html}" data-with_scrollbar="${args->with_scrollbar:html}" data-scrollbar_style="${args->scrollbar_style:html}" data-hide_scrollbar="${args->hide_scrollbar:html}" style="width: 74%; padding: 0; margin-left:auto; margin-right:auto; box-sizing: border-box; border:none; max-width:${args->width:html:default(80vw)}" for_max_vw="${args->for_max_vw:html:default(always)}" eq_cell_width="${args->eq_cell_width:html:default(1)}" eq_cell_height="${args->eq_cell_height:html:default(1)}" arrows_line="${args->arrows_line:html:default(0)}" arrow_back_img="${args->arrow_back_img:html:default('https://cdn.personyze.com/upload/4545/96b6126f483ffd5a.png')}" arrow_style="${args->arrow_style:html:default('background-color: #ffffff;
max-height: none;
padding-top: 7px;
padding-right: 2px;
padding-bottom: 7px;
padding-left: 2px;
width: 44px;
')}" pagination_id="tsp" arrow_back_id="button_back" arrow_forward_id="button_forward" arrows_offset="${args->arrows_offset:html:default(-10)}" hide_buttons="${args->hide_buttons:html}" buttons_always="${args->buttons_always:html}">
			${foreach categories_sum_products as p where p->for_period='recently' order by p->n_viewed desc limit 15}
				<td data-style="padding:0; text-align:center; background-color:white; ${args->td_css:html:default('vertical-align: middle;
box-shadow: none;
max-width: 230px;
min-width: 0;
')}">
					<a href="${args->p_content_url:html:default('${p->content_url}')}">
						<div data-style="${args->div_css:html:default('background-color: #ffffff;
padding: 4px;')}">
							<img src="${p->image_big_url:html}" data-style="${args->img_css:html:default('width: auto;
height: auto;
max-width: 165px;
min-height: 100px;
')}">
						</div>
					</a>
					<a href="${args->p_content_url:html}" target="_blank">
						<div data-style="display:inline-block; text-align:left; text-align:start; ${args->a_css:html:default('color: BLACK;
font-size: sel(14px, 5vw);
padding-top: 0px;
padding-right: 5px;
padding-bottom: 0px;
padding-left: 5px;
text-align: center;
font-family: Apercu, Arial, Helvetica, sans-serif;
text-decoration: none;
line-height: 23px;
font-weight: 500;
')}">
							${args->p_title:default('${p->title}')}
						</div>
					</a>
				</td>
			${end}
		</tr>
	</table>
</div>

${menu name='Frame', icon='th-large'}
	${menu args->width name='Widget maximum width', type='css_length', param='with_options=none'}
	${menu args->style name='Style', type='css', param='with_responsive=1'}
	${menu args->eq_cell_width name='EqualCell width', type='checkbox', param='value_off=', param='value_on=1'}
	${menu args->eq_cell_height name='Equal Cell Hight', type='checkbox', param='value_off=', param='value_on=1'}
	${menu args->td_css name='Cell CSS', type='css', param='with_responsive=1'}
${menu name='With slider', icon='arrow-right'}
	${menu block->with_arrows name='Met pijl knoppen'}
	${menu args->btn_style name='Pijl knop stijl', type='css'}
	${menu args->btn_hover_style name='Pijl knop stijl: hover', type='css'}
	${menu args->hide_buttons name='Hide arrow buttons when nothing to scroll', type='checkbox', param='value_off=', param='value_on=1', visible_if='block.title-0 && block.with_arrows-0'}
	${menu args->with_slider name='Use slider widget', type='checkbox', param='value_off=1', param='value_on=', onchange='if (args.with_slider==1) block.with_arrows = block.pagination = 0'}
	${menu args->for_max_vw name='Slider widget only if screen width is less than or equal to', type='css_length', param='with_options=always', visible_if='args.with_slider!=1'}
	${menu args->arrow_back_img name='Left arrow image', type='personyze_media_url', visible_if='args.with_slider!=1'}
	${menu args->arrow_style name='Arrows style', type='css', visible_if='args.with_slider!=1'}
	${menu args->arrows_offset name='Slider arrows offset', type='number', visible_if='args.with_slider!=1'}
	${menu args->arrows_line name='Arrows in the middle of images', type='checkbox', param='value_off=-1', param='value_on=0', visible_if='args.with_slider!=1'}
${menu name='Title', icon='bookmark'}
	${menu block->title name='With title bar'}
	${menu args->title name='Text'}
	${menu args->title_bg name='Style', type='css', param='with_responsive=1'}
	${menu args->title_style name='Title style', type='css', param='with_responsive=1'}
${menu name='Close button', icon='close'}
	${menu block->x name='With close button'}
	${menu args->x name='Close button', type='dontshowagain', param='style=cursor:pointer; vertical-align:middle'}
	${menu args->x_style name='Close button position', type='css'}
${menu name='Image', icon='image'}
	${menu p->image_big_url name='Image URL', column_tags='image'}
	${menu args->img_css name='Image Style', type='css', param='with_responsive=1'}
	${menu args->div_css name='BAckground image style', type='css', param='with_responsive=1'}
${menu name='Text', icon='align-justify'}
	${menu args->p_title name='Category text'}
	${menu args->a_css name='Text style', type='css', param='with_responsive=1'}
${menu name='Link target URL', icon='link'}
	${menu args->p_content_url name='Link target URL', column_tags='url, custom text'}
```


