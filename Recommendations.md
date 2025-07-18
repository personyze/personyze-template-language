## Vertical widgets



```
<div class="$responsive $a_add_params" data-style="display:inline-block; position:relative; ${args->style:html:default('padding: 0px;
border: none;
margin: auto;
width: 250px;
display: block;
height: 500px;
')}; direction: ${args->direction:html:default(ltr)};" data-json-params="${args->url_params:html}">
    ${block->animate_cart_button:default(1)}
    <style>
        .st-add-to-cart-button {overflow:hidden}
        .st-add-to-cart-button > a {transition: all ease 0.3s; position:relative; top: 5em; opacity: 0}
        .st-holder-${action_id:html} > div:hover .st-add-to-cart-button > a {top: 0; opacity: 1}
    </style>

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
    <div class="st-holder-${action_id:html}" data-style="display:flex; flex-direction:column; align-items:stretch; ${args->holder_style:html:default('background-color: white;
color: #2E3234;
text-align: center;
')}">
		${foreach products as p order by p->time_created desc union sum_products where p->for_period='recently' order by p->n_viewed desc limit 5}
			<div data-style="${args->item_style:html}">
				<a data-personyze-click-target="products ${p->internal_id:html}" href="${p->cart_url:html}" target="${args->target:html:default(_self)}" data-style="position:relative; display:block; margin:auto; box-sizing:border-box; overflow: hidden; width:${args->img_width:html:default('sel(150px, 44vw)')}; padding: ${args->img_max_height:html:default('sel(109px, 120px)')} 0 0 0; text-decoration: none;">
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

					${block->with_wishlist_badge:default(1)}
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
				</a>
				<a data-personyze-click-target="products ${p->internal_id:html}" href="${p->cart_url:html}" target="${args->target:html}" data-style="display:block; margin:auto; box-sizing:border-box; width:${args->img_width:html}; text-decoration:none">
					<div data-style="${args->a_css:html:default('padding: 1px;
text-transform: none;
color: black;
font-weight: 400;
font-size: 14px;
margin: 10px;
text-align: center;
line-height: 1.0;
max-height: 5.2em;
overflow: hidden;
min-height: 2.5em;
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
					${if p->rank > 0}
						<hr class="$rating" data-value="${p->rank:html:default(0)}" style="${args->rating_style:html:default('color: #ffbd0c;
--bgcolor: white;
--border-color: #ffbd0c;
width: 100px;
height: 16px;
margin-top: 1em;
margin-right: 0px;
margin-bottom: 0px;
margin-left: 0px;
')}">
						${if p->n_reviews > 0}
							${args->n_reviews:default('${p->n_reviews} reviews')}
						${end}
					${end}
				</span>

				${block->stats_1day:default(1)}
				<div style="${args->text_style_1day:html:default('padding-top: 1em;
padding-right: 0;
padding-bottom: 1em;
padding-left: 0;
font-weight: 600;
')}">
					${foreach sum_products_1day as s where s->internal_id = p->internal_id limit 1}
						${args->n_viewed_1day:default('${s->n_viewed*1} viewed today ${if s-&gt;n_goal &gt; 0}
<div>${s->n_goal*1}&nbsp; purchased today</div>
${end}')}
						<span ontplready="this._v='${s->n_viewed:html}'|0; this._g='${s->n_goal:html}'|0"></span>
					${end}
					${block->hide_no_view_1day:default(1)}
					<span ontplready="var p=this.previousElementSibling||{}; if (ns==window._S_T) if ((p._v|0) < ('${args->hide_no_view_1day:html:default(3)}'|0) || (p._g|0) < ('${args->hide_no_goal_1day:html:default(1)}'|0)) this.parentNode.style.display='none'"></span>
				</div>

				${block->stats_week:default(0)}
				<div style="${args->text_style_week:html:default('padding:1em 0')}">
					${foreach sum_products_week as s where s->internal_id = p->internal_id limit 1}
						${args->n_viewed_week:default('<span style="font-size:14px;">Good choice! This product has been popular in the last week!</span><br />
&nbsp;
<div><span style="color:#fac200;"><strong>${s->n_viewed*1} viewed</strong></span></div>
${if s-&gt;n_goal &gt; 0}

<div><span style="color:#fac200;"><strong>${s->n_goal*1} purchased</strong></span></div>
${end}')}
						<span ontplready="this._v='${s->n_viewed:html}'|0; this._g='${s->n_goal:html}'|0"></span>
					${end}
					${block->hide_no_view_week}
					<span ontplready="var p=this.previousElementSibling||{}; if (ns==window._S_T) if ((p._v|0) < ('${args->hide_no_view_week:html}'|0) || (p._g|0) < ('${args->hide_no_goal_week:html}'|0)) this.parentNode.style.display='none'"></span>
				</div>

				<div style="clear:left;"></div>
				${block->price:default(1)}
				<div data-style="margin:auto; box-sizing:border-box; width:${args->img_width:html}; ${args->price_style:html}">
					${if p->price_after_discount}
						${if p->price_after_discount < p->price_before_discount}
							<span style="white-space:nowrap">
								<span style="${args->old_price_style:html:default('font-size: 14px;
font-weight: 700;
text-decoration: line-through;
')}">
									${args->old_price_before}${args->p_price_before_discount:default('$${p->price_before_discount:price('''')}')}${args->old_price_after}
								</span>
							</span>
							<span style="white-space:nowrap">
								<span style="${args->new_price_style:html:default('font-size: 14px;
font-weight: 700;
color: red;
')}">
									${args->old_price_before)}${args->p_price_after_discount:default('$${p->price_after_discount:price('''')}')}${args->old_price_after}
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
							<span style="white-space:nowrap; ${args->nosale_price_style:html:default('font-size: 14px;
font-weight: 700;
')}">
								${args->old_price_before}${args->p_price_before_discount}${args->old_price_after}
							</span>
						${end}
					${end}
				</div>

				${block->description:default(0)}
				<div data-style="margin:auto; box-sizing:border-box; width:${args->img_width:html}">
					<div data-style="display:inline-block; ${args->a_css_3:html}; padding-bottom:0">
						${p->description}
					</div>
				</div>

				${block->with_link_button:default(0)}
				<div>
					<a data-personyze-click-target="products ${p->internal_id:html}" class="$flat_btn" href="${args->link_button_href:html:default('${p->custom_1}')}" data-style="box-sizing:border-box; ${args->link_button_style:html:default('color: rgb(39, 36, 70);
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
						${args->link_button_text:default(View)}
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
						data-arg="${args->cart_arg:html}"
						data-yes="${args->cart_yes:html}"
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
			</div>
		${end}
		<span data-style="display:block; ${args->more_box_style:html:default('background-color: white;
margin-bottom: 2em;
')}">
			<a href="javascript:" class="$btn" onclick="this.parentNode.parentNode.removeChild(this.parentNode)" data-n="${args->hide_from:html:default(3)}" ontplready="if (this.parentNode.parentNode.children.length <= this.dataset.n-0) this.parentNode.parentNode.removeChild(this.parentNode)" data-style="text-decoration:none; ${args->more_style:html:default('background-color: rgb(243, 237, 237);
')}">
				${args->more_text:default(Show more)}
				<style>
					.st-holder-${action_id} > div:nth-child(n+${args->hide_from}) {display:none}
				</style>
			</a>
		</span>
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
	${menu args->landscape name='Orientation of each product image is landscape', type='checkbox', param='value_off=', param='value_on=1'}
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
${menu name='Product text/desc', icon='align-justify'}
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


## Buy together



```
<div class="$responsive" data-style="display:inline-block; ${args->style:html:default('color: rgb(45, 26, 26);
    border: solid 0px rgb(228, 206, 206);
    font-size: 15px;
    min-width: 0vw;
    padding-top: 0px;
    padding-right: 0px;
    padding-bottom: 10px;
    padding-left: 0px;
    margin-top: 10px;
    margin-right: auto;
    margin-bottom: 10px;
    margin-left: auto;
    line-height: 29px;
    width: sel(800px, 97%);
    text-align: left;
')}">

    <!-- Header Table (Widget Title) - Always borderless -->
    <table data-style="width:100%; border-collapse:collapse; border:0; ${args->title_bg:html:default('width: 400px;
text-align: center;
')}">
        <tr>
            <td data-style="vertical-align:middle; ${args->title_style:html:default('font-size: sel(23px, 16px);
font-weight: 500;
line-height: 1.3;
color: rgb(39, 22, 22);
margin-top: 0px;
margin-right: 0px;
margin-bottom: 10px;
margin-left: 0px;
padding-top: 12px;
padding-right: 10px;
padding-bottom: 22px;
padding-left: 1px;
background-color: rgba(249, 247, 247, 0);
text-align: left;
text-transform: uppercase;
')}">
                <!-- The inner flex container uses title_justify for aligning its content -->
                <div style="display: flex; align-items: center; justify-content: ${args->title_justify:html:default(flex-start)};">
                    ${if args->title_icon}
                        <img src="${args->title_icon:html}" alt="Title Icon" style="margin-right: 8px; max-height: 40px;"/>
                    ${end}
                    <span>${args->title:default(Bought together)}</span>
                </div>
            </td>
            ${block->x:default(0)}
            <td style="width:1px; white-space:nowrap; ${args->x_style:html}">
                ${args->x}
            </td>
        </tr>
    </table>

    <!-- Styles for plus icon and table header elements -->
    <style>
        .st_t .st_plus {
            display: none !important;
        }
        .st_t td.st_vis ~ td .st_plus {
            display: block !important;
        }
        tr > td > span.st_th {
            display: block !important;
        }
        tr + tr + tr > td > span.st_th {
            display: none !important;
        }
    </style>

    <!-- Revised .st_f style: No internal borders; outer border controlled by menu -->
    <style>
        .st_f {
            border: ${args->table_border_style:html:default(0)};
            border-collapse: separate;
            border-spacing: 0;
            border-radius: 6px;
        }
        .st_f > * > * > * {
            padding: 1em !important;
            border: none !important;
        }
    </style>

    <!-- Numeric formatting script remains unchanged -->
    <script ontplready="
        window._s_t_numfmt = function(v) {
            try {
                var locale = new Intl.Locale(${args->num_locale:json:html:default(en)});
            } catch (e) {
                locale = new Intl.Locale('en-US');
            }
            var fmt = ${args->num_frac:json:html:default(3)};
            return new Intl.NumberFormat(locale, {
                minimumFractionDigits: Number.isInteger(v) ? 0 : fmt,
                maximumFractionDigits: fmt
            }).format(v);
        };
    "></script>

    <!-- Main content container with flex layout; desktop: images left, total/buttons right -->
    <div id="layout_wrapper" style="display:flex; flex-wrap:wrap; ${args->flex_style:html:default('align-items: flex-start;
justify-content: flex-start;
')}">

        <!-- Product images container -->
        <div id="products_container" style="flex:1;">
            <table id="st_t" class="st_t" style="width:100%; border-collapse:collapse; border:0;">
                <tr class="$table_slider" data-disabled="${args->with_slider:html:default(1)}" style="border:none; max-width:${args->width:html:default(98vw)}">

                    ${foreach products_interactions as c where c->last_interaction_time >= tm order by c->last_interaction_time desc limit 1}
                        <td data-style="position:relative; ${args->td_style:html:default('text-align: left;
                            vertical-align: middle;
                            padding: sel(2px, 0);
                            border: none;
                        ')}">
                            <span>
                                <input class="st_internal_id" type="hidden" value="${c->internal_id:html}" data-json-add_to_cart_columns="${c->add_to_cart_columns:html}">
                                <a data-personyze-click-target="products ${c->internal_id:html}"
                                   href="${c->cart_url:html}"
                                   target="${args->target:html:default(_self)}"
                                   style="${args->c_link_style:html:default('color: rgb(41, 24, 24);
text-decoration: none;
max-width: 79px;
font-weight: bold;
')}">
                                    <img src="${c->image_big_url:html}"
                                         data-style="${args->main_img_style:html:default('border: double rgb(116, 176, 105) 0px;
width: sel(auto, auto);
height: sel(auto, auto);
max-width: sel(130px, 20vw);
max-height: 200px;
padding-top: sel(15px, );
padding-right: sel(15px, 0);
padding-bottom: sel(15px, 0);
padding-left: sel(15px, 0);
')}"
                                         onerror="this.parentNode.parentNode.style.display='none'"
                                         alt="${c->title:html:ellipsis(90):html}">
                                </a>
                            </span>
                            <a class="st_title" data-personyze-click-target="products ${c->internal_id:html}"
                               href="${c->cart_url:html}"
                               target="${args->target:html}"
                               style="${args->c_link_style:html}; display:${args->with_product_name:html:default(none)}">
                                ${c->title:ellipsis(90)}
                            </a>
                            <div class="st_price" data-price="${c->price_after_discount:html}"
                                 data-price-crazy="${c->price_before_discount:html}"
                                 style="display:${args->with_price:html:default(none)}; ${args->price_style:html:default('margin-top: 0.4em;
color: #d00;
')}">
                                ${if c->price_after_discount}
                                    ${if c->price_after_discount >= c->price_before_discount}
                                        <span style="white-space:nowrap; ${args->c_price_without_discount_style:html:default('color: #191919;')}">
                                            ${args->c_price_symbol_pre:default($)}
                                            <span ontplready="this.textContent = _s_t_numfmt(this.textContent)">
                                                ${c->price_before_discount}
                                            </span>
                                            ${args->c_price_symbol_post}
                                        </span>
                                    ${else}
                                        ${if c->price_after_discount = 0}
                                            ${args->c_free:default(FREE)}
                                        ${else}
                                            <span style="white-space:nowrap; ${args->c_price_after_discount_style:html:default('color: rgb(40, 121, 254);')}">
                                                ${args->c_discount_text:default('<span style="display:inline-block; font-size:50%; line-height:1; font-weight: 300;">Discounted<br />
price</span>')}
                                                ${args->c_price_symbol_pre}
                                                <span ontplready="this.textContent = _s_t_numfmt(this.textContent)">
                                                    ${c->price_after_discount}
                                                </span>
                                                ${args->c_price_symbol_post}
                                            </span>
                                            <span style="white-space:nowrap; ${args->c_price_before_discount_style:html:default('text-decoration: line-through;
color: rgb(75, 75, 75);
')}">
                                                ${args->c_price_symbol_pre}
                                                <span ontplready="this.textContent = _s_t_numfmt(this.textContent)">
                                                    ${c->price_before_discount}
                                                </span>
                                                ${args->c_price_symbol_post}
                                            </span>
                                        ${end}
                                    ${end}
                                ${end}
                            </div>
                            ${block->rating:default(0)}
                            <span style="display:block; ${args->rating_style:html}">
                                <input class="$rating" value="${c->rank:html}" max="${args->rank_max:html}">
                            </span>
                        </td>
                    ${end}

                    ${foreach products as main where (main->image_big_url IS NOT NULL AND main->image_big_url!='') order by main->time_created desc limit 2}
                        <td data-style="position:relative; ${args->td_style:html}">
                            <span>
                                <div class="st_plus" style="position:absolute; top:50%; left:-1.2em; width:1em; height:1em; line-height:1em; margin-top:-0.5em; text-align:center; ${args->plus_style:html:default('color: #ff6700; font-size: 26px;')}">
                                    +
                                </div>
                                <input class="st_internal_id" type="hidden" value="${main->internal_id:html}" data-json-add_to_cart_columns="${main->add_to_cart_columns:html}">
                                <a data-personyze-click-target="products ${main->internal_id:html}"
                                   href="${main->cart_url:html}"
                                   target="${args->target:html}"
                                   style="${args->link_style:html:default('color: rgb(41, 24, 24);
text-decoration: none;
max-width: 79px;
')}">
                                    <img src="${main->image_big_url:html}"
                                         data-style="${args->img_style:html:default('border: double rgb(235, 220, 220) 0px;
width: sel(auto, auto);
height: sel(auto, auto);
max-height: 100px;
max-width: sel(150px, 15vw);
padding-top: sel(10px, );
padding-right: sel(10px, 0);
padding-bottom: sel(10px, 0);
padding-left: sel(10px, 0);
')}"
                                         onerror="this.parentNode.parentNode.style.display='none'"
                                         alt="${main->title:html:ellipsis(90):html}">
                                </a>
                            </span>

                            <a class="st_title" data-personyze-click-target="products ${main->internal_id:html}"
                               href="${main->cart_url:html}"
                               target="${args->target:html}"
                               style="${args->link_style:html}; display:${args->with_product_name:html}">
                                ${main->title:ellipsis(90)}
                            </a>

                            <div class="st_price" data-price="${discount(main->prices, main->internal_id)}" data-price-crazy="${main->price_before_discount:html}" style="display:${args->with_price:html}; ${args->price_style:html}">
                                ${if main->price_after_discount}
                                    ${if discount(main->prices, main->internal_id) >= main->price_before_discount}
                                        <span style="white-space:nowrap; ${args->price_without_discount_style:html:default('color: #191919;')}">
                                            ${args->c_price_symbol_pre}
                                            <span ontplready="this.textContent = _s_t_numfmt(this.textContent)">
                                                ${main->price_before_discount}
                                            </span>
                                            ${args->c_price_symbol_post}
                                        </span>
                                    ${else}
                                        ${if discount(main->prices, main->internal_id) = 0}
                                            ${args->c_free}
                                        ${else}
                                            <span style="white-space:nowrap; ${args->price_after_discount_style:html:default('color: rgb(40, 121, 254);')}">
                                                ${args->c_discount_text}
                                                ${args->c_price_symbol_pre}
                                                <span ontplready="this.textContent = _s_t_numfmt(this.textContent)">
                                                    ${discount(main->prices, main->internal_id)}
                                                </span>
                                                ${args->c_price_symbol_post}
                                            </span>
                                            <span style="white-space:nowrap; ${args->price_before_discount_style:html:default('text-decoration: line-through;
color: rgb(75, 75, 75);
')}">
                                                ${args->c_price_symbol_pre}
                                                <span ontplready="this.textContent = _s_t_numfmt(this.textContent)">
                                                    ${main->price_before_discount}
                                                </span>
                                                ${args->c_price_symbol_post}
                                            </span>
                                        ${end}
                                    ${end}
                                ${end}
                            </div>
                            ${block->rating:default(0)}
                            <span style="display:block; ${args->rating_style:html}">
                                <input class="$rating" value="${main->rank:html}" max="${args->rank_max:html}">
                            </span>
                        </td>
                    ${end}
                </tr>
            </table>
        </div>

        <!-- Cart & Total Section -->
        <div id="price-and-cart-container" style="flex:0 0 auto; margin-left:1rem;">
            <div>
                <span style="${args->tot_text_style:html:default('font-weight: bold;
                    font-size: 12px;
                    margin-top: 23px;
                    margin-right: 10px;
                    margin-bottom: 10px;
                    margin-left: 0px;
                    color: rgb(12, 7, 7);
                ')}">
                    ${args->tot_text:default('Total:')}
                </span>
                <span id="st_tot" style="${args->tot_style:html:default('line-height: 2.0em;
                    font-size: 1.6em;
                    font-weight: 700;
                    color: rgb(40, 121, 254);
                ')}"></span>
                <span id="st_tot_crazy" style="${args->tot_crazy_style:html:default('line-height: 2.0em;
                    font-size: 1em;
                    text-decoration: line-through;
                    font-weight: 700;
                    color: rgb(75, 75, 75);
                ')}"></span>
            </div>
            <a href="javascript:" id="st_btn1" class="$flat_btn product-widget-product-cart-button" style="${args->add_btn_style:html:default('font-weight: normal;
border-radius: 6px;
color: white;
background-color: rgb(40, 121, 254);
text-align: center;
margin-top: 13px;
margin-right: auto;
margin-left: auto;
text-decoration: none;
padding-top: 8px;
padding-right: 20px;
padding-bottom: 8px;
padding-left: 20px;
width: auto;
max-width: 80vw;
')}" hover_style="${args->add_btn_hover_style:html:default('font-weight: normal;
color: white;
background-color: #fc9234;
text-align: center;
text-decoration: none;
')}" onclick="
                    var btn = this;
                    btn._load_begin();
                    personyze.add_to_cart(this._list, ${action_id:json:html}, ${args->js:json:html}).then(
                        function() {
                            btn._load_end();
                            new Function(btn.dataset.yes).call(btn);
                        },
                        function() {
                            btn._load_end();
                            new Function(btn.dataset.no).call(btn);
                        }
                    );
            " data-yes="${args->cart_yes:html:default('location.href=location.href')}" data-no="${args->cart_no:html:default('new _S_T.ElemsAnnotator(&quot;error&quot;).add(this, &quot;Couldn&apos;t add this product. Please, try from the product page.&quot;).annotate()')}">
                ${args->add_btn_text:default(Add checked to cart)}
            </a>
            ${block->with_fav:default(0)}
            <div>
                <button id="st_btn2" class="$flat_btn" style="${args->fvt_btn_style:html:default('width: 0px;
                    display: block;
                    margin-top: 0.5em;
                    padding: 0px;
                    outline: none;
                    border: none;
                    font-size: 13px;
                    font-weight: normal;
                    border-radius: 3px;
                    color: white;
                    background-color: rgba(7, 2, 2, 0.38);
                    text-align: center;
                ')}" hover_style="${args->fvt_btn_hover_style:html:default('color: white;
                    background-color: rgba(119, 119, 119, 0.76);
                ')}" data-added-msg="${args->added:html:default(Products added to wishlist)}">
                ${args->fvt_btn_text:default('<span style="font-size:0px;">Add to wishlist</span>')}
                </button>
            </div>
        </div>
    </div>

    <!-- Mobile override: on mobile, stack layout and adjust image sizes/spaces -->
    <style>
        @media (max-width: 600px) {
            #layout_wrapper {
                flex-direction: column !important;
            }
            #price-and-cart-container {
                margin-top: 1rem;
                width: 100% !important;
            }
            #st_t {
                display: block;
                white-space: nowrap;
                overflow-x: auto;
                width: 100%;
            }
            #st_t tr {
                display: inline-block;
            }
            .st_t td {
                display: inline-block !important;
                width: auto !important;
                vertical-align: top;
                margin-right: 2em;
            }
            .st_t td:last-child {
                margin-right: 0;
            }
            .st_t td img {
                max-width: 90px !important;
                height: auto !important;
            }
            .st_plus {
                left: -1.2em !important;
            }
        }
    </style>

    <!-- Footer Table with summary logic remains unchanged -->
    <table class="st_f" style="width:100%; border-collapse:separate; border-spacing:0; margin:5px;
           border:${args->table_border_style:html};"
           data-price-pre="${args->c_price_symbol_pre:html}"
           data-price-post="${args->c_price_symbol_post:html}"
           ontplready="
         var tr = by_id.st_tr,
             tbody = by_id.st_t.children[0],
             n = tbody.children[0].children.length,
             price_pre = this.dataset.pricePre,
             price_post = this.dataset.pricePost,
             add_to_cart_columns = [];
         if (tr) {
             for (var i = 0; i != n; i++) {
                 tr.set_length(n);
                 var t_by_id = tr[i].by_id;
                 function gt(i, name) {
                     return ns.joyquery('td:nth-child(' + (i+1) + ') [class~=\'st_' + name + '\']', tbody).get(0);
                 }
                 var ii = gt(i, 'internal_id');
                 try {
                     add_to_cart_columns[i] = JSON.parse(ii.getAttribute('data-json-add_to_cart_columns'));
                 } catch (e) {}
                 if (!add_to_cart_columns[i] || typeof(add_to_cart_columns[i]) != 'object')
                     add_to_cart_columns[i] = {};
                 add_to_cart_columns[i].internal_id = ii.value;
                 t_by_id.st_for_internal_id.value = ii.value;
                 var title = gt(i, 'title').cloneNode(true);
                 title.style.display = '';
                 if (i != 0)
                     t_by_id.st_for_title.innerHTML = '';
                 t_by_id.st_for_title.appendChild(title);
                 var price = gt(i, 'price');
                 t_by_id.st_for_price.innerHTML = price ? price.innerHTML : '';
                 t_by_id.st_for_price.style.cssText = price ? price.style.cssText : '';
                 t_by_id.st_for_price.style.display = '';
                 function ch() {
                     var tot = 0, tot_c = 0, v, list = [], vis = 0;
                     for (var i = 0; i != tr.length; i++) {
                         var price = gt(i, 'price');
                         var price_c = price ? parseFloat(price.dataset.priceCrazy) : NaN;
                         price = price ? parseFloat(price.dataset.price) : NaN;
                         if (isNaN(price)) return;
                         var t_by_id = tr[i].by_id;
                         v = t_by_id.st_for_internal_id.checked;
                         if (v) {
                             tot += parseFloat(price);
                             tot_c += parseFloat(price_c);
                             list.push(add_to_cart_columns[i]);
                             vis++;
                         }
                         for (var e, it = ns.joyquery('td:nth-child(' + (i+1) + ')', tbody); e = it();) {
                             e.className = v ? 'st_vis' : '';
                             ns.new_elem(e).add_style({ opacity: +v, display: v ? '' : 'none' }, {});
                         }
                     }
                     by_id.st_tot.innerHTML = price_pre + _s_t_numfmt(tot) + price_post;
                     by_id.st_tot_crazy.innerHTML = (tot == tot_c) ? '' : price_pre + _s_t_numfmt(tot_c) + price_post;
                     by_id.st_btn1._list = list;
                     by_id.st_btn1.style.display = vis ? 'block' : 'none';
                     if (by_id.st_btn2)
                         by_id.st_btn2.style.display = vis ? '' : 'none';
                 }
                 this.onclick = ch;
                 setTimeout(ch, 0);

                 if (by_id.st_btn2) {
                     by_id.st_btn2.onclick = function() {
                         var vis = 0;
                         for (var i = 0; i != tr.length; i++) {
                             var t_by_id = tr[i].by_id;
                             if (t_by_id.st_for_internal_id.checked) {
                                 ns.push(['Product Liked', t_by_id.st_for_internal_id.value]);
                                 vis++;
                             }
                         }
                         if (vis) {
                             new ns.ElemsAnnotator('info').add(this, this.getAttribute('data-added-msg')).annotate(3000);
                         }
                     };
                 }
             }
         }
   ">
        <tr id="st_tr" class="$repeat-elem">
            <td style="width:1px; vertical-align:top">
                <input id="st_for_internal_id" type="checkbox" checked="1">
            </td>
            <td style="padding:0 5px; vertical-align:top" id="st_for_title">
                ${args->this_pr:default('<b>This product:</b>')}
            </td>
            <td id="st_for_price" style="vertical-align:top" onclick="this.previousElementSibling.onclick()"></td>
        </tr>
    </table>
</div>

${menu name='Layout Settings', icon='th-large', description='Adjust the overall layout and responsive behavior.'}
	${menu args->style name='Main Style', description='CSS styles for the outer widget container.', type='css', param='with_responsive=1'}
	${menu args->td_style name='Cell Style', description='Customize the style of each product cell.', type='css', param='with_responsive=1'}
	${menu args->table_border_style name='Product Table Border', description='Set custom border for the final summary table (default is 0).', type='css'}
	${menu args->flex_style name='Flex Layout Style', description='Set alignment and wrapping for inner content layout.', type='css'}
${menu name='Header Settings', icon='bookmark', description='Configure title, optional icon, and close button for the widget.'}
	${menu args->title name='Title Text'}
	${menu args->title_icon name='Title Icon', description='Optional icon to display with the widget title.', type='personyze_media_url'}
	${menu args->title_bg name='Title Background Style', type='css', param='with_responsive=1'}
	${menu args->title_style name='Title Text Style', description='Edit text styling including color and font-size.', type='css', param='with_responsive=1'}
	${menu args->title_justify name='Title Justification', description='Set justify-content for the title flex container (flex-start, center, flex-end).', type='text'}
	${menu block->x name='Enable Close Button'}
	${menu args->x name='Close Button Code', type='dontshowagain', param='style=cursor:pointer; vertical-align:middle'}
	${menu args->x_style name='Close Button Position', type='css'}
${menu name='Product Image Settings', icon='image', description='Customize how product images appear.'}
	${menu c->image_big_url name='Product Image URL', column_tags='image'}
	${menu args->main_img_style name='Main Product Image Style', type='css', param='with_responsive=1'}
	${menu args->img_style name='Other Product Image Style', type='css', param='with_responsive=1'}
${menu name='Product Info Display', icon='text-height', description='Configure visibility and style of product name and price.'}
	${menu args->with_product_name name='Show Product Name', type='checkbox', param='value_off=none', param='value_on='}
	${menu args->c_link_style name='Link Style (First Product)', type='css'}
	${menu args->link_style name='Link Style (Other Products)', type='css'}
${menu name='Pricing Display', icon='dollar-sign', description='Set how prices and discounts are shown.'}
	${menu args->with_price name='Show Prices', type='checkbox', param='value_off=none', param='value_on=block'}
	${menu args->num_locale name='Number Format Locale'}
	${menu args->num_frac name='Decimal Places', type='number'}
	${menu args->price_style name='General Price Style', type='css', visible_if='args.with_price!="none"'}
	${menu args->c_price_symbol_pre name='Currency Symbol (Before Price)'}
	${menu args->c_price_symbol_post name='Currency Symbol (After Price)'}
	${menu args->c_free name='Text for Free Items'}
	${menu args->c_discount_text name='Discount Text Label'}
	${menu args->c_price_without_discount_style name='Regular Price Style (First Product)', type='css'}
	${menu args->c_price_before_discount_style name='Strikethrough Price Style (First Product)', type='css'}
	${menu args->c_price_after_discount_style name='Discounted Price Style (First Product)', type='css'}
	${menu args->price_without_discount_style name='Regular Price Style', type='css'}
	${menu args->price_before_discount_style name='Strikethrough Price Style', type='css'}
	${menu args->price_after_discount_style name='Discounted Price Style', type='css'}
	${menu args->this_pr name='Label for First Product'}
${menu name='Ratings', icon='star', description='Add rating stars to product items.'}
	${menu block->rating name='Show Rating Stars'}
	${menu c->rank name='Product Rating'}
	${menu args->rank_max name='Maximum Rating Value', type='number'}
	${menu args->rating_style name='Rating Stars Style', type='css'}
${menu name='Interactive UI', icon='plus', description='Control visual elements and call-to-actions.'}
	${menu args->plus_style name='Plus Sign Style Between Items', type='css'}
	${menu args->target name='Open Link In', type='a_target'}
	${menu c->cart_url name='Product Link URL', column_tags='url, custom text'}
${menu name='Cart & Button Settings', icon='cart-plus', description='Control cart button and total price display.'}
	${menu args->add_btn_text name='Add to Cart Button Text'}
	${menu args->add_btn_style name='Add to Cart Style', type='css'}
	${menu args->add_btn_hover_style name='Add to Cart Hover Style', type='css'}
	${menu args->tot_text name='Total Price Label'}
	${menu args->tot_text_style name='Total Price Label Style', type='css'}
	${menu args->tot_style name='Total Price Amount Style', type='css'}
	${menu args->tot_crazy_style name='Original Price Style', type='css'}
	${menu args->js name='Add to Cart JS Argument'}
	${menu args->cart_yes name='JS on Success', type='source_javascript'}
	${menu args->cart_no name='JS on Error', type='source_javascript'}
${menu name='Favorites (Wishlist)', icon='heart', description='Configure Add to Favorites (Wishlist) option.'}
	${menu block->with_fav name='Show Add to Favorites Button'}
	${menu args->fvt_btn_text name='Favorites Button Text'}
	${menu args->fvt_btn_style name='Favorites Button Style', type='css'}
	${menu args->fvt_btn_hover_style name='Favorites Button Hover Style', type='css'}
	${menu args->added name='Confirmation Message After Adding'}
```


## Widget with mouse hover button



```
<div class="$responsive $a_add_params" data-style="display:inline-block; position:relative; display:flex; flex-direction:column; justify-content:stretch; ${args->style:html:default('padding: 0px;
border: none;
margin: auto;
width: 100%;
height: auto;
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
        ${block->animate_cart_button:default(1)}
        <style>
            .st-add-to-cart-button {overflow:hidden}
            .st-add-to-cart-button > a {transition: all ease 0.3s; position:relative; top: 5em; opacity: 0}
            .st-td-hover .st-add-to-cart-button > a {top: 0; opacity: 1}
        </style>

        <style>
            .st-zoom {text-decoration:none}
            .st-zoom:hover {text-decoration:none}

            .st-zoom > div {transition:transform ease 0.3s; transform: scale(1)}
			.st-zoom:hover > div {transform: scale(calc(${args->img_zoom_on_hover:default(105)} / 100))}

            .st-hov:hover {color: ${args->a_hover_color:html:default('#F69442')} !important}
        </style>

        ${block->with_hover_image:default(0)}
        <style>
            .st-zoom > div {transition-property:opacity; transform: scale(1) !important; opacity:1}

            .st-zoom > div + .st-z2 {position:absolute; width:100%; height:100%; left:0; top:0; transition-property:opacity; opacity:0; transform:scale(1); background-size:cover; background-repeat:no-repeat}
            .st-zoom:hover > div + .st-z2 {opacity:1}
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
max-width: 98%;
')}">
            <table class="st-tab-rnd" data-style="height:10px; width:auto; border-collapse: separate; border-spacing: ${args->space_between_items:html:default(14px)} 0; margin:0 -${args->space_between_items:html}">
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
                    ${foreach products as p order by p->time_created desc union sum_products where p->for_period='recently' order by p->n_viewed desc limit 12}
                        <td style="position:relative; height:100%; padding:0; text-align:center; background-color:white; vertical-align:top; border:solid ${args->border_color:html:default('#dddddd')} 1px">
                            <a class="st-zoom" data-personyze-click-target="products ${p->internal_id:html}" href="${p->cart_url:html}" target="${args->target:html:default(_self)}">
                                <div data-style="display:flex; height:100%; margin:auto; box-sizing:border-box; overflow: hidden; width:${args->img_width:html:default('sel(380px, 45vw)')}; text-decoration:none; background-image:url('${p->image_big_url:html}'); background-repeat:no-repeat; background-size:cover">
                                    <img src="${p->image_big_url:html}" data-style="visibility:hidden; width:auto; height:auto; max-width:100%; max-height:${args->img_max_height:html:default('sel(409px, 120px)')}; border:none">
                                </div>

                                ${if p->image_medium_url <> ''}
                                    ${block->with_hover_image:default(0)}
                                    <div class="st-z2" style="background-image:url('${p->image_medium_url:html}')"></div>
                                ${end}

                                ${block->with_popular_badge_week:default(0)}
                                <span>
                                    ${foreach sum_products_week as s where s->internal_id = p->internal_id limit 1}
                                        ${if 100 - s->percentile_viewed <= args->badge_if_more_popular_week:default(5)}
                                            <div data-style="position: absolute; ${args->popular_badge_week_style:html:default('top: 0;
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
                                                <span data-style="${args->popular_badge_week_text_style:html:default('font-size: 16px;
font-weight: 600;
')}">${args->popular_badge_week_text:default(Popular)}</span>
                                            </div>
                                        ${end}
                                    ${end}
                                </span>

                                ${block->with_popular_badge_1day:default(0)}
                                <span>
                                    ${foreach sum_products_1day as s where s->internal_id = p->internal_id limit 1}
                                        ${if 100 - s->percentile_viewed <= args->badge_if_more_popular_1day:default(5)}
                                            <div data-style="position: absolute; ${args->popular_badge_1day_style:html:default('top: 0;
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
                                                <span data-style="${args->popular_badge_1day_text_style:html:default('font-size: 16px;
font-weight: 600;
')}">${args->popular_badge_1day_text:default(Popular)}</span>
                                            </div>
                                        ${end}
                                    ${end}
                                </span>

                                ${block->with_bestseller_badge_week:default(0)}
                                <span>
                                    ${foreach sum_products_week as s where s->internal_id = p->internal_id limit 1}
                                        ${if 100 - s->percentile_goal <= args->badge_if_more_sold_week:default(5)}
                                            <div data-style="position: absolute; ${args->bestseller_badge_week_style:html:default('top: 0;
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
                                                <span data-style="${args->bestseller_badge_week_text_style:html:default('font-size: 16px;
font-weight: 600;
')}">${args->bestseller_badge_week_text:default(Best seller)}</span>
                                            </div>
                                        ${end}
                                    ${end}
                                </span>

                                ${block->with_bestseller_badge_1day:default(0)}
                                <span>
                                    ${foreach sum_products_1day as s where s->internal_id = p->internal_id limit 1}
                                        ${if 100 - s->percentile_goal <= args->badge_if_more_sold_1day:default(5)}
                                            <div data-style="position: absolute; ${args->bestseller_badge_1day_style:html:default('top: 0;
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
                                                <span data-style="${args->bestseller_badge_1day_text_style:html:default('font-size: 16px;
font-weight: 600;
')}">${args->bestseller_badge_1day_text:default(Best seller)}</span>
                                            </div>
                                        ${end}
                                    ${end}
                                </span>

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
                                        <hr class="$icon ${args->db_badge_text_icon:html}">
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

                            ${block->with_title:default(1)}
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

                            ${block->price:default(1)}
                            <div data-style="margin:auto; box-sizing:border-box; width:${args->img_width:html}; ${args->price_style:html}">
                                ${if p->price_after_discount}
                                    ${if p->price_after_discount < p->price_before_discount}
                                        <span style="white-space:nowrap">
                                            <span style="${args->old_price_style:html:default('font-size: 22px;
font-weight: 700;
text-decoration: line-through;
')}">
                                                ${args->old_price_before}${args->p_price_before_discount:default('$${p->price_before_discount:price('''')}')}${args->old_price_after}
                                            </span>
                                        </span>
                                        <span style="white-space:nowrap">
                                            <span style="${args->new_price_style:html:default('font-size: 22px;
font-weight: 700;
color: red;
')}">
                                                ${args->old_price_before)}${args->p_price_after_discount:default('$${p->price_after_discount:price('''')}')}${args->old_price_after}
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

                            ${block->description:default(1)}
                            <div data-style="margin:auto; box-sizing:border-box; width:${args->img_width:html}">
                                <div data-style="display:inline-block; ${args->a_css_3:html}; padding-bottom:0">
                                    ${p->description}
                                </div>
                            </div>

                            ${block->with_link_button:default(1)}
                            <div data-style="box-sizing:border-box; ${args->link_button_box_style:html:default('text-align: center;
')}">
                                <a data-personyze-click-target="products ${p->internal_id:html}" class="$flat_btn" href="${args->link_button_href:html:default('${p->cart_url}')}" data-style="box-sizing:border-box; ${args->link_button_style:html:default('color: rgb(39, 36, 70);
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
    </div>
</div>

${menu name='Main Layout Settings', icon='th-large', description='General layout configuration for the widget.'}
	${menu args->style name='Base Style', description='Customize the base CSS for overall appearance.', type='css', param='with_responsive=1'}
	${menu args->content_padding name='Content Box Padding', description='Set the padding around the content area.', type='css', param='with_responsive=1'}
	${menu args->round name='Non-Rounded Cells', description='Disable rounded cell edges.', type='checkbox', param='value_off=', param='value_on=1'}
	${menu args->eq_cell_width name='Equal Cell Width', description='Force product cells to have the same width.', type='checkbox', param='value_off=', param='value_on=1'}
	${menu args->eq_cell_height name='Equal Cell Height', description='Force product cells to have the same height.', type='checkbox', param='value_off=', param='value_on=1'}
	${menu args->space_between_items name='Space Between Items', description='Set gap between product items.', type='css_length', param='with_responsive=1'}
	${menu args->border_color name='Border Color', description='Choose a color for cell borders.', type='color'}
	${menu args->round_border name='Round Border', description='Set the radius for rounded borders.', type='css_length'}
	${menu args->direction name='Localization Settings', description='Select text direction for localization.', type='select', param='options=[["Left to right","ltr"],["Right to left","rtl"]]'}
	${menu args->url_params name='Additional URL Parameters', description='Append extra URL parameters if needed.', type='external_media_url_params'}
${menu name='Logo Settings', icon='bars', description='Configure the logo display options.'}
	${menu block->with_logo name='Display Logo', description='Toggle whether the logo is shown.'}
	${menu args->logo_src name='Logo Image URL', description='Provide the URL for the logo image.', type='media_url'}
	${menu args->logo_block_style name='Logo Container Style', description='Customize the logo container style.', type='css'}
	${menu args->logo_text name='Logo Text', description='Text to appear beneath the logo.'}
	${menu args->logo_text_style name='Logo Text Style', description='Style the text below the logo.', type='css'}
${menu name='Slider Options', icon='arrow-right', description='Configure the slider for product display.'}
	${menu block->with_arrows name='Enable Arrow Navigation', description='Show previous/next arrows for slider navigation.'}
	${menu args->btn_style name='Arrow Button Style', description='CSS for slider arrow buttons.', type='css'}
	${menu args->btn_hover_style name='Arrow Button Hover Style', description='CSS for arrow buttons on hover.', type='css'}
	${menu args->hide_buttons name='Auto Hide Arrows', description='Hide arrows when scrolling is not necessary.', type='checkbox', param='value_off=', param='value_on=1', visible_if='block.title-0 && block.with_arrows-0'}
	${menu args->buttons_always name='Always Show Arrows', description='Display arrows even when not hovered.', type='checkbox', param='value_off=', param='value_on=1', visible_if='!(block.with_arrows-0)'}
	${menu args->with_slider name='Activate Slider', description='Use a slider instead of static layout.', type='checkbox', param='value_off=1', param='value_on=', onchange='if (args.with_slider==1) block.with_arrows = block.pagination = 0'}
	${menu args->with_scrollbar name='Show Scrollbar', description='Display a scrollbar if not using the slider.', type='checkbox', param='value_off=', param='value_on=1', visible_if='args.with_slider!=1'}
	${menu args->hide_scrollbar name='Hide Scrollbar', description='Hide the scrollbar visually while maintaining functionality.', type='checkbox', param='value_off=', param='value_on=1', visible_if='args.with_slider!=1 && args.with_scrollbar==1'}
	${menu args->scrollbar_style name='Scrollbar Style', description='Customize the scrollbar appearance.', type='css', visible_if='args.with_slider!=1 && args.with_scrollbar==1'}
	${menu args->for_max_vw name='Slider Max Width', description='Enable slider only on screens below this width.', type='css_length', param='with_options=always', visible_if='args.with_slider!=1'}
	${menu args->arrow_back_img name='Left Arrow Image', description='Custom image for the left arrow.', type='arrow', visible_if='args.with_slider!=1'}
	${menu args->arrow_style name='Arrows Style', description='Style the slider arrows.', type='css', visible_if='args.with_slider!=1'}
	${menu args->arrows_offset name='Arrows Offset', description='Adjust horizontal offset of arrows.', type='number', visible_if='args.with_slider!=1'}
	${menu args->arrows_line name='Arrows Alignment', description='Center arrows vertically over product images.', type='checkbox', param='value_off=-1', param='value_on=0', visible_if='args.with_slider!=1'}
	${menu block->pagination name='Slider Pagination', description='Toggle pagination dots for the slider.', visible_if='args.with_slider!=1'}
	${menu args->pagination_color_on name='Active Bullet Color', description='Color for the selected pagination bullet.', type='color', visible_if='args.with_slider!=1'}
	${menu args->pagination_color name='Bullet Style', description='Customize pagination bullet styling.', type='css', visible_if='args.with_slider!=1'}
${menu name='Widget Title', icon='bookmark', description='Configure the title bar for the widget.'}
	${menu block->title name='Display Title Bar', description='Toggle the title bar display.'}
	${menu args->title name='Title Text', description='Text to display as the widget title.'}
	${menu args->title_bg name='Title Background', description='CSS styling for the title bar background.', type='css', param='with_responsive=1'}
	${menu args->title_style name='Title Text Style', description='Customize the title text appearance.', type='css', param='with_responsive=1'}
${menu name='Close Button', icon='close', description='Configure the widget close button.'}
	${menu block->x name='Show Close Button', description='Toggle the close button display.'}
	${menu args->x name='Close Button Element', description='Style and configure the close button.', type='dontshowagain', param='style=cursor:pointer; vertical-align:middle'}
	${menu args->x_style name='Close Button Position', description='Position and style the close button.', type='css'}
${menu name='Image & Cell Settings', icon='image', description='Adjust product image and cell dimensions.'}
	${menu args->img_width name='Cell Width', description='Set the width of each product cell.', type='css_length', param='with_responsive=1'}
	${menu args->img_max_height name='Image Max Height', description='Define the maximum height for product images.', type='css_length', param='with_responsive=1'}
	${menu p->image_big_url name='Main Product Image', description='URL for the primary product image.', column_tags='image'}
${menu name='Image Effects', icon='bars', description='Configure zoom and alternative image effects.'}
	${menu args->img_zoom_on_hover name='Zoom %', description='Percentage zoom on hover.', type='number'}
${menu name='Hover Alternative Image', icon='image', description='Show an alternate image on hover if available.'}
	${menu block->with_hover_image name='Enable Hover Image', description='Toggle display of an alternate hover image.', onchange='block.with_zoom_image=block.with_hover_image^1||""'}
	${menu p->image_medium_url name='Hover Image URL', description='URL for the alternative hover image.', column_tags='image'}
${menu name='Most Popular Badge (week)', icon='align-justify', description='Display a badge for products that are amongst N% of the most popular on the site.'}
	${menu block->with_popular_badge_week name='Show Most Popular Badge (week)', description='Toggle the most popular badge display.'}
	${menu args->badge_if_more_popular_week name='Most Popular Badge Threshold', description='Badge appears if product is more popular than this percent of most popular products.', type='number'}
	${menu args->popular_badge_week_style name='Badge Style', description='CSS styling for the most popular badge.', type='css', param='with_responsive=1'}
	${menu args->popular_badge_week_text_style name='Badge Text Style', description='CSS styling for the most popular badge text.', type='css', param='with_responsive=1'}
	${menu args->popular_badge_week_text name='Badge Text', description='Text to display for the most popular badge.'}
${menu name='Most Popular Badge (1 day)', icon='align-justify', description='Display a badge for products that are amongst N% of the most popular on the site.'}
	${menu block->with_popular_badge_1day name='Show Most Popular Badge (1 day)', description='Toggle the most popular badge display.'}
	${menu args->badge_if_more_popular_1day name='Most Popular Badge Threshold', description='Badge appears if product is more popular than this percent of most popular products.', type='number'}
	${menu args->popular_badge_1day_style name='Badge Style', description='CSS styling for the most popular badge.', type='css', param='with_responsive=1'}
	${menu args->popular_badge_1day_text_style name='Badge Text Style', description='CSS styling for the most popular badge text.', type='css', param='with_responsive=1'}
	${menu args->popular_badge_1day_text name='Badge Text', description='Text to display for the most popular badge.'}
${menu name='Best Seller Badge (week)', icon='align-justify', description='Display a badge for products that are amongst N% of the best sellers on the site.'}
	${menu block->with_bestseller_badge_week name='Show Best Seller Badge (week)', description='Toggle the best seller badge display.'}
	${menu args->badge_if_more_sold_week name='Best Seller Badge Threshold', description='Badge appears if product is more sold than this percent of best seller products.', type='number'}
	${menu args->bestseller_badge_week_style name='Badge Style', description='CSS styling for the best seller badge.', type='css', param='with_responsive=1'}
	${menu args->bestseller_badge_week_text_style name='Badge Text Style', description='CSS styling for the best seller badge text.', type='css', param='with_responsive=1'}
	${menu args->bestseller_badge_week_text name='Badge Text', description='Text to display for the best seller badge.'}
${menu name='Best Seller Badge (1 day)', icon='align-justify', description='Display a badge for products that are amongst N% of the best sellers on the site.'}
	${menu block->with_bestseller_badge_1day name='Show Best Seller Badge (1 day)', description='Toggle the best seller badge display.'}
	${menu args->badge_if_more_sold_1day name='Best Seller Badge Threshold', description='Badge appears if product is more sold than this percent of best seller products.', type='number'}
	${menu args->bestseller_badge_1day_style name='Badge Style', description='CSS styling for the best seller badge.', type='css', param='with_responsive=1'}
	${menu args->bestseller_badge_1day_text_style name='Badge Text Style', description='CSS styling for the best seller badge text.', type='css', param='with_responsive=1'}
	${menu args->bestseller_badge_1day_text name='Badge Text', description='Text to display for the best seller badge.'}
${menu name='Discount Badge', icon='align-justify', description='Show a badge for discounted products.'}
	${menu block->with_discount_badge name='Enable Discount Badge', description='Toggle discount badge display.'}
	${menu args->min_discount_percent name='Min Discount %', description='Badge appears if discount is at least this %.', type='number', param='min=1'}
	${menu args->discount_badge_style name='Badge Style', description='CSS style for the discount badge.', type='css', param='with_responsive=1'}
	${menu args->discount_badge_text_style name='Badge Text Style', description='Style for the discount badge text.', type='css', param='with_responsive=1'}
	${menu args->discount_badge_text name='Badge Text', description='Custom text for the discount badge.'}
${menu name='New Badge', icon='align-justify', description='Highlight products that are new.'}
	${menu block->with_new_badge name='Enable New Badge', description='Toggle the new badge display.'}
	${menu args->badge_if_newer name='New Badge Threshold', description='Product is considered new if added within this period.', type='date', param='is_span=true', param='format=%0..999d days'}
	${menu args->new_badge_style name='Badge Style', description='Style for the new badge.', type='css', param='with_responsive=1'}
	${menu args->new_badge_text_style name='Badge Text Style', description='Text style for the new badge.', type='css', param='with_responsive=1'}
	${menu args->new_badge_text name='Badge Text', description='Label text for the new badge.'}
${menu name='Time-based Badge', icon='align-justify', description='Show a badge with a countdown for time-sensitive offers.'}
	${menu block->with_time_badge name='Enable Time-based Badge', description='Toggle the time-based badge display.'}
	${menu args->time_badge_style name='Badge Style', description='CSS style for the time-based badge.', type='css', param='with_responsive=1'}
	${menu args->time_badge_text_style name='Badge Text Style', description='Text style for the badge.', type='css', param='with_responsive=1'}
	${menu args->time_badge_text name='Badge Text', description='Label text for the time-based badge.'}
	${menu p->custom_i_1 name='Offer End Date Field', description='Catalog field (UNIX-timestamp) for offer end date.'}
	${menu block->with_time_badge_countdown name='Enable Countdown Timer', description='Toggle countdown timer for the badge.'}
	${menu args->time_badge_days name='Days Label', description='Caption for days in countdown.'}
	${menu args->time_badge_hr name='Hours Label', description='Caption for hours in countdown.'}
	${menu args->time_badge_min name='Minutes Label', description='Caption for minutes in countdown.'}
	${menu args->time_badge_sec name='Seconds Label', description='Caption for seconds in countdown.'}
${menu name='Stock Badge', icon='align-justify', description='Show a badge when stock is low.'}
	${menu block->with_stock_badge name='Enable Stock Badge', description='Toggle stock badge display.'}
	${menu args->badge_if_less_stock name='Stock Threshold', description='Badge appears if stock is below this number.', type='number', param='min=1'}
	${menu args->stock_badge_style name='Badge Style', description='CSS style for the stock badge.', type='css', param='with_responsive=1'}
	${menu args->stock_badge_text_style name='Badge Text Style', description='Text style for the stock badge.', type='css', param='with_responsive=1'}
	${menu args->stock_badge_text name='Badge Text', description='Custom text for the stock badge.'}
${menu name='Add to Wishlist', icon='bars', description='Enable wishlist functionality for products.'}
	${menu block->with_wishlist_badge name='Display Wishlist Icon', description='Toggle wishlist icon display.'}
	${menu args->wishlist_style name='Wishlist Icon Style', description='Style for the wishlist icon.', type='css'}
	${menu args->wishlist_off_style name='Wishlist Off Tooltip Style', description='Style for the tooltip when inactive.', type='css'}
	${menu args->wishlist_add_text name='Add Wishlist Tooltip', description='Text for adding item to wishlist.'}
	${menu args->wishlist_on_style name='Wishlist On Icon Style', description='Style for the active wishlist icon.', type='css'}
	${menu args->wishlist_rm_text name='Remove Wishlist Tooltip', description='Text for removing item from wishlist.'}
${menu name='DB Badge', icon='star', description='Display custom data as a badge from the product feed.'}
	${menu block->with_db_badge name='Enable DB Badge', description='Toggle DB badge display.'}
	${menu args->db_badge_style name='Badge Container Style', description='CSS styling for the badge container.', type='css'}
	${menu block->with_db_badge_icon name='Include Badge Icon', description='Toggle the badge icon display.'}
	${menu args->db_badge_text_icon name='Badge Icon', description='Select the icon for the badge.', type='icon'}
	${menu args->db_badge_text_style name='Badge Text Style', description='Style for the badge text.', type='css'}
	${menu args->db_badge_text name='Badge Text', description='Text to display in the badge.'}
${menu name='Custom Column', icon='database', description='Display an additional field as a custom column.'}
	${menu block->with_custom_column name='Enable Custom Column', description='Toggle the custom column display.'}
	${menu args->custom_column name='Custom Field', description='Name of the field to display.'}
	${menu args->custom_column_style name='Custom Column Style', description='Style for the custom column.', type='css'}
${menu name='Product Title', icon='align-justify', description='Show product titles.'}
	${menu block->with_title name='Display Title', description='Toggle product title visibility.'}
	${menu p->title name='Title Text', description='Product title from your feed.'}
	${menu args->title_max_lines name='Max Title Lines', description='Limit the number of title lines.', type='number', param='min=1'}
${menu name='Product Description', icon='align-justify', description='Show product description text.'}
	${menu block->description name='Display Description', description='Toggle product description display.'}
	${menu p->description name='Description Text', description='Product description from your feed.'}
	${menu args->a_css name='Description CSS', description='CSS styling for product description.', type='css', param='with_responsive=1'}
	${menu args->a_hover_color name='Description Hover Color', description='Text color on hover for the description.', type='color'}
	${menu args->a_css_3 name='Description Text Color', description='Set the primary color for the description.', type='css', param='with_responsive=1'}
${menu name='Link Button', icon='mouse-pointer', description='Set up a button that links to product details.'}
	${menu block->with_link_button name='Display Link Button', description='Toggle the link button display.'}
	${menu args->link_button_href name='Link Button URL', description='Destination URL for the link button.'}
	${menu args->link_button_text name='Button Text', description='Text displayed on the link button.'}
	${menu args->link_button_box_style name='Button Box Style', description='CSS styling for the button container.', type='css', param='with_responsive=1'}
	${menu args->link_button_style name='Button Style', description='Button CSS styling.', type='css', param='with_responsive=1'}
	${menu args->link_button_style_hover name='Button Hover Style', description='Button style when hovered.', type='css'}
${menu name='Quick Add to Cart', icon='cart-plus', description='Enable a button for quick add-to-cart functionality.'}
	${menu block->with_cart name='Display Quick Add', description='Toggle quick add-to-cart button.'}
	${menu args->button name='Cart Button Text', description='Text on the add-to-cart button.'}
	${menu args->button_icon name='Cart Button Icon', description='Icon on the add-to-cart button.', type='icon'}
	${menu args->button_icon_style name='Cart Button Icon Style', description='Style for the icon on the button.', type='css'}
	${menu args->button_style name='Cart Button Style', description='CSS styling for the cart button.', type='css', param='with_responsive=1'}
	${menu args->button_style_hover name='Cart Button Hover Style', description='Style for the cart button when hovered.', type='css'}
	${menu block->animate_cart_button name='Animate Cart Button', description='Enable hover animation for the cart button.'}
	${menu args->cart_is_code name='Trigger Integration Code', description='Execute add-to-cart integration code on click.', type='checkbox', param='value_off=', param='value_on=1'}
	${menu args->cart_arg name='Integration Code Argument', description='Optional argument for the add-to-cart code.', visible_if='args.cart_is_code'}
	${menu args->cart_yes name='On Success JS', description='JavaScript to run on successful add-to-cart.', type='source_javascript', visible_if='args.cart_is_code'}
	${menu args->cart_no name='On Error JS', description='JavaScript to run if add-to-cart fails.', type='source_javascript', visible_if='args.cart_is_code'}
${menu name='Onclick Target URL', icon='link', description='Specify the target URL for product click actions.'}
	${menu p->cart_url name='Product Click URL', description='URL opened on product click.', column_tags='url, custom text'}
	${menu args->target name='Link Target', description='Determine how the link opens (e.g., new tab).', type='a_target'}
${menu name='Ratings & Reviews', icon='star', description='Configure product rating display.'}
	${menu block->rating name='Display Ratings', description='Toggle product rating display.'}
	${menu p->rank name='Rating Value', description='Rating from the product feed.'}
	${menu args->rating_style name='Rating Colors', description='Customize rating background and border colors.', type='css', param='vars=--bgcolor:color; --border-color:color'}
${menu name='Statistics: 1-Day', icon='bar-chart', description='Display statistics from the last 24 hours.'}
	${menu block->stats_1day name='Enable 1-Day Stats', description='Toggle statistics for the last day.'}
	${menu args->hide_no_view_1day name='Min Views for Display', description='Hide stats if views are below this number.', type='number', param='min=0'}
	${menu args->hide_no_goal_1day name='Min Purchases for Display', description='Hide stats if purchases are below this number.', type='number', param='min=0'}
	${menu args->text_style_1day name='1-Day Stats Style', description='Style for 1-day statistics text.', type='css'}
	${menu args->n_viewed_1day name='Views Template', description='Text template for view count.'}
	${menu args->n_goal_1day name='Purchases Template', description='Text template for purchase count.'}
${menu name='Statistics: Week', icon='bar-chart', description='Display statistics for the past week.'}
	${menu block->stats_week name='Enable Weekly Stats', description='Toggle weekly statistics display.'}
	${menu args->hide_no_view_week name='Min Weekly Views', description='Hide weekly stats if views are too low.', type='number', param='min=0'}
	${menu args->hide_no_goal_week name='Min Weekly Purchases', description='Hide weekly stats if purchases are too low.', type='number', param='min=0'}
	${menu args->text_style_week name='Weekly Stats Style', description='Style for weekly statistics text.', type='css'}
	${menu args->n_viewed_week name='Weekly Views Template', description='Template for weekly view count.'}
	${menu args->n_goal_week name='Weekly Purchases Template', description='Template for weekly purchase count.'}
${menu name='Pricing', icon='dollar', description='Configure product price display options.'}
	${menu block->price name='Display Price', description='Toggle product price display.'}
	${menu args->price_style name='Price Style', description='Customize the CSS styling for prices.', type='css', param='with_responsive=1'}
	${menu args->old_price_style name='Old Price Style', description='Style for the original (pre-discount) price.', type='css'}
	${menu args->old_price_before name='Old Price Prefix', description='Text before the old price value.'}
	${menu args->p_price_before_discount name='Old Price Value', description='Product’s original price.'}
	${menu args->old_price_after name='Old Price Suffix', description='Text after the old price.'}
	${menu args->p_price_after_discount name='Discount Price Value', description='Product’s discounted price.'}
	${menu args->new_price_style name='Discount Price Style', description='Style for the discounted price.', type='css'}
	${menu args->sale_text_style name='Sale Text Style', description='Style for sale announcement text.', type='css'}
	${menu args->sale_text name='Sale Announcement', description='Text to indicate that the product is on sale.'}
	${menu args->nosale_price_style name='Regular Price Style', description='Style for products without a discount.', type='css'}
```


## Widget



```
<div class="$responsive $a_add_params" data-style="display:block; position:relative; max-width:${args->width:html:default(100vw)}; margin:auto; box-sizing: border-box; ${args->style:html:default('padding-top: 10px;
padding-right: 40px;
padding-bottom: 50px;
padding-left: 40px;
border: none;
text-align: left;
font-weight: bold;
font-size: sel(20px, 14px);
background-color: rgb(256, 256, 256);
border-top: 1px none #e8e8e1;
')}" data-json-params="${args->url_params:html}">
		${block->animate_cart_button:default(0)}
		<style>
			.st-add-to-cart-button {overflow:hidden; display:block}
			.st-add-to-cart-button > a {transition: all ease 0.3s; position:relative; top: 5em; opacity: 0}
			.st-td-hover .st-add-to-cart-button > a {top: 0; opacity: 1}
		</style>

		${block->title:default(1)}
		<div data-style="display:flex; align-items:center; ${args->title_bg:html}">
			<div data-style="flex-grow:1000; ${args->title_style:html:default('text-align: center;
font-size: sel(25px, 18px);
font-weight: 500;
color: #383838;
padding-top: 10px;
padding-right: sel(15px, 1px);
padding-bottom: sel(20px, 5px);
padding-left: 0px;
text-transform: none;
')}">
				${args->title:default(Recommended for you)}
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
		<table style="height:10px; width:auto; border-collapse:separate; border-spacing:${args->space_between_items:html:default(33px)} 0; margin:0 -${args->space_between_items:html}">
			<tbody style="height:100%">
			<tr id="ts" class="$table_slider" data-disabled="${args->with_slider:html}" data-hover_add_class="st-td-hover" data-round="${args->round:html:default(1)}" data-with_scrollbar="${args->with_scrollbar:html}" data-scrollbar_style="${args->scrollbar_style:html:default('background-color: #D8D8D8;
color: #999999;
height: 12px;
')}" data-hide_scrollbar="${args->hide_scrollbar:html}" style="box-sizing: border-box; border:none; height:100%; max-width:${args->width:html}" for_max_vw="${args->for_max_vw:html:default(always)}" eq_cell_width="${args->eq_cell_width:html:default(1)}" eq_cell_height="${args->eq_cell_height:html:default(1)}" arrows_line="${args->arrows_line:html:default(-1)}" arrow_back_img="${args->arrow_back_img:html:default('<svg viewBox="0 0 54 54" width="24" height="24" style="fill: rgb(86, 123, 80);"><path d="M0,0v54h54V0H0z M52,52H2V2h50V52z"></path><path d="M23.707,36.293L15.414,28H40c0.552,0,1-0.447,1-1s-0.448-1-1-1H15.414l8.293-8.293l-1.414-1.414L11.586,27l10.707,10.707 L23.707,36.293z"></path></svg>')}" arrow_style="${args->arrow_style:html:default('max-height: 28px;
')}" pagination_id="tsp" arrow_back_id="button_back" arrow_forward_id="button_forward" arrows_offset="${args->arrows_offset:html:default(-15)}" hide_buttons="${args->hide_buttons:html:default(1)}" buttons_always="${args->buttons_always:html:default(1)}">
				${foreach products as p order by p->time_created desc union sum_last_viewed_categories_products where p->for_period='all' order by p->n_viewed desc limit 11}
					<td style="position:relative; height:100%; padding:0; vertical-align:top; ${args->td_style:html:default('border:solid transparent 1px')}">
						<div style="display:flex; justify-content:stretch; align-items:stretch; height:100%">
							<a data-personyze-click-target="products ${p->internal_id:html}" href="${p->cart_url:html}" target="${args->target:html:default(_self)}" data-style="position:relative; display:block; margin:auto; box-sizing:border-box; overflow: hidden; width:${args->img_width:html:default('sel(149px, 44vw)')}; padding: ${args->img_max_height:html:default('sel(239px, 120px)')} 0 0 0; text-decoration: none;">
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

								${block->with_discount_badge:default(1)}
								<span>
									${if p->discount_percent >= args->min_discount_percent:default(1)}
										<div data-style="position: absolute; ${args->discount_badge_style:html:default('top: 0;
right: 48px;
width: 7em;
height: 7em;
font-size: 7px;
text-shadow: rgba(255,255,255,0.5) 0px 3px 3px;
background-color: #db3932;
border: double rgb(221, 228, 165) 6px;
color: rgb(225, 227, 191);
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
									${if unix_timestamp() - p->time_created <= args->badge_if_newer}
										<div data-style="position: absolute; ${args->new_badge_style:html:default('top: 0;
left: 48px;
font-size: 14px;
text-shadow: rgba(255,255,255,0.5) 0px 3px 3px;
background-color: #db3932;
color: rgb(225, 227, 191);
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

								${block->with_stock_badge:default(1)}
								<span>
									${if p->inventory between 1 and args->badge_if_less_stock}
										<div data-style="position: absolute; ${args->stock_badge_style:html:default('bottom: 0;
left: 48px;
font-size: 14px;
text-shadow: rgba(255,255,255,0.5) 0px 3px 3px;
background-color: #db3932;
color: rgb(225, 227, 191);
display: flex;
justify-content: center;
align-items: center;
padding: 0.3em;
')}">
											<span data-style="${args->stock_badge_text_style:html:default('font-size: 16px;
font-weight: 600;
')}">${args->stock_badge_text:default('${p->inventory} items remaining')}</span>
										</div>
									${end}
								</span>

								${block->with_wishlist_badge:default(0)}
								<span class="$switch-elem"
									data-case="${foreach products_interactions as w where w->internal_id = p->internal_id and w->interaction_status = 'favorite' limit 1}on${end}"
									data-p="${p->internal_id:html}"
									data-style="position:absolute; transition: all 0.3s ease; ${args->wishlist_style:html:default('top: 0;
right: 5px;
color: #E5007F;
font-size: 30px;
')}"
									onclick="var on=this._get_case(); _S_T.push([on ? 'Product Unliked' : 'Product Liked', this.dataset.p]); this._set_case(on ? '' : 'on'); event.stopPropagation(); event.preventDefault()"
								>
									<div data-case="" class="$hint" style="${args->wishlist_off_style:html}">
										<span data-content="1">${args->wishlist_add_text:default(Add to wishlist)}</span>
										<hr class="$icon heart-o">
									</div>
									<div data-case="on" class="$hint" style="${args->wishlist_on_style:html}">
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

							<div style="flex-grow:1000; display:flex; flex-direction:column; justify-content:stretch; align-items:stretch; ${args->cell_style:html:default('margin-left: 1em;
min-width: 10em;
')}">
								<div style="flex-grow:1000; ${args->p_title_style:html:default('text-align: left;
font-weight: 700;
font-size: 15px;
padding-top: 0;
padding-right: 0;
padding-bottom: 2em;
padding-left: 0;
')}; overflow:hidden; text-overflow:ellipsis; display:-webkit-box; -webkit-box-orient:vertical; -webkit-line-clamp:${args->title_max_lines:html:default(3)}; line-clamp:${args->title_max_lines:html}">
									${args->p_title:default('${p->title}')}
								</div>

								${block->rating:default(1)}
								<span>
									<hr class="$rating" data-value="${p->rank:html:default(0)}" style="${args->rating_style:html:default('color: yellow;
--bgcolor: white;
--border-color: blue;
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

								<div style="white-space:nowrap">
									${if p->price_after_discount}
										${args->before_price}
										${if p->price_after_discount < p->price_before_discount}
											${block->with_discount:default(1)}
											<div data-style="${args->discount_style:html:default('color: #dc263d;
font-size: 12px;
')}">
												${args->discount_text:default('Desconto:')}
												${sprintf(round((p->price_before_discount - p->price_after_discount) / p->price_before_discount * 100), '%s%%')}
											</div>

											<span data-style="${args->sale_style:html:default('text-decoration: line-through;
color: gray;
font-size: 12px;
font-weight: 600;
line-height: 20px;
padding-right: 0.2em;
')}">
												${args->p_price_before_discount:default('${p->price_before_discount:price('''')} &euro;')}
											</span>
											<span data-style="${args->discounted_style:html:default('font-size: 18px;
font-weight: 700;
color: #dc263d;
line-height: 1;
')}">
												${args->p_price_after_discount:default('${p->price_after_discount:price('''')} €')}
											</span>
										${else}
											<span data-style="${args->no_discount_style:html:default('font-size: 120%;
')}">
												${args->p_price_before_discount}
											</span>
										${end}
										${args->after_price}
									${end}

									${block->with_cart:default(1)}
									<span class="st-add-to-cart-button">
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
											data-style="box-sizing:border-box; ${args->button_style:html:default('vertical-align: bottom;
margin-left: 1em;
border: solid 1px;
border-radius: 6px;
font-size: 17px;
padding-top: 7px;
padding-right: 15px;
padding-bottom: 7px;
padding-left: 15px;
color: #dc263d;
background-color: white;
')}" hover_style="${args->button_style_hover:html:default('color:white; background-color:#dc263d')}">
											<hr class="$icon ${args->button_icon:html:default(shopping-cart)}" style="${args->button_icon_style:html:default('padding-right: 0.5em;
font-size: 100%;
color: inherit;
')}">
											<i class="fa fa-shopping-bag"></i>${args->button:default('&nbsp;+')}
										</a>
									</span>
								</div>
							</div>
						</div>

						${block->button:default(1)}
						<div data-style="${args->button_spacer:html}">
							<a class="det" data-personyze-click-target="products ${p->internal_id:html}" href="${p->cart_url:html}" target="${args->target:html}" data-style="display:block; box-sizing:border-box; position:absolute; width:100%; height:0; display:none; left:0; bottom:0; text-decoration:none; ${args->a_css_4:html}">
								<div style="display:inline-block; width:1em; height:1em; line-height:1; border-radius:50%; ${args->plus_style:html}">${args->button_add_plus}</div>
								${args->button_add_text}
							</a>
						</div>
					</td>
				${end}
			</tr>
			</tbody>
		</table>
		${block->pagination:default(0)}
		<div id="tsp" class="$table_slider_pagination" slider_id="ts" selected_color="${args->pagination_color_on:html:default('rgba(0, 0, 0, 1)')}" style="${args->pagination_color:html}">
		</div>
	</div>

${menu name='Frame', icon='th-large'}
	${menu args->width name='Widget maximum width', type='css_length', param='with_options=none'}
	${menu args->style name='Style', type='css', param='with_responsive=1'}
	${menu args->round name='No cut cell', type='checkbox', param='value_off=', param='value_on=1'}
	${menu args->eq_cell_width name='Equal cell width', type='checkbox', param='value_off=', param='value_on=1'}
	${menu args->eq_cell_height name='Equal cell height', type='checkbox', param='value_off=', param='value_on=1'}
	${menu args->space_between_items name='Space between items', type='css_length', param='with_responsive=1'}
	${menu args->td_style name='Border color', type='css'}
	${menu args->cell_style name='Cell style', type='css'}
	${menu args->url_params name='URL additional parameters', type='external_media_url_params'}
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
	${menu args->arrow_back_img name='Left arrow image', type='arrow', visible_if='args.with_slider!=1'}
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
	${menu args->img_width name='Cell width', type='css_length', param='with_responsive=1'}
	${menu args->img_max_height name='Image maximum height', type='css_length', param='with_responsive=1'}
	${menu p->image_big_url name='Item image', column_tags='image'}
${menu name='Zoom image on hover', icon='bars'}
	${menu block->with_zoom_image name='Zoom image on hover', onchange='block.with_hover_image=block.with_zoom_image^1||""'}
	${menu args->zoom name='Zoom %', type='number'}
	${menu args->landscape name='Orientation of each product image is landscape', type='checkbox', param='value_off=', param='value_on=1'}
${menu name='Hover alternative image', icon='image', description='On mouse hover, show additional product images when available on the product.'}
	${menu block->with_hover_image name='With hover image', onchange='block.with_zoom_image=block.with_hover_image^1||""'}
	${menu p->image_medium_url name='Hover image', column_tags='image'}
${menu name='Discount badge', icon='align-justify', description='Set discount badge to appear for a discounted product, you may choose to set it to show only if the discount is greater than X.'}
	${menu block->with_discount_badge name='With discount badge'}
	${menu args->min_discount_percent name='Show discount badge if % ≥', type='number', param='min=1'}
	${menu args->discount_badge_style name='Badge style', type='css', param='with_responsive=1'}
	${menu args->discount_badge_text_style name='Badge text style', type='css', param='with_responsive=1'}
	${menu args->discount_badge_text name='Text'}
${menu name='New badge', icon='align-justify', description='Set "New" badge to appear for items debut recently.
You may choose a time frame for a product to be considered new. * For new accounts/product feed, all products are new until the day setting condition has been met  .'}
	${menu block->with_new_badge name='With new badge'}
	${menu args->badge_if_newer name='Show NEW badge if newer than', type='date', param='is_span=true', param='format=%0..999d days'}
	${menu args->new_badge_style name='Badge style', type='css', param='with_responsive=1'}
	${menu args->new_badge_text_style name='Badge text style', type='css', param='with_responsive=1'}
	${menu args->new_badge_text name='Text'}
${menu name='Stock badge', icon='align-justify', description='Set "Low in stock" badge to appear for low stock items.
In addition, you can set the quantity number below it a product is considered to be low in stock.  This requires you to populate "quantity" on your product feed   .'}
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
${menu name='Item title', icon='align-justify'}
	${menu args->p_title name='Item title'}
	${menu args->p_title_style name='Item title style', type='css'}
	${menu args->title_max_lines name='Title max lines', type='number', param='min=1'}
${menu name='Add to cart button', icon='cart-plus', description='Set the widget button to add items to the visitor cart. This feature requires you to set a quick add to cart under product interaction settings>add to cart. '}
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
${menu name='Link target URL', icon='link'}
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
	${menu block->with_discount name='With doscount percentage'}
	${menu args->before_price name='Text before price'}
	${menu args->p_price_before_discount name='Price'}
	${menu args->sale_style name='Price before discount: style', type='css', param='with_responsive=1'}
	${menu args->discounted_style name='Discounted style', type='css', param='with_responsive=1'}
	${menu args->no_discount_style name='Discounted style', type='css', param='with_responsive=1'}
	${menu args->after_price name='Text after price'}
	${menu args->discount_style name='Price discount: style', type='css', param='with_responsive=1'}
${menu name='Button', icon='hand-pointer-o'}
	${menu block->button name='With button'}
	${menu args->button_add_text name='Button text'}
	${menu args->button_add_plus name='Icon text'}
	${menu args->a_css_4 name='Button style', type='css', param='with_responsive=1'}
	${menu args->plus_style name='Button style', type='css', param='with_responsive=1'}
	${menu args->button_spacer name='Button reserved space', type='css', param='with_responsive=1'}
```


## Advanced Product Recommendations Widget Template

 This widget supports configurable layout, advanced CSS styling, hover effects, and more.

```
<div id="st_root" class="$responsive $a_add_params" data-style="display:inline-block; position:relative; display:flex; flex-direction:column; justify-content:stretch; ${args->style:html:default('padding: 0px;
border: none;
margin-top: 0px;
margin-right: auto;
margin-bottom: 60px;
margin-left: auto;
width: 100%;
height: auto;
background-color: transparent;
')}; direction: ${args->direction:html:default(ltr)};" data-json-params="${args->url_params:html}" ontplready="
	this._tr = function tr(e, f) {if (e.nodeType==1) for (var i=0; i!=e.childNodes.length; i++) tr(e.childNodes[i], f); else if (e.nodeType==3) f(e)}
">
		${block->with_logo:default(0)}
		<div style="${args->logo_block_style:html:default('text-align: center;
')}">
			<img src="${args->logo_src:html:default('https://counter-backend.personyze.com/upload/362/18a94c1299224ec8-th.jpeg')}">
			<div data-style="${args->logo_text_style:html}">
				${args->logo_text:default(Have a nice day!)}
			</div>
		</div>

		<div style="flex-grow:1000; display:flex; flex-direction:column; justify-content:center">
			${block->animate_cart_button:default(1)}
			<style>
				.st-add-to-cart-button-${action_id} {overflow:hidden}
				.st-add-to-cart-button-${action_id} > a {transition: all ease 0.3s; position:relative; top: 5em; opacity: 0}
				.st-td-hover .st-add-to-cart-button-${action_id} > a {top: 0; opacity: 1}
			</style>

			<style>
				img.st-zoom {transition:transform ease 0.3s; transform: scale(1)}
				img.st-zoom:hover {transform: scale(calc(${args->img_zoom_on_hover:default(100)} / 100))}

				.st-hov:hover {color: ${args->a_hover_color:html:default('#3b3b3b')} !important}
			</style>

			${block->with_hover_image:default(1)}
			<style>
				img.st-zoom {transition-property:opacity; transform: scale(1); opacity: 1}
				img.st-zoom:hover {transform: scale(1); opacity: 0}

				img.st-zoom:last-child {transition:transform ease 0.3s; transform: scale(1)}
				img.st-zoom:last-child:hover {transform: scale(calc(${args->img_zoom_on_hover} / 100)); opacity: 1}

				.st-zoom-b {transition:opacity ease 0.3s; opacity: 0}
				.st-zoom-b:hover {opacity: 1}
			</style>

			<style>
				.st-tab-rnd > *:first-child > tr:first-child > *
				{	border-top-left-radius: ${args->round_border:default(0px)};
					border-top-right-radius: ${args->round_border};
					overflow: hidden;
				}

				.st-tab-rnd > *:last-child > tr:last-child > *
				{	border-bottom-left-radius: ${args->round_border};
					border-bottom-right-radius: ${args->round_border};
					overflow: hidden;
				}
			</style>

			${block->with_hover_shadow:default(0)}
			<style>
				.st-tab-rnd > * > tr > .st-td-hover > .st-tab-rnd-cell
				{   ${args->hover_shadow:default('box-shadow: 0px 0px 3px 3px rgb(15, 10, 10);
')}
				}
			</style>

			${block->with_hover_overlay:default(0)}
			<style>
				.st-tab-rnd > *:first-child > tr:first-child > * > div:first-child > a
				{   transition-property: opacity;
					opacity: 1;
				}
				.st-tab-rnd > *:first-child > tr:first-child > .st-td-hover > div:first-child > a
				{   opacity: 0.33;
				}
				.st-tab-rnd .st-tab-ovy
				{   display: flex;
					flex-direction: column;
					justify-content: center;
					align-items: center;
					position: absolute;
					z-index: 1;
					left: 0;
					top: 0;
					width: 100%;
					height: 100%;
					transition: opacity ease 0.3s;
					opacity: 0;
				}
				.st-tab-rnd .st-td-hover .st-tab-ovy
				{   ${args->hover_opacity:default('opacity: 1;')}
				}
			</style>

			${block->with_ovy2:default(0)}
			<style>
				.ovy2 {position:relative; width:100%; height:0; overflow:visible}
				.ovy2 > div {position:absolute; width:100%; height:100%; bottom:0}
				.ovy2 > span {display:block; pointer-events:none; content:""; position:absolute; width:100%; height:var(--st-tab-rnd-height); left:0; bottom:0; background-color:transparent; opacity:0; transition:all ease 0.4s}
				.st-td-hover .ovy2 > span {${args->hover_ovy2_shad_style:default('background-color:rgb(225, 214, 214); opacity:0.4')}}
				.ovy2 > div > div {transform:translate(0, 0); transition:transform ease 0.4s}
				.st-td-hover .ovy2 > div > div {transform:translate(0, -100%)}
			</style>

			${block->title:default(1)}
			<div data-style="display:flex; align-items:center; ${args->title_bg:html}">
				<div data-style="flex-grow:1000; ${args->title_style:html:default('text-align: center;
font-size: sel(1.75rem, 18px);
font-weight: 700;
letter-spacing: 0.25px;
color: black;
padding-top: 0rem;
padding-right: 0;
padding-bottom: 3rem;
padding-left: 0;
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
					${args->x:default('<div onmouseenter="this.style.backgroundColor=this.style.outlineColor" onmouseleave="this.style.backgroundColor=this.style.textDecorationColor" style="display: inline-block; vertical-align: text-bottom; width: 24px; height: 24px; box-sizing: border-box; border-radius: 50%; border: 0px solid; box-shadow: none; padding: 2px; background-color: rgba(0, 0, 0, 0); text-decoration-color: rgba(0, 0, 0, 0); outline-color: rgb(206, 54, 64); outline-width: 15px; color: rgb(10, 4, 4); cursor: pointer; transition: all 0.3s ease 0s;" class="$personyze_button_dont_show_again" data-action_id="${action_id}"><div style="display: block; width: 100%; height: 100%; transition: all 0.3s ease 0s; border-radius: 50%; background-image: linear-gradient(-45deg, transparent 0%, transparent 43%, currentcolor 43%, currentcolor 59%, transparent 59%, transparent 100%), linear-gradient(45deg, transparent 0%, transparent 43%, currentcolor 43%, currentcolor 59%, transparent 59%, transparent 100%);"></div></div>')}
				</div>
			</div>

			${block->with_timer:default(0)}
			<div style="display:flex; flex-wrap:wrap; justify-content:center; align-items:center">
				${block->with_left_text}
				<div data-style="${args->left_style:html:default('margin-top: 10px;
margin-right: 20px;
margin-bottom: 10px;
margin-left: 20px;
color: white;
font-size: 24px;
text-align: center;
')}">
					${args->left_text:default('<img src="https://cdn.personyze.com/upload/5506/610fad918b0b9980.png" style="width:102px; float:left" />')}
				</div>

				<div class="$timer_custom" data-action_id="${action_id:html}" data-json-value='{
					"start":${args->value:html:default('{"type":"restart_everytime","fixed_date_date":"","fixed_date_timezone":"","fixed_date_time":"","cookie_based_days":"0","cookie_based_hours":1,"cookie_based_minutes":1,"cookie_based_restart":0,"cookie_based_restart_after":"hours","cookie_based_restart_after_hours":"1","cookie_based_restart_after_weekday":"0","restart_everytime_days":"0","restart_everytime_hours":1,"restart_everytime_minutes":1,"timeup_action":"","timeup_message":"","timeup_message_style":""}')},
					"design":{
						"timer_background_style":${args->timer_background_style:json:html:default('display: table-cell;
white-space: nowrap;
vertical-align: middle;
text-align: center;
')},
						"timer_box_style":${args->timer_box_style:json:html:default('display: inline-block;
width: 70px;
height: 72px;
margin-left: .5em;
background-color: #2A2A2A;
border-width: 3px;
border-color: #494949;
border-style: solid;
border-radius: 10px;
text-align: center;
')},
						"timer_caption_days":${args->timer_caption_days:json:html:default('Day(s)')},
						"timer_caption_hours":${args->timer_caption_hours:json:html:default('Hour(s)')},
						"timer_caption_minutes":${args->timer_caption_minutes:json:html:default('Minute(s)')},
						"timer_caption_seconds":${args->timer_caption_seconds:json:html:default('Second(s)')},
						"timer_caption_style":${args->timer_caption_style:json:html:default('color: #A0A0A0;
font-size: 8pt;
font-family: Arial;
font-weight: bold;
')},
						"timer_number_style":${args->timer_number_style:json:html:default('color: white;
font-size: 32pt;
font-family: Arial;
font-weight: bold;
line-height: 1em;
margin-top: -3px;
')}
					}
				}' data-style="${args->timersubstrate_style:html:default('margin: 10px 20px 30px;')}">
				</div>

				${block->with_right_button}
				<a ${args->right_href:default('href=""')} data-style="display:inline-block; ${args->right_button_style:html:default('margin-top: sel(16px, 18px);
margin-right: sel(32px, auto);
margin-bottom: sel(16px, 33px);
margin-left: sel(33px, auto);
padding-top: sel(8px, 2px);
padding-right: sel(15px, 2px);
padding-bottom: sel(8px, 2px);
padding-left: sel(15px, 2px);
height: auto;
line-height: 25px;
font-size: sel(15px, 12px);
font-weight: 600;
background-color: rgb(59, 73, 114);
color: #fff;
border: medium outset rgb(64, 40, 97);
border-radius: 25px;
text-align: center;
vertical-align: middle;
text-decoration: none;
width: 126.656px;
${case }
${when known_device_type=''phone''}display: block;
${else}display: inline-block;
${end}
')}">
					${args->right_button_text:default(SALE PAGE)}
				</a>
			</div>

			<div data-style="${args->content_padding:html:default('width: auto;
margin: auto;
max-width: 98%;
')}">
				<table class="st-tab-rnd" data-style="height:10px; width:auto; border-collapse: separate; border-spacing: ${args->space_between_items:html:default(24px)} 0; margin:0 -${args->space_between_items:html}" ontplready="var that=this; new ResizeObserver(function() {that.style.setProperty('--st-tab-rnd-height', that.offsetHeight+'px')}).observe(this);">
					<tr id="ts" class="$table_slider" data-disabled="${args->with_slider:html}" data-hover_add_class="st-td-hover" data-round="${args->round:html:default(1)}" data-with_scrollbar="${args->with_scrollbar:html}" data-scrollbar_style="${args->scrollbar_style:html:default('background-color: #D8D8D8;
color: #999999;
height: 12px;
')}" data-hide_scrollbar="${args->hide_scrollbar:html:default(1)}" style="width: 100%; box-sizing: border-box; border:none" for_max_vw="${args->for_max_vw:html:default(always)}" eq_cell_width="${args->eq_cell_width:html:default(1)}" eq_cell_height="${args->eq_cell_height:html:default(1)}" arrows_line="${args->arrows_line:html:default(-1)}" arrow_back_img="${args->arrow_back_img:html:default('<svg xmlns=''http://www.w3.org/2000/svg'' width=''24'' height=''42'' viewBox=''0 0 24 42''><path d=''M22.4572074 1.00746147l-21 20.02482143 20.9479397 19.9751786'' stroke=''#b7b7b7'' stroke-width=''2'' stroke-linecap=''round'' stroke-linejoin=''round'' fill=''none'' fill-rule=''evenodd'' /></svg>')}" arrow_style="z-index:9; ${args->arrow_style:html:default('background-color: rgba(219, 195, 195, 0);
max-height: none;
padding-top: 0px;
padding-right: 2px;
padding-bottom: 0px;
padding-left: 2px;
width: auto;
')}" pagination_id="tsp" arrow_back_id="button_back" arrow_forward_id="button_forward" arrows_offset="${args->arrows_offset:html:default(-8)}" hide_buttons="${args->hide_buttons:html}" buttons_always="${args->buttons_always:html:default(1)}" extend_box_length="10px">
						${foreach products as p order by p->time_created desc union sum_last_interested_products order by p->n_viewed desc limit 12}
							<td style="position:relative; height:100%; padding:0; text-align:center; background-color:white; vertical-align:top; border:solid ${args->border_color:html:default(transparent)} 1px">
								<div style="display:block; overflow:visible; position:absolute; z-index:1; left:0; top:0; width:100%; height:var(--st-tab-rnd-height); pointer-events:none; transform:translate(0, 0)">
									<div class="st-tab-rnd-cell" style="${args->cell_border:html}; position:fixed; left:0; top:0; width:100%; height:100%" ontplready="this.parentNode.parentNode.style.overflow='visible'"></div>
								</div>
								<div data-personyze-click-target="products ${p->internal_id:html}" onclick="for (let e=event.target; e &amp;&amp; e!=this; e=e.parentNode) if (e.nodeName == 'A') return; var a=_S_T.new_elem('a', this, {href: ${p->cart_url:json:html}, target: ${args->target:json:html:default(_self)}, style: 'position:absolute; visibility:hidden'}); a.click(); setTimeout(function() {a.parentNode.removeChild(a)}, 100)" data-style="cursor:pointer; width:${args->img_width:html:default('sel(344px, 44vw)')}; ${if args->eq_cell_height:html = 1}height:100%;${end} position:relative; overflow:hidden; box-sizing:border-box">
									<div data-style="position:relative; display:flex; width:100%; ${if args->eq_cell_height:html = 1}height:100%;${end} max-width:100%; margin:auto; box-sizing:border-box; overflow:hidden; text-decoration:none; ${args->img_alignment:html:default('align-items: baseline;
width: 100%;
height: auto;
margin-top: 0px;
margin-right: 0;
margin-bottom: 14px;
margin-left: 0;
z-index: 0;
')}">
										<img class="st-zoom" data-src="${p->image_big_url:html}" data-style="margin:auto; width:auto; height:auto; max-width:100%; max-height:${args->img_max_height:html:default('sel(350px, 80vh)')}; border:none" alt="${p->title:html}">

										${if p->image_medium_url <> ''}
											${block->with_hover_image:default(1)}
											<div class="st-zoom-b" style="position:absolute; background-color:white; display:flex; left:0; top: 0; width:100%; height:100%; justify-content:center; ${args->img_alignment:html}">
												<img data-src="${p->image_medium_url:html}" data-style="width:auto; height:auto; max-width:100%; max-height:${args->img_max_height:html}; border:none" alt="${p->title:html}">
											</div>
										${end}
									</div>

									${block->with_sc:default(1)}
									<div class="$info_lines_scroller" data-no_dismiss_action="1" data-without_close="${args->sc_without_close:html:default(1)}" style="${args->sc_style:html:default('background-color: black;
color: white;
${case }
${when known_device_type=''phone''}font-size: 8px;
${else}font-size: 11px;
${end}
line-height: 3em;
border-radius: 0px;
bottom: 1em;
animation-delay: 1s;
animation-duration: 5s;
animation-iteration-count: infinite;
width: 100%;
display: inline-block;
padding-top: 0px;
padding-right: 5px;
padding-bottom: 0px;
padding-left: 5px;
')}">
										${foreach sum_products_week as s where s->internal_id = p->internal_id limit 1}
											${if s->n_viewed >= args->sc_min_views:json:html:default(800)}
												${block->sc_with_views:default(0)}
												<div>
													<hr class="$icon ${args->sc_icon_views:html:default(user)}" style="${args->sc_icon_views_style:html:default('font-size: 100%;
')}">&nbsp;
													${args->sc_text_views:default('<strong>Trending now!</strong>&nbsp;${s->n_viewed}&nbsp; looked at this recently&nbsp;')}
												</div>
											${end}
											${if s->n_goal >= args->sc_min_goals:json:html:default(20)}
												${block->sc_with_goals:default(0)}
												<div>
													<hr class="$icon ${args->sc_icon_goals:html:default(shopping-cart)}" style="${args->sc_icon_goals_style:html:default('font-size: 100%;
')}">&nbsp;
													${args->sc_text_goals:default('<strong>Popular!</strong> Sold ${s->n_goal}&nbsp;times recently')}
												</div>
											${end}
											${if p->inventory between 1 and args->sc_min_inventory:html:default(5)}
												${if s->n_goal >= args->sc_min_goals_for_inventory:json:html:default(0)}
													${block->sc_with_inventory:default(0)}
													<div>
														<hr class="$icon ${args->sc_icon_inventory:html:default(redo)}" style="${args->sc_icon_inventory_style:html}">&nbsp;
														${args->sc_text_inventory:default('<strong>Only&nbsp;${p->inventory}&nbsp; </strong>left in stock!')}
													</div>
												${end}
											${end}
										${end}
										${if (p->prev_price - p->price_after_discount) * 100 / p->prev_price >= args->sc_min_price_drop:html:default(10)}
											${if p->time_price_changed >= unix_timestamp() - 24*60*60*args->sc_min_price_drop_days:html:default(10)}
												${block->sc_with_price_drop:default(0)}
												<div ontplload="by_id.st_root._tr(this, n => {n.data = n.data.replace(/\{D\}/g, this.dataset.days).replace(/\{P\}/g, this.dataset.prc)})" data-days="${ceil(greatest(1, unix_timestamp() - p->time_price_changed) / (24*60*60))}" data-prc="${floor((p->prev_price - p->price_after_discount) * 100 / p->prev_price)}">
													<hr class="$icon ${args->sc_icon_price_drop:html:default(tag)}" style="${args->sc_icon_price_drop_style:html:default('font-size: 100%;
')}">&nbsp;
													${args->sc_text_price_drop:default('Price dropped by {P}% in last {D} days')}
												</div>
											${end}
										${end}
										${if (p->price_before_discount - p->price_after_discount) * 100 / p->price_before_discount >= args->sc_min_discount:html:default(50)}
											${block->sc_with_discount:default(0)}
											<div ontplload="by_id.st_root._tr(this, n => {n.data = n.data.replace(/\{P\}/g, this.dataset.prc)})" data-prc="${floor((p->price_before_discount - p->price_after_discount) * 100 / p->price_before_discount)}">
												<hr class="$icon ${args->sc_icon_discount:html:default(tag)}" style="${args->sc_icon_discount_style:html:default('font-size: 100%;
')}">&nbsp;
												${args->sc_text_discount:default('<strong>Sale!</strong> {P}% discount')}
											</div>
										${end}
										${if p->time_created > unix_timestamp() - 24*60*60*args->sc_min_new_days:html:default(7)}
											${block->sc_with_new:default(0)}
											<div ontplload="by_id.st_root._tr(this, n => {n.data = n.data.replace(/\{D\}/g, this.dataset.days)})" data-days="${ceil(greatest(1, unix_timestamp() - p->time_created) / (24*60*60))}">
												<hr class="$icon ${args->sc_icon_new:html:default(fire)}" style="${args->sc_icon_new_style:html:default('font-size: 100%;
')}">&nbsp;
												${args->sc_text_new:default('<strong>New in stock.</strong> Added before {D} days')}
											</div>
										${end}
										${block->sc_with_free1:default(0)}
										<div>
											<hr class="$icon ${args->sc_icon_free1:html:default(fire)}" style="${args->sc_icon_free1_style:html:default('font-size: 100%;
')}">&nbsp;
											${args->sc_text_free1:default(Time limited special offer)}
										</div>
										${block->sc_with_free2:default(0)}
										<div>
											<hr class="$icon ${args->sc_icon_free2:html:default(fire)}" style="${args->sc_icon_free2_style:html:default('font-size: 100%;
')}">&nbsp;
											${args->sc_text_free2:default(Time limited special offer2)}
										</div>
										${block->sc_with_free3:default(0)}
										<div>
											<hr class="$icon ${args->sc_icon_free3:html:default(fire)}" style="${args->sc_icon_free3_style:html:default('font-size: 100%;
')}">&nbsp;
											${args->sc_text_free3:default(Time limited special offer3)}
										</div>
									</div>

									${block->with_popular_badge_week:default(0)}
									<span>
										${foreach sum_products_week as s where s->internal_id = p->internal_id limit 1}
											${if 100 - s->percentile_viewed <= args->badge_if_more_popular_week:default(5)}
												<div data-style="position: absolute; ${args->popular_badge_week_style:html:default('top: 0;
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
													<span data-style="${args->popular_badge_week_text_style:html:default('font-size: 16px;
font-weight: 600;
')}">${args->popular_badge_week_text:default(Popular)}</span>
												</div>
											${end}
										${end}
									</span>

									${block->with_popular_badge_1day:default(0)}
									<span>
										${foreach sum_products_1day as s where s->internal_id = p->internal_id limit 1}
											${if 100 - s->percentile_viewed <= args->badge_if_more_popular_1day:default(5)}
												<div data-style="position: absolute; ${args->popular_badge_1day_style:html:default('top: 0;
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
													<span data-style="${args->popular_badge_1day_text_style:html:default('font-size: 16px;
font-weight: 600;
')}">${args->popular_badge_1day_text:default(Popular)}</span>
												</div>
											${end}
										${end}
									</span>

									${block->with_bestseller_badge_week:default(0)}
									<span>
										${foreach sum_products_week as s where s->internal_id = p->internal_id limit 1}
											${if 100 - s->percentile_goal <= args->badge_if_more_sold_week:default(5)}
												<div data-style="position: absolute; ${args->bestseller_badge_week_style:html:default('top: 0;
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
													<span data-style="${args->bestseller_badge_week_text_style:html:default('font-size: 16px;
font-weight: 600;
')}">${args->bestseller_badge_week_text:default(Best seller)}</span>
												</div>
											${end}
										${end}
									</span>

									${block->with_bestseller_badge_1day:default(0)}
									<span>
										${foreach sum_products_1day as s where s->internal_id = p->internal_id limit 1}
											${if 100 - s->percentile_goal <= args->badge_if_more_sold_1day:default(5)}
												<div data-style="position: absolute; ${args->bestseller_badge_1day_style:html:default('top: 0;
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
													<span data-style="${args->bestseller_badge_1day_text_style:html:default('font-size: 16px;
font-weight: 600;
')}">${args->bestseller_badge_1day_text:default(Best seller)}</span>
												</div>
											${end}
										${end}
									</span>

									${block->with_discount_badge:default(1)}
									<span>
										${if p->discount_percent >= args->min_discount_percent:default(10)}
											<div data-style="position: absolute; ${args->discount_badge_style:html:default('top: 0;
right: 0px;
width: 7em;
height: 7em;
font-size: 7px;
text-shadow: rgba(255,255,255,0.5) 0px 3px 3px;
background-color: red;
border: solid rgb(221, 228, 165) 0px;
color: rgb(252, 249, 249);
border-radius: 0%;
display: flex;
justify-content: center;
align-items: center;
')}">
												<span data-style="${args->discount_badge_text_style:html:default('line-height: 1.25;
font-size: 9px;
font-weight: 600;
')}">${args->discount_badge_text:default('<div style="font-size:14px">${p->discount_percent:floor}%</div>
')}</span>
											</div>
										${end}
									</span>

									${block->with_price_drop_badge:default(0)}
									<span>
										${if (p->prev_price - p->price_after_discount) * 100 / p->prev_price >= args->min_price_drop:html:default(6)}
											${if p->time_price_changed >= unix_timestamp() - 24*60*60*args->min_price_drop_days:html:default(500)}
												<div data-style="position: absolute; ${args->price_drop_badge_style:html:default('top: 0;
right: 48px;
width: 7em;
height: 7em;
font-size: 7px;
text-shadow: rgba(255,255,255,0.5) 0px 3px 3px;
background-color: red;
border: solid rgb(221, 228, 165) 6px;
color: rgb(252, 249, 249);
border-radius: 50%;
display: flex;
justify-content: center;
align-items: center;
')}">
													<span data-style="${args->price_drop_badge_text_style:html:default('line-height: 1.25;
font-size: 9px;
font-weight: 600;
')}"
													ontplload="by_id.st_root._tr(this, n => {n.data = n.data.replace(/\{D\}/g, this.dataset.days).replace(/\{P\}/g, this.dataset.prc)})"
													data-days="${ceil(greatest(1, unix_timestamp() - p->time_price_changed) / (24*60*60))}"
													data-prc="${floor((p->prev_price - p->price_after_discount) * 100 / p->prev_price)}"
													>${args->text_price_drop:default('Price dropped by {P}% in last {D} days')}</span>
												</div>
											${end}
										${end}
									</span>

									${block->with_new_badge:default(1)}
									<span>
										${if unix_timestamp() - p->time_created <= args->badge_if_newer:default(604800)}
											<div data-style="position: absolute; ${args->new_badge_style:html:default('top: 0;
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
												<span data-style="${args->new_badge_text_style:html:default('font-size: 16px;
font-weight: 600;
')}">${args->new_badge_text:default(NEW)}</span>
											</div>
										${end}
									</span>

									${block->with_time_badge:default(1)}
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
										${if p->inventory between 1 and args->badge_if_less_stock:default(5000)}
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
										${if p->custom_9 != ''}
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
')}">${args->db_badge_text:default('${p->custom_9}')}</span>
											</div>
										${end}
									</span>

									${block->with_hover_overlay:default(0)}
									<div class="st-tab-ovy" style="${args->hover_overlay_style:html:default('background-color: rgba(208, 221, 211, 0.48);
')}">
										${args->hover_overlay_text:default(MORE)}

										${block->with_hover_overlay_a}
										<div style="${args->hover_overlay_a_block_style:html:default('text-align: center;
')}">
										<a class="$flat_btn" href="${args->hover_overlay_a_href:html:default('javascript:')}" data-style="box-sizing:border-box; ${args->hover_overlay_a_style:html:default('color: rgb(39, 36, 70);
padding-top: 9px;
padding-right: 13px;
padding-bottom: 9px;
padding-left: 13px;
font-size: 17px;
line-height: 14px;
font-weight: 700;
font-family: Lato;
margin-top: 0px;
margin-right: 0px;
margin-bottom: 10px;
margin-left: 0px;
background-color: rgba(245, 36, 36, 0);
width: 10.6rem;
border: solid;
white-space: nowrap;
')}" hover_style="${args->hover_overlay_a_style_hover:html:default('color: rgb(251, 250, 250);
background-color: #631d85;
')}">
											${args->hover_overlay_a_text:default(Quick view)}
										</a>
										</div>

										${block->with_hover_overlay_a2}
										<div style="${args->hover_overlay_a2_block_style:html:default('text-align: center;
')}">
										<a class="$flat_btn" data-personyze-click-target="products ${p->internal_id:html}" href="${args->hover_overlay_a2_href:html:default('${p->cart_url}')}" data-style="box-sizing:border-box; ${args->hover_overlay_a2_style:html:default('color: rgb(39, 36, 70);
padding-top: 9px;
padding-right: 13px;
padding-bottom: 9px;
padding-left: 13px;
font-size: 17px;
line-height: 14px;
font-weight: 700;
font-family: Lato;
margin: 0px;
background-color: rgba(245, 36, 36, 0);
width: 10.6rem;
border: solid;
white-space: nowrap;
')}" hover_style="${args->hover_overlay_a2_style_hover:html:default('color: rgb(7, 3, 3);
background-color: rgb(237, 238, 227);
')}">
											${args->hover_overlay_a2_text:default(Choose options)}
										</a>
										</div>
									</div>
								</div>

								${block->with_custom_column:default(0)}
								<div>
									<div style="${args->custom_column_style:html:default('text-align: left;
padding: 1em;
font-weight: 600;
')}">${args->custom_column:html:default('${p->category}')}</div>
								</div>

								${block->with_options_link:default(0)}
								<a data-personyze-click-target="products ${p->internal_id:html}" href="${args->options_link_href:html:default('${p->cart_url:html}')}" target="${args->target:html}" data-style="${args->options_link_style:html:default('padding-top: 15px;
padding-right: 0px;
padding-bottom: 0px;
padding-left: 0px;
')}; display:block; margin:auto; box-sizing:border-box; width:${args->img_width:html}; text-decoration:none">
									${args->options_link_text:default(+ See options)}
								</a>

								${block->with_title:default(1)}
								<a data-personyze-click-target="products ${p->internal_id:html}" href="${p->cart_url:html}" target="${args->target:html}" data-style="display:block; margin:auto; box-sizing:border-box; width:${args->img_width:html}; text-decoration:none">
									<div class="st-hov" data-style="${args->a_css:html:default('padding: 1px;
text-transform: none;
color: black;
font-size: sel(16px, 16px);
font-weight: 100;
margin: 10px;
text-align: center;
line-height: 1.3;
transition: color .15s ease;
')}; position:relative; overflow:hidden; text-overflow:ellipsis; display:-webkit-box; -webkit-box-orient:vertical; -webkit-line-clamp:${args->title_max_lines:html:default(3)}; line-clamp:${args->title_max_lines:html}">
										${p->title}
										<div style="display:none; position:absolute; bottom:0; left:0; background-color:white">…</div>
									</div>
								</a>

								${block->stats_1day:default(0)}
								<span>
									${foreach sum_products_1day as s where s->internal_id = p->internal_id limit 1}
										${if s->n_viewed >= args->hide_no_view_1day:default(3)}
											${if s->n_goal >= args->hide_no_goal_1day:default(1)}
												${if s->n_viewed > 0}
													<div style="${args->text_style_1day:html:default('padding-top: 1em;
padding-right: 0;
padding-bottom: 1em;
padding-left: 0;
font-weight: 600;
')}">
														<hr class="$icon ${args->icon_n_viewed_1day:html:default(users)}" style="${args->icon_style_n_viewed_1day:html:default('padding-right: 0.5em;
font-size: 100%;
color: inherit;
')}">
														${args->n_viewed_1day:default('${s->n_viewed*1} views today')}
													</div>
												${end}
												${if s->n_goal > 0}
													<div style="${args->text_style_1day:html}">
														<hr class="$icon ${args->icon_n_goal_1day:html:default(users)}" style="${args->icon_style_n_goal_1day:html:default('padding-right: 0.5em;
font-size: 100%;
color: inherit;
')}">
														${args->n_goal_1day:default('${s->n_goal*1} purchases today')}
													</div>
												${end}
											${end}
										${end}
									${end}
								</span>

								${block->stats_week:default(1)}
								<span>
									${foreach sum_products_week as s where s->internal_id = p->internal_id limit 1}
										${if s->n_viewed >= args->hide_no_view_week:default(600)}
											${if s->n_goal >= args->hide_no_goal_week:default(10)}
												${if s->n_viewed > 0}
													<div style="${args->text_style_week:html:default('padding-top: 8px;
padding-right: 0;
padding-bottom: 8px;
padding-left: 0;
font-weight: 400;
background-color: rgb(3, 1, 1);
border-top-left-radius: 0px;
border-top-right-radius: 55px;
border-bottom-right-radius: 55px;
border-bottom-left-radius: 0px;
height: auto;
color: rgb(256, 256, 256);
width: 265px;
margin-top: -33px;
margin-right: 22px;
margin-bottom: 20px;
margin-left: 0px;
font-size: 11px;
position: absolute;
top: -170px;
text-transform: lowercase;
')}">
														<hr class="$icon ${args->icon_n_viewed_week:html:default(users)}" style="${args->icon_style_n_viewed_week:html:default('padding-right: 0.5em;
font-size: 100%;
color: inherit;
')}">
														${args->n_viewed_week:default('This product has been popular&nbsp;${s->n_viewed*1}&nbsp; views recently.')}
													</div>
												${end}
												${if s->n_goal > 0}
													<div style="${args->text_style_week:html}">
														<hr class="$icon ${args->icon_n_goal_week:html:default(users)}" style="${args->icon_style_n_goal_week:html:default('padding-right: 0.5em;
font-size: 100%;
color: inherit;
')}">
														${args->n_goal_week:default('This product has been popular&nbsp;${s->n_goal}&nbsp; purchases recently.')}
													</div>
												${end}
											${end}
										${end}
									${end}
								</span>

								${block->price:default(1)}
								<div data-style="margin:auto; box-sizing:border-box; width:${args->img_width:html}; ${args->price_style:html:default('padding-top: 0px;
padding-right: 0px;
padding-bottom: 5px;
padding-left: 0px;
')}">
									${if p->price_after_discount}
										${if p->price_after_discount < p->price_before_discount}
											<span style="white-space:nowrap">
												<span style="${args->old_price_style:html:default('font-size: 17px;
font-weight: 500;
text-decoration: line-through;
')}">
													${args->old_price_before}${args->p_price_before_discount:default('&euro;${p->price_before_discount:price('''')}')}${args->old_price_after}
												</span>
											</span>
											<span style="white-space:nowrap">
												<span style="${args->new_price_style:html:default('font-size: 17px;
font-weight: 500;
color: black;
')}">
													${args->old_price_before)}${args->p_price_after_discount:default('&euro;${p->price_after_discount:price('''')}')}${args->old_price_after}
												</span>
											</span>
											<div style="${args->sale_text_style:html:default('display: inline-block;
font-size: 50%;
line-height: 1;
')}">
												${args->sale_text}
											</div>
										${else}
											<span style="white-space:nowrap; ${args->nosale_price_style:html:default('font-size: 17px;
font-weight: 500;
')}">
												${args->old_price_before}${args->p_price_before_discount}${args->old_price_after}
											</span>
										${end}
									${end}
								</div>

								${block->rating:default(0)}
								<span>
									${if p->rank > 0}
										<hr class="$rating" data-value="${p->rank:html:default(0)}" style="vertical-align:middle; ${args->rating_style:html:default('color: #631d85;
--bgcolor: white;
--border-color: rgba(225, 214, 214, 0.87);
width: 120px;
height: 16px;
')}">
										${if p->n_reviews > 0}
											<span style="vertical-align:middle; ${args->n_reviews_style:html:default('font-size:85%')}">${args->n_reviews:default('(${p->n_reviews})')}</span>
										${end}
									${end}
								</span>

								${block->description:default(0)}
								<div data-style="margin:auto; box-sizing:border-box; width:${args->img_width:html}">
									<div data-style="display:inline-block; ${args->a_css_3:html}; padding-bottom:0">
										${p->description}
									</div>
								</div>

								${block->payment:default(0)}
								<div data-style="${args->payment_style:html:default('font-size: 12px;
color: #17120f;
font-weight: 400;
font-family: -apple-system, BlinkMacSystemFont, ''Segoe UI'', Roboto, Arial, sans-serif;
')}; margin:auto; box-sizing:border-box; width:${args->img_width:html}">
									<span ontplready="
										this.textContent =
										${if p->price_after_discount >= args->payment_min:default(35)}
											this.dataset.yes
										${else}
											this.dataset.no
										${end}.replace(/\{(M|N|P)\}/g, function(a, m) {return {M: '${args->payment_min:html}', N: '${args->payment_n:html:default(4)}', P: ('${p->price_after_discount:html}'/'${args->payment_n:html}').toFixed(2)}[m]})
									" data-yes="${args->payment_text_yes:html:default('{N} interest-free payments of {P} with')}" data-no="${args->payment_text_no:html:default('{N} interest-free payments. Available for orders above {M}.')}"></span>
									${args->payment_text_2:default('<font color="#17120f" face="Klarna Headline"><span style="letter-spacing: -0.5px;"><b>FREE TEXT</b></span></font>')}
								</div>

								${block->with_link_button:default(0)}
								<div data-style="box-sizing:border-box; ${args->link_button_box_style:html:default('text-align: center;
')}">
									<a class="$flat_btn" data-personyze-click-target="products ${p->internal_id:html}" href="${args->link_button_href:html:default('${p->cart_url}')}" data-style="box-sizing:border-box; ${args->link_button_style:html:default('color: rgb(39, 36, 70);
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
white-space: no-wrap;
')}" hover_style="${args->link_button_style_hover:html:default('color: rgb(7, 3, 3);
font-weight: 700;
background-color: rgb(237, 238, 227);
')}">
										${args->link_button_text:default(See details)}
									</a>
								</div>

								${block->with_cart:default(0)}
								<div class="st-add-to-cart-button-${action_id:html}">
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

								${block->with_ovy2:default(0)}
								<div class="ovy2">
									<span></span>
									<div>
										<div style="${args->hover_ovy2_style:html:default('background-color: white;
font-size: 20px;
')}">



											<div style="${args->hover_ovy2_style2:html:default('font-size: 30px;
margin-top: 0em;
margin-right: 0em;
margin-bottom: 1em;
margin-left: 0em;
')}">
												${args->hover_ovy2_text:default(MORE INFO)}
											</div>

											${block->with_hover_ovy2_a}
											<div style="${args->hover_ovy2_a_block_style:html:default('text-align: center;
')}">
												<a class="$flat_btn" href="${args->hover_ovy2_a_href:html:default('javascript:')}" data-style="box-sizing:border-box; ${args->hover_ovy2_a_style:html:default('color: rgb(39, 36, 70);
padding-top: 9px;
padding-right: 13px;
padding-bottom: 9px;
padding-left: 13px;
font-size: 17px;
line-height: 14px;
font-weight: 700;
font-family: Lato;
margin-top: 0px;
margin-right: 0px;
margin-bottom: 10px;
margin-left: 0px;
background-color: rgba(245, 36, 36, 0);
width: 10.6rem;
border: solid;
white-space: nowrap;
')}" hover_style="${args->hover_ovy2_a_style_hover:html:default('color: rgb(251, 250, 250);
background-color: #631d85;
')}">
													${args->hover_ovy2_a_text:default(Quick view)}
												</a>
											</div>

											${block->with_hover_ovy2_a2}
											<div style="${args->hover_ovy2_a2_block_style:html:default('text-align: center;
')}">
												<a class="$flat_btn" data-personyze-click-target="products ${p->internal_id:html}" href="${args->hover_ovy2_a2_href:html:default('${p->cart_url}')}" data-style="box-sizing:border-box; ${args->hover_ovy2_a2_style:html:default('color: rgb(39, 36, 70);
padding-top: 9px;
padding-right: 13px;
padding-bottom: 9px;
padding-left: 13px;
font-size: 17px;
line-height: 14px;
font-weight: 700;
font-family: Lato;
margin: 0px;
background-color: rgba(245, 36, 36, 0);
width: 10.6rem;
border: solid;
white-space: nowrap;
')}" hover_style="${args->hover_ovy2_a2_style_hover:html:default('color: rgb(7, 3, 3);
background-color: rgb(237, 238, 227);
')}">
													${args->hover_ovy2_a2_text:default(Choose options)}
												</a>
											</div>
										</div>
									</div>
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

${menu name='Main Layout Settings', icon='th-large', description='Configure the overall layout and appearance of your product recommendations widget.'}
	${menu args->style name='Base Style', description='Set the basic CSS styling for the layout.', type='css', param='with_responsive=1'}
	${menu args->content_padding name='Content Box Padding', description='Adjust the spacing around your content area.', type='css', param='with_responsive=1'}
	${menu args->round name='Non-Rounded Cells', description='Disable rounded corners on cells.', type='checkbox', param='value_off=', param='value_on=1'}
	${menu args->eq_cell_width name='Equal Cell Width', description='Force all product cells to have the same width.', type='checkbox', param='value_off=', param='value_on=1'}
	${menu args->eq_cell_height name='Equal Cell Height', description='Force all product cells to have the same height.', type='checkbox', param='value_off=', param='value_on=1'}
	${menu args->space_between_items name='Spacing Between Items', description='Set the gap between individual product items.', type='css_length', param='with_responsive=1'}
	${menu args->border_color name='Border Color', description='Define the cell border color.', type='color'}
	${menu args->cell_border name='Shadow Effect', description='Apply a shadow effect to product cells.', type='css'}
	${menu args->round_border name='Rounded Border', description='Set the radius for rounded cell corners.', type='css_length'}
	${menu args->direction name='Localization Settings', description='Choose the text direction for proper localization.', type='select', param='options=[["Left to right","ltr"],["Right to left","rtl"]]'}
	${menu args->url_params name='Additional URL Parameters', description='Define extra URL parameters for advanced behaviors.', type='external_media_url_params'}
${menu name='Hover Shadow', icon='clone', description='Configure the shadow effect that appears on product items when hovered.'}
	${menu block->with_hover_shadow name='Enable Hover Shadow', description='Toggle a shadow effect on product items when the mouse hovers over them.'}
	${menu args->hover_shadow name='Shadow Styling', description='Define the CSS shadow style to apply on hover.', type='css'}
${menu name='Hover Overlay', icon='mouse-pointer', description='Set up an overlay effect to appear when hovering over a product.'}
	${menu block->with_hover_overlay name='Enable Hover Overlay', description='Toggle an overlay on product items on mouse hover.'}
	${menu args->hover_overlay_style name='Overlay Style', description='Specify CSS styling for the overlay.', type='css'}
	${menu args->hover_opacity name='Overlay Opacity', description='Define the opacity level of the overlay on hover.', type='css'}
	${menu args->hover_overlay_text name='Overlay Text', description='Set custom text to display on the overlay.'}
	${menu block->with_hover_overlay_a name='Overlay Link 1', description='Add a clickable link within the overlay.'}
	${menu args->hover_overlay_a_block_style name='Overlay Link 1 Block Style', description='Apply CSS styling to the container of the overlay link.', type='css'}
	${menu args->hover_overlay_a_text name='Overlay Link 1 Text', description='Text to display for the first overlay link.'}
	${menu args->hover_overlay_a_href name='Overlay Link 1 URL', description='Destination URL for the first overlay link.'}
	${menu args->hover_overlay_a_style name='Overlay Link 1 Style', description='CSS style for the first overlay link.', type='css'}
	${menu args->hover_overlay_a_style_hover name='Overlay Link 1 Hover Style', description='CSS style for the first overlay link when hovered.', type='css'}
	${menu block->with_hover_overlay_a2 name='Overlay Link 2', description='Add a secondary clickable link in the overlay.'}
	${menu args->hover_overlay_a2_block_style name='Overlay Link 2 Block Style', description='Apply CSS styling to the container of the second overlay link.', type='css'}
	${menu args->hover_overlay_a2_text name='Overlay Link 2 Text', description='Text for the second overlay link.'}
	${menu args->hover_overlay_a2_href name='Overlay Link 2 URL', description='Destination URL for the second overlay link.'}
	${menu args->hover_overlay_a2_style name='Overlay Link 2 Style', description='CSS styling for the second overlay link.', type='css'}
	${menu args->hover_overlay_a2_style_hover name='Overlay Link 2 Hover Style', description='CSS styling for the second overlay link on hover.', type='css'}
${menu name='Hover Overlay from Bottom', icon='mouse-pointer', description='Set up an overlay that slides up from the bottom on hover.'}
	${menu block->with_ovy2 name='Enable Bottom Overlay', description='Toggle the bottom overlay effect.'}
	${menu args->hover_ovy2_shad_style name='Overlay Shadow Style', description='CSS for the shadow effect on the bottom overlay.', type='css'}
	${menu args->hover_ovy2_style name='Bottom Overlay Style', description='Define the CSS styling for the bottom overlay container.', type='css'}
	${menu args->hover_ovy2_text name='Bottom Overlay Text', description='Text to display within the bottom overlay.'}
	${menu args->hover_ovy2_style2 name='Overlay Text Style', description='CSS styling for the text within the bottom overlay.', type='css'}
	${menu block->with_hover_ovy2_a name='Bottom Overlay Link 1', description='Add a link inside the bottom overlay.'}
	${menu args->hover_ovy2_a_block_style name='Overlay Link 1 Block Style', description='Style the block for the first link in the bottom overlay.', type='css'}
	${menu args->hover_ovy2_a_text name='Bottom Overlay Link 1 Text', description='Text for the first link in the bottom overlay.'}
	${menu args->hover_ovy2_a_href name='Bottom Overlay Link 1 URL', description='URL for the first bottom overlay link.'}
	${menu args->hover_ovy2_a_style name='Bottom Overlay Link 1 Style', description='CSS styling for the first bottom overlay link.', type='css'}
	${menu args->hover_ovy2_a_style_hover name='Bottom Overlay Link 1 Hover Style', description='CSS styling for the first bottom overlay link when hovered.', type='css'}
	${menu block->with_hover_ovy2_a2 name='Bottom Overlay Link 2', description='Add a second link inside the bottom overlay.'}
	${menu args->hover_ovy2_a2_block_style name='Overlay Link 2 Block Style', description='Style the block for the second link in the bottom overlay.', type='css'}
	${menu args->hover_ovy2_a2_text name='Bottom Overlay Link 2 Text', description='Text for the second link in the bottom overlay.'}
	${menu args->hover_ovy2_a2_href name='Bottom Overlay Link 2 URL', description='URL for the second bottom overlay link.'}
	${menu args->hover_ovy2_a2_style name='Bottom Overlay Link 2 Style', description='CSS styling for the second bottom overlay link.', type='css'}
	${menu args->hover_ovy2_a2_style_hover name='Bottom Overlay Link 2 Hover Style', description='CSS styling for the second bottom overlay link on hover.', type='css'}
${menu name='Logo', icon='bars', description='Customize logo settings for the widget.'}
	${menu block->with_logo name='Enable Logo', description='Toggle the display of the logo.'}
	${menu args->logo_src name='Logo Image', description='Set the URL for the logo image.', type='media_url'}
	${menu args->logo_block_style name='Logo Block Style', description='Define the CSS style for the logo container.', type='css'}
	${menu args->logo_text name='Logo Text', description='Text to display below the logo.'}
	${menu args->logo_text_style name='Logo Text Style', description='CSS styling for the logo text.', type='css'}
${menu name='Slider Options', icon='arrow-right', description='Adjust slider behavior for product display.'}
	${menu block->with_arrows name='Enable Arrow Buttons', description='Toggle arrow buttons for slider navigation.'}
	${menu args->btn_style name='Arrow Button Style', description='CSS styling for slider arrow buttons.', type='css'}
	${menu args->btn_hover_style name='Arrow Button Hover Style', description='CSS styling for arrow buttons on hover.', type='css'}
	${menu args->hide_buttons name='Hide Arrow Buttons', description='Hide arrow buttons if nothing is left to scroll.', type='checkbox', param='value_off=', param='value_on=1', visible_if='block.title-0 && block.with_arrows-0'}
	${menu args->buttons_always name='Always Show Arrows', description='Always display arrow buttons, even when the mouse is not hovering.', type='checkbox', param='value_off=', param='value_on=1', visible_if='!(block.with_arrows-0)'}
	${menu args->with_slider name='Use Slider Widget', description='Enable the slider widget for a carousel-like display.', type='checkbox', param='value_off=1', param='value_on=', onchange='if (args.with_slider==1) block.with_arrows = block.pagination = 0'}
	${menu args->with_scrollbar name='Include Scrollbar', description='Display a scrollbar when not using the slider widget.', type='checkbox', param='value_off=', param='value_on=1', visible_if='args.with_slider!=1'}
	${menu args->hide_scrollbar name='Hide Scrollbar', description='Hide the scrollbar from the view.', type='checkbox', param='value_off=', param='value_on=1', visible_if='args.with_slider!=1 && args.with_scrollbar==1'}
	${menu args->scrollbar_style name='Scrollbar Style', description='CSS styling for the scrollbar.', type='css', visible_if='args.with_slider!=1 && args.with_scrollbar==1'}
	${menu args->for_max_vw name='Slider Widget Max Width', description='Show the slider widget only if screen width is below this threshold.', type='css_length', param='with_options=always', visible_if='args.with_slider!=1'}
	${menu args->arrow_back_img name='Left Arrow Image', description='Set the image for the left arrow of the slider.', type='arrow', visible_if='args.with_slider!=1'}
	${menu args->arrow_style name='Arrows Style', description='CSS styling for the slider arrows.', type='css', visible_if='args.with_slider!=1'}
	${menu args->arrows_offset name='Slider Arrows Offset', description='Adjust the offset of the slider arrows.', type='number', visible_if='args.with_slider!=1'}
	${menu args->arrows_line name='Arrows Alignment', description='Center the arrows vertically on product images.', type='checkbox', param='value_off=-1', param='value_on=0', visible_if='args.with_slider!=1'}
	${menu block->pagination name='Slider Pagination', description='Toggle pagination bullets for the slider.', visible_if='args.with_slider!=1'}
	${menu args->pagination_color_on name='Selected Bullet Color', description='Color of the active pagination bullet.', type='color', visible_if='args.with_slider!=1'}
	${menu args->pagination_color name='Bullet Style', description='CSS styling for pagination bullets.', type='css', visible_if='args.with_slider!=1'}
${menu name='Widget Title', icon='bookmark', description='Configure the title bar of your widget.'}
	${menu block->title name='Enable Title Bar', description='Toggle the display of the widget title bar.'}
	${menu args->title name='Title Text', description='Enter the title text for your widget.'}
	${menu args->title_bg name='Title Background Style', description='CSS styling for the title background.', type='css', param='with_responsive=1'}
	${menu args->title_style name='Title Text Style', description='CSS styling for the title text.', type='css', param='with_responsive=1'}
${menu name='Close Button', icon='close', description='Set up the close button for the widget.'}
	${menu block->x name='Enable Close Button', description='Toggle the display of the close button.'}
	${menu args->x name='Close Button', description='Customize the look of the close button.', type='dontshowagain', param='style=cursor:pointer; vertical-align:middle'}
	${menu args->x_style name='Close Button Position', description='CSS styling for the close button placement.', type='css'}
${menu name='Image/Cell Width', icon='image', description='Adjust dimensions and alignment for product images.'}
	${menu args->img_width name='Cell Width', description='Set the width of each product cell.', type='css_length', param='with_responsive=1'}
	${menu args->img_max_height name='Image Maximum Height', description='Define the maximum height for product images.', type='css_length', param='with_responsive=1'}
	${menu args->img_alignment name='Image Alignment', description='Set how product images are aligned within their cell.', type='css'}
	${menu p->image_big_url name='Item Image', description='URL for the main product image.', column_tags='image'}
${menu name='Zoom Image on Hover', icon='bars', description='Set the zoom effect on product images when hovered.'}
	${menu args->img_zoom_on_hover name='Zoom Percentage', description='Define the zoom percentage applied on hover.', type='number'}
${menu name='Hover Alternative Image', icon='image', description='Display an alternate image on mouse hover when available.'}
	${menu block->with_hover_image name='Enable Hover Image', description='Toggle the alternate hover image.', onchange='block.with_zoom_image=block.with_hover_image^1||""'}
	${menu p->image_medium_url name='Hover Image', description='URL for the alternate hover image.', column_tags='image'}
${menu name='Most Popular Badge (week)', icon='align-justify', description='Display a badge for products that are amongst N% of the most popular on the site.'}
	${menu block->with_popular_badge_week name='Show Most Popular Badge (week)', description='Toggle the most popular badge display.'}
	${menu args->badge_if_more_popular_week name='Most Popular Badge Threshold', description='Badge appears if product is more popular than this percent of most popular products.', type='number'}
	${menu args->popular_badge_week_style name='Badge Style', description='CSS styling for the most popular badge.', type='css', param='with_responsive=1'}
	${menu args->popular_badge_week_text_style name='Badge Text Style', description='CSS styling for the most popular badge text.', type='css', param='with_responsive=1'}
	${menu args->popular_badge_week_text name='Badge Text', description='Text to display for the most popular badge.'}
${menu name='Most Popular Badge (1 day)', icon='align-justify', description='Display a badge for products that are amongst N% of the most popular on the site.'}
	${menu block->with_popular_badge_1day name='Show Most Popular Badge (1 day)', description='Toggle the most popular badge display.'}
	${menu args->badge_if_more_popular_1day name='Most Popular Badge Threshold', description='Badge appears if product is more popular than this percent of most popular products.', type='number'}
	${menu args->popular_badge_1day_style name='Badge Style', description='CSS styling for the most popular badge.', type='css', param='with_responsive=1'}
	${menu args->popular_badge_1day_text_style name='Badge Text Style', description='CSS styling for the most popular badge text.', type='css', param='with_responsive=1'}
	${menu args->popular_badge_1day_text name='Badge Text', description='Text to display for the most popular badge.'}
${menu name='Best Seller Badge (week)', icon='align-justify', description='Display a badge for products that are amongst N% of the best sellers on the site.'}
	${menu block->with_bestseller_badge_week name='Show Best Seller Badge (week)', description='Toggle the best seller badge display.'}
	${menu args->badge_if_more_sold_week name='Best Seller Badge Threshold', description='Badge appears if product is more sold than this percent of best seller products.', type='number'}
	${menu args->bestseller_badge_week_style name='Badge Style', description='CSS styling for the best seller badge.', type='css', param='with_responsive=1'}
	${menu args->bestseller_badge_week_text_style name='Badge Text Style', description='CSS styling for the best seller badge text.', type='css', param='with_responsive=1'}
	${menu args->bestseller_badge_week_text name='Badge Text', description='Text to display for the best seller badge.'}
${menu name='Best Seller Badge (1 day)', icon='align-justify', description='Display a badge for products that are amongst N% of the best sellers on the site.'}
	${menu block->with_bestseller_badge_1day name='Show Best Seller Badge (1 day)', description='Toggle the best seller badge display.'}
	${menu args->badge_if_more_sold_1day name='Best Seller Badge Threshold', description='Badge appears if product is more sold than this percent of best seller products.', type='number'}
	${menu args->bestseller_badge_1day_style name='Badge Style', description='CSS styling for the best seller badge.', type='css', param='with_responsive=1'}
	${menu args->bestseller_badge_1day_text_style name='Badge Text Style', description='CSS styling for the best seller badge text.', type='css', param='with_responsive=1'}
	${menu args->bestseller_badge_1day_text name='Badge Text', description='Text to display for the best seller badge.'}
${menu name='Discount Badge', icon='align-justify', description='Set up a badge to display discount information on products.'}
	${menu block->with_discount_badge name='Show Discount Badge', description='Toggle the discount badge display.'}
	${menu args->min_discount_percent name='Minimum Discount %', description='Badge shows if discount is at least this percentage.', type='number', param='min=1'}
	${menu args->discount_badge_style name='Badge Style', description='CSS styling for the discount badge.', type='css', param='with_responsive=1'}
	${menu args->discount_badge_text_style name='Badge Text Style', description='CSS styling for the discount badge text.', type='css', param='with_responsive=1'}
	${menu args->discount_badge_text name='Badge Text', description='Text to display on the discount badge.'}
${menu name='Price Drop Badge', icon='tag', description='Display a badge when there is a notable price drop.'}
	${menu block->with_price_drop_badge name='Show Price Drop Badge', description='Toggle the display of the price drop badge.'}
	${menu args->min_price_drop name='Minimum Price Drop %', description='Badge appears if the price drop is at least this percentage.', type='number', param='min=1'}
	${menu args->min_price_drop_days name='Price Drop Timeframe (Days)', description='Badge appears if the drop occurred within these days.', type='number', param='min=1'}
	${menu args->price_drop_badge_style name='Badge Style', description='CSS styling for the price drop badge.', type='css', param='with_responsive=1'}
	${menu args->price_drop_badge_text_style name='Badge Text Style', description='CSS styling for the price drop badge text.', type='css', param='with_responsive=1'}
	${menu args->text_price_drop name='Badge Text Template', description='Text template for price drop; use {P} for percent and {D} for days.'}
${menu name='New Badge', icon='align-justify', description='Display a badge for products that are new.'}
	${menu block->with_new_badge name='Show New Badge', description='Toggle the new badge display.'}
	${menu args->badge_if_newer name='New Badge Threshold', description='Badge appears if product is newer than this duration.', type='date', param='is_span=true', param='format=%0..999d days'}
	${menu args->new_badge_style name='Badge Style', description='CSS styling for the new badge.', type='css', param='with_responsive=1'}
	${menu args->new_badge_text_style name='Badge Text Style', description='CSS styling for the new badge text.', type='css', param='with_responsive=1'}
	${menu args->new_badge_text name='Badge Text', description='Text to display for the new badge.'}
${menu name='Time-based Badge', icon='align-justify', description='Configure a badge for time-sensitive offers.'}
	${menu block->with_time_badge name='Show Time-based Badge', description='Toggle the time-based badge display.'}
	${menu args->time_badge_style name='Badge Style', description='CSS styling for the time-based badge.', type='css', param='with_responsive=1'}
	${menu args->time_badge_text_style name='Badge Text Style', description='CSS styling for the badge text.', type='css', param='with_responsive=1'}
	${menu args->time_badge_text name='Badge Text', description='Text to display on the time-based badge.'}
	${menu p->custom_i_1 name='End Date Field', description='Catalog field with the offer end date (UNIX-timestamp).'}
	${menu block->with_time_badge_countdown name='Enable Countdown', description='Toggle a countdown timer for the time-based badge.'}
	${menu args->time_badge_days name='Days Label', description='Label for “days” in the countdown.'}
	${menu args->time_badge_hr name='Hours Label', description='Label for “hours” in the countdown.'}
	${menu args->time_badge_min name='Minutes Label', description='Label for “minutes” in the countdown.'}
	${menu args->time_badge_sec name='Seconds Label', description='Label for “seconds” in the countdown.'}
${menu name='Stock Badge', icon='align-justify', description='Display a badge when stock is low.'}
	${menu block->with_stock_badge name='Show Stock Badge', description='Toggle the low stock badge display.'}
	${menu args->badge_if_less_stock name='Stock Threshold', description='Badge appears if items in stock are below this number.', type='number', param='min=1'}
	${menu args->stock_badge_style name='Badge Style', description='CSS styling for the stock badge.', type='css', param='with_responsive=1'}
	${menu args->stock_badge_text_style name='Badge Text Style', description='CSS styling for the stock badge text.', type='css', param='with_responsive=1'}
	${menu args->stock_badge_text name='Badge Text', description='Text to display in the stock badge.'}
${menu name='Add to Wishlist', icon='bars', description='Enable and configure the wishlist functionality.'}
	${menu block->with_wishlist_badge name='Enable Wishlist', description='Toggle the “add to wishlist” icon.'}
	${menu args->wishlist_style name='Wishlist Icon Style', description='CSS styling for the wishlist icon.', type='css'}
	${menu args->wishlist_off_style name='Wishlist Off Tooltip Style', description='CSS styling for the tooltip when wishlist is inactive.', type='css'}
	${menu args->wishlist_add_text name='Add to Wishlist Tooltip', description='Tooltip text for adding an item to the wishlist.'}
	${menu args->wishlist_on_style name='Wishlist On Icon Style', description='CSS styling for the wishlist icon when active.', type='css'}
	${menu args->wishlist_rm_text name='Remove from Wishlist Tooltip', description='Tooltip text for removing an item from the wishlist.'}
${menu name='Icon or Text Badge', icon='star', description='Display additional data using an icon or text badge.'}
	${menu block->with_db_badge name='Enable DB Badge', description='Toggle display of the DB badge.'}
	${menu args->db_badge_style name='Badge Block Style', description='CSS styling for the badge container.', type='css'}
	${menu block->with_db_badge_icon name='Badge Icon', description='Include an icon in the DB badge.'}
	${menu args->db_badge_text_icon name='Badge Icon Option', description='Select the icon for the DB badge.', type='icon'}
	${menu args->db_badge_text name='Badge Text', description='Text to use for the DB badge.'}
	${menu args->db_badge_text_style name='Badge Text Style', description='CSS styling for the DB badge text.', type='css'}
${menu name='Options Link', icon='external-link', description='Configure the “see options” link for products.'}
	${menu block->with_options_link name='Enable Options Link', description='Toggle the display of the options link.'}
	${menu args->options_link_href name='Link URL', description='URL for the options link.'}
	${menu args->options_link_style name='Link Style', description='CSS styling for the options link.', type='css'}
	${menu args->options_link_text name='Link Text', description='Text to display for the options link.'}
${menu name='Custom Column', icon='database', description='Add a custom column with additional product data.'}
	${menu block->with_custom_column name='Enable Custom Column', description='Toggle the custom column display.'}
	${menu args->custom_column name='Column Data', description='Data field to display in the custom column.'}
	${menu args->custom_column_style name='Column Style', description='CSS styling for the custom column.', type='css'}
${menu name='Product Title', icon='align-justify', description='Display product titles.'}
	${menu block->with_title name='Enable Title', description='Toggle the display of product titles.'}
	${menu p->title name='Product Title Text', description='Product title from the feed.'}
	${menu args->title_max_lines name='Maximum Title Lines', description='Set the maximum number of lines for product titles.', type='number', param='min=1'}
${menu name='Product Text/Description', icon='align-justify', description='Display product descriptions or additional text.'}
	${menu block->description name='Enable Description', description='Toggle the product description display.'}
	${menu p->description name='Product Description Text', description='Product description from the feed.'}
	${menu args->a_css name='Description Text Style', description='CSS styling for the description text.', type='css', param='with_responsive=1'}
	${menu args->a_hover_color name='Text Hover Color', description='Color for the description text on hover.', type='color'}
	${menu args->a_css_3 name='Text Color', description='Primary color for the product description.', type='css', param='with_responsive=1'}
${menu name='Payments', icon='bars', description='Configure payment options and display text.'}
	${menu block->payment name='Enable Payments', description='Toggle the display of payment information.'}
	${menu args->payment_style name='Payment Style', description='CSS styling for payment information.', type='css'}
	${menu args->payment_min name='Minimum Order Amount', description='Set the minimum order amount for payment options.'}
	${menu args->payment_n name='Number of Payments', description='Set the number of interest-free payments available.'}
	${menu args->payment_text_yes name='Available Payments Text', description='Text to display when payments are available.'}
	${menu args->payment_text_no name='Unavailable Payments Text', description='Text to display when payments are unavailable.'}
	${menu args->payment_text_2 name='Payment Sub-Text', description='Additional text to display below payment options.'}
${menu name='Link Button', icon='mouse-pointer', description='Configure a button that links to more product details.'}
	${menu block->with_link_button name='Enable Link Button', description='Toggle the display of the link button.'}
	${menu args->link_button_href name='Button URL', description='URL the button should link to.'}
	${menu args->link_button_text name='Button Text', description='Text to display on the button.'}
	${menu args->link_button_box_style name='Button Box Style', description='CSS styling for the button container.', type='css', param='with_responsive=1'}
	${menu args->link_button_style name='Button Style', description='CSS styling for the button.', type='css', param='with_responsive=1'}
	${menu args->link_button_style_hover name='Button Hover Style', description='CSS styling for the button on hover.', type='css'}
${menu name='Quick Add to Cart Button', icon='cart-plus', description='Set up a button for quick add-to-cart functionality.'}
	${menu block->with_cart name='Enable Quick Add to Cart', description='Toggle the quick add-to-cart button.'}
	${menu args->button name='Button Text', description='Text displayed on the add-to-cart button.'}
	${menu args->button_icon name='Button Icon', description='Icon to display on the button.', type='icon'}
	${menu args->button_icon_style name='Button Icon Style', description='CSS styling for the button icon.', type='css'}
	${menu args->button_style name='Button Style', description='CSS styling for the add-to-cart button.', type='css', param='with_responsive=1'}
	${menu args->button_style_hover name='Button Hover Style', description='CSS styling for the add-to-cart button on hover.', type='css'}
	${menu block->animate_cart_button name='Animate Button on Hover', description='Enable a sliding animation for the button when hovered.'}
	${menu args->cart_is_code name='Trigger Integration Code', description='Run integration code when the button is clicked.', type='checkbox', param='value_off=', param='value_on=1'}
	${menu args->cart_arg name='Cart Argument', description='Optional argument to pass to the integration function.', visible_if='args.cart_is_code'}
	${menu args->cart_yes name='On Complete JavaScript', description='JavaScript code to execute when adding to cart succeeds.', type='source_javascript', visible_if='args.cart_is_code'}
	${menu args->cart_no name='On Error JavaScript', description='JavaScript code to execute when adding to cart fails.', type='source_javascript', visible_if='args.cart_is_code'}
${menu name='Onclick Target URL', icon='link', description='Set the target URL for product click actions.'}
	${menu p->cart_url name='Product Link URL', description='URL to open when a product is clicked.', column_tags='url, custom text'}
	${menu args->target name='Link Target', description='Select how the link is opened (e.g., in a new tab).', type='a_target'}
${menu name='Rating', icon='star', description='Configure product rating display.'}
	${menu block->rating name='Enable Rating', description='Toggle the display of product ratings.'}
	${menu p->rank name='Product Rating', description='Rating value from the product feed.'}
	${menu args->rating_style name='Rating Colors', description='Customize the color scheme for the rating display.', type='css', param='vars=--bgcolor:color; --border-color:color'}
	${menu args->n_reviews name='Number of Reviews', description='Display the number of reviews for the product.'}
	${menu args->n_reviews_style name='Reviews Style', description='CSS styling for the reviews text.', type='css'}
${menu name='Site Statistics: 1-day', icon='bar-chart', description='Display product views and purchases from the last 24 hours.'}
	${menu block->stats_1day name='Enable 1-day Statistics', description='Toggle the display of 1-day statistics.'}
	${menu args->hide_no_view_1day name='Minimum Views', description='Hide statistics if views are below this number.', type='number', param='min=0'}
	${menu args->hide_no_goal_1day name='Minimum Purchases', description='Hide statistics if purchases are below this number.', type='number', param='min=0'}
	${menu args->text_style_1day name='Statistics Text Style', description='CSS styling for the 1-day statistics text.', type='css'}
	${menu args->icon_n_viewed_1day name='Views Icon', description='Icon to represent the number of views.', type='icon'}
	${menu args->icon_style_n_viewed_1day name='Views Icon Style', description='CSS styling for the views icon.', type='css'}
	${menu args->n_viewed_1day name='Views Text', description='Template text for displaying view count.'}
	${menu args->icon_n_goal_1day name='Purchases Icon', description='Icon to represent product purchases.', type='icon'}
	${menu args->icon_style_n_goal_1day name='Purchases Icon Style', description='CSS styling for the purchases icon.', type='css'}
	${menu args->n_goal_1day name='Purchases Text', description='Template text for displaying purchase count.'}
${menu name='Site Statistics: Week', icon='bar-chart', description='Display product views and purchases from the past week.'}
	${menu block->stats_week name='Enable Weekly Statistics', description='Toggle the display of weekly statistics.'}
	${menu args->hide_no_view_week name='Minimum Weekly Views', description='Hide weekly stats if views are below this number.', type='number', param='min=0'}
	${menu args->hide_no_goal_week name='Minimum Weekly Purchases', description='Hide weekly stats if purchases are below this number.', type='number', param='min=0'}
	${menu args->text_style_week name='Weekly Statistics Text Style', description='CSS styling for the weekly statistics text.', type='css'}
	${menu args->icon_n_viewed_week name='Weekly Views Icon', description='Icon for weekly view count.', type='icon'}
	${menu args->icon_style_n_viewed_week name='Weekly Views Icon Style', description='CSS styling for the weekly views icon.', type='css'}
	${menu args->n_viewed_week name='Weekly Views Text', description='Template text for weekly view statistics.'}
	${menu args->icon_n_goal_week name='Weekly Purchases Icon', description='Icon for weekly purchase count.', type='icon'}
	${menu args->icon_style_n_goal_week name='Weekly Purchases Icon Style', description='CSS styling for the weekly purchases icon.', type='css'}
	${menu args->n_goal_week name='Weekly Purchases Text', description='Template text for weekly purchase statistics.'}
${menu name='Price', icon='dollar', description='Configure product pricing display options.'}
	${menu block->price name='Enable Price Display', description='Toggle the display of product prices.'}
	${menu args->price_style name='Price Style', description='CSS styling for the product price.', type='css', param='with_responsive=1'}
	${menu args->old_price_style name='Old Price Style', description='CSS styling for the pre-discount price.', type='css'}
	${menu args->old_price_before name='Old Price Prefix', description='Text to display before the old price.'}
	${menu args->p_price_before_discount name='Old Price Value', description='The product’s price before discount.'}
	${menu args->old_price_after name='Old Price Suffix', description='Text to display after the old price.'}
	${menu args->p_price_after_discount name='Discounted Price Value', description='The product’s price after discount.'}
	${menu args->new_price_style name='New Price Style', description='CSS styling for the discounted price.', type='css'}
	${menu args->sale_text_style name='Sale Text Style', description='CSS styling for the sale notification text.', type='css'}
	${menu args->sale_text name='Sale Text', description='Text to indicate a sale is active.'}
	${menu args->nosale_price_style name='Non-discount Price Style', description='CSS styling for prices when no discount is applied.', type='css'}
${menu name='Lines Scroller', icon='film', description='Display scrolling lines of product information.'}
	${menu block->with_sc name='Enable Scroller', description='Toggle the lines scroller display.'}
	${menu args->sc_style name='Scroller Style', description='CSS styling for the scroller.', type='css'}
	${menu args->sc_without_close name='Keep Scroller Open', description='Decide whether the scroller remains open after its animation.', type='checkbox', param='value_on=1', param='value_off='}
	${menu block->sc_with_views name='Include Views Data', description='Show view statistics within the scroller.'}
	${menu args->sc_min_views name='Minimum Views', description='Do not show view data if below this threshold.', type='number', param='min=0'}
	${menu args->sc_icon_views name='Views Icon', description='Icon representing the number of views.', type='icon'}
	${menu args->sc_icon_views_style name='Views Icon Style', description='CSS styling for the views icon.', type='css'}
	${menu args->sc_text_views name='Views Text', description='Text template for the views information.'}
	${menu block->sc_with_goals name='Include Purchases Data', description='Show purchase statistics within the scroller.'}
	${menu args->sc_min_goals name='Minimum Purchases', description='Do not show purchase data if below this threshold.', type='number', param='min=0'}
	${menu args->sc_icon_goals name='Purchases Icon', description='Icon representing the number of purchases.', type='icon'}
	${menu args->sc_icon_goals_style name='Purchases Icon Style', description='CSS styling for the purchases icon.', type='css'}
	${menu args->sc_text_goals name='Purchases Text', description='Text template for purchase information.'}
	${menu block->sc_with_inventory name='Include Inventory Data', description='Show remaining inventory information.'}
	${menu args->sc_min_inventory name='Inventory Threshold', description='Do not show inventory data if above this number.', type='number', param='min=0'}
	${menu args->sc_min_goals_for_inventory name='Minimum Purchases for Inventory', description='Display inventory only if the product has reached this number of purchases.', type='number', param='min=0'}
	${menu args->sc_icon_inventory name='Inventory Icon', description='Icon representing inventory levels.', type='icon'}
	${menu args->sc_icon_inventory_style name='Inventory Icon Style', description='CSS styling for the inventory icon.', type='css'}
	${menu args->sc_text_inventory name='Inventory Text', description='Text template for inventory information.'}
	${menu block->sc_with_price_drop name='Include Price Drop Data', description='Show information about price drops in the scroller.'}
	${menu args->sc_min_price_drop name='Minimum Price Drop %', description='Display price drop data if the drop is at least this percentage.', type='number', param='min=1'}
	${menu args->sc_min_price_drop_days name='Price Drop Timeframe', description='Display price drop data only if it occurred within these days.', type='number', param='min=1'}
	${menu args->sc_icon_price_drop name='Price Drop Icon', description='Icon for price drop information.', type='icon'}
	${menu args->sc_icon_price_drop_style name='Price Drop Icon Style', description='CSS styling for the price drop icon.', type='css'}
	${menu args->sc_text_price_drop name='Price Drop Text', description='Text template for price drop info (use {P} for percent and {D} for days).'}
	${menu block->sc_with_discount name='Include Discount Data', description='Show discount information in the scroller.'}
	${menu args->sc_min_discount name='Minimum Discount %', description='Display discount info if discount is at least this percentage.', type='number', param='min=1'}
	${menu args->sc_icon_discount name='Discount Icon', description='Icon for discount data.', type='icon'}
	${menu args->sc_icon_discount_style name='Discount Icon Style', description='CSS styling for the discount icon.', type='css'}
	${menu args->sc_text_discount name='Discount Text', description='Text template for discount data (use {P} for discount percentage).'}
	${menu block->sc_with_new name='Include New Product Data', description='Show a “new” indicator for recently added products.'}
	${menu args->sc_min_new_days name='New Product Threshold (Days)', description='Mark product as new if added within these days.', type='number', param='min=1'}
	${menu args->sc_icon_new name='New Product Icon', description='Icon for indicating new products.', type='icon'}
	${menu args->sc_icon_new_style name='New Product Icon Style', description='CSS styling for the new product icon.', type='css'}
	${menu args->sc_text_new name='New Badge Text', description='Text to display for new products (use {D} for days).'}
	${menu block->sc_with_free1 name='Include Free Text 1', description='Show additional free information text (line 1).'}
	${menu args->sc_icon_free1 name='Free Text 1 Icon', description='Icon for free text 1.', type='icon'}
	${menu args->sc_icon_free1_style name='Free Text 1 Icon Style', description='CSS styling for free text 1 icon.', type='css'}
	${menu args->sc_text_free1 name='Free Text 1', description='Content for free text line 1.'}
	${menu block->sc_with_free2 name='Include Free Text 2', description='Show additional free information text (line 2).'}
	${menu args->sc_icon_free2 name='Free Text 2 Icon', description='Icon for free text 2.', type='icon'}
	${menu args->sc_icon_free2_style name='Free Text 2 Icon Style', description='CSS styling for free text 2 icon.', type='css'}
	${menu args->sc_text_free2 name='Free Text 2', description='Content for free text line 2.'}
	${menu block->sc_with_free3 name='Include Free Text 3', description='Show additional free information text (line 3).'}
	${menu args->sc_icon_free3 name='Free Text 3 Icon', description='Icon for free text 3.', type='icon'}
	${menu args->sc_icon_free3_style name='Free Text 3 Icon Style', description='CSS styling for free text 3 icon.', type='css'}
	${menu args->sc_text_free3 name='Free Text 3', description='Content for free text line 3.'}
${menu name='Countdown', icon='clock-o', description='Configure a countdown timer for time-sensitive offers.'}
	${menu block->with_timer name='Enable Countdown', description='Toggle the countdown timer display.'}
	${menu args->value name='Countdown Type', description='Set the countdown timer parameters.', type='timer_custom_params'}
	${menu args->timersubstrate_style name='Countdown Substrate Style', description='CSS styling for the countdown substrate.', type='css', param='with_responsive=1'}
	${menu args->timer_background_style name='Countdown Background Style', description='CSS styling for the countdown background.', type='css', param='with_responsive=1'}
	${menu args->timer_box_style name='Countdown Box Style', description='CSS styling for the countdown container.', type='css', param='with_responsive=1'}
	${menu args->timer_caption_days name='Days Caption', description='Caption for “days” in the countdown.'}
	${menu args->timer_caption_hours name='Hours Caption', description='Caption for “hours” in the countdown.'}
	${menu args->timer_caption_minutes name='Minutes Caption', description='Caption for “minutes” in the countdown.'}
	${menu args->timer_caption_seconds name='Seconds Caption', description='Caption for “seconds” in the countdown.'}
	${menu args->timer_caption_style name='Countdown Caption Style', description='CSS styling for the countdown captions.', type='css', param='with_responsive=1'}
	${menu args->timer_number_style name='Countdown Number Style', description='CSS styling for the countdown numbers.', type='css', param='with_responsive=1'}
	${menu block->with_left_text name='Show Left Text', description='Toggle display of text to the left of the countdown.'}
	${menu args->left_text name='Left Text', description='Custom text to display on the left side of the countdown.'}
	${menu args->left_style name='Left Text Style', description='CSS styling for the left text.', type='css', param='with_responsive=1'}
	${menu block->with_right_button name='Show Right Button', description='Toggle display of a button to the right of the countdown.'}
	${menu args->right_button_text name='Right Button Text', description='Text to display on the countdown right button.'}
	${menu args->right_href name='Right Button URL', description='Target URL for the countdown right button.', type='a_attrs'}
	${menu args->right_button_style name='Right Button Style', description='CSS styling for the countdown right button.', type='css', param='with_responsive=1'}
```


