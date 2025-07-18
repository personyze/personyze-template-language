## Number of views/purchases in a time range



```
<div id=st_w class="$responsive" data-style="display:inline-block; position:relative; ${args->style:html:default('padding-top: sel(5px, 1px);
	padding-right: sel(15px, 4px);
	padding-bottom: 0px;
	padding-left: sel(15px, 4px);
	text-align: left;
	font-weight: bold;
	font-size: sel(16px, 12px);
	box-sizing: border-box;
	width: sel(350px, auto);
	font-family: Roboto,sans-serif;
	box-shadow: 0 0px 0px 0 rgba(0,0,0,0.08);
	background-color: #C70039;
	color: rgb(255, 256, 256);
	border-radius: 40px;
	margin: 5px;')}" onupdate="
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

		${block->show_close_button:default(1)}
		<div data-style="position:absolute; cursor:pointer; ${args->close_button_style:html:default('right:25px;
	top: 15px;')}">
			${args->close_button:default('<div onmouseenter="this.style.backgroundColor=this.style.outlineColor" onmouseleave="this.style.backgroundColor=this.style.textDecorationColor" style="display: inline-block; vertical-align: text-bottom; width: 24px; height: 24px; box-sizing: border-box; border-top-left-radius: 50%; border-top-right-radius: 50%; border-bottom-right-radius: 50%; border-bottom-left-radius: 50%; border: 0px solid; -webkit-box-shadow: none; padding: 2px; background-color: rgba(0, 0, 0, 0); text-decoration-color: rgba(0, 0, 0, 0); outline-color: rgb(206, 54, 64); outline-width: 15px; color: rgb(10, 4, 4); cursor: pointer; transition: all 0.3s ease;" class="$personyze_button_dont_show_again" data-action_id="${action_id}"><div style="display: block; width: 100%; height: 100%; transition: all 0.3s ease 0s; border-top-left-radius: 50%; border-top-right-radius: 50%; border-bottom-right-radius: 50%; border-bottom-left-radius: 50%; background-image: linear-gradient(-45deg, transparent 0%, transparent 43%, currentcolor 43%, currentcolor 59%, transparent 59%, transparent 100%), linear-gradient(45deg, transparent 0%, transparent 43%, currentcolor 43%, currentcolor 59%, transparent 59%, transparent 100%);"></div></div>')}
		</div>

		${block->title:default(1)}
		<table data-style="width:98%; margin-right: 1%; margin-left: 1%; border-collapse:collapse; border:none; ${args->title_bg:html:default('background-color: rgba(0, 0, 0, 0);
	margin-top: 0px;
	margin-right: 0;
	margin-bottom: 0px;
	padding-top: 0px;
	padding-right: 0;
	padding-bottom: 0px;
	padding-left: 0;
	border-bottom: none;')}">
			<tr>
				<td data-style="vertical-align:middle; ${args->title_style:html}">
					${args->title}
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
		<table style="width:100%; border-collapse:separate; border-spacing:12px 0">
			<tr id="ts" class="$table_slider" data-disabled="${args->with_slider:html:default(1)}" style="width: 100%; padding: 0 1%; box-sizing: border-box; border:none; max-width:${args->width:html:default(none)}" for_max_vw="${args->for_max_vw:html}" eq_cell_width="${args->eq_cell_width:html:default(1)}" arrows_line="${args->arrows_line:html}" arrow_back_img="${args->arrow_back_img:html}" arrow_style="${args->arrow_style:html}" pagination_id="tsp" arrow_back_id="button_back" arrow_forward_id="button_forward" arrows_offset="${args->arrows_offset:html}" hide_buttons="${args->hide_buttons:html}">
				${foreach products_interactions as p where p->interaction_status in ('viewed','extra','favorite') and p->last_interaction_time>=tm order by p->last_interaction_time desc limit 1}
					<td style="position:relative; padding:0; text-align:center; vertical-align:top; border:solid ${args->border_color:html:default('rgba(178, 32, 32, 0)')} 1px">
						${block->img:default(0)}
						<a data-personyze-click-target="products ${p->internal_id:html}" href="${p->cart_url:html}" target="${args->target:html}" data-style="display:block; margin:auto; box-sizing:border-box; width:${args->img_width:html:default(0)}">
							<img src="${p->image_big_url:html}" data-style="width:auto; height:auto; max-width:100%; max-height:${args->img_max_height:html}">
						</a>
						${block->rating:default(0)}
						<div style="margin: auto; margin-bottom: .6em">
							<div style="width: 69px; height: 13px; font-size: 0; line-height: 0; background: url(https://skin.christys-hats.com/frontend/ultimo/totalRecall/images/img/rating.png) 0 0 repeat-x; text-indent: -999em; overflow: hidden; margin-left: 0; margin-right: 0; display: inline-block; vertical-align: middle;">
								<div style="float: left; height: 13px; background: url(https://skin.christys-hats.com/frontend/ultimo/totalRecall/images/img/rating.png) 0 100% repeat-x; width: ${p->rank:html:default(0)}%">
								</div>
							</div>
						</div>
						<div style="clear:left;"></div>

						${block->stats_recently:default(0)}
						<span data-style="${args->text_style_recently:html}">
							${foreach sum_products_recently as s where s->internal_id = p->internal_id limit 1}
								${args->n_viewed_recently:default('&nbsp;
<div><span style="color:#000000;"><strong>&nbsp;</strong></span><span style="color:#ffffff;"><strong><img src="https://cdn.personyze.com/upload/5219/5da962a711c810f6.png" />Good choice! This product has been popular in the last days!</strong></span><br />
<strong>&nbsp; </strong>
<div><strong><span style="color:#fac200;"><strong>${s->n_viewed} viewed</strong></span></strong></div>
<strong> </strong>

<div><strong><span style="color:#fac200;"><strong>${s->n_goal} purchased</strong></span></strong></div>
<strong> </strong></div>

<div><strong>&nbsp;</strong></div>
')}
								<span ontplready="this._v='${s->n_viewed:html}'|0; this._g='${s->n_goal:html}'|0"></span>
							${end}
							${block->hide_no_view_recently}
							<span ontplready="var p=this.previousElementSibling||{}; if ((p._v|0) < ('${args->hide_no_view_recently:html:default(10)}'|0) || (p._g|0) < ('${args->hide_no_goal_recently:html:default(7)}'|0)) _S_T.dismiss_action(${action_id:html})"></span>
						</span>

						${block->stats_1day:default(0)}
						<span data-style="${args->text_style_1day:html}">
							${foreach sum_products_1day as s where s->internal_id = p->internal_id limit 1}
								${args->n_viewed_1day:default('&nbsp;
<div><span style="color:#000000;"><strong>&nbsp;</strong></span><span style="color:#ffffff;"><strong><img src="https://cdn.personyze.com/upload/5219/5da962a711c810f6.png" />Good choice! This product has been popular in the last 24 hours!</strong></span><br />
<strong>&nbsp; </strong>
<div><strong><span style="color:#fac200;"><strong>${s->n_viewed} viewed</strong></span></strong></div>
<strong> </strong>

<div><strong><span style="color:#fac200;"><strong>${s->n_goal} purchased</strong></span></strong></div>
<strong> </strong></div>

<div><strong>&nbsp;</strong></div>
')}
								<span ontplready="this._v='${s->n_viewed:html}'|0; this._g='${s->n_goal:html}'|0"></span>
							${end}
							${block->hide_no_view_1day}
							<span ontplready="var p=this.previousElementSibling||{}; if ((p._v|0) < ('${args->hide_no_view_1day:html:default(10)}'|0) || (p._g|0) < ('${args->hide_no_goal_1day:html:default(7)}'|0)) _S_T.dismiss_action(${action_id:html})"></span>
						</span>

						${block->stats_2day:default(1)}
						<span data-style="${args->text_style_2day:html}">
							${foreach sum_products_2day as s where s->internal_id = p->internal_id limit 1}
								${args->n_viewed_2day:default('&nbsp;
<div><span style="color:#000000;"><strong>&nbsp;</strong></span><span style="color:#ffffff;"><strong><img src="https://cdn.personyze.com/upload/5219/5da962a711c810f6.png" />Good choice! This product has been popular in the last 48 hours!</strong></span><br />
<strong>&nbsp; </strong>
<div><strong><span style="color:#fac200;"><strong>${s->n_viewed} viewed</strong></span></strong></div>
<strong> </strong>

<div><strong><span style="color:#fac200;"><strong>${s->n_goal} purchased</strong></span></strong></div>
<strong> </strong></div>

<div><strong>&nbsp;</strong></div>
')}
								<span ontplready="this._v='${s->n_viewed:html}'|0; this._g='${s->n_goal:html}'|0"></span>
							${end}
							${block->hide_no_view_2day:default(1)}
							<span ontplready="var p=this.previousElementSibling||{}; if ((p._v|0) < ('${args->hide_no_view_2day:html:default(1)}'|0) || (p._g|0) < ('${args->hide_no_goal_2day:html}'|0)) _S_T.dismiss_action(${action_id:html})"></span>
						</span>

						${block->stats_4day:default(0)}
						<span data-style="${args->text_style_4day:html}">
							${foreach sum_products_4day as s where s->internal_id = p->internal_id limit 1}
								${args->n_viewed_4day:default('&nbsp;
<div><span style="color:#000000;"><strong>&nbsp;</strong></span><span style="color:#ffffff;"><strong><img src="https://cdn.personyze.com/upload/5219/5da962a711c810f6.png" />Good choice! This product has been popular in the last 4 days!</strong></span><br />
<strong>&nbsp; </strong>
<div><strong><span style="color:#fac200;"><strong>${s->n_viewed} viewed</strong></span></strong></div>
<strong> </strong>

<div><strong><span style="color:#fac200;"><strong>${s->n_goal} purchased</strong></span></strong></div>
<strong> </strong></div>

<div><strong>&nbsp;</strong></div>
')}
								<span ontplready="this._v='${s->n_viewed:html}'|0; this._g='${s->n_goal:html}'|0"></span>
							${end}
							${block->hide_no_view_4day}
							<span ontplready="var p=this.previousElementSibling||{}; if ((p._v|0) < ('${args->hide_no_view_4day:html:default(1)}'|0) || (p._g|0) < ('${args->hide_no_goal_4day:html}'|0)) _S_T.dismiss_action(${action_id:html})"></span>
						</span>

						${block->stats_week:default(0)}
						<span data-style="${args->text_style_week:html}">
							${foreach sum_products_week as s where s->internal_id = p->internal_id limit 1}
								${args->n_viewed_week:default('&nbsp;
<div><span style="color:#000000;"><strong>&nbsp;</strong></span><span style="color:#ffffff;"><strong><img src="https://cdn.personyze.com/upload/5219/5da962a711c810f6.png" />Good choice! This product has been popular in the last week!</strong></span><br />
<strong>&nbsp; </strong>
<div><strong><span style="color:#fac200;"><strong>${s->n_viewed} viewed</strong></span></strong></div>
<strong> </strong>

<div><strong><span style="color:#fac200;"><strong>${s->n_goal} purchased</strong></span></strong></div>
<strong> </strong></div>

<div><strong>&nbsp;</strong></div>
')}
								<span ontplready="this._v='${s->n_viewed:html}'|0; this._g='${s->n_goal:html}'|0"></span>
							${end}
							${block->hide_no_view_week}
							<span ontplready="var p=this.previousElementSibling||{}; if ((p._v|0) < ('${args->hide_no_view_week:html}'|0) || (p._g|0) < ('${args->hide_no_goal_week:html}'|0)) _S_T.dismiss_action(${action_id:html})"></span>
						</span>

						${block->price:default(0)}
						<div data-style="margin:auto; box-sizing:border-box; width:${args->img_width:html}; ${args->price_style:html}">
							${if p->price}
								${args->before_price}
								${if p->sale_price and p->sale_price < p->price}
									${p->sale_price:truncate(2):sprintf($%s)}
									<div style="${args->sale_style:html}">
										${p->price:truncate(2):sprintf($%s)}
									</div>
								${end}
								${if not p->sale_price or p->sale_price >= p->price}
									${p->price:truncate(2):sprintf($%s)}
								${end}
								${args->after_price}
							${end}
						</div>
						<div style="margin:auto; box-sizing:border-box; font-size:1px">
							<div data-style="display:inline-block; background-color:${args->border_color:html}; ${args->a_css_2:html:default('width: 100px;
height: 3px;
max-width: 80%;
')}"></div>
						</div>
						${block->description:default(0)}
						<div data-style="margin:auto; box-sizing:border-box; width:${args->img_width:html}">
							<div data-style="display:inline-block; ${args->a_css_3:html}; padding-bottom:0">
								${p->description}
							</div>
						</div>
						${block->button:default(0)}
						<div data-style="${args->button_spacer:html}">
							<a data-personyze-click-target="products ${p->internal_id:html}" href="${p->cart_url:html}" target="${args->target:html}" data-style="display:block; box-sizing:border-box; position:absolute; width:100%; height:0; display:none; left:0; bottom:0; ${args->a_css_4:html}" ontplready="
								var a=ns.new_elem(this), p=this.parentNode.parentNode;
								p.onmouseenter = p.onmouseleave = function(e)
								{	var on = e.type == 'mouseenter';
									a.add_style({height: on ? 'auto' : '0', display: on ? '' : 'none'}, {});
								};
							">
								<div style="display:inline-block; width:1em; height:1em; line-height:1; border-radius:50%; ${args->plus_style:html}">${args->button_add_plus}</div>
								${args->button_add_text}
							</a>
						</div>
					</td>
				${end}
			</tr>
		</table>
		${block->pagination}
		<div id="tsp" class="$table_slider_pagination" slider_id="ts" selected_color="${args->pagination_color_on:html:default('rgba(0, 0, 0, 1)')}" style="${args->pagination_color:html}"></div>
	</div>

${menu name='Frame', icon='th-large'}
	${menu args->width name='Widget maximum width', type='css_length', param='with_options=none'}
	${menu args->style name='Style', type='css', param='with_responsive=1'}
	${menu args->eq_cell_width name='Equal cell width', type='checkbox', param='value_off=', param='value_on=1'}
	${menu args->img_width name='Cell width', type='css_length', param='with_responsive=1'}
	${menu args->border_color name='Border color', type='color'}
	${menu args->img_max_height name='Image maximum height', type='css_length', param='with_responsive=1'}
${menu name='Close Button', icon='times-circle'}
	${menu block->show_close_button name='Show close button'}
	${menu args->close_button_style name='Close button style', type='css', param='with_responsive=1'}
	${menu args->close_button name='Close button', type='dontshowagain'}
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
${menu name='Image', icon='image'}
	${menu block->img name='With image'}
	${menu p->image_big_url name='Item image', column_tags='image'}
${menu name='Text', icon='align-justify'}
	${menu block->description name='With description'}
	${menu p->description name='Item text'}
	${menu args->a_css_3 name='Text color', type='css', param='with_responsive=1'}
	${menu args->a_css_2 name='Ruler', type='css', param='with_responsive=1'}
${menu name='Link target URL', icon='link'}
	${menu p->cart_url name='Link target URL', column_tags='url, custom text'}
	${menu args->target name='Open link in', type='a_target'}
${menu name='Rating', icon='star'}
	${menu block->rating name='With rating'}
	${menu p->rank name='Rating'}
${menu name='Site statistics: recently', icon='bar-chart'}
	${menu block->stats_recently name='Site statistics: recently'}
	${menu args->text_style_recently name='Style', type='css', param='with_responsive=1'}
	${menu args->n_viewed_recently name='Text'}
	${menu block->hide_no_view_recently name='Hide the widget if no views'}
	${menu args->hide_no_view_recently name='Hide the widget if less views than', type='number', param='min=0'}
	${menu args->hide_no_goal_recently name='Hide the widget if less purchases than', type='number', param='min=0'}
${menu name='Site statistics: 1-day', icon='bar-chart'}
	${menu block->stats_1day name='Site statistics: 1day'}
	${menu args->text_style_1day name='Style', type='css', param='with_responsive=1'}
	${menu args->n_viewed_1day name='Text'}
	${menu block->hide_no_view_1day name='Hide the widget if no views'}
	${menu args->hide_no_view_1day name='Hide the widget if less views than', type='number', param='min=0'}
	${menu args->hide_no_goal_1day name='Hide the widget if less purchases than', type='number', param='min=0'}
${menu name='Site statistics: 2-day', icon='bar-chart'}
	${menu block->stats_2day name='Site statistics: 2day'}
	${menu args->text_style_2day name='Style', type='css', param='with_responsive=1'}
	${menu args->n_viewed_2day name='Text'}
	${menu block->hide_no_view_2day name='Hide the widget if no views'}
	${menu args->hide_no_view_2day name='Hide the widget if less views than', type='number', param='min=0'}
	${menu args->hide_no_goal_2day name='Hide the widget if less purchases than', type='number', param='min=0'}
${menu name='Site statistics: 4-day', icon='bar-chart'}
	${menu block->stats_4day name='Site statistics: 4day'}
	${menu args->text_style_4day name='Style', type='css', param='with_responsive=1'}
	${menu args->n_viewed_4day name='Text'}
	${menu block->hide_no_view_4day name='Hide the widget if no views'}
	${menu args->hide_no_view_4day name='Hide the widget if less views than', type='number', param='min=0'}
	${menu args->hide_no_goal_4day name='Hide the widget if less purchases than', type='number', param='min=0'}
${menu name='Site statistics: week', icon='bar-chart'}
	${menu block->stats_week name='Site statistics: week'}
	${menu args->text_style_week name='Style', type='css', param='with_responsive=1'}
	${menu args->n_viewed_week name='Text'}
	${menu block->hide_no_view_week name='Hide the widget if no views'}
	${menu args->hide_no_view_week name='Hide the widget if less views than', type='number', param='min=0'}
	${menu args->hide_no_goal_week name='Hide the widget if less purchases than', type='number', param='min=0'}
${menu name='Price', icon='dollar'}
	${menu block->price name='With price'}
	${menu args->before_price name='Text before price'}
	${menu p->price:truncate(2):sprintf($%s) name='Price'}
	${menu args->sale_style name='Price before discount: style', type='css', param='with_responsive=1'}
	${menu args->after_price name='Text after price'}
	${menu args->price_style name='Price style', type='css', param='with_responsive=1'}
	${menu p->sale_price:truncate(2):sprintf($%s) name='Price'}
${menu name='Button', icon='hand-pointer-o'}
	${menu block->button name='With button'}
	${menu args->button_add_text name='Button text'}
	${menu args->button_add_plus name='Icon text'}
	${menu args->a_css_4 name='Button style', type='css', param='with_responsive=1'}
	${menu args->plus_style name='Button style', type='css', param='with_responsive=1'}
	${menu args->button_spacer name='Button reserved space', type='css', param='with_responsive=1'}
```


## First name and city of user who last bought current product



```
<div class="$responsive" data-style="position:relative; ${args->style:html:default('background-color: #e8e8e8;
border-radius: 20px;
padding: 1em;
max-width: sel(420px, 200px);
font-size: sel(12px, 10px);
align-items: center;
margin: 9px;
')}">

	${block->show_close_button:default(1)}
	<div data-style="position:absolute; cursor:pointer; ${args->close_button_style:html:default('right: 10px;
top: 10px;
')}">
		${args->close_button:default('<div onmouseenter="this.style.backgroundColor=this.style.outlineColor" onmouseleave="this.style.backgroundColor=this.style.textDecorationColor" style="display: inline-block; vertical-align: text-bottom; width: 24px; height: 24px; box-sizing: border-box; border-radius: 50%; border: 0px solid; box-shadow: rgba(255, 255, 255, 0.2) 0px 1px 0px inset, rgba(0, 0, 0, 0.2) 0px 1px 2px; padding: 5px; background-color: rgb(190, 61, 22); text-decoration-color: rgb(190, 61, 22); outline-color: rgb(110, 88, 52); outline-width: 10px; color: rgb(246, 244, 244); cursor: pointer; transition: all 0.3s ease 0s;" class="$personyze_button_dont_show_again" data-action_id="${action_id}"><div style="display: block; width: 100%; height: 100%; transition: all 0.3s ease 0s; border-radius: 50%; background-image: linear-gradient(-45deg, transparent 0%, transparent 46%, currentcolor 46%, currentcolor 56%, transparent 56%, transparent 100%), linear-gradient(45deg, transparent 0%, transparent 46%, currentcolor 46%, currentcolor 56%, transparent 56%, transparent 100%);"></div></div>')}
	</div>

    ${foreach products_interactions as p where p->interaction_status in ('viewed','extra','favorite') and p->last_interaction_time>=tm order by p->last_interaction_time desc limit 1}
		<a style="display:flex" href="${p->cart_url:html}">
			${block->with_img:default(0)}
			<div data-style="${args->style2:html}">
				<img src="${args->image_src:html}" data-style="width: auto; height: auto; ${args->image_style:html}">
			</div>
			${block->with_product_img:default(1)}
			<div data-style="${args->style_p:html:default('padding-top: 1em;
padding-right: 0;
padding-bottom: 1em;
padding-left: 1em;
width: 100%;
')}">
				<img src="${p->image_big_url:html}" data-style="width: auto; height: auto; ${args->product_image_style:html:default('max-width: 90%;
')}">
			</div>
			<div data-style="flex-grow:100; ${args->style3:html:default('padding: 1em;
font-size: sel(16px, 12px);
align-items: center;
margin: 9px;
font-style: normal;
text-decoration: none;
color: rgb(22, 13, 13);
')}">
				${args->text_1:default('${p->last_goal_user_0_first_name} ${p->last_goal_user_0_last_name:substr(0, 1):uc:sprintf(''%s.'')}')}
				${if p->last_goal_user_0_current_city != ''}
					${args->text_city:default('from ${p->last_goal_user_0_current_city}')}
				${end}
				${args->text_2:default('bought&nbsp;recently&nbsp;${p->title}')}
			</div>
		</a>
	${end}
</div>

${menu name='Settings', icon='sliders'}
	${menu args->text_1 name='Text'}
	${menu args->text_city name='Text'}
	${menu args->text_2 name='Text'}
	${menu args->style name='Style', type='css', param='with_responsive=1'}
	${menu args->style3 name='Text Box Style', type='css', param='with_responsive=1'}
${menu name='Close Button', icon='times-circle'}
	${menu block->show_close_button name='Show close button'}
	${menu args->close_button_style name='Close button style', type='css', param='with_responsive=1'}
	${menu args->close_button name='Close button', type='dontshowagain'}
${menu name='Image', icon='image'}
	${menu block->with_img name=''}
	${menu args->image_src name='URL', type='personyze_media_url'}
	${menu args->style2 name='Image Box Style', type='css', param='with_responsive=1'}
	${menu args->image_style name='Image style', type='css', param='with_responsive=1'}
${menu name='Product Image', icon='image'}
	${menu block->with_product_img name=''}
	${menu args->style_p name='Image Box Style', type='css', param='with_responsive=1'}
	${menu args->product_image_style name='Image style', type='css', param='with_responsive=1'}
```


## Social proof - last entry info



```
<div>
${foreach sum_products as p where p->for_period='recently' and p->last_goal_user_time_0 >= unix_timestamp()-172800 order by p->n_viewed desc limit 1}
	<div class="$responsive" style="${args->box_style:html:default('border-radius: 0em;
background-color: rgb(253, 253, 253);
display: inline-flex;
align-items: center;
color: black;
box-shadow: 0 0 2px rgb(238, 238, 238);
width: auto;
')}">
		${block->show_img:default(1)}
		<div>
			<a href="${p->cart_url:html}">
                <img data-src="${p->image_big_url:html}" style="${args->img_style:html:default('max-width: 100px;
max-height: 100px;
width: auto;
height: auto;
border-radius: 50%;
margin: 10px;
')}">
            </a>
		</div>

		<div>
			<div>
				${args->p_last_goal_user_0_first_name:default('<span>${p->last_goal_user_0_first_name} ${p->last_goal_user_0_last_name:substr(0, 1):uc:sprintf(''%s.'')}&nbsp;from&nbsp;${p->last_goal_user_0_current_city:sprintf(''city %s'')}</span>')}
				${if p->last_goal_user_0_current_city}
					(${p->last_goal_user_0_current_city})
				${end}
				<span style="color:gray">purchased</span>
			</div>
			<a href="${p->cart_url:html}" style="display:block; ${args->title_style:html:default('color: inherit;
text-decoration: none;
font-weight: bold;
margin-top: 0.7em;
margin-right: 0;
margin-bottom: 0.7em;
margin-left: 0;
max-width: 15em;
')}">
                ${p->title}
            </a>
			<div>
                ${args->text_before_time}
				<span style="color:gray" data-v="${if tm-p->last_goal_user_time_0<86400}${p->last_goal_user_time_0:html}${end}" data-earlier="${args->earlier:html:default(recently)}" data-days="${args->days:html:default(days)}" data-hours="${args->hours:html:default(hours)}" data-minutes="${args->minutes:html:default(minutes ago)}" ontplready="var v=this.dataset.v, f=Date.now()/1000 - v, d=Math.floor(f/(24*60*60)), h=Math.floor(f/(60*60))%24, m=Math.floor(f/60)%60; this.textContent = !v ? this.dataset.earlier : (d ? d+' '+this.dataset.days+' ' : '') + (h+' '+this.dataset.hours+' ') + (this.dataset.minutes ? m+' '+this.dataset.minutes : '')"></span>
                ${args->text_after_time:default('✅ Verified')}
			</div>
		</div>
		${block->show_close_button:default(1)}
		<div style="margin:10px 10px 10px 30px">
			${args->close_button:default('<a href="javascript:" style="font-size: 24px; color: black; font-weight: lighter; line-height: 1; text-decoration: none; position: absolute; inset: 5px auto auto; margin: 0px 0px 0px -13px;" class="$personyze_button_dont_show_again" data-action_id="${action_id}">×</a>')}
		</div>
	</div>
${end}
</div>

${menu name='Frame', icon='th-large'}
	${menu args->box_style name='Style', type='css', param='with_responsive=1'}
	${menu args->title_style name='Product name Style', type='css', param='with_responsive=1'}
	${menu p->title name='Product name'}
${menu name='Time texts', icon='clock-o'}
	${menu args->text_before_time name='Text before time'}
	${menu args->days name='days'}
	${menu args->hours name='hours'}
	${menu args->minutes name='minutes'}
	${menu args->earlier name='earlier'}
	${menu args->text_after_time name='Text after time'}
${menu name='Close Button', icon='times-circle'}
	${menu block->show_close_button name='Show close button'}
	${menu args->close_button name='Close button', type='dontshowagain'}
${menu name='Image', icon='image'}
	${menu block->show_img name='Show image'}
	${menu args->img_style name='Image Style', type='css', param='with_responsive=1'}
	${menu p->image_big_url name='Image db column'}
```


## Social proof widget

Print products number of view/purchase in a given time range

```
<div id=st_w class="$responsive" data-style="display:inline-block; position:relative; ${args->style:html:default('padding: 15px;
text-align: left;
font-weight: bold;
font-size: 16px;
box-sizing: border-box;
width: 350px;
font-family: Roboto,sans-serif;
box-shadow: 0 0px 0px 0 rgba(0,0,0,0.08);
background-color: rgb(65, 59, 109);
margin-top: 00px;
margin-right: 0px;
margin-bottom: 1px;
margin-left: 0px;
color: rgb(255, 256, 256);
border-radius: 5px;
line-height: 20px;')}" onupdate="
	var
		w=this.children[0].offsetWidth,
		b=12,
		a=ns.joyquery('parent::*>tr>td>*', by_id.ts).get(),
		d=a[0].parentNode,
		t=d.offsetWidth,
		n=Math.max(Math.round((w-b)/(t+b)), Math.min(2, by_id.ts.children.length)),
		T=(w-b)/n-b-parseFloat(d.style.borderLeftWidth)*2;
	for (i=0; i!=a.length; i++) if (a[i].style.display!='inline-block') a[i].style.width=T+'px'
">
	${block->title:default(1)}
	<table data-style="width:98%; margin-right: 1%; margin-left: 1%; border-collapse:collapse; border:none; ${args->title_bg:html:default('background-color: rgba(0, 0, 0, 0);
margin-top: 0px;
margin-right: 0;
margin-bottom: 0px;
margin-left: auto;
padding-top: 0px;
padding-right: 0;
padding-bottom: 0px;
padding-left: 0;
border-bottom: none;')}">
		<tr>
			<td data-style="vertical-align:middle; ${args->title_style:html:default('text-align: left;
font-family: "Source Sans Pro",sans-serif;
font-weight: 700;
padding-top: 5px;
padding-right: 0px;
padding-bottom: 5px;
padding-left: 5px;
font-size: 14px;
line-height: 17px;
text-transform: uppercase;
color: #FAC200;')}">
				${args->title}
			</td>
			${block->with_arrows:default(0)}
			<td style="width:1px; white-space:nowrap; vertical-align:middle">
				<a id="button_back" class="$flat_btn" style="${args->btn_style:html}" hover_style="${args->btn_hover_style:html}"><</a>
				<a id="button_forward" class="$flat_btn" style="${args->btn_style:html}" hover_style="${args->btn_hover_style:html}">></a>
			</td>
			${block->x:default(1)}
			<td style="width:1px; white-space:nowrap; ${args->x_style:html}">
				${args->x:default('<a href="javascript:" style="font-size: 18px; color: rgb(253, 253, 253); font-weight: bold; line-height: 1; text-decoration: none;" class="$personyze_button_dont_show_again" data-action_id="${action_id}">×</a>')}
			</td>
		</tr>
	</table>
	<table style="width:100%; border-collapse:separate; border-spacing:12px 0">
		<tr id="ts" class="$table_slider" data-disabled="${args->with_slider:html:default(1)}" style="width: 100%; padding: 0 1%; box-sizing: border-box; border:none; max-width:${args->width:html:default(none)}" for_max_vw="${args->for_max_vw:html}" eq_cell_width="${args->eq_cell_width:html:default(1)}" arrows_line="${args->arrows_line:html}" arrow_back_img="${args->arrow_back_img:html}" arrow_style="${args->arrow_style:html}" pagination_id="tsp" arrow_back_id="button_back" arrow_forward_id="button_forward" arrows_offset="${args->arrows_offset:html}" hide_buttons="${args->hide_buttons:html}">
			${foreach products_interactions as p where p->interaction_status in ('viewed','extra','favorite') and p->last_interaction_time>=tm order by p->last_interaction_time desc limit 1}
				<td style="position:relative; padding:0; text-align:center; vertical-align:top; border:solid ${args->border_color:html:default('rgba(178, 32, 32, 0)')} 1px">
					${block->img:default(0)}
					<a data-personyze-click-target="products ${p->internal_id:html}" href="${p->cart_url:html}" target="${args->target:html}" data-style="display:block; margin:auto; box-sizing:border-box; width:${args->img_width:html:default(0)}">
						<img src="${p->image_big_url:html}" data-style="width:auto; height:auto; max-width:100%; max-height:${args->img_max_height:html}">
					</a>
					<div data-style="margin:auto; box-sizing:border-box; width:${args->img_width:html}">
						<div data-style="${args->a_css:html:default('padding: 1px;
text-transform: none;
color: #333;
font-family: "Source Sans Pro",sans-serif;
font-weight: 300;
font-size: 0px;
margin: 0px;
text-overflow: clip;
max-height: 90px;
overflow: hidden;
text-align: left;
height: 0px;
background-color: rgba(29, 17, 17, 0);
')}">
							${p->age_to}
						</div>
					</div>
					${block->rating:default(0)}
					<div style="margin: auto; margin-bottom: .6em; line-height: 12px">
						<div style="width: 69px; height: 13px; font-size: 0; line-height: 0; background: url(https://skin.christys-hats.com/frontend/ultimo/totalRecall/images/img/rating.png) 0 0 repeat-x; text-indent: -999em; overflow: hidden; margin-left: 0; margin-right: 0; display: inline-block; vertical-align: middle;">
							<div style="float: left; height: 13px; background: url(https://skin.christys-hats.com/frontend/ultimo/totalRecall/images/img/rating.png) 0 100% repeat-x; width: ${p->rank:html:default(0)}%">
							</div>
						</div>
					</div>
					<div style="clear:left;"></div>

					${block->stats_recently:default(0)}
					<div data-style="${args->text_style_recently:html}">
						${foreach sum_products_recently as s where s->internal_id = p->internal_id limit 1}
							${args->n_viewed_recently:default('Great choice!&nbsp;
<div>This item was viewed&nbsp;<span><strong>${s->n_viewed*1}&nbsp;times&nbsp;in the last&nbsp;few hours.<br />
And was&nbsp;</strong></span><b>purchased&nbsp;</b></div>
${if s-&gt;n_goal &gt; 0}

<div><span><strong>${s->n_goal*1}&nbsp; times</strong></span></div>
${end}')}
							<span ontplready="this._v='${s->n_viewed:html}'|0; this._g='${s->n_goal:html}'|0"></span>
						${end}
						${block->hide_no_view_recently}
						<span ontplready="var p=this.previousElementSibling||{}; if ((p._v|0) < ('${args->hide_no_view_recently:html:default(10)}'|0) || (p._g|0) < ('${args->hide_no_goal_recently:html:default(7)}'|0)) _S_T.dismiss_action(${action_id:html})"></span>
					</div>

					${block->stats_1day:default(0)}
					<div data-style="${args->text_style_1day:html}">
						${foreach sum_products_1day as s where s->internal_id = p->internal_id limit 1}
							${args->n_viewed_1day:default('Great choice!&nbsp;
<div>This item was viewed&nbsp;<span><strong>${s->n_viewed*1}&nbsp;times&nbsp;in the last&nbsp;few hours.<br />
And was&nbsp;</strong></span><b>purchased&nbsp;</b></div>
${if s-&gt;n_goal &gt; 0}

<div><span><strong>${s->n_goal*1}&nbsp; times</strong></span></div>
${end}')}
							<span ontplready="this._v='${s->n_viewed:html}'|0; this._g='${s->n_goal:html}'|0"></span>
						${end}
						${block->hide_no_view_1day}
						<span ontplready="var p=this.previousElementSibling||{}; if ((p._v|0) < ('${args->hide_no_view_1day:html:default(10)}'|0) || (p._g|0) < ('${args->hide_no_goal_1day:html:default(7)}'|0)) _S_T.dismiss_action(${action_id:html})"></span>
					</div>

					${block->stats_2day:default(1)}
					<div data-style="${args->text_style_2day:html}">
						${foreach sum_products_2day as s where s->internal_id = p->internal_id limit 1}
							${args->n_viewed_2day:default('Great choice!&nbsp;
<div>This item was viewed&nbsp;<span><strong>${s->n_viewed*1}&nbsp;times&nbsp;in the last&nbsp;few hours.<br />
And was&nbsp;</strong></span><b>purchased&nbsp;</b></div>
${if s-&gt;n_goal &gt; 0}

<div><span><strong>${s->n_goal*1}&nbsp; times</strong></span></div>
${end}')}
							<span ontplready="this._v='${s->n_viewed:html}'|0; this._g='${s->n_goal:html}'|0"></span>
						${end}
						${block->hide_no_view_2day:default(0)}
						<span ontplready="var p=this.previousElementSibling||{}; if ((p._v|0) < ('${args->hide_no_view_2day:html:default(10)}'|0) || (p._g|0) < ('${args->hide_no_goal_2day:html:default(7)}'|0)) _S_T.dismiss_action(${action_id:html})"></span>
					</div>

					${block->stats_4day:default(0)}
					<div data-style="${args->text_style_4day:html}">
						${foreach sum_products_4day as s where s->internal_id = p->internal_id limit 1}
							${args->n_viewed_4day:default('Great choice!&nbsp;
<div>This item was viewed&nbsp;<span><strong>${s->n_viewed*1}&nbsp;times&nbsp;in the last&nbsp;few hours.<br />
And was&nbsp;</strong></span><b>purchased&nbsp;</b></div>
${if s-&gt;n_goal &gt; 0}

<div><span><strong>${s->n_goal*1}&nbsp; times</strong></span></div>
${end}')}
							<span ontplready="this._v='${s->n_viewed:html}'|0; this._g='${s->n_goal:html}'|0"></span>
						${end}
						${block->hide_no_view_4day}
						<span ontplready="var p=this.previousElementSibling||{}; if ((p._v|0) < ('${args->hide_no_view_4day:html:default(10)}'|0) || (p._g|0) < ('${args->hide_no_goal_4day:html:default(7)}'|0)) _S_T.dismiss_action(${action_id:html})"></span>
					</div>

					${block->stats_week:default(0)}
					<div data-style="${args->text_style_week:html}">
						${foreach sum_products_week as s where s->internal_id = p->internal_id limit 1}
							${args->n_viewed_week:default('Great choice!&nbsp;
<div>This item was viewed&nbsp;<span><strong>${s->n_viewed*1}&nbsp;times&nbsp;in the last&nbsp;few hours.<br />
And was&nbsp;</strong></span><b>purchased&nbsp;</b></div>
${if s-&gt;n_goal &gt; 0}

<div><span><strong>${s->n_goal*1}&nbsp; times</strong></span></div>
${end}')}
							<span ontplready="this._v='${s->n_viewed:html}'|0; this._g='${s->n_goal:html}'|0"></span>
						${end}
						${block->hide_no_view_week}
						<span ontplready="var p=this.previousElementSibling||{}; if ((p._v|0) < ('${args->hide_no_view_week:html:default(10)}'|0) || (p._g|0) < ('${args->hide_no_goal_week:html:default(7)}'|0)) _S_T.dismiss_action(${action_id:html})"></span>
					</div>

					${block->price:default(0)}
					<div data-style="margin:auto; box-sizing:border-box; width:${args->img_width:html}; ${args->price_style:html}">
						${if p->price}
							${args->before_price}
							${if p->sale_price and p->sale_price < p->price}
								${p->sale_price:truncate(2):sprintf($%s)}
								<div style="${args->sale_style:html}">
									${p->price:truncate(2):sprintf($%s)}
								</div>
							${end}
							${if not p->sale_price or p->sale_price >= p->price}
								${p->price:truncate(2):sprintf($%s)}
							${end}
							${args->after_price}
						${end}
					</div>
					<div style="margin:auto; box-sizing:border-box; font-size:1px">
						<div data-style="display:inline-block; background-color:${args->border_color:html}; ${args->a_css_2:html:default('width: 100px;
height: 3px;
max-width: 80%;
')}"></div>
					</div>
					${block->description:default(0)}
					<div data-style="margin:auto; box-sizing:border-box; width:${args->img_width:html}">
						<div data-style="display:inline-block; ${args->a_css_3:html}; padding-bottom:0">
							${p->description}
						</div>
					</div>
					${block->button:default(0)}
					<div data-style="${args->button_spacer:html}">
						<a data-personyze-click-target="products ${p->internal_id:html}" href="${p->cart_url:html}" target="${args->target:html}" data-style="display:block; box-sizing:border-box; position:absolute; width:100%; height:0; display:none; left:0; bottom:0; ${args->a_css_4:html}" ontplready="
							var a=ns.new_elem(this), p=this.parentNode.parentNode;
							p.onmouseenter = p.onmouseleave = function(e)
							{	var on = e.type == 'mouseenter';
								a.add_style({height: on ? 'auto' : '0', display: on ? '' : 'none'}, {});
							};
						">
							<div style="display:inline-block; width:1em; height:1em; line-height:1; border-radius:50%; ${args->plus_style:html}">${args->button_add_plus}</div>
							${args->button_add_text}
						</a>
					</div>
				</td>
			${end}
		</tr>
	</table>
	${block->pagination}
	<div id="tsp" class="$table_slider_pagination" slider_id="ts" selected_color="${args->pagination_color_on:html:default('rgba(0, 0, 0, 1)')}" style="${args->pagination_color:html}"></div>
</div>

${menu name='Frame', icon='th-large'}
	${menu args->width name='Widget maximum width', type='css_length', param='with_options=none'}
	${menu args->style name='Style', type='css', param='with_responsive=1'}
	${menu args->eq_cell_width name='Equal cell width', type='checkbox', param='value_off=', param='value_on=1'}
	${menu args->img_width name='Cell width', type='css_length', param='with_responsive=1'}
	${menu args->border_color name='Border color', type='color'}
	${menu args->img_max_height name='Image maximum height', type='css_length', param='with_responsive=1'}
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
${menu name='Image', icon='image'}
	${menu block->img name='With image'}
	${menu p->image_big_url name='Item image', column_tags='image'}
${menu name='Text', icon='align-justify'}
	${menu block->description name='With description'}
	${menu p->age_to name='Item text'}
	${menu p->description name='Item text'}
	${menu args->a_css name='Text color', type='css', param='with_responsive=1'}
	${menu args->a_css_3 name='Text color', type='css', param='with_responsive=1'}
	${menu args->a_css_2 name='Ruler', type='css', param='with_responsive=1'}
${menu name='Link target URL', icon='link'}
	${menu p->cart_url name='Link target URL', column_tags='url, custom text'}
	${menu args->target name='Open link in', type='a_target'}
${menu name='Rating', icon='star'}
	${menu block->rating name='With rating'}
	${menu p->rank name='Rating'}
${menu name='Site statistics: recently', icon='bar-chart'}
	${menu block->stats_recently name='Site statistics: recently'}
	${menu args->text_style_recently name='Style', type='css', param='with_responsive=1'}
	${menu args->n_viewed_recently name='Text'}
	${menu block->hide_no_view_recently name='Hide the widget if no views'}
	${menu args->hide_no_view_recently name='Hide the widget if less views than', type='number', param='min=0'}
	${menu args->hide_no_goal_recently name='Hide the widget if less purchases than', type='number', param='min=0'}
${menu name='Site statistics: 1-day', icon='bar-chart'}
	${menu block->stats_1day name='Site statistics: 1day'}
	${menu args->text_style_1day name='Style', type='css', param='with_responsive=1'}
	${menu args->n_viewed_1day name='Text'}
	${menu block->hide_no_view_1day name='Hide the widget if no views'}
	${menu args->hide_no_view_1day name='Hide the widget if less views than', type='number', param='min=0'}
	${menu args->hide_no_goal_1day name='Hide the widget if less purchases than', type='number', param='min=0'}
${menu name='Site statistics: 2-day', icon='bar-chart'}
	${menu block->stats_2day name='Site statistics: 2day'}
	${menu args->text_style_2day name='Style', type='css', param='with_responsive=1'}
	${menu args->n_viewed_2day name='Text'}
	${menu block->hide_no_view_2day name='Hide the widget if no views'}
	${menu args->hide_no_view_2day name='Hide the widget if less views than', type='number', param='min=0'}
	${menu args->hide_no_goal_2day name='Hide the widget if less purchases than', type='number', param='min=0'}
${menu name='Site statistics: 4-day', icon='bar-chart'}
	${menu block->stats_4day name='Site statistics: 4day'}
	${menu args->text_style_4day name='Style', type='css', param='with_responsive=1'}
	${menu args->n_viewed_4day name='Text'}
	${menu block->hide_no_view_4day name='Hide the widget if no views'}
	${menu args->hide_no_view_4day name='Hide the widget if less views than', type='number', param='min=0'}
	${menu args->hide_no_goal_4day name='Hide the widget if less purchases than', type='number', param='min=0'}
${menu name='Site statistics: week', icon='bar-chart'}
	${menu block->stats_week name='Site statistics: week'}
	${menu args->text_style_week name='Style', type='css', param='with_responsive=1'}
	${menu args->n_viewed_week name='Text'}
	${menu block->hide_no_view_week name='Hide the widget if no views'}
	${menu args->hide_no_view_week name='Hide the widget if less views than', type='number', param='min=0'}
	${menu args->hide_no_goal_week name='Hide the widget if less purchases than', type='number', param='min=0'}
${menu name='Price', icon='dollar'}
	${menu block->price name='With price'}
	${menu args->before_price name='Text before price'}
	${menu p->price:truncate(2):sprintf($%s) name='Price'}
	${menu args->sale_style name='Price before discount: style', type='css', param='with_responsive=1'}
	${menu args->after_price name='Text after price'}
	${menu args->price_style name='Price style', type='css', param='with_responsive=1'}
	${menu p->sale_price:truncate(2):sprintf($%s) name='Price'}
${menu name='Button', icon='hand-pointer-o'}
	${menu block->button name='With button'}
	${menu args->button_add_text name='Button text'}
	${menu args->button_add_plus name='Icon text'}
	${menu args->a_css_4 name='Button style', type='css', param='with_responsive=1'}
	${menu args->plus_style name='Button style', type='css', param='with_responsive=1'}
	${menu args->button_spacer name='Button reserved space', type='css', param='with_responsive=1'}
```


## Popular



```
<div class="$responsive" data-style="display:inline-block; position:relative; ${args->style:html:default('background-color: #f1f1f1;
color: #666666;
padding: 0.5em;
margin-top: 11px;
margin-right: 0px;
margin-bottom: 11px;
margin-left: 0px;
')}">
	${block->x:default(0)}
	<div style="position:absolute; ${args->x_style:html}">
		${args->x}
	</div>

	${foreach products_interactions as p where p->interaction_status in ('viewed','extra','favorite') and p->last_interaction_time>=tm order by p->last_interaction_time desc limit 1}
		<div data-style="display:inline-block; vertical-align:middle; ${args->tag_style:html:default('background-color: #fc9208;
color: white;
padding-top: 0.2em;
padding-right: 0.3em;
padding-bottom: 0.2em;
padding-left: 0.3em;
margin-right: 0.5em;
')}">
			${args->tag:default(Popular!)}
		</div>

		&nbsp;

		${block->stats_recently:default(0)}
		<span data-style="${args->text_style_recently:html}">
			${foreach sum_products_recently as s where s->internal_id = p->internal_id limit 1}
				${args->n_viewed_recently:default('${s->n_viewed} other people are considering this.')}
				<span ontplready="this._v='${s->n_viewed:html}'|0; this._g='${s->n_goal:html}'|0"></span>
			${end}
			${block->hide_no_view_recently}
			<span ontplready="var p=this.previousElementSibling||{}; if ((p._v|0) < ('${args->hide_no_view_recently:html:default(10)}'|0) || (p._g|0) < ('${args->hide_no_goal_recently:html:default(7)}'|0)) _S_T.dismiss_action(${action_id:html})"></span>
		</span>

		${block->stats_1day:default(0)}
		<span data-style="${args->text_style_1day:html}">
			${foreach sum_products_1day as s where s->internal_id = p->internal_id limit 1}
				${args->n_viewed_1day:default('${s->n_viewed}&nbsp;visitors viewed in the last 24 hour.')}
				<span ontplready="this._v='${s->n_viewed:html}'|0; this._g='${s->n_goal:html}'|0"></span>
			${end}
			${block->hide_no_view_1day}
			<span ontplready="var p=this.previousElementSibling||{}; if ((p._v|0) < ('${args->hide_no_view_1day:html:default(10)}'|0) || (p._g|0) < ('${args->hide_no_goal_1day:html:default(7)}'|0)) _S_T.dismiss_action(${action_id:html})"></span>
		</span>

		${block->stats_2day:default(1)}
		<span data-style="${args->text_style_2day:html:default('font-size: 12px;
')}">
			${foreach sum_products_2day as s where s->internal_id = p->internal_id limit 1}
				${args->n_viewed_2day:default('${s->n_viewed}&nbsp;visitors viewed in the last 48 hours.')}
				<span ontplready="this._v='${s->n_viewed:html}'|0; this._g='${s->n_goal:html}'|0"></span>
			${end}
			${block->hide_no_view_2day:default(1)}
			<span ontplready="var p=this.previousElementSibling||{}; if ((p._v|0) < ('${args->hide_no_view_2day:html:default(1)}'|0) || (p._g|0) < ('${args->hide_no_goal_2day:html}'|0)) _S_T.dismiss_action(${action_id:html})"></span>
		</span>

		${block->stats_4day:default(0)}
		<span data-style="${args->text_style_4day:html}">
			${foreach sum_products_4day as s where s->internal_id = p->internal_id limit 1}
				${args->n_viewed_4day:default('${s->n_viewed}&nbsp;visitors viewed in the last 4 days.')}
				<span ontplready="this._v='${s->n_viewed:html}'|0; this._g='${s->n_goal:html}'|0"></span>
			${end}
			${block->hide_no_view_4day}
			<span ontplready="var p=this.previousElementSibling||{}; if ((p._v|0) < ('${args->hide_no_view_4day:html:default(1)}'|0) || (p._g|0) < ('${args->hide_no_goal_4day:html}'|0)) _S_T.dismiss_action(${action_id:html})"></span>
		</span>

		${block->stats_week:default(0)}
		<span data-style="${args->text_style_week:html}">
			${foreach sum_products_week as s where s->internal_id = p->internal_id limit 1}
				${args->n_viewed_week:default('${s->n_viewed} other people are considering this.')}
				<span ontplready="this._v='${s->n_viewed:html}'|0; this._g='${s->n_goal:html}'|0"></span>
			${end}
			${block->hide_no_view_week}
			<span ontplready="var p=this.previousElementSibling||{}; if ((p._v|0) < ('${args->hide_no_view_week:html}'|0) || (p._g|0) < ('${args->hide_no_goal_week:html}'|0)) _S_T.dismiss_action(${action_id:html})"></span>
		</span>
	${end}
</div>

${menu name='Frame', icon='th-large'}
	${menu args->style name='Style', type='css', param='with_responsive=1'}
${menu name='Badge', icon='bookmark'}
	${menu args->tag name='Text'}
	${menu args->tag_style name='Style', type='css', param='with_responsive=1'}
${menu name='Close button', icon='close'}
	${menu block->x name='With close button'}
	${menu args->x name='Close button', type='dontshowagain', param='style=cursor:pointer; vertical-align:middle'}
	${menu args->x_style name='Close button position', type='css'}
${menu name='Site statistics: recently', icon='bar-chart'}
	${menu block->stats_recently name='Site statistics: recently'}
	${menu args->text_style_recently name='Style', type='css', param='with_responsive=1'}
	${menu args->n_viewed_recently name='Text'}
	${menu block->hide_no_view_recently name='Hide the widget if no views'}
	${menu args->hide_no_view_recently name='Hide the widget if less views than', type='number', param='min=0'}
	${menu args->hide_no_goal_recently name='Hide the widget if less purchases than', type='number', param='min=0'}
${menu name='Site statistics: 1-day', icon='bar-chart'}
	${menu block->stats_1day name='Site statistics: 1day'}
	${menu args->text_style_1day name='Style', type='css', param='with_responsive=1'}
	${menu args->n_viewed_1day name='Text'}
	${menu block->hide_no_view_1day name='Hide the widget if no views'}
	${menu args->hide_no_view_1day name='Hide the widget if less views than', type='number', param='min=0'}
	${menu args->hide_no_goal_1day name='Hide the widget if less purchases than', type='number', param='min=0'}
${menu name='Site statistics: 2-day', icon='bar-chart'}
	${menu block->stats_2day name='Site statistics: 2day'}
	${menu args->text_style_2day name='Style', type='css', param='with_responsive=1'}
	${menu args->n_viewed_2day name='Text'}
	${menu block->hide_no_view_2day name='Hide the widget if no views'}
	${menu args->hide_no_view_2day name='Hide the widget if less views than', type='number', param='min=0'}
	${menu args->hide_no_goal_2day name='Hide the widget if less purchases than', type='number', param='min=0'}
${menu name='Site statistics: 4-day', icon='bar-chart'}
	${menu block->stats_4day name='Site statistics: 4day'}
	${menu args->text_style_4day name='Style', type='css', param='with_responsive=1'}
	${menu args->n_viewed_4day name='Text'}
	${menu block->hide_no_view_4day name='Hide the widget if no views'}
	${menu args->hide_no_view_4day name='Hide the widget if less views than', type='number', param='min=0'}
	${menu args->hide_no_goal_4day name='Hide the widget if less purchases than', type='number', param='min=0'}
${menu name='Site statistics: week', icon='bar-chart'}
	${menu block->stats_week name='Site statistics: week'}
	${menu args->text_style_week name='Style', type='css', param='with_responsive=1'}
	${menu args->n_viewed_week name='Text'}
	${menu block->hide_no_view_week name='Hide the widget if no views'}
	${menu args->hide_no_view_week name='Hide the widget if less views than', type='number', param='min=0'}
	${menu args->hide_no_goal_week name='Hide the widget if less purchases than', type='number', param='min=0'}
```


## Purchased



```
<div>
${foreach sum_products as p where p->for_period='recently' and p->n_goal>0 and p->last_goal_user_time_0 >= unix_timestamp()-172800 order by p->n_goal desc limit 1}
	<div class="$responsive" style="${args->box_style:html:default('border-radius: 3em;
background-color: rgb(219, 231, 208);
display: inline-flex;
align-items: center;
color: black;
')}">
		${block->show_img:default(1)}
		<div>
			<a href="${p->cart_url:html}">
                <img data-src="${p->image_big_url:html}" style="${args->img_style:html:default('max-width: 100px;
max-height: 100px;
width: auto;
height: auto;
border-radius: 50%;
margin: 10px;
')}">
            </a>
		</div>

		<div>
			<div>
				${args->p_last_goal_user_0_first_name:default('<span>${p->last_goal_user_0_first_name} ${p->last_goal_user_0_last_name:substr(0, 1):uc:sprintf(''%s.'')}&nbsp;from&nbsp;${p->last_goal_user_0_current_city:sprintf(''city %s'')}</span>')}
				${if p->last_goal_user_0_current_city}
					(${p->last_goal_user_0_current_city})
				${end}
				<span style="color:gray">purchased</span>
			</div>
			<a href="${p->cart_url:html}" style="display:block; ${args->title_style:html:default('color: inherit;
text-decoration: none;
font-weight: bold;
margin-top: 0.7em;
margin-right: 0;
margin-bottom: 0.7em;
margin-left: 0;
max-width: 15em;
')}">
                ${p->title}
            </a>
			<div>
                ${args->text_before_time}
				<span style="color:gray" data-v="${if tm-p->last_goal_user_time_0<86400}${p->last_goal_user_time_0:html}${end}" data-earlier="${args->earlier:html:default(recently)}" data-days="${args->days:html:default(days)}" data-hours="${args->hours:html:default(hours)}" data-minutes="${args->minutes:html:default(minutes ago)}" ontplready="var v=this.dataset.v, f=Date.now()/1000 - v, d=Math.floor(f/(24*60*60)), h=Math.floor(f/(60*60))%24, m=Math.floor(f/60)%60; this.textContent = !v ? this.dataset.earlier : (d ? d+' '+this.dataset.days+' ' : '') + (h+' '+this.dataset.hours+' ') + (this.dataset.minutes ? m+' '+this.dataset.minutes : '')"></span>
                ${args->text_after_time:default('✅ Verified')}
			</div>
		</div>
		${block->show_close_button:default(1)}
		<div style="margin:10px 10px 10px 30px">
			${args->close_button:default('<div onmouseenter="this.style.backgroundColor=this.style.outlineColor" onmouseleave="this.style.backgroundColor=this.style.textDecorationColor" style="display: inline-block; vertical-align: text-bottom; width: 24px; height: 24px; box-sizing: border-box; border-top-left-radius: 50%; border-top-right-radius: 50%; border-bottom-right-radius: 50%; border-bottom-left-radius: 50%; border: 0px solid; -webkit-box-shadow: none; padding: 2px; background-color: rgba(0, 0, 0, 0); text-decoration-color: rgba(0, 0, 0, 0); outline-color: rgb(206, 54, 64); outline-width: 8px; color: rgb(10, 4, 4); cursor: pointer; transition: all 0.3s ease;" class="$personyze_button_dont_show_again" data-action_id="${action_id}"><div style="display: block; width: 100%; height: 100%; transition: all 0.3s ease 0s; border-top-left-radius: 50%; border-top-right-radius: 50%; border-bottom-right-radius: 50%; border-bottom-left-radius: 50%; background-image: linear-gradient(-45deg, transparent 0%, transparent 47%, currentcolor 47%, currentcolor 55%, transparent 55%, transparent 100%), linear-gradient(45deg, transparent 0%, transparent 47%, currentcolor 47%, currentcolor 55%, transparent 55%, transparent 100%);"></div></div>')}
		</div>
	</div>
${end}
</div>

${menu name='Frame', icon='th-large'}
	${menu args->box_style name='Style', type='css', param='with_responsive=1'}
	${menu args->title_style name='Product name Style', type='css', param='with_responsive=1'}
	${menu p->title name='Product name'}
${menu name='Time texts', icon='clock-o'}
	${menu args->text_before_time name='Text before time'}
	${menu args->days name='days'}
	${menu args->hours name='hours'}
	${menu args->minutes name='minutes'}
	${menu args->earlier name='earlier'}
	${menu args->text_after_time name='Text after time'}
${menu name='Close Button', icon='times-circle'}
	${menu block->show_close_button name='Show close button'}
	${menu args->close_button name='Close button', type='dontshowagain'}
${menu name='Image', icon='image'}
	${menu block->show_img name='Show image'}
	${menu args->img_style name='Image Style', type='css', param='with_responsive=1'}
	${menu p->image_big_url name='Image db column'}
```


## Multiple lines with animation



```
<div id="st_root" style=" width:100%; height:100%; overflow:hidden; pointer-events:none; background-color:transparent" ontplready="
	this._tr = function tr(e, f) {if (e.nodeType==1) for (var i=0; i!=e.childNodes.length; i++) tr(e.childNodes[i], f); else if (e.nodeType==3) f(e)}
	this.parentNode.style.position='relative'; this.parentNode.style.overflow='hidden'; if (ns == window.stgui) this.style.cssText += 'position:relative; min-height:6em'
">
	${foreach products_interactions as p where p->interaction_status in ('viewed','extra','favorite') order by p->interaction_time desc limit 1}
		${foreach sum_products_week as s where s->internal_id = p->internal_id limit 1}
			<div class="$info_lines_scroller" data-without_close="${args->without_close:html:default(1)}" style="${args->style:html:default('background-color: black;
color: white;
${case }
${when known_device_type=''phone''}font-size: 8px;
${else}font-size: 11px;
${end}
line-height: 3em;
border-top-left-radius: 0px;
border-top-right-radius: 22px;
border-bottom-right-radius: 22px;
border-bottom-left-radius: 0px;
bottom: 1em;
animation-delay: 1s;
animation-duration: 5s;
animation-iteration-count: infinite;
width: auto;
display: inline-block;
')}">
				${if s->n_viewed >= args->min_views:json:html:default(50)}
					${block->with_views:default(1)}
					<div>
						<hr class="$icon ${args->icon_views:html:default(user)}" style="${args->icon_views_style:html:default('font-size: 100%;
')}">&nbsp;
						${args->text_views:default('<strong>Trending now!</strong>&nbsp;${s->n_viewed}&nbsp;others have looked at this recently&nbsp;')}
					</div>
				${end}
				${if 100 - s->n_viewed / s->overall_n_viewed * 100 < args->min_views_percent:json:html:default(5)}
					${block->with_views_percent:default(0)}
					<div>
						<hr class="$icon ${args->icon_views_percent:html:default(user)}" style="${args->icon_views_style_percent:html:default('font-size: 100%;
')}">&nbsp;
						${args->text_views_percent:default('<strong>Popular!</strong>&nbsp;One of the ${args->min_views_percent}%&nbsp;most popular products')}
					</div>
				${end}
				${if s->n_goal >= args->min_goals:json:html:default(2)}
					${block->with_goals:default(1)}
					<div>
						<hr class="$icon ${args->icon_goals:html:default(shopping-cart)}" style="${args->icon_goals_style:html:default('font-size: 100%;
')}">&nbsp;
						${args->text_goals:default('<strong>Popular!</strong> Sold ${s->n_goal}&nbsp;times recently')}
					</div>
				${end}
				${if 100 - s->percentile_goal < args->min_goals_percent:json:html:default(5)}
					${block->with_goals_percent:default(0)}
					<div>
						<hr class="$icon ${args->icon_goals_percent:html:default(user)}" style="${args->icon_goals_style_percent:html:default('font-size: 100%;
')}">&nbsp;
						${args->text_goals_percent:default('<strong>Best seller!</strong>&nbsp;One of the ${args->min_goals_percent}%&nbsp;of best selling products')}
					</div>
				${end}
				${if p->inventory between 1 and args->min_inventory:html:default(300)}
					${if s->n_goal >= args->min_goals_for_inventory:json:html:default(0)}
						${block->with_inventory:default(1)}
						<div>
							<hr class="$icon ${args->icon_inventory:html:default(redo)}" style="${args->icon_inventory_style:html}">&nbsp;
							${args->text_inventory:default('<strong>Only&nbsp;${p->inventory}&nbsp; </strong>left in stock!')}
						</div>
					${end}
				${end}
				${if (s->prev_price - s->price_after_discount) * 100 / s->prev_price >= args->min_price_drop:html:default(6)}
					${if s->time_price_changed >= unix_timestamp() - 24*60*60*args->min_price_drop_days:html:default(500)}
						${block->with_price_drop:default(1)}
						<div ontplload="by_id.st_root._tr(this, n => {n.data = n.data.replace(/\{D\}/g, this.dataset.days).replace(/\{P\}/g, this.dataset.prc)})" data-days="${ceil(greatest(1, unix_timestamp() - s->time_price_changed) / (24*60*60))}" data-prc="${floor((s->prev_price - s->price_after_discount) * 100 / s->prev_price)}">
							<hr class="$icon ${args->icon_price_drop:html:default(tag)}" style="${args->icon_price_drop_style:html:default('font-size: 100%;
')}">&nbsp;
							${args->text_price_drop:default('Price dropped by {P}% in last {D} days')}
						</div>
					${end}
				${end}
				${if (s->price_before_discount - s->price_after_discount) * 100 / s->price_before_discount >= args->min_discount:html:default(1)}
					${block->with_discount:default(1)}
					<div ontplload="by_id.st_root._tr(this, n => {n.data = n.data.replace(/\{P\}/g, this.dataset.prc)})" data-prc="${floor((s->price_before_discount - s->price_after_discount) * 100 / s->price_before_discount)}">
						<hr class="$icon ${args->icon_discount:html:default(tag)}" style="${args->icon_discount_style:html:default('font-size: 100%;
')}">&nbsp;
						${args->text_discount:default('<strong>Sale!</strong> {P}% discount')}
					</div>
				${end}
				${if s->time_created > unix_timestamp() - 24*60*60*args->min_new_days:html:default(30)}
					${block->with_new:default(1)}
					<div ontplload="by_id.st_root._tr(this, n => {n.data = n.data.replace(/\{D\}/g, this.dataset.days)})" data-days="${ceil(greatest(1, unix_timestamp() - s->time_created) / (24*60*60))}">
						<hr class="$icon ${args->icon_new:html:default(fire)}" style="${args->icon_new_style:html:default('font-size: 100%;
')}">&nbsp;
						${args->text_new:default('<strong>New in stock.</strong> Added before {D} days')}
					</div>
				${end}
				${block->with_free1:default(1)}
				<div>
					<hr class="$icon ${args->icon_free1:html:default(fire)}" style="${args->icon_free1_style:html:default('font-size: 100%;
')}">&nbsp;
					${args->text_free1:default(Time limited special offer)}
				</div>
				${block->with_free2:default(1)}
				<div>
					<hr class="$icon ${args->icon_free2:html:default(fire)}" style="${args->icon_free2_style:html:default('font-size: 100%;
')}">&nbsp;
					${args->text_free2:default(Time limited special offer2)}
				</div>
				${block->with_free3:default(1)}
				<div>
					<hr class="$icon ${args->icon_free3:html:default(fire)}" style="${args->icon_free3_style:html:default('font-size: 100%;
')}">&nbsp;
					${args->text_free3:default(Time limited special offer3)}
				</div>
			</div>
		${end}
	${end}
</div>

${menu name='Settings', icon='sliders'}
	${menu args->style name='Style', type='css'}
	${menu args->without_close name='Leave info box open at the end of the animation', type='checkbox', param='value_on=1', param='value_off='}
${menu name='Line 1: views', icon='bars'}
	${menu block->with_views name='With views'}
	${menu args->min_views name='Dont show if less views', type='site_db_overall_stat', param='stat_table_alias=s'}
	${menu args->icon_views name='Icon for views', type='icon'}
	${menu args->icon_views_style name='Icon for views: style', type='css'}
	${menu args->text_views name='Line 1: views'}
${menu name='Line 2: most popular', icon='bars'}
	${menu block->with_views_percent name='With most popular'}
	${menu args->min_views_percent name='Show if this product is amongst N% of the most popular products on the site', type='site_db_overall_stat', param='stat_table_alias=s'}
	${menu args->icon_views_percent name='Icon for most popular', type='icon'}
	${menu args->icon_views_style_percent name='Icon for most popular: style', type='css'}
	${menu args->text_views_percent name='Line 2: most popular'}
${menu name='Line 3: purchases', icon='bars'}
	${menu block->with_goals name='With goals'}
	${menu args->min_goals name='Dont show if less purchases', type='site_db_overall_stat', param='stat_table_alias=s'}
	${menu args->icon_goals name='Icon for purchases', type='icon'}
	${menu args->icon_goals_style name='Icon for purchases: style', type='css'}
	${menu args->text_goals name='Line 3: purchases'}
${menu name='Line 4: best seller', icon='bars'}
	${menu block->with_goals_percent name='With best seller'}
	${menu args->min_goals_percent name='Show if this product is amongst N% of the best selling products on the site', type='site_db_overall_stat', param='stat_table_alias=s'}
	${menu args->icon_goals_percent name='Icon for best seller', type='icon'}
	${menu args->icon_goals_style_percent name='Icon for best seller: style', type='css'}
	${menu args->text_goals_percent name='Line 4: best seller'}
${menu name='Line 5: inventory', icon='bars'}
	${menu block->with_inventory name='With inventory'}
	${menu args->min_inventory name='Dont show if more items in stock than', type='number', param='min=0'}
	${menu args->min_goals_for_inventory name='Dont show if less purchases', type='site_db_overall_stat', param='stat_table_alias=s'}
	${menu args->icon_inventory name='Icon for inventory', type='icon'}
	${menu args->icon_inventory_style name='Icon for inventory: style', type='css'}
	${menu args->text_inventory name='Line 5: inventory'}
${menu name='Line 6: Price drop', icon='bars'}
	${menu block->with_price_drop name='With price drop'}
	${menu args->min_price_drop name='Show if drop percent at least', type='number', param='min=1'}
	${menu args->min_price_drop_days name='Show if drop was before N days or less', type='number', param='min=1'}
	${menu args->icon_price_drop name='Icon for price drop', type='icon'}
	${menu args->icon_price_drop_style name='Icon for price drop: style', type='css'}
	${menu args->text_price_drop name='Line 6: text. Use {P} for percent, and {D} for no. of days'}
${menu name='Line 7: Discount', icon='bars'}
	${menu block->with_discount name='With discount'}
	${menu args->min_discount name='Show if discount % is at least', type='number', param='min=1'}
	${menu args->icon_discount name='Icon for discount', type='icon'}
	${menu args->icon_discount_style name='Icon for discount: style', type='css'}
	${menu args->text_discount name='Line 7: text. Use {P} for discount percent'}
${menu name='Line 8: New in stock', icon='bars'}
	${menu block->with_new name='With new in stock'}
	${menu args->min_new_days name='Show if product appeared this no. of days ago', type='number', param='min=1'}
	${menu args->icon_new name='Icon for new in stock', type='icon'}
	${menu args->icon_new_style name='Icon for new in stock: style', type='css'}
	${menu args->text_new name='Line 8: text. Use {D} for no. of days'}
${menu name='Free text 1', icon='bars'}
	${menu block->with_free1 name='With free text 1'}
	${menu args->icon_free1 name='Icon for free text 1', type='icon'}
	${menu args->icon_free1_style name='Icon for free text 1: style', type='css'}
	${menu args->text_free1 name='Free text 1'}
${menu name='Free text 2', icon='bars'}
	${menu block->with_free2 name='With free text 2'}
	${menu args->icon_free2 name='Icon for free text 2', type='icon'}
	${menu args->icon_free2_style name='Icon for free text 2: style', type='css'}
	${menu args->text_free2 name='Free text 2'}
${menu name='Free text 3', icon='bars'}
	${menu block->with_free3 name='With free text 3'}
	${menu args->icon_free3 name='Icon for free text 3', type='icon'}
	${menu args->icon_free3_style name='Icon for free text 3: style', type='css'}
	${menu args->text_free3 name='Free text 3'}
```


