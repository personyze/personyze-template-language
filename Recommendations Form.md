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


## Form with cart item



```
<div class="$responsive" data-style="position:relative; text-align:center; ${args->style:html:default('color: #333;
position: relative;
top: 0px;
box-shadow: 0 0 black;
min-width: 600px;
background-color: #fff;
width: auto;
border-radius: 4px;
padding-top: 40px;
padding-right: 48px;
padding-bottom: 40px;
padding-left: 48px;
font-family: Karla, HelveticaNeue, "Helvetica Neue", sans-serif;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(0, 0, 'Box', 'th-large')}">
	${block->show_close_button:default(1):arg_name(Show close button):arg_section(4, 0, 'Close button', 'close')}
	<div style="position:absolute; top:16px; right:16px; z-index:2">
		${args->close_button:default('<img style="width:19px;" src="https://static.emarketer.com/upload/4035/18e8b5d116db12cf.png" class="$emarketer_button_dont_show_again" data-action_id="${action_id}" data-n_sessions="0">'):input_type(dontshowagain):arg_name(Close button):arg_section(4, 1, 'Close button', 'close')}
	</div>
	<div class="$switch-elem" data-case="a" data-style="box-sizing:border-box">
		<div data-case="a" class="$cform st_f" ontplsubmit="emarketer.push(['Submit', '${action_id:html}', this._get_value_ex(), arguments[1], arguments[2]]); return true" ontplaftersubmit="this.parentNode._set_case('b', null, false, {template: 'animator_fade'}); var email=this.querySelector('input[data-prop-column=email]').value; var ids=[]; this.querySelectorAll('*[data-emarketer-click-target]').forEach(function(e) {ids.push(e.dataset.emarketerClickTarget.replace(/^\w+\s/, ''))}); new Function(this.dataset.custom).call(this, email, ids)" data-custom="${args->custom:html:input_type(textarea):arg_name(Javascript after submit):arg_section(0, 1, 'Box', 'th-large')}">
			<div data-style="position:relative; z-index:1; background-color:white; margin:auto; width:80%; padding:0.6em">
				<div data-style="border:solid black 1px; padding:0.6em; font-size:19px">
					Wait a minute!
				</div>
			</div>
			<div data-style="position:relative; z-index:0; top:0; background-color:white; font-size:18px">
				${args->line_1:default('<p style="padding:0;font-size:22px;"><strong>SAVE YOUR CART BEFORE YOU LEAVE</strong></p>
'):arg_name(Line 1 Text):arg_section(5, 0, 'Text', 'bars')}
				<table style="width:100%; border-collapse:separate; border-spacing:12px 0; margin-bottom:1.2em">
					<tr class="$table_slider" data-disabled="${args->with_slider:html:default(1):input_type(checkbox):input_props('value_off=1','value_on='):arg_name(Use slider widget):arg_section(2, 1, 'With slider', 'arrow-right')}" style="border:none" for_max_vw="${args->for_max_vw:html:input_type(css_length):input_props('with_options=always'):arg_name(Slider widget only if screen width is less than or equal to):arg_section(2, 2, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" eq_cell_width="1" eq_cell_height="1" arrows_line="${args->arrows_line:html:input_type(checkbox):input_props('value_off=-1','value_on=0'):arg_name(Arrows in the middle of images):arg_section(2, 6, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" arrow_back_img="${args->arrow_back_img:html:input_type(emarketer_media_url):arg_name(Left arrow image):arg_section(2, 3, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" arrow_forward_img="${args->arrow_forward_img:html:input_type(emarketer_media_url):arg_name(Right arrow image):arg_section(2, 4, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" pagination_id="tsp" arrow_back_id="button_back" arrow_forward_id="button_forward" arrows_offset="${args->arrows_offset:html:input_type(number):arg_name(Slider arrows offset):arg_section(2, 5, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" hide_buttons="${args->hide_buttons:html:input_type(checkbox):input_props('value_off=','value_on=1'):arg_name(Hide arrow buttons when nothing to scroll):arg_section(2, 0, 'With slider', 'arrow-right'):visible_if('block.title-0 && block.with_arrows-0')}">
						${foreach products_interactions as p where p->interaction_status IN ('extra') order by p->interaction_time desc limit 16}
							<td style="${args->td_style:html:default('padding:0; text-align:center'):input_type(css):input_props('with_responsive=1'):arg_name(Cell Style):arg_section(1, 1, 'Cells', 'th-large')}">
								<a data-emarketer-click-target="products ${p->internal_id:html}" href="${p->cart_url:html:arg_name(Link target URL):arg_section(10, 0, 'Link target URL', 'link'):column_tags('url','custom text')}" target="${args->target:html:default(_self):input_type(a_target):arg_name(Open link in):arg_section(10, 1, 'Link target URL', 'link')}" data-style="display:block; margin:auto; box-sizing:border-box; width:${args->img_width:html:default('sel(120px, 30vw)'):input_type(css_length):input_props('with_responsive=1'):arg_name(Cell width):arg_section(1, 0, 'Cells', 'th-large')}">
									<img src="${p->image_big_url:html:arg_name(Item image):arg_section(6, 0, 'Image', 'close'):column_tags(image)}" data-style="${args->img_style:html:default('border: double white 5px;
width: auto;
height: auto;
max-height: 120px;
max-width: 120px;'):input_type(css):input_props('with_responsive=1'):arg_name(Image style):arg_section(6, 1, 'Image', 'close')}">
								</a>
								<div data-style="margin:auto; box-sizing:border-box; width:${args->img_width:html:default('sel(120px, 30vw)'):input_type(css_length):input_props('with_responsive=1'):arg_name(Cell width):arg_section(1, 0, 'Cells', 'th-large')}">
									<div data-style="${args->a_css:html:default('font-size: 0px;
color: rgb(0,110,204);
text-decoration: none;
text-align: center;'):input_type(css):input_props('with_responsive=1'):arg_name(Title):arg_section(7, 3, 'Text', 'align-justify')}">
										<a style="text-decoration:inherit; color:inherit" href="${p->cart_url:html:arg_name(Link target URL):arg_section(10, 0, 'Link target URL', 'link'):column_tags('url','custom text')}">
											${p->title:arg_name(Item text):arg_section(7, 1, 'Text', 'align-justify')}
										</a>
									</div>
								</div>
								${block->rating:default(0):arg_name(With rating):arg_section(8, 0, 'Rating', 'star')}
								<div style="${args->rating_style:html:input_type(css):arg_name(Rating style)}">
									<input class="$rating" value="${p->rank:html:arg_name(Rating):arg_section(8, 1, 'Rating', 'star')}" max="${args->rank_max:html:input_type(number):arg_name(Maximum rating number that corresponds to 100%):arg_section(8, 2, 'Rating', 'star')}">
								</div>
								${block->price:default(0):arg_name(With price):arg_section(9, 0, 'Price', 'tag')}
								<div data-style="margin:auto; box-sizing:border-box; width:${args->img_width:html:default('sel(120px, 30vw)'):input_type(css_length):input_props('with_responsive=1'):arg_name(Cell width):arg_section(1, 0, 'Cells', 'th-large')}">
									${if p->price}
										${if p->sale_price and p->sale_price < p->price}
											<div style="${args->sale_style:html:input_type(css):input_props('with_responsive=1'):arg_name('Price after discount: style'):arg_section(9, 5, 'Price', 'tag')}">
												${args->before_price:arg_name(Text before price):arg_section(9, 2, 'Price', 'tag')}
												${p->sale_price:truncate(2):sprintf($%s):arg_name(Price after discount):arg_section(9, 3, 'Price', 'tag')}
												${args->after_price:arg_name(Text after price):arg_section(9, 1, 'Price', 'tag')}
											</div>
											<div style="${args->price_style:html:input_type(css):input_props('with_responsive=1'):arg_name('Price before discount: style'):arg_section(9, 6, 'Price', 'tag')}">
												${p->price:truncate(2):sprintf($%s):arg_name(Price before discount):arg_section(9, 4, 'Price', 'tag')}
											</div>
										${end}
										${if not p->sale_price or p->sale_price >= p->price}
											<div style="${args->price_style:html:input_type(css):input_props('with_responsive=1'):arg_name('Price before discount: style'):arg_section(9, 6, 'Price', 'tag')}">
												${args->before_price:arg_name(Text before price):arg_section(9, 2, 'Price', 'tag')}
												${p->price:truncate(2):sprintf($%s):arg_name(Price before discount):arg_section(9, 4, 'Price', 'tag')}
												${args->after_price:arg_name(Text after price):arg_section(9, 1, 'Price', 'tag')}
											</div>
										${end}
									${end}
								</div>
								${block->description:default(0):arg_name(With description):arg_section(7, 0, 'Text', 'align-justify')}
								<div data-style="margin:auto; box-sizing:border-box; width:${args->img_width:html:default('sel(120px, 30vw)'):input_type(css_length):input_props('with_responsive=1'):arg_name(Cell width):arg_section(1, 0, 'Cells', 'th-large')}">
									<div data-style="display:inline-block; ${args->a_css_3:html:input_type(css):input_props('with_responsive=1'):arg_name(Description):arg_section(7, 4, 'Text', 'align-justify')}; padding-bottom:0">
										${p->description:arg_name(Item text):arg_section(7, 2, 'Text', 'align-justify')}
									</div>
								</div>

								${block->button:default(0):arg_name(With button):arg_section(3, 0, 'Add Button', 'hand-pointer-o')}
								<div style="margin-top:0.4em">
									<a data-emarketer-click-target="products ${p->internal_id:html}" onclick="AddProductsToBasket(${p->internal_id:html}); _S_T.push(['Product Added to cart', '${p->internal_id:html}', 'action_id', ${action_id:html}]);" href="javascript:void(0);" data-style="display: inline-block; ${args->button_style:html:input_type(css):input_props('with_responsive=1'):arg_name(Button style):arg_section(3, 2, 'Add Button', 'hand-pointer-o')}">${args->button:arg_name('Text', 'Link target URL'):arg_section(3, 1, 'Add Button', 'hand-pointer-o')}</a>
								</div>
							</td>
						${end}
					</tr>
				</table>

				${block->with_f2:default(0):arg_name(With Name):arg_section(11, 0, 'Name Box', 'edit')}
				<div>
					<input form="st_f" name="Name" required="1" data-prop-column="${args->f2_db:html:input_type(select_social):input_props('with_empty=1'):arg_name(Name save to database):arg_section(11, 1, 'Name Box', 'edit')}" data-style="box-sizing:border-box; ${args->f1_style:html:default('margin-bottom: 20px;
padding: 10px;
font-family: Karla, HelveticaNeue, "Helvetica Neue", sans-serif;
font-weight: 400;
font-size: 16px;
width: 100%;
border: 1px solid rgb(62,62,62);
border-radius: 4px;
color: rgb(3, 1, 1);
text-align: left;
min-height: 48px;'):input_type(css):input_props('with_responsive=1'):arg_name(Input style):arg_section(11, 3, 'Name Box', 'edit')}" placeholder="${args->f2:html:arg_name(Name Placeholder Text):arg_section(11, 2, 'Name Box', 'edit')}">
				</div>
				<div>
					<input form="st_f" name="Email" pattern="^[^\s@]+@[^\s@\.]+\.[^\s@]+$" required="1" data-prop-column="${args->f3_db:html:default(email):input_type(select_social):input_props('with_empty=1'):arg_name(Email save to database):arg_section(12, 1, 'Email Box', 'envelope')}" data-style="box-sizing:border-box; ${args->f1_style:html:default('margin-bottom: 20px;
padding: 10px;
font-family: Karla, HelveticaNeue, "Helvetica Neue", sans-serif;
font-weight: 400;
font-size: 16px;
width: 100%;
border: 1px solid rgb(62,62,62);
border-radius: 4px;
color: rgb(3, 1, 1);
text-align: left;
min-height: 48px;'):input_type(css):input_props('with_responsive=1'):arg_name(Input style):arg_section(11, 3, 'Name Box', 'edit')}" placeholder="${args->f3:html:default(Email Address):arg_name(Email Placeholder Text):arg_section(12, 0, 'Email Box', 'envelope')}">
				</div>
				${block->with_f5:default(0):arg_name(With Details):arg_section(13, 0, 'Details Box', 'edit')}
				<div>
					<textarea form="st_f" name="Details" data-style="box-sizing:border-box; ${args->f5_style:html:input_type(css):input_props('with_responsive=1'):arg_name(Input style):arg_section(13, 2, 'Details Box', 'edit')}" placeholder="${args->f5:html:arg_name(Details Placeholder Text):arg_section(13, 1, 'Details Box', 'edit')}"></textarea>
				</div>
				${block->with_f4:default(0):arg_name(With Checkbox):arg_section(14, 0, 'Checkbox', 'edit')}
				<div data-style="${args->style9:html:input_type(css):input_props('with_responsive=1'):arg_name(Checkbox Style):arg_section(14, 1, 'Checkbox', 'edit')}">
					<label>
						<input form="st_f" name="Checkbox" type="checkbox" data-prop-column="${args->f4_db:html:input_type(select_social):input_props('with_empty=1'):arg_name(Checkbox save to database):arg_section(14, 2, 'Checkbox', 'edit')}" value="1">
						${args->text_9:arg_name(Text):arg_section(14, 3, 'Checkbox', 'edit')}
					</label>
				</div>

                <button form="st_f" type="submit" class="$flat_btn" with_responsive="1" style="display:block; border:0; white-space:normal; box-sizing:border-box; ${args->button_style2:html:default('display: block;
padding-top: 8px;
padding-right: 32px;
padding-bottom: 8px;
padding-left: 32px;
font-family: Karla, HelveticaNeue, "Helvetica Neue", sans-serif;
font-weight: normal;
font-size: sel(18px, 14px);
width: 100%;
min-height: 48px;
background-color: #d92e1b;
color: white;
border-bottom: 0px solid #3f75bd;
border-radius: 4px;
text-transform: uppercase;'):input_type(css):arg_name(Style):arg_section(16, 1, 'Action button', 'check')}" hover_style="${args->button_h_style:html:default('background-color: rgba(217, 27, 27, 0.96);
border-color: #fff;
color: rgb(249, 247, 247);'):input_type(css):arg_name(Hover Style):arg_section(16, 2, 'Action button', 'check')}">
					${args->button_caption:default(EMAIL MY CART FOR LATER):arg_name(Caption):arg_section(16, 0, 'Action button', 'check')}
                </button>
			</div>
		</div>
		<div data-case="b">
			${args->success:default('<div style="text-align: center;"><br />
<br />
<strong><span style="color:black;">Thank you!</span></strong></div>
'):arg_name(Thank you text):arg_section(15, 0, 'After submit', 'check')}
		</div>
	</div>
</div>
```


## Form



```
<div class="$responsive" data-style="position:relative; text-align:center; ${args->style:html:default('color: rgb(122, 122, 122);
position: relative;
top: 0px;
background:#fff;
box-shadow: 0 0 black;
width: 620px;

min-height: 453px;
border-radius: 4px;
padding: 0px 48px 43px 48px;
box-sizing: border-box;
font-family: Karla, HelveticaNeue, "Helvetica Neue", sans-serif !important;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(0, 0, 'Box', 'th-large')}">
	${block->show_close_button:default(1):arg_name(Show close button):arg_section(4, 0, 'Close button', 'close')}
	<div style="position:absolute; top:-42px; right:-32px; z-index:2">
		${args->close_button:default('<img src="https://static.emarketer.com/upload/4035/6f0bc68fd3c8c332.png" class="$emarketer_button_dont_show_again" data-action_id="${action_id}" data-n_sessions="0">'):input_type(dontshowagain):arg_name(Close button):arg_section(4, 1, 'Close button', 'close')}
	</div>
	<div class="$switch-elem" data-case="a" data-style="box-sizing:border-box">
		<div data-case="a" class="$cform st_f" ontplsubmit="emarketer.push(['Submit', '${action_id:html}', this._get_value_ex(), arguments[1], arguments[2]]); return true" ontplaftersubmit="
			this.parentNode._set_case('b', null, false, {template: 'animator_fade'});
			var email=this.querySelector('input[data-prop-column=email]').value;
			var ids=[], list=[];
			this.querySelectorAll('*[data-emarketer-click-target] > img').forEach
			(	function(e)
				{	var id = e.parentNode.dataset.emarketerClickTarget.replace(/^\w+\s/, '');
					var img = e.src;
					ids.push(id);
					list.push({id: id, img: img});
				}
			);
			new Function(this.dataset.custom).call(this, email, ids, list);
		" data-custom="${args->custom:html:input_type(textarea):arg_name(Javascript after submit):arg_section(0, 1, 'Box', 'th-large')}">
			<div data-style="    background-image: url(https://image.ibb.co/igSMy0/save-your-cart-title.png);
position: relative;
top: -54px;
z-index: 1;
margin: auto;
padding: 0.6em;
height: 96px;
background-repeat: no-repeat;
background-position: center;
">
				<div data-style="display:none;border:solid black 1px; padding:0.6em; font-size:19px">
					Wait a minute!
				</div>
			</div>
			<div data-style="position:relative; z-index:0; top:0; background-color:white; font-size:18px;    margin-top: -45px;">
				${args->line_1:default('<p style="padding:0;font-size:25px;margin-top:5px;color:#000;font-weight:900;">SAVE YOUR CART BEFORE YOU LEAVE</p>
'):arg_name(Line 1 Text):arg_section(5, 0, 'Text', 'bars')}
				<table style="width:100%; border-collapse:separate; border-spacing:12px 0; margin-bottom:1.2em">
					<tr class="$table_slider" data-disabled="${args->with_slider:html:default(1):input_type(checkbox):input_props('value_off=1','value_on='):arg_name(Use slider widget):arg_section(2, 1, 'With slider', 'arrow-right')}" style="border:none" for_max_vw="${args->for_max_vw:html:input_type(css_length):input_props('with_options=always'):arg_name(Slider widget only if screen width is less than or equal to):arg_section(2, 2, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" eq_cell_width="1" eq_cell_height="1" arrows_line="${args->arrows_line:html:input_type(checkbox):input_props('value_off=-1','value_on=0'):arg_name(Arrows in the middle of images):arg_section(2, 6, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" arrow_back_img="${args->arrow_back_img:html:input_type(emarketer_media_url):arg_name(Left arrow image):arg_section(2, 3, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" arrow_forward_img="${args->arrow_forward_img:html:input_type(emarketer_media_url):arg_name(Right arrow image):arg_section(2, 4, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" pagination_id="tsp" arrow_back_id="button_back" arrow_forward_id="button_forward" arrows_offset="${args->arrows_offset:html:input_type(number):arg_name(Slider arrows offset):arg_section(2, 5, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" hide_buttons="${args->hide_buttons:html:input_type(checkbox):input_props('value_off=','value_on=1'):arg_name(Hide arrow buttons when nothing to scroll):arg_section(2, 0, 'With slider', 'arrow-right'):visible_if('block.title-0 && block.with_arrows-0')}">
						${foreach products_interactions as p where p->interaction_status IN ('extra') order by p->interaction_time desc limit 16}
							<td style="${args->td_style:html:default('padding:0; text-align:center'):input_type(css):input_props('with_responsive=1'):arg_name(Cell Style):arg_section(1, 1, 'Cells', 'th-large')}">
								<a data-emarketer-click-target="products ${p->internal_id:html}" href="${p->cart_url:html:arg_name(Link target URL):arg_section(10, 0, 'Link target URL', 'link'):column_tags('url','custom text')}" target="${args->target:html:default(_self):input_type(a_target):arg_name(Open link in):arg_section(10, 1, 'Link target URL', 'link')}" data-style="display:block; margin:auto; box-sizing:border-box; width:${args->img_width:html:default('sel(120px, 30vw)'):input_type(css_length):input_props('with_responsive=1'):arg_name(Cell width):arg_section(1, 0, 'Cells', 'th-large')}">
									<img src="${p->image_big_url:html:arg_name(Item image):arg_section(6, 0, 'Image', 'close'):column_tags(image)}" data-style="${args->img_style:html:default('border: double white 5px;
width: auto;
height: auto;
max-height: 120px;
max-width: 120px;'):input_type(css):input_props('with_responsive=1'):arg_name(Image style):arg_section(6, 1, 'Image', 'close')}">
								</a>
								<div data-style="margin:auto; box-sizing:border-box; width:${args->img_width:html:default('sel(120px, 30vw)'):input_type(css_length):input_props('with_responsive=1'):arg_name(Cell width):arg_section(1, 0, 'Cells', 'th-large')}">
									<div data-style="${args->a_css:html:default('font-size: 0px;
color: rgb(0,110,204);
text-decoration: none;
text-align: center;'):input_type(css):input_props('with_responsive=1'):arg_name(Title):arg_section(7, 3, 'Text', 'align-justify')}">
										<a style="text-decoration:inherit; color:inherit" href="${p->cart_url:html:arg_name(Link target URL):arg_section(10, 0, 'Link target URL', 'link'):column_tags('url','custom text')}">
											${p->title:arg_name(Item text):arg_section(7, 1, 'Text', 'align-justify')}
										</a>
									</div>
								</div>
								${block->rating:default(0):arg_name(With rating):arg_section(8, 0, 'Rating', 'star')}
								<div style="${args->rating_style:html:input_type(css):arg_name(Rating style)}">
									<input class="$rating" value="${p->rank:html:arg_name(Rating):arg_section(8, 1, 'Rating', 'star')}" max="${args->rank_max:html:input_type(number):arg_name(Maximum rating number that corresponds to 100%):arg_section(8, 2, 'Rating', 'star')}">
								</div>
								${block->price:default(0):arg_name(With price):arg_section(9, 0, 'Price', 'tag')}
								<div data-style="margin:auto; box-sizing:border-box; width:${args->img_width:html:default('sel(120px, 30vw)'):input_type(css_length):input_props('with_responsive=1'):arg_name(Cell width):arg_section(1, 0, 'Cells', 'th-large')}">
									${if p->price}
										${if p->sale_price and p->sale_price < p->price}
											<div style="${args->sale_style:html:input_type(css):input_props('with_responsive=1'):arg_name('Price after discount: style'):arg_section(9, 5, 'Price', 'tag')}">
												${args->before_price:arg_name(Text before price):arg_section(9, 2, 'Price', 'tag')}
												${p->sale_price:truncate(2):sprintf($%s):arg_name(Price after discount):arg_section(9, 3, 'Price', 'tag')}
												${args->after_price:arg_name(Text after price):arg_section(9, 1, 'Price', 'tag')}
											</div>
											<div style="${args->price_style:html:input_type(css):input_props('with_responsive=1'):arg_name('Price before discount: style'):arg_section(9, 6, 'Price', 'tag')}">
												${p->price:truncate(2):sprintf($%s):arg_name(Price before discount):arg_section(9, 4, 'Price', 'tag')}
											</div>
										${end}
										${if not p->sale_price or p->sale_price >= p->price}
											<div style="${args->price_style:html:input_type(css):input_props('with_responsive=1'):arg_name('Price before discount: style'):arg_section(9, 6, 'Price', 'tag')}">
												${args->before_price:arg_name(Text before price):arg_section(9, 2, 'Price', 'tag')}
												${p->price:truncate(2):sprintf($%s):arg_name(Price before discount):arg_section(9, 4, 'Price', 'tag')}
												${args->after_price:arg_name(Text after price):arg_section(9, 1, 'Price', 'tag')}
											</div>
										${end}
									${end}
								</div>
								${block->description:default(0):arg_name(With description):arg_section(7, 0, 'Text', 'align-justify')}
								<div data-style="margin:auto; box-sizing:border-box; width:${args->img_width:html:default('sel(120px, 30vw)'):input_type(css_length):input_props('with_responsive=1'):arg_name(Cell width):arg_section(1, 0, 'Cells', 'th-large')}">
									<div data-style="display:inline-block; ${args->a_css_3:html:input_type(css):input_props('with_responsive=1'):arg_name(Description):arg_section(7, 4, 'Text', 'align-justify')}; padding-bottom:0">
										${p->description:arg_name(Item text):arg_section(7, 2, 'Text', 'align-justify')}
									</div>
								</div>

								${block->button:default(0):arg_name(With button):arg_section(3, 0, 'Add Button', 'hand-pointer-o')}
								<div style="margin-top:0.4em">
									<a data-emarketer-click-target="products ${p->internal_id:html}" onclick="AddProductsToBasket(${p->internal_id:html}); _S_T.push(['Product Added to cart', '${p->internal_id:html}', 'action_id', ${action_id:html}]);" href="javascript:void(0);" data-style="display: inline-block; ${args->button_style:html:input_type(css):input_props('with_responsive=1'):arg_name(Button style):arg_section(3, 2, 'Add Button', 'hand-pointer-o')}">${args->button:arg_name('Text', 'Link target URL'):arg_section(3, 1, 'Add Button', 'hand-pointer-o')}</a>
								</div>
							</td>
						${end}
					</tr>
				</table>

				${block->with_f2:default(0):arg_name(With Name):arg_section(11, 0, 'Name Box', 'edit')}
				<div>
					<input form="st_f" name="Name" required="1" data-prop-column="${args->f2_db:html:input_type(select_social):input_props('with_empty=1'):arg_name(Name save to database):arg_section(11, 1, 'Name Box', 'edit')}" data-style="box-sizing:border-box; ${args->f1_style:html:default('margin-bottom: 20px;
padding: 10px;
font-family: Karla, HelveticaNeue, "Helvetica Neue", sans-serif;
font-weight: 400;
font-size: 16px;
width: 100%;
border: 1px solid rgb(62,62,62);
border-radius: 4px;
color: rgb(3, 1, 1);
text-align: left;
min-height: 48px;'):input_type(css):input_props('with_responsive=1'):arg_name(Input style):arg_section(11, 3, 'Name Box', 'edit')}" placeholder="${args->f2:html:arg_name(Name Placeholder Text):arg_section(11, 2, 'Name Box', 'edit')}">
				</div>
				<div>
					<input form="st_f" name="Email" pattern="^[^\s@]+@[^\s@\.]+\.[^\s@]+$" required="1" data-prop-column="${args->f3_db:html:default(email):input_type(select_social):input_props('with_empty=1'):arg_name(Email save to database):arg_section(12, 1, 'Email Box', 'envelope')}" data-style="box-sizing:border-box; ${args->f1_style:html:default('margin-bottom: 20px;
padding: 10px;
font-family: Karla, HelveticaNeue, "Helvetica Neue", sans-serif;
font-weight: 400;
font-size: 16px;
width: 100%;
border: 1px solid rgb(62,62,62);
border-radius: 4px;
color: rgb(3, 1, 1);
text-align: left;
min-height: 48px;'):input_type(css):input_props('with_responsive=1'):arg_name(Input style):arg_section(11, 3, 'Name Box', 'edit')}" placeholder="${args->f3:html:default(Email Address):arg_name(Email Placeholder Text):arg_section(12, 0, 'Email Box', 'envelope')}">
				</div>
				${block->with_f5:default(0):arg_name(With Details):arg_section(13, 0, 'Details Box', 'edit')}
				<div>
					<textarea form="st_f" name="Details" data-style="box-sizing:border-box; ${args->f5_style:html:input_type(css):input_props('with_responsive=1'):arg_name(Input style):arg_section(13, 2, 'Details Box', 'edit')}" placeholder="${args->f5:html:arg_name(Details Placeholder Text):arg_section(13, 1, 'Details Box', 'edit')}"></textarea>
				</div>
				${block->with_f4:default(0):arg_name(With Checkbox):arg_section(14, 0, 'Checkbox', 'edit')}
				<div data-style="${args->style9:html:input_type(css):input_props('with_responsive=1'):arg_name(Checkbox Style):arg_section(14, 1, 'Checkbox', 'edit')}">
					<label>
						<input form="st_f" name="Checkbox" type="checkbox" data-prop-column="${args->f4_db:html:input_type(select_social):input_props('with_empty=1'):arg_name(Checkbox save to database):arg_section(14, 2, 'Checkbox', 'edit')}" value="1">
						${args->text_9:arg_name(Text):arg_section(14, 3, 'Checkbox', 'edit')}
					</label>
				</div>

                <button form="st_f" type="submit" class="$flat_btn" with_responsive="1" style="display:block; border:0; white-space:normal; box-sizing:border-box; ${args->button_style2:html:default('display: block;
padding-top: 8px;
padding-right: 32px;
padding-bottom: 8px;
padding-left: 32px;
font-family: Karla, HelveticaNeue, "Helvetica Neue", sans-serif;
font-weight: normal;
font-size: 18px;
width: 100%;
min-height: 52px;
background-color: #000;
color: white;
border-bottom: 0px solid #3f75bd;
border-radius: 4px;
text-transform: uppercase;'):input_type(css):arg_name(Style):arg_section(16, 1, 'Action button', 'check')}" hover_style="${args->button_h_style:html:default('background-color: #000;
border-color: #fff;
color: rgb(249, 247, 247);'):input_type(css):arg_name(Hover Style):arg_section(16, 2, 'Action button', 'check')}">
					${args->button_caption:default(EMAIL MY CART FOR LATER):arg_name(Caption):arg_section(16, 0, 'Action button', 'check')}
                </button>
			</div>
		</div>
		<div data-case="b">
			${args->success:default('<div style="text-align: center;"><br />
<br />
<br />
<br />
<br />
<br />
<strong><span style="font-size: 24px;max-width: 600px;color:black;">Thank you!<br />
Your cart items have been sent to your email.</span></strong><br />
<br />
<br />
&nbsp;</div>
'):arg_name(Thank you text):arg_section(15, 0, 'After submit', 'check')}
		</div>
	</div>
</div>
```


## Form with dynamic products recommendations



```
<div class="$responsive" data-style="position:relative; text-align:center; ${args->style:html:default('color: #333;
position: relative;
top: 0px;
box-shadow: 0 0 black;
min-width: 500px;
background-color: #fff;
width: 540px;
border-radius: 4px;
padding-top: 40px;
padding-right: 48px;
padding-bottom: 40px;
padding-left: 48px;
font-family: Karla, HelveticaNeue, "Helvetica Neue", sans-serif;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(0, 0, 'Box', 'th-large')}">
	${block->show_close_button:default(1):arg_name(Show close button):arg_section(4, 0, 'Close button', 'close')}
	<div style="position:absolute; top:16px; right:16px; z-index:2">
		${args->close_button:default('<img style="width:19px;" src="https://static.emarketer.com/upload/4035/18e8b5d116db12cf.png" class="$emarketer_button_dont_show_again" data-action_id="${action_id}" data-n_sessions="0">'):input_type(dontshowagain):arg_name(Close button):arg_section(4, 1, 'Close button', 'close')}
	</div>
	<div class="$switch-elem" data-case="a" data-style="box-sizing:border-box">
		<div data-case="a" class="$cform st_f" ontplsubmit="emarketer.push(['Submit', '${action_id:html}', this._get_value_ex(), arguments[1], arguments[2]]); return true" ontplaftersubmit="this.parentNode._set_case('b', null, false, {template: 'animator_fade'}); var email=this.querySelector('input[data-prop-column=email]').value; var ids=[]; this.querySelectorAll('*[data-emarketer-click-target]').forEach(function(e) {ids.push(e.dataset.emarketerClickTarget.replace(/^\w+\s/, ''))}); new Function(this.dataset.custom).call(this, email, ids)" data-custom="${args->custom:html:input_type(textarea):arg_name(Javascript after submit):arg_section(0, 1, 'Box', 'th-large')}">
			<div data-style="position:relative; z-index:1; background-color:white; margin:auto; width:80%; padding:0.6em">
				<div data-style="border:solid black 1px; padding:0.6em; font-size:19px">
					Wait a minute!
				</div>
			</div>
			<div data-style="position:relative; z-index:0; top:0; background-color:white; font-size:18px">
				${args->line_1:default('<h2>Send your cart?</h2>
'):arg_name(Line 1 Text):arg_section(5, 0, 'Text', 'bars')}
				<table style="width:100%; border-collapse:separate; border-spacing:12px 0; margin-bottom:1.2em">
					<tr class="$table_slider" data-disabled="${args->with_slider:html:input_type(checkbox):input_props('value_off=1','value_on='):arg_name(Use slider widget):arg_section(2, 1, 'With slider', 'arrow-right')}" style="border:none" for_max_vw="${args->for_max_vw:html:input_type(css_length):input_props('with_options=always'):arg_name(Slider widget only if screen width is less than or equal to):arg_section(2, 2, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" eq_cell_width="1" eq_cell_height="1" arrows_line="${args->arrows_line:html:default(0):input_type(checkbox):input_props('value_off=-1','value_on=0'):arg_name(Arrows in the middle of images):arg_section(2, 6, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" arrow_back_img="${args->arrow_back_img:html:default('https://static.emarketer.com/upload/4035/3256192fabeef23a.png'):input_type(emarketer_media_url):arg_name(Left arrow image):arg_section(2, 3, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" arrow_forward_img="${args->arrow_forward_img:html:default('https://static.emarketer.com/upload/4035/3256192fabeef23a.png'):input_type(emarketer_media_url):arg_name(Right arrow image):arg_section(2, 4, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" pagination_id="tsp" arrow_back_id="button_back" arrow_forward_id="button_forward" arrows_offset="${args->arrows_offset:html:default(-22):input_type(number):arg_name(Slider arrows offset):arg_section(2, 5, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" hide_buttons="${args->hide_buttons:html:input_type(checkbox):input_props('value_off=','value_on=1'):arg_name(Hide arrow buttons when nothing to scroll):arg_section(2, 0, 'With slider', 'arrow-right'):visible_if('block.title-0 && block.with_arrows-0')}">
						${foreach products_interactions as p where p->interaction_status in ('extra') and p->custom_i_5='1' order by p->interaction_time desc limit 16}
							<td style="${args->td_style:html:default('padding:0; text-align:center'):input_type(css):input_props('with_responsive=1'):arg_name(Cell Style):arg_section(1, 1, 'Cells', 'th-large')}">
								<a data-emarketer-click-target="products ${p->internal_id:html}" href="${p->cart_url:html:arg_name(Link target URL):arg_section(10, 0, 'Link target URL', 'link'):column_tags('url','custom text')}" target="${args->target:html:default(_self):input_type(a_target):arg_name(Open link in):arg_section(10, 1, 'Link target URL', 'link')}" data-style="display:block; margin:auto; box-sizing:border-box; width:${args->img_width:html:default('sel(120px, 30vw)'):input_type(css_length):input_props('with_responsive=1'):arg_name(Cell width):arg_section(1, 0, 'Cells', 'th-large')}">
									<img src="${p->image_big_url:html:arg_name(Item image):arg_section(6, 0, 'Image', 'close'):column_tags(image)}" data-style="${args->img_style:html:default('border: double white 5px;
width: auto;
height: auto;
max-height: 120px;
max-width: 120px;'):input_type(css):input_props('with_responsive=1'):arg_name(Image style):arg_section(6, 1, 'Image', 'close')}">
								</a>
								<div data-style="margin:auto; box-sizing:border-box; width:${args->img_width:html}">
									<div data-style="${args->a_css:html:default('font-size: 14px;
color: rgb(58, 34, 34);
text-decoration: none;
text-align: center;'):input_type(css):input_props('with_responsive=1'):arg_name(Title):arg_section(7, 2, 'Text', 'align-justify')}">
										<a style="text-decoration:inherit; color:inherit" href="${p->cart_url:html}">

<!-- title was here -->
										</a>
									</div>
								</div>
								${block->rating:default(0):arg_name(With rating):arg_section(8, 0, 'Rating', 'star')}
								<div style="${args->rating_style:html:input_type(css):arg_name(Rating style)}">
									<input class="$rating" value="${p->rank:html:arg_name(Rating):arg_section(8, 1, 'Rating', 'star')}" max="${args->rank_max:html:input_type(number):arg_name(Maximum rating number that corresponds to 100%):arg_section(8, 2, 'Rating', 'star')}">
								</div>
								${block->price:default(0):arg_name(With price):arg_section(9, 0, 'Price', 'tag')}
								<div data-style="margin:auto; box-sizing:border-box; width:${args->img_width:html}">
									${if p->price}
										${if p->sale_price and p->sale_price < p->price}
											<div style="${args->sale_style:html:input_type(css):input_props('with_responsive=1'):arg_name('Price after discount: style'):arg_section(9, 5, 'Price', 'tag')}">
												${args->before_price:arg_name(Text before price):arg_section(9, 2, 'Price', 'tag')}
												${p->sale_price:truncate(2):sprintf($%s):arg_name(Price after discount):arg_section(9, 3, 'Price', 'tag')}
												${args->after_price:arg_name(Text after price):arg_section(9, 1, 'Price', 'tag')}
											</div>
											<div style="${args->price_style:html:input_type(css):input_props('with_responsive=1'):arg_name('Price before discount: style'):arg_section(9, 6, 'Price', 'tag')}">
												${p->price:truncate(2):sprintf($%s):arg_name(Price before discount):arg_section(9, 4, 'Price', 'tag')}
											</div>
										${end}
										${if not p->sale_price or p->sale_price >= p->price}
											<div style="${args->price_style:html}">
												${args->before_price}
												${p->price:truncate(2):sprintf($%s)}
												${args->after_price}
											</div>
										${end}
									${end}
								</div>
								${block->description:default(0):arg_name(With description):arg_section(7, 0, 'Text', 'align-justify')}
								<div data-style="margin:auto; box-sizing:border-box; width:${args->img_width:html}">
									<div data-style="display:inline-block; ${args->a_css_3:html:input_type(css):input_props('with_responsive=1'):arg_name(Description):arg_section(7, 3, 'Text', 'align-justify')}; padding-bottom:0">
										${p->description:arg_name(Item text):arg_section(7, 1, 'Text', 'align-justify')}
									</div>
								</div>

								${block->button:default(0):arg_name(With button):arg_section(3, 0, 'Add Button', 'hand-pointer-o')}
								<div style="margin-top:0.4em">
									<a data-emarketer-click-target="products ${p->internal_id:html}" onclick="AddProductsToBasket(${p->internal_id:html}); _S_T.push(['Product Added to cart', '${p->internal_id:html}', 'action_id', ${action_id:html}]);" href="javascript:void(0);" data-style="display: inline-block; ${args->button_style:html:input_type(css):input_props('with_responsive=1'):arg_name(Button style):arg_section(3, 2, 'Add Button', 'hand-pointer-o')}">${args->button:arg_name('Text', 'Link target URL'):arg_section(3, 1, 'Add Button', 'hand-pointer-o')}</a>
								</div>
							</td>
						${end}
					</tr>
				</table>

				${block->with_f2:default(1):arg_name(With Name):arg_section(11, 0, 'Name Box', 'edit')}
				<div>
					<input form="st_f" name="Name" required="1" data-prop-column="${args->f2_db:html:default(first_name):input_type(select_social):input_props('with_empty=1'):arg_name(Name save to database):arg_section(11, 1, 'Name Box', 'edit')}" data-style="box-sizing:border-box; ${args->f1_style:html:default('margin-bottom: 20px;
padding: 10px;
font-family: Karla, HelveticaNeue, "Helvetica Neue", sans-serif;
font-weight: 400;
font-size: 16px;
width: 100%;
border: 1px solid rgb(62,62,62);
border-radius: 4px;
color: rgb(3, 1, 1);
text-align: left;
min-height: 48px;'):input_type(css):input_props('with_responsive=1'):arg_name(Input style):arg_section(11, 3, 'Name Box', 'edit')}" placeholder="${args->f2:html:default(Your First Name):arg_name(Name Placeholder Text):arg_section(11, 2, 'Name Box', 'edit')}">
				</div>
				${block->with_f6:default(1):arg_name(With Telephone):arg_section(12, 0, 'Telephone Box', 'edit')}
				<div>
					<input form="st_f" name="Phone" type="tel" required="${args->f6_req:html:default(1):input_type(checkbox):arg_name(Telephone is required field):arg_section(12, 2, 'Telephone Box', 'edit')}" data-prop-column="${args->f6_db:html:input_type(select_social):input_props('with_empty=1'):arg_name(Telephone save to database):arg_section(12, 1, 'Telephone Box', 'edit')}" data-style="box-sizing:border-box; ${args->f1_style:html}" placeholder="${args->f6:html:default(Telephone):arg_name(Telephone Placeholder Text):arg_section(12, 3, 'Telephone Box', 'edit')}">
				</div>
				<div>
					<input form="st_f" name="Email" pattern="^[^\s@]+@[^\s@\.]+\.[^\s@]+$" required="1" data-prop-column="${args->f3_db:html:default(email):input_type(select_social):input_props('with_empty=1'):arg_name(Email save to database):arg_section(13, 1, 'Email Box', 'envelope')}" data-style="box-sizing:border-box; ${args->f1_style:html}" placeholder="${args->f3:html:default(Your Email Address):arg_name(Email Placeholder Text):arg_section(13, 0, 'Email Box', 'envelope')}">
				</div>
				${block->with_f5:default(0):arg_name(With Details):arg_section(14, 0, 'Details Box', 'edit')}
				<div>
					<textarea form="st_f" name="Details" data-style="box-sizing:border-box; ${args->f5_style:html:input_type(css):input_props('with_responsive=1'):arg_name(Input style):arg_section(14, 2, 'Details Box', 'edit')}" placeholder="${args->f5:html:arg_name(Details Placeholder Text):arg_section(14, 1, 'Details Box', 'edit')}"></textarea>
				</div>
				${block->with_f4:default(0):arg_name(With Checkbox):arg_section(15, 0, 'Checkbox', 'edit')}
				<div data-style="${args->style9:html:input_type(css):input_props('with_responsive=1'):arg_name(Checkbox Style):arg_section(15, 1, 'Checkbox', 'edit')}">
					<label>
						<input form="st_f" name="Checkbox" type="checkbox" data-prop-column="${args->f4_db:html:input_type(select_social):input_props('with_empty=1'):arg_name(Checkbox save to database):arg_section(15, 2, 'Checkbox', 'edit')}" value="1">
						${args->text_9:arg_name(Text):arg_section(15, 3, 'Checkbox', 'edit')}
					</label>
				</div>

                <button form="st_f" type="submit" class="$flat_btn" with_responsive="1" style="display:block; border:0; white-space:normal; box-sizing:border-box; ${args->button_style2:html:default('display: block;
padding-top: 8px;
padding-right: 32px;
padding-bottom: 8px;
padding-left: 32px;
font-family: Karla, HelveticaNeue, "Helvetica Neue", sans-serif;
font-weight: normal;
font-size: sel(18px, 14px);
width: 100%;
min-height: 48px;
background-color: #a30001;
color: white;
border-bottom: 0px solid #3f75bd;
border-radius: 4px;
text-transform: uppercase;'):input_type(css):arg_name(Style):arg_section(17, 1, 'Action button', 'check')}" hover_style="${args->button_h_style:html:default('background-color: #111111;
border-color: #fff;
color: #FFFFFF;'):input_type(css):arg_name(Hover Style):arg_section(17, 2, 'Action button', 'check')}">
					${args->button_caption:default(SEND):arg_name(Caption):arg_section(17, 0, 'Action button', 'check')}
                </button>
			</div>
		</div>
		<div data-case="b">
			${args->success:default('<div style="text-align: center;">&nbsp;
<p><span style="font-size:36px;">Awesome! We will keep you posted.</span></p>
</div>
'):arg_name(Thank you text):arg_section(16, 0, 'After submit', 'check')}
		</div>
	</div>

	${args->footer:default('<p>We are GDPR compliant and will not spam you. By clicking the above button, you agree to our <a href="https://www.abbotsfordchrysler.com/privacy-policy/" target="_blank">Privacy Policy</a>.</p>
'):arg_name(Footer):arg_section(18, 0, 'Footer', 'bars')}

</div>
```


## Form



```
<div class="$responsive" data-style="display:inline-block; position:relative; ${args->style:html:default('border: none;
text-align: center;
font-family: Roboto-Medium;
margin: 0px;
overflow: visible;
padding-top: 20px;
padding-right: 50px;
padding-bottom: 50px;
padding-left: 50px;
background-color: white;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(0, 1, 'Frame', 'th-large')}; width:${args->width:html:default(600px):input_type(css_length):input_props('with_options=none'):arg_name(Widget width):arg_section(0, 0, 'Frame', 'th-large')}" onupdate="
	var
		w=Math.min(ns.joyquery('ancestor::table:limit(1) parent::div parent::div', by_id.ts).get(0).offsetWidth, document.documentElement.clientWidth-1),
		b=12,
		a=ns.joyquery('parent::*>tr>td>*', by_id.ts).get(),
		d=a[0].parentNode,
		t=d.offsetWidth,
		n=Math.max(Math.round((w-b)/(t+b)), Math.min(1, by_id.ts.children.length)),
		T=Math.round((w-b)/n-b-parseFloat(d.style.borderLeftWidth)*2);
	for (i=0; i!=a.length; i++) if (a[i].style.display!='inline-block') a[i].style.width=T+'px'
">
	<div class="$switch-elem" data-case="a" data-style="box-sizing:border-box">
		<div data-case="a" class="$cform st_f" ontplsubmit="emarketer.push(['Submit', '${action_id:html}', this._get_value_ex(), arguments[1], arguments[2]]); return true" ontplaftersubmit="this.parentNode._set_case('b', null, false, {template: 'animator_fade'}); var email=this.querySelector('input[data-prop-column=email]').value; var ids=[]; this.querySelectorAll('*[data-emarketer-click-target]').forEach(function(e) {ids.push(e.dataset.emarketerClickTarget.replace(/^\w+\s/, ''))}); new Function(this.dataset.custom).call(this, email, ids)" data-custom="${args->custom:html:input_type(textarea):arg_name(Javascript after submit):arg_section(0, 2, 'Frame', 'th-large')}">

			${block->title:default(1):arg_name(With title bar):arg_section(2, 0, 'Title', 'bookmark')}
			<table data-style="width:100%; border-collapse:collapse; border:none; ${args->title_bg:html:default('margin-top: 5px;
margin-right: 0px;
margin-bottom: 5px;
margin-left: 20px;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(2, 2, 'Title', 'bookmark')}">
				<tr>
					<td data-style="vertical-align:middle; ${args->title_style:html:default('font-family: roboto-bold;
line-height: 1.1875;
letter-spacing: -1px;
margin-bottom: 25px;
font-size: 32px;
color: #000;
text-align: center;'):input_type(css):input_props('with_responsive=1'):arg_name(Title style):arg_section(2, 3, 'Title', 'bookmark')}">
						${args->title:default(Remember Me?):arg_name(Text):arg_section(2, 1, 'Title', 'bookmark')}
					</td>
					${block->with_arrows:default(0):arg_name(With arrow buttons):arg_section(1, 0, 'With slider', 'arrow-right')}
					<td style="width:1px; white-space:nowrap; vertical-align:middle">
						<a id="button_back" class="$flat_btn" style="${args->btn_style:html:input_type(css):arg_name(Arrow button style):arg_section(1, 1, 'With slider', 'arrow-right')}" hover_style="${args->btn_hover_style:html:input_type(css):arg_name('Arrow button style: hover'):arg_section(1, 2, 'With slider', 'arrow-right')}"><</a>
						<a id="button_forward" class="$flat_btn" style="${args->btn_style:html}" hover_style="${args->btn_hover_style:html}">></a>
					</td>
					${block->x:default(1):arg_name(With close button):arg_section(3, 0, 'Close button', 'close')}
					<td style="width:1px; white-space:nowrap; ${args->x_style:html:default():input_type(css):arg_name(Close button position):arg_section(3, 2, 'Close button', 'close')}">
						${args->x:default('<div onmouseenter="this.style.backgroundColor=this.style.outlineColor" onmouseleave="this.style.backgroundColor=this.style.textDecorationColor" style="display: inline-block; vertical-align: text-bottom; width: 24px; height: 24px; box-sizing: border-box; border-top-left-radius: 50%; border-top-right-radius: 50%; border-bottom-right-radius: 50%; border-bottom-left-radius: 50%; border: 2px solid; -webkit-box-shadow: rgba(255, 255, 255, 0.2) 0px 1px 0px inset, rgba(0, 0, 0, 0.2) 0px 1px 2px; padding: 3px; background-color: rgb(207, 120, 58); text-decoration-color: rgb(207, 120, 58); outline-color: rgb(206, 54, 64); outline-width: 10px; color: rgb(10, 4, 4); cursor: pointer; transition: all 0.3s ease;" class="$emarketer_button_dont_show_again" data-action_id="${action_id}"><div style="display: block; width: 100%; height: 100%; transition: all 0.3s ease 0s; border-top-left-radius: 50%; border-top-right-radius: 50%; border-bottom-right-radius: 50%; border-bottom-left-radius: 50%; background-image: linear-gradient(-45deg, transparent 0%, transparent 46%, currentcolor 46%, currentcolor 56%, transparent 56%, transparent 100%), linear-gradient(45deg, transparent 0%, transparent 46%, currentcolor 46%, currentcolor 56%, transparent 56%, transparent 100%);"></div></div>'):input_type(dontshowagain):input_props('style=cursor:pointer; vertical-align:middle'):arg_name(Close button):arg_section(3, 1, 'Close button', 'close')}
					</td>
				</tr>
			</table>

			<table data-style="${args->table_style:html:default('margin: 0;
background-color: rgba(256, 256, 256, 0);
padding: 5px;'):input_type(css):arg_name(Style):arg_section(0, 8, 'Frame', 'th-large')}; width:100%; border-collapse:separate; border-spacing:12px 8px; height:${args->img_max_height:html:default('sel(202px, 30vw)'):input_type(css_length):input_props('with_responsive=1'):arg_name(Image maximum height):arg_section(0, 6, 'Frame', 'th-large')}">
				<tr id="ts" class="$table_slider" data-disabled="${args->with_slider:html:input_type(checkbox):input_props('value_off=1','value_on='):arg_name(Use slider widget):arg_section(1, 4, 'With slider', 'arrow-right'):onchange('if (args.with_slider==1) block.with_arrows = block.pagination = 0')}" style="width:100%; height:100%; border:none" for_max_vw="${args->for_max_vw:html:default(always):input_type(css_length):input_props('with_options=always'):arg_name(Slider widget only if screen width is less than or equal to):arg_section(1, 5, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" eq_cell_width="${args->eq_cell_width:html:default(1):input_type(checkbox):input_props('value_off=','value_on=1'):arg_name(Equal cell width):arg_section(0, 3, 'Frame', 'th-large')}" eq_cell_height="1" arrows_line="${args->arrows_line:html:default(0):input_type(checkbox):input_props('value_off=-1','value_on=0'):arg_name(Arrows in the middle of images):arg_section(1, 9, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" arrow_back_img="${args->arrow_back_img:html:default('https://cdn.e-marketer.io/upload/4861/faa5e1a44bd31d61.png'):input_type(emarketer_media_url):arg_name(Left arrow image):arg_section(1, 6, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" arrow_style="${args->arrow_style:html:default('background-color: rgba(256, 256, 256, 0);
z-index: 99999;'):input_type(css):arg_name(Arrows style):arg_section(1, 7, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" pagination_id="tsp" arrow_back_id="button_back" arrow_forward_id="button_forward" arrows_offset="${args->arrows_offset:html:default(-25):input_type(number):arg_name(Slider arrows offset):arg_section(1, 8, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" hide_buttons="${args->hide_buttons:html:input_type(checkbox):input_props('value_off=','value_on=1'):arg_name(Hide arrow buttons when nothing to scroll):arg_section(1, 3, 'With slider', 'arrow-right'):visible_if('block.title-0 && block.with_arrows-0')}">
					${foreach products_interactions as p where p->interaction_status in ('viewed','extra','favorite') order by p->interaction_time desc limit 4}
						<td style="position:relative; height:100%; vertical-align:top; width:${args->img_width:html:default('sel(280px, 50vw)'):input_type(css_length):input_props('with_responsive=1'):arg_name(Cell width):arg_section(0, 4, 'Frame', 'th-large')}; padding:0; text-align:center; background-color:white; border:solid ${args->border_color:html:default('rgba(64, 42, 42, 0)'):input_type(color):arg_name(Border color):arg_section(0, 5, 'Frame', 'th-large')} 1px; transition: all .3s ease-in-out" onmouseenter="this.style.boxShadow='0 0 20px rgba(0,0,0,.2)'; var i=this.getElementsByTagName('a')[0].getElementsByTagName('img'); if (i[1]) {i[0].style.opacity=0; i[1].style.opacity=1}" onmouseleave="this.style.boxShadow=''; var i=this.getElementsByTagName('a')[0].getElementsByTagName('img'); if (i[1]) {i[0].style.opacity=1; i[1].style.opacity=0}">
							<div data-style="width:${args->img_width:html}; margin:auto; box-sizing:border-box">
								<a data-emarketer-click-target="products ${p->internal_id:html}" href="${p->cart_url:html:arg_name(Link target URL):arg_section(5, 0, 'Link target URL', 'link'):column_tags('url','custom text')}" target="${args->target:html:default(_self):input_type(a_target):arg_name(Open link in):arg_section(5, 1, 'Link target URL', 'link')}" data-style="display:flex; justify-content:center; align-items:center; margin:auto; box-sizing:border-box">
									<div style="position:relative; display:inline-block">
										<img src="${p->image_big_url:html}" data-style="width:auto; height:auto; max-width:100%; max-height:${args->img_max_height:html}; opacity:1; border-radius:4px; transition:opacity ease 0.4s">
										${if p->image_medium_url != ''}
											${block->with_2_img:default(1):arg_name(With 2 Pictures):arg_section(0, 7, 'Frame', 'th-large')}
											<div style="position:absolute; left:0; top:0; width:100%; height:100%; display:flex; justify-content:center; align-items:center">
												<img src="${p->image_medium_url:html}" style="width:auto; height:auto; max-width:100%; max-height:100%; opacity:0; border-radius:4px; transition:opacity ease 0.4s">
											</div>
										${end}
									</div>
								</a>
								${block->with_wishlist:default(0):arg_name(With wishlist):arg_section(10, 0, 'Wishlist', 'heart')}
								<a class="$flat_btn" onclick="
									var that = this;
									function gf(code)
									{	try
										{	if (code.trim()) return new Function(code).bind(that);
										}
										catch (e)
										{	_S_T.error(e);
											_S_T.act_params[${action_id:json:html}].fire_event('onerror', e);
										}
										return function() {};
									}
									this._load_begin();
									_S_T.add_to_wishlist({internal_id: ${p->internal_id:json:html}, custom_i_1: ${p->custom_i_1:json:html}, url: this.parentNode.getElementsByTagName('a')[0].href}, ${action_id:json:html}, this.dataset.arg).then(gf(this.dataset.yes), gf(this.dataset.no))
								" href="javascript:" data-arg="${args->wishlist_arg:html:arg_name(Argument to pass to your defined Add to Wishlist function):arg_section(10, 3, 'Wishlist', 'heart')}" data-yes="${args->wishlist_yes:html:input_type(source_javascript):arg_name(Javascript on complete):arg_section(10, 4, 'Wishlist', 'heart')}" data-no="${args->wishlist_no:html:input_type(source_javascript):arg_name(Javascript on error):arg_section(10, 5, 'Wishlist', 'heart')}" style="position:absolute; ${args->div_wishlist:html:input_type(css):input_props('with_responsive=1'):arg_name(Wishlist style):arg_section(10, 1, 'Wishlist', 'heart')}" hover_style="background-color: transparent">
									<img src="${args->wishlist_src:html:input_type(emarketer_media_url):arg_name(Add to wishlist image):arg_section(10, 2, 'Wishlist', 'heart')}">
								</a>
							</div>
							<div data-style="width:${args->img_width:html}; margin:auto; box-sizing:border-box">
								<div data-style="${args->a_css:html:default('font-size: 16px;
		font-weight: 700;
		text-align: start;
		margin-top: 0px;
		margin-right: 10px;
		margin-bottom: 0px;
		margin-left: 10px;
		text-overflow: ellipsis;
		text-transform: none;
		white-space: normal;
		overflow: hidden;
		color: #333;'):input_type(css):input_props('with_responsive=1'):arg_name(Text color):arg_section(4, 3, 'Text', 'align-justify')}">
									${p->description_short:arg_name(Item text):arg_section(4, 1, 'Text', 'align-justify')}
								</div>
							</div>
							<div data-style="width:${args->img_width:html}; box-sizing:border-box">
								${block->price:default(1):arg_name(With price):arg_section(6, 0, 'Price', 'dollar')}
								<div data-style="margin:auto; box-sizing:border-box; ${args->price_style:html:default('color: #606060;
		text-align: start;
		padding-top: 0px;
		padding-right: 10px;
		padding-bottom: 10px;
		padding-left: 10px;
		font-size: 16px;
		font-weight: 700;
		margin-top: -5px;
		margin-right: 01px;
		margin-bottom: 10px;
		margin-left: 01px;
		font-family: roboto-regular,Arial,Helvetica,sans-serif;'):input_type(css):input_props('with_responsive=1'):arg_name(Price style):arg_section(6, 1, 'Price', 'dollar')}">
									${if p->price}
										${args->before_price:arg_name(Text before price):arg_section(6, 2, 'Price', 'dollar')}
										${if p->sale_price and p->sale_price < p->price}
											<span style="${args->sale_style:html:default('text-decoration:line-through'):input_type(css):input_props('with_responsive=1'):arg_name('Price before discount: style'):arg_section(6, 5, 'Price', 'dollar')}">
												${p->price:truncate('0'):sprintf('£%s'):arg_name(Price):arg_section(6, 4, 'Price', 'dollar')}
											</span>
											${args->before_sale_price:default('Nu:'):arg_name(Text before sale price):arg_section(6, 3, 'Price', 'dollar')}
											${p->sale_price:truncate('0'):sprintf('£%s'):arg_name(Sale price):arg_section(6, 7, 'Price', 'dollar')}
										${end}
										${if not p->sale_price or p->sale_price >= p->price}
											${p->price:truncate('0'):sprintf('£%s')}
										${end}
										${args->after_price:arg_name(Text after price):arg_section(6, 6, 'Price', 'dollar')}
									${end}
									${block->with_info1:default(1):arg_name(With Product info 1):arg_section(7, 0, 'Product info near price', 'info')}
									<span data-style="${args->info1_style:html:default('font-weight: normal;'):input_type(css):input_props('with_responsive=1'):arg_name(Product info 1 style):arg_section(7, 2, 'Product info near price', 'info')}">
										${p->custom_3:sprintf('%s'):arg_name(Product info 1):arg_section(7, 1, 'Product info near price', 'info')}
									</span>
									${block->with_info2:default(1):arg_name(With Product info 2):arg_section(7, 3, 'Product info near price', 'info')}
									<span data-style="${args->info2_style:html:default('font-weight: normal;'):input_type(css):input_props('with_responsive=1'):arg_name(Product info 2 style):arg_section(7, 5, 'Product info near price', 'info')}">
										${p->custom_2:sprintf('| %s miles'):arg_name(Product info 2):arg_section(7, 4, 'Product info near price', 'info')}
									</span>
								</div>
								${block->description:default(0):arg_name(With description):arg_section(4, 0, 'Text', 'align-justify')}
								<div data-style="margin:auto; box-sizing:border-box">
									<div data-style="display:inline-block; ${args->a_css_3:html:input_type(css):input_props('with_responsive=1'):arg_name(Text color):arg_section(4, 4, 'Text', 'align-justify')}; padding-bottom:0">
										${p->description:arg_name(Item text):arg_section(4, 2, 'Text', 'align-justify')}
									</div>
								</div>
								${block->button:default(0):arg_name(With button):arg_section(8, 0, 'Second line', 'text-height')}
								<a data-emarketer-click-target="products ${p->internal_id:html}" href="${p->cart_url:html}" target="${args->target:html}" data-style="position:relative; top:1.3em; text-decoration:none; transition: font-size 0.3s ease; background-color:${args->border_color:html}; ${args->a_css_4:html:input_type(css):input_props('with_responsive=1'):arg_name(Button style):arg_section(8, 2, 'Second line', 'text-height')}" onmouseenter="var t=this; s=t.style, f=s.fontSize, p=f.match(/^([\d\.]+)(\w+)$/); if (!t._b) t._b=[s.backgroundColor, s.color, f]; s.backgroundColor=t._b[1]; s.color=t._b[0]; if (p) if (!t._p) {s.fontSize=(p[1]*0.9)+p[2]; t._p=1; setTimeout(function() {s.fontSize=t._b[2]; t._p=0;}, 300)}" onmouseleave="var s=this.style, b=this._b; s.backgroundColor=b[0]; s.color=b[1]">
									<div data-style="border:solid 1px; ${args->a_css_5:html:input_type(css):input_props('with_responsive=1'):arg_name(Button style):arg_section(8, 3, 'Second line', 'text-height')}">
										${args->button_text:arg_name(Button text):arg_section(8, 1, 'Second line', 'text-height')}
									</div>
								</a>
								${block->with_cart:default(0):arg_name(With add to cart):arg_section(9, 0, 'Add to cart button', 'cart-plus')}
								<a data-emarketer-click-target="products ${p->internal_id:html}" class="$flat_btn" onclick="
									var that = this;
									function gf(code)
									{	try
										{	if (code.trim()) return new Function(code).bind(that);
										}
										catch (e)
										{	_S_T.error(e);
											_S_T.act_params[${action_id:json:html}].fire_event('onerror', e);
										}
										return function() {};
									}
									this._load_begin();
									_S_T.add_to_cart({internal_id: ${p->internal_id:json:html}, custom_i_1: ${p->custom_i_1:json:html}, url: this.parentNode.parentNode.getElementsByTagName('a')[0].href}, ${action_id:json:html}, this.dataset.arg).then(gf(this.dataset.yes), gf(this.dataset.no))
								" href="javascript:" data-arg="${args->cart_arg:html:arg_name(Argument to pass to your defined Add to Cart function):arg_section(9, 4, 'Add to cart button', 'cart-plus')}" data-yes="${args->cart_yes:html:input_type(source_javascript):arg_name(Javascript on complete):arg_section(9, 5, 'Add to cart button', 'cart-plus')}" data-no="${args->cart_no:html:input_type(source_javascript):arg_name(Javascript on error):arg_section(9, 6, 'Add to cart button', 'cart-plus')}" data-style="box-sizing:border-box; ${args->button_style:html:input_type(css):input_props('with_responsive=1'):arg_name(Button style):arg_section(9, 2, 'Add to cart button', 'cart-plus')}" hover_style="${args->button_style_hover:html:input_type(css):arg_name(Button hover style):arg_section(9, 3, 'Add to cart button', 'cart-plus')}">
									${args->button:arg_name('Text', 'Button text'):arg_section(9, 1, 'Add to cart button', 'cart-plus')}
								</a>
							</div>
						</td>
					${end}
				</tr>
			</table>
			${block->pagination:default(0):arg_name(With slider pagination):arg_section(1, 10, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}
			<div id="tsp" class="$table_slider_pagination" slider_id="ts" selected_color="${args->pagination_color_on:html:input_type(color):arg_name(Bullet Selected Color):arg_section(1, 11, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" style="${args->pagination_color:html:input_type(css):arg_name(Bullet style):arg_section(1, 12, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}"></div>

			<div data-style="${args->a_css_25:html:default('padding-top: 0px;
padding-right: 12px;
padding-bottom: 0px;
padding-left: 12px;
text-align: center;'):input_type(css):input_props('with_responsive=1'):arg_name(Form box style):arg_section(12, 0, 'Form box', 'font')}">

				<div data-style="${args->form_title_style:html:default('font-size: 32px;
color: #000;
text-align: center;
margin-bottom: 30px;'):input_type(css):input_props('with_responsive=1'):arg_name(Form title style):arg_section(12, 2, 'Form box', 'font')}">
					${args->form_title:default(Want an email with details of your saved items?):arg_name(Form title):arg_section(12, 1, 'Form box', 'font')}
				</div>

				${block->with_f2:default(0):arg_name(With Name):arg_section(13, 0, 'Name Box', 'edit')}
				<div>
					<input form="st_f" name="Name" required="1" data-prop-column="${args->f2_db:html:input_type(select_social):input_props('with_empty=1'):arg_name(Name save to database):arg_section(13, 1, 'Name Box', 'edit')}" data-style="box-sizing:border-box; ${args->f1_style:html:default('margin-bottom: 20px;
padding: 10px;
font-family: Karla, HelveticaNeue, "Helvetica Neue", sans-serif;
font-weight: 400;
font-size: 16px;
width: 100%;
border: 1px solid rgb(62,62,62);
border-radius: 4px;
color: rgb(3, 1, 1);
text-align: left;
min-height: 48px;
max-width: 360px;'):input_type(css):input_props('with_responsive=1'):arg_name(Input style):arg_section(11, 0, 'Input style', 'square-o')}" placeholder="${args->f2:html:arg_name(Name Placeholder Text):arg_section(13, 2, 'Name Box', 'edit')}">
				</div>
				${block->with_f6:default(0):arg_name(With Telephone):arg_section(14, 0, 'Telephone Box', 'edit')}
				<div>
					<input form="st_f" name="Phone" type="tel" required="${args->f6_req:html:input_type(checkbox):arg_name(Telephone is required field):arg_section(14, 2, 'Telephone Box', 'edit')}" data-prop-column="${args->f6_db:html:input_type(select_social):input_props('with_empty=1'):arg_name(Telephone save to database):arg_section(14, 1, 'Telephone Box', 'edit')}" data-style="box-sizing:border-box; ${args->f1_style:html}" placeholder="${args->f6:html:arg_name(Telephone Placeholder Text):arg_section(14, 3, 'Telephone Box', 'edit')}">
				</div>
				<div>
					<input form="st_f" name="Email" pattern="^[^\s@]+@[^\s@\.]+\.[^\s@]+$" required="1" data-prop-column="${args->f3_db:html:default(email):input_type(select_social):input_props('with_empty=1'):arg_name(Email save to database):arg_section(15, 1, 'Email Box', 'envelope')}" data-style="box-sizing:border-box; ${args->f1_style:html}" placeholder="${args->f3:html:default(Your Email Address):arg_name(Email Placeholder Text):arg_section(15, 0, 'Email Box', 'envelope')}" value="${email:html}">
				</div>
				${block->with_f5:default(0):arg_name(With Details):arg_section(16, 0, 'Details Box', 'edit')}
				<div>
					<textarea form="st_f" name="Details" data-style="box-sizing:border-box; ${args->f5_style:html:input_type(css):input_props('with_responsive=1'):arg_name(Input style):arg_section(16, 2, 'Details Box', 'edit')}" placeholder="${args->f5:html:arg_name(Details Placeholder Text):arg_section(16, 1, 'Details Box', 'edit')}"></textarea>
				</div>
				${block->with_f4:default(0):arg_name(With Checkbox):arg_section(17, 0, 'Checkbox', 'edit')}
				<div data-style="${args->style9:html:input_type(css):input_props('with_responsive=1'):arg_name(Checkbox Style):arg_section(17, 1, 'Checkbox', 'edit')}">
					<label>
						<input form="st_f" name="Checkbox" type="checkbox" data-prop-column="${args->f4_db:html:input_type(select_social):input_props('with_empty=1'):arg_name(Checkbox save to database):arg_section(17, 2, 'Checkbox', 'edit')}" value="1">
						${args->text_9:arg_name(Text):arg_section(17, 3, 'Checkbox', 'edit')}
					</label>
				</div>

                <button form="st_f" type="submit" class="$flat_btn" with_responsive="1" data-style="border:0; white-space:normal; box-sizing:border-box; ${args->f1_style:html}; ${args->button_style2:html:default('padding: 8px;
font-size: sel(18px, 14px);
background-color: #017EDB;
color: white;
border-bottom: 0px solid #3f75bd;
text-align: center;'):input_type(css):arg_name(Style):arg_section(19, 1, 'Action button', 'check')}" hover_style="${args->button_h_style:html:default('background-color: #111111;
border-color: #fff;
color: #FFFFFF;'):input_type(css):arg_name(Hover Style):arg_section(19, 2, 'Action button', 'check')}">
					${args->button_caption:default(Send):arg_name(Caption):arg_section(19, 0, 'Action button', 'check')}
                </button>
			</div>
		</div>
		<div data-case="b">
			${args->success:default('<div style="text-align: center;">&nbsp;
<p><span style="font-size:36px;">Awesome! We will keep you posted.</span></p>
</div>
'):arg_name(Thank you text):arg_section(18, 0, 'After submit', 'check')}
		</div>
	</div>
</div>
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


