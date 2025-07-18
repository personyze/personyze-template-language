## Form



```
<div class="$responsive" data-style="position:relative; text-align:center; ${args->style__c0gv:html:default('color: #333;
position: relative;
top: 0px;
box-shadow: 0 0 black;
background-color: rgb(256, 255, 256);
width: 100%;
border-radius: 4px;
padding-top: sel(20px, 2px);
padding-right: 48px;
padding-bottom: sel(33px, 2px);
padding-left: 48px;
font-family: Karla, HelveticaNeue, "Helvetica Neue", sans-serif;
height: 100%;
')}">
	${block->animate_cart_button:default(1)}
	<style>
		.st-add-to-cart-button {overflow:hidden}
		.st-add-to-cart-button > a {transition: all ease 0.3s; position:relative; top: 5em; opacity: 0}
		.st-td-hover .st-add-to-cart-button > a {top: 0; opacity: 1}
	</style>

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

	${block->show_close_button__bzrx:default(1)}
	<div style="position:absolute; top:16px; right:16px; z-index:2">
		${args->close_button__yj9r:default('<img style="width:19px;" src="https://static.personyze.com/upload/4035/18e8b5d116db12cf.png" class="$personyze_button_dont_show_again" data-action_id="${action_id}" data-n_sessions="0">')}
	</div>
	<div class="$switch-elem" data-case="a" data-style="box-sizing:border-box">
		<div data-case="a" class="$cform st_f" ontplsubmit="personyze.push(['Submit', ${action_id:json:html}, this._get_value_ex(), arguments[1], arguments[2]]); return true" ontplaftersubmit="
			var sw=this.parentNode;
			sw._set_case('b', null, false, {template: 'animator_fade'});
			var js=this.dataset.customJs.trim(), redir=this.dataset.redir.trim(), t=this.dataset.redirDelay, v=this._get_value();
			if (js) new Function('action_id', 'by_id', 'data', 'report_error', js).call(this, ${action_id:json:html}, by_id, v);
			if (redir) setTimeout(function() {location.href=redir.replace(/\{([^{\r\n]+)\}/g, function(a, w) {return v[w]==null ? a : encodeURIComponent(v[w])})}, t*1000)
		" data-custom-js="${args->custom__bw0n:html}" data-redir="${args->redir:html}" data-redir-delay="${args->redir_delay:html}" style="position:relative; width:100%; height:100%">
			<div data-style="position:relative; z-index:1; background-color:white; margin:auto; width:80%; padding:0.6em">
				${block->with_header:default(1)}
				<div data-style="${args->header_style:html:default('border: solid black 0px;
padding: 0.6em;
font-size: 19px;
')}">
					${args->header_text:default(Wait a minute!)}
				</div>
			</div>
			<div data-style="position:relative; z-index:0; top:0; background-color:white; font-size:18px">
				${args->line_1__ycvk:default('<span style="font-size:20px;">Send your recent views to your inbox?</span><br />
<span style="font-size:12px;">Good choice! We can email your recent views to your inbox.</span><br />
&nbsp;')}

				<div data-style="${args->content_padding:html:default('width: 550px;
margin-top: 0;
margin-right: auto;
margin-bottom: 0;
margin-left: auto;
background-color: rgb(256, 256, 256);
')}">
					<table class="st-tab-rnd" data-style="height:10px; width:auto; border-collapse: separate; border-spacing: ${args->space_between_items:html:default(14px)} 0; margin:0 -${args->space_between_items:html}">
						<tr id="ts" class="$table_slider" data-disabled="${args->with_slider:html}" data-hover_add_class="st-td-hover" data-round="${args->round:html:default(1)}" data-with_scrollbar="${args->with_scrollbar:html}" data-scrollbar_style="${args->scrollbar_style:html:default('background-color: #D8D8D8;
color: #999999;
height: 12px;
')}" data-hide_scrollbar="${args->hide_scrollbar:html}" style="width: 100%; box-sizing: border-box; border:none" for_max_vw="${args->for_max_vw:html:default(always)}" eq_cell_width="${args->eq_cell_width:html:default(1)}" eq_cell_height="${args->eq_cell_height:html:default(1)}" arrows_line="${args->arrows_line:html:default(-1)}" arrow_back_img="${args->arrow_back_img:html:default('<svg viewBox="0 0 512.006 512.006" width="24" height="24" style="fill:#000;enable-background:new 0 0 512.006 512.006"><path d="M388.419,475.59L168.834,256.005L388.418,36.421c8.341-8.341,8.341-21.824,0-30.165s-21.824-8.341-30.165,0 L123.586,240.923c-8.341,8.341-8.341,21.824,0,30.165l234.667,234.667c4.16,4.16,9.621,6.251,15.083,6.251 c5.461,0,10.923-2.091,15.083-6.251C396.76,497.414,396.76,483.931,388.419,475.59z"/></svg>')}" arrow_style="${args->arrow_style:html:default('background-color: rgba(219, 195, 195, 0);
max-height: none;
padding-top: 0px;
padding-right: 2px;
padding-bottom: 0px;
padding-left: 2px;
width: auto;
')}" pagination_id="tsp" arrow_back_id="button_back" arrow_forward_id="button_forward" arrows_offset="${args->arrows_offset:html:default(-8)}" hide_buttons="${args->hide_buttons:html:default(1)}" buttons_always="${args->buttons_always:html:default(1)}">
							${foreach products as p order by p->time_created desc union sum_products where p->for_period='recently' order by p->n_viewed desc limit 12}
								<td style="position:relative; height:1px; padding:0; text-align:center; background-color:white; vertical-align:top; border:solid ${args->border_color:html:default('rgba(221, 221, 221, 0.01)')} 1px">
									<a data-personyze-click-target="products ${p->internal_id:html}" href="${p->cart_url:html}" target="${args->target:html:default(_self)}" data-style="position:relative; display:flex; height:100%; margin:auto; box-sizing:border-box; overflow:hidden; width:${args->img_width:html:default('sel(200px, 44vw)')}; text-decoration:none; ${args->img_alignment:html:default('align-items: baseline;
		')}">
										<img class="st-zoom" src="${p->image_big_url:html}" data-style="width:auto; height:auto; max-width:100%; max-height:${args->img_max_height:html:default('sel(209px, 120px)')}; border:none">

										${if p->image_medium_url <> ''}
											${block->with_hover_image:default(0)}
											<div style="position:absolute; display:flex; left:0; top: 0; width:100%; height:100%; ${args->img_alignment:html}">
												<img src="${p->image_medium_url:html}" data-style="width:auto; height:auto; max-width:100%; max-height:${args->img_max_height:html}; border:none">
											</div>
										${end}

										${block->with_discount_badge:default(1)}
										<span>
											${if p->discount_percent >= args->min_discount_percent:default(1)}
												<div data-style="position: absolute; ${args->discount_badge_style:html:default('top: 0;
right: 48px;
width: 7em;
height: 7em;
font-size: 7px;
text-shadow: rgba(255,255,255,0.5) 0px 3px 3px;
background-color: red;
border: double rgb(221, 228, 165) 6px;
color: rgb(252, 249, 249);
border-radius: 50%;
display: flex;
justify-content: center;
align-items: center;
')}">
													<span data-style="${args->discount_badge_text_style:html:default('line-height: 1.25;
font-size: 9px;
font-weight: 600;
')}">${args->discount_badge_text:default('<div style="font-size:14px">${p->discount_percent:floor}%</div>
Discount')}</span>
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

										${block->with_stock_badge:default(1)}
										<span>
											${if p->inventory between 1 and args->badge_if_less_stock:default(3)}
												<div data-style="position: absolute; ${args->stock_badge_style:html:default('bottom: 0;
left: 48px;
font-size: 14px;
text-shadow: rgba(255,255,255,0.5) 0px 3px 3px;
background-color: #db3932;
color: rgb(256, 256, 256);
display: flex;
justify-content: center;
align-items: center;
padding: 0.3em;
')}">
													<span data-style="${args->stock_badge_text_style:html:default('font-size: 16px;
font-weight: 500;
')}">${args->stock_badge_text:default('${p->inventory}&nbsp;left in stock')}</span>
												</div>
											${end}
										</span>

										${block->with_wishlist_badge:default(0)}
										<span class="$switch-elem"
											data-case="${foreach products_interactions as w where w->internal_id = p->internal_id and w->interaction_status = 'favorite' limit 1}on${end}"
											data-p="${p->internal_id:html}"
											data-style="position:absolute; transition: all 0.3s ease; ${args->wishlist_style:html:default('top: 5px;
right: 5px;
color: rgb(119, 181, 115);
font-size: 25px;
')}"
											onclick="var on=this._get_case(); _S_T.push([on ? 'Product Unliked' : 'Product Liked', this.dataset.p]); this._set_case(on ? '' : 'on'); event.stopPropagation(); event.preventDefault()"
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

									${block->with_custom_column:default(0)}
									<div>
										<div style="${args->custom_column_style:html:default('text-align: left;
padding: 1em;
font-weight: 600;
')}">${args->custom_column:html:default('${p->category}')}</div>
									</div>

									<a data-personyze-click-target="products ${p->internal_id:html}" href="${p->cart_url:html}" target="${args->target:html}" data-style="display:block; margin:auto; box-sizing:border-box; width:${args->img_width:html}; text-decoration:none">
										<div class="st-hov" data-style="${args->a_css:html:default('padding: 1px;
text-transform: none;
color: black;
font-weight: 400;
font-size: 0px;
margin: 2px;
text-align: center;
line-height: 1.3;
')}; position:relative; overflow:hidden; text-overflow:ellipsis; display:-webkit-box; -webkit-box-orient:vertical; -webkit-line-clamp:${args->title_max_lines:html:default(3)}; line-clamp:${args->title_max_lines:html}">
											${p->title}
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
															${args->n_viewed_1day:default('<div>${s->n_viewed*1} views today</div>
')}
														${end}
														${if s->n_goal > 0}
															${args->n_goal_1day:default('<div>${s->n_goal*1}&nbsp; purchases today</div>
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
															${args->n_viewed_week:default('<div>Good choice! This product has been popular in the last week! ${s->n_viewed*1} views this week.</div>
')}
														${end}
														${if s->n_goal > 0}
															${args->n_goal_week:default('<div>${s->n_goal*1}&nbsp; purchases this week</div>
')}
														${end}
													</div>
												${end}
											${end}
										${end}
									</span>

									<div style="clear:left;"></div>
									${block->price:default(0)}
									<div data-style="margin:auto; box-sizing:border-box; width:${args->img_width:html}; ${args->price_style:html}">
										${if p->price_after_discount}
											${if p->price_after_discount < p->price_before_discount}
												<span style="white-space:nowrap">
													<span style="${args->old_price_style:html:default('font-size: 22px;
font-weight: 700;
text-decoration: line-through;
')}">
														${args->old_price_before}${args->p_price_before_discount:default('$${p->price_before_discount:sprintf(''%[#,###.#]f'')}')}${args->old_price_after}
													</span>
												</span>
												<span style="white-space:nowrap">
													<span style="${args->new_price_style:html:default('font-size: 22px;
font-weight: 700;
color: red;
')}">
														${args->old_price_before)}${args->p_price_after_discount:default('$${p->price_after_discount:sprintf(''%[#,###.#]f'')}')}${args->old_price_after}
													</span>
												</span>
												<div style="${args->sale_text_style:html:default('display: inline-block;
font-size: 50%;
line-height: 1;
')}">
													${args->sale_text:default('<span style="white-space:nowrap; font-weight:400; font-size:80%; color:red">sale<br />
price</span>')}
												</div>
											${else}
												<span style="white-space:nowrap; ${args->nosale_price_style:html:default('font-size: 22px;
font-weight: 700;
')}">
													${args->old_price_before}${args->p_price_before_discount}${args->old_price_after}
												</span>
											${end}
										${end}
									</div>
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

									${block->with_link_button:default(0)}
									<div data-style="box-sizing:border-box; ${args->link_button_box_style:html:default('text-align: center;
')}">
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

									${block->with_cart:default(1)}
									<div class="st-add-to-cart-button">
										<a
											data-personyze-click-target="products ${p->internal_id:html}"
											class="$flat_btn $button_add_to_cart"
											data-is_code="${args->cart_is_code:html:default(1)}"
											data-action_id="${action_id:html}"
											data-url="${p->cart_url:html}"
											data-json-add_to_cart_columns="${p->add_to_cart_columns:html}"
											data-arg="${args->cart_arg:html}"
											data-yes="${args->cart_yes:html:default('location.href=location.href')}"
											data-no="${args->cart_no:html}"
											data-style="box-sizing:border-box; ${args->button_style:html:default('color: rgb(253, 252, 252);
padding-top: 9px;
padding-right: 13px;
padding-bottom: 9px;
padding-left: 13px;
font-size: 14px;
line-height: 14px;
font-weight: 700;
font-family: Lato;
margin: 15px;
background-color: #f57224;
width: auto;
')}" hover_style="${args->button_style_hover:html:default('color: rgb(253, 252, 252);
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
background-color: #f57224;
width: auto;
')}">
											<hr class="$icon ${args->button_icon:html:default(cart-plus)}" style="${args->button_icon_style:html:default('padding-right: 0.5em;
font-size: 100%;
color: inherit;
')}">
											${args->button:default(Add to cart)}
										</a>
									</div>
								</td>
							${end}
						</tr>
					</table>
					${block->pagination:default(0)}
					<div id="tsp" class="$table_slider_pagination" slider_id="ts" selected_color="${args->pagination_color_on:html:default('rgba(0, 0, 0, 1)')}" style="${args->pagination_color:html}"></div>
				</div>

				${block->with_f2__xu0n:default(0)}
				<div>
					<input form="st_f" name="Name" required="1" data-prop-column="${args->f2_db__i80f:html:default(first_name)}" data-style="box-sizing:border-box; ${args->f1_style__dsv8:html:default('margin-bottom: 20px;
padding: 10px;
font-family: Karla, HelveticaNeue, "Helvetica Neue", sans-serif;
font-weight: 400;
font-size: 16px;
width: 550px;
border: 1px solid rgb(62,62,62);
border-radius: 4px;
color: rgb(3, 1, 1);
text-align: left;
min-height: sel(48px, 23px);
')}" placeholder="${args->f2__utq1:html:default(Your First Name)}">
				</div>
				${block->with_f6__hhn1:default(0)}
				<div>
					<input form="st_f" name="Phone" type="tel" required="${args->f6_req__hj9h:html}" data-prop-column="${args->f6_db__j6p2:html}" data-style="box-sizing:border-box; ${args->f1_style__dsv8:html}" placeholder="${args->f6__fo5x:html}">
				</div>
				<div>
					<input form="st_f" name="Email" pattern="^[^\s@]+@[^\s@\.]+\.[^\s@]+$" required="1" data-prop-column="${args->f3_db__s3sv:html:default(email)}" data-style="box-sizing:border-box; ${args->f1_style__dsv8:html}" placeholder="${args->f3__pheb:html:default(Your Email Address)}">
				</div>
				${block->with_f5__ovmj:default(0)}
				<div>
					<textarea form="st_f" name="Details" data-style="box-sizing:border-box; ${args->f5_style__ksj6:html}" placeholder="${args->f5__z1qz:html}"></textarea>
				</div>
				${block->with_f4__lft0:default(0)}
				<div data-style="${args->style9__menn:html:default('text-align: left;
margin-top: 0px;
margin-right: 0px;
margin-bottom: 11px;
margin-left: 0px;
font-weight: 300;
font-size: 15px;
color: rgba(51, 51, 51, 0.83);
')}">
					<label>
						<input form="st_f" name="Checkbox" type="checkbox" data-prop-column="${args->f4_db__rvzd:html}" value="1">
						${args->text_9__i72g:default(Optin for marketing and promotions)}
					</label>
				</div>

                <button form="st_f" type="submit" class="$flat_btn" with_responsive="1" style="display:block; border:0; white-space:normal; box-sizing:border-box; ${args->button_style2__ef2g:html:default('display: block;
padding-top: 8px;
padding-right: 32px;
padding-bottom: 8px;
padding-left: 32px;
font-family: Karla, HelveticaNeue, "Helvetica Neue", sans-serif;
font-weight: normal;
font-size: 12px;
width: 550px;
min-height: 48px;
background: #4848a1;
border-color: #4848a1;
color: white;
border-bottom: 0px solid #3f75bd;
border-radius: 4px;
text-transform: uppercase;
margin: auto;
')}" hover_style="${args->button_h_style__iy3x:html:default('background-color: #111111;
border-color: #fff;
color: #FFFFFF;')}">
					${args->button_caption__lmzd:default(SEND)}
                </button>
			</div>
		</div>
		<div data-case="b" data-style="${args->style10:html:default('color: rgb(15, 9, 9);')}">
			${args->success__dpax:default('<div style="text-align: center;">&nbsp;
<p><span style="font-size:36px;">Awesome! We will keep you posted.</span></p>
</div>
')}
		</div>
	</div>

	${args->footer__lqk5}

</div>

${menu name='Box', icon='th-large'}
	${menu args->style__c0gv name='Style', type='css', param='with_responsive=1'}
	${menu args->content_padding name='Content box padding', type='css', param='with_responsive=1'}
	${menu args->round name='No cut cell', type='checkbox', param='value_off=', param='value_on=1'}
	${menu args->eq_cell_width name='Equal cell width', type='checkbox', param='value_off=', param='value_on=1'}
	${menu args->eq_cell_height name='Equal cell height', type='checkbox', param='value_off=', param='value_on=1'}
	${menu args->space_between_items name='Space between items', type='css_length', param='with_responsive=1'}
	${menu args->border_color name='Border color', type='color'}
	${menu args->round_border name='Round border', type='css_length'}
${menu name='Close button', icon='close'}
	${menu block->show_close_button__bzrx name='Show close button'}
	${menu args->close_button__yj9r name='Close button', type='dontshowagain'}
${menu name='Slider options', icon='arrow-right'}
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
${menu name='Header', icon='bars'}
	${menu block->with_header name='With Header'}
	${menu args->header_text name='Header text'}
	${menu args->header_style name='Header style', type='css', param='with_responsive=1'}
${menu name='Text', icon='bars'}
	${menu args->line_1__ycvk name='Line 1 Text'}
${menu name='Name Box', icon='edit'}
	${menu block->with_f2__xu0n name='With Name'}
	${menu args->f2_db__i80f name='Name save to database', type='select_social', param='with_empty=1'}
	${menu args->f2__utq1 name='Name Placeholder Text'}
	${menu args->f1_style__dsv8 name='Input style', type='css', param='with_responsive=1'}
${menu name='Telephone Box', icon='edit'}
	${menu block->with_f6__hhn1 name='With Telephone'}
	${menu args->f6_db__j6p2 name='Telephone save to database', type='select_social', param='with_empty=1'}
	${menu args->f6_req__hj9h name='Telephone is required field', type='checkbox'}
	${menu args->f6__fo5x name='Telephone Placeholder Text'}
${menu name='Email Box', icon='envelope'}
	${menu args->f3__pheb name='Email Placeholder Text'}
	${menu args->f3_db__s3sv name='Email save to database', type='select_social', param='with_empty=1'}
${menu name='Details Box', icon='edit'}
	${menu block->with_f5__ovmj name='With Details'}
	${menu args->f5__z1qz name='Details Placeholder Text'}
	${menu args->f5_style__ksj6 name='Input style', type='css', param='with_responsive=1'}
${menu name='Checkbox', icon='edit'}
	${menu block->with_f4__lft0 name='With Checkbox'}
	${menu args->style9__menn name='Checkbox Style', type='css', param='with_responsive=1'}
	${menu args->f4_db__rvzd name='Checkbox save to database', type='select_social', param='with_empty=1'}
	${menu args->text_9__i72g name='Text'}
${menu name='After submit', icon='check'}
	${menu args->success__dpax name='Thank you text'}
	${menu args->custom__bw0n name='After submit execute this JavaScript', type='textarea'}
	${menu args->style10 name='Thank you text Style', type='css', param='with_responsive=1'}
	${menu args->redir name='After submit redirect to this URL. Placeholders like {Field name} will be substituted'}
	${menu args->redir_delay name='Redirect delay, sec', type='number'}
${menu name='Action button', icon='check'}
	${menu args->button_caption__lmzd name='Caption'}
	${menu args->button_style2__ef2g name='Style', type='css'}
	${menu args->button_h_style__iy3x name='Hover Style', type='css'}
${menu name='Footer', icon='bars'}
	${menu args->footer__lqk5 name='Footer'}
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
${menu name='Discount badge', icon='align-justify', description='Set discount badge to appear for a discounted product, you may choose to set it to show only if the discount is greater than X.'}
	${menu block->with_discount_badge name='With new badge'}
	${menu args->min_discount_percent name='Show discount badge if % ≥', type='number', param='min=1'}
	${menu args->discount_badge_style name='Badge style', type='css', param='with_responsive=1'}
	${menu args->discount_badge_text_style name='Badge text style', type='css', param='with_responsive=1'}
	${menu args->discount_badge_text name='Text'}
${menu name='New badge', icon='align-justify', description='Set "New" badge to appear for items debut recently.
You may choose a time frame for a product to be considered new. * For new accounts/product feed, all products are new until the day setting condition has been met.'}
	${menu block->with_new_badge name='With discount badge'}
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
${menu name='Stock badge', icon='align-justify', description='Set "Low in stock" badge to appear for low stock items.
In addition, you can set the quantity number below it a product is considered to be low in stock.  This requires you to populate "quantity" on your product feed.'}
	${menu block->with_stock_badge name='With stock badge'}
	${menu args->badge_if_less_stock name='Show stock badge if items less than', type='number', param='min=1'}
	${menu args->stock_badge_style name='Badge style', type='css', param='with_responsive=1'}
	${menu args->stock_badge_text_style name='Badge text style', type='css', param='with_responsive=1'}
	${menu args->stock_badge_text name='Text'}
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
${menu name='Product text/desc', icon='align-justify'}
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
${menu name='Quick add to cart button', icon='cart-plus', description='Set the widget button to add items to the visitor cart. This feature requires you to set a quick add to cart under product interaction settings>add to cart.'}
	${menu block->with_cart name='With add to cart'}
	${menu args->button name='Text'}
	${menu args->button_icon name='Icon on button', type='icon'}
	${menu args->button_icon_style name='Icon on button style', type='css'}
	${menu args->button_style name='Button style', type='css', param='with_responsive=1'}
	${menu args->button_style_hover name='Button hover style', type='css'}
	${menu block->animate_cart_button name='Slide button on mouse hover'}
	${menu args->cart_is_code name='Button triggers "Add to cart" integration code', type='checkbox', param='value_off=', param='value_on=1'}
	${menu args->cart_arg name='Argument to pass to your defined Add to Cart function (optional)', visible_if='args.cart_is_code'}
	${menu args->cart_yes name='Javascript on complete (optional)', type='source_javascript', visible_if='args.cart_is_code'}
	${menu args->cart_no name='Javascript on error (optional)', type='source_javascript', visible_if='args.cart_is_code'}
${menu name='Onclick target URL', icon='link'}
	${menu p->cart_url name='Link target URL', column_tags='url, custom text'}
	${menu args->target name='Open link in', type='a_target'}
${menu name='Rating', icon='star', description='Show product rating when available
This requires you to populate "Rank" on your product feed   .'}
	${menu block->rating name='With rating'}
	${menu p->rank name='Rating'}
	${menu args->rating_style name='Colors', type='css', param='vars=--bgcolor:color; --border-color:color'}
${menu name='Site statistics: 1-day', icon='bar-chart', description='Show number of viewed or purchases in the last 24 hours for a given item as tracked by Personyze. You can set a condition not to show if the number of views/purchases is below X number.'}
	${menu block->stats_1day name='Site statistics: 1day'}
	${menu args->hide_no_view_1day name='Hide statistics if less views than', type='number', param='min=0'}
	${menu args->hide_no_goal_1day name='Hide statistics if less purchases than', type='number', param='min=0'}
	${menu args->text_style_1day name='Style', type='css'}
	${menu args->n_viewed_1day name='Text'}
	${menu args->n_goal_1day name='Text'}
${menu name='Site statistics: week', icon='bar-chart', description='Show number of viewed or purchases in the last week for a given item as tracked by Personyze. You can set a condition not to show if the number of views/purchases is below X number.'}
	${menu block->stats_week name='Site statistics: week'}
	${menu args->hide_no_view_week name='Hide statistics if less views than', type='number', param='min=0'}
	${menu args->hide_no_goal_week name='Hide statistics if less purchases than', type='number', param='min=0'}
	${menu args->text_style_week name='Style', type='css'}
	${menu args->n_viewed_week name='Text'}
	${menu args->n_goal_week name='Text'}
${menu name='Price', icon='dollar'}
	${menu block->price name='With price'}
	${menu args->price_style name='Price style', type='css', param='with_responsive=1'}
	${menu args->old_price_style name='Price before discount - style', type='css'}
	${menu args->old_price_before name='Price before discount - text before'}
	${menu args->p_price_before_discount name='Price before discount'}
	${menu args->old_price_after name='Price before discount - text before'}
	${menu args->p_price_after_discount name='Price after discount'}
	${menu args->new_price_style name='Price after discount - style', type='css'}
	${menu args->sale_text_style name='Sale text style', type='css'}
	${menu args->sale_text name='Sale text'}
	${menu args->nosale_price_style name='Price without discount - style', type='css'}
```


## Form



```
<div class="$responsive" data-style="position:relative; text-align:center; ${args->style__c0gv:html:default('color: #333;
position: relative;
top: 0px;
box-shadow: 0 0 black;
background-color: #fff;
width: auto;
border-radius: 4px;
padding-top: sel(20px, 2px);
padding-right: 48px;
padding-bottom: sel(4px, 2px);
padding-left: 48px;
font-family: Karla, HelveticaNeue, "Helvetica Neue", sans-serif;
max-height: none;
max-width: 550px;
')}">
	${block->animate_cart_button:default(1)}
	<style>
		.st-add-to-cart-button {overflow:hidden}
		.st-add-to-cart-button > a {transition: all ease 0.3s; position:relative; top: 5em; opacity: 0}
		.st-td-hover .st-add-to-cart-button > a {top: 0; opacity: 1}
	</style>

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

	${block->show_close_button__bzrx:default(1)}
	<div style="position:absolute; top:16px; right:16px; z-index:2">
		${args->close_button__yj9r:default('<img style="width:19px;" src="https://static.personyze.com/upload/4035/18e8b5d116db12cf.png" class="$personyze_button_dont_show_again" data-action_id="${action_id}" data-n_sessions="0">')}
	</div>
	<div class="$switch-elem" data-case="a" data-style="box-sizing:border-box">
		<div data-case="a" class="$cform st_f" ontplsubmit="personyze.push(['Submit', ${action_id:json:html}, this._get_value_ex(), arguments[1], arguments[2]]); return true" ontplaftersubmit="
			var sw=this.parentNode;
			sw._set_case('b', null, false, {template: 'animator_fade'});
			var js=this.dataset.customJs.trim(), redir=this.dataset.redir.trim(), t=this.dataset.redirDelay, v=this._get_value();
			if (js) new Function('action_id', 'by_id', 'data', 'report_error', js).call(this, ${action_id:json:html}, by_id, v);
			if (redir) setTimeout(function() {location.href=redir.replace(/\{([^{\r\n]+)\}/g, function(a, w) {return v[w]==null ? a : encodeURIComponent(v[w])})}, t*1000)
		" data-custom-js="${args->custom__bw0n:html}" data-redir="${args->redir:html}" data-redir-delay="${args->redir_delay:html}" style="position:relative; width:100%; height:100%">
			<div data-style="position:relative; z-index:1; background-color:white; margin:auto; width:80%; padding:0.6em">
				${block->with_header:default(1)}
				<div data-style="${args->header_style:html:default('border: solid black 0px;
padding: 0.6em;
font-size: 19px;
')}">
					${args->header_text:default(Wait a minute!)}
				</div>
			</div>
			<div data-style="position:relative; z-index:0; top:0; background-color:white; font-size:18px">
				${args->line_1__ycvk:default('<span style="font-size:20px;">Send your recent views to your inbox?</span><br />
<span style="font-size:12px;">Good choice! We can email your recent views to your inbox.</span><br />
&nbsp;')}

				<div data-style="${args->content_padding:html:default('width: 100%;
margin-top: 0;
margin-right: auto;
margin-bottom: 0;
margin-left: auto;
')}">
					<table class="st-tab-rnd" data-style="height:10px; width:auto; border-collapse: separate; border-spacing: ${args->space_between_items:html:default(14px)} 0; margin:0 -${args->space_between_items:html}">
						<tr id="ts" class="$table_slider" data-disabled="${args->with_slider:html}" data-hover_add_class="st-td-hover" data-round="${args->round:html:default(1)}" data-with_scrollbar="${args->with_scrollbar:html}" data-scrollbar_style="${args->scrollbar_style:html:default('background-color: #D8D8D8;
color: #999999;
height: 12px;
')}" data-hide_scrollbar="${args->hide_scrollbar:html}" style="width: 100%; box-sizing: border-box; border:none" for_max_vw="${args->for_max_vw:html:default(always)}" eq_cell_width="${args->eq_cell_width:html:default(1)}" eq_cell_height="${args->eq_cell_height:html:default(1)}" arrows_line="${args->arrows_line:html:default(-1)}" arrow_back_img="${args->arrow_back_img:html:default('<svg viewBox="0 0 512.006 512.006" width="24" height="24" style="fill:#000;enable-background:new 0 0 512.006 512.006"><path d="M388.419,475.59L168.834,256.005L388.418,36.421c8.341-8.341,8.341-21.824,0-30.165s-21.824-8.341-30.165,0 L123.586,240.923c-8.341,8.341-8.341,21.824,0,30.165l234.667,234.667c4.16,4.16,9.621,6.251,15.083,6.251 c5.461,0,10.923-2.091,15.083-6.251C396.76,497.414,396.76,483.931,388.419,475.59z"/></svg>')}" arrow_style="${args->arrow_style:html:default('background-color: rgba(219, 195, 195, 0);
max-height: none;
padding-top: 0px;
padding-right: 2px;
padding-bottom: 0px;
padding-left: 2px;
width: auto;
')}" pagination_id="tsp" arrow_back_id="button_back" arrow_forward_id="button_forward" arrows_offset="${args->arrows_offset:html:default(-8)}" hide_buttons="${args->hide_buttons:html:default(1)}" buttons_always="${args->buttons_always:html:default(1)}">
							${foreach products as p order by p->time_created desc union sum_products where p->for_period='recently' order by p->n_viewed desc limit 12}
								<td style="position:relative; height:1px; padding:0; text-align:center; background-color:white; vertical-align:top; border:solid ${args->border_color:html:default('rgba(221, 221, 221, 0.01)')} 1px">
									<a data-personyze-click-target="products ${p->internal_id:html}" href="${p->cart_url:html}" target="${args->target:html:default(_self)}" data-style="position:relative; display:flex; height:100%; margin:auto; box-sizing:border-box; overflow:hidden; width:${args->img_width:html:default('sel(200px, 44vw)')}; text-decoration:none; ${args->img_alignment:html:default('align-items: baseline;
		')}">
										<img class="st-zoom" src="${p->image_big_url:html}" data-style="width:auto; height:auto; max-width:100%; max-height:${args->img_max_height:html:default('sel(209px, 120px)')}; border:none">

										${if p->image_medium_url <> ''}
											${block->with_hover_image:default(0)}
											<div style="position:absolute; display:flex; left:0; top: 0; width:100%; height:100%; ${args->img_alignment:html}">
												<img src="${p->image_medium_url:html}" data-style="width:auto; height:auto; max-width:100%; max-height:${args->img_max_height:html}; border:none">
											</div>
										${end}

										${block->with_discount_badge:default(1)}
										<span>
											${if p->discount_percent >= args->min_discount_percent:default(1)}
												<div data-style="position: absolute; ${args->discount_badge_style:html:default('top: 0;
right: 48px;
width: 7em;
height: 7em;
font-size: 7px;
text-shadow: rgba(255,255,255,0.5) 0px 3px 3px;
background-color: red;
border: double rgb(221, 228, 165) 6px;
color: rgb(252, 249, 249);
border-radius: 50%;
display: flex;
justify-content: center;
align-items: center;
')}">
													<span data-style="${args->discount_badge_text_style:html:default('line-height: 1.25;
font-size: 9px;
font-weight: 600;
')}">${args->discount_badge_text:default('<div style="font-size:14px">${p->discount_percent:floor}%</div>
Discount')}</span>
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

										${block->with_stock_badge:default(1)}
										<span>
											${if p->inventory between 1 and args->badge_if_less_stock:default(3)}
												<div data-style="position: absolute; ${args->stock_badge_style:html:default('bottom: 0;
left: 48px;
font-size: 14px;
text-shadow: rgba(255,255,255,0.5) 0px 3px 3px;
background-color: #db3932;
color: rgb(256, 256, 256);
display: flex;
justify-content: center;
align-items: center;
padding: 0.3em;
')}">
													<span data-style="${args->stock_badge_text_style:html:default('font-size: 16px;
font-weight: 500;
')}">${args->stock_badge_text:default('${p->inventory}&nbsp;left in stock')}</span>
												</div>
											${end}
										</span>

										${block->with_wishlist_badge:default(0)}
										<span class="$switch-elem"
											data-case="${foreach products_interactions as w where w->internal_id = p->internal_id and w->interaction_status = 'favorite' limit 1}on${end}"
											data-p="${p->internal_id:html}"
											data-style="position:absolute; transition: all 0.3s ease; ${args->wishlist_style:html:default('top: 5px;
right: 5px;
color: rgb(119, 181, 115);
font-size: 25px;
')}"
											onclick="var on=this._get_case(); _S_T.push([on ? 'Product Unliked' : 'Product Liked', this.dataset.p]); this._set_case(on ? '' : 'on'); event.stopPropagation(); event.preventDefault()"
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

									${block->with_custom_column:default(0)}
									<div>
										<div style="${args->custom_column_style:html:default('text-align: left;
padding: 1em;
font-weight: 600;
')}">${args->custom_column:html:default('${p->category}')}</div>
									</div>

									<a data-personyze-click-target="products ${p->internal_id:html}" href="${p->cart_url:html}" target="${args->target:html}" data-style="display:block; margin:auto; box-sizing:border-box; width:${args->img_width:html}; text-decoration:none">
										<div class="st-hov" data-style="${args->a_css:html:default('padding: 1px;
text-transform: none;
color: black;
font-weight: 400;
font-size: 0px;
margin: 2px;
text-align: center;
line-height: 1.3;
')}; position:relative; overflow:hidden; text-overflow:ellipsis; display:-webkit-box; -webkit-box-orient:vertical; -webkit-line-clamp:${args->title_max_lines:html:default(3)}; line-clamp:${args->title_max_lines:html}">
											${p->title}
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
															${args->n_viewed_1day:default('<div>${s->n_viewed*1} views today</div>
')}
														${end}
														${if s->n_goal > 0}
															${args->n_goal_1day:default('<div>${s->n_goal*1}&nbsp; purchases today</div>
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
															${args->n_viewed_week:default('<div>Good choice! This product has been popular in the last week! ${s->n_viewed*1} views this week.</div>
')}
														${end}
														${if s->n_goal > 0}
															${args->n_goal_week:default('<div>${s->n_goal*1}&nbsp; purchases this week</div>
')}
														${end}
													</div>
												${end}
											${end}
										${end}
									</span>

									<div style="clear:left;"></div>
									${block->price:default(0)}
									<div data-style="margin:auto; box-sizing:border-box; width:${args->img_width:html}; ${args->price_style:html}">
										${if p->price_after_discount}
											${if p->price_after_discount < p->price_before_discount}
												<span style="white-space:nowrap">
													<span style="${args->old_price_style:html:default('font-size: 22px;
font-weight: 700;
text-decoration: line-through;
')}">
														${args->old_price_before}${args->p_price_before_discount:default('$${p->price_before_discount:sprintf(''%[#,###.#]f'')}')}${args->old_price_after}
													</span>
												</span>
												<span style="white-space:nowrap">
													<span style="${args->new_price_style:html:default('font-size: 22px;
font-weight: 700;
color: red;
')}">
														${args->old_price_before)}${args->p_price_after_discount:default('$${p->price_after_discount:sprintf(''%[#,###.#]f'')}')}${args->old_price_after}
													</span>
												</span>
												<div style="${args->sale_text_style:html:default('display: inline-block;
font-size: 50%;
line-height: 1;
')}">
													${args->sale_text:default('<span style="white-space:nowrap; font-weight:400; font-size:80%; color:red">sale<br />
price</span>')}
												</div>
											${else}
												<span style="white-space:nowrap; ${args->nosale_price_style:html:default('font-size: 22px;
font-weight: 700;
')}">
													${args->old_price_before}${args->p_price_before_discount}${args->old_price_after}
												</span>
											${end}
										${end}
									</div>
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

									${block->with_link_button:default(0)}
									<div data-style="box-sizing:border-box; ${args->link_button_box_style:html:default('text-align: center;
')}">
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

									${block->with_cart:default(1)}
									<div class="st-add-to-cart-button">
										<a
											data-personyze-click-target="products ${p->internal_id:html}"
											class="$flat_btn $button_add_to_cart"
											data-is_code="${args->cart_is_code:html:default(1)}"
											data-action_id="${action_id:html}"
											data-url="${p->cart_url:html}"
											data-json-add_to_cart_columns="${p->add_to_cart_columns:html}"
											data-arg="${args->cart_arg:html}"
											data-yes="${args->cart_yes:html:default('location.href=location.href')}"
											data-no="${args->cart_no:html}"
											data-style="box-sizing:border-box; ${args->button_style:html:default('color: rgb(253, 252, 252);
padding-top: 9px;
padding-right: 13px;
padding-bottom: 9px;
padding-left: 13px;
font-size: 14px;
line-height: 14px;
font-weight: 700;
font-family: Lato;
margin: 15px;
background-color: #f57224;
width: auto;
')}" hover_style="${args->button_style_hover:html:default('color: rgb(253, 252, 252);
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
background-color: #f57224;
width: auto;
')}">
											<hr class="$icon ${args->button_icon:html:default(cart-plus)}" style="${args->button_icon_style:html:default('padding-right: 0.5em;
font-size: 100%;
color: inherit;
')}">
											${args->button:default(Add to cart)}
										</a>
									</div>
								</td>
							${end}
						</tr>
					</table>
					${block->pagination:default(0)}
					<div id="tsp" class="$table_slider_pagination" slider_id="ts" selected_color="${args->pagination_color_on:html:default('rgba(0, 0, 0, 1)')}" style="${args->pagination_color:html}"></div>
				</div>

				${block->with_f2__xu0n:default(0)}
				<div>
					<input form="st_f" name="Name" required="1" data-prop-column="${args->f2_db__i80f:html:default(first_name)}" data-style="box-sizing:border-box; ${args->f1_style__dsv8:html:default('margin-bottom: 20px;
padding: 10px;
font-family: Karla, HelveticaNeue, "Helvetica Neue", sans-serif;
font-weight: 400;
font-size: 16px;
width: 100%;
border: 1px solid rgb(62,62,62);
border-radius: 4px;
color: rgb(3, 1, 1);
text-align: left;
min-height: sel(48px, 23px);
')}" placeholder="${args->f2__utq1:html:default(Your First Name)}">
				</div>
				${block->with_f6__hhn1:default(0)}
				<div>
					<input form="st_f" name="Phone" type="tel" required="${args->f6_req__hj9h:html}" data-prop-column="${args->f6_db__j6p2:html}" data-style="box-sizing:border-box; ${args->f1_style__dsv8:html}" placeholder="${args->f6__fo5x:html}">
				</div>
				<div>
					<input form="st_f" name="Email" pattern="^[^\s@]+@[^\s@\.]+\.[^\s@]+$" required="1" data-prop-column="${args->f3_db__s3sv:html:default(email)}" data-style="box-sizing:border-box; ${args->f1_style__dsv8:html}" placeholder="${args->f3__pheb:html:default(Your Email Address)}">
				</div>
				${block->with_f5__ovmj:default(0)}
				<div>
					<textarea form="st_f" name="Details" data-style="box-sizing:border-box; ${args->f5_style__ksj6:html}" placeholder="${args->f5__z1qz:html}"></textarea>
				</div>
				${block->with_f4__lft0:default(0)}
				<div data-style="${args->style9__menn:html:default('text-align: left;
margin-top: 0px;
margin-right: 0px;
margin-bottom: 11px;
margin-left: 0px;
font-weight: 300;
font-size: 15px;
color: rgba(51, 51, 51, 0.83);
')}">
					<label>
						<input form="st_f" name="Checkbox" type="checkbox" data-prop-column="${args->f4_db__rvzd:html}" value="1">
						${args->text_9__i72g:default(Optin for marketing and promotions)}
					</label>
				</div>

                <button form="st_f" type="submit" class="$flat_btn" with_responsive="1" style="display:block; border:0; white-space:normal; box-sizing:border-box; ${args->button_style2__ef2g:html:default('display: block;
padding-top: 8px;
padding-right: 32px;
padding-bottom: 8px;
padding-left: 32px;
font-family: Karla, HelveticaNeue, "Helvetica Neue", sans-serif;
font-weight: normal;
font-size: 12px;
width: 100%;
min-height: 48px;
background: #4848a1;
border-color: #4848a1;
color: white;
border-bottom: 0px solid #3f75bd;
border-radius: 4px;
text-transform: uppercase;
')}" hover_style="${args->button_h_style__iy3x:html:default('background-color: #111111;
border-color: #fff;
color: #FFFFFF;')}">
					${args->button_caption__lmzd:default(SEND)}
                </button>
			</div>
		</div>
		<div data-case="b" data-style="${args->style10:html:default('color: rgb(15, 9, 9);')}">
			${args->success__dpax:default('<div style="text-align: center;">&nbsp;
<p><span style="font-size:36px;">Awesome! We will keep you posted.</span></p>
</div>
')}
		</div>
	</div>

	${args->footer__lqk5:default('<p>We are GDPR compliant and will not spam you. By clicking the above button, you agree to our <a href="https://www.tsg-training.co.uk/privacy-policy/" target="_blank">Privacy Policy</a>.</p>
')}

</div>

${menu name='Box', icon='th-large'}
	${menu args->style__c0gv name='Style', type='css', param='with_responsive=1'}
	${menu args->content_padding name='Content box padding', type='css', param='with_responsive=1'}
	${menu args->round name='No cut cell', type='checkbox', param='value_off=', param='value_on=1'}
	${menu args->eq_cell_width name='Equal cell width', type='checkbox', param='value_off=', param='value_on=1'}
	${menu args->eq_cell_height name='Equal cell height', type='checkbox', param='value_off=', param='value_on=1'}
	${menu args->space_between_items name='Space between items', type='css_length', param='with_responsive=1'}
	${menu args->border_color name='Border color', type='color'}
	${menu args->round_border name='Round border', type='css_length'}
${menu name='Close button', icon='close'}
	${menu block->show_close_button__bzrx name='Show close button'}
	${menu args->close_button__yj9r name='Close button', type='dontshowagain'}
${menu name='Slider options', icon='arrow-right'}
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
${menu name='Header', icon='bars'}
	${menu block->with_header name='With Header'}
	${menu args->header_text name='Header text'}
	${menu args->header_style name='Header style', type='css', param='with_responsive=1'}
${menu name='Text', icon='bars'}
	${menu args->line_1__ycvk name='Line 1 Text'}
${menu name='Name Box', icon='edit'}
	${menu block->with_f2__xu0n name='With Name'}
	${menu args->f2_db__i80f name='Name save to database', type='select_social', param='with_empty=1'}
	${menu args->f2__utq1 name='Name Placeholder Text'}
	${menu args->f1_style__dsv8 name='Input style', type='css', param='with_responsive=1'}
${menu name='Telephone Box', icon='edit'}
	${menu block->with_f6__hhn1 name='With Telephone'}
	${menu args->f6_db__j6p2 name='Telephone save to database', type='select_social', param='with_empty=1'}
	${menu args->f6_req__hj9h name='Telephone is required field', type='checkbox'}
	${menu args->f6__fo5x name='Telephone Placeholder Text'}
${menu name='Email Box', icon='envelope'}
	${menu args->f3__pheb name='Email Placeholder Text'}
	${menu args->f3_db__s3sv name='Email save to database', type='select_social', param='with_empty=1'}
${menu name='Details Box', icon='edit'}
	${menu block->with_f5__ovmj name='With Details'}
	${menu args->f5__z1qz name='Details Placeholder Text'}
	${menu args->f5_style__ksj6 name='Input style', type='css', param='with_responsive=1'}
${menu name='Checkbox', icon='edit'}
	${menu block->with_f4__lft0 name='With Checkbox'}
	${menu args->style9__menn name='Checkbox Style', type='css', param='with_responsive=1'}
	${menu args->f4_db__rvzd name='Checkbox save to database', type='select_social', param='with_empty=1'}
	${menu args->text_9__i72g name='Text'}
${menu name='After submit', icon='check'}
	${menu args->success__dpax name='Thank you text'}
	${menu args->custom__bw0n name='After submit execute this JavaScript', type='textarea'}
	${menu args->style10 name='Thank you text Style', type='css', param='with_responsive=1'}
	${menu args->redir name='After submit redirect to this URL. Placeholders like {Field name} will be substituted'}
	${menu args->redir_delay name='Redirect delay, sec', type='number'}
${menu name='Action button', icon='check'}
	${menu args->button_caption__lmzd name='Caption'}
	${menu args->button_style2__ef2g name='Style', type='css'}
	${menu args->button_h_style__iy3x name='Hover Style', type='css'}
${menu name='Footer', icon='bars'}
	${menu args->footer__lqk5 name='Footer'}
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
${menu name='Discount badge', icon='align-justify', description='Set discount badge to appear for a discounted product, you may choose to set it to show only if the discount is greater than X.'}
	${menu block->with_discount_badge name='With new badge'}
	${menu args->min_discount_percent name='Show discount badge if % ≥', type='number', param='min=1'}
	${menu args->discount_badge_style name='Badge style', type='css', param='with_responsive=1'}
	${menu args->discount_badge_text_style name='Badge text style', type='css', param='with_responsive=1'}
	${menu args->discount_badge_text name='Text'}
${menu name='New badge', icon='align-justify', description='Set "New" badge to appear for items debut recently.
You may choose a time frame for a product to be considered new. * For new accounts/product feed, all products are new until the day setting condition has been met.'}
	${menu block->with_new_badge name='With discount badge'}
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
${menu name='Stock badge', icon='align-justify', description='Set "Low in stock" badge to appear for low stock items.
In addition, you can set the quantity number below it a product is considered to be low in stock.  This requires you to populate "quantity" on your product feed.'}
	${menu block->with_stock_badge name='With stock badge'}
	${menu args->badge_if_less_stock name='Show stock badge if items less than', type='number', param='min=1'}
	${menu args->stock_badge_style name='Badge style', type='css', param='with_responsive=1'}
	${menu args->stock_badge_text_style name='Badge text style', type='css', param='with_responsive=1'}
	${menu args->stock_badge_text name='Text'}
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
${menu name='Product text/desc', icon='align-justify'}
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
${menu name='Quick add to cart button', icon='cart-plus', description='Set the widget button to add items to the visitor cart. This feature requires you to set a quick add to cart under product interaction settings>add to cart.'}
	${menu block->with_cart name='With add to cart'}
	${menu args->button name='Text'}
	${menu args->button_icon name='Icon on button', type='icon'}
	${menu args->button_icon_style name='Icon on button style', type='css'}
	${menu args->button_style name='Button style', type='css', param='with_responsive=1'}
	${menu args->button_style_hover name='Button hover style', type='css'}
	${menu block->animate_cart_button name='Slide button on mouse hover'}
	${menu args->cart_is_code name='Button triggers "Add to cart" integration code', type='checkbox', param='value_off=', param='value_on=1'}
	${menu args->cart_arg name='Argument to pass to your defined Add to Cart function (optional)', visible_if='args.cart_is_code'}
	${menu args->cart_yes name='Javascript on complete (optional)', type='source_javascript', visible_if='args.cart_is_code'}
	${menu args->cart_no name='Javascript on error (optional)', type='source_javascript', visible_if='args.cart_is_code'}
${menu name='Onclick target URL', icon='link'}
	${menu p->cart_url name='Link target URL', column_tags='url, custom text'}
	${menu args->target name='Open link in', type='a_target'}
${menu name='Rating', icon='star', description='Show product rating when available
This requires you to populate "Rank" on your product feed   .'}
	${menu block->rating name='With rating'}
	${menu p->rank name='Rating'}
	${menu args->rating_style name='Colors', type='css', param='vars=--bgcolor:color; --border-color:color'}
${menu name='Site statistics: 1-day', icon='bar-chart', description='Show number of viewed or purchases in the last 24 hours for a given item as tracked by Personyze. You can set a condition not to show if the number of views/purchases is below X number.'}
	${menu block->stats_1day name='Site statistics: 1day'}
	${menu args->hide_no_view_1day name='Hide statistics if less views than', type='number', param='min=0'}
	${menu args->hide_no_goal_1day name='Hide statistics if less purchases than', type='number', param='min=0'}
	${menu args->text_style_1day name='Style', type='css'}
	${menu args->n_viewed_1day name='Text'}
	${menu args->n_goal_1day name='Text'}
${menu name='Site statistics: week', icon='bar-chart', description='Show number of viewed or purchases in the last week for a given item as tracked by Personyze. You can set a condition not to show if the number of views/purchases is below X number.'}
	${menu block->stats_week name='Site statistics: week'}
	${menu args->hide_no_view_week name='Hide statistics if less views than', type='number', param='min=0'}
	${menu args->hide_no_goal_week name='Hide statistics if less purchases than', type='number', param='min=0'}
	${menu args->text_style_week name='Style', type='css'}
	${menu args->n_viewed_week name='Text'}
	${menu args->n_goal_week name='Text'}
${menu name='Price', icon='dollar'}
	${menu block->price name='With price'}
	${menu args->price_style name='Price style', type='css', param='with_responsive=1'}
	${menu args->old_price_style name='Price before discount - style', type='css'}
	${menu args->old_price_before name='Price before discount - text before'}
	${menu args->p_price_before_discount name='Price before discount'}
	${menu args->old_price_after name='Price before discount - text before'}
	${menu args->p_price_after_discount name='Price after discount'}
	${menu args->new_price_style name='Price after discount - style', type='css'}
	${menu args->sale_text_style name='Sale text style', type='css'}
	${menu args->sale_text name='Sale text'}
	${menu args->nosale_price_style name='Price without discount - style', type='css'}
```


## Form



```
<div class="$responsive" data-style="position:relative; text-align:center; ${args->style__c0gv:html:default('color: #333;
position: relative;
top: 0px;
box-shadow: 0 0 black;
background-color: #fff;
width: auto;
border-radius: 4px;
padding-top: sel(20px, 2px);
padding-right: 48px;
padding-bottom: sel(20px, 2px);
padding-left: 48px;
font-family: Karla, HelveticaNeue, "Helvetica Neue", sans-serif;
max-height: none;
max-width: 550px;
')}">
	${block->animate_cart_button:default(1)}
	<style>
		.st-add-to-cart-button {overflow:hidden}
		.st-add-to-cart-button > a {transition: all ease 0.3s; position:relative; top: 5em; opacity: 0}
		.st-td-hover .st-add-to-cart-button > a {top: 0; opacity: 1}
	</style>

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

	${block->show_close_button__bzrx:default(1)}
	<div style="position:absolute; top:16px; right:16px; z-index:2">
		${args->close_button__yj9r:default('<img style="width:19px;" src="https://static.personyze.com/upload/4035/18e8b5d116db12cf.png" class="$personyze_button_dont_show_again" data-action_id="${action_id}" data-n_sessions="0">')}
	</div>
	<div class="$switch-elem" data-case="a" data-style="box-sizing:border-box">
		<div data-case="a" class="$cform st_f" ontplsubmit="personyze.push(['Submit', ${action_id:json:html}, this._get_value_ex(), arguments[1], arguments[2]]); return true" ontplaftersubmit="
			var sw=this.parentNode;
			sw._set_case('b', null, false, {template: 'animator_fade'});
			var js=this.dataset.customJs.trim(), redir=this.dataset.redir.trim(), t=this.dataset.redirDelay, v=this._get_value();
			if (js) new Function('action_id', 'by_id', 'data', 'report_error', js).call(this, ${action_id:json:html}, by_id, v);
			if (redir) setTimeout(function() {location.href=redir.replace(/\{([^{\r\n]+)\}/g, function(a, w) {return v[w]==null ? a : encodeURIComponent(v[w])})}, t*1000)
		" data-custom-js="${args->custom__bw0n:html}" data-redir="${args->redir:html}" data-redir-delay="${args->redir_delay:html}" style="position:relative; width:100%; height:100%">
			<div data-style="position:relative; z-index:1; background-color:white; margin:auto; width:80%; padding:0.6em">
				${block->with_header:default(1)}
				<div data-style="${args->header_style:html:default('border: solid black 1px;
padding: 0.6em;
font-size: 19px;
')}">
					${args->header_text:default(Wait a minute!)}
				</div>
			</div>
			<div data-style="position:relative; z-index:0; top:0; background-color:white; font-size:18px">
				${args->line_1__ycvk:default('<span style="font-size:20px;">Send your recent views to your inbox?</span><br />
<span style="font-size:12px;">Good choice! We can email your recent views to your inbox.</span><br />
&nbsp;')}

				<div data-style="${args->content_padding:html:default('width: 100%;
margin-top: auto;
margin-right: auto;
margin-bottom: 2em;
margin-left: auto;
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
							${foreach products as p order by p->time_created desc limit 12}
								<td style="position:relative; height:1px; padding:0; text-align:center; background-color:white; vertical-align:top; border:solid ${args->border_color:html:default('#dddddd')} 1px">
									<a data-personyze-click-target="products ${p->internal_id:html}" href="${p->cart_url:html}" target="${args->target:html:default(_self)}" data-style="position:relative; display:flex; height:100%; margin:auto; box-sizing:border-box; overflow:hidden; width:${args->img_width:html:default('sel(200px, 44vw)')}; text-decoration:none; ${args->img_alignment:html:default('align-items: baseline;
		')}">
										<img class="st-zoom" src="${p->image_big_url:html}" data-style="width:auto; height:auto; max-width:100%; max-height:${args->img_max_height:html:default('sel(209px, 120px)')}; border:none">

										${if p->image_medium_url <> ''}
											${block->with_hover_image:default(0)}
											<div style="position:absolute; display:flex; left:0; top: 0; width:100%; height:100%; ${args->img_alignment:html}">
												<img src="${p->image_medium_url:html}" data-style="width:auto; height:auto; max-width:100%; max-height:${args->img_max_height:html}; border:none">
											</div>
										${end}

										${block->with_discount_badge:default(1)}
										<span>
											${if p->discount_percent >= args->min_discount_percent:default(1)}
												<div data-style="position: absolute; ${args->discount_badge_style:html:default('top: 0;
right: 48px;
width: 7em;
height: 7em;
font-size: 7px;
text-shadow: rgba(255,255,255,0.5) 0px 3px 3px;
background-color: red;
border: double rgb(221, 228, 165) 6px;
color: rgb(252, 249, 249);
border-radius: 50%;
display: flex;
justify-content: center;
align-items: center;
')}">
													<span data-style="${args->discount_badge_text_style:html:default('line-height: 1.25;
font-size: 9px;
font-weight: 600;
')}">${args->discount_badge_text:default('<div style="font-size:14px">${p->discount_percent:floor}%</div>
Discount')}</span>
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

										${block->with_stock_badge:default(1)}
										<span>
											${if p->inventory between 1 and args->badge_if_less_stock:default(3)}
												<div data-style="position: absolute; ${args->stock_badge_style:html:default('bottom: 0;
left: 48px;
font-size: 14px;
text-shadow: rgba(255,255,255,0.5) 0px 3px 3px;
background-color: #db3932;
color: rgb(256, 256, 256);
display: flex;
justify-content: center;
align-items: center;
padding: 0.3em;
')}">
													<span data-style="${args->stock_badge_text_style:html:default('font-size: 16px;
font-weight: 500;
')}">${args->stock_badge_text:default('${p->inventory}&nbsp;left in stock')}</span>
												</div>
											${end}
										</span>

										${block->with_wishlist_badge:default(0)}
										<span class="$switch-elem"
											data-case="${foreach products_interactions as w where w->internal_id = p->internal_id and w->interaction_status = 'favorite' limit 1}on${end}"
											data-p="${p->internal_id:html}"
											data-style="position:absolute; transition: all 0.3s ease; ${args->wishlist_style:html:default('top: 5px;
right: 5px;
color: rgb(119, 181, 115);
font-size: 25px;
')}"
											onclick="var on=this._get_case(); _S_T.push([on ? 'Product Unliked' : 'Product Liked', this.dataset.p]); this._set_case(on ? '' : 'on'); event.stopPropagation(); event.preventDefault()"
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

									${block->with_custom_column:default(0)}
									<div>
										<div style="${args->custom_column_style:html:default('text-align: left;
padding: 1em;
font-weight: 600;
')}">${args->custom_column:html:default('${p->category}')}</div>
									</div>

									<a data-personyze-click-target="products ${p->internal_id:html}" href="${p->cart_url:html}" target="${args->target:html}" data-style="display:block; margin:auto; box-sizing:border-box; width:${args->img_width:html}; text-decoration:none">
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
															${args->n_viewed_1day:default('<div>${s->n_viewed*1} views today</div>
')}
														${end}
														${if s->n_goal > 0}
															${args->n_goal_1day:default('<div>${s->n_goal*1}&nbsp; purchases today</div>
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
															${args->n_viewed_week:default('<div>Good choice! This product has been popular in the last week! ${s->n_viewed*1} views this week.</div>
')}
														${end}
														${if s->n_goal > 0}
															${args->n_goal_week:default('<div>${s->n_goal*1}&nbsp; purchases this week</div>
')}
														${end}
													</div>
												${end}
											${end}
										${end}
									</span>

									<div style="clear:left;"></div>
									${block->price:default(1)}
									<div data-style="margin:auto; box-sizing:border-box; width:${args->img_width:html}; ${args->price_style:html}">
										${if p->price_after_discount}
											${if p->price_after_discount < p->price_before_discount}
												<span style="white-space:nowrap">
													<span style="${args->old_price_style:html:default('font-size: 22px;
font-weight: 700;
text-decoration: line-through;
')}">
														${args->old_price_before}${args->p_price_before_discount:default('$${p->price_before_discount:sprintf(''%[#,###.#]f'')}')}${args->old_price_after}
													</span>
												</span>
												<span style="white-space:nowrap">
													<span style="${args->new_price_style:html:default('font-size: 22px;
font-weight: 700;
color: red;
')}">
														${args->old_price_before)}${args->p_price_after_discount:default('$${p->price_after_discount:sprintf(''%[#,###.#]f'')}')}${args->old_price_after}
													</span>
												</span>
												<div style="${args->sale_text_style:html:default('display: inline-block;
font-size: 50%;
line-height: 1;
')}">
													${args->sale_text:default('<span style="white-space:nowrap; font-weight:400; font-size:80%; color:red">sale<br />
price</span>')}
												</div>
											${else}
												<span style="white-space:nowrap; ${args->nosale_price_style:html:default('font-size: 22px;
font-weight: 700;
')}">
													${args->old_price_before}${args->p_price_before_discount}${args->old_price_after}
												</span>
											${end}
										${end}
									</div>
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

									${block->with_link_button:default(0)}
									<div data-style="box-sizing:border-box; ${args->link_button_box_style:html:default('text-align: center;
')}">
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

									${block->with_cart:default(1)}
									<div class="st-add-to-cart-button">
										<a
											data-personyze-click-target="products ${p->internal_id:html}"
											class="$flat_btn $button_add_to_cart"
											data-is_code="${args->cart_is_code:html:default(1)}"
											data-action_id="${action_id:html}"
											data-url="${p->cart_url:html}"
											data-json-add_to_cart_columns="${p->add_to_cart_columns:html}"
											data-arg="${args->cart_arg:html}"
											data-yes="${args->cart_yes:html:default('location.href=location.href')}"
											data-no="${args->cart_no:html}"
											data-style="box-sizing:border-box; ${args->button_style:html:default('color: rgb(253, 252, 252);
padding-top: 9px;
padding-right: 13px;
padding-bottom: 9px;
padding-left: 13px;
font-size: 14px;
line-height: 14px;
font-weight: 700;
font-family: Lato;
margin: 15px;
background-color: #f57224;
width: auto;
')}" hover_style="${args->button_style_hover:html:default('color: rgb(253, 252, 252);
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
background-color: #f57224;
width: auto;
')}">
											<hr class="$icon ${args->button_icon:html:default(cart-plus)}" style="${args->button_icon_style:html:default('padding-right: 0.5em;
font-size: 100%;
color: inherit;
')}">
											${args->button:default(Add to cart)}
										</a>
									</div>
								</td>
							${end}
						</tr>
					</table>
					${block->pagination:default(0)}
					<div id="tsp" class="$table_slider_pagination" slider_id="ts" selected_color="${args->pagination_color_on:html:default('rgba(0, 0, 0, 1)')}" style="${args->pagination_color:html}"></div>
				</div>

				${block->with_f2__xu0n:default(1)}
				<div>
					<input form="st_f" name="Name" required="1" data-prop-column="${args->f2_db__i80f:html:default(first_name)}" data-style="box-sizing:border-box; ${args->f1_style__dsv8:html:default('margin-bottom: 20px;
padding: 10px;
font-family: Karla, HelveticaNeue, "Helvetica Neue", sans-serif;
font-weight: 400;
font-size: 16px;
width: 100%;
border: 1px solid rgb(62,62,62);
border-radius: 4px;
color: rgb(3, 1, 1);
text-align: left;
min-height: sel(48px, 23px);
')}" placeholder="${args->f2__utq1:html:default(Your First Name)}">
				</div>
				${block->with_f6__hhn1:default(0)}
				<div>
					<input form="st_f" name="Phone" type="tel" required="${args->f6_req__hj9h:html}" data-prop-column="${args->f6_db__j6p2:html}" data-style="box-sizing:border-box; ${args->f1_style__dsv8:html}" placeholder="${args->f6__fo5x:html}">
				</div>
				<div>
					<input form="st_f" name="Email" pattern="^[^\s@]+@[^\s@\.]+\.[^\s@]+$" required="1" data-prop-column="${args->f3_db__s3sv:html:default(email)}" data-style="box-sizing:border-box; ${args->f1_style__dsv8:html}" placeholder="${args->f3__pheb:html:default(Your Email Address)}">
				</div>
				${block->with_f5__ovmj:default(0)}
				<div>
					<textarea form="st_f" name="Details" data-style="box-sizing:border-box; ${args->f5_style__ksj6:html}" placeholder="${args->f5__z1qz:html}"></textarea>
				</div>
				${block->with_f4__lft0:default(1)}
				<div data-style="${args->style9__menn:html:default('text-align: left;
margin-top: 0px;
margin-right: 0px;
margin-bottom: 11px;
margin-left: 0px;
font-weight: 300;
font-size: 15px;
color: rgba(51, 51, 51, 0.83);
')}">
					<label>
						<input form="st_f" name="Checkbox" type="checkbox" data-prop-column="${args->f4_db__rvzd:html}" value="1">
						${args->text_9__i72g:default(Optin for marketing and promotions)}
					</label>
				</div>

                <button form="st_f" type="submit" class="$flat_btn" with_responsive="1" style="display:block; border:0; white-space:normal; box-sizing:border-box; ${args->button_style2__ef2g:html:default('display: block;
padding-top: 8px;
padding-right: 32px;
padding-bottom: 8px;
padding-left: 32px;
font-family: Karla, HelveticaNeue, "Helvetica Neue", sans-serif;
font-weight: normal;
font-size: 12px;
width: 100%;
min-height: 48px;
background: #4848a1;
border-color: #4848a1;
color: white;
border-bottom: 0px solid #3f75bd;
border-radius: 4px;
text-transform: uppercase;
')}" hover_style="${args->button_h_style__iy3x:html:default('background-color: #111111;
border-color: #fff;
color: #FFFFFF;')}">
					${args->button_caption__lmzd:default(SEND)}
                </button>
			</div>
		</div>
		<div data-case="b" data-style="${args->style10:html:default('color: rgb(15, 9, 9);')}">
			${args->success__dpax:default('<div style="text-align: center;">&nbsp;
<p><span style="font-size:36px;">Awesome! We will keep you posted.</span></p>
</div>
')}
		</div>
	</div>

	${args->footer__lqk5:default('<p>We are GDPR compliant and will not spam you. By clicking the above button, you agree to our <a href="https://www.tsg-training.co.uk/privacy-policy/" target="_blank">Privacy Policy</a>.</p>
')}

</div>

${menu name='Box', icon='th-large'}
	${menu args->style__c0gv name='Style', type='css', param='with_responsive=1'}
	${menu args->content_padding name='Content box padding', type='css', param='with_responsive=1'}
	${menu args->round name='No cut cell', type='checkbox', param='value_off=', param='value_on=1'}
	${menu args->eq_cell_width name='Equal cell width', type='checkbox', param='value_off=', param='value_on=1'}
	${menu args->eq_cell_height name='Equal cell height', type='checkbox', param='value_off=', param='value_on=1'}
	${menu args->space_between_items name='Space between items', type='css_length', param='with_responsive=1'}
	${menu args->border_color name='Border color', type='color'}
	${menu args->round_border name='Round border', type='css_length'}
${menu name='Close button', icon='close'}
	${menu block->show_close_button__bzrx name='Show close button'}
	${menu args->close_button__yj9r name='Close button', type='dontshowagain'}
${menu name='Slider options', icon='arrow-right'}
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
${menu name='Header', icon='bars'}
	${menu block->with_header name='With Header'}
	${menu args->header_text name='Header text'}
	${menu args->header_style name='Header style', type='css', param='with_responsive=1'}
${menu name='Text', icon='bars'}
	${menu args->line_1__ycvk name='Line 1 Text'}
${menu name='Name Box', icon='edit'}
	${menu block->with_f2__xu0n name='With Name'}
	${menu args->f2_db__i80f name='Name save to database', type='select_social', param='with_empty=1'}
	${menu args->f2__utq1 name='Name Placeholder Text'}
	${menu args->f1_style__dsv8 name='Input style', type='css', param='with_responsive=1'}
${menu name='Telephone Box', icon='edit'}
	${menu block->with_f6__hhn1 name='With Telephone'}
	${menu args->f6_db__j6p2 name='Telephone save to database', type='select_social', param='with_empty=1'}
	${menu args->f6_req__hj9h name='Telephone is required field', type='checkbox'}
	${menu args->f6__fo5x name='Telephone Placeholder Text'}
${menu name='Email Box', icon='envelope'}
	${menu args->f3__pheb name='Email Placeholder Text'}
	${menu args->f3_db__s3sv name='Email save to database', type='select_social', param='with_empty=1'}
${menu name='Details Box', icon='edit'}
	${menu block->with_f5__ovmj name='With Details'}
	${menu args->f5__z1qz name='Details Placeholder Text'}
	${menu args->f5_style__ksj6 name='Input style', type='css', param='with_responsive=1'}
${menu name='Checkbox', icon='edit'}
	${menu block->with_f4__lft0 name='With Checkbox'}
	${menu args->style9__menn name='Checkbox Style', type='css', param='with_responsive=1'}
	${menu args->f4_db__rvzd name='Checkbox save to database', type='select_social', param='with_empty=1'}
	${menu args->text_9__i72g name='Text'}
${menu name='After submit', icon='check'}
	${menu args->success__dpax name='Thank you text'}
	${menu args->custom__bw0n name='After submit execute this JavaScript', type='textarea'}
	${menu args->style10 name='Thank you text Style', type='css', param='with_responsive=1'}
	${menu args->redir name='After submit redirect to this URL. Placeholders like {Field name} will be substituted'}
	${menu args->redir_delay name='Redirect delay, sec', type='number'}
${menu name='Action button', icon='check'}
	${menu args->button_caption__lmzd name='Caption'}
	${menu args->button_style2__ef2g name='Style', type='css'}
	${menu args->button_h_style__iy3x name='Hover Style', type='css'}
${menu name='Footer', icon='bars'}
	${menu args->footer__lqk5 name='Footer'}
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
${menu name='Discount badge', icon='align-justify', description='Set discount badge to appear for a discounted product, you may choose to set it to show only if the discount is greater than X.'}
	${menu block->with_discount_badge name='With new badge'}
	${menu args->min_discount_percent name='Show discount badge if % ≥', type='number', param='min=1'}
	${menu args->discount_badge_style name='Badge style', type='css', param='with_responsive=1'}
	${menu args->discount_badge_text_style name='Badge text style', type='css', param='with_responsive=1'}
	${menu args->discount_badge_text name='Text'}
${menu name='New badge', icon='align-justify', description='Set "New" badge to appear for items debut recently.
You may choose a time frame for a product to be considered new. * For new accounts/product feed, all products are new until the day setting condition has been met.'}
	${menu block->with_new_badge name='With discount badge'}
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
${menu name='Stock badge', icon='align-justify', description='Set "Low in stock" badge to appear for low stock items.
In addition, you can set the quantity number below it a product is considered to be low in stock.  This requires you to populate "quantity" on your product feed.'}
	${menu block->with_stock_badge name='With stock badge'}
	${menu args->badge_if_less_stock name='Show stock badge if items less than', type='number', param='min=1'}
	${menu args->stock_badge_style name='Badge style', type='css', param='with_responsive=1'}
	${menu args->stock_badge_text_style name='Badge text style', type='css', param='with_responsive=1'}
	${menu args->stock_badge_text name='Text'}
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
${menu name='Product text/desc', icon='align-justify'}
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
${menu name='Quick add to cart button', icon='cart-plus', description='Set the widget button to add items to the visitor cart. This feature requires you to set a quick add to cart under product interaction settings>add to cart.'}
	${menu block->with_cart name='With add to cart'}
	${menu args->button name='Text'}
	${menu args->button_icon name='Icon on button', type='icon'}
	${menu args->button_icon_style name='Icon on button style', type='css'}
	${menu args->button_style name='Button style', type='css', param='with_responsive=1'}
	${menu args->button_style_hover name='Button hover style', type='css'}
	${menu block->animate_cart_button name='Slide button on mouse hover'}
	${menu args->cart_is_code name='Button triggers "Add to cart" integration code', type='checkbox', param='value_off=', param='value_on=1'}
	${menu args->cart_arg name='Argument to pass to your defined Add to Cart function (optional)', visible_if='args.cart_is_code'}
	${menu args->cart_yes name='Javascript on complete (optional)', type='source_javascript', visible_if='args.cart_is_code'}
	${menu args->cart_no name='Javascript on error (optional)', type='source_javascript', visible_if='args.cart_is_code'}
${menu name='Onclick target URL', icon='link'}
	${menu p->cart_url name='Link target URL', column_tags='url, custom text'}
	${menu args->target name='Open link in', type='a_target'}
${menu name='Rating', icon='star', description='Show product rating when available
This requires you to populate "Rank" on your product feed   .'}
	${menu block->rating name='With rating'}
	${menu p->rank name='Rating'}
	${menu args->rating_style name='Colors', type='css', param='vars=--bgcolor:color; --border-color:color'}
${menu name='Site statistics: 1-day', icon='bar-chart', description='Show number of viewed or purchases in the last 24 hours for a given item as tracked by Personyze. You can set a condition not to show if the number of views/purchases is below X number.'}
	${menu block->stats_1day name='Site statistics: 1day'}
	${menu args->hide_no_view_1day name='Hide statistics if less views than', type='number', param='min=0'}
	${menu args->hide_no_goal_1day name='Hide statistics if less purchases than', type='number', param='min=0'}
	${menu args->text_style_1day name='Style', type='css'}
	${menu args->n_viewed_1day name='Text'}
	${menu args->n_goal_1day name='Text'}
${menu name='Site statistics: week', icon='bar-chart', description='Show number of viewed or purchases in the last week for a given item as tracked by Personyze. You can set a condition not to show if the number of views/purchases is below X number.'}
	${menu block->stats_week name='Site statistics: week'}
	${menu args->hide_no_view_week name='Hide statistics if less views than', type='number', param='min=0'}
	${menu args->hide_no_goal_week name='Hide statistics if less purchases than', type='number', param='min=0'}
	${menu args->text_style_week name='Style', type='css'}
	${menu args->n_viewed_week name='Text'}
	${menu args->n_goal_week name='Text'}
${menu name='Price', icon='dollar'}
	${menu block->price name='With price'}
	${menu args->price_style name='Price style', type='css', param='with_responsive=1'}
	${menu args->old_price_style name='Price before discount - style', type='css'}
	${menu args->old_price_before name='Price before discount - text before'}
	${menu args->p_price_before_discount name='Price before discount'}
	${menu args->old_price_after name='Price before discount - text before'}
	${menu args->p_price_after_discount name='Price after discount'}
	${menu args->new_price_style name='Price after discount - style', type='css'}
	${menu args->sale_text_style name='Sale text style', type='css'}
	${menu args->sale_text name='Sale text'}
	${menu args->nosale_price_style name='Price without discount - style', type='css'}
```


