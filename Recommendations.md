## Paging recommendations

The recommended items are shown on screen corners

```
<div class="$responsive" style="width:100%; display:flex; justify-content:space-between; align-items:stretch; background-color:transparent; pointer-events:none">
	${foreach products as p where (p->image_big_url IS NOT NULL AND p->image_big_url!='') order by p->price limit 2}
		${if p->row_number = 1}
			<a id="trigger_${p->row_number:html}" href="${p->cart_url:html}" style="${args->a_style:html:default('text-decoration: none;
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

			<a id="trigger_${p->row_number:html}" href="${p->cart_url:html}" style="${args->a_style:html}; display:flex; pointer-events:all">
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
			<a href="${p->cart_url:html}" target="${args->target:html:default(_self)}" style="display:block; margin:auto; box-sizing:border-box">
				<img src="${p->image_big_url:html}" style="width:auto; height:auto; ${args->img_style:html:default('max-width: 100%;
max-height: 255px;
')}">
				${p->title}
			</a>
			${block->price:default(1)}
			<div data-style="margin:auto; box-sizing:border-box; width:${args->img_width:html}; ${args->price_style:html}">
                        ${if p->price_after_discount}
                            ${if p->price_after_discount and p->price_after_discount < p->price_before_discount}
                                ${args->price_with_discount:default('<span style="white-space:nowrap"><span style="font-size: 22px;
font-weight: 700; text-decoration: line-through">${p->price_before_discount:price('''')}</span> </span><span style="font-weight: 400; font-size: 16.8px;">$</span> <span style="white-space:nowrap"><span style="font-size: 22px;
font-weight: 700; color:red">${p->price_after_discount:price('''')} <span style="font-weight: 400; font-size: 16.8px;">$</span></span></span>
<div style="display:inline-block; font-size:50%; line-height:1"><span style="white-space:nowrap;font-weight: 400;font-size:80%;color:red">sale<br />
price</span></div>
')}
                            ${end}
                            ${if not p->price_after_discount or p->price_after_discount >= p->price_before_discount}
                                ${args->price_without_discount:default('<span style="font-size: 22px;
font-weight: 700; white-space:nowrap">${p->price_before_discount:price('''')} <span style="font-weight: 400; font-size: 16.8px;">$</span></span>')}
                            ${end}
                        ${end}
                    </div>
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
	${menu p->cart_url name='Link target URL', column_tags='url, custom text'}
${menu name='Description', icon='align-justify'}
	${menu block->description name='With description'}
	${menu p->description name='Description text'}
	${menu args->a_css_3 name='Description color', type='css'}
${menu name='Price', icon='dollar'}
	${menu block->price name='With price'}
	${menu args->price_with_discount name='Price with discount'}
	${menu args->price_without_discount name='Price without discount'}
	${menu args->price_style name='Price style', type='css'}
```


## Horizontal display



```
<div class="$responsive" style="${args->a_style3:html:default('color: #444;
font-family: arial,sans-serif;
font-size: 12px;
line-height: 18px;
max-width: 450px;')}">
	<style>
		.st-ce-a > .st-ce-ov
		{	position: absolute;
			top: 0;
			left: 0;
			width: 100%;
			height: 100%;
			z-index: 1;
			display: flex;
			flex-direction: column;
			justify-content: center;
			align-items: stretch;
			opacity: 0;
			transition: opacity ease 0.4s;
		}
		.st-ce-a:hover > .st-ce-ov
		{	opacity: 1;
		}
	</style>
	<div style="${args->a_style:html:default('font-size: 15px;
text-align: left;
padding-top: 5px;
padding-right: 0;
padding-bottom: 5px;
padding-left: 15px;
')}">
		${args->line:default('<div style="text-align: center;"><strong>Popular Items</strong></div>
')}
	</div>
	<div style="display:flex; flex-wrap:wrap; justify-content:space-between; align-items:stretch">
		${foreach recom_products as p limit 6}
			<div class="st-ce-a" data-personyze-click-target="products ${p->internal_id:html}" onclick="for (let e=event.target; e &amp;&amp; e!=this; e=e.parentNode) if (e.nodeName == 'A') return; var a=_S_T.new_elem('a', this, {href: ${p->cart_url:json:html}, target: ${args->target:json:html:default(_blank)}, style: 'position:absolute; visibility:hidden'}); a.click(); setTimeout(function() {a.parentNode.removeChild(a)}, 100)" style="display:block; position:relative; overflow:hidden; cursor:pointer; ${args->a_style4:html:default('margin-top: 0px;
margin-right: 21px;
margin-bottom: 20px;
margin-left: 21px;
border: none;
background-color: white;
text-align: center;
width: 180px;
box-shadow: 0px 0px 20px rgba(0, 0, 0, 0.09);
text-decoration: none;')}">
				${block->with_overlay:default(0)}
				<div class="st-ce-ov" style="${args->overlay_style:html:default('background-color: rgba(0, 0, 0, 0.68);
color: white;
')}">
					${args->hover_overlay_text}

					${block->with_hover_overlay_a}
					<div style="${args->hover_overlay_a_block_style:html:default('text-align: center;
margin-top: 25px;
margin-right: 0px;
margin-bottom: 0px;
margin-left: 0px;
')}">
						<a class="$flat_btn" href="${args->hover_overlay_a_href:html:default('${p->cart_url}')}" data-style="box-sizing:border-box; ${args->hover_overlay_a_style:html:default('align-items: center;
justify-content: center;
border: 1px solid;
padding-top: 13px;
padding-right: 20px;
padding-bottom: 13px;
padding-left: 20px;
text-align: center;
line-height: 1.2;
font-family: ''cerapro-regular'', Futura, sans-serif;
font-style: normal;
font-size: 14px;
text-transform: uppercase;
letter-spacing: 1px;
cursor: pointer;
transition: all 0.2s linear;
border-color: var(--button-color-border, #303619);
background: var(--button-color-background, #303619);
color: #393838;
background-color: rgba(245, 36, 36, 0);
font-weight: 300;
')}" hover_style="${args->hover_overlay_a_style_hover:html:default('color: rgb(251, 250, 250);
background-color: #393838;
')}">
							${args->hover_overlay_a_text:default(Quick view)}
						</a>
					</div>

					${block->with_hover_overlay_a2}
					<div style="${args->hover_overlay_a2_block_style:html:default('text-align: center;
')}">
						<a class="$flat_btn" data-personyze-click-target="products ${p->internal_id:html}" href="${args->hover_overlay_a2_href:html:default('${p->cart_url}')}" data-style="box-sizing:border-box; ${args->hover_overlay_a2_style:html:default('align-items: center;
justify-content: center;
border: 1px solid;
padding-top: 13px;
padding-right: 20px;
padding-bottom: 13px;
padding-left: 20px;
text-align: center;
line-height: 1.2;
font-family: ''cerapro-regular'', Futura, sans-serif;
font-style: normal;
font-size: 14px;
text-transform: uppercase;
letter-spacing: 1px;
cursor: pointer;
transition: all 0.2s linear;
border-color: var(--button-color-border, #303619);
background: var(--button-color-background, #303619);
color: #393838;
background-color: rgba(245, 36, 36, 0);
font-weight: 300;
')}" hover_style="${args->hover_overlay_a_style_hover:html}">
							${args->hover_overlay_a2_text:default(Choose options)}
						</a>
					</div>

					${block->with_cart_2}
					<div>
						<a
							data-personyze-click-target="products ${p->internal_id:html}"
							class="$flat_btn $button_add_to_cart"
							data-is_code="${args->cart_is_code:html:default(1)}"
							data-action_id="${action_id:html}"
							data-url="${p->cart_url:html}"
							data-json-add_to_cart_columns="${p->add_to_cart_columns:html}"
							data-arg="${args->cart_arg:html}"
							data-yes="${args->cart_yes:html}"
							data-no="${args->cart_no:html}"
							data-style="box-sizing:border-box; ${args->hover_overlay_a2_style:html}" hover_style="${args->hover_overlay_a_style_hover:html}">
							<hr class="$icon ${args->button_icon:html}" style="${args->button_icon_style:html:default('padding-right: 0.5em;
font-size: 100%;
color: inherit;
')}">
							${args->button:default(Quick View)}
						</a>
					</div>
				</div>

				<div style="margin-bottom:4em; ${args->a_style40:html:default('padding:10px 15px
')}">
					<img src="${p->image_big_url:html:default('p->image_big_url')}" alt="${p->title:html}" title="${p->title:html}" style="width:auto; height:auto; ${args->a_style7:html:default('max-height: 100px;
margin-bottom: 10px;
border: none;
max-width: 100px;
height: auto;
width: auto;')}">
					<div style="${args->a_style5:html:default('color: #b72913;
font-size: 14px;
font-weight: bold;
text-align: center;')}">
						${p->title}
					</div>

					${block->rating:default(1)}
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
										${args->old_price_before}${args->p_price_before_discount:default('$${p->price_before_discount:price('''')}')}${args->old_price_after}
									</span>
								</span>
								<span style="white-space:nowrap">
									<span style="${args->new_price_style:html:default('font-size: 17px;
font-weight: 500;
color: black;
')}">
										${args->old_price_before)}${args->p_price_after_discount:default('$${p->price_after_discount:price('''')}')}${args->old_price_after}
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
				</div>

				${block->with_button:default(1)}
				<div style="position:absolute; width:100%; bottom:10px; text-align:center">
					<div style="display:inline-block; ${args->a_style6:html:default('background-color: #006ecc;
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
-webkit-appearance: none;
')}">
						${args->line3:default(View Now)}
					</div>
				</div>
			</div>
		${end}
	</div>
</div>

${menu name='Box', icon='th-large'}
	${menu args->a_style3 name='Style', type='css'}
${menu name='Hover overlay', icon='bars'}
	${menu block->with_overlay name='With hover overlay'}
	${menu args->overlay_style name='Style', type='css'}
	${menu args->hover_overlay_text name='Text'}
	${menu block->with_hover_overlay_a name='With link 1'}
	${menu args->hover_overlay_a_block_style name='Link 1 block style', type='css'}
	${menu args->hover_overlay_a_text name='Link 1 text'}
	${menu args->hover_overlay_a_href name='Link 1 URL'}
	${menu args->hover_overlay_a_style name='Link 1 style', type='css'}
	${menu args->hover_overlay_a_style_hover name='Link 1 hover style', type='css'}
	${menu block->with_hover_overlay_a2 name='With link 2'}
	${menu args->hover_overlay_a2_block_style name='Link 2 block style', type='css'}
	${menu args->hover_overlay_a2_text name='Link 2 text'}
	${menu args->hover_overlay_a2_href name='Link 2 URL'}
	${menu args->hover_overlay_a2_style name='Link 2 style', type='css'}
	${menu block->with_cart_2 name='With add to cart (over image)'}
	${menu args->button name='Text'}
	${menu args->button_icon name='Icon on button', type='icon'}
	${menu args->button_icon_style name='Icon on button style', type='css'}
	${menu args->cart_is_code name='Button triggers "Add to cart" integration code', type='checkbox', param='value_off=', param='value_on=1'}
	${menu args->cart_arg name='Argument to pass to your defined Add to Cart function (optional)', visible_if='args.cart_is_code'}
	${menu args->cart_yes name='Javascript on complete (optional)', type='source_javascript', visible_if='args.cart_is_code'}
	${menu args->cart_no name='Javascript on error (optional)', type='source_javascript', visible_if='args.cart_is_code'}
${menu name='Onclick target URL', icon='link'}
	${menu p->cart_url name='Link target URL', column_tags='url, custom text'}
	${menu args->target name='Open link in', type='a_target'}
${menu name='Cell', icon='bars'}
	${menu args->a_style5 name='Product name', type='css'}
	${menu args->a_style7 name='Product image style', type='css'}
	${menu args->a_style4 name='Cell', type='css'}
	${menu args->a_style40 name='Cell', type='css'}
${menu name='Title', icon='bookmark'}
	${menu args->a_style name='Style', type='css'}
	${menu args->line name='Text'}
${menu name='Rating', icon='star', description='Show product rating when available
	This requires you to populate "Rank" on your product feed   .'}
	${menu block->rating name='With rating'}
	${menu p->rank name='Rating'}
	${menu args->rating_style name='Colors', type='css', param='vars=--bgcolor:color; --border-color:color'}
	${menu args->n_reviews name='No. of reviews'}
	${menu args->n_reviews_style name='No. of reviews style', type='css'}
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
${menu name='Button', icon='bars'}
	${menu block->with_button name='With button'}
	${menu args->line3 name='Text'}
	${menu args->a_style6 name='Style', type='css'}
```


## Side bar expendable



```
<div class="$responsive" style="${args->a_style3:html:default('max-width: 250px;
color: #444;
font-family: arial,sans-serif;
font-size: 12px;
line-height: 18px;'):input_type(css):arg_name(Style):arg_section(0, 0, 'Box', 'th-large')}">
	<div style="${args->a_style:html:default('color: #FFF;
font-size: 15px;
text-align: center;
padding-top: 5px;
padding-right: 0;
padding-bottom: 5px;
padding-left: 0;
background: rgb(0, 106, 254);
border-top-left-radius: 0px;
border-top-right-radius: 0px;
border-bottom-right-radius: 0;
border-bottom-left-radius: 0;
margin-top: 15px;
margin-right: 0px;
margin-bottom: 10px;
margin-left: 0px;'):input_type(css):arg_name(Background Color):arg_section(1, 0, 'Title', 'bookmark')}">
		${args->line:default('<span style="color: #FFF;
display: block;
font-size: 15px;
text-align: center;
text-decoration: none;"><strong>RECOMMENDED FOR YOU</strong></span>'):arg_name(Text):arg_section(1, 1, 'Title', 'bookmark')}
	</div>
	<div style="${args->a_style2:html:default('		padding-top: 5px;
		border-bottom-right-radius: 8px;
		border-bottom-left-radius: 8px;
		border-bottom: 1px solid #c1c1c1;
		border-left: 1px solid #c1c1c1;
		border-right: 1px solid #c1c1c1;
		padding: 7px 0 12px 4px;
	'):input_type(css):arg_name(Border):arg_section(0, 1, 'Box', 'th-large')}" data-n="${args->n:html:default(3):input_type(number):input_props('min=1'):arg_name(Initially visible):arg_section(4, 0, 'See More Button', 'eye')}" ontplready="var n=this.getAttribute('data-n'), c=this.children, l=c.length-1; if (l>n) {c[l].style.display=''; while (n!=l) c[n++].style.display='none'}">
		${foreach recom_products as p limit 15}
			<div style="${args->a_style4:html:default('				margin: 0 auto 8px;
				width: 95%;
				border-bottom: 1px solid #eee;
			'):input_type(css):arg_name(Cell):arg_section(2, 4, 'Cell', 'bars')}">
				<div style="${args->a_style5:html:default('					    float: left;
						width: 90px;
						text-align: left;
						font-weight: bold;
						font-size: 12px;
'):input_type(css):arg_name(Product name):arg_section(2, 0, 'Cell', 'bars')}">
					<span ontplready="var t=this.textContent,i=t.indexOf(','); if (i!=-1) this.textContent=t.substr(0,i)">${p->title}</span>
					${if p->sale_price > 0 and p->sale_price < p->price}
						<div style="${args->a_style50:html:default('							color: #9c223f;
							font-size: 11px;
						'):input_type(css):arg_name(Product name):arg_section(2, 1, 'Cell', 'bars')}">
							${args->line2:default(20% Off Each!):arg_name(Discount text):arg_section(2, 2, 'Cell', 'bars')}
						</div>
					${end}
				</div>
				<img src="${p->image_big_url:html:default('p->image_medium_url')}" alt="${p->title:html}" title="${p->title:html}" style="${args->a_style7:html:default('					    height: 87px;
					    width: 87px;
					    float: right;
					    margin-bottom: 10px;
					    border: none;
				'):input_type(css):arg_name(Product image style):arg_section(2, 3, 'Cell', 'bars')}">
				<a data-personyze-click-target="products ${p->internal_id:html}" href="${p->cart_url:html:default('p->cart_url')}" title="${args->line3:html:default(Add to Cart):arg_name(Tooltip):arg_section(3, 2, 'Button', 'bars')}" style="${args->a_style6:html:default('background-color: rgb(0, 106, 254);
border-bottom: 1px solid #b4a600;
border-left: 1px solid rgb(0, 106, 254);
border-right: 1px solid #d5c614;
border-top: 1px solid rgb(0, 106, 254);
color: white;
font-size: 14px;
padding-top: 5px;
padding-right: 20px;
padding-bottom: 5px;
padding-left: 20px;
-webkit-appearance: none;
text-decoration: none;
clear: both;
display: block;
width: 56px;
margin-top: 10px;
margin-right: auto;
margin-bottom: 10px;
margin-left: auto;
white-space: nowrap;'):input_type(css):arg_name(Style):arg_section(3, 1, 'Button', 'bars')}">
					${args->line3:default(Buy Now):arg_name(Text):arg_section(3, 0, 'Button', 'bars')}
				</a>
			</div>
		${end}
		<div style="display:none; text-align:center">
			<a href="javascript:" onclick="var c=this.parentNode.parentNode.children, i=0; while (c[i]) c[i++].style.display=''; c[--i].style.display='none'" style="${args->a_style9:html:default('font-size: 120%;
color: #005274;
text-decoration: none;'):input_type(css):arg_name(Style):arg_section(4, 2, 'See More Button', 'eye')}">
				${args->seemore:default(See More):arg_name(Text):arg_section(4, 1, 'See More Button', 'eye')}
			</a>
		</div>
	</div>
</div>
```


## Category view



```
<div class="$responsive" data-style="box-sizing:border-box; background-color:${args->bg:html:default('rgba(0, 0, 0, 0)')}; ${args->style:html:default('max-width: none;
border: none;
line-height: 1.42857143;
color: black;
font-family: ProximaNova-Regular, "Helvetica Neue", Helvetica, Arial, sans-serif;
font-weight: 500;
margin-top: 20px;
margin-right: auto;
margin-bottom: 0;
margin-left: auto;
height: auto;
display: inline-block;
width: auto;
min-width: 100%;
')}">
	${block->title:default(1)}
	<div data-style="${args->title_style:html:default('padding-top: 1px;
padding-right: 1px;
padding-bottom: 1px;
padding-left: 0px;
font-family: ProximaNova-Regular, "Helvetica Neue", Helvetica, Arial, sans-serif;
font-size: 18px;
font-weight: 400;
text-align: left;
line-height: 35px;
letter-spacing: 2px;
text-transform: uppercase;
')}">
		${block->x:default(0)}
		<div style="float:right; cursor:pointer; margin:0 0 .3em .3em">
			${args->x}
		</div>
		${args->title:default(RECOMMENDED)}
		<div style="clear:both"></div>
	</div>
	<div style="display:flex; flex-flow:row; flex-wrap:wrap; justify-content:center">
		${foreach sum_products as p where p->for_period='recently' order by p->n_viewed desc limit 12}
			<div style="box-sizing:border-box; width:${args->cell_width:html:default(47vw)}; max-width:${args->cell_max_width:html:default(300px)}">
				<div data-style="display:flex; align-items:center; ${args->a_style:html:default('font-size: 11px;
margin-top: 5px;
margin-right: auto;
margin-bottom: 5px;
margin-left: auto;
width: auto;
height: auto;
justify-content: center;
text-align: center;
min-width: 0;
')}" onmouseenter="this._s=this.style.cssText; this.style.cssText+=';'+this.dataset.hoverStyle; var i=this.getElementsByTagName('img'); if (i[1]) {i[0].style.opacity=0; i[1].style.opacity=1}" onmouseleave="if (this._s) this.style.cssText=this._s; var i=this.getElementsByTagName('a')[0].getElementsByTagName('img'); if (i[1]) {i[0].style.opacity=1; i[1].style.opacity=0}" data-hover-style="${args->a_hover_style:html:default('box-shadow: 0 0 10px #888;
width: auto;
height: auto;
text-overflow: inherit;
')}">
					<a data-personyze-click-target="products ${p->internal_id:html}" href="${p->cart_url:html}" data-style="color:inherit; text-decoration:none; text-align:center; padding:${args->a_padding:html:default(0px)}">
						${block->with_img:default(1)}
						<div style="position:relative; display:inline-block">
							<img src="${p->image_big_url:html}" data-style="width:auto; height:auto; ${args->img_style:html:default('width: 165px;
')}; opacity:1; transition:opacity ease 0.4s">
							${if p->image_medium_url != ''}
								${block->with_2_img:default(1)}
								<div style="position:absolute; left:0; top:0; width:100%; height:100%; display:flex; justify-content:center; align-items:center">
									<img src="${p->image_big_url:html}" style="width:auto; height:auto; max-width:100%; max-height:100%; opacity:0; border-radius:4px; transition:opacity ease 0.4s">
								</div>
							${end}
						</div>

						<div data-style="${args->title_style2:html:default('width: 90%;
height: auto;
font-family: ProximaNova-Regular, "Helvetica Neue", Helvetica, Arial, sans-serif;
text-align: center;
margin: auto;
')}">
							${args->p_title:default('${p->title}')}
						</div>

						${if p->price_after_discount or p->price_before_discount}
							${args->before_price}
							${if p->price_after_discount = p->price_before_discount}
								${args->p_price_after_discount}
							${end}
							${if p->price_after_discount != p->price_before_discount}
								${args->p_price_after_discount}
								<span style="${args->sale_style:html:default('color: gray;
text-decoration: line-through;
font-size: 85%;
')}">
									${args->p_price_before_discount}
								</span>
							${end}
							${args->after_price}
						${end}

						${block->with_info1:default(0)}
						<span data-style="${args->info1_style:html}">
							${p->custom_3:sprintf('%s')}
						</span>
						${block->with_info2:default(0)}
						<span data-style="${args->info2_style:html}">
							${p->custom_2:sprintf('| %s miles')}
						</span>

						${block->rating:default(0)}
						<div data-style="${args->rating_style:html}">
							<input class="$rating" value="${p->custom_1:html:default(0)}" max="${args->rank_max:html:default(5)}" style="background-color:${args->bg:html}">
						</div>
						${block->rating_text:default(0)}
						<div data-style="${args->rating_text_style:html}">
							${p->custom_1:html:default(0)}
							${args->of}
							${args->rank_max:html}

							${block->rating_votes}
							<span>
								${args->votes_before}${p->custom_i_1:html:default(0)}${args->votes_after}
							</span>
						</div>
					</a>
					${block->with_arrow:default(0)}
					<div style="padding:${args->a_padding:html}; padding-left:0; padding-top:0; padding-bottom:0; text-align:right; ${args->arrow_style:html:default('width: auto;
')}">
						>
					</div>
				</div>
			</div>
		${end}
	</div>
</div>

${menu name='Frame', icon='th-large'}
	${menu args->bg name='Background color', type='color'}
	${menu args->style name='Style', type='css', param='with_responsive=1'}
	${menu args->cell_width name='Cell width', type='css_length', param='with_responsive=1'}
	${menu args->cell_max_width name='Cell max width', type='css_length', param='with_responsive=1'}
${menu name='Title', icon='bookmark'}
	${menu block->title name='With title bar'}
	${menu args->title name='Text'}
	${menu args->title_style name='Style', type='css', param='with_responsive=1'}
${menu name='Close button', icon='close'}
	${menu block->x name='With close button'}
	${menu args->x name='Close button', type='dontshowagain'}
${menu name='Cell', icon='bars'}
	${menu args->p_title name='Item text'}
	${menu args->title_style2 name='Title style', type='css', param='with_responsive=1'}
	${menu args->a_style name='Cell style', type='css', param='with_responsive=1'}
	${menu args->a_hover_style name='Style', type='css'}
	${menu block->with_arrow name='With arrow'}
	${menu args->a_padding name='Padding', type='css_length', param='with_responsive=1'}
	${menu args->arrow_style name='Style', type='css', param='with_responsive=1'}
	${menu args->before_price name='Text before price'}
	${menu args->after_price name='Text after price'}
	${menu args->p_price_after_discount name='Price after discount'}
	${menu args->p_price_before_discount name='Price before discount'}
	${menu args->sale_style name='Price before discount: style', type='css'}
${menu name='Product info near price', icon='info'}
	${menu block->with_info1 name='With Product info 1'}
	${menu p->custom_3:sprintf('%s') name='Product info 1'}
	${menu args->info1_style name='Product info 1 style', type='css', param='with_responsive=1'}
	${menu block->with_info2 name='With Product info 2'}
	${menu p->custom_2:sprintf('| %s miles') name='Product info 2'}
	${menu args->info2_style name='Product info 2 style', type='css', param='with_responsive=1'}
${menu name='Rating', icon='star-half-empty'}
	${menu block->rating name='With rating'}
	${menu p->custom_1 name='Rating'}
	${menu args->of name='Of'}
	${menu args->rank_max name='Maximum rating number that corresponds to 100%', type='number'}
	${menu args->rating_style name='Rating style', type='css', param='with_responsive=1'}
	${menu block->rating_text name='With rating text'}
	${menu args->rating_text_style name='Rating text style', type='css', param='with_responsive=1'}
	${menu block->rating_votes name='With no. of votes'}
	${menu args->votes_before name='No. of votes: text before'}
	${menu p->custom_i_1 name='No. of votes'}
	${menu args->votes_after name='No. of votes: text after'}
${menu name='Picture', icon='image'}
	${menu block->with_img name='With Picture'}
	${menu p->image_big_url name='Data source'}
	${menu args->img_style name='Picture style', type='css', param='with_responsive=1'}
	${menu block->with_2_img name='With 2 Pictures'}
```


## Recommended for you with title

Recommended for you with title

```
<div class="$responsive" data-style="display:inline-block; ${args->style:html:default('color:black; background-color:white; border:none'):input_type(css):input_props(with_responsive=1):arg_name(Style):arg_section(0, 1, 'Frame', 'th-large')}">
	${block->title:default(1):arg_name(With title bar):arg_section(3, 0, 'Title', 'bookmark')}
	<table data-style="width:100%; border-collapse:collapse; border:none; ${args->title_bg:html:default('background-color: white;'):input_type(css):input_props(with_responsive=1):arg_name(Style):arg_section(3, 2, 'Title', 'bookmark')}">
		<tr>
			<td data-style="vertical-align:middle; ${args->title_style:html:default('color: black;
font-size: sel(24px, 4vw);
font-weight: bold;
text-align: center;
padding: 0.2em;
(custom): margin-bottom: 4px; font-family: "Cantata One"; font-weight: normal; color: #c9a978; font-size: 25px; line-height: 1.25em; vertical-align: top; border-bottom: solid 2px #d02c30; padding-bottom: 10px; margin-top: 12px;'):input_type(css):input_props(with_responsive=1):arg_name(Title style):arg_section(3, 3, 'Title', 'bookmark')}">
				${args->title:default(Recommended to you):arg_name(Text):arg_section(3, 1, 'Title', 'bookmark')}
			</td>
			${block->with_arrows:default(1):arg_name(With arrow buttons):arg_section(4, 0, 'With slider arrows', 'arrows-h')}
			<td style="width:1px; white-space:nowrap; vertical-align:middle">
				<a id="button_back" class="$flat_btn" style="${args->btn_style:html:default('color:black; background-color:#F5F5F5'):input_type(css):arg_name(Arrow button style):arg_section(4, 1, 'With slider arrows', 'arrows-h')}" hover_style="${args->btn_hover_style:html:default('color:white; background-color:#E5007F'):input_type(css):arg_name('Arrow button style: hover'):arg_section(4, 2, 'With slider arrows', 'arrows-h')}"><</a>
				<a id="button_forward" class="$flat_btn" style="${args->btn_style:html:default('color:black; background-color:#F5F5F5'):input_type(css):arg_name(Arrow button style):arg_section(4, 1, 'With slider arrows', 'arrows-h')}" hover_style="${args->btn_hover_style:html:default('color:white; background-color:#E5007F'):input_type(css):arg_name('Arrow button style: hover'):arg_section(4, 2, 'With slider arrows', 'arrows-h')}">></a>
			</td>
			${block->x:default(0):arg_name(With close button):arg_section(5, 0, 'Close button', 'close')}
			<td style="width:1px; white-space:nowrap; ${args->x_style:html:input_type(css):arg_name(Close button position):arg_section(5, 2, 'Close button', 'close')}">
				${args->x:input_type(dontshowagain):input_props(style=cursor:pointer; vertical-align:middle):arg_name(Close button):arg_section(5, 1, 'Close button', 'close')}
			</td>
		</tr>
	</table>
	<table style="width:100%; border-collapse:collapse; border:none">
		<tr class="$table_slider" data-disabled="${args->with_slider:html:input_type(checkbox):input_props(value_off=1,value_on=):arg_name(Use slider widget):arg_section(1, 0, 'With slider', 'arrow-right'):onchange('block.with_arrows=args.with_slider!=1')}" style="border:none; max-width:${args->width:html:default(650px):input_type(css_length):input_props(with_options=none):arg_name(Widget maximum width):arg_section(0, 0, 'Frame', 'th-large')}" for_max_vw="${args->for_max_vw:html:default(650px):input_type(css_length):input_props(with_options=always):arg_name(Slider widget only if screen width is less than or equal to):arg_section(1, 1, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" eq_cell_width="${args->eq_cell_width:html:default(1):input_type(checkbox):input_props(value_off=,value_on=1):arg_name(Equal cell width):arg_section(0, 2, 'Frame', 'th-large')}" eq_cell_height="${args->eq_cell_height:html:default(1):input_type(checkbox):input_props(value_off=,value_on=1):arg_name(Equal rows height):arg_section(0, 3, 'Frame', 'th-large')}" arrow_back_img="${args->arrow_back_img:html:default('//counter.emarketer.com/images/icon_square_arrow_left.png'):input_type(emarketer_media_url):arg_name(Left arrow image):arg_section(1, 2, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" arrow_forward_img="${args->arrow_forward_img:html:default('//counter.emarketer.com/images/icon_square_arrow_right.png'):input_type(emarketer_media_url):arg_name(Right arrow image):arg_section(1, 3, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" arrow_back_id="button_back" arrow_forward_id="button_forward">
			${foreach sum_interested_products_week as p order by p->n_viewed desc limit 4}
				<td data-style="${args->td_style:html:default('text-align: center;
vertical-align: middle;
padding: 5px;
border: none;
max-width: 250px;
min-width: 150px;'):input_type(css):input_props(with_responsive=1):arg_name(Cell style):arg_section(0, 4, 'Frame', 'th-large')}">
					<a data-emarketer-click-target="products ${p->internal_id:html}" href="${p->guide_url:html:arg_name(Link target URL):arg_section(8, 0, 'Link target URL', 'link'):column_tags('url','custom text')}" target="${args->target:html:default(_blank):input_type(a_target):arg_name(Open link in):arg_section(8, 1, 'Link target URL', 'link')}" style="${args->link_style:html:default('color:'):input_type(css):arg_name(Link style):arg_section(7, 2, 'Product name', 'text-height')}">
						<img src="${p->image_big_url:html:arg_name(Item image):arg_section(6, 0, 'Image', 'image'):column_tags(image)}" data-style="${args->img_style:html:default('border:double white 5px; width:sel(130px, 20vw); height:sel(130px, 20vw)'):input_type(css):input_props(with_responsive=1):arg_name(Item image style):arg_section(6, 1, 'Image', 'image')}" onerror="this.parentNode.parentNode.style.display='none'">
					</a>
					${block->p_title:default(1):arg_name(With product name):arg_section(7, 0, 'Product name', 'text-height')}
					<a data-emarketer-click-target="products ${p->internal_id:html}" href="${p->guide_url:html:arg_name(Link target URL):arg_section(8, 0, 'Link target URL', 'link'):column_tags('url','custom text')}" target="${args->target:html:default(_blank):input_type(a_target):arg_name(Open link in):arg_section(8, 1, 'Link target URL', 'link')}" style="${args->link_style:html:default('color:'):input_type(css):arg_name(Link style):arg_section(7, 2, 'Product name', 'text-height')}">
						<div>${p->title:arg_name(Product name):arg_section(7, 1, 'Product name', 'text-height')}</div>
					</a>
					${block->n_viewed:default(0):arg_name(With site statistics):arg_section(9, 0, 'Site statistics', 'bar-chart')}
					<div>${args->n_viewed_text:arg_name(Text):arg_section(9, 1, 'Site statistics', 'bar-chart')} ${foreach sum_products_all as s where s->internal_id = p->internal_id limit 1}${s->n_viewed:arg_name(Number):arg_section(9, 2, 'Site statistics', 'bar-chart')}${end}</div>
					<div style="margin-top:0.4em">
						${block->price:default(1):arg_name(With price):arg_section(10, 0, 'Second line', 'text-height'):onchange('args.rating_style = block.price ? ''float:right'' : '''';')}
						<div style="${args->price_style:html:input_type(css):arg_name(Price position):arg_section(10, 4, 'Second line', 'text-height')}">
							${if p->price}
								${args->before_price:arg_name(Text before price):arg_section(10, 1, 'Second line', 'text-height')}
								${if p->sale_price}
									${p->sale_price:truncate(2):sprintf($%s):arg_name(Price):arg_section(10, 2, 'Second line', 'text-height')}
									<div style="${args->sale_style:html:default('color:gray; text-decoration:line-through; font-size:85%'):input_type(css):input_props(with_responsive=1):arg_name('Price before discount: style'):arg_section(10, 6, 'Second line', 'text-height')}">
										${p->price:truncate(2):sprintf($%s):arg_name(Price):arg_section(10, 5, 'Second line', 'text-height')}
									</div>
								${end}
								${if not p->sale_price}
									${p->price:truncate(2):sprintf($%s):arg_name(Price):arg_section(10, 5, 'Second line', 'text-height')}
								${end}
								${args->after_price:arg_name(Text after price):arg_section(10, 3, 'Second line', 'text-height')}
							${end}
						</div>
						${block->rating:default(0):arg_name(With rating):arg_section(10, 7, 'Second line', 'text-height'):onchange('args.price_style = block.rating ? ''float:left'' : '''';')}
						<div style="${args->rating_style:html:input_type(css):arg_name(Rating position):arg_section(10, 10, 'Second line', 'text-height')}">
							<input class="$rating" value="${p->rank:html:arg_name(Rating):arg_section(10, 8, 'Second line', 'text-height')}" max="${args->rank_max:html:input_type(number):arg_name(Maximum rating number that corresponds to 100%):arg_section(10, 9, 'Second line', 'text-height')}">
						</div>
						<div style="clear:both"></div>
					</div>
					${block->button:default(1):arg_name(With button):arg_section(2, 0, 'Add to cart button', 'plus-square')}
					<div style="margin-top:0.4em">
						<a data-emarketer-click-target="products ${p->internal_id:html}" href="${p->cart_url:html:arg_name(Link target URL):arg_section(2, 2, 'Add to cart button', 'plus-square'):column_tags('url','custom text')}" data-style="${args->button_style:html:default('display: inline-block;
background-color: rgb(88, 107, 61);
border-radius: 5px;
padding-top: 6px;
padding-right: 9px;
padding-bottom: 6px;
padding-left: 9px;
color: white;
text-decoration: none;'):input_type(css):input_props(with_responsive=1):arg_name(Button style):arg_section(2, 3, 'Add to cart button', 'plus-square')}">${args->button:default(Add to cart):arg_name('Text', 'Link target URL'):arg_section(2, 1, 'Add to cart button', 'plus-square')}</a>
					</div>
				</td>
			${end}
		</tr>
	</table>
</div>
```


## Recommendation slider vertical

Recommendation slider vertical

```
<div class="$responsive" data-style="display:inline-block; ${args->style:html:default('color: rgb(90, 128, 39);
background-color: white;
border: none;'):input_type(css):input_props(with_responsive=1):arg_name(Style):arg_section(0, 0, 'Frame', 'th-large')}">
	${block->title:default(0):arg_name(With title bar):arg_section(2, 0, 'Title', 'bookmark')}
	<div style="${args->title_style:html:input_type(css):arg_name(Style):arg_section(2, 2, 'Title', 'bookmark')}">
		${block->x:arg_name(With close button):arg_section(3, 0, 'Close button', 'close')}
		<div style="float:right; cursor:pointer; margin:0 0 .3em .3em">
			${args->x:input_type(dontshowagain):arg_name(Close button):arg_section(3, 1, 'Close button', 'close')}
		</div>
		${args->title:arg_name(Text):arg_section(2, 1, 'Title', 'bookmark')}
		<div style="clear:both"></div>
	</div>
	<table style="height:100%; border-collapse:collapse">
		<tbody class="$table_slider" data-disabled="${args->with_slider:html:input_type(checkbox):input_props(value_off=1,value_on=):arg_name(Use slider widget):arg_section(1, 0, 'With slider', 'arrow-right')}" style="border:none; height:${args->height:html:default(550px):input_type(css_length):arg_name(Widget height):arg_section(1, 1, 'With slider', 'arrow-right')}" arrow_back_img="${args->arrow_back_img:html:default('https://static.emarketer.com/upload/362/3644becd0404ff8d.png'):input_type(emarketer_media_url):arg_name(Up arrow image):arg_section(1, 2, 'With slider', 'arrow-right')}" arrow_forward_img="${args->arrow_forward_img:html:default('https://static.emarketer.com/upload/362/12bddb03dee50eed.png'):input_type(emarketer_media_url):arg_name(Down arrow image):arg_section(1, 3, 'With slider', 'arrow-right')}">
			${foreach sum_interested_products_week as p order by p->n_goal desc limit 5}
				<tr style="border:none">
					<td data-style="${args->td_style:html:default('text-align: center;
vertical-align: top;
padding: 5px;
border: none;
width: auto;
height: auto;'):input_type(css):input_props(with_responsive=1):arg_name(Cell style):arg_section(0, 1, 'Frame', 'th-large')}">
						<a data-emarketer-click-target="products ${p->internal_id:html}" href="${p->cart_url:html:arg_name(Link target URL):arg_section(6, 0, 'Link target URL', 'link'):column_tags('url','custom text')}" target="${args->target:html:default(_blank):input_type(a_target):arg_name(Open link in):arg_section(6, 1, 'Link target URL', 'link')}" style="${args->link_style:html:default('color:'):input_type(css):arg_name(Link style):arg_section(5, 2, 'Product name', 'text-height')}">
							<img src="${p->image_big_url:html:arg_name(Item image):arg_section(4, 0, 'Image', 'image'):column_tags(image)}" data-style="${args->img_style:html:default('border:double white 5px; width:sel(130px, 20vw); height:sel(130px, 20vw)'):input_type(css):input_props(with_responsive=1):arg_name(Item image style):arg_section(4, 1, 'Image', 'image')}" onerror="this.parentNode.parentNode.parentNode.style.display='none'">
							${block->p_title:default(1):arg_name(With product name):arg_section(5, 0, 'Product name', 'text-height')}
							<div>${p->title:arg_name(Product name):arg_section(5, 1, 'Product name', 'text-height')}</div>
						</a>
						${block->n_viewed:default(0):arg_name(With site statistics):arg_section(7, 0, 'Site statistics', 'bar-chart')}
						<div>${args->n_viewed_text:arg_name(Text):arg_section(7, 1, 'Site statistics', 'bar-chart')} ${foreach sum_products_all as s where s->internal_id = p->internal_id limit 1}${s->n_viewed:arg_name(Number):arg_section(7, 2, 'Site statistics', 'bar-chart')}${end}</div>
						<div style="margin-top:0.4em">
							${block->price:default(1):arg_name(With price):arg_section(8, 0, 'Second line', 'text-height'):onchange('args.rating_style = block.price ? ''float:right'' : '''';')}
							<div style="${args->price_style:html:input_type(css):arg_name(Price position):arg_section(8, 4, 'Second line', 'text-height')}">
								${if p->price}
									${args->before_price:arg_name(Text before price):arg_section(8, 1, 'Second line', 'text-height')}
									${if p->sale_price}
										${p->sale_price:truncate(2):sprintf($%s):arg_name(Price):arg_section(8, 2, 'Second line', 'text-height')}
										<div style="${args->sale_style:html:default('color:gray; text-decoration:line-through; font-size:85%'):input_type(css):input_props(with_responsive=1):arg_name('Price before discount: style'):arg_section(8, 6, 'Second line', 'text-height')}">
											${p->price:truncate(2):sprintf($%s):arg_name(Price):arg_section(8, 5, 'Second line', 'text-height')}
										</div>
									${end}
									${if not p->sale_price}
										${p->price:truncate(2):sprintf($%s):arg_name(Price):arg_section(8, 5, 'Second line', 'text-height')}
									${end}
									${args->after_price:arg_name(Text after price):arg_section(8, 3, 'Second line', 'text-height')}
								${end}
							</div>
							${block->rating:default(0):arg_name(With rating):arg_section(8, 7, 'Second line', 'text-height'):onchange('args.price_style = block.rating ? ''float:left'' : '''';')}
							<div style="${args->rating_style:html:input_type(css):arg_name(Rating position):arg_section(8, 10, 'Second line', 'text-height')}">
								<input class="$rating" value="${p->rank:html:arg_name(Rating):arg_section(8, 8, 'Second line', 'text-height')}" max="${args->rank_max:html:input_type(number):arg_name(Maximum rating number that corresponds to 100%):arg_section(8, 9, 'Second line', 'text-height')}">
							</div>
							<div style="clear:both"></div>
						</div>
						${block->button:default(1):arg_name(With button):arg_section(9, 0, 'Add to cart button', 'plus-square')}
						<div style="margin-top:0.4em">
							<a data-emarketer-click-target="products ${p->internal_id:html}" href="${p->cart_url:html:arg_name(Link target URL):arg_section(6, 0, 'Link target URL', 'link'):column_tags('url','custom text')}" data-style="${args->button_style:html:default('display:inline-block; background-color:royalblue; border-radius:4px; padding:2px 6px; color:white; text-decoration:none'):input_type(css):input_props(with_responsive=1):arg_name(Button style):arg_section(9, 2, 'Add to cart button', 'plus-square')}">${args->button:default(Add to cart):arg_name('Text', 'Link target URL'):arg_section(9, 1, 'Add to cart button', 'plus-square')}</a>
						</div>
					</td>
				</tr>
			${end}
		</tbody>
	</table>
</div>
```


## Only images

Only images

```
<div class="$responsive" data-style="display:inline-block; ${args->style:html:default('color:black; background-color:white; border:none'):input_type(css):input_props(with_responsive=1):arg_name(Style):arg_section(0, 1, 'Frame', 'th-large')}">
	${block->title:default(0):arg_name(With title bar):arg_section(3, 0, 'Title', 'bookmark')}
	<table data-style="width:100%; border-collapse:collapse; border:none; ${args->title_bg:html:input_type(css):input_props(with_responsive=1):arg_name(Style):arg_section(3, 2, 'Title', 'bookmark')}">
		<tr>
			<td data-style="vertical-align:middle; ${args->title_style:html:input_type(css):input_props(with_responsive=1):arg_name(Title style):arg_section(3, 3, 'Title', 'bookmark')}">
				${args->title:arg_name(Text):arg_section(3, 1, 'Title', 'bookmark')}
			</td>
			${block->with_arrows:arg_name(With arrow buttons):arg_section(4, 0, 'With slider arrows', 'arrows-h')}
			<td style="width:1px; white-space:nowrap; vertical-align:middle">
				<a id="button_back" class="$flat_btn" style="${args->btn_style:html:input_type(css):arg_name(Arrow button style):arg_section(4, 1, 'With slider arrows', 'arrows-h')}" hover_style="${args->btn_hover_style:html:input_type(css):arg_name('Arrow button style: hover'):arg_section(4, 2, 'With slider arrows', 'arrows-h')}"><</a>
				<a id="button_forward" class="$flat_btn" style="${args->btn_style:html:input_type(css):arg_name(Arrow button style):arg_section(4, 1, 'With slider arrows', 'arrows-h')}" hover_style="${args->btn_hover_style:html:input_type(css):arg_name('Arrow button style: hover'):arg_section(4, 2, 'With slider arrows', 'arrows-h')}">></a>
			</td>
			${block->x:arg_name(With close button):arg_section(5, 0, 'Close button', 'close')}
			<td style="width:1px; white-space:nowrap; ${args->x_style:html:input_type(css):arg_name(Close button position):arg_section(5, 2, 'Close button', 'close')}">
				${args->x:input_type(dontshowagain):input_props(style=cursor:pointer; vertical-align:middle):arg_name(Close button):arg_section(5, 1, 'Close button', 'close')}
			</td>
		</tr>
	</table>
	<table style="width:100%; border-collapse:collapse; border:none">
		<tr class="$table_slider" data-disabled="${args->with_slider:html:input_type(checkbox):input_props(value_off=1,value_on=):arg_name(Use slider widget):arg_section(1, 0, 'With slider', 'arrow-right'):onchange('block.with_arrows=args.with_slider!=1')}" style="border:none; max-width:${args->width:html:default(600px):input_type(css_length):input_props(with_options=none):arg_name(Widget maximum width):arg_section(0, 0, 'Frame', 'th-large')}" for_max_vw="${args->for_max_vw:html:default(600px):input_type(css_length):input_props(with_options=always):arg_name(Slider widget only if screen width is less than or equal to):arg_section(1, 1, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" eq_cell_width="${args->eq_cell_width:html:default(1):input_type(checkbox):input_props(value_off=,value_on=1):arg_name(Equal cell width):arg_section(0, 2, 'Frame', 'th-large')}" eq_cell_height="${args->eq_cell_height:html:default(1):input_type(checkbox):input_props(value_off=,value_on=1):arg_name(Equal rows height):arg_section(0, 3, 'Frame', 'th-large')}" arrow_back_img="${args->arrow_back_img:html:default('//counter.emarketer.com/images/icon_square_arrow_left.png'):input_type(emarketer_media_url):arg_name(Left arrow image):arg_section(1, 2, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" arrow_forward_img="${args->arrow_forward_img:html:default('//counter.emarketer.com/images/icon_square_arrow_right.png'):input_type(emarketer_media_url):arg_name(Right arrow image):arg_section(1, 3, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" arrow_back_id="button_back" arrow_forward_id="button_forward">
			${foreach sum_interested_products_week as p order by p->n_goal desc limit 5}
				<td data-style="${args->td_style:html:default('text-align: center;
vertical-align: middle;
padding: 0px;
border: none;
max-width: 250px;
min-width: 150px;'):input_type(css):input_props(with_responsive=1):arg_name(Cell style):arg_section(0, 4, 'Frame', 'th-large')}">
					<a data-emarketer-click-target="products ${p->internal_id:html}" href="${p->cart_url:html:arg_name(Link target URL):arg_section(8, 0, 'Link target URL', 'link'):column_tags('url','custom text')}" target="${args->target:html:default(_blank):input_type(a_target):arg_name(Open link in):arg_section(8, 1, 'Link target URL', 'link')}" style="${args->link_style:html:default('color:'):input_type(css):arg_name(Link style):arg_section(7, 2, 'Product name', 'text-height')}">
						<img src="${p->image_big_url:html:arg_name(Item image):arg_section(6, 0, 'Image', 'image'):column_tags(image)}" data-style="${args->img_style:html:default('border: double white 5px;
width: sel(130px, 20vw);
height: sel(130px, 20vw);'):input_type(css):input_props(with_responsive=1):arg_name(Item image style):arg_section(6, 1, 'Image', 'image')}" onerror="this.parentNode.parentNode.style.display='none'">
					</a>
					${block->p_title:default(1):arg_name(With product name):arg_section(7, 0, 'Product name', 'text-height')}
					<a data-emarketer-click-target="products ${p->internal_id:html}" href="${p->cart_url:html:arg_name(Link target URL):arg_section(8, 0, 'Link target URL', 'link'):column_tags('url','custom text')}" target="${args->target:html:default(_blank):input_type(a_target):arg_name(Open link in):arg_section(8, 1, 'Link target URL', 'link')}" style="${args->link_style:html:default('color:'):input_type(css):arg_name(Link style):arg_section(7, 2, 'Product name', 'text-height')}">
						<div>${p->title:arg_name(Product name):arg_section(7, 1, 'Product name', 'text-height')}</div>
					</a>
					${block->n_viewed:default(1):arg_name(With site statistics):arg_section(9, 0, 'Site statistics', 'bar-chart')}
					<div>${args->n_viewed_text:default('Viewed:'):arg_name(Text):arg_section(9, 1, 'Site statistics', 'bar-chart')} ${foreach sum_products_all as s where s->internal_id = p->internal_id limit 1}${s->n_viewed:arg_name(Number):arg_section(9, 2, 'Site statistics', 'bar-chart')}${end}</div>
					<div style="margin-top:0.4em">
						${block->price:default(1):arg_name(With price):arg_section(10, 0, 'Second line', 'text-height'):onchange('args.rating_style = block.price ? ''float:right'' : '''';')}
						<div style="${args->price_style:html:input_type(css):arg_name(Price position):arg_section(10, 4, 'Second line', 'text-height')}">
							${if p->price}
								${args->before_price:arg_name(Text before price):arg_section(10, 1, 'Second line', 'text-height')}
								${if p->sale_price}
									${p->sale_price:truncate(2):sprintf($%s):arg_name(Price):arg_section(10, 2, 'Second line', 'text-height')}
									<div style="${args->sale_style:html:default('color:gray; text-decoration:line-through; font-size:85%'):input_type(css):input_props(with_responsive=1):arg_name('Price before discount: style'):arg_section(10, 6, 'Second line', 'text-height')}">
										${p->price:truncate(2):sprintf($%s):arg_name(Price):arg_section(10, 5, 'Second line', 'text-height')}
									</div>
								${end}
								${if not p->sale_price}
									${p->price:truncate(2):sprintf($%s):arg_name(Price):arg_section(10, 5, 'Second line', 'text-height')}
								${end}
								${args->after_price:arg_name(Text after price):arg_section(10, 3, 'Second line', 'text-height')}
							${end}
						</div>
						${block->rating:default(1):arg_name(With rating):arg_section(10, 7, 'Second line', 'text-height'):onchange('args.price_style = block.rating ? ''float:left'' : '''';')}
						<div style="${args->rating_style:html:input_type(css):arg_name(Rating position):arg_section(10, 10, 'Second line', 'text-height')}">
							<input class="$rating" value="${p->rank:html:arg_name(Rating):arg_section(10, 8, 'Second line', 'text-height')}" max="${args->rank_max:html:default(100):input_type(number):arg_name(Maximum rating number that corresponds to 100%):arg_section(10, 9, 'Second line', 'text-height')}">
						</div>
						<div style="clear:both"></div>
					</div>
					${block->button:default(1):arg_name(With button):arg_section(2, 0, 'Add to cart button', 'plus-square')}
					<div style="margin-top:0.4em">
						<a data-emarketer-click-target="products ${p->internal_id:html}" href="${p->cart_url:html:arg_name(Link target URL):arg_section(8, 0, 'Link target URL', 'link'):column_tags('url','custom text')}" data-style="${args->button_style:html:default('display: inline-block;
background-color: royalblue;
border-radius: 0px;
padding-top: 2px;
padding-right: 6px;
padding-bottom: 2px;
padding-left: 6px;
color: white;
text-decoration: none;'):input_type(css):input_props(with_responsive=1):arg_name(Button style):arg_section(2, 2, 'Add to cart button', 'plus-square')}">${args->button:default(Add to cart):arg_name('Text', 'Link target URL'):arg_section(2, 1, 'Add to cart button', 'plus-square')}</a>
					</div>
				</td>
			${end}
		</tr>
	</table>
</div>
```


## Recommendation with rating and statistics

Recommendation with rating and statistics

```
<div class="$responsive" data-style="display:inline-block; ${args->style:html:default('color:black; background-color:white; border:none'):input_type(css):input_props(with_responsive=1):arg_name(Style):arg_section(0, 1, 'Frame', 'th-large')}">
	${block->title:default(0):arg_name(With title bar):arg_section(3, 0, 'Title', 'bookmark')}
	<table data-style="width:100%; border-collapse:collapse; border:none; ${args->title_bg:html:input_type(css):input_props(with_responsive=1):arg_name(Style):arg_section(3, 2, 'Title', 'bookmark')}">
		<tr>
			<td data-style="vertical-align:middle; ${args->title_style:html:input_type(css):input_props(with_responsive=1):arg_name(Title style):arg_section(3, 3, 'Title', 'bookmark')}">
				${args->title:arg_name(Text):arg_section(3, 1, 'Title', 'bookmark')}
			</td>
			${block->with_arrows:arg_name(With arrow buttons):arg_section(4, 0, 'With slider arrows', 'arrows-h')}
			<td style="width:1px; white-space:nowrap; vertical-align:middle">
				<a id="button_back" class="$flat_btn" style="${args->btn_style:html:input_type(css):arg_name(Arrow button style):arg_section(4, 1, 'With slider arrows', 'arrows-h')}" hover_style="${args->btn_hover_style:html:input_type(css):arg_name('Arrow button style: hover'):arg_section(4, 2, 'With slider arrows', 'arrows-h')}"><</a>
				<a id="button_forward" class="$flat_btn" style="${args->btn_style:html:input_type(css):arg_name(Arrow button style):arg_section(4, 1, 'With slider arrows', 'arrows-h')}" hover_style="${args->btn_hover_style:html:input_type(css):arg_name('Arrow button style: hover'):arg_section(4, 2, 'With slider arrows', 'arrows-h')}">></a>
			</td>
			${block->x:arg_name(With close button):arg_section(5, 0, 'Close button', 'close')}
			<td style="width:1px; white-space:nowrap; ${args->x_style:html:input_type(css):arg_name(Close button position):arg_section(5, 2, 'Close button', 'close')}">
				${args->x:input_type(dontshowagain):input_props(style=cursor:pointer; vertical-align:middle):arg_name(Close button):arg_section(5, 1, 'Close button', 'close')}
			</td>
		</tr>
	</table>
	<table style="width:100%; border-collapse:collapse; border:none">
		<tr class="$table_slider" data-disabled="${args->with_slider:html:default(1):input_type(checkbox):input_props(value_off=1,value_on=):arg_name(Use slider widget):arg_section(1, 0, 'With slider', 'arrow-right'):onchange('block.with_arrows=args.with_slider!=1')}" style="border:none; max-width:${args->width:html:default(600px):input_type(css_length):input_props(with_options=none):arg_name(Widget maximum width):arg_section(0, 0, 'Frame', 'th-large')}" for_max_vw="${args->for_max_vw:html:input_type(css_length):input_props(with_options=always):arg_name(Slider widget only if screen width is less than or equal to):arg_section(1, 1, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" eq_cell_width="${args->eq_cell_width:html:default(1):input_type(checkbox):input_props(value_off=,value_on=1):arg_name(Equal cell width):arg_section(0, 2, 'Frame', 'th-large')}" eq_cell_height="${args->eq_cell_height:html:default(1):input_type(checkbox):input_props(value_off=,value_on=1):arg_name(Equal rows height):arg_section(0, 3, 'Frame', 'th-large')}" arrow_back_img="${args->arrow_back_img:html:input_type(emarketer_media_url):arg_name(Left arrow image):arg_section(1, 2, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" arrow_forward_img="${args->arrow_forward_img:html:input_type(emarketer_media_url):arg_name(Right arrow image):arg_section(1, 3, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" arrow_back_id="button_back" arrow_forward_id="button_forward">
			${foreach sum_interested_products_week as p order by p->n_goal desc limit 3}
				<td data-style="${args->td_style:html:default('text-align:center; vertical-align:middle; padding:5px; border:none; max-width:250px; min-width:150px'):input_type(css):input_props(with_responsive=1):arg_name(Cell style):arg_section(0, 4, 'Frame', 'th-large')}">
					<a data-emarketer-click-target="products ${p->internal_id:html}" href="${p->cart_url:html:arg_name(Link target URL):arg_section(8, 0, 'Link target URL', 'link'):column_tags('url','custom text')}" target="${args->target:html:default(_self):input_type(a_target):arg_name(Open link in):arg_section(8, 1, 'Link target URL', 'link')}" style="${args->link_style:html:default('color:'):input_type(css):arg_name(Link style):arg_section(7, 2, 'Product name', 'text-height')}">
						<img src="${p->image_big_url:html:arg_name(Item image):arg_section(6, 0, 'Image', 'image'):column_tags(image)}" data-style="${args->img_style:html:default('border:double white 5px; width:sel(130px, 20vw); height:sel(130px, 20vw)'):input_type(css):input_props(with_responsive=1):arg_name(Item image style):arg_section(6, 1, 'Image', 'image')}" onerror="this.parentNode.parentNode.style.display='none'">
					</a>
					${block->p_title:default(1):arg_name(With product name):arg_section(7, 0, 'Product name', 'text-height')}
					<a data-emarketer-click-target="products ${p->internal_id:html}" href="${p->cart_url:html:arg_name(Link target URL):arg_section(8, 0, 'Link target URL', 'link'):column_tags('url','custom text')}" target="${args->target:html:default(_self):input_type(a_target):arg_name(Open link in):arg_section(8, 1, 'Link target URL', 'link')}" style="${args->link_style:html:default('color:'):input_type(css):arg_name(Link style):arg_section(7, 2, 'Product name', 'text-height')}">
						<div>${p->title:arg_name(Product name):arg_section(7, 1, 'Product name', 'text-height')}</div>
					</a>
					${block->n_viewed:default(1):arg_name(With site statistics):arg_section(9, 0, 'Site statistics', 'bar-chart')}
					<div>${args->n_viewed_text:default('Viewed:'):arg_name(Text):arg_section(9, 1, 'Site statistics', 'bar-chart')} ${foreach sum_products_all as s where s->internal_id = p->internal_id limit 1}${s->n_viewed:arg_name(Number):arg_section(9, 2, 'Site statistics', 'bar-chart')}${end}</div>
					<div style="margin-top:0.4em">
						${block->price:default(1):arg_name(With price):arg_section(10, 0, 'Second line', 'text-height'):onchange('args.rating_style = block.price ? ''float:right'' : '''';')}
						<div style="${args->price_style:html:default('float:left'):input_type(css):arg_name(Price position):arg_section(10, 4, 'Second line', 'text-height')}">
							${if p->price}
								${args->before_price:arg_name(Text before price):arg_section(10, 1, 'Second line', 'text-height')}
								${if p->sale_price}
									${p->sale_price:truncate(2):sprintf($%s):arg_name(Price):arg_section(10, 2, 'Second line', 'text-height')}
									<div style="${args->sale_style:html:default('color:gray; text-decoration:line-through; font-size:85%'):input_type(css):input_props(with_responsive=1):arg_name('Price before discount: style'):arg_section(10, 6, 'Second line', 'text-height')}">
										${p->price:truncate(2):sprintf($%s):arg_name(Price):arg_section(10, 5, 'Second line', 'text-height')}
									</div>
								${end}
								${if not p->sale_price}
									${p->price:truncate(2):sprintf($%s):arg_name(Price):arg_section(10, 5, 'Second line', 'text-height')}
								${end}
								${args->after_price:arg_name(Text after price):arg_section(10, 3, 'Second line', 'text-height')}
							${end}
						</div>
						${block->rating:default(1):arg_name(With rating):arg_section(10, 7, 'Second line', 'text-height'):onchange('args.price_style = block.rating ? ''float:left'' : '''';')}
						<div style="${args->rating_style:html:default('float:right'):input_type(css):arg_name(Rating position):arg_section(10, 10, 'Second line', 'text-height')}">
							<input class="$rating" value="${p->rank:html:arg_name(Rating):arg_section(10, 8, 'Second line', 'text-height')}" max="${args->rank_max:html:default(100):input_type(number):arg_name(Maximum rating number that corresponds to 100%):arg_section(10, 9, 'Second line', 'text-height')}">
						</div>
						<div style="clear:both"></div>
					</div>
					${block->button:default(1):arg_name(With button):arg_section(2, 0, 'Add to cart button', 'plus-square')}
					<div style="margin-top:0.4em">
						<a data-emarketer-click-target="products ${p->internal_id:html}" href="${p->cart_url:html:arg_name(Link target URL):arg_section(8, 0, 'Link target URL', 'link'):column_tags('url','custom text')}" data-style="${args->button_style:html:default('display:inline-block; background-color:royalblue; border-radius:4px; padding:2px 6px; color:white; text-decoration:none'):input_type(css):input_props(with_responsive=1):arg_name(Button style):arg_section(2, 2, 'Add to cart button', 'plus-square')}">${args->button:default(Add to cart):arg_name('Text', 'Link target URL'):arg_section(2, 1, 'Add to cart button', 'plus-square')}</a>
					</div>
				</td>
			${end}
		</tr>
	</table>
</div>
```


## Zoomed pictures



```
<div class="$responsive" data-style="display:inline-block; ${args->style:html:default('border:none'):input_type(css):input_props(with_responsive=1):arg_name(Style):arg_section(0, 1, 'Frame', 'th-large')}">
	${block->title:default(0):arg_name(With title bar):arg_section(2, 0, 'Title', 'bookmark')}
	<table data-style="width:100%; border-collapse:collapse; border:none; ${args->title_bg:html:input_type(css):input_props(with_responsive=1):arg_name(Style):arg_section(2, 2, 'Title', 'bookmark')}">
		<tr>
			<td data-style="vertical-align:middle; ${args->title_style:html:input_type(css):input_props(with_responsive=1):arg_name(Title style):arg_section(2, 3, 'Title', 'bookmark')}">
				${args->title:arg_name(Text):arg_section(2, 1, 'Title', 'bookmark')}
			</td>
			${block->with_arrows:arg_name(With arrow buttons):arg_section(3, 0, 'With slider arrows', 'arrows-h')}
			<td style="width:1px; white-space:nowrap; vertical-align:middle">
				<a id="button_back" class="$flat_btn" style="${args->btn_style:html:input_type(css):arg_name(Arrow button style):arg_section(3, 1, 'With slider arrows', 'arrows-h')}" hover_style="${args->btn_hover_style:html:input_type(css):arg_name('Arrow button style: hover'):arg_section(3, 2, 'With slider arrows', 'arrows-h')}"><</a>
				<a id="button_forward" class="$flat_btn" style="${args->btn_style:html:input_type(css):arg_name(Arrow button style):arg_section(3, 1, 'With slider arrows', 'arrows-h')}" hover_style="${args->btn_hover_style:html:input_type(css):arg_name('Arrow button style: hover'):arg_section(3, 2, 'With slider arrows', 'arrows-h')}">></a>
			</td>
			${block->x:arg_name(With close button):arg_section(4, 0, 'Close button', 'close')}
			<td style="width:1px; white-space:nowrap; ${args->x_style:html:input_type(css):arg_name(Close button position):arg_section(4, 2, 'Close button', 'close')}">
				${args->x:input_type(dontshowagain):input_props(style=cursor:pointer; vertical-align:middle):arg_name(Close button):arg_section(4, 1, 'Close button', 'close')}
			</td>
		</tr>
	</table>
	<table style="width:100%; border-collapse:separate; border-spacing:12px 0; margin-bottom:1.2em">
		<tr class="$table_slider" data-disabled="${args->with_slider:html:default(1):input_type(checkbox):input_props(value_off=1,value_on=):arg_name(Use slider widget):arg_section(1, 0, 'With slider', 'arrow-right'):onchange('block.with_arrows=args.with_slider!=1')}" style="border:none; max-width:${args->width:html:default(none):input_type(css_length):input_props(with_options=none):arg_name(Widget maximum width):arg_section(0, 0, 'Frame', 'th-large')}" for_max_vw="${args->for_max_vw:html:input_type(css_length):input_props(with_options=always):arg_name(Slider widget only if screen width is less than or equal to):arg_section(1, 1, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" eq_cell_height="1" arrow_back_img="${args->arrow_back_img:html:input_type(emarketer_media_url):arg_name(Left arrow image):arg_section(1, 2, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" arrow_forward_img="${args->arrow_forward_img:html:input_type(emarketer_media_url):arg_name(Right arrow image):arg_section(1, 3, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" arrow_back_id="button_back" arrow_forward_id="button_forward">
			${foreach sum_interested_products_week as p order by p->n_goal desc limit 5}
				<td style="padding:0; text-align:center; background-color:white; border:solid ${args->border_color:html:default('#20b298'):input_type(color):arg_name(Border color):arg_section(0, 3, 'Frame', 'th-large')} 1px">
					<a data-emarketer-click-target="products ${p->internal_id:html}" href="${p->content_url:html:arg_name(Link target URL):arg_section(7, 0, 'Link target URL', 'link'):column_tags('url','custom text')}" target="_blank" data-style="display:block; width:${args->img_width:html:default('sel(250px, 26vw)'):input_type(css_length):input_props(with_responsive=1):arg_name(Cell width):arg_section(0, 2, 'Frame', 'th-large')}">
						<div data-style="background-image:url('${p->image_small_url:html:arg_name(Item image):arg_section(5, 0, 'Image', 'image'):column_tags(image)}'); background-repeat:no-repeat; background-position:center; background-size:100% 100%; transition: background-size 0.7s ease; width:100%" data-z='${args->zoom:html:default(120):input_type(number):arg_name('Image zoom on hover, %'):arg_section(5, 1, 'Image', 'image')}' onmouseover="var z=this.getAttribute('data-z'); this.style.backgroundSize=z+'% '+z+'%'" onmouseout="this.style.backgroundSize='100% 100%'">
							<img src="${p->image_small_url:html:arg_name(Item image):arg_section(5, 0, 'Image', 'image'):column_tags(image)}" data-style="visibility:hidden; width:auto; height:auto; max-width:100%; max-height:${args->img_max_height:html:default('sel(300px, 30vw)'):input_type(css_length):input_props(with_responsive=1):arg_name(Image maximum height):arg_section(0, 4, 'Frame', 'th-large')}">
						</div>
					</a>
					<div data-style="width:${args->img_width:html:default('sel(250px, 26vw)'):input_type(css_length):input_props(with_responsive=1):arg_name(Cell width):arg_section(0, 2, 'Frame', 'th-large')}">
						<div data-style="display:inline-block; ${args->a_css:html:default('font-size:sel(16px, 5vw); padding:0.6em 0; text-transform:uppercase; color:rgb(51, 51, 51))'):input_type(css):input_props(with_responsive=1):arg_name(Text color):arg_section(6, 2, 'Text', 'align-justify')}">
							${p->title:arg_name(Item text):arg_section(6, 0, 'Text', 'align-justify')}
						</div>
					</div>
					${block->price:default(1):arg_name(With price):arg_section(8, 0, 'Price', 'dollar')}
					<div data-style="width:${args->img_width:html:default('sel(250px, 26vw)'):input_type(css_length):input_props(with_responsive=1):arg_name(Cell width):arg_section(0, 2, 'Frame', 'th-large')}">
						${if p->price}
							${args->before_price:arg_name(Text before price):arg_section(8, 1, 'Price', 'dollar')}
							${if p->sale_price and p->sale_price < p->price}
								${p->sale_price:truncate(2):sprintf($%s):arg_name(Price):arg_section(8, 2, 'Price', 'dollar')}
								<div style="${args->sale_style:html:default('color:gray; text-decoration:line-through; font-size:85%'):input_type(css):input_props(with_responsive=1):arg_name('Price before discount: style'):arg_section(8, 5, 'Price', 'dollar')}">
									${p->price:truncate(2):sprintf($%s):arg_name(Price):arg_section(8, 4, 'Price', 'dollar')}
								</div>
							${end}
							${if not p->sale_price or p->sale_price >= p->price}
								${p->price:truncate(2):sprintf($%s):arg_name(Price):arg_section(8, 4, 'Price', 'dollar')}
							${end}
							${args->after_price:arg_name(Text after price):arg_section(8, 3, 'Price', 'dollar')}
						${end}
					</div>
					<div style="font-size:1px">
						<div data-style="display:inline-block; background-color:${args->border_color:html:default('#20b298'):input_type(color):arg_name(Border color):arg_section(0, 3, 'Frame', 'th-large')}; ${args->a_css_2:html:default('width:100px; height:3px; max-width:80%'):input_type(css):input_props(with_responsive=1):arg_name(Ruler):arg_section(6, 4, 'Text', 'align-justify')}"></div>
					</div>
					<div data-style="width:${args->img_width:html:default('sel(250px, 26vw)'):input_type(css_length):input_props(with_responsive=1):arg_name(Cell width):arg_section(0, 2, 'Frame', 'th-large')}">
						<div data-style="display:inline-block; ${args->a_css_3:html:default('font-size:sel(16px, 5vw); padding:0.6em 0; color:#777; font-style:italic; letter-spacing:1px; line-height:1.3'):input_type(css):input_props(with_responsive=1):arg_name(Text color):arg_section(6, 3, 'Text', 'align-justify')}; padding-bottom:0">
							${p->description:arg_name(Item text):arg_section(6, 1, 'Text', 'align-justify')}
						</div>
					</div>
					<a data-emarketer-click-target="products ${p->internal_id:html}" href="${p->content_url:html:arg_name(Link target URL):arg_section(7, 0, 'Link target URL', 'link'):column_tags('url','custom text')}" target="_blank" data-style="display:inline-block; position:relative; top:1.3em; text-decoration:none; transition: font-size 0.3s ease; background-color:${args->border_color:html:default('#20b298'):input_type(color):arg_name(Border color):arg_section(0, 3, 'Frame', 'th-large')}; ${args->a_css_4:html:default('padding:0.2em; color:white; font-size:sel(16px, 4vw)'):input_type(css):input_props(with_responsive=1):arg_name(Button style):arg_section(9, 1, 'Button', 'hand-pointer-o')}" onmouseenter="var t=this; s=t.style, f=s.fontSize, p=f.match(/^([\d\.]+)(\w+)$/); if (!t._b) t._b=[s.backgroundColor, s.color, f]; s.backgroundColor=t._b[1]; s.color=t._b[0]; if (p) if (!t._p) {s.fontSize=(p[1]*0.9)+p[2]; t._p=1; setTimeout(function() {s.fontSize=t._b[2]; t._p=0;}, 300)}" onmouseleave="var s=this.style, b=this._b; s.backgroundColor=b[0]; s.color=b[1]">
						<div data-style="border:solid 1px; ${args->a_css_5:html:default('padding-left:sel(1.8em, 2vw); padding-right:sel(1.8em, 2vw); padding-top:sel(0.4em, 1vw); padding-bottom:sel(0.4em, 1vw)'):input_type(css):input_props(with_responsive=1):arg_name(Button style):arg_section(9, 2, 'Button', 'hand-pointer-o')}">
							${args->button_text:default(DETAILS):arg_name(Button text):arg_section(9, 0, 'Button', 'hand-pointer-o')}
						</div>
					</a>
				</td>
			${end}
		</tr>
	</table>
</div>
```


## Category View



```
<div class="$responsive" style="${args->a_style3:html:default('color: #444;
font-family: arial,sans-serif;
font-size: 12px;
line-height: 18px;'):input_type(css):arg_name(Style):arg_section(0, 0, 'Box', 'th-large')}">
	<div style="${args->a_style:html:default('font-size: 15px;
text-align: left;
padding-top: 5px;
padding-right: 0;
padding-bottom: 5px;
padding-left: 15px;'):input_type(css):arg_name(Style):arg_section(1, 0, 'Title', 'bookmark')}">
		${args->line:default('<strong>Recommended For You:</strong>'):arg_name(Text):arg_section(1, 1, 'Title', 'bookmark')}
	</div>
	<div style="display:flex; flex-wrap:wrap; justify-content:space-between; align-items:stretch">
		${foreach recom_products as p limit 12}
			<a data-emarketer-click-target="products ${p->internal_id:html}" href="${p->cart_url:html:default('p->cart_url')}" style="display:block; position:relative; ${args->a_style4:html:default('margin-top: 0px;
margin-right: 21px;
margin-bottom: 20px;
margin-left: 21px;
border: 1px solid #bababa;
text-align: center;
width: 180px;
box-shadow: 0 4px 5px rgba(0,0,0,0.3);
text-decoration: none;'):input_type(css):arg_name(Cell):arg_section(2, 3, 'Cell', 'bars')}">
				<div style="margin-bottom:4em; ${args->a_style40:html:default('					padding:10px 15px
				'):input_type(css):arg_name(Cell):arg_section(2, 4, 'Cell', 'bars')}">
					<img src="${p->image_big_url:html:default('p->image_medium_url')}" alt="${p->title:html}" title="${p->title:html}" style="width:auto; height:auto; ${args->a_style7:html:default('							max-height: 100px;
							margin-bottom: 10px;
							border: none;
					'):input_type(css):arg_name(Product image style):arg_section(2, 2, 'Cell', 'bars')}">
					<div style="${args->a_style5:html:default('							color: #005274;
							font-size: 14px;
							font-weight: bold;
							text-align: center;
					'):input_type(css):arg_name(Product name):arg_section(2, 0, 'Cell', 'bars')}">
						${p->title}
						<div>
							${if p->sale_price > 0 and p->sale_price < p->price}
								<span style="${args->a_style50:html:default('									text-decoration: line-through;
									color: red;
								'):input_type(css):arg_name(Product name):arg_section(2, 1, 'Cell', 'bars')}">
									${p->price:sprintf('$%s')}
								</span>
								${p->sale_price:sprintf('$%s')}
							${end}
							${if p->sale_price <= 0 or p->sale_price >= p->price}
								${p->price:sprintf('$%s')}
							${end}
						</div>
					</div>
				</div>
				<div style="position:absolute; width:100%; bottom:10px; text-align:center">
					<div style="display:inline-block; ${args->a_style6:html:default('							background-color: #fef200;
							border-bottom: 1px solid #b4a600;
							border-left: 1px solid #fff045;
							border-right: 1px solid #d5c614;
							border-top: 1px solid #fff045;
							color: #000!important;
							font-size: 14px;
							padding: 5px 20px;
							-webkit-appearance: none;
					'):input_type(css):arg_name(Style):arg_section(3, 1, 'Button', 'bars')}">
						${args->line3:default(View Now):arg_name(Text):arg_section(3, 0, 'Button', 'bars')}
					</div>
				</div>
			</a>
		${end}
	</div>
</div>
```


## Small size widget



```
<div class="$responsive" data-style="display:inline-block; position:relative; ${args->style:html:default('border: none;
text-align: left;
background-color: rgb(240, 235, 235);'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(0, 1, 'Frame', 'th-large')}" onupdate="
	var
		w=this.offsetWidth,
		b=12,
		a=ns.joyquery('parent::*>tr>td>*', by_id.ts).get(),
		d=a[0].parentNode,
		t=d.offsetWidth,
		n=Math.max(Math.round((w-b)/(t+b)), Math.min(2, by_id.ts.children.length)),
		T=(w-b)/n-b-parseFloat(d.style.borderLeftWidth)*2;
	for (i=0; i!=a.length; i++) if (a[i].style.display!='inline-block') a[i].style.width=T+'px'
">
	${block->title:default(1):arg_name(With title bar):arg_section(2, 0, 'Title', 'bookmark')}
	<table data-style="width:100%; border-collapse:collapse; border:none; ${args->title_bg:html:default('background-color: rgba(170, 76, 76, 0);
margin-top: 23px;
margin-right: 0px;
margin-bottom: 7px;
margin-left: 7px;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(2, 2, 'Title', 'bookmark')}">
		<tr>
			<td data-style="vertical-align:middle; ${args->title_style:html:default('text-align: left;
padding-top: 0px;
padding-right: 0px;
padding-bottom: 15px;
padding-left: 0px;
font-size: 23px;
text-transform: uppercase;
font-family: "Karla","HelveticaNeue","Helvetica Neue",sans-serif;
font-weight: 600;
color: rgb(36, 29, 29);'):input_type(css):input_props('with_responsive=1'):arg_name(Title style):arg_section(2, 3, 'Title', 'bookmark')}">
				${args->title:default(You May Also Like):arg_name(Text):arg_section(2, 1, 'Title', 'bookmark')}
			</td>
			${block->with_arrows:default(0):arg_name(With arrow buttons):arg_section(1, 0, 'With slider', 'arrow-right')}
			<td style="width:1px; white-space:nowrap; vertical-align:middle">
				<a id="button_back" class="$flat_btn" style="${args->btn_style:html:input_type(css):arg_name(Arrow button style):arg_section(1, 1, 'With slider', 'arrow-right')}" hover_style="${args->btn_hover_style:html:input_type(css):arg_name('Arrow button style: hover'):arg_section(1, 2, 'With slider', 'arrow-right')}"><</a>
				<a id="button_forward" class="$flat_btn" style="${args->btn_style:html:input_type(css):arg_name(Arrow button style):arg_section(1, 1, 'With slider', 'arrow-right')}" hover_style="${args->btn_hover_style:html:input_type(css):arg_name('Arrow button style: hover'):arg_section(1, 2, 'With slider', 'arrow-right')}">></a>
			</td>
			${block->x:default(0):arg_name(With close button):arg_section(3, 0, 'Close button', 'close')}
			<td style="width:1px; white-space:nowrap; ${args->x_style:html:input_type(css):arg_name(Close button position):arg_section(3, 2, 'Close button', 'close')}">
				${args->x:input_type(dontshowagain):input_props('style=cursor:pointer; vertical-align:middle'):arg_name(Close button):arg_section(3, 1, 'Close button', 'close')}
			</td>
		</tr>
	</table>
	<table style="width:100%; border-collapse:separate; border-spacing:12px 0; margin-bottom:1.2em">
		<tr id="ts" class="$table_slider" data-disabled="${args->with_slider:html:input_type(checkbox):input_props('value_off=1','value_on='):arg_name(Use slider widget):arg_section(1, 4, 'With slider', 'arrow-right'):onchange('if (args.with_slider==1) block.with_arrows = block.pagination = 0')}" style="border:none; max-width:${args->width:html:default(970px):input_type(css_length):input_props('with_options=none'):arg_name(Widget maximum width):arg_section(0, 0, 'Frame', 'th-large')}" for_max_vw="${args->for_max_vw:html:default(always):input_type(css_length):input_props('with_options=always'):arg_name(Slider widget only if screen width is less than or equal to):arg_section(1, 5, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" eq_cell_width="${args->eq_cell_width:html:input_type(checkbox):input_props('value_off=','value_on=1'):arg_name(Equal cell width):arg_section(0, 2, 'Frame', 'th-large')}" eq_cell_height="1" arrows_line="${args->arrows_line:html:default(0):input_type(checkbox):input_props('value_off=-1','value_on=0'):arg_name(Arrows in the middle of images):arg_section(1, 9, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" arrow_back_img="${args->arrow_back_img:html:default('https://static.emarketer.com/upload/4035/81cac4981db4ac11.png'):input_type(emarketer_media_url):arg_name(Left arrow image):arg_section(1, 6, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" arrow_forward_img="${args->arrow_forward_img:html:default('https://static.emarketer.com/upload/4035/d8fc13382d711207.png'):input_type(emarketer_media_url):arg_name(Right arrow image):arg_section(1, 7, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" pagination_id="tsp" arrow_back_id="button_back" arrow_forward_id="button_forward" arrows_offset="${args->arrows_offset:html:default(0):input_type(number):arg_name(Slider arrows offset):arg_section(1, 8, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" hide_buttons="${args->hide_buttons:html:input_type(checkbox):input_props('value_off=','value_on=1'):arg_name(Hide arrow buttons when nothing to scroll):arg_section(1, 3, 'With slider', 'arrow-right'):visible_if('block.title-0 && block.with_arrows-0')}">
			${foreach recom_products as p limit 18}
				<td style="padding:0; text-align:center; background-color:white; border:solid ${args->border_color:html:default(white):input_type(color):arg_name(Border color):arg_section(0, 4, 'Frame', 'th-large')} 1px">
					<a data-emarketer-click-target="" href="${p->cart_url:html:arg_name(Link target URL):arg_section(6, 0, 'Link target URL', 'link'):column_tags('url','custom text')}" target="${args->target:html:default(_self):input_type(a_target):arg_name(Open link in):arg_section(6, 1, 'Link target URL', 'link')}" data-style="display:block; margin:auto; box-sizing:border-box; width:${args->img_width:html:default('sel(119px, 17vw)'):input_type(css_length):input_props('with_responsive=1'):arg_name(Cell width):arg_section(0, 3, 'Frame', 'th-large')}">
						<div data-style="background-image:url('${p->image_big_url:html:arg_name(Item image):arg_section(4, 0, 'Image', 'image'):column_tags(image)}'); background-repeat:no-repeat; background-position:center; background-size:100% 100%; transition: background-size 0.7s ease; width:100%" data-z='${args->zoom:html:default(100):input_type(number):arg_name('Image zoom on hover, %'):arg_section(4, 1, 'Image', 'image')}' onmouseover="var z=this.getAttribute('data-z'); this.style.backgroundSize=z+'% '+z+'%'" onmouseout="this.style.backgroundSize='100% 100%'">
							<img src="${p->image_big_url:html:arg_name(Item image):arg_section(4, 0, 'Image', 'image'):column_tags(image)}" data-style="visibility:hidden; width:auto; height:auto; max-width:100%; max-height:${args->img_max_height:html:default('sel(200px, 30vw)'):input_type(css_length):input_props('with_responsive=1'):arg_name(Image maximum height):arg_section(0, 5, 'Frame', 'th-large')}">
						</div>
					</a>
					<div data-style="margin:auto; box-sizing:border-box; width:${args->img_width:html:default('sel(119px, 17vw)'):input_type(css_length):input_props('with_responsive=1'):arg_name(Cell width):arg_section(0, 3, 'Frame', 'th-large')}">
						<div data-style="display:inline-block; ${args->a_css:html:default('font-size: 11px;
font-family: "Karla";
color: #666;
text-decoration: inherit;
text-align: left;
float: left;
padding-top: 2px;
padding-right: 0px;
padding-bottom: 0px;
padding-left: 2px;
text-transform: none;
overflow: visible;
font-weight: 700;
vertical-align: top;'):input_type(css):input_props('with_responsive=1'):arg_name(Text color):arg_section(5, 3, 'Text', 'align-justify')}">
							${p->title:arg_name(Item text):arg_section(5, 1, 'Text', 'align-justify')}
						</div>
					</div>
					${block->price:default(0):arg_name(With price):arg_section(7, 0, 'Price', 'dollar')}
					<div data-style="margin:auto; box-sizing:border-box; width:${args->img_width:html:default('sel(119px, 17vw)'):input_type(css_length):input_props('with_responsive=1'):arg_name(Cell width):arg_section(0, 3, 'Frame', 'th-large')}">
						${if p->price}
							${args->before_price:arg_name(Text before price):arg_section(7, 1, 'Price', 'dollar')}
							${if p->sale_price and p->sale_price < p->price}
								${p->sale_price:truncate(2):sprintf($%s):arg_name(Price):arg_section(7, 2, 'Price', 'dollar')}
								<div style="${args->sale_style:html:input_type(css):input_props('with_responsive=1'):arg_name('Price before discount: style'):arg_section(7, 5, 'Price', 'dollar')}">
									${p->price:truncate(2):sprintf($%s):arg_name(Price):arg_section(7, 4, 'Price', 'dollar')}
								</div>
							${end}
							${if not p->sale_price or p->sale_price >= p->price}
								${p->price:truncate(2):sprintf($%s):arg_name(Price):arg_section(7, 4, 'Price', 'dollar')}
							${end}
							${args->after_price:arg_name(Text after price):arg_section(7, 3, 'Price', 'dollar')}
						${end}
					</div>
					<div style="margin:auto; box-sizing:border-box; font-size:1px">
						<div data-style="display:inline-block; background-color:${args->border_color:html:default(white):input_type(color):arg_name(Border color):arg_section(0, 4, 'Frame', 'th-large')}; ${args->a_css_2:html:default('width: 98%;
height: 2px;
max-width: 90%;'):input_type(css):input_props('with_responsive=1'):arg_name(Ruler):arg_section(5, 5, 'Text', 'align-justify')}"></div>
					</div>
					${block->description:default(0):arg_name(With description):arg_section(5, 0, 'Text', 'align-justify')}
					<div data-style="margin:auto; box-sizing:border-box; width:${args->img_width:html:default('sel(119px, 17vw)'):input_type(css_length):input_props('with_responsive=1'):arg_name(Cell width):arg_section(0, 3, 'Frame', 'th-large')}">
						<div data-style="display:inline-block; ${args->a_css_3:html:input_type(css):input_props('with_responsive=1'):arg_name(Text color):arg_section(5, 4, 'Text', 'align-justify')}; padding-bottom:0">
							${p->description:arg_name(Item text):arg_section(5, 2, 'Text', 'align-justify')}
						</div>
					</div>
					${block->button:default(0):arg_name(With button):arg_section(8, 0, 'Button', 'hand-pointer-o')}
					<a data-emarketer-click-target="" href="${p->cart_url:html:arg_name(Link target URL):arg_section(6, 0, 'Link target URL', 'link'):column_tags('url','custom text')}" target="${args->target:html:default(_self):input_type(a_target):arg_name(Open link in):arg_section(6, 1, 'Link target URL', 'link')}" data-style="display:inline-block; position:relative; top:1.3em; text-decoration:none; transition: font-size 0.3s ease; background-color:${args->border_color:html:default(white):input_type(color):arg_name(Border color):arg_section(0, 4, 'Frame', 'th-large')}; ${args->a_css_4:html:input_type(css):input_props('with_responsive=1'):arg_name(Button style):arg_section(8, 2, 'Button', 'hand-pointer-o')}" onmouseenter="var t=this; s=t.style, f=s.fontSize, p=f.match(/^([\d\.]+)(\w+)$/); if (!t._b) t._b=[s.backgroundColor, s.color, f]; s.backgroundColor=t._b[1]; s.color=t._b[0]; if (p) if (!t._p) {s.fontSize=(p[1]*0.9)+p[2]; t._p=1; setTimeout(function() {s.fontSize=t._b[2]; t._p=0;}, 300)}" onmouseleave="var s=this.style, b=this._b; s.backgroundColor=b[0]; s.color=b[1]">
						<div data-style="border:solid 1px; ${args->a_css_5:html:input_type(css):input_props('with_responsive=1'):arg_name(Button style):arg_section(8, 3, 'Button', 'hand-pointer-o')}">
							${args->button_text:arg_name(Button text):arg_section(8, 1, 'Button', 'hand-pointer-o')}
						</div>
					</a>
				</td>
			${end}
		</tr>
	</table>
	${block->pagination:default(0):arg_name(With slider pagination):arg_section(1, 10, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}
	<div id="tsp" class="$table_slider_pagination" slider_id="ts" selected_color="${args->pagination_color_on:html:input_type(color):arg_name(Bullet Selected Color):arg_section(1, 11, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" style="${args->pagination_color:html:input_type(css):arg_name(Bullet style):arg_section(1, 12, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}"></div>
</div>
```


## Corner slide widget



```
<div class="$responsive" data-style="position:relative; margin:auto; ${args->style:html:default('border: none;
text-align: left;
color: rgb(183,41,19);
max-width: 90%;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(0, 0, 'Frame', 'th-large')}" onupdate="
	var
		w=Math.min(ns.joyquery('ancestor::table:limit(1) parent::div parent::div', by_id.ts).get(0).offsetWidth, document.documentElement.clientWidth-1),
		b=12,
		a=ns.joyquery('parent::*>tr>td>*', by_id.ts).get(),
		d=a[0].parentNode,
		t=d.offsetWidth,
		n=Math.max(Math.round((w-b)/(t+b)), Math.min(2, by_id.ts.children.length)),
		T=(w-b)/n-b-parseFloat(d.style.borderLeftWidth)*2;
	for (i=0; i!=a.length; i++) if (a[i].style.display!='inline-block') a[i].style.width=T+'px'
">
	${block->title:default(1):arg_name(With title bar):arg_section(2, 0, 'Title', 'bookmark')}
	<table data-style="width:100%; border-collapse:collapse; border:none; ${args->title_bg:html:default('background-color: rgba(170, 76, 76, 0);
margin-top: 0px;
margin-right: 0;
margin-bottom: 0px;
margin-left: 0px;
font-size: 16px;
text-transform: uppercase;
font-family: "Karla","HelveticaNeue","Helvetica Neue",sans-serif;
font-weight: 500;
color: #4b4f59;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(2, 2, 'Title', 'bookmark')}">
		<tr>
			<td data-style="vertical-align:middle; ${args->title_style:html:default('text-align: left;
padding-top: 0px;
padding-right: 0px;
padding-bottom: 25px;
padding-left: 0px;
'):input_type(css):input_props('with_responsive=1'):arg_name(Title style):arg_section(2, 3, 'Title', 'bookmark')}">
				${args->title:default(RECOMMENDED FOR YOU):arg_name(Text):arg_section(2, 1, 'Title', 'bookmark')}
			</td>
			${block->with_arrows:default(1):arg_name(With arrow buttons):arg_section(1, 0, 'With slider', 'arrow-right')}
			<td style="width:1px; white-space:nowrap; vertical-align:middle">
				<a id="button_back" class="$flat_btn" style="${args->btn_style:html:input_type(css):arg_name(Arrow button style):arg_section(1, 1, 'With slider', 'arrow-right')}" hover_style="${args->btn_hover_style:html:input_type(css):arg_name('Arrow button style: hover'):arg_section(1, 2, 'With slider', 'arrow-right')}"><</a>
				<a id="button_forward" class="$flat_btn" style="${args->btn_style:html:input_type(css):arg_name(Arrow button style):arg_section(1, 1, 'With slider', 'arrow-right')}" hover_style="${args->btn_hover_style:html:input_type(css):arg_name('Arrow button style: hover'):arg_section(1, 2, 'With slider', 'arrow-right')}">></a>
			</td>
			${block->x:default(0):arg_name(With close button):arg_section(3, 0, 'Close button', 'close')}
			<td style="width:1px; white-space:nowrap; ${args->x_style:html:input_type(css):arg_name(Close button position):arg_section(3, 2, 'Close button', 'close')}">
				${args->x:input_type(dontshowagain):input_props('style=cursor:pointer; vertical-align:middle'):arg_name(Close button):arg_section(3, 1, 'Close button', 'close')}
			</td>
		</tr>
	</table>
	<table style="width:100%; border-collapse:separate; border-spacing:12px 0; margin-bottom:1.2em">
		<tr id="ts" class="$table_slider" data-disabled="${args->with_slider:html:input_type(checkbox):input_props('value_off=1','value_on='):arg_name(Use slider widget):arg_section(1, 4, 'With slider', 'arrow-right'):onchange('if (args.with_slider==1) block.with_arrows = block.pagination = 0')}" style="border:none" for_max_vw="${args->for_max_vw:html:default(always):input_type(css_length):input_props('with_options=always'):arg_name(Slider widget only if screen width is less than or equal to):arg_section(1, 5, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" eq_cell_width="${args->eq_cell_width:html:default(1):input_type(checkbox):input_props('value_off=','value_on=1'):arg_name(Equal cell width):arg_section(0, 1, 'Frame', 'th-large')}" eq_cell_height="1" arrows_line="${args->arrows_line:html:default(-1):input_type(checkbox):input_props('value_off=-1','value_on=0'):arg_name(Arrows in the middle of images):arg_section(1, 9, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" arrow_back_img="${args->arrow_back_img:html:default('https://static.emarketer.com/upload/4035/3256192fabeef23a.png'):input_type(emarketer_media_url):arg_name(Left arrow image):arg_section(1, 6, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" arrow_forward_img="${args->arrow_forward_img:html:default('https://static.emarketer.com/upload/4035/6447f3eea66d7795.png'):input_type(emarketer_media_url):arg_name(Right arrow image):arg_section(1, 7, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" pagination_id="tsp" arrow_back_id="button_back" arrow_forward_id="button_forward" arrows_offset="${args->arrows_offset:html:default(10):input_type(number):arg_name(Slider arrows offset):arg_section(1, 8, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" hide_buttons="${args->hide_buttons:html:default(1):input_type(checkbox):input_props('value_off=','value_on=1'):arg_name(Hide arrow buttons when nothing to scroll):arg_section(1, 3, 'With slider', 'arrow-right'):visible_if('block.title-0 && block.with_arrows-0')}">
			${foreach recom_products as p limit 16}
				<td style="padding:0; text-align:center; background-color:white; border:solid ${args->border_color:html:default(white):input_type(color):arg_name(Border color):arg_section(0, 3, 'Frame', 'th-large')} 1px; ${args->td_style:html:input_type(css):input_props('with_responsive=1'):arg_name(Cell Style):arg_section(0, 4, 'Frame', 'th-large')}">
					<a data-emarketer-click-target="products ${p->internal_id:html}" href="${p->cart_url:html:arg_name(Link target URL):arg_section(6, 0, 'Link target URL', 'link'):column_tags('url','custom text')}" target="${args->target:html:default(_self):input_type(a_target):arg_name(Open link in):arg_section(6, 1, 'Link target URL', 'link')}" data-style="display:block; margin:auto; box-sizing:border-box; width:${args->img_width:html:default('sel(230px, 30vw)'):input_type(css_length):input_props('with_responsive=1'):arg_name(Cell width):arg_section(0, 2, 'Frame', 'th-large')}">
						<img src="${p->image_big_url:html:arg_name(Item image):arg_section(4, 0, 'Image', 'image'):column_tags(image)}" data-style="${args->img_style:html:default('border: double white 5px;
width: auto;
height: auto;
max-height: 120px;
max-width: 120px;'):input_type(css):input_props('with_responsive=1'):arg_name(Image style):arg_section(4, 1, 'Image', 'image')}">
					</a>
					<div data-style="margin:auto; box-sizing:border-box; width:${args->img_width:html:default('sel(230px, 30vw)'):input_type(css_length):input_props('with_responsive=1'):arg_name(Cell width):arg_section(0, 2, 'Frame', 'th-large')}">
						<div data-style="display:inline-block; ${args->a_css:html:default('font-size: 12px;
color: rgb(0,110,204);
text-decoration: inherit;
text-align: center;
float: left;
padding-top: 5px;
padding-right: 0px;
padding-bottom: 5px;
padding-left: 0px;
text-overflow: inherit;
text-transform: none;
width: 100%;
white-space: normal;
max-width: none;'):input_type(css):input_props('with_responsive=1'):arg_name(Text color):arg_section(5, 3, 'Text', 'align-justify')}">
<a style="font-family:Helvetica, Arial !important; text-decoration:none; color:rgb(0,110,204);" href="${p->cart_url:html:arg_name(Link target URL):arg_section(6, 0, 'Link target URL', 'link'):column_tags('url','custom text')}">
							${p->title:arg_name(Item text):arg_section(5, 1, 'Text', 'align-justify')}
</a>
						</div>
					</div>
					${block->rating:default(0):arg_name(With rating):arg_section(7, 0, 'Rating', 'star')}
					<div style="${args->rating_style:html:input_type(css):arg_name(Rating style)}">
						<input class="$rating" value="${p->rank:html:arg_name(Rating):arg_section(7, 1, 'Rating', 'star')}" max="${args->rank_max:html:input_type(number):arg_name(Maximum rating number that corresponds to 100%):arg_section(7, 2, 'Rating', 'star')}">
					</div>
					${block->price:default(1):arg_name(With price):arg_section(8, 0, 'Price', 'tag')}
					<div data-style="margin:auto; box-sizing:border-box; width:${args->img_width:html:default('sel(230px, 30vw)'):input_type(css_length):input_props('with_responsive=1'):arg_name(Cell width):arg_section(0, 2, 'Frame', 'th-large')}">
						${if p->price}
							${if p->sale_price and p->sale_price < p->price}
								<div style="${args->sale_style:html:input_type(css):input_props('with_responsive=1'):arg_name('Price after discount: style'):arg_section(8, 5, 'Price', 'tag')}">
									${args->before_price:arg_name(Text before price):arg_section(8, 2, 'Price', 'tag')}
									${p->sale_price:truncate(2):sprintf($%s):arg_name(Price after discount):arg_section(8, 3, 'Price', 'tag')}
									${args->after_price:arg_name(Text after price):arg_section(8, 1, 'Price', 'tag')}
								</div>
								<div style="${args->price_style:html:default('color: rgba(119, 119, 119, 0.53);
text-decoration: line-through;
font-size: 11px;'):input_type(css):input_props('with_responsive=1'):arg_name('Price before discount: style'):arg_section(8, 6, 'Price', 'tag')}">
									${p->price:truncate(2):sprintf($%s):arg_name(Price before discount):arg_section(8, 4, 'Price', 'tag')}
								</div>
							${end}
							${if not p->sale_price or p->sale_price >= p->price}
								<div style="${args->price_style:html:default('color: rgba(119, 119, 119, 0.53);
text-decoration: line-through;
font-size: 11px;'):input_type(css):input_props('with_responsive=1'):arg_name('Price before discount: style'):arg_section(8, 6, 'Price', 'tag')}">
									${args->before_price:arg_name(Text before price):arg_section(8, 2, 'Price', 'tag')}
									${p->price:truncate(2):sprintf($%s):arg_name(Price before discount):arg_section(8, 4, 'Price', 'tag')}
									${args->after_price:arg_name(Text after price):arg_section(8, 1, 'Price', 'tag')}
								</div>
							${end}
						${end}
					</div>
					<div style="margin:auto; box-sizing:border-box; font-size:1px">
						<div data-style="display:inline-block; background-color:${args->border_color:html:default(white):input_type(color):arg_name(Border color):arg_section(0, 3, 'Frame', 'th-large')}; ${args->a_css_2:html:default('width:100px; height:3px; max-width:80%'):input_type(css):input_props('with_responsive=1'):arg_name(Ruler):arg_section(5, 5, 'Text', 'align-justify')}"></div>
					</div>
					${block->description:default(0):arg_name(With description):arg_section(5, 0, 'Text', 'align-justify')}
					<div data-style="margin:auto; box-sizing:border-box; width:${args->img_width:html:default('sel(230px, 30vw)'):input_type(css_length):input_props('with_responsive=1'):arg_name(Cell width):arg_section(0, 2, 'Frame', 'th-large')}">
						<div data-style="display:inline-block; ${args->a_css_3:html:input_type(css):input_props('with_responsive=1'):arg_name(Text color):arg_section(5, 4, 'Text', 'align-justify')}; padding-bottom:0">
							${p->description:arg_name(Item text):arg_section(5, 2, 'Text', 'align-justify')}
						</div>
					</div>
					${block->button:default(0):arg_name(With button):arg_section(9, 0, 'Button', 'hand-pointer-o')}
					<a data-emarketer-click-target="products ${p->internal_id:html}" href="${p->cart_url:html:arg_name(Link target URL):arg_section(6, 0, 'Link target URL', 'link'):column_tags('url','custom text')}" target="${args->target:html:default(_self):input_type(a_target):arg_name(Open link in):arg_section(6, 1, 'Link target URL', 'link')}" data-style="display:inline-block; position:relative; top:1.3em; text-decoration:none; transition: font-size 0.3s ease; background-color:${args->border_color:html:default(white):input_type(color):arg_name(Border color):arg_section(0, 3, 'Frame', 'th-large')}; ${args->a_css_4:html:input_type(css):input_props('with_responsive=1'):arg_name(Button style):arg_section(9, 2, 'Button', 'hand-pointer-o')}" onmouseenter="var t=this; s=t.style, f=s.fontSize, p=f.match(/^([\d\.]+)(\w+)$/); if (!t._b) t._b=[s.backgroundColor, s.color, f]; s.backgroundColor=t._b[1]; s.color=t._b[0]; if (p) if (!t._p) {s.fontSize=(p[1]*0.9)+p[2]; t._p=1; setTimeout(function() {s.fontSize=t._b[2]; t._p=0;}, 300)}" onmouseleave="var s=this.style, b=this._b; s.backgroundColor=b[0]; s.color=b[1]">
						<div data-style="border:solid 1px; ${args->a_css_5:html:input_type(css):input_props('with_responsive=1'):arg_name(Button style):arg_section(9, 3, 'Button', 'hand-pointer-o')}">
							${args->button_text:arg_name(Button text):arg_section(9, 1, 'Button', 'hand-pointer-o')}
						</div>
					</a>
				</td>
			${end}
		</tr>
	</table>
	${block->pagination:default(0):arg_name(With slider pagination):arg_section(1, 10, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}
	<div id="tsp" class="$table_slider_pagination" slider_id="ts" selected_color="${args->pagination_color_on:html:input_type(color):arg_name(Bullet Selected Color):arg_section(1, 11, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" style="${args->pagination_color:html:input_type(css):arg_name(Bullet style):arg_section(1, 12, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}"></div>
</div>
```


## Arrows slider with rating



```
<div class="$responsive" data-style="position:relative; margin:auto; ${args->style:html:default('border: none;
text-align: center;
color: rgb(183,41,19);
max-width: 100%;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(0, 0, 'Frame', 'th-large')}" onupdate="
	var
		w=Math.min(ns.joyquery('ancestor::table:limit(1) parent::div parent::div', by_id.ts).get(0).offsetWidth, document.documentElement.clientWidth-1),
		b=12,
		a=ns.joyquery('parent::*>tr>td>*', by_id.ts).get(),
		d=a[0].parentNode,
		t=d.offsetWidth,
		n=Math.max(Math.round((w-b)/(t+b)), Math.min(2, by_id.ts.children.length)),
		T=(w-b)/n-b-parseFloat(d.style.borderLeftWidth)*2;
	for (i=0; i!=a.length; i++) if (a[i].style.display!='inline-block') a[i].style.width=T+'px'
">
	${block->title:default(1):arg_name(With title bar):arg_section(2, 0, 'Title', 'bookmark')}
	<table data-style="width:100%; border-collapse:collapse; border:none; ${args->title_bg:html:default('background-color: rgba(170, 76, 76, 0);
margin-top: 0px;
margin-right: 0;
margin-bottom: 0px;
margin-left: 0px;
font-size: 16px;
text-transform: uppercase;
font-family: "Karla","HelveticaNeue","Helvetica Neue",sans-serif;
font-weight: 500;
color: #4b4f59;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(2, 2, 'Title', 'bookmark')}">
		<tr>
			<td data-style="vertical-align:middle; ${args->title_style:html:default('text-align: center;
padding-top: 0px;
padding-right: 0px;
padding-bottom: 25px;
padding-left: 0px;
font-size: 22px;'):input_type(css):input_props('with_responsive=1'):arg_name(Title style):arg_section(2, 3, 'Title', 'bookmark')}">
				${args->title:default(POPULAR ITEMS):arg_name(Text):arg_section(2, 1, 'Title', 'bookmark')}
			</td>
			${block->with_arrows:default(0):arg_name(With arrow buttons):arg_section(1, 0, 'With slider', 'arrow-right')}
			<td style="width:1px; white-space:nowrap; vertical-align:middle">
				<a id="button_back" class="$flat_btn" style="${args->btn_style:html:input_type(css):arg_name(Arrow button style):arg_section(1, 1, 'With slider', 'arrow-right')}" hover_style="${args->btn_hover_style:html:input_type(css):arg_name('Arrow button style: hover'):arg_section(1, 2, 'With slider', 'arrow-right')}"><</a>
				<a id="button_forward" class="$flat_btn" style="${args->btn_style:html:input_type(css):arg_name(Arrow button style):arg_section(1, 1, 'With slider', 'arrow-right')}" hover_style="${args->btn_hover_style:html:input_type(css):arg_name('Arrow button style: hover'):arg_section(1, 2, 'With slider', 'arrow-right')}">></a>
			</td>
			${block->x:default(0):arg_name(With close button):arg_section(3, 0, 'Close button', 'close')}
			<td style="width:1px; white-space:nowrap; ${args->x_style:html:input_type(css):arg_name(Close button position):arg_section(3, 2, 'Close button', 'close')}">
				${args->x:input_type(dontshowagain):input_props('style=cursor:pointer; vertical-align:middle'):arg_name(Close button):arg_section(3, 1, 'Close button', 'close')}
			</td>
		</tr>
	</table>
	<table style="width:100%; border-collapse:separate; border-spacing:12px 0; margin-bottom:1.2em">
		<tr id="ts" class="$table_slider" data-disabled="${args->with_slider:html:input_type(checkbox):input_props('value_off=1','value_on='):arg_name(Use slider widget):arg_section(1, 4, 'With slider', 'arrow-right'):onchange('if (args.with_slider==1) block.with_arrows = block.pagination = 0')}" style="border:none" for_max_vw="${args->for_max_vw:html:default(always):input_type(css_length):input_props('with_options=always'):arg_name(Slider widget only if screen width is less than or equal to):arg_section(1, 5, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" eq_cell_width="${args->eq_cell_width:html:default(1):input_type(checkbox):input_props('value_off=','value_on=1'):arg_name(Equal cell width):arg_section(0, 1, 'Frame', 'th-large')}" eq_cell_height="1" arrows_line="${args->arrows_line:html:default(-1):input_type(checkbox):input_props('value_off=-1','value_on=0'):arg_name(Arrows in the middle of images):arg_section(1, 9, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" arrow_back_img="${args->arrow_back_img:html:default('https://static.emarketer.com/upload/4035/3256192fabeef23a.png'):input_type(emarketer_media_url):arg_name(Left arrow image):arg_section(1, 6, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" arrow_forward_img="${args->arrow_forward_img:html:default('https://static.emarketer.com/upload/4035/6447f3eea66d7795.png'):input_type(emarketer_media_url):arg_name(Right arrow image):arg_section(1, 7, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" pagination_id="tsp" arrow_back_id="button_back" arrow_forward_id="button_forward" arrows_offset="${args->arrows_offset:html:default(0):input_type(number):arg_name(Slider arrows offset):arg_section(1, 8, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" hide_buttons="${args->hide_buttons:html:input_type(checkbox):input_props('value_off=','value_on=1'):arg_name(Hide arrow buttons when nothing to scroll):arg_section(1, 3, 'With slider', 'arrow-right'):visible_if('block.title-0 && block.with_arrows-0')}">
			${foreach sum_products_week as p order by p->n_viewed desc limit 16}
				<td style="padding:0; text-align:center; background-color:white; border:solid ${args->border_color:html:default(white):input_type(color):arg_name(Border color):arg_section(0, 3, 'Frame', 'th-large')} 1px; ${args->td_style:html:input_type(css):input_props('with_responsive=1'):arg_name(Cell Style):arg_section(0, 4, 'Frame', 'th-large')}">
					<a data-emarketer-click-target="products ${p->internal_id:html}" href="${p->cart_url:html:arg_name(Link target URL):arg_section(6, 0, 'Link target URL', 'link'):column_tags('url','custom text')}" target="${args->target:html:default(_self):input_type(a_target):arg_name(Open link in):arg_section(6, 1, 'Link target URL', 'link')}" data-style="display:block; margin:auto; box-sizing:border-box; width:${args->img_width:html:default('sel(225px, 30vw)'):input_type(css_length):input_props('with_responsive=1'):arg_name(Cell width):arg_section(0, 2, 'Frame', 'th-large')}">
						<img src="${p->image_big_url:html:arg_name(Item image):arg_section(4, 0, 'Image', 'image'):column_tags(image)}" data-style="${args->img_style:html:default('border: double white 1px;
width: auto;
height: auto;
max-height: 140px;
max-width: 140px;'):input_type(css):input_props('with_responsive=1'):arg_name(Image style):arg_section(4, 1, 'Image', 'image')}">
					</a>
					<div data-style="margin:auto; box-sizing:border-box; width:${args->img_width:html:default('sel(225px, 30vw)'):input_type(css_length):input_props('with_responsive=1'):arg_name(Cell width):arg_section(0, 2, 'Frame', 'th-large')}">
						<div data-style="display:inline-block; ${args->a_css:html:default('font-size: 14px;
color: rgb(0,110,204);
text-decoration: inherit;
text-align: center;
float: left;
padding-top: 5px;
padding-right: 0px;
padding-bottom: 5px;
padding-left: 0px;
text-overflow: inherit;
text-transform: none;
width: 100%;
white-space: normal;
max-width: none;'):input_type(css):input_props('with_responsive=1'):arg_name(Text color):arg_section(5, 3, 'Text', 'align-justify')}">
<a style="font-family:Helvetica, Arial !important; text-decoration:none; color:rgb(0,110,204);" href="${p->cart_url:html:arg_name(Link target URL):arg_section(6, 0, 'Link target URL', 'link'):column_tags('url','custom text')}">
							${p->title:arg_name(Item text):arg_section(5, 1, 'Text', 'align-justify')}
</a>
						</div>
					</div>
					${block->rating:default(1):arg_name(With rating):arg_section(7, 0, 'Rating', 'star')}
					<div style="${args->rating_style:html:input_type(css):arg_name(Rating style)}">
						<input class="$rating" value="${p->rank:html:arg_name(Rating):arg_section(7, 1, 'Rating', 'star')}" max="${args->rank_max:html:input_type(number):arg_name(Maximum rating number that corresponds to 100%):arg_section(7, 2, 'Rating', 'star')}">
					</div>
					${block->price:default(1):arg_name(With price):arg_section(8, 0, 'Price', 'tag')}
					<div data-style="margin:auto; box-sizing:border-box; width:${args->img_width:html:default('sel(225px, 30vw)'):input_type(css_length):input_props('with_responsive=1'):arg_name(Cell width):arg_section(0, 2, 'Frame', 'th-large')}">
						${if p->price}
							${if p->sale_price and p->sale_price < p->price}
								<div style="${args->sale_style:html:input_type(css):input_props('with_responsive=1'):arg_name('Price after discount: style'):arg_section(8, 5, 'Price', 'tag')}">
									${args->before_price:arg_name(Text before price):arg_section(8, 2, 'Price', 'tag')}
									${p->sale_price:truncate(2):sprintf($%s):arg_name(Price after discount):arg_section(8, 3, 'Price', 'tag')}
									${args->after_price:arg_name(Text after price):arg_section(8, 1, 'Price', 'tag')}
								</div>
								<div style="${args->price_style:html:default('color: rgba(119, 119, 119, 0.53);
text-decoration: line-through;
font-size: 11px;'):input_type(css):input_props('with_responsive=1'):arg_name('Price before discount: style'):arg_section(8, 6, 'Price', 'tag')}">
									${p->price:truncate(2):sprintf($%s):arg_name(Price before discount):arg_section(8, 4, 'Price', 'tag')}
								</div>
							${end}
							${if not p->sale_price or p->sale_price >= p->price}
								<div style="${args->price_style:html:default('color: rgba(119, 119, 119, 0.53);
text-decoration: line-through;
font-size: 11px;'):input_type(css):input_props('with_responsive=1'):arg_name('Price before discount: style'):arg_section(8, 6, 'Price', 'tag')}">
									${args->before_price:arg_name(Text before price):arg_section(8, 2, 'Price', 'tag')}
									${p->price:truncate(2):sprintf($%s):arg_name(Price before discount):arg_section(8, 4, 'Price', 'tag')}
									${args->after_price:arg_name(Text after price):arg_section(8, 1, 'Price', 'tag')}
								</div>
							${end}
						${end}
					</div>
					<div style="margin:auto; box-sizing:border-box; font-size:1px">
						<div data-style="display:inline-block; background-color:${args->border_color:html:default(white):input_type(color):arg_name(Border color):arg_section(0, 3, 'Frame', 'th-large')}; ${args->a_css_2:html:default('width:100px; height:3px; max-width:80%'):input_type(css):input_props('with_responsive=1'):arg_name(Ruler):arg_section(5, 5, 'Text', 'align-justify')}"></div>
					</div>
					${block->description:default(0):arg_name(With description):arg_section(5, 0, 'Text', 'align-justify')}
					<div data-style="margin:auto; box-sizing:border-box; width:${args->img_width:html:default('sel(225px, 30vw)'):input_type(css_length):input_props('with_responsive=1'):arg_name(Cell width):arg_section(0, 2, 'Frame', 'th-large')}">
						<div data-style="display:inline-block; ${args->a_css_3:html:input_type(css):input_props('with_responsive=1'):arg_name(Text color):arg_section(5, 4, 'Text', 'align-justify')}; padding-bottom:0">
							${p->description:arg_name(Item text):arg_section(5, 2, 'Text', 'align-justify')}
						</div>
					</div>
					${block->button:default(0):arg_name(With button):arg_section(9, 0, 'Button', 'hand-pointer-o')}
					<a data-emarketer-click-target="products ${p->internal_id:html}" href="${p->cart_url:html:arg_name(Link target URL):arg_section(6, 0, 'Link target URL', 'link'):column_tags('url','custom text')}" target="${args->target:html:default(_self):input_type(a_target):arg_name(Open link in):arg_section(6, 1, 'Link target URL', 'link')}" data-style="display:inline-block; position:relative; top:1.3em; text-decoration:none; transition: font-size 0.3s ease; background-color:${args->border_color:html:default(white):input_type(color):arg_name(Border color):arg_section(0, 3, 'Frame', 'th-large')}; ${args->a_css_4:html:input_type(css):input_props('with_responsive=1'):arg_name(Button style):arg_section(9, 2, 'Button', 'hand-pointer-o')}" onmouseenter="var t=this; s=t.style, f=s.fontSize, p=f.match(/^([\d\.]+)(\w+)$/); if (!t._b) t._b=[s.backgroundColor, s.color, f]; s.backgroundColor=t._b[1]; s.color=t._b[0]; if (p) if (!t._p) {s.fontSize=(p[1]*0.9)+p[2]; t._p=1; setTimeout(function() {s.fontSize=t._b[2]; t._p=0;}, 300)}" onmouseleave="var s=this.style, b=this._b; s.backgroundColor=b[0]; s.color=b[1]">
						<div data-style="border:solid 1px; ${args->a_css_5:html:input_type(css):input_props('with_responsive=1'):arg_name(Button style):arg_section(9, 3, 'Button', 'hand-pointer-o')}">
							${args->button_text:arg_name(Button text):arg_section(9, 1, 'Button', 'hand-pointer-o')}
						</div>
					</a>
				</td>
			${end}
		</tr>
	</table>
	${block->pagination:default(0):arg_name(With slider pagination):arg_section(1, 10, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}
	<div id="tsp" class="$table_slider_pagination" slider_id="ts" selected_color="${args->pagination_color_on:html:input_type(color):arg_name(Bullet Selected Color):arg_section(1, 11, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" style="${args->pagination_color:html:input_type(css):arg_name(Bullet style):arg_section(1, 12, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}"></div>
</div>
```


## Quick add to cart



```
<div class="$responsive" data-style="display:inline-block; ${args->style:html:default('color: #777777;
background-color: white;
border: none;
font-size: 12px;
text-align: left;
min-width: 320px;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(0, 1, 'Frame', 'th-large')}">
	${block->title:default(1):arg_name(With title bar):arg_section(2, 0, 'Title', 'bookmark')}
	<table data-style="width:100%; border-collapse:collapse; border:none; ${args->title_bg:html:input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(2, 2, 'Title', 'bookmark')}">
		<tr>
			<td data-style="vertical-align:middle; ${args->title_style:html:default('font-size: 15px;
color: #0477cc;
padding-top: 5px;
padding-right: 0px;
padding-bottom: 0px;
padding-left: 12px;
font-weight: bolder;'):input_type(css):input_props('with_responsive=1'):arg_name(Title style):arg_section(2, 3, 'Title', 'bookmark')}">
				${args->title:default(Frequently bought together):arg_name(Text):arg_section(2, 1, 'Title', 'bookmark')}
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
	<style>
		.st_t .st_plus {display: none !important}
		.st_t td.st_vis ~ td .st_plus {display: block !important}
	</style>
	<table>
		<tr>
			<td>
				<table id="st_t" class="st_t" style="width:100%; border-collapse:collapse; border:none" data-main-style="${args->td_main_style:html:default('cursor:pointer; vertical-align:top; font-weight:bold'):input_type(css):arg_name(Style - main):arg_section(13, 1, 'Checkbox line', 'check-square')}" data-sec-style="${args->td_sec_style:html:default('cursor:pointer; vertical-align:top'):input_type(css):arg_name(Style - secondary):arg_section(13, 2, 'Checkbox line', 'check-square')}" data-price-style="${args->td_price_style:html:default('color:rgb(4, 119, 204)'):input_type(css):arg_name(Style - price):arg_section(13, 3, 'Checkbox line', 'check-square')}">
					<tr class="$table_slider" data-disabled="${args->with_slider:html:default(1):input_type(checkbox):input_props('value_off=1','value_on='):arg_name(Use slider widget):arg_section(1, 0, 'With slider', 'arrow-right'):onchange('block.with_arrows=args.with_slider!=1')}" style="border:none; max-width:${args->width:html:default(600px):input_type(css_length):input_props('with_options=none'):arg_name(Widget maximum width):arg_section(0, 0, 'Frame', 'th-large')}" for_max_vw="${args->for_max_vw:html:input_type(css_length):input_props('with_options=always'):arg_name(Slider widget only if screen width is less than or equal to):arg_section(1, 1, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" eq_cell_width="${args->eq_cell_width:html:default(1):input_type(checkbox):input_props('value_off=','value_on=1'):arg_name(Equal cell width):arg_section(0, 2, 'Frame', 'th-large')}" eq_cell_height="${args->eq_cell_height:html:default(1):input_type(checkbox):input_props('value_off=','value_on=1'):arg_name(Equal rows height):arg_section(0, 3, 'Frame', 'th-large')}" arrow_back_img="${args->arrow_back_img:html:input_type(emarketer_media_url):arg_name(Left arrow image):arg_section(1, 2, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" arrow_forward_img="${args->arrow_forward_img:html:input_type(emarketer_media_url):arg_name(Right arrow image):arg_section(1, 3, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" arrow_back_id="button_back" arrow_forward_id="button_forward">
						${foreach products_interactions as p order by p->interaction_time desc limit 1}
							<td data-style="position:relative; ${args->td_style:html:default('text-align: center;
vertical-align: middle;
padding-top: 5px;
padding-right: 10px;
padding-bottom: 5px;
padding-left: 10px;
border: none;
max-width: 130px;
min-width: 110px;
width: 110px;'):input_type(css):input_props('with_responsive=1'):arg_name(Cell style):arg_section(0, 4, 'Frame', 'th-large')}">
								<span>
									<input class="st_internal_id" type="hidden" value="${p->internal_id:html}" data-main="1">
									<a data-emarketer-click-target="products ${p->internal_id:html}" href="${p->cart_url:html:arg_name(Link target URL):arg_section(7, 0, 'Link target URL', 'link'):column_tags('url','custom text')}" target="${args->target:html:default(_self):input_type(a_target):arg_name(Open link in):arg_section(7, 1, 'Link target URL', 'link')}" style="${args->link_style:html:default('font-size: 0px;'):input_type(css):arg_name(Link style):arg_section(6, 1, 'Product name', 'text-height')}">
										<img src="${p->image_big_url:html:arg_name(Item image):arg_section(5, 0, 'Image', 'image'):column_tags(image)}" data-style="${args->main_img_style:html:default('border: double white 5px;
width: sel(auto, auto);
height: sel(auto, auto);
max-width: 100px;
max-height: 100px;'):input_type(css):input_props('with_responsive=1'):arg_name(Main image style):arg_section(5, 1, 'Image', 'image')}" onerror="this.parentNode.parentNode.style.display='none'">
									</a>
								</span>
								<a data-emarketer-click-target="products ${p->internal_id:html}" href="${p->cart_url:html:arg_name(Link target URL):arg_section(7, 0, 'Link target URL', 'link'):column_tags('url','custom text')}" target="${args->target:html:default(_self):input_type(a_target):arg_name(Open link in):arg_section(7, 1, 'Link target URL', 'link')}" style="${args->link_style:html:default('font-size: 0px;'):input_type(css):arg_name(Link style):arg_section(6, 1, 'Product name', 'text-height')}">
									<div class="st_title">${p->title:arg_name(Product name):arg_section(6, 0, 'Product name', 'text-height')}</div>
								</a>
								${block->n_viewed:default(0):arg_name(With site statistics):arg_section(8, 0, 'Site statistics', 'bar-chart')}
								<div>${args->n_viewed_text:default('

									<div'):arg_name(Text):arg_section(8, 1, 'Site statistics', 'bar-chart')} ${foreach recom_products_goal_goal_for_last as p where (p->image_small_url IS NOT NULL AND p->image_small_url!='') limit 1}${s->n_viewed:arg_name(Number):arg_section(8, 2, 'Site statistics', 'bar-chart')}${end}</div>
								<div>
									${block->price:default(1):arg_name(With price):arg_section(9, 0, 'Second line', 'text-height')}
									<div style="${args->price_style:html:default('margin-top: 0.4em;
font-size: 0px;'):input_type(css):arg_name(Price style):arg_section(9, 4, 'Second line', 'text-height')}">
										${if p->price}
											${args->before_price:arg_name(Text before price):arg_section(9, 1, 'Second line', 'text-height')}
											${if p->sale_price}
												<span class="st_price">
													${p->sale_price:truncate(2):sprintf($%s):arg_name(Price):arg_section(9, 2, 'Second line', 'text-height')}
												</span>
												<div style="${args->sale_style:html:default('color:gray; text-decoration:line-through; font-size:85%'):input_type(css):input_props('with_responsive=1'):arg_name('Price before discount: style'):arg_section(9, 6, 'Second line', 'text-height')}">
													${p->price:truncate(2):sprintf($%s):arg_name(Price):arg_section(9, 5, 'Second line', 'text-height')}
												</div>
											${end}
											${if not p->sale_price}
												<span class="st_price">
													${p->price:truncate(2):sprintf($%s):arg_name(Price):arg_section(9, 5, 'Second line', 'text-height')}
												</span>
											${end}
											${args->after_price:arg_name(Text after price):arg_section(9, 3, 'Second line', 'text-height')}
										${end}
									</div>
									${block->rating:default(0):arg_name(With rating):arg_section(9, 7, 'Second line', 'text-height')}
									<span style="display:block; ${args->rating_style:html:default('margin-top:0'):input_type(css):arg_name(Rating block style):arg_section(9, 10, 'Second line', 'text-height')}">
										<input class="$rating" value="${p->sale_price:html:arg_name(Rating):arg_section(9, 8, 'Second line', 'text-height')}" max="${args->rank_max:html:default(5000):input_type(number):arg_name(Maximum rating number that corresponds to 100%):arg_section(9, 9, 'Second line', 'text-height')}">
									</span>
								</div>
							</td>
						${end}

						${foreach recom_products_goal_goal_for_last as p where (p->image_small_url IS NOT NULL AND p->image_small_url!='') limit 1}
							<td data-style="position:relative; ${args->td_style:html:default('text-align: center;
vertical-align: middle;
padding-top: 5px;
padding-right: 10px;
padding-bottom: 5px;
padding-left: 10px;
border: none;
max-width: 130px;
min-width: 110px;
width: 110px;'):input_type(css):input_props('with_responsive=1'):arg_name(Cell style):arg_section(0, 4, 'Frame', 'th-large')}">
								<span>
									<div class="st_plus" style="position:absolute; top:50%; left:-0.5em; width:1em; height:1em; line-height:1em; margin-top:-0.5em; text-align: center; ${args->plus_style:html:default('color:gray; font-size:26px'):input_type(css):arg_name(Plus sign style):arg_section(10, 0, 'Plus sign', 'plus')}">+</div>
									<input class="st_internal_id" type="hidden" value="${p->internal_id:html}">
									<a data-emarketer-click-target="products ${p->internal_id:html}" href="${p->cart_url:html:arg_name(Link target URL):arg_section(7, 0, 'Link target URL', 'link'):column_tags('url','custom text')}" target="${args->target:html:default(_self):input_type(a_target):arg_name(Open link in):arg_section(7, 1, 'Link target URL', 'link')}" style="${args->link_style:html:default('font-size: 0px;'):input_type(css):arg_name(Link style):arg_section(6, 1, 'Product name', 'text-height')}">
										<img src="${p->image_big_url:html:arg_name(Item image):arg_section(5, 0, 'Image', 'image'):column_tags(image)}" data-style="${args->img_style:html:default('border: double white 5px;
width: sel(auto, auto);
height: sel(auto, auto);
max-height: 100px;
max-width: 100px;'):input_type(css):input_props('with_responsive=1'):arg_name(Item image style):arg_section(5, 2, 'Image', 'image')}" onerror="this.parentNode.parentNode.style.display='none'">
									</a>
								</span>
								<a data-emarketer-click-target="products ${p->internal_id:html}" href="${p->cart_url:html:arg_name(Link target URL):arg_section(7, 0, 'Link target URL', 'link'):column_tags('url','custom text')}" target="${args->target:html:default(_self):input_type(a_target):arg_name(Open link in):arg_section(7, 1, 'Link target URL', 'link')}" style="${args->link_style:html:default('font-size: 0px;'):input_type(css):arg_name(Link style):arg_section(6, 1, 'Product name', 'text-height')}">
									<div class="st_title">${p->title:arg_name(Product name):arg_section(6, 0, 'Product name', 'text-height')}</div>
								</a>
								${block->n_viewed:default(0):arg_name(With site statistics):arg_section(8, 0, 'Site statistics', 'bar-chart')}
								<div>${args->n_viewed_text:default('

									<div'):arg_name(Text):arg_section(8, 1, 'Site statistics', 'bar-chart')} ${foreach sum_products_all as s where s->internal_id = p->internal_id limit 1}${s->n_viewed:arg_name(Number):arg_section(8, 2, 'Site statistics', 'bar-chart')}${end}</div>
								<div>
									${block->price:default(1):arg_name(With price):arg_section(9, 0, 'Second line', 'text-height')}
									<div style="${args->price_style:html:default('margin-top: 0.4em;
font-size: 0px;'):input_type(css):arg_name(Price style):arg_section(9, 4, 'Second line', 'text-height')}">
										${if p->price}
											${args->before_price:arg_name(Text before price):arg_section(9, 1, 'Second line', 'text-height')}
											${if p->sale_price}
												<span class="st_price">
													${p->sale_price:truncate(2):sprintf($%s):arg_name(Price):arg_section(9, 2, 'Second line', 'text-height')}
												</span>
												<div style="${args->sale_style:html:default('color:gray; text-decoration:line-through; font-size:85%'):input_type(css):input_props('with_responsive=1'):arg_name('Price before discount: style'):arg_section(9, 6, 'Second line', 'text-height')}">
													${p->price:truncate(2):sprintf($%s):arg_name(Price):arg_section(9, 5, 'Second line', 'text-height')}
												</div>
											${end}
											${if not p->sale_price}
												<span class="st_price">
													${p->price:truncate(2):sprintf($%s):arg_name(Price):arg_section(9, 5, 'Second line', 'text-height')}
												</span>
											${end}
											${args->after_price:arg_name(Text after price):arg_section(9, 3, 'Second line', 'text-height')}
										${end}
									</div>
									${block->rating:default(0):arg_name(With rating):arg_section(9, 7, 'Second line', 'text-height')}
									<span style="display:block; ${args->rating_style:html:default('margin-top:0'):input_type(css):arg_name(Rating block style):arg_section(9, 10, 'Second line', 'text-height')}">
										<input class="$rating" value="${p->sale_price:html:arg_name(Rating):arg_section(9, 8, 'Second line', 'text-height')}" max="${args->rank_max:html:default(5000):input_type(number):arg_name(Maximum rating number that corresponds to 100%):arg_section(9, 9, 'Second line', 'text-height')}">
									</span>
								</div>
							</td>
						${end}
					</tr>
				</table>
			</td>
			<td style="vertical-align:top; white-space:nowrap">
				<div>
					<span style="${args->tot_text_style:html:default('font-weight: normal;
font-size: 13px;'):input_type(css):arg_name(Total price text style):arg_section(11, 8, 'Add to cart button', 'mouse-pointer')}">
						${args->tot_text:default('Total price:'):arg_name(Total price text):arg_section(11, 7, 'Add to cart button', 'mouse-pointer')}
					</span>
					<span id="st_tot" style="${args->tot_style:html:default('font-weight: normal;
font-size: 20px;
color: #B1240B;'):input_type(css):arg_name(Total price style):arg_section(11, 9, 'Add to cart button', 'mouse-pointer')}"></span>
				</div>
				<button  id="st_btn1" class="$flat_btn" style="${args->add_btn_style:html:default('width: 120px;
display: block;
padding: 8px;
outline: none;
border: none;
font-size: 13px;
font-weight: normal;
border-radius: 3px;
color: white;
background-color: #0477cc;
text-align: center;
margin-top: 13px;
margin-right: 0px;
margin-bottom: 0px;
margin-left: 0px;'):input_type(css):arg_name(Button style):arg_section(11, 4, 'Add to cart button', 'mouse-pointer')}" hover_style="${args->add_btn_hover_style:html:default('color: white;
background-color: rgb(49, 143, 237);'):input_type(css):arg_name('Button style: hover'):arg_section(11, 5, 'Add to cart button', 'mouse-pointer')}" data-alt-text-1="${args->add_btn_text_1:html:default(Add to cart):arg_name(Alt. Text for 1 item):arg_section(11, 1, 'Add to cart button', 'mouse-pointer')}" data-alt-text-2="${args->add_btn_text_2:html:default(Add both to cart):arg_name(Alt. Text for 2 items):arg_section(11, 2, 'Add to cart button', 'mouse-pointer')}" data-alt-text-3="${args->add_btn_text_3:html:default(Add all three to cart):arg_name(Alt. Text for 3 items):arg_section(11, 3, 'Add to cart button', 'mouse-pointer')}" onclick="
					var list = this._list;
					${args->js:html:default('AddProductsToBasket(list.join());'):input_type(source_javascript):arg_name(Add button Javascript Action):arg_section(11, 6, 'Add to cart button', 'mouse-pointer')}
				">
					${args->add_btn_text:default(Add all to cart):arg_name(Text):arg_section(11, 0, 'Add to cart button', 'mouse-pointer')}
				</button>
				${block->with_fav:default(1):arg_name(With Add to favorites):arg_section(12, 0, 'Add to favorites', 'heart')}
				<div>
					<button id="st_btn2" class="$flat_btn" style="${args->fvt_btn_style:html:default('width: 120px;
display: block;
margin-top: 0.5em;
padding: 8px;
outline: none;
border: none;
font-size: 13px;
font-weight: normal;
border-radius: 3px;
color: white;
background-color: rgba(7, 2, 2, 0.38);
text-align: center;'):input_type(css):arg_name(Button style):arg_section(12, 5, 'Add to favorites', 'heart')}" hover_style="${args->fvt_btn_hover_style:html:default('color: white;
background-color: rgba(119, 119, 119, 0.76);'):input_type(css):arg_name('Button style: hover'):arg_section(12, 6, 'Add to favorites', 'heart')}" data-added-msg="${args->added:html:default(Products added to wishlist):arg_name(Added to wishlist message):arg_section(12, 3, 'Add to favorites', 'heart')}" data-rm-msg="${args->rm_msg:html:default(Products removed from wishlist):arg_name(Remove from wishlist message):arg_section(12, 4, 'Add to favorites', 'heart')}" data-rm-text="${args->rm:html:default(Remove from wishlist):arg_name(Remove Text):arg_section(12, 2, 'Add to favorites', 'heart')}">
						${args->fvt_btn_text:default(Add to wishlist):arg_name(Text):arg_section(12, 1, 'Add to favorites', 'heart')}
					</button>
				</div>
			</td>
		</tr>
	</table>
	<table style="border-collapse:collapse; border:none; ${args->table_style:html:default('margin:5px 5px 5px 15px'):input_type(css):arg_name(Margin):arg_section(13, 0, 'Checkbox line', 'check-square')}" ontplready="
		var tr=by_id.st_tr, st_t=by_id.st_t, tbody=st_t.children[0], n=tbody.children[0].children.length, st_btn1=by_id.st_btn1, st_btn2=by_id.st_btn2;
		if (tr) for (var i=0; i!=n; i++)
		{	tr.set_length(n);
			function gt(i, name)
			{	return ns.joyquery('td:nth-child('+(i+1)+') [class~=\'st_'+name+'\']', tbody).get(0);
			}
			var t_by_id = tr[i].by_id, is_main=gt(i, 'internal_id').getAttribute('data-main'), def_t=st_btn1.innerHTML;

			t_by_id.st_for_internal_id.value = gt(i, 'internal_id').value;
			t_by_id.st_for_title.innerHTML = gt(i, 'title').innerHTML;
			t_by_id.st_for_price.innerHTML = (gt(i, 'price') || {}).innerHTML || '';

			tr[i].elem.style.cssText = st_t.getAttribute(is_main ? 'data-main-style' : 'data-sec-style');
			t_by_id.st_for_price.style.cssText = st_t.getAttribute('data-price-style');

			function ch()
			{	var tot=0, fmt='~`', d, v, list=[], vis=0;
				for (var i=0; i!=tr.length; i++)
				{	var t_by_id = tr[i].by_id;
					fmt = t_by_id.st_for_price.textContent.replace(/[\d\.]+/, function(m) {d=+m; return '~`'});
					v = t_by_id.st_for_internal_id.checked;
					if (v)
					{	tot += d||0;
						list.push(t_by_id.st_for_internal_id.value);
						vis++;
					}
					for (var e, it=ns.joyquery('td:nth-child('+(i+1)+')', tbody); e=it();)
					{	e.className = v ? 'st_vis' : '';
						_S_T.new_elem(e).add_style({opacity: +v, display: v ? '' : 'none'}, {});
					}
				}
				by_id.st_tot.textContent = fmt.replace('~`', tot.toFixed(2));
				st_btn1._list = list;
				st_btn1.style.display = vis ? '' : 'none';
				var alt_t = st_btn1.getAttribute('data-alt-text-'+vis);
				st_btn1.innerHTML = alt_t || def_t;
				if (st_btn2) st_btn2.style.display = vis ? '' : 'none';
			}
			this.onclick = ch;
			setTimeout(ch, 0);

			if (st_btn2)
			{	var wl=false, wl_def_t=st_btn2.innerHTML, wl_rm_t=st_btn2.getAttribute('data-rm-text');
				st_btn2.onclick = function()
				{	var vis=0;
					for (var i=0; i!=tr.length; i++)
					{	var t_by_id = tr[i].by_id;
						if (t_by_id.st_for_internal_id.checked)
						{	_S_T.push([wl ? 'Product Liked' : 'Product Unliked', t_by_id.st_for_internal_id.value]);
							vis++;
						}
					}
					if (vis)
					{	st_btn2.innerHTML = (wl=!wl) ? wl_rm_t : wl_def_t;
						new _S_T.ElemsAnnotator('info').add(this, this.getAttribute(wl ? 'data-added-msg' : 'data-rm-msg')).annotate(3000);
					}
				};
			}
		}
	">
		<tr id="st_tr" class="$repeat-elem">
			<td style="width:1px"><input id="st_for_internal_id" type="checkbox" checked="1"></td>
			<td style="padding:0 5px" id="st_for_title" onClick="var i=this.previousElementSibling.firstChild; i.checked=!i.checked"></td>
			<td id="st_for_price" onClick="this.previousElementSibling.onclick()"></td>
		</tr>
	</table>
</div>
```


## Horizontal display



```
<div class="$responsive" style="${args->a_style3:html:default('color: #444;
font-family: arial,sans-serif;
font-size: 12px;
line-height: 18px;
max-width: 450px;'):input_type(css):arg_name(Style):arg_section(0, 0, 'Box', 'th-large')}">
	<div style="${args->a_style:html:default('font-size: 15px;
text-align: left;
padding-top: 5px;
padding-right: 0;
padding-bottom: 5px;
padding-left: 15px;'):input_type(css):arg_name(Style):arg_section(1, 0, 'Title', 'bookmark')}">
		${args->line:default('<div style="text-align: center;"><strong>Popular Items</strong></div>
'):arg_name(Text):arg_section(1, 1, 'Title', 'bookmark')}
	</div>
	<div style="display:flex; flex-wrap:wrap; justify-content:space-between; align-items:stretch">
		${foreach recom_products as p limit 12}
			<a data-emarketer-click-target="products ${p->internal_id:html}" href="${p->cart_url:html:default('p->cart_url')}" style="display:block; position:relative; ${args->a_style4:html:default('margin-top: 0px;
margin-right: 21px;
margin-bottom: 20px;
margin-left: 21px;
border: -43px solid #bababa;
text-align: center;
width: 180px;
box-shadow: 0px 0px 20px rgba(0, 0, 0, 0.09);
text-decoration: none;'):input_type(css):arg_name(Cell):arg_section(2, 3, 'Cell', 'bars')}">
				<div style="margin-bottom:4em; ${args->a_style40:html:default('					padding:10px 15px
				'):input_type(css):arg_name(Cell):arg_section(2, 4, 'Cell', 'bars')}">
					<img src="${p->image_big_url:html:default('p->image_big_url')}" alt="${p->title:html}" title="${p->title:html}" style="width:auto; height:auto; ${args->a_style7:html:default('max-height: 100px;
margin-bottom: 10px;
border: none;
max-width: 100px;
height: auto;
width: auto;'):input_type(css):arg_name(Product image style):arg_section(2, 2, 'Cell', 'bars')}">
					<div style="${args->a_style5:html:default('color: #b72913;
font-size: 14px;
font-weight: bold;
text-align: center;'):input_type(css):arg_name(Product name):arg_section(2, 0, 'Cell', 'bars')}">
						${p->title}
						<div>
							${if p->sale_price > 0 and p->sale_price < p->price}
								<span style="${args->a_style50:html:default('text-decoration: line-through;
color: #777777;
font-weight: 300;'):input_type(css):arg_name(Product name):arg_section(2, 1, 'Cell', 'bars')}">
									${p->price:sprintf('$%s')}
								</span>
								${p->sale_price:sprintf('$%s')}
							${end}
							${if p->sale_price <= 0 or p->sale_price >= p->price}
								${p->price:sprintf('$%s')}
							${end}
						</div>
					</div>
				</div>
				<div style="position:absolute; width:100%; bottom:10px; text-align:center">
					<div style="display:inline-block; ${args->a_style6:html:default('background-color: #006ecc;
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
						${args->line3:default(View Now):arg_name(Text):arg_section(3, 0, 'Button', 'bars')}
					</div>
				</div>
			</a>
		${end}
	</div>
</div>
```


## Slider widget



```
<div class="$responsive" data-style="position:relative; margin:auto; ${args->style:html:default('border: none;
text-align: center;
color: rgb(183,41,19);
max-width: 100%;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(0, 0, 'Frame', 'th-large')}" onupdate="
	var
		w=Math.min(ns.joyquery('ancestor::table:limit(1) parent::div parent::div', by_id.ts).get(0).offsetWidth, document.documentElement.clientWidth-1),
		b=12,
		a=ns.joyquery('parent::*>tr>td>*', by_id.ts).get(),
		d=a[0].parentNode,
		t=d.offsetWidth,
		n=Math.max(Math.round((w-b)/(t+b)), Math.min(2, by_id.ts.children.length)),
		T=(w-b)/n-b-parseFloat(d.style.borderLeftWidth)*2;
	for (i=0; i!=a.length; i++) if (a[i].style.display!='inline-block') a[i].style.width=T+'px'
">
	${block->title:default(1):arg_name(With title bar):arg_section(2, 0, 'Title', 'bookmark')}
	<table data-style="width:100%; border-collapse:collapse; border:none; ${args->title_bg:html:default('background-color: rgba(170, 76, 76, 0);
margin-top: 0px;
margin-right: 0;
margin-bottom: 0px;
margin-left: 0px;
font-size: 16px;
text-transform: uppercase;
font-family: "Karla","HelveticaNeue","Helvetica Neue",sans-serif;
font-weight: 500;
color: #4b4f59;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(2, 4, 'Title', 'bookmark')}">
		<tr>
			<td data-style="vertical-align:middle; ${args->title_style:html:default('text-align: center;
padding-top: 0px;
padding-right: 0px;
padding-bottom: 25px;
padding-left: 0px;'):input_type(css):input_props('with_responsive=1'):arg_name(Title style):arg_section(2, 6, 'Title', 'bookmark')}">
				${args->title:default(FREQUENTLY BOUGHT TOGETHER):arg_name(Text):arg_section(2, 2, 'Title', 'bookmark')}
			</td>
			${block->with_arrows:default(0):arg_name(With arrow buttons):arg_section(1, 0, 'With slider', 'arrow-right')}
			<td style="width:1px; white-space:nowrap; vertical-align:middle">
				<a id="button_back" class="$flat_btn" style="${args->btn_style:html:input_type(css):arg_name(Arrow button style):arg_section(1, 1, 'With slider', 'arrow-right')}" hover_style="${args->btn_hover_style:html:input_type(css):arg_name('Arrow button style: hover'):arg_section(1, 2, 'With slider', 'arrow-right')}"><</a>
				<a id="button_forward" class="$flat_btn" style="${args->btn_style:html:input_type(css):arg_name(Arrow button style):arg_section(1, 1, 'With slider', 'arrow-right')}" hover_style="${args->btn_hover_style:html:input_type(css):arg_name('Arrow button style: hover'):arg_section(1, 2, 'With slider', 'arrow-right')}">></a>
			</td>
			${block->x:default(0):arg_name(With close button):arg_section(3, 0, 'Close button', 'close')}
			<td style="width:1px; white-space:nowrap; ${args->x_style:html:input_type(css):arg_name(Close button position):arg_section(3, 2, 'Close button', 'close')}">
				${args->x:input_type(dontshowagain):input_props('style=cursor:pointer; vertical-align:middle'):arg_name(Close button):arg_section(3, 1, 'Close button', 'close')}
			</td>
		</tr>
	</table>
	<table style="width:100%; border-collapse:separate; border-spacing:12px 0; margin-bottom:1.2em">
		<tr id="ts" class="$table_slider" data-disabled="${args->with_slider:html:input_type(checkbox):input_props('value_off=1','value_on='):arg_name(Use slider widget):arg_section(1, 4, 'With slider', 'arrow-right'):onchange('if (args.with_slider==1) block.with_arrows = block.pagination = 0')}" style="border:none" for_max_vw="${args->for_max_vw:html:default(always):input_type(css_length):input_props('with_options=always'):arg_name(Slider widget only if screen width is less than or equal to):arg_section(1, 5, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" eq_cell_width="${args->eq_cell_width:html:default(1):input_type(checkbox):input_props('value_off=','value_on=1'):arg_name(Equal cell width):arg_section(0, 1, 'Frame', 'th-large')}" eq_cell_height="1" arrows_line="${args->arrows_line:html:default(-1):input_type(checkbox):input_props('value_off=-1','value_on=0'):arg_name(Arrows in the middle of images):arg_section(1, 9, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" arrow_back_img="${args->arrow_back_img:html:default('https://static.emarketer.com/upload/4035/3256192fabeef23a.png'):input_type(emarketer_media_url):arg_name(Left arrow image):arg_section(1, 6, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" arrow_forward_img="${args->arrow_forward_img:html:default('https://static.emarketer.com/upload/4035/6447f3eea66d7795.png'):input_type(emarketer_media_url):arg_name(Right arrow image):arg_section(1, 7, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" pagination_id="tsp" arrow_back_id="button_back" arrow_forward_id="button_forward" arrows_offset="${args->arrows_offset:html:default(0):input_type(number):arg_name(Slider arrows offset):arg_section(1, 8, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" hide_buttons="${args->hide_buttons:html:input_type(checkbox):input_props('value_off=','value_on=1'):arg_name(Hide arrow buttons when nothing to scroll):arg_section(1, 3, 'With slider', 'arrow-right'):visible_if('block.title-0 && block.with_arrows-0')}">
			${foreach sum_last_products_interactions_cross_all as p where p->interaction_status IN ('viewed') order by p->n_goal desc limit 16}
				<td style="padding:0; text-align:center; background-color:white; border:solid ${args->border_color:html:default(white):input_type(color):arg_name(Border color):arg_section(0, 3, 'Frame', 'th-large')} 1px; ${args->td_style:html:input_type(css):input_props('with_responsive=1'):arg_name(Cell Style):arg_section(0, 4, 'Frame', 'th-large')}">
					<a data-emarketer-click-target="products ${p->internal_id:html}" href="${p->cart_url:html:arg_name(Link target URL):arg_section(6, 0, 'Link target URL', 'link'):column_tags('url','custom text')}" target="${args->target:html:default(_self):input_type(a_target):arg_name(Open link in):arg_section(6, 1, 'Link target URL', 'link')}" data-style="display:block; margin:auto; box-sizing:border-box; width:${args->img_width:html:default('sel(230px, 30vw)'):input_type(css_length):input_props('with_responsive=1'):arg_name(Cell width):arg_section(0, 2, 'Frame', 'th-large')}">
						<img src="${p->image_big_url:html:arg_name(Item image):arg_section(4, 0, 'Image', 'image'):column_tags(image)}" data-style="${args->img_style:html:default('border: double white 5px;
width: auto;
height: auto;
max-height: 120px;
max-width: 120px;'):input_type(css):input_props('with_responsive=1'):arg_name(Image style):arg_section(4, 1, 'Image', 'image')}">
					</a>
					<div data-style="margin:auto; box-sizing:border-box; width:${args->img_width:html:default('sel(230px, 30vw)'):input_type(css_length):input_props('with_responsive=1'):arg_name(Cell width):arg_section(0, 2, 'Frame', 'th-large')}">
						<div data-style="display:inline-block; ${args->a_css:html:default('font-size: 12px;
color: rgb(0,110,204);
text-decoration: inherit;
text-align: center;
float: left;
padding-top: 5px;
padding-right: 0px;
padding-bottom: 5px;
padding-left: 0px;
text-overflow: inherit;
text-transform: none;
width: 100%;
white-space: normal;
max-width: none;'):input_type(css):input_props('with_responsive=1'):arg_name(Text color):arg_section(5, 3, 'Text', 'align-justify')}">
<a style="font-family:Helvetica, Arial !important; text-decoration:none; color:rgb(0,110,204);" href="${p->cart_url:html:arg_name(Link target URL):arg_section(6, 0, 'Link target URL', 'link'):column_tags('url','custom text')}">
							${p->title:arg_name(Item text):arg_section(5, 1, 'Text', 'align-justify')}
</a>
						</div>
					</div>
					${block->rating:default(1):arg_name(With rating):arg_section(7, 0, 'Rating', 'star')}
					<div style="${args->rating_style:html:input_type(css):arg_name(Rating style)}">
						<input class="$rating" value="${p->rank:html:arg_name(Rating):arg_section(7, 1, 'Rating', 'star')}" max="${args->rank_max:html:input_type(number):arg_name(Maximum rating number that corresponds to 100%):arg_section(7, 2, 'Rating', 'star')}">
					</div>
					${block->price:default(1):arg_name(With price):arg_section(8, 0, 'Price', 'tag')}
					<div data-style="margin:auto; box-sizing:border-box; width:${args->img_width:html:default('sel(230px, 30vw)'):input_type(css_length):input_props('with_responsive=1'):arg_name(Cell width):arg_section(0, 2, 'Frame', 'th-large')}">
						${if p->price}
							${if p->sale_price and p->sale_price < p->price}
								<div style="${args->sale_style:html:input_type(css):input_props('with_responsive=1'):arg_name('Price after discount: style'):arg_section(8, 5, 'Price', 'tag')}">
									${args->before_price:arg_name(Text before price):arg_section(8, 2, 'Price', 'tag')}
									${p->sale_price:truncate(2):sprintf($%s):arg_name(Price after discount):arg_section(8, 3, 'Price', 'tag')}
									${args->after_price:arg_name(Text after price):arg_section(8, 1, 'Price', 'tag')}
								</div>
								<div style="${args->price_style:html:default('color: rgba(119, 119, 119, 0.53);
text-decoration: line-through;
font-size: 11px;'):input_type(css):input_props('with_responsive=1'):arg_name('Price before discount: style'):arg_section(8, 6, 'Price', 'tag')}">
									${p->price:truncate(2):sprintf($%s):arg_name(Price before discount):arg_section(8, 4, 'Price', 'tag')}
								</div>
							${end}
							${if not p->sale_price or p->sale_price >= p->price}
								<div style="${args->price_style:html:default('color: rgba(119, 119, 119, 0.53);
text-decoration: line-through;
font-size: 11px;'):input_type(css):input_props('with_responsive=1'):arg_name('Price before discount: style'):arg_section(8, 6, 'Price', 'tag')}">
									${args->before_price:arg_name(Text before price):arg_section(8, 2, 'Price', 'tag')}
									${p->price:truncate(2):sprintf($%s):arg_name(Price before discount):arg_section(8, 4, 'Price', 'tag')}
									${args->after_price:arg_name(Text after price):arg_section(8, 1, 'Price', 'tag')}
								</div>
							${end}
						${end}
					</div>
					<div style="margin:auto; box-sizing:border-box; font-size:1px">
						<div data-style="display:inline-block; background-color:${args->border_color:html:default(white):input_type(color):arg_name(Border color):arg_section(0, 3, 'Frame', 'th-large')}; ${args->a_css_2:html:default('width:100px; height:3px; max-width:80%'):input_type(css):input_props('with_responsive=1'):arg_name(Ruler):arg_section(5, 5, 'Text', 'align-justify')}"></div>
					</div>
					${block->description:default(0):arg_name(With description):arg_section(5, 0, 'Text', 'align-justify')}
					<div data-style="margin:auto; box-sizing:border-box; width:${args->img_width:html:default('sel(230px, 30vw)'):input_type(css_length):input_props('with_responsive=1'):arg_name(Cell width):arg_section(0, 2, 'Frame', 'th-large')}">
						<div data-style="display:inline-block; ${args->a_css_3:html:input_type(css):input_props('with_responsive=1'):arg_name(Text color):arg_section(5, 4, 'Text', 'align-justify')}; padding-bottom:0">
							${p->description:arg_name(Item text):arg_section(5, 2, 'Text', 'align-justify')}
						</div>
					</div>

${block->button:default(1):arg_name(With button):arg_section(2, 1, 'Title', 'bookmark')}
					<div style="margin-top:0.4em">
						<a data-emarketer-click-target="products ${p->internal_id:html}" onclick="AddProductsToBasket(${p->internal_id:html}); _S_T.push(['Product Added to cart', '${p->internal_id:html}', 'action_id', ${action_id:html}]);" href="javascript:void(0);" data-style="${args->button_style:html:default('display: inline-block;
background-color: rgb(0,110,204);
border-radius: 4px;
padding-top: 2px;
padding-right: 16px;
padding-bottom: 2px;
padding-left: 16px;
color: white;
text-decoration: none;
margin-top: 0px;
margin-right: 0px;
margin-bottom: 0px;
margin-left: 7px;'):input_type(css):input_props('with_responsive=1'):arg_name(Button style):arg_section(2, 5, 'Title', 'bookmark')}">${args->button:default(Add):arg_name('Text', 'Link target URL'):arg_section(2, 3, 'Title', 'bookmark')}</a>

${block->button:default(1):arg_name(With button):arg_section(2, 1, 'Title', 'bookmark')}
					<a data-emarketer-click-target="products ${p->internal_id:html}" href="${p->cart_url:html:arg_name(Link target URL):arg_section(6, 0, 'Link target URL', 'link'):column_tags('url','custom text')}" target="${args->target:html:default(_self):input_type(a_target):arg_name(Open link in):arg_section(6, 1, 'Link target URL', 'link')}" data-style="display:inline-block; position:relative; top:1.3em; text-decoration:none; transition: font-size 0.3s ease; background-color:${args->border_color:html:default(white):input_type(color):arg_name(Border color):arg_section(0, 3, 'Frame', 'th-large')}; ${args->a_css_4:html:input_type(css):input_props('with_responsive=1'):arg_name(Button style):arg_section(9, 1, 'Button', 'hand-pointer-o')}" onmouseenter="var t=this; s=t.style, f=s.fontSize, p=f.match(/^([\d\.]+)(\w+)$/); if (!t._b) t._b=[s.backgroundColor, s.color, f]; s.backgroundColor=t._b[1]; s.color=t._b[0]; if (p) if (!t._p) {s.fontSize=(p[1]*0.9)+p[2]; t._p=1; setTimeout(function() {s.fontSize=t._b[2]; t._p=0;}, 300)}" onmouseleave="var s=this.style, b=this._b; s.backgroundColor=b[0]; s.color=b[1]">
						<div data-style="border:solid 1px; ${args->a_css_5:html:default('display: none;'):input_type(css):input_props('with_responsive=1'):arg_name(Button style):arg_section(9, 2, 'Button', 'hand-pointer-o')}">
							${args->button_text:default(sfdf):arg_name(Button text):arg_section(9, 0, 'Button', 'hand-pointer-o')}
						</div>
					</a>
				</td>
			${end}
		</tr>
	</table>



${block->pagination:default(0):arg_name(With slider pagination):arg_section(1, 10, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}
	<div id="tsp" class="$table_slider_pagination" slider_id="ts" selected_color="${args->pagination_color_on:html:input_type(color):arg_name(Bullet Selected Color):arg_section(1, 11, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" style="${args->pagination_color:html:input_type(css):arg_name(Bullet style):arg_section(1, 12, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}"></div>
</div>
```


## Side bar expendable



```
<div class="$responsive" style="${args->a_style3:html:default('max-width: 250px;
color: #444;
font-family: arial,sans-serif;
font-size: 12px;
line-height: 18px;'):input_type(css):arg_name(Style):arg_section(0, 0, 'Box', 'th-large')}">
	<div style="${args->a_style:html:default('color: #FFF;
font-size: 15px;
text-align: center;
padding-top: 5px;
padding-right: 0;
padding-bottom: 5px;
padding-left: 0;
background: rgb(0, 106, 254);
border-top-left-radius: 0px;
border-top-right-radius: 0px;
border-bottom-right-radius: 0;
border-bottom-left-radius: 0;
margin-top: 15px;
margin-right: 0px;
margin-bottom: 10px;
margin-left: 0px;'):input_type(css):arg_name(Background Color):arg_section(1, 0, 'Title', 'bookmark')}">
		${args->line:default('<span style="color: #FFF;
display: block;
font-size: 15px;
text-align: center;
text-decoration: none;"><strong>RECOMMENDED FOR YOU</strong></span>'):arg_name(Text):arg_section(1, 1, 'Title', 'bookmark')}
	</div>
	<div style="${args->a_style2:html:default('		padding-top: 5px;
		border-bottom-right-radius: 8px;
		border-bottom-left-radius: 8px;
		border-bottom: 1px solid #c1c1c1;
		border-left: 1px solid #c1c1c1;
		border-right: 1px solid #c1c1c1;
		padding: 7px 0 12px 4px;
	'):input_type(css):arg_name(Border):arg_section(0, 1, 'Box', 'th-large')}" data-n="${args->n:html:default(3):input_type(number):input_props('min=1'):arg_name(Initially visible):arg_section(4, 0, 'See More Button', 'eye')}" ontplready="var n=this.getAttribute('data-n'), c=this.children, l=c.length-1; if (l>n) {c[l].style.display=''; while (n!=l) c[n++].style.display='none'}">
		${foreach recom_products as p limit 15}
			<div style="${args->a_style4:html:default('				margin: 0 auto 8px;
				width: 95%;
				border-bottom: 1px solid #eee;
			'):input_type(css):arg_name(Cell):arg_section(2, 4, 'Cell', 'bars')}">
				<div style="${args->a_style5:html:default('					    float: left;
						width: 90px;
						text-align: left;
						font-weight: bold;
						font-size: 12px;
'):input_type(css):arg_name(Product name):arg_section(2, 0, 'Cell', 'bars')}">
					<span ontplready="var t=this.textContent,i=t.indexOf(','); if (i!=-1) this.textContent=t.substr(0,i)">${p->title}</span>
					${if p->sale_price > 0 and p->sale_price < p->price}
						<div style="${args->a_style50:html:default('							color: #9c223f;
							font-size: 11px;
						'):input_type(css):arg_name(Product name):arg_section(2, 1, 'Cell', 'bars')}">
							${args->line2:default(20% Off Each!):arg_name(Discount text):arg_section(2, 2, 'Cell', 'bars')}
						</div>
					${end}
				</div>
				<img src="${p->image_big_url:html:default('p->image_medium_url')}" alt="${p->title:html}" title="${p->title:html}" style="${args->a_style7:html:default('					    height: 87px;
					    width: 87px;
					    float: right;
					    margin-bottom: 10px;
					    border: none;
				'):input_type(css):arg_name(Product image style):arg_section(2, 3, 'Cell', 'bars')}">
				<a data-emarketer-click-target="products ${p->internal_id:html}" href="${p->cart_url:html:default('p->cart_url')}" title="${args->line3:html:default(Add to Cart):arg_name(Tooltip):arg_section(3, 2, 'Button', 'bars')}" style="${args->a_style6:html:default('background-color: rgb(0, 106, 254);
border-bottom: 1px solid #b4a600;
border-left: 1px solid rgb(0, 106, 254);
border-right: 1px solid #d5c614;
border-top: 1px solid rgb(0, 106, 254);
color: white;
font-size: 14px;
padding-top: 5px;
padding-right: 20px;
padding-bottom: 5px;
padding-left: 20px;
-webkit-appearance: none;
text-decoration: none;
clear: both;
display: block;
width: 56px;
margin-top: 10px;
margin-right: auto;
margin-bottom: 10px;
margin-left: auto;
white-space: nowrap;'):input_type(css):arg_name(Style):arg_section(3, 1, 'Button', 'bars')}">
					${args->line3:default(Buy Now):arg_name(Text):arg_section(3, 0, 'Button', 'bars')}
				</a>
			</div>
		${end}
		<div style="display:none; text-align:center">
			<a href="javascript:" onclick="var c=this.parentNode.parentNode.children, i=0; while (c[i]) c[i++].style.display=''; c[--i].style.display='none'" style="${args->a_style9:html:default('font-size: 120%;
color: #005274;
text-decoration: none;'):input_type(css):arg_name(Style):arg_section(4, 2, 'See More Button', 'eye')}">
				${args->seemore:default(See More):arg_name(Text):arg_section(4, 1, 'See More Button', 'eye')}
			</a>
		</div>
	</div>
</div>
```


## Side bar slider



```
<div class="$responsive" data-style="display:inline-block; ${args->style:html:default('color: black;
background-color: white;
border: solid thin rgb(68, 98, 146);'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(0, 0, 'Frame', 'th-large')}">
			${block->title:default(1):arg_name(With title bar):arg_section(2, 0, 'Title', 'bookmark')}
			<div style="${args->title_style:html:default('background-color: rgb(68, 98, 146);
color: white;
margin-top: 0px;
margin-right: 0px;
margin-bottom: 10px;
margin-left: 0px;'):input_type(css):arg_name(Style):arg_section(2, 2, 'Title', 'bookmark')}">
				${block->x:default(0):arg_name(With close button):arg_section(3, 0, 'Close button', 'close')}
				<div style="float:right; cursor:pointer; margin:0 0 .3em .3em">
					${args->x:input_type(dontshowagain):arg_name(Close button):arg_section(3, 1, 'Close button', 'close')}
				</div>
				${args->title:default('<div style="text-align: center;"><span style="font-size:20px;"><strong>Just For You</strong></span></div>
'):arg_name(Text):arg_section(2, 1, 'Title', 'bookmark')}
				<div style="clear:both"></div>
			</div>
			<table style="height:100%; border-collapse:collapse">
				<tbody class="$table_slider" data-disabled="${args->with_slider:html:default():input_type(checkbox):input_props('value_off=1','value_on='):arg_name(Use slider widget):arg_section(1, 0, 'With slider', 'arrow-right')}" style="border:none; height:${args->height:html:default(550px):input_type(css_length):arg_name(Widget height):arg_section(1, 1, 'With slider', 'arrow-right')}" arrow_back_img="${args->arrow_back_img:html:default('https://static.emarketer.com/upload/362/bf7c62b881cc193b.png'):input_type(emarketer_media_url):arg_name(Up arrow image):arg_section(1, 2, 'With slider', 'arrow-right')}" arrow_forward_img="${args->arrow_forward_img:html:default('https://static.emarketer.com/upload/362/a6c8232e6c9d2182.png'):input_type(emarketer_media_url):arg_name(Down arrow image):arg_section(1, 3, 'With slider', 'arrow-right')}">
					${foreach sum_products_week as p order by p->n_goal desc limit 5}
						<tr style="border:none">
							<td data-style="${args->td_style:html:default('text-align: center;
vertical-align: top;
padding: 5px;
border: none;
width: 200px;'):input_type(css):input_props('with_responsive=1'):arg_name(Cell style):arg_section(0, 1, 'Frame', 'th-large')}">
								<a data-emarketer-click-target="products ${p->internal_id:html}" href="${p->guide_url:html:arg_name(Link target URL):arg_section(6, 0, 'Link target URL', 'link'):column_tags('url','custom text')}" target="${args->target:html:default(_self):input_type(a_target):arg_name(Open link in):arg_section(6, 1, 'Link target URL', 'link')}" style="${args->link_style:html:default('color:'):input_type(css):arg_name(Link style):arg_section(5, 2, 'Product name', 'text-height')}">
									<img src="${p->image_big_url:html:arg_name(Item image):arg_section(4, 0, 'Image', 'image'):column_tags(image)}" data-style="${args->img_style:html:default('border:double white 5px; width:auto; height:auto; max-width:sel(130px, 20vw); max-height:sel(130px, 20vw)'):input_type(css):input_props('with_responsive=1'):arg_name(Item image style):arg_section(4, 1, 'Image', 'image')}" onerror="this.parentNode.parentNode.parentNode.style.display='none'">
									${block->p_title:default(1):arg_name(With product name):arg_section(5, 0, 'Product name', 'text-height')}
									<div>${p->title:arg_name(Product name):arg_section(5, 1, 'Product name', 'text-height')}</div>
								</a>
								${block->n_viewed:default(0):arg_name(With site statistics):arg_section(7, 0, 'Site statistics', 'bar-chart')}
								<div>${args->n_viewed_text:arg_name(Text):arg_section(7, 1, 'Site statistics', 'bar-chart')} ${foreach sum_products_all as s where s->internal_id = p->internal_id limit 1}${s->n_viewed:arg_name(Number):arg_section(7, 2, 'Site statistics', 'bar-chart')}${end}</div>
								<div style="margin-top:0.4em">
									${block->price:default(1):arg_name(With price):arg_section(8, 0, 'Second line', 'text-height'):onchange('args.rating_style = block.price ? ''float:right'' : '''';')}
									<div style="${args->price_style:html:default('float:left'):input_type(css):arg_name(Price position):arg_section(8, 4, 'Second line', 'text-height')}">
										${if p->price}
											${args->before_price:default():arg_name(Text before price):arg_section(8, 1, 'Second line', 'text-height')}
											${if p->sale_price and p->sale_price &lt; p->price}
												${p->sale_price:truncate(2):sprintf($%s):arg_name(Price):arg_section(8, 2, 'Second line', 'text-height')}
												<div style="${args->sale_style:html:default('color:gray; text-decoration:line-through; font-size:85%'):input_type(css):input_props('with_responsive=1'):arg_name('Price before discount: style'):arg_section(8, 6, 'Second line', 'text-height')}">
													${p->price:truncate(2):sprintf($%s):arg_name(Price):arg_section(8, 5, 'Second line', 'text-height')}
												</div>
											${end}
											${if not p->sale_price or p->sale_price &gt;= p->price}
												${p->price:truncate(2):sprintf($%s):arg_name(Price):arg_section(8, 5, 'Second line', 'text-height')}
											${end}
											${args->after_price:default():arg_name(Text after price):arg_section(8, 3, 'Second line', 'text-height')}
										${end}
									</div>
									${block->rating:default(1):arg_name(With rating):arg_section(8, 7, 'Second line', 'text-height'):onchange('args.price_style = block.rating ? ''float:left'' : '''';')}
									<div style="${args->rating_style:html:default('float:right'):input_type(css):arg_name(Rating position):arg_section(8, 10, 'Second line', 'text-height')}">
										<input class="$rating" value="${p->rank:html:arg_name(Rating):arg_section(8, 8, 'Second line', 'text-height')}" max="${args->rank_max:html:default(100):input_type(number):arg_name(Maximum rating number that corresponds to 100%):arg_section(8, 9, 'Second line', 'text-height')}">
									</div>
									<div style="clear:both"></div>
								</div>
								${block->button:default(1):arg_name(With button):arg_section(9, 0, 'Add to cart button', 'plus-square')}
								<div style="margin-top:0.4em">
									<a data-emarketer-click-target="products ${p->internal_id:html}" href="${p->cart_url:html:arg_name(Link target URL):arg_section(9, 2, 'Add to cart button', 'plus-square'):column_tags('url','custom text')}" data-style="${args->button_style:html:default('display:inline-block; background-color:royalblue; border-radius:4px; padding:2px 6px; color:white; text-decoration:none'):input_type(css):input_props('with_responsive=1'):arg_name(Button style):arg_section(9, 3, 'Add to cart button', 'plus-square')}">${args->button:default(Add to cart):arg_name('Text', 'Link target URL'):arg_section(9, 1, 'Add to cart button', 'plus-square')}</a>
								</div>
							</td>
						</tr>
					${end}
				</tbody>
			</table>
		</div>
```


## Slider with zoomin



```
<div class="$responsive" data-style="display:inline-block; position:relative; ${args->style:html:default('border: none;
text-align: center;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(0, 1, 'Frame', 'th-large')}" onupdate="
	var
		w=Math.min(ns.joyquery('ancestor::table:limit(1) parent::div parent::div', by_id.ts).get(0).offsetWidth, document.documentElement.clientWidth-1),
		b=12,
		a=ns.joyquery('parent::*>tr>td>*', by_id.ts).get(),
		d=a[0].parentNode,
		t=d.offsetWidth,
		n=Math.max(Math.round((w-b)/(t+b)), Math.min(2, by_id.ts.children.length)),
		T=(w-b)/n-b-parseFloat(d.style.borderLeftWidth)*2;
	for (i=0; i!=a.length; i++) if (a[i].style.display!='inline-block') a[i].style.width=T+'px'
">
	${block->title:default(1):arg_name(With title bar):arg_section(2, 0, 'Title', 'bookmark')}
	<table data-style="width:100%; border-collapse:collapse; border:none; ${args->title_bg:html:default('background-color: rgba(170, 76, 76, 0);
margin-top: 43px;
margin-right: 0px;
margin-bottom: 7px;
margin-left: 7px;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(2, 2, 'Title', 'bookmark')}">
		<tr>
			<td data-style="vertical-align:middle; ${args->title_style:html:default('text-align: center;
padding-top: 0px;
padding-right: 0px;
padding-bottom: 25px;
padding-left: 0px;
font-size: 25px;
text-transform: uppercase;
font-family: "Karla","HelveticaNeue","Helvetica Neue",sans-serif;
font-weight: 700;
color: #4b4f59;'):input_type(css):input_props('with_responsive=1'):arg_name(Title style):arg_section(2, 3, 'Title', 'bookmark')}">
				${args->title:default(RECOMMENDED FOR YOU):arg_name(Text):arg_section(2, 1, 'Title', 'bookmark')}
			</td>
			${block->with_arrows:default(0):arg_name(With arrow buttons):arg_section(1, 0, 'With slider', 'arrow-right')}
			<td style="width:1px; white-space:nowrap; vertical-align:middle">
				<a id="button_back" class="$flat_btn" style="${args->btn_style:html:input_type(css):arg_name(Arrow button style):arg_section(1, 1, 'With slider', 'arrow-right')}" hover_style="${args->btn_hover_style:html:input_type(css):arg_name('Arrow button style: hover'):arg_section(1, 2, 'With slider', 'arrow-right')}"><</a>
				<a id="button_forward" class="$flat_btn" style="${args->btn_style:html:input_type(css):arg_name(Arrow button style):arg_section(1, 1, 'With slider', 'arrow-right')}" hover_style="${args->btn_hover_style:html:input_type(css):arg_name('Arrow button style: hover'):arg_section(1, 2, 'With slider', 'arrow-right')}">></a>
			</td>
			${block->x:default(0):arg_name(With close button):arg_section(3, 0, 'Close button', 'close')}
			<td style="width:1px; white-space:nowrap; ${args->x_style:html:input_type(css):arg_name(Close button position):arg_section(3, 2, 'Close button', 'close')}">
				${args->x:input_type(dontshowagain):input_props('style=cursor:pointer; vertical-align:middle'):arg_name(Close button):arg_section(3, 1, 'Close button', 'close')}
			</td>
		</tr>
	</table>
	<table style="width:100%; border-collapse:separate; border-spacing:12px 0; margin-bottom:1.2em">
		<tr id="ts" class="$table_slider" data-disabled="${args->with_slider:html:default():input_type(checkbox):input_props('value_off=1','value_on='):arg_name(Use slider widget):arg_section(1, 4, 'With slider', 'arrow-right'):onchange('if (args.with_slider==1) block.with_arrows = block.pagination = 0')}" style="border:none; max-width:${args->width:html:default(none):input_type(css_length):input_props('with_options=none'):arg_name(Widget maximum width):arg_section(0, 0, 'Frame', 'th-large')}" for_max_vw="${args->for_max_vw:html:default(always):input_type(css_length):input_props('with_options=always'):arg_name(Slider widget only if screen width is less than or equal to):arg_section(1, 5, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" eq_cell_width="${args->eq_cell_width:html:default(1):input_type(checkbox):input_props('value_off=','value_on=1'):arg_name(Equal cell width):arg_section(0, 2, 'Frame', 'th-large')}" eq_cell_height="1" arrows_line="${args->arrows_line:html:default(0):input_type(checkbox):input_props('value_off=-1','value_on=0'):arg_name(Arrows in the middle of images):arg_section(1, 9, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" arrow_back_img="${args->arrow_back_img:html:default('https://static.emarketer.com/upload/4035/3256192fabeef23a.png'):input_type(emarketer_media_url):arg_name(Left arrow image):arg_section(1, 6, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" arrow_forward_img="${args->arrow_forward_img:html:default('https://static.emarketer.com/upload/4035/6447f3eea66d7795.png'):input_type(emarketer_media_url):arg_name(Right arrow image):arg_section(1, 7, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" pagination_id="tsp" arrow_back_id="button_back" arrow_forward_id="button_forward" arrows_offset="${args->arrows_offset:html:default(-15):input_type(number):arg_name(Slider arrows offset):arg_section(1, 8, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" hide_buttons="${args->hide_buttons:html:input_type(checkbox):input_props('value_off=','value_on=1'):arg_name(Hide arrow buttons when nothing to scroll):arg_section(1, 3, 'With slider', 'arrow-right'):visible_if('block.title-0 && block.with_arrows-0')}">
			${foreach sum_interested_products_week as p order by p->n_goal desc limit 18}
				<td style="padding:0; text-align:center; background-color:white; border:solid ${args->border_color:html:default(white):input_type(color):arg_name(Border color):arg_section(0, 4, 'Frame', 'th-large')} 1px">
					<a data-emarketer-click-target="products ${p->internal_id:html}" href="${p->cart_url:html:arg_name(Link target URL):arg_section(6, 0, 'Link target URL', 'link'):column_tags('url','custom text')}" target="${args->target:html:default(_self):input_type(a_target):arg_name(Open link in):arg_section(6, 1, 'Link target URL', 'link')}" data-style="display:block; margin:auto; box-sizing:border-box; width:${args->img_width:html:default('sel(200px, 25vw)'):input_type(css_length):input_props('with_responsive=1'):arg_name(Cell width):arg_section(0, 3, 'Frame', 'th-large')}">
						<div data-style="background-image:url('${p->image_big_url:html:arg_name(Item image):arg_section(4, 0, 'Image', 'image'):column_tags(image)}'); background-repeat:no-repeat; background-position:center; background-size:100% 100%; transition: background-size 0.7s ease; width:100%" data-z='${args->zoom:html:default(105):input_type(number):arg_name('Image zoom on hover, %'):arg_section(4, 1, 'Image', 'image')}' onmouseover="var z=this.getAttribute('data-z'); this.style.backgroundSize=z+'% '+z+'%'" onmouseout="this.style.backgroundSize='100% 100%'">
							<img src="${p->image_big_url:html:arg_name(Item image):arg_section(4, 0, 'Image', 'image'):column_tags(image)}" data-style="visibility:hidden; width:auto; height:auto; max-width:100%; max-height:${args->img_max_height:html:default('sel(300px, 30vw)'):input_type(css_length):input_props('with_responsive=1'):arg_name(Image maximum height):arg_section(0, 5, 'Frame', 'th-large')}">
						</div>
					</a>
					<div data-style="margin:auto; box-sizing:border-box; width:${args->img_width:html:default('sel(200px, 25vw)'):input_type(css_length):input_props('with_responsive=1'):arg_name(Cell width):arg_section(0, 3, 'Frame', 'th-large')}">
						<div data-style="display:inline-block; ${args->a_css:html:default('font-size: 12px;
color: #666;
text-decoration: inherit;
text-align: left;
float: left;
padding-top: 5px;
padding-right: 0px;
padding-bottom: 0px;
padding-left: 0px;
text-overflow: ellipsis;
text-transform: none;
width: 100%;
white-space: nowrap;
overflow: hidden;'):input_type(css):input_props('with_responsive=1'):arg_name(Text color):arg_section(5, 3, 'Text', 'align-justify')}">
							${p->title:arg_name(Item text):arg_section(5, 1, 'Text', 'align-justify')}
						</div>
					</div>
					${block->price:default(0):arg_name(With price):arg_section(7, 0, 'Price', 'dollar')}
					<div data-style="margin:auto; box-sizing:border-box; width:${args->img_width:html:default('sel(200px, 25vw)'):input_type(css_length):input_props('with_responsive=1'):arg_name(Cell width):arg_section(0, 3, 'Frame', 'th-large')}">
						${if p->price}
							${args->before_price:arg_name(Text before price):arg_section(7, 1, 'Price', 'dollar')}
							${if p->sale_price and p->sale_price < p->price}
								${p->sale_price:truncate(2):sprintf($%s):arg_name(Price):arg_section(7, 2, 'Price', 'dollar')}
								<div style="${args->sale_style:html:input_type(css):input_props('with_responsive=1'):arg_name('Price before discount: style'):arg_section(7, 5, 'Price', 'dollar')}">
									${p->price:truncate(2):sprintf($%s):arg_name(Price):arg_section(7, 4, 'Price', 'dollar')}
								</div>
							${end}
							${if not p->sale_price or p->sale_price >= p->price}
								${p->price:truncate(2):sprintf($%s):arg_name(Price):arg_section(7, 4, 'Price', 'dollar')}
							${end}
							${args->after_price:arg_name(Text after price):arg_section(7, 3, 'Price', 'dollar')}
						${end}
					</div>
					<div style="margin:auto; box-sizing:border-box; font-size:1px">
						<div data-style="display:inline-block; background-color:${args->border_color:html:default(white):input_type(color):arg_name(Border color):arg_section(0, 4, 'Frame', 'th-large')}; ${args->a_css_2:html:default('width:100px; height:3px; max-width:80%'):input_type(css):input_props('with_responsive=1'):arg_name(Ruler):arg_section(5, 5, 'Text', 'align-justify')}"></div>
					</div>
					${block->description:default(0):arg_name(With description):arg_section(5, 0, 'Text', 'align-justify')}
					<div data-style="margin:auto; box-sizing:border-box; width:${args->img_width:html:default('sel(200px, 25vw)'):input_type(css_length):input_props('with_responsive=1'):arg_name(Cell width):arg_section(0, 3, 'Frame', 'th-large')}">
						<div data-style="display:inline-block; ${args->a_css_3:html:input_type(css):input_props('with_responsive=1'):arg_name(Text color):arg_section(5, 4, 'Text', 'align-justify')}; padding-bottom:0">
							${p->description:arg_name(Item text):arg_section(5, 2, 'Text', 'align-justify')}
						</div>
					</div>
					${block->button:default(0):arg_name(With button):arg_section(8, 0, 'Button', 'hand-pointer-o')}
					<a data-emarketer-click-target="products ${p->internal_id:html}" href="${p->cart_url:html:arg_name(Link target URL):arg_section(6, 0, 'Link target URL', 'link'):column_tags('url','custom text')}" target="${args->target:html:default(_self):input_type(a_target):arg_name(Open link in):arg_section(6, 1, 'Link target URL', 'link')}" data-style="display:inline-block; position:relative; top:1.3em; text-decoration:none; transition: font-size 0.3s ease; background-color:${args->border_color:html:default(white):input_type(color):arg_name(Border color):arg_section(0, 4, 'Frame', 'th-large')}; ${args->a_css_4:html:input_type(css):input_props('with_responsive=1'):arg_name(Button style):arg_section(8, 2, 'Button', 'hand-pointer-o')}" onmouseenter="var t=this; s=t.style, f=s.fontSize, p=f.match(/^([\d\.]+)(\w+)$/); if (!t._b) t._b=[s.backgroundColor, s.color, f]; s.backgroundColor=t._b[1]; s.color=t._b[0]; if (p) if (!t._p) {s.fontSize=(p[1]*0.9)+p[2]; t._p=1; setTimeout(function() {s.fontSize=t._b[2]; t._p=0;}, 300)}" onmouseleave="var s=this.style, b=this._b; s.backgroundColor=b[0]; s.color=b[1]">
						<div data-style="border:solid 1px; ${args->a_css_5:html:input_type(css):input_props('with_responsive=1'):arg_name(Button style):arg_section(8, 3, 'Button', 'hand-pointer-o')}">
							${args->button_text:arg_name(Button text):arg_section(8, 1, 'Button', 'hand-pointer-o')}
						</div>
					</a>
				</td>
			${end}
		</tr>
	</table>
	${block->pagination:default(0):arg_name(With slider pagination):arg_section(1, 10, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}
	<div id="tsp" class="$table_slider_pagination" slider_id="ts" selected_color="${args->pagination_color_on:html:input_type(color):arg_name(Bullet Selected Color):arg_section(1, 11, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" style="${args->pagination_color:html:input_type(css):arg_name(Bullet style):arg_section(1, 12, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}"></div>
</div>
```


## Widget with frame

Widget with frame

```
<div class="$responsive" data-style="display:inline-block; position:relative; ${args->style:html:default('border: solid rgb(43, 167, 38);
text-align: left;
width: 100%;
background-color: white;
font-family: Roboto, sans-serif;
box-sizing: border-box;
margin-top: 10px;
margin-right: 1px;
margin-bottom: 10px;
margin-left: 1px;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(0, 1, 'Frame', 'th-large')}" onupdate="
	var
		w=Math.min(ns.joyquery('ancestor::table:limit(1) parent::div parent::div', by_id.ts).get(0).offsetWidth, document.documentElement.clientWidth-1),
		b=12,
		a=ns.joyquery('parent::*>tr>td>*', by_id.ts).get(),
		d=a[0].parentNode,
		t=d.offsetWidth,
		n=Math.max(Math.round((w-b)/(t+b)), Math.min(2, by_id.ts.children.length)),
		T=(w-b)/n-b-parseFloat(d.style.borderLeftWidth)*2;
	for (i=0; i!=a.length; i++) if (a[i].style.display!='inline-block') a[i].style.width=T+'px'
">
	${block->title:default(1):arg_name(With title bar):arg_section(2, 0, 'Title', 'bookmark')}
	<div style="${args->title_bg:html:default('background-color: rgb(43, 167, 38);
margin-top: 0px;
margin-right: 0px;
margin-bottom: 25px;
margin-left: 0px;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(2, 2, 'Title', 'bookmark')}">
		<table data-style="width:100%; border-collapse:collapse; border:none">
			<tr>
				<td data-style="vertical-align:middle; ${args->title_style:html:default('text-align: left;
padding-top: 10px;
padding-right: 0px;
padding-bottom: 15px;
padding-left: 15px;
font-size: 18px;
text-transform: none;
font-weight: 500;
color: white;'):input_type(css):input_props('with_responsive=1'):arg_name(Title style):arg_section(2, 3, 'Title', 'bookmark')}">
					${args->title:default(Top Picks For You):arg_name(Text):arg_section(2, 1, 'Title', 'bookmark')}
				</td>
				${block->with_arrows:default(0):arg_name(With arrow buttons):arg_section(1, 0, 'With slider', 'arrow-right')}
				<td style="width:1px; white-space:nowrap; vertical-align:middle">
					<a id="button_back" class="$flat_btn" style="${args->btn_style:html:input_type(css):arg_name(Arrow button style):arg_section(1, 1, 'With slider', 'arrow-right')}" hover_style="${args->btn_hover_style:html:input_type(css):arg_name('Arrow button style: hover'):arg_section(1, 2, 'With slider', 'arrow-right')}"><</a>
					<a id="button_forward" class="$flat_btn" style="${args->btn_style:html}" hover_style="${args->btn_hover_style:html}">></a>
				</td>
				${block->x:default(0):arg_name(With close button):arg_section(3, 0, 'Close button', 'close')}
				<td style="width:1px; white-space:nowrap; ${args->x_style:html:input_type(css):arg_name(Close button position):arg_section(3, 2, 'Close button', 'close')}">
					${args->x:input_type(dontshowagain):input_props('style=cursor:pointer; vertical-align:middle'):arg_name(Close button):arg_section(3, 1, 'Close button', 'close')}
				</td>
			</tr>
		</table>
	</div>
	<table style="width:100%; border-collapse:separate; border-spacing:12px 0; margin-bottom:1.2em">
		<tr id="ts" class="$table_slider" data-disabled="${args->with_slider:html:input_type(checkbox):input_props('value_off=1','value_on='):arg_name(Use slider widget):arg_section(1, 4, 'With slider', 'arrow-right'):onchange('if (args.with_slider==1) block.with_arrows = block.pagination = 0')}" style="border:none; max-width:${args->width:html:default(none):input_type(css_length):input_props('with_options=none'):arg_name(Widget maximum width):arg_section(0, 0, 'Frame', 'th-large')}" for_max_vw="${args->for_max_vw:html:default(always):input_type(css_length):input_props('with_options=always'):arg_name(Slider widget only if screen width is less than or equal to):arg_section(1, 5, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" eq_cell_width="${args->eq_cell_width:html:default(1):input_type(checkbox):input_props('value_off=','value_on=1'):arg_name(Equal cell width):arg_section(0, 2, 'Frame', 'th-large')}" eq_cell_height="1" arrows_line="${args->arrows_line:html:default(0):input_type(checkbox):input_props('value_off=-1','value_on=0'):arg_name(Arrows in the middle of images):arg_section(1, 9, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" arrow_back_img="${args->arrow_back_img:html:default('https://static.emarketer.com/upload/4545/96b6126f483ffd5a.png'):input_type(emarketer_media_url):arg_name(Left arrow image):arg_section(1, 6, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" arrow_style="${args->arrow_style:html:default('box-shadow: 0px 8px 6px 8px rgba(0, 0, 0, 0.23);
background-color: rgba(256, 256, 256, 0.62);'):input_type(css):arg_name(Arrows style):arg_section(1, 7, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" pagination_id="tsp" arrow_back_id="button_back" arrow_forward_id="button_forward" arrows_offset="${args->arrows_offset:html:default(0):input_type(number):arg_name(Slider arrows offset):arg_section(1, 8, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" hide_buttons="${args->hide_buttons:html:input_type(checkbox):input_props('value_off=','value_on=1'):arg_name(Hide arrow buttons when nothing to scroll):arg_section(1, 3, 'With slider', 'arrow-right'):visible_if('block.title-0 && block.with_arrows-0')}">
			${foreach sum_viewed_categories_products_week as p where p->n_goal>0 order by p->n_goal desc limit 18}
				<td style="padding:0; text-align:center; background-color:white; border:solid ${args->border_color:html:default(white):input_type(color):arg_name(Border color):arg_section(0, 4, 'Frame', 'th-large')} 1px">
					<a data-emarketer-click-target="products ${p->internal_id:html}" href="${p->cart_url:html:arg_name(Link target URL):arg_section(6, 0, 'Link target URL', 'link'):column_tags('url','custom text')}" target="${args->target:html:default(_self):input_type(a_target):arg_name(Open link in):arg_section(6, 1, 'Link target URL', 'link')}" data-style="display:block; margin:auto; box-sizing:border-box; width:${args->img_width:html:default('sel(190px, 26vw)'):input_type(css_length):input_props('with_responsive=1'):arg_name(Cell width):arg_section(0, 3, 'Frame', 'th-large')}">
						<div data-style="background-image:url('${p->image_big_url:html:arg_name(Item image):arg_section(4, 0, 'Image', 'image'):column_tags(image)}'); background-repeat:no-repeat; background-position:center; background-size:100% 100%; transition: background-size 0.7s ease; width:100%" data-z='${args->zoom:html:default(110):input_type(number):arg_name('Image zoom on hover, %'):arg_section(4, 1, 'Image', 'image')}' onmouseover="var z=this.getAttribute('data-z'); this.style.backgroundSize=z+'% '+z+'%'" onmouseout="this.style.backgroundSize='100% 100%'">
							<img src="${p->image_big_url:html}" data-style="visibility:hidden; width:auto; height:auto; max-width:100%; max-height:${args->img_max_height:html:default('sel(300px, 30vw)'):input_type(css_length):input_props('with_responsive=1'):arg_name(Image maximum height):arg_section(0, 5, 'Frame', 'th-large')}">
						</div>
					</a>
					<div data-style="margin:auto; box-sizing:border-box; width:${args->img_width:html}">
						<div data-style="${args->a_css:html:default('    font-family: ''Roboto'',sans-serif;
    font-size: 14px;
    line-height: 1.6;
    color: #333;
    font-weight:500;
text-align: left;
margin: 10px;
text-overflow: ellipsis;
text-transform: none;
white-space: nowrap;
overflow: hidden;'):input_type(css):input_props('with_responsive=1'):arg_name(Text color):arg_section(5, 3, 'Text', 'align-justify')}">
							${p->title:arg_name(Item text):arg_section(5, 1, 'Text', 'align-justify')}
						</div>
					</div>
					${block->price:default(1):arg_name(With price):arg_section(7, 0, 'Price', 'dollar')}
					<div data-style="margin:auto; box-sizing:border-box; width:${args->img_width:html}; ${args->price_style:html:default('color: #d32f2f;
text-align: start;
padding: 10px;
font-size: sel(1.2em, 1.1em);
font-weight: 500;'):input_type(css):input_props('with_responsive=1'):arg_name(Price style):arg_section(7, 1, 'Price', 'dollar')}">
						${if p->price}
							${args->before_price:arg_name(Text before price):arg_section(7, 2, 'Price', 'dollar')}
							${if p->sale_price and p->sale_price < p->price}
								${p->sale_price:truncate(2):sprintf($%s):arg_name(Price):arg_section(7, 6, 'Price', 'dollar')}
								<div style="${args->sale_style:html:default('color:gray; text-decoration:line-through; font-size:85%'):input_type(css):input_props('with_responsive=1'):arg_name('Price before discount: style'):arg_section(7, 4, 'Price', 'dollar')}">
									${p->price:truncate(2):sprintf($%s):arg_name(Price):arg_section(7, 3, 'Price', 'dollar')}
								</div>
							${end}
							${if not p->sale_price or p->sale_price >= p->price}
								${p->price:truncate(2):sprintf($%s)}
							${end}
							${args->after_price:arg_name(Text after price):arg_section(7, 5, 'Price', 'dollar')}
						${end}
					</div>
					<div style="margin:auto; box-sizing:border-box; font-size:1px">
						<div data-style="display:inline-block; background-color:${args->border_color:html}; ${args->a_css_2:html:default('width:100px; height:3px; max-width:80%'):input_type(css):input_props('with_responsive=1'):arg_name(Ruler):arg_section(5, 5, 'Text', 'align-justify')}"></div>
					</div>
					${block->description:default(0):arg_name(With description):arg_section(5, 0, 'Text', 'align-justify')}
					<div data-style="margin:auto; box-sizing:border-box; width:${args->img_width:html}">
						<div data-style="display:inline-block; ${args->a_css_3:html:input_type(css):input_props('with_responsive=1'):arg_name(Text color):arg_section(5, 4, 'Text', 'align-justify')}; padding-bottom:0">
							${p->description:arg_name(Item text):arg_section(5, 2, 'Text', 'align-justify')}
						</div>
					</div>
					${block->button:default(0):arg_name(With button):arg_section(8, 0, 'Button', 'hand-pointer-o')}
					<a data-emarketer-click-target="products ${p->internal_id:html}" href="${p->cart_url:html}" target="${args->target:html}" data-style="display:inline-block; position:relative; top:1.3em; text-decoration:none; transition: font-size 0.3s ease; background-color:${args->border_color:html}; ${args->a_css_4:html:input_type(css):input_props('with_responsive=1'):arg_name(Button style):arg_section(8, 2, 'Button', 'hand-pointer-o')}" onmouseenter="var t=this; s=t.style, f=s.fontSize, p=f.match(/^([\d\.]+)(\w+)$/); if (!t._b) t._b=[s.backgroundColor, s.color, f]; s.backgroundColor=t._b[1]; s.color=t._b[0]; if (p) if (!t._p) {s.fontSize=(p[1]*0.9)+p[2]; t._p=1; setTimeout(function() {s.fontSize=t._b[2]; t._p=0;}, 300)}" onmouseleave="var s=this.style, b=this._b; s.backgroundColor=b[0]; s.color=b[1]">
						<div data-style="border:solid 1px; ${args->a_css_5:html:input_type(css):input_props('with_responsive=1'):arg_name(Button style):arg_section(8, 3, 'Button', 'hand-pointer-o')}">
							${args->button_text:arg_name(Button text):arg_section(8, 1, 'Button', 'hand-pointer-o')}
						</div>
					</a>
				</td>
			${end}
		</tr>
	</table>
	${block->pagination:default(0):arg_name(With slider pagination):arg_section(1, 10, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}
	<div id="tsp" class="$table_slider_pagination" slider_id="ts" selected_color="${args->pagination_color_on:html:input_type(color):arg_name(Bullet Selected Color):arg_section(1, 11, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" style="${args->pagination_color:html:input_type(css):arg_name(Bullet style):arg_section(1, 12, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}"></div>
</div>
```


## Widget with frame

Widget with frame

```
<div class="$responsive" data-style="display:inline-block; position:relative; ${args->style:html:default('border: solid rgb(43, 167, 38);
text-align: left;
width: 100%;
background-color: white;
font-family: Roboto, sans-serif;
box-sizing: border-box;
margin-top: 10px;
margin-right: 1px;
margin-bottom: 10px;
margin-left: 1px;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(0, 1, 'Frame', 'th-large')}" onupdate="
	var
		w=Math.min(ns.joyquery('ancestor::table:limit(1) parent::div parent::div', by_id.ts).get(0).offsetWidth, document.documentElement.clientWidth-1),
		b=12,
		a=ns.joyquery('parent::*>tr>td>*', by_id.ts).get(),
		d=a[0].parentNode,
		t=d.offsetWidth,
		n=Math.max(Math.round((w-b)/(t+b)), Math.min(2, by_id.ts.children.length)),
		T=(w-b)/n-b-parseFloat(d.style.borderLeftWidth)*2;
	for (i=0; i!=a.length; i++) if (a[i].style.display!='inline-block') a[i].style.width=T+'px'
">
	${block->title:default(1):arg_name(With title bar):arg_section(2, 0, 'Title', 'bookmark')}
	<div style="${args->title_bg:html:default('background-color: rgb(43, 167, 38);
margin-top: 0px;
margin-right: 0px;
margin-bottom: 25px;
margin-left: 0px;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(2, 2, 'Title', 'bookmark')}">
		<table data-style="width:100%; border-collapse:collapse; border:none">
			<tr>
				<td data-style="vertical-align:middle; ${args->title_style:html:default('text-align: left;
padding-top: 10px;
padding-right: 0px;
padding-bottom: 15px;
padding-left: 15px;
font-size: 18px;
text-transform: none;
font-weight: 500;
color: white;'):input_type(css):input_props('with_responsive=1'):arg_name(Title style):arg_section(2, 3, 'Title', 'bookmark')}">
					${args->title:default(Top Picks For You):arg_name(Text):arg_section(2, 1, 'Title', 'bookmark')}
				</td>
				${block->with_arrows:default(0):arg_name(With arrow buttons):arg_section(1, 0, 'With slider', 'arrow-right')}
				<td style="width:1px; white-space:nowrap; vertical-align:middle">
					<a id="button_back" class="$flat_btn" style="${args->btn_style:html:input_type(css):arg_name(Arrow button style):arg_section(1, 1, 'With slider', 'arrow-right')}" hover_style="${args->btn_hover_style:html:input_type(css):arg_name('Arrow button style: hover'):arg_section(1, 2, 'With slider', 'arrow-right')}"><</a>
					<a id="button_forward" class="$flat_btn" style="${args->btn_style:html}" hover_style="${args->btn_hover_style:html}">></a>
				</td>
				${block->x:default(0):arg_name(With close button):arg_section(3, 0, 'Close button', 'close')}
				<td style="width:1px; white-space:nowrap; ${args->x_style:html:input_type(css):arg_name(Close button position):arg_section(3, 2, 'Close button', 'close')}">
					${args->x:input_type(dontshowagain):input_props('style=cursor:pointer; vertical-align:middle'):arg_name(Close button):arg_section(3, 1, 'Close button', 'close')}
				</td>
			</tr>
		</table>
	</div>
	<table style="width:100%; border-collapse:separate; border-spacing:12px 0; margin-bottom:1.2em">
		<tr id="ts" class="$table_slider" data-disabled="${args->with_slider:html:input_type(checkbox):input_props('value_off=1','value_on='):arg_name(Use slider widget):arg_section(1, 4, 'With slider', 'arrow-right'):onchange('if (args.with_slider==1) block.with_arrows = block.pagination = 0')}" style="border:none; max-width:${args->width:html:default(none):input_type(css_length):input_props('with_options=none'):arg_name(Widget maximum width):arg_section(0, 0, 'Frame', 'th-large')}" for_max_vw="${args->for_max_vw:html:default(always):input_type(css_length):input_props('with_options=always'):arg_name(Slider widget only if screen width is less than or equal to):arg_section(1, 5, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" eq_cell_width="${args->eq_cell_width:html:default(1):input_type(checkbox):input_props('value_off=','value_on=1'):arg_name(Equal cell width):arg_section(0, 2, 'Frame', 'th-large')}" eq_cell_height="1" arrows_line="${args->arrows_line:html:default(0):input_type(checkbox):input_props('value_off=-1','value_on=0'):arg_name(Arrows in the middle of images):arg_section(1, 9, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" arrow_back_img="${args->arrow_back_img:html:default('https://static.emarketer.com/upload/4545/96b6126f483ffd5a.png'):input_type(emarketer_media_url):arg_name(Left arrow image):arg_section(1, 6, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" arrow_style="${args->arrow_style:html:default('box-shadow: 0px 8px 6px 8px rgba(0, 0, 0, 0.23);
background-color: rgba(256, 256, 256, 0.62);'):input_type(css):arg_name(Arrows style):arg_section(1, 7, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" pagination_id="tsp" arrow_back_id="button_back" arrow_forward_id="button_forward" arrows_offset="${args->arrows_offset:html:default(0):input_type(number):arg_name(Slider arrows offset):arg_section(1, 8, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" hide_buttons="${args->hide_buttons:html:input_type(checkbox):input_props('value_off=','value_on=1'):arg_name(Hide arrow buttons when nothing to scroll):arg_section(1, 3, 'With slider', 'arrow-right'):visible_if('block.title-0 && block.with_arrows-0')}">
			${foreach sum_viewed_categories_products_week as p where p->n_goal>0 order by p->n_goal desc limit 18}
				<td style="padding:0; text-align:center; background-color:white; border:solid ${args->border_color:html:default(white):input_type(color):arg_name(Border color):arg_section(0, 4, 'Frame', 'th-large')} 1px">
					<a data-emarketer-click-target="products ${p->internal_id:html}" href="${p->cart_url:html:arg_name(Link target URL):arg_section(6, 0, 'Link target URL', 'link'):column_tags('url','custom text')}" target="${args->target:html:default(_self):input_type(a_target):arg_name(Open link in):arg_section(6, 1, 'Link target URL', 'link')}" data-style="display:block; margin:auto; box-sizing:border-box; width:${args->img_width:html:default('sel(190px, 26vw)'):input_type(css_length):input_props('with_responsive=1'):arg_name(Cell width):arg_section(0, 3, 'Frame', 'th-large')}">
						<div data-style="background-image:url('${p->image_big_url:html:arg_name(Item image):arg_section(4, 0, 'Image', 'image'):column_tags(image)}'); background-repeat:no-repeat; background-position:center; background-size:100% 100%; transition: background-size 0.7s ease; width:100%" data-z='${args->zoom:html:default(110):input_type(number):arg_name('Image zoom on hover, %'):arg_section(4, 1, 'Image', 'image')}' onmouseover="var z=this.getAttribute('data-z'); this.style.backgroundSize=z+'% '+z+'%'" onmouseout="this.style.backgroundSize='100% 100%'">
							<img src="${p->image_big_url:html}" data-style="visibility:hidden; width:auto; height:auto; max-width:100%; max-height:${args->img_max_height:html:default('sel(300px, 30vw)'):input_type(css_length):input_props('with_responsive=1'):arg_name(Image maximum height):arg_section(0, 5, 'Frame', 'th-large')}">
						</div>
					</a>
					<div data-style="margin:auto; box-sizing:border-box; width:${args->img_width:html}">
						<div data-style="${args->a_css:html:default('    font-family: ''Roboto'',sans-serif;
    font-size: 14px;
    line-height: 1.6;
    color: #333;
    font-weight:500;
text-align: left;
margin: 10px;
text-overflow: ellipsis;
text-transform: none;
white-space: nowrap;
overflow: hidden;'):input_type(css):input_props('with_responsive=1'):arg_name(Text color):arg_section(5, 3, 'Text', 'align-justify')}">
							${p->title:arg_name(Item text):arg_section(5, 1, 'Text', 'align-justify')}
						</div>
					</div>
					${block->price:default(1):arg_name(With price):arg_section(7, 0, 'Price', 'dollar')}
					<div data-style="margin:auto; box-sizing:border-box; width:${args->img_width:html}; ${args->price_style:html:default('color: #d32f2f;
text-align: start;
padding: 10px;
font-size: sel(1.2em, 1.1em);
font-weight: 500;'):input_type(css):input_props('with_responsive=1'):arg_name(Price style):arg_section(7, 1, 'Price', 'dollar')}">
						${if p->price}
							${args->before_price:arg_name(Text before price):arg_section(7, 2, 'Price', 'dollar')}
							${if p->sale_price and p->sale_price < p->price}
								${p->sale_price:truncate(2):sprintf($%s):arg_name(Price):arg_section(7, 6, 'Price', 'dollar')}
								<div style="${args->sale_style:html:default('color:gray; text-decoration:line-through; font-size:85%'):input_type(css):input_props('with_responsive=1'):arg_name('Price before discount: style'):arg_section(7, 4, 'Price', 'dollar')}">
									${p->price:truncate(2):sprintf($%s):arg_name(Price):arg_section(7, 3, 'Price', 'dollar')}
								</div>
							${end}
							${if not p->sale_price or p->sale_price >= p->price}
								${p->price:truncate(2):sprintf($%s)}
							${end}
							${args->after_price:arg_name(Text after price):arg_section(7, 5, 'Price', 'dollar')}
						${end}
					</div>
					<div style="margin:auto; box-sizing:border-box; font-size:1px">
						<div data-style="display:inline-block; background-color:${args->border_color:html}; ${args->a_css_2:html:default('width:100px; height:3px; max-width:80%'):input_type(css):input_props('with_responsive=1'):arg_name(Ruler):arg_section(5, 5, 'Text', 'align-justify')}"></div>
					</div>
					${block->description:default(0):arg_name(With description):arg_section(5, 0, 'Text', 'align-justify')}
					<div data-style="margin:auto; box-sizing:border-box; width:${args->img_width:html}">
						<div data-style="display:inline-block; ${args->a_css_3:html:input_type(css):input_props('with_responsive=1'):arg_name(Text color):arg_section(5, 4, 'Text', 'align-justify')}; padding-bottom:0">
							${p->description:arg_name(Item text):arg_section(5, 2, 'Text', 'align-justify')}
						</div>
					</div>
					${block->button:default(0):arg_name(With button):arg_section(8, 0, 'Button', 'hand-pointer-o')}
					<a data-emarketer-click-target="products ${p->internal_id:html}" href="${p->cart_url:html}" target="${args->target:html}" data-style="display:inline-block; position:relative; top:1.3em; text-decoration:none; transition: font-size 0.3s ease; background-color:${args->border_color:html}; ${args->a_css_4:html:input_type(css):input_props('with_responsive=1'):arg_name(Button style):arg_section(8, 2, 'Button', 'hand-pointer-o')}" onmouseenter="var t=this; s=t.style, f=s.fontSize, p=f.match(/^([\d\.]+)(\w+)$/); if (!t._b) t._b=[s.backgroundColor, s.color, f]; s.backgroundColor=t._b[1]; s.color=t._b[0]; if (p) if (!t._p) {s.fontSize=(p[1]*0.9)+p[2]; t._p=1; setTimeout(function() {s.fontSize=t._b[2]; t._p=0;}, 300)}" onmouseleave="var s=this.style, b=this._b; s.backgroundColor=b[0]; s.color=b[1]">
						<div data-style="border:solid 1px; ${args->a_css_5:html:input_type(css):input_props('with_responsive=1'):arg_name(Button style):arg_section(8, 3, 'Button', 'hand-pointer-o')}">
							${args->button_text:arg_name(Button text):arg_section(8, 1, 'Button', 'hand-pointer-o')}
						</div>
					</a>
				</td>
			${end}
		</tr>
	</table>
	${block->pagination:default(0):arg_name(With slider pagination):arg_section(1, 10, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}
	<div id="tsp" class="$table_slider_pagination" slider_id="ts" selected_color="${args->pagination_color_on:html:input_type(color):arg_name(Bullet Selected Color):arg_section(1, 11, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" style="${args->pagination_color:html:input_type(css):arg_name(Bullet style):arg_section(1, 12, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}"></div>
</div>
```


## Widget default



```
<div class="$responsive" data-style="display:inline-block; position:relative; ${args->style:html:default('border: none;
text-align: left;
min-width: 99%;
width: 99%;
font-family: ''Roboto'',sans-serif;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(0, 1, 'Frame', 'th-large')}" onupdate="
	var
		w=Math.min(ns.joyquery('ancestor::table:limit(1) parent::div parent::div', by_id.ts).get(0).offsetWidth, document.documentElement.clientWidth-1),
		b=12,
		a=ns.joyquery('parent::*>tr>td>*', by_id.ts).get(),
		d=a[0].parentNode,
		t=d.offsetWidth,
		n=Math.max(Math.round((w-b)/(t+b)), Math.min(2, by_id.ts.children.length)),
		T=(w-b)/n-b-parseFloat(d.style.borderLeftWidth)*2;
	for (i=0; i!=a.length; i++) if (a[i].style.display!='inline-block') a[i].style.width=T+'px'
">
	${block->title:default(1):arg_name(With title bar):arg_section(2, 0, 'Title', 'bookmark')}
	<table data-style="width:100%; border-collapse:collapse; border:none; ${args->title_bg:html:default('margin-top: 5px;
margin-right: 0px;
margin-bottom: 5px;
margin-left: 20px;
border-bottom: 1px solid #eaeaea;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(2, 2, 'Title', 'bookmark')}">
		<tr>
			<td data-style="vertical-align:middle; ${args->title_style:html:default('text-align: left;
padding-top: 0px;
padding-right: 0px;
padding-bottom: 15px;
padding-left: 0px;
font-size: 18px;
text-transform: none;
font-weight: 500;
color: rgb(3, 1, 1);
padding: 0 0 15px;
    position: relative;
    font-family: "Open Sans",Arial,sans-serif;
    font-size: 21px;
    font-weight: 400;
    line-height: 21px;
    text-transform: capitalize;'):input_type(css):input_props('with_responsive=1'):arg_name(Title style):arg_section(2, 3, 'Title', 'bookmark')}">
				${args->title:default(Recommended for you):arg_name(Text):arg_section(2, 1, 'Title', 'bookmark')}
			</td>
			${block->with_arrows:default(0):arg_name(With arrow buttons):arg_section(1, 0, 'With slider', 'arrow-right')}
			<td style="width:1px; white-space:nowrap; vertical-align:middle">
				<a id="button_back" class="$flat_btn" style="${args->btn_style:html:input_type(css):arg_name(Arrow button style):arg_section(1, 1, 'With slider', 'arrow-right')}" hover_style="${args->btn_hover_style:html:input_type(css):arg_name('Arrow button style: hover'):arg_section(1, 2, 'With slider', 'arrow-right')}"><</a>
				<a id="button_forward" class="$flat_btn" style="${args->btn_style:html}" hover_style="${args->btn_hover_style:html}">></a>
			</td>
			${block->x:default(0):arg_name(With close button):arg_section(3, 0, 'Close button', 'close')}
			<td style="width:1px; white-space:nowrap; ${args->x_style:html:input_type(css):arg_name(Close button position):arg_section(3, 2, 'Close button', 'close')}">
				${args->x:input_type(dontshowagain):input_props('style=cursor:pointer; vertical-align:middle'):arg_name(Close button):arg_section(3, 1, 'Close button', 'close')}
			</td>
		</tr>
	</table>
	<table style="width:100%; border-collapse:separate; border-spacing:12px 0; margin-bottom:1.2em">
		<tr id="ts" class="$table_slider" data-disabled="${args->with_slider:html:input_type(checkbox):input_props('value_off=1','value_on='):arg_name(Use slider widget):arg_section(1, 4, 'With slider', 'arrow-right'):onchange('if (args.with_slider==1) block.with_arrows = block.pagination = 0')}" style="border:none; max-width:${args->width:html:default(none):input_type(css_length):input_props('with_options=none'):arg_name(Widget maximum width):arg_section(0, 0, 'Frame', 'th-large')}" for_max_vw="${args->for_max_vw:html:default(always):input_type(css_length):input_props('with_options=always'):arg_name(Slider widget only if screen width is less than or equal to):arg_section(1, 5, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" eq_cell_width="${args->eq_cell_width:html:default(1):input_type(checkbox):input_props('value_off=','value_on=1'):arg_name(Equal cell width):arg_section(0, 2, 'Frame', 'th-large')}" eq_cell_height="1" arrows_line="${args->arrows_line:html:default(0):input_type(checkbox):input_props('value_off=-1','value_on=0'):arg_name(Arrows in the middle of images):arg_section(1, 9, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" arrow_back_img="${args->arrow_back_img:html:default('https://static.emarketer.com/upload/4545/96b6126f483ffd5a.png'):input_type(emarketer_media_url):arg_name(Left arrow image):arg_section(1, 6, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" arrow_style="${args->arrow_style:html:default('box-shadow: 0px 8px 6px 8px rgba(0, 0, 0, 0.23);
background-color: rgba(256, 256, 256, 0.56);'):input_type(css):arg_name(Arrows style):arg_section(1, 7, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" pagination_id="tsp" arrow_back_id="button_back" arrow_forward_id="button_forward" arrows_offset="${args->arrows_offset:html:default(0):input_type(number):arg_name(Slider arrows offset):arg_section(1, 8, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" hide_buttons="${args->hide_buttons:html:input_type(checkbox):input_props('value_off=','value_on=1'):arg_name(Hide arrow buttons when nothing to scroll):arg_section(1, 3, 'With slider', 'arrow-right'):visible_if('block.title-0 && block.with_arrows-0')}">
			${foreach sum_last_viewed_categories_products_week as p order by p->n_viewed desc limit 18}
				<td style="padding:0; text-align:center; background-color:white; border:solid ${args->border_color:html:default(white):input_type(color):arg_name(Border color):arg_section(0, 4, 'Frame', 'th-large')} 1px">
					<a data-emarketer-click-target="products ${p->internal_id:html}" href="${p->cart_url:html:arg_name(Link target URL):arg_section(6, 0, 'Link target URL', 'link'):column_tags('url','custom text')}" target="${args->target:html:default(_self):input_type(a_target):arg_name(Open link in):arg_section(6, 1, 'Link target URL', 'link')}" data-style="display:block; margin:auto; box-sizing:border-box; width:${args->img_width:html:default('sel(190px, 26vw)'):input_type(css_length):input_props('with_responsive=1'):arg_name(Cell width):arg_section(0, 3, 'Frame', 'th-large')}">
						<div data-style="background-image:url('${p->image_big_url:html:arg_name(Item image):arg_section(4, 0, 'Image', 'image'):column_tags(image)}'); background-repeat:no-repeat; background-position:center; background-size:100% 100%; transition: background-size 0.7s ease; width:100%" data-z='${args->zoom:html:default(110):input_type(number):arg_name('Image zoom on hover, %'):arg_section(4, 1, 'Image', 'image')}' onmouseover="var z=this.getAttribute('data-z'); this.style.backgroundSize=z+'% '+z+'%'" onmouseout="this.style.backgroundSize='100% 100%'">
							<img src="${p->image_big_url:html}" data-style="visibility:hidden; width:auto; height:auto; max-width:100%; max-height:${args->img_max_height:html:default('sel(300px, 30vw)'):input_type(css_length):input_props('with_responsive=1'):arg_name(Image maximum height):arg_section(0, 5, 'Frame', 'th-large')}">
						</div>
					</a>
					<div data-style="margin:auto; box-sizing:border-box; width:${args->img_width:html}">
						<div data-style="${args->a_css:html:default('    font-family: ''Roboto'',sans-serif;
    font-size: 14px;
    line-height: 1.6;
    color: #333;
    font-weight:500;
text-align: start;
margin: 10px;
text-overflow: ellipsis;
text-transform: none;
white-space: nowrap;
overflow: hidden;'):input_type(css):input_props('with_responsive=1'):arg_name(Text color):arg_section(5, 3, 'Text', 'align-justify')}">
							${p->title:arg_name(Item text):arg_section(5, 1, 'Text', 'align-justify')}
						</div>
					</div>
					${block->price:default(1):arg_name(With price):arg_section(7, 0, 'Price', 'dollar')}
					<div data-style="margin:auto; box-sizing:border-box; width:${args->img_width:html}; ${args->price_style:html:default('color: #d32f2f;
text-align: start;
padding: 10px;
font-size: sel(1.2em, 1.1em);
font-size: 17px;
    font-weight: 700;
    color: #a00003;'):input_type(css):input_props('with_responsive=1'):arg_name(Price style):arg_section(7, 1, 'Price', 'dollar')}">
						${if p->price}
							${args->before_price:arg_name(Text before price):arg_section(7, 2, 'Price', 'dollar')}
							${if p->sale_price and p->sale_price < p->price}
								${p->sale_price:truncate(2):sprintf($%s):arg_name(Price):arg_section(7, 6, 'Price', 'dollar')}
								<div style="${args->sale_style:html:default('color:gray; text-decoration:line-through; font-size:85%'):input_type(css):input_props('with_responsive=1'):arg_name('Price before discount: style'):arg_section(7, 4, 'Price', 'dollar')}">
									${p->price:truncate(2):sprintf($%s):arg_name(Price):arg_section(7, 3, 'Price', 'dollar')}
								</div>
							${end}
							${if not p->sale_price or p->sale_price >= p->price}
								${p->price:truncate(2):sprintf($%s)}
							${end}
							${args->after_price:arg_name(Text after price):arg_section(7, 5, 'Price', 'dollar')}
						${end}
					</div>
					<div style="margin:auto; box-sizing:border-box; font-size:1px">
						<div data-style="display:inline-block; background-color:${args->border_color:html}; ${args->a_css_2:html:default('width:100px; height:3px; max-width:80%'):input_type(css):input_props('with_responsive=1'):arg_name(Ruler):arg_section(5, 5, 'Text', 'align-justify')}"></div>
					</div>
					${block->description:default(0):arg_name(With description):arg_section(5, 0, 'Text', 'align-justify')}
					<div data-style="margin:auto; box-sizing:border-box; width:${args->img_width:html}">
						<div data-style="display:inline-block; ${args->a_css_3:html:input_type(css):input_props('with_responsive=1'):arg_name(Text color):arg_section(5, 4, 'Text', 'align-justify')}; padding-bottom:0">
							${p->description:arg_name(Item text):arg_section(5, 2, 'Text', 'align-justify')}
						</div>
					</div>
					${block->button:default(0):arg_name(With button):arg_section(8, 0, 'Second line', 'text-height')}
					<a data-emarketer-click-target="products ${p->internal_id:html}" href="${p->cart_url:html}" target="${args->target:html}" data-style="display:inline-block; position:relative; top:1.3em; text-decoration:none; transition: font-size 0.3s ease; background-color:${args->border_color:html}; ${args->a_css_4:html:input_type(css):input_props('with_responsive=1'):arg_name(Button style):arg_section(8, 2, 'Second line', 'text-height')}" onmouseenter="var t=this; s=t.style, f=s.fontSize, p=f.match(/^([\d\.]+)(\w+)$/); if (!t._b) t._b=[s.backgroundColor, s.color, f]; s.backgroundColor=t._b[1]; s.color=t._b[0]; if (p) if (!t._p) {s.fontSize=(p[1]*0.9)+p[2]; t._p=1; setTimeout(function() {s.fontSize=t._b[2]; t._p=0;}, 300)}" onmouseleave="var s=this.style, b=this._b; s.backgroundColor=b[0]; s.color=b[1]">
						<div data-style="border:solid 1px; ${args->a_css_5:html:input_type(css):input_props('with_responsive=1'):arg_name(Button style):arg_section(8, 3, 'Second line', 'text-height')}">
							${args->button_text:arg_name(Button text):arg_section(8, 1, 'Second line', 'text-height')}
						</div>
					</a>
				</td>
			${end}
		</tr>
	</table>
	${block->pagination:default(0):arg_name(With slider pagination):arg_section(1, 10, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}
	<div id="tsp" class="$table_slider_pagination" slider_id="ts" selected_color="${args->pagination_color_on:html:input_type(color):arg_name(Bullet Selected Color):arg_section(1, 11, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" style="${args->pagination_color:html:input_type(css):arg_name(Bullet style):arg_section(1, 12, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}"></div>
</div>
```


## Slider with text on image

Slider with product image as a background

```
<div class="$responsive" data-style="display:inline-block; position:relative; ${args->style:html:default('border: none;
text-align: center;
max-width: 1100px;
margin-top: 1px;
margin-right: auto;
margin-bottom: 50px;
margin-left: auto;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(0, 1, 'Frame', 'th-large')}" onupdate="
	var
		w=Math.min(ns.joyquery('ancestor::table:limit(1) parent::div parent::div', by_id.ts).get(0).offsetWidth, document.documentElement.clientWidth-1),
		b=parseInt(by_id.ts.parentNode.parentNode.style.borderSpacing),
		a=ns.joyquery('parent::*>tr>td>*', by_id.ts).get(),
		d=a[0].parentNode,
		t=d.offsetWidth,
		n=Math.max(Math.round((w-b)/(t+b)), Math.min(2, by_id.ts.children.length)),
		T=Math.round((w-b)/n-b-parseFloat(d.style.borderLeftWidth)*2);
	for (i=0; i!=a.length; i++) if (a[i].style.display!='inline-block') a[i].style.width=T+'px';

	for (var e, i=ns.joyquery('.st_ovr', this); e=i();) e.style.borderRadius = e.parentNode.style.borderRadius;
	for (var e, i=ns.joyquery('.st_pd', this); e=i();) e.style.padding = e.previousElementSibling.style.padding, e.style.paddingLeft=0;
">
	${block->title:default(1):arg_name(With title bar):arg_section(2, 0, 'Title', 'bookmark')}
	<table data-style="width:100%; border-collapse:collapse; border:none; ${args->title_bg:html:default('background-color: rgba(170, 76, 76, 0);
margin-top: 0px;
margin-right: 0;
margin-bottom: 7px;
margin-left: 0px;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(2, 2, 'Title', 'bookmark')}">
		<tr>
			<td data-style="vertical-align:middle; ${args->title_style:html:default('font-size: sel(36px, 25px);
font-weight: normal;
text-align: center;
padding-top: 0.2em;
padding-right: 0.2em;
padding-bottom: 10px;
padding-left: 0.2em;
(custom): margin-bottom: 4px;
line-height: 1.1em;
vertical-align: top;
margin-top: 12px;
font-family: Georgia;'):input_type(css):input_props('with_responsive=1'):arg_name(Title style):arg_section(2, 3, 'Title', 'bookmark')}">
				${args->title:default('<div>#WeekBestSellers</div>
<span style="color: #999;
    font-size: 16px;
    line-height: 30px;">This-week hottest deals</span>'):arg_name(Text):arg_section(2, 1, 'Title', 'bookmark')}
			</td>
			${block->with_arrows:default(0):arg_name(With arrow buttons):arg_section(1, 0, 'With slider', 'arrow-right')}
			<td style="width:1px; white-space:nowrap; vertical-align:middle">
				<a id="button_back" class="$flat_btn" style="${args->btn_style:html:input_type(css):arg_name(Arrow button style):arg_section(1, 1, 'With slider', 'arrow-right')}" hover_style="${args->btn_hover_style:html:input_type(css):arg_name('Arrow button style: hover'):arg_section(1, 2, 'With slider', 'arrow-right')}"><</a>
				<a id="button_forward" class="$flat_btn" style="${args->btn_style:html}" hover_style="${args->btn_hover_style:html}">></a>
			</td>
			${block->x:default(0):arg_name(With close button):arg_section(3, 0, 'Close button', 'close')}
			<td style="width:1px; white-space:nowrap; ${args->x_style:html:input_type(css):arg_name(Close button position):arg_section(3, 2, 'Close button', 'close')}">
				${args->x:input_type(dontshowagain):input_props('style=cursor:pointer; vertical-align:middle'):arg_name(Close button):arg_section(3, 1, 'Close button', 'close')}
			</td>
		</tr>
	</table>
	<table style="width:100%; border-collapse:separate; border-spacing:12px 0; margin-bottom:1.2em">
		<tr id="ts" class="$table_slider" data-disabled="${args->with_slider:html:input_type(checkbox):input_props('value_off=1','value_on='):arg_name(Use slider widget):arg_section(1, 4, 'With slider', 'arrow-right'):onchange('if (args.with_slider==1) block.with_arrows = block.pagination = 0')}" style="border:none; max-width:${args->width:html:default(none):input_type(css_length):input_props('with_options=none'):arg_name(Widget maximum width):arg_section(0, 0, 'Frame', 'th-large')}" for_max_vw="${args->for_max_vw:html:default(always):input_type(css_length):input_props('with_options=always'):arg_name(Slider widget only if screen width is less than or equal to):arg_section(1, 5, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" eq_cell_width="${args->eq_cell_width:html:default(1):input_type(checkbox):input_props('value_off=','value_on=1'):arg_name(Equal cell width):arg_section(0, 2, 'Frame', 'th-large')}" eq_cell_height="1" arrows_line="${args->arrows_line:html:default(0):input_type(checkbox):input_props('value_off=-1','value_on=0'):arg_name(Arrows in the middle of images):arg_section(1, 9, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" arrow_back_img="${args->arrow_back_img:html:default('https://static.emarketer.com/upload/4035/3256192fabeef23a.png'):input_type(emarketer_media_url):arg_name(Left arrow image):arg_section(1, 6, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" arrow_forward_img="${args->arrow_forward_img:html:default('https://static.emarketer.com/upload/4035/6447f3eea66d7795.png'):input_type(emarketer_media_url):arg_name(Right arrow image):arg_section(1, 7, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" pagination_id="tsp" arrow_back_id="button_back" arrow_forward_id="button_forward" arrows_offset="${args->arrows_offset:html:default(-15):input_type(number):arg_name(Slider arrows offset):arg_section(1, 8, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" hide_buttons="${args->hide_buttons:html:input_type(checkbox):input_props('value_off=','value_on=1'):arg_name(Hide arrow buttons when nothing to scroll):arg_section(1, 3, 'With slider', 'arrow-right'):visible_if('block.title-0 && block.with_arrows-0')}">
			${foreach sum_interested_products as p where p->n_goal>0 and p->custom_i_4=custom_i_4 order by p->n_goal desc limit 18}
				<td style="padding:0; text-align:center; background-color:white; border:solid ${args->border_color:html:default(white):input_type(color):arg_name(Border color):arg_section(0, 3, 'Frame', 'th-large')} 1px">
					<a data-emarketer-click-target="products ${p->internal_id:html}" href="${p->cart_url:html:arg_name(Link target URL):arg_section(6, 0, 'Link target URL', 'link'):column_tags('url','custom text')}" target="${args->target:html:default(_blank):input_type(a_target):arg_name(Open link in):arg_section(6, 1, 'Link target URL', 'link')}" data-style="display:block; position:relative; text-decoration:none; color:inherit; background-image:url(&quot;${p->image_big_url:html:arg_name(Item image):arg_section(4, 0, 'Image', 'image'):column_tags(image)}&quot;); background-repeat:no-repeat; ${args->link_style:html:default('background-size: cover;
border-radius: 10px;
box-shadow: box-shadow: rgb(173, 173, 173) 0px 5px 10px;
height: 210px;
width: 270px;
border: 5px;
white-space: normal;'):input_type(css):input_props('with_responsive=1'):arg_name(Picture style):arg_section(4, 3, 'Image', 'image')}" ontplready="try {new Function('ns', this.dataset.js).call(this, ns)} catch (e) {ns.error(e)}" data-js="${args->js:html:default('// this.href = ...'):input_type(source_javascript):arg_name(Javascript for Preprocessing Link URL):arg_section(6, 2, 'Link target URL', 'link')}">
						<img src="${p->image_big_url:html}" data-style="visibility:hidden; border:none; width:auto; height:auto; max-width:${args->img_w:html:default(270px):input_type(css_length):input_props('with_responsive=1'):arg_name(Image Maximum Width):arg_section(4, 1, 'Image', 'image')}; max-height:${args->img_h:html:default(210px):input_type(css_length):input_props('with_responsive=1'):arg_name(Image Maximum Height):arg_section(4, 2, 'Image', 'image')}" onerror="this.parentNode.parentNode.style.display='none'">

						${block->with_gradient_overlay:default(1):arg_name(With Gradient Overlay):arg_section(4, 4, 'Image', 'image')}
						<div class="st_ovr" data-style="position:absolute; width:100%; height:100%; left:0; top:0; ${args->gradient:html:default('background-image:linear-gradient(transparent,transparent,rgba(0,0,0,.8) 81%)'):input_type(css):input_props('with_responsive=1'):arg_name(Gradient Overlay):arg_section(4, 5, 'Image', 'image')}"></div>

						<div style="position:absolute; left:0; bottom:0; width:100%">
							<div style="display:flex; width:100%">
								<div data-style="flex-shrink:1; ${args->name_style:html:default('padding: 0.8em;
text-align: left;
color: white;
text-shadow: 1px 1px 1px rgba(0,0,0,.7);
font-size: sel(19px, 14px);
font-weight: 700;
font-family: "Open Sans", sans-serif;
border-right: 3 px;
white-space: normal;'):input_type(css):input_props('with_responsive=1'):arg_name(Price style):arg_section(5, 0, 'Product name', 'text-height')}">
									<div style="overflow:hidden" title="${p->title:html:arg_name(Product name):arg_section(5, 1, 'Product name', 'text-height')}">
										${p->title:html}
									</div>
									${block->with_l2:default(1):arg_name(With Second Line):arg_section(5, 2, 'Product name', 'text-height')}
									<div data-style="overflow:hidden; ${args->l2_style:html:default('font-size: sel(14px, 13px);
font-weight: lighter;'):input_type(css):input_props('with_responsive=1'):arg_name(Second Line Style):arg_section(5, 4, 'Product name', 'text-height')}">
										${p->brand:html:arg_name(Second Line):arg_section(5, 3, 'Product name', 'text-height')}
									</div>
								</div>
								${block->price:default(1):arg_name(With price):arg_section(7, 0, 'Second line', 'text-height'):onchange('args.rating_style = block.price ? ''float:right'' : '''';')}
								<div class="st_pd" data-style="flex-shrink:0; ${args->price_style:html:default('text-align:end; color:white; text-shadow:1px 1px 1px rgba(0,0,0,.7)'):input_type(css):input_props('with_responsive=1'):arg_name(Price style):arg_section(7, 4, 'Second line', 'text-height')}">
									${if p->price}
										${args->before_price:arg_name(Text before price):arg_section(7, 1, 'Second line', 'text-height')}
										${if p->sale_price and p->sale_price < p->price}
											${p->sale_price:truncate(2):sprintf($%s):arg_name(Price):arg_section(7, 2, 'Second line', 'text-height')}
											<div style="${args->sale_style:html:default('color: gray;
text-decoration: line-through;
font-size: 85%;
text-align: left;'):input_type(css):input_props('with_responsive=1'):arg_name('Price before discount: style'):arg_section(7, 6, 'Second line', 'text-height')}">
												${p->price:truncate(2):sprintf($%s):arg_name(Price):arg_section(7, 5, 'Second line', 'text-height')}
											</div>
										${end}
										${if not p->sale_price or p->sale_price >= p->price}
											${p->price:truncate(2):sprintf($%s)}
										${end}
										${args->after_price:arg_name(Text after price):arg_section(7, 3, 'Second line', 'text-height')}
									${end}
								</div>
							</div>
						</div>
					</a>
				</td>
			${end}
		</tr>
	</table>
	${block->pagination:default(0):arg_name(With slider pagination):arg_section(1, 10, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}
	<div id="tsp" class="$table_slider_pagination" slider_id="ts" selected_color="${args->pagination_color_on:html:input_type(color):arg_name(Bullet Selected Color):arg_section(1, 11, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" style="${args->pagination_color:html:input_type(css):arg_name(Bullet style):arg_section(1, 12, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}"></div>
</div>
```


## Slider with quick add to cart button

You can set quick add to cart button for recommended items

```
<div class="$responsive" data-style="display:inline-block; position:relative; ${args->style:html:default('padding-right: 0px;
padding-left: 0px;
border: none;
text-align: center;
font-weight: bold;
font-size: 17px;
box-sizing: border-box;
width: sel(auto, auto);
font-family: Roboto,sans-serif;
box-shadow: 0 3px 10px 0 rgba(0,0,0,0.08);
background-color: white;
margin-top: 50px;
margin-right: 0px;
margin-bottom: 1px;
margin-left: 0px;
min-width: 98%;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(0, 1, 'Frame', 'th-large')}" onupdate="
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
	${block->title:default(1):arg_name(With title bar):arg_section(2, 0, 'Title', 'bookmark')}
	<table data-style="width:98%; margin-right: 1%; margin-left: 1%; border-collapse:collapse; border:none; ${args->title_bg:html:default('background-color: rgb(75, 103, 129);
margin-top: 0px;
margin-right: 0;
margin-bottom: 25px;
padding-top: 0px;
padding-right: 0;
padding-bottom: 0px;
padding-left: 0;
border-bottom: none;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(2, 2, 'Title', 'bookmark')}">
		<tr>
			<td data-style="vertical-align:middle; ${args->title_style:html:default('text-align: center;
font-family: Lora, georgia, serif;
padding-top: 15px;
padding-right: 0px;
padding-bottom: 15px;
padding-left: 0px;
font-weight: 500;
font-size: 20px;
line-height: 1.2222em;
text-transform: capitalize;
color: white;'):input_type(css):input_props('with_responsive=1'):arg_name(Title style):arg_section(2, 3, 'Title', 'bookmark')}">
				${args->title:default('<div>Make Sure you got everything you need</div>
'):arg_name(Text):arg_section(2, 1, 'Title', 'bookmark')}
			</td>
			${block->with_arrows:default(0):arg_name(With arrow buttons):arg_section(1, 0, 'With slider', 'arrow-right')}
			<td style="width:1px; white-space:nowrap; vertical-align:middle">
				<a id="button_back" class="$flat_btn" style="${args->btn_style:html:input_type(css):arg_name(Arrow button style):arg_section(1, 1, 'With slider', 'arrow-right')}" hover_style="${args->btn_hover_style:html:input_type(css):arg_name('Arrow button style: hover'):arg_section(1, 2, 'With slider', 'arrow-right')}"><</a>
				<a id="button_forward" class="$flat_btn" style="${args->btn_style:html}" hover_style="${args->btn_hover_style:html}">></a>
			</td>
			${block->x:default(0):arg_name(With close button):arg_section(3, 0, 'Close button', 'close')}
			<td style="width:1px; white-space:nowrap; ${args->x_style:html:input_type(css):arg_name(Close button position):arg_section(3, 2, 'Close button', 'close')}">
				${args->x:input_type(dontshowagain):input_props('style=cursor:pointer; vertical-align:middle'):arg_name(Close button):arg_section(3, 1, 'Close button', 'close')}
			</td>
		</tr>
	</table>
	<table style="width:100%; border-collapse:separate; border-spacing:12px 0; margin-bottom:1.2em">
		<tr id="ts" class="$table_slider" data-disabled="${args->with_slider:html:input_type(checkbox):input_props('value_off=1','value_on='):arg_name(Use slider widget):arg_section(1, 4, 'With slider', 'arrow-right'):onchange('if (args.with_slider==1) block.with_arrows = block.pagination = 0')}" style="width: 100%; padding: 0 1%; box-sizing: border-box; border:none; max-width:${args->width:html:default(none):input_type(css_length):input_props('with_options=none'):arg_name(Widget maximum width):arg_section(0, 0, 'Frame', 'th-large')}" for_max_vw="${args->for_max_vw:html:input_type(css_length):input_props('with_options=always'):arg_name(Slider widget only if screen width is less than or equal to):arg_section(1, 5, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" eq_cell_width="${args->eq_cell_width:html:default(1):input_type(checkbox):input_props('value_off=','value_on=1'):arg_name(Equal cell width):arg_section(0, 2, 'Frame', 'th-large')}" eq_cell_height="1" arrows_line="${args->arrows_line:html:default(-1):input_type(checkbox):input_props('value_off=-1','value_on=0'):arg_name(Arrows in the middle of images):arg_section(1, 9, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" arrow_back_img="${args->arrow_back_img:html:default('https://static.emarketer.com/upload/4545/96b6126f483ffd5a.png'):input_type(emarketer_media_url):arg_name(Left arrow image):arg_section(1, 6, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" arrow_style="${args->arrow_style:html:default('background-color: rgba(256, 256, 256, 0.63);
box-shadow:0px 1px 6px -1px rgba(0, 0, 0, .3)'):input_type(css):arg_name(Arrows style):arg_section(1, 7, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" pagination_id="tsp" arrow_back_id="button_back" arrow_forward_id="button_forward" arrows_offset="${args->arrows_offset:html:input_type(number):arg_name(Slider arrows offset):arg_section(1, 8, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" hide_buttons="${args->hide_buttons:html:input_type(checkbox):input_props('value_off=','value_on=1'):arg_name(Hide arrow buttons when nothing to scroll):arg_section(1, 3, 'With slider', 'arrow-right'):visible_if('block.title-0 && block.with_arrows-0')}">
			${foreach recom_products_goal_goal_for_extra as p order by p->recom_rate_n_users desc limit 12}
				<td style="padding:0; text-align:center; background-color:white; border:solid ${args->border_color:html:default('rgba(178, 32, 32, 0)'):input_type(color):arg_name(Border color):arg_section(0, 4, 'Frame', 'th-large')} 1px">
					<a data-emarketer-click-target="products ${p->internal_id:html}" href="${p->cart_url:html:arg_name(Link target URL):arg_section(6, 0, 'Link target URL', 'link'):column_tags('url','custom text')}" target="${args->target:html:default(_self):input_type(a_target):arg_name(Open link in):arg_section(6, 1, 'Link target URL', 'link')}" data-style="display:block; margin:auto; box-sizing:border-box; width:${args->img_width:html:default('sel(170px, 52vw)'):input_type(css_length):input_props('with_responsive=1'):arg_name(Cell width):arg_section(0, 3, 'Frame', 'th-large')}">
						<img src="${p->image_big_url:html:arg_name(Item image):arg_section(4, 0, 'Image', 'image'):column_tags(image)}" data-style="width:auto; height:auto; max-width:100%; max-height:${args->img_max_height:html:default('sel(196px, 30vw)'):input_type(css_length):input_props('with_responsive=1'):arg_name(Image maximum height):arg_section(0, 5, 'Frame', 'th-large')}">
					</a>
					<div data-style="margin:auto; box-sizing:border-box; width:${args->img_width:html}">
						<div data-style="${args->a_css:html:default('padding: 10px;
text-transform: none;
color: rgb(68, 68, 68);
font-family: Roboto;
font-weight: bold;
font-size: 14px;
text-align: left;'):input_type(css):input_props('with_responsive=1'):arg_name(Text color):arg_section(5, 3, 'Text', 'align-justify')}">
							${p->title:arg_name(Item text):arg_section(5, 1, 'Text', 'align-justify')}
						</div>
					</div>
					${block->rating:default(0):arg_name(With rating):arg_section(7, 0, 'Rating', 'star')}
					<div style="margin: auto; margin-bottom: .6em; line-height: 12px">
						<div style="width: 69px; height: 13px; font-size: 0; line-height: 0; background: url(https://skin.christys-hats.com/frontend/ultimo/totalRecall/images/img/rating.png) 0 0 repeat-x; text-indent: -999em; overflow: hidden; margin-left: 0; margin-right: 0; display: inline-block; vertical-align: middle;">
							<div style="float: left; height: 13px; background: url(https://skin.christys-hats.com/frontend/ultimo/totalRecall/images/img/rating.png) 0 100% repeat-x; width: ${p->rank:html:default(0):arg_name(Rating):arg_section(7, 1, 'Rating', 'star')}%">
							</div>
						</div>
					</div>
					<div style="clear:left;"></div>
					${block->price:default(1):arg_name(With price):arg_section(8, 0, 'Price', 'dollar')}
					<div data-style="margin:auto; box-sizing:border-box; width:${args->img_width:html}; ${args->price_style:html:default('color: #d32f2f;
font-size: sel(1.2em, 1.1em);
font-weight: 500;
text-align: start;
padding-top: 0px;
padding-right: 10px;
padding-bottom: 0px;
padding-left: 10px;'):input_type(css):input_props('with_responsive=1'):arg_name(Price style):arg_section(8, 5, 'Price', 'dollar')}">
						${if p->price}
							${args->before_price:arg_name(Text before price):arg_section(8, 1, 'Price', 'dollar')}
							${if p->sale_price and p->sale_price < p->price}
								${p->sale_price:truncate(2):sprintf($%s):arg_name(Price):arg_section(8, 6, 'Price', 'dollar')}
								<div style="${args->sale_style:html:default('color:gray; text-decoration:line-through; font-size:85%'):input_type(css):input_props('with_responsive=1'):arg_name('Price before discount: style'):arg_section(8, 3, 'Price', 'dollar')}">
									${p->price:truncate(2):sprintf($%s):arg_name(Price):arg_section(8, 2, 'Price', 'dollar')}
								</div>
							${end}
							${if not p->sale_price or p->sale_price >= p->price}
								${p->price:truncate(2):sprintf($%s)}
							${end}
							${args->after_price:arg_name(Text after price):arg_section(8, 4, 'Price', 'dollar')}
						${end}
					</div>
					<div style="margin:auto; box-sizing:border-box; font-size:1px">
						<div data-style="display:inline-block; background-color:${args->border_color:html}; ${args->a_css_2:html:default('width:100px; height:3px; max-width:80%'):input_type(css):input_props('with_responsive=1'):arg_name(Ruler):arg_section(5, 5, 'Text', 'align-justify')}"></div>
					</div>
					${block->description:default(0):arg_name(With description):arg_section(5, 0, 'Text', 'align-justify')}
					<div data-style="margin:auto; box-sizing:border-box; width:${args->img_width:html}">
						<div data-style="display:inline-block; ${args->a_css_3:html:input_type(css):input_props('with_responsive=1'):arg_name(Text color):arg_section(5, 4, 'Text', 'align-justify')}; padding-bottom:0">
							${p->description:arg_name(Item text):arg_section(5, 2, 'Text', 'align-justify')}
						</div>
					</div>
					${block->button:default(1):arg_name(With button):arg_section(9, 0, 'Button', 'hand-pointer-o')}
					<a class="$flat_btn" data-pid="${p->internal_id:html}" href="javascript:" data-style="${args->a_css_4:html:default('margin-top:1.3em; background-color:rgb(43, 167, 38); color:white; text-shadow:1px 1px 1px rgba(0,0,0,.7)'):input_type(css):input_props('with_responsive=1'):arg_name(Button style):arg_section(9, 2, 'Button', 'hand-pointer-o')}" hover_style="${args->a_css_42:html:default('background-color:rgb(55, 220, 48)'):input_type(css):input_props('with_responsive=1'):arg_name(Button style):arg_section(9, 3, 'Button', 'hand-pointer-o')}" data-added-msg="${args->added_msg:html:default(Product was added):arg_name(Text when Added to Cart):arg_section(9, 4, 'Button', 'hand-pointer-o')}" onclick="
						var pid = this.dataset.pid;
						var added_msg = this.dataset.addedMsg;
						${args->js:html:default('// Call your facility to add 1 product to cart
function add_to_cart(product_id, onsuccess)
{	// ...
	// ...
	// ...
	onsuccess();
	popup(added_msg, 5000); // variable "added_msg" contains message configurable from action parameters
}

// Function that shows popup (you can replace with your version)
function popup(html, timeout)
{	var pp = _S_T.new_elem
	(	''<div class="$popup" data-design="menu" style="padding:50px; font-size:22px; min-width:120px">''+
			html+
			''<center><a id="x" style="display:inline-block; margin-top:1em; border-radius:4px; text-decoration:none; font-size:15px; background-color:#FF9900; color:white; padding:0.3em; cursor:pointer">Close</a></center>''+
		''</div>'',
		null,
		{x: {onclick: x}}
	);
	pp._show({template: ''animator_fade''});
	if (timeout)
	{	setTimeout(x, timeout);
	}
	function x()
	{	pp._hide({template: ''animator_fade''});
	}
}

// This logs interaction event to Personyze
function success()
{	emarketer.push([''Product Added to cart'', pid, ''action_id'', ${action_id}]);
}

add_to_cart(pid, success);
'):input_type(source_javascript):arg_name(Add button Javascript Action):arg_section(9, 5, 'Button', 'hand-pointer-o')}
					">
						${args->button_add_text:default(Add to cart):arg_name(Add to cart Button text):arg_section(9, 1, 'Button', 'hand-pointer-o')}
					</a>
				</td>
			${end}
		</tr>
	</table>
	${block->pagination:default(0):arg_name(With slider pagination):arg_section(1, 10, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}
	<div id="tsp" class="$table_slider_pagination" slider_id="ts" selected_color="${args->pagination_color_on:html:input_type(color):arg_name(Bullet Selected Color):arg_section(1, 11, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" style="${args->pagination_color:html:input_type(css):arg_name(Bullet style):arg_section(1, 12, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}"></div>
</div>
```


## Bundle

Bundle with a quick checkout option or add to Personyze wishlist

```
<div class="$responsive" data-style="${args->style:html:default('display:inline-block; color: #777777;
background-color: white;
border: none;
font-size: 12px;
text-align: left;
min-width: 320px;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(0, 1, 'Frame', 'th-large')}">
	${block->title:default(1):arg_name(With title bar):arg_section(2, 0, 'Title', 'bookmark')}
	<table data-style="width:100%; border-collapse:collapse; border:none; ${args->title_bg:html:input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(2, 2, 'Title', 'bookmark')}">
		<tr>
			<td data-style="vertical-align:middle; ${args->title_style:html:default('font-size: 20px;
color: rgb(31, 19, 19);
padding-top: 5px;
padding-right: 0px;
padding-bottom: 0px;
padding-left: 12px;
font-weight: 500;'):input_type(css):input_props('with_responsive=1'):arg_name(Title style):arg_section(2, 3, 'Title', 'bookmark')}">
				${args->title:default(Frequently bought together):arg_name(Text):arg_section(2, 1, 'Title', 'bookmark')}
			</td>
			${block->with_arrows:default(0):arg_name(With arrow buttons):arg_section(3, 0, 'With slider arrows', 'arrows-h')}
			<td style="width:1px; white-space:nowrap; vertical-align:middle">
				<a id="button_back" class="$flat_btn" style="${args->btn_style:html:input_type(css):arg_name(Arrow button style):arg_section(3, 1, 'With slider arrows', 'arrows-h')}" hover_style="${args->btn_hover_style:html:input_type(css):arg_name('Arrow button style: hover'):arg_section(3, 2, 'With slider arrows', 'arrows-h')}"><</a>
				<a id="button_forward" class="$flat_btn" style="${args->btn_style:html}" hover_style="${args->btn_hover_style:html}">></a>
			</td>
			${block->x:default(0):arg_name(With close button):arg_section(4, 0, 'Close button', 'close')}
			<td style="width:1px; white-space:nowrap; ${args->x_style:html:input_type(css):arg_name(Close button position):arg_section(4, 2, 'Close button', 'close')}">
				${args->x:input_type(dontshowagain):input_props('style=cursor:pointer; vertical-align:middle'):arg_name(Close button):arg_section(4, 1, 'Close button', 'close')}
			</td>
		</tr>
	</table>
	<style>
		.st_t .st_plus {display: none !important}
		.st_t td.st_vis ~ td .st_plus {display: block !important}
	</style>
	<table>
		<tr>
			<td>
				<table id="st_t" class="st_t" style="width:100%; border-collapse:collapse; border:none">
					<tr class="$table_slider" data-disabled="${args->with_slider:html:default(1):input_type(checkbox):input_props('value_off=1','value_on='):arg_name(Use slider widget):arg_section(1, 0, 'With slider', 'arrow-right'):onchange('block.with_arrows=args.with_slider!=1')}" style="border:none; max-width:${args->width:html:default(600px):input_type(css_length):input_props('with_options=none'):arg_name(Widget maximum width):arg_section(0, 0, 'Frame', 'th-large')}" for_max_vw="${args->for_max_vw:html:input_type(css_length):input_props('with_options=always'):arg_name(Slider widget only if screen width is less than or equal to):arg_section(1, 1, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" eq_cell_width="${args->eq_cell_width:html:default(1):input_type(checkbox):input_props('value_off=','value_on=1'):arg_name(Equal cell width):arg_section(0, 2, 'Frame', 'th-large')}" eq_cell_height="${args->eq_cell_height:html:input_type(checkbox):input_props('value_off=','value_on=1'):arg_name(Equal rows height):arg_section(0, 3, 'Frame', 'th-large')}" arrow_back_img="${args->arrow_back_img:html:input_type(emarketer_media_url):arg_name(Left arrow image):arg_section(1, 2, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" arrow_forward_img="${args->arrow_forward_img:html:input_type(emarketer_media_url):arg_name(Right arrow image):arg_section(1, 3, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" arrow_back_id="button_back" arrow_forward_id="button_forward">
						${foreach products_interactions as p where p->interaction_time >= tm order by p->interaction_time desc limit 1}
							<td data-style="position:relative; ${args->td_style:html:default('text-align: center;
vertical-align: middle;
padding-top: 5px;
padding-right: 10px;
padding-bottom: 5px;
padding-left: 10px;
border: none;
max-width: 130px;
min-width: 110px;
width: 110px;'):input_type(css):input_props('with_responsive=1'):arg_name(Cell style):arg_section(0, 4, 'Frame', 'th-large')}">
								<span>
									<input class="st_internal_id" type="hidden" value="${p->internal_id:html}">
									<a data-emarketer-click-target="products ${p->internal_id:html}" href="${p->cart_url:html:arg_name(Link target URL):arg_section(7, 0, 'Link target URL', 'link'):column_tags('url','custom text')}" target="${args->target:html:default(_self):input_type(a_target):arg_name(Open link in):arg_section(7, 1, 'Link target URL', 'link')}" style="${args->link_style:html:default('font-size: 0px;'):input_type(css):arg_name(Link style):arg_section(6, 1, 'Product name', 'text-height')}">
										<img src="${p->image_big_url:html:arg_name(Item image):arg_section(5, 0, 'Image', 'image'):column_tags(image)}" data-style="${args->main_img_style:html:default('border: double white 5px;
width: sel(auto, auto);
height: sel(120px, auto);
max-width: 200px;
max-height: 200px;'):input_type(css):input_props('with_responsive=1'):arg_name(Main image style):arg_section(5, 1, 'Image', 'image')}" onerror="this.parentNode.parentNode.style.display='none'">
									</a>
								</span>
								<a data-emarketer-click-target="products ${p->internal_id:html}" href="${p->cart_url:html}" target="${args->target:html}" style="${args->link_style:html}">
									<div class="st_title">${p->title:arg_name(Product name):arg_section(6, 0, 'Product name', 'text-height')}</div>
								</a>
								${block->n_viewed:default(0):arg_name(With site statistics):arg_section(8, 0, 'Site statistics', 'bar-chart')}
								<div>
									${args->n_viewed_text:arg_name(Text):arg_section(8, 1, 'Site statistics', 'bar-chart')}
									${foreach recom_products_goal_goal_for_last as p where (p->image_big_url IS NOT NULL AND p->image_big_url!='') limit 1}
										${s->n_viewed:arg_name(Number):arg_section(8, 2, 'Site statistics', 'bar-chart')}
									${end}
								</div>
								<div class="st_price" style="display:${args->with_price:html:default(none):input_type(checkbox):input_props('value_off=none','value_on=block'):arg_name(With price):arg_section(9, 0, 'Second line', 'text-height')}; ${args->price_style:html:default('margin-top: 0.4em'):input_type(css):arg_name(Price style):arg_section(9, 5, 'Second line', 'text-height')}">
									${if p->price}
										${args->before_price:arg_name(Text before price):arg_section(9, 2, 'Second line', 'text-height')}
										${if p->sale_price}
											<span style="${args->sale_style:html:default('color:gray; text-decoration:line-through; font-size:85%'):input_type(css):input_props('with_responsive=1'):arg_name('Price before discount: style'):arg_section(9, 7, 'Second line', 'text-height')}">
												${p->price:truncate(2):sprintf($%s):arg_name(Price):arg_section(9, 6, 'Second line', 'text-height')}
											</span>
											${p->sale_price:truncate(2):sprintf($%s):arg_name(Price):arg_section(9, 3, 'Second line', 'text-height')}
										${end}
										${if not p->sale_price}
											${p->price:truncate(2):sprintf($%s)}
										${end}
										${args->after_price:arg_name(Text after price):arg_section(9, 4, 'Second line', 'text-height')}
									${end}
								</div>
								${block->rating:default(0):arg_name(With rating):arg_section(9, 8, 'Second line', 'text-height')}
								<span style="display:block; ${args->rating_style:html:default('margin-top:0'):input_type(css):arg_name(Rating block style):arg_section(9, 11, 'Second line', 'text-height')}">
									<input class="$rating" value="${p->sale_price:html:arg_name(Rating):arg_section(9, 9, 'Second line', 'text-height')}" max="${args->rank_max:html:default(5000):input_type(number):arg_name(Maximum rating number that corresponds to 100%):arg_section(9, 10, 'Second line', 'text-height')}">
								</span>
							</td>
						${end}

						${foreach recom_products_goal_goal_for_last as p where (p->price - p->last_interaction_price)/p->last_interaction_price between 0 and 0 and (p->image_big_url IS NOT NULL AND p->image_big_url!='') limit 2}
							<td data-style="position:relative; ${args->td_style:html}">
								<span>
									<div class="st_plus" style="position:absolute; top:50%; left:-0.5em; width:1em; height:1em; line-height:1em; margin-top:-0.5em; text-align: center; ${args->plus_style:html:default('color:gray; font-size:26px'):input_type(css):arg_name(Plus sign style):arg_section(10, 0, 'Plus sign', 'plus')}">+</div>
									<input class="st_internal_id" type="hidden" value="${p->internal_id:html}">
									<a data-emarketer-click-target="products ${p->internal_id:html}" href="${p->cart_url:html}" target="${args->target:html}" style="${args->link_style:html}">
										<img src="${p->image_big_url:html}" data-style="${args->img_style:html:default('border: double white 5px;
width: sel(auto, auto);
height: sel(auto, auto);
max-height: 100px;
max-width: 100px;'):input_type(css):input_props('with_responsive=1'):arg_name(Item image style):arg_section(5, 2, 'Image', 'image')}" onerror="this.parentNode.parentNode.style.display='none'">
									</a>
								</span>
								<a data-emarketer-click-target="products ${p->internal_id:html}" href="${p->cart_url:html}" target="${args->target:html}" style="${args->link_style:html}">
									<div class="st_title">${p->title}</div>
								</a>
								${block->n_viewed:default(0):arg_name(With site statistics):arg_section(8, 0, 'Site statistics', 'bar-chart')}
								<div>
									${args->n_viewed_text}
									${foreach recom_products_goal_goal_for_last as p where (p->image_small_url IS NOT NULL AND p->image_small_url!='') limit 1}
										${s->n_viewed}
									${end}
								</div>
								${block->price:default(1):arg_name(With price):arg_section(9, 1, 'Second line', 'text-height')}
								<div class="st_price" style="display:${args->with_price:html}; ${args->price_style:html}">
									${if p->price}
										${args->before_price}
										${if p->sale_price}
											<span style="${args->sale_style:html}">
												${p->price:truncate(2):sprintf($%s)}
											</span>
											${p->sale_price:truncate(2):sprintf($%s)}
										${end}
										${if not p->sale_price}
											${p->price:truncate(2):sprintf($%s)}
										${end}
										${args->after_price}
									${end}
								</div>
								${block->rating:default(0):arg_name(With rating):arg_section(9, 8, 'Second line', 'text-height')}
								<span style="display:block; ${args->rating_style:html}">
									<input class="$rating" value="${p->sale_price:html}" max="${args->rank_max:html}">
								</span>
							</td>
						${end}
					</tr>
				</table>
			</td>
			<td style="vertical-align:top; white-space:nowrap">
				<div>
					<span style="${args->tot_text_style:html:default('font-weight: normal;
font-size: 13px;'):input_type(css):arg_name(Total price text style):arg_section(11, 6, 'Add to cart button', 'mouse-pointer')}">
						${args->tot_text:default('Total price:'):arg_name(Total price text):arg_section(11, 5, 'Add to cart button', 'mouse-pointer')}
					</span>
					<span id="st_tot" style="${args->tot_style:html:default('font-weight: normal;
font-size: 20px;
color: #B1240B;'):input_type(css):arg_name(Total price style):arg_section(11, 7, 'Add to cart button', 'mouse-pointer')}"></span>
				</div>
				<button  id="st_btn1" class="$flat_btn" data-added-msg="${args->added_msg:html:default(Products were added):arg_name(Text when Added to Cart):arg_section(11, 3, 'Add to cart button', 'mouse-pointer')}" style="${args->add_btn_style:html:default('width: 120px;
display: block;
padding: 8px;
outline: none;
border: none;
font-size: 13px;
font-weight: normal;
border-radius: 3px;
color: white;
background-color: rgb(4, 204, 10);
text-align: center;
margin-top: 13px;
margin-right: 0px;
margin-bottom: 0px;
margin-left: 0px;'):input_type(css):arg_name(Button style):arg_section(11, 1, 'Add to cart button', 'mouse-pointer')}" hover_style="${args->add_btn_hover_style:html:default('color: white;
background-color: rgb(49, 237, 121);'):input_type(css):arg_name('Button style: hover'):arg_section(11, 2, 'Add to cart button', 'mouse-pointer')}" data-onclick="
     var list = this._list;
     var added_msg = this.dataset.addedMsg;
     ${args->js:html:default('// Call your facility to add products to cart
function add_to_cart(product_id_array, onsuccess)
{	// ...
	// ...
	// ...
	onsuccess();
	popup(added_msg, 5000); // variable "added_msg" contains message configurable from action parameters
}

// Function that shows popup (you can replace with your version)
function popup(html, timeout)
{	var pp = _S_T.new_elem
	(	''<div class="$popup" data-design="menu" style="padding:50px; font-size:22px; min-width:120px">''+
			html+
			''<center><a id="x" style="display:inline-block; margin-top:1em; border-radius:4px; text-decoration:none; font-size:15px; background-color:#FF9900; color:white; padding:0.3em; cursor:pointer">Close</a></center>''+
		''</div>'',
		null,
		{x: {onclick: x}}
	);
	pp._show({template: ''animator_fade''});
	if (timeout)
	{	setTimeout(x, timeout);
	}
	function x()
	{	pp._hide({template: ''animator_fade''});
	}
}

// This logs interaction events to Personyze
function success()
{	for (var i=0; i<list.length; i++)
	{	emarketer.push([''Product Added to cart'', list[i], ''action_id'', ${action_id}]);
	}
}

add_to_cart(list, success);
'):input_type(source_javascript):arg_name(Add button Javascript Action):arg_section(11, 4, 'Add to cart button', 'mouse-pointer')}
    ">
     ${args->add_btn_text:default(Add all to cart):arg_name(Text):arg_section(11, 0, 'Add to cart button', 'mouse-pointer')}
    </button>
				${block->with_fav:default(1):arg_name(With Add to favorites):arg_section(12, 0, 'Add to favorites', 'heart')}
				<div>
					<button id="st_btn2" class="$flat_btn" style="${args->fvt_btn_style:html:default('width: 120px;
display: block;
margin-top: 0.5em;
padding: 8px;
outline: none;
border: none;
font-size: 13px;
font-weight: normal;
border-radius: 3px;
color: white;
background-color: rgba(7, 2, 2, 0.38);
text-align: center;'):input_type(css):arg_name(Button style):arg_section(12, 2, 'Add to favorites', 'heart')}" hover_style="${args->fvt_btn_hover_style:html:default('color: white;
background-color: rgba(119, 119, 119, 0.76);'):input_type(css):arg_name('Button style: hover'):arg_section(12, 3, 'Add to favorites', 'heart')}" data-added-msg="${args->added:html:default(Products added to wishlist):arg_name(Added to wishlist message):arg_section(12, 4, 'Add to favorites', 'heart')}">
						${args->fvt_btn_text:default(Add to wishlist):arg_name(Text):arg_section(12, 1, 'Add to favorites', 'heart')}
					</button>
				</div>
			</td>
		</tr>
	</table>
	<table style="border-collapse:collapse; border:none; margin:5px" ontplready="
		var tr=by_id.st_tr, tbody=by_id.st_t.children[0], n=tbody.children[0].children.length;
		if (tr) for (var i=0; i!=n; i++)
		{	tr.set_length(n);
			var t_by_id = tr[i].by_id;
			function gt(i, name)
			{	return ns.joyquery('td:nth-child('+(i+1)+') [class~=\'st_'+name+'\']', tbody).get(0);
			}
			t_by_id.st_for_internal_id.value = gt(i, 'internal_id').value;
			t_by_id.st_for_title.innerHTML = gt(i, 'title').innerHTML;
			t_by_id.st_for_price.innerHTML = (gt(i, 'price') || {}).innerHTML || '';
			function text_l0(elem)
			{	var t = '';
				for (var e=elem.firstChild; e; e=e.nextSibling)
				{	if (e.nodeType == 3) t += e.data;
				}
				return t;
			}
			function ch()
			{	var tot=0, fmt='~`', d, v, list=[], vis=0;
				for (var i=0; i!=tr.length; i++)
				{	var t_by_id = tr[i].by_id;
					fmt = text_l0(t_by_id.st_for_price).replace(/[\d\.]+/, function(m) {d=+m; return '~`'});
					v = t_by_id.st_for_internal_id.checked;
					if (v)
					{	tot += d||0;
						list.push(t_by_id.st_for_internal_id.value);
						vis++;
					}
					for (var e, it=ns.joyquery('td:nth-child('+(i+1)+')', tbody); e=it();)
					{	e.className = v ? 'st_vis' : '';
						_S_T.new_elem(e).add_style({opacity: +v, display: v ? '' : 'none'}, {});
					}
				}
				by_id.st_tot.textContent = fmt.replace('~`', tot.toFixed(2));
				by_id.st_btn1._list = list;
				by_id.st_btn1.style.display = vis ? '' : 'none';
				if (by_id.st_btn2) by_id.st_btn2.style.display = vis ? '' : 'none';
			}
			this.onclick = ch;
			setTimeout(ch, 0);

			if (by_id.st_btn2)
			{	by_id.st_btn2.onclick = function()
				{	var vis=0;
					for (var i=0; i!=tr.length; i++)
					{	var t_by_id = tr[i].by_id;
						if (t_by_id.st_for_internal_id.checked)
						{	_S_T.push(['Product Liked', t_by_id.st_for_internal_id.value]);
							vis++;
						}
					}
					if (vis)
					{	new _S_T.ElemsAnnotator('info').add(this, this.getAttribute('data-added-msg')).annotate(3000);
					}
				};
			}
		}
	">
		<tr id="st_tr" class="$repeat-elem" style="cursor:pointer">
			<td style="width:1px"><input id="st_for_internal_id" type="checkbox" checked="1"></td>
			<td style="padding:0 5px" id="st_for_title" onClick="var i=this.previousElementSibling.firstChild; i.checked=!i.checked"></td>
			<td id="st_for_price" onClick="this.previousElementSibling.onclick()"></td>
		</tr>
	</table>
</div>
```


## Buy together slider



```
<div class="$responsive" data-style="display:block; position:relative; ${args->style:html:default('padding-right: 0px;
padding-left: 0px;
border: none;
text-align: center;
font-weight: 500;
font-size: 17px;
box-sizing: border-box;
width: sel(auto, auto);
font-family: Roboto,sans-serif;
background-color: white;
margin-top: 10px;
margin-right: 0px;
margin-bottom: 1px;
margin-left: 0px;
min-width: 98%;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(0, 1, 'Frame', 'th-large')}" onupdate="
	var
		i,
		w=this.children[0].offsetWidth,
		b=parseFloat(by_id.st_ts.parentNode.parentNode.style.borderSpacing),
		a=ns.joyquery('parent::*>tr>td>*', by_id.st_ts).get()
	for (i=0; i!=a.length; i++) a[i].style.width=''
	var
		d=a[0].parentNode,
		t=d.offsetWidth,
		n=Math.floor((w-b)/(t+b)),
		T=(w-b)/n-b-parseFloat(d.style.borderLeftWidth)*2
	for (i=0; i!=a.length; i++) a[i].style.width=T+'px'
">
	${block->title:default(1):arg_name(With title bar):arg_section(2, 0, 'Title', 'bookmark')}
	<table data-style="width:100%; border-collapse:collapse; border:none; ${args->title_bg:html:default('background-color: rgb(75, 103, 129);
margin: 0px;
padding-top: 0px;
padding-right: 0;
padding-bottom: 0px;
padding-left: 0;
border-bottom: solid 1px #eaeaea;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(2, 2, 'Title', 'bookmark')}">
		<tr>
			<td data-style="vertical-align:middle; ${args->title_style:html:default('text-align: left;
font-family: Roboto, Sans-Serif;
padding: 15px;
font-weight: 500;
font-size: 18px;
line-height: 1.2222em;
text-transform: capitalize;
color: #333;
background-color: #ffffff;'):input_type(css):input_props('with_responsive=1'):arg_name(Title style):arg_section(2, 3, 'Title', 'bookmark')}">
				${args->title:default('Make sure you&#39;ve got everything you need'):arg_name(Text):arg_section(2, 1, 'Title', 'bookmark')}
			</td>
			${block->with_arrows:default(0):arg_name(With arrow buttons):arg_section(1, 0, 'With slider', 'arrow-right')}
			<td style="width:1px; white-space:nowrap; vertical-align:middle">
				<a id="button_back" class="$flat_btn" style="${args->btn_style:html:input_type(css):arg_name(Arrow button style):arg_section(1, 1, 'With slider', 'arrow-right')}" hover_style="${args->btn_hover_style:html:input_type(css):arg_name('Arrow button style: hover'):arg_section(1, 2, 'With slider', 'arrow-right')}"><</a>
				<a id="button_forward" class="$flat_btn" style="${args->btn_style:html}" hover_style="${args->btn_hover_style:html}">></a>
			</td>
			${block->x:default(0):arg_name(With close button):arg_section(3, 0, 'Close button', 'close')}
			<td style="width:1px; white-space:nowrap; ${args->x_style:html:input_type(css):arg_name(Close button position):arg_section(3, 2, 'Close button', 'close')}">
				${args->x:input_type(dontshowagain):input_props('style=cursor:pointer; vertical-align:middle'):arg_name(Close button):arg_section(3, 1, 'Close button', 'close')}
			</td>
		</tr>
	</table>
	<style>
		@media (max-width: 799px)
		{	.st_flex_wrap_nar {flex-wrap:wrap}
			.st_flex_wrap_nar a[data-emarketer-click-target] > img {max-width:40vw !important}
		}
	</style>
	<table style="width:100%; border-collapse:separate; border-spacing:8px 0; margin-bottom:1.2em">
		<tr id="st_ts" class="$table_slider" data-disabled="${args->with_slider:html:input_type(checkbox):input_props('value_off=1','value_on='):arg_name(Use slider widget):arg_section(1, 4, 'With slider', 'arrow-right'):onchange('if (args.with_slider==1) block.with_arrows = block.pagination = 0')}" style="width: 100%; padding: 0 1%; box-sizing: border-box; border:none; max-width:${args->width:html:default(none):input_type(css_length):input_props('with_options=none'):arg_name(Widget maximum width):arg_section(0, 0, 'Frame', 'th-large')}" for_max_vw="${args->for_max_vw:html:input_type(css_length):input_props('with_options=always'):arg_name(Slider widget only if screen width is less than or equal to):arg_section(1, 5, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" eq_cell_width="${args->eq_cell_width:html:default(1):input_type(checkbox):input_props('value_off=','value_on=1'):arg_name(Equal cell width):arg_section(0, 2, 'Frame', 'th-large')}" arrows_line="${args->arrows_line:html:default(-1):input_type(checkbox):input_props('value_off=-1','value_on=0'):arg_name(Arrows in the middle of images):arg_section(1, 9, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" arrow_back_img="${args->arrow_back_img:html:default('https://static.emarketer.com/upload/4545/96b6126f483ffd5a.png'):input_type(emarketer_media_url):arg_name(Left arrow image):arg_section(1, 6, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" arrow_style="${args->arrow_style:html:default('background-color: rgba(256, 256, 256, 0.63); box-shadow:0px 1px 6px -1px rgba(0, 0, 0, .3)'):input_type(css):arg_name(Arrows style):arg_section(1, 7, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" pagination_id="st_tsp" arrow_back_id="button_back" arrow_forward_id="button_forward" arrows_offset="${args->arrows_offset:html:input_type(number):arg_name(Slider arrows offset):arg_section(1, 8, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" hide_buttons="${args->hide_buttons:html:input_type(checkbox):input_props('value_off=','value_on=1'):arg_name(Hide arrow buttons when nothing to scroll):arg_section(1, 3, 'With slider', 'arrow-right'):visible_if('block.title-0 && block.with_arrows-0')}">
			${foreach recom_products_goal_goal_for_last as p order by p->recom_rate_n_transactions desc limit 12}
				<td style="padding:0; background-color:white; border:solid ${args->border_color:html:default('rgba(178, 32, 32, 0)'):input_type(color):arg_name(Border color):arg_section(0, 4, 'Frame', 'th-large')} 1px">
					<div class="st_flex_wrap_nar" style="display:flex; height:100%">
						${foreach products_interactions as c where c->interaction_time >= tm and c->status='viewed' order by c->interaction_time desc limit 1}
							<table style="height:100%; border-collapse:separate; border-spacing:12px 0">
								<tr>
									<td>
										<a data-emarketer-click-target="products ${c->internal_id:html}" href="${c->cart_url:html:arg_name(Link target URL):arg_section(6, 0, 'Link target URL', 'link'):column_tags('url','custom text')}" target="${args->target:html:default(_self):input_type(a_target):arg_name(Open link in):arg_section(6, 2, 'Link target URL', 'link')}" data-style="display:block; margin:auto; box-sizing:border-box; width:${args->img_width:html:default(140px):input_type(css_length):input_props('with_responsive=1'):arg_name(Cell width):arg_section(0, 3, 'Frame', 'th-large')}">
											<img src="${c->image_big_url:html:arg_name(Item image):arg_section(4, 0, 'Image', 'image'):column_tags(image)}" data-style="width:auto; height:auto; max-width:100%; max-height:${args->img_max_height:html:default(197px):input_type(css_length):input_props('with_responsive=1'):arg_name(Image maximum height):arg_section(0, 5, 'Frame', 'th-large')}">
										</a>
									</td>
									<td style="position:relative">
										<a data-emarketer-click-target="products ${p->internal_id:html}" href="${p->cart_url:html:arg_name(Link target URL):arg_section(6, 1, 'Link target URL', 'link'):column_tags('url','custom text')}" target="${args->target:html}" data-style="display:block; margin:auto; box-sizing:border-box; width:${args->img_width:html}">
											<img src="${p->image_big_url:html:arg_name(Item image):arg_section(4, 1, 'Image', 'image'):column_tags(image)}" data-style="width:auto; height:auto; max-width:100%; max-height:${args->img_max_height:html}">
										</a>
										<div style="position:absolute; top:50%; left:-0.8em; width:1em; height:1em; line-height:1em; margin-top:-0.5em; text-align: center; ${args->plus_style:html:default('color: gray; font-size: 20px;'):input_type(css):arg_name(Plus sign style):arg_section(8, 0, 'Plus sign', 'plus')}">+</div>
									</td>
								</tr>
								<tr>
									<td style="vertical-align:top;">
										<div data-style="margin:auto; box-sizing:border-box; width:${args->img_width:html}">
											<div data-style="${args->a_css:html:default('padding: 10px;
text-transform: none;
vertical-align: top;
color: rgb(68, 68, 68);
font-family: Roboto;
font-weight: 500;
font-size: 14px;
text-align: left;
max-height: 50px;
overflow: hidden;'):input_type(css):input_props('with_responsive=1'):arg_name(Text color):arg_section(5, 5, 'Text', 'align-justify')}">
												${c->title:arg_name(Item text):arg_section(5, 1, 'Text', 'align-justify')}
											</div>
										</div>
									</td>
									<td style="vertical-align:top;">
										<div data-style="margin:auto; box-sizing:border-box; width:${args->img_width:html}">
											<div data-style="${args->a_css:html}">
												${p->title:arg_name(Item text):arg_section(5, 2, 'Text', 'align-justify')}
											</div>
										</div>
									</td>
								</tr>
								<tr>
									<td style="vertical-align:top;">
										${block->price:default(1):arg_name(With price):arg_section(7, 0, 'Price', 'dollar')}
										<div class="st_price" data-style="margin:auto; box-sizing:border-box; width:${args->img_width:html}; ${args->price_style:html:default('color: #d32f2f;
font-size: sel(1em, 1.1em);
font-weight: 500;
text-align: start;
vertical-align: top;
padding-top: 0px;
padding-right: 10px;
padding-bottom: 0px;
padding-left: 10px;
display: block;'):input_type(css):input_props('with_responsive=1'):arg_name(Price style):arg_section(7, 1, 'Price', 'dollar')}">
											${if c->price}
												${args->before_price:arg_name(Text before price):arg_section(9, 2, 'Add to cart button', 'mouse-pointer')}
												${c->price:truncate('3'):sprintf('%s $'):arg_name(Price):arg_section(9, 4, 'Add to cart button', 'mouse-pointer')}
												${args->after_price:arg_name(Text after price):arg_section(9, 7, 'Add to cart button', 'mouse-pointer')}
												${if c->custom_1}
													<span style="${args->sale_style:html:default('color: gray;
text-decoration: line-through;
font-size: 85%;
display: block;'):input_type(css):input_props('with_responsive=1'):arg_name('Price before discount: style'):arg_section(9, 11, 'Add to cart button', 'mouse-pointer')}">
														${c->custom_1:truncate('2'):sprintf('%s $'):arg_name(Price):arg_section(9, 9, 'Add to cart button', 'mouse-pointer')}
													</span>
												${end}
											${end}
										</div>
										${block->description:default(0):arg_name(With description):arg_section(5, 0, 'Text', 'align-justify')}
										<div data-style="margin:auto; box-sizing:border-box; width:${args->img_width:html}">
											<div data-style="display:inline-block; ${args->a_css_3:html:input_type(css):input_props('with_responsive=1'):arg_name(Text color):arg_section(5, 6, 'Text', 'align-justify')}; padding-bottom:0">
												${c->description:arg_name(Item text):arg_section(5, 3, 'Text', 'align-justify')}
											</div>
										</div>
									</td>
									<td style="vertical-align:top;">
										${block->price:default(1):arg_name(With price):arg_section(7, 0, 'Price', 'dollar')}
										<div data-style="margin:auto; box-sizing:border-box; width:${args->img_width:html}; ${args->price_style:html}">
											${if p->price}
												${args->before_price}
												${p->price:truncate('3'):sprintf('%s $'):arg_name(Price):arg_section(9, 5, 'Add to cart button', 'mouse-pointer')}
												${args->after_price}
												${if p->custom_1}
													<span style="${args->sale_style:html}">
														${p->custom_1:truncate('2'):sprintf('%s $'):arg_name(Price):arg_section(9, 10, 'Add to cart button', 'mouse-pointer')}
													</span>
												${end}
											${end}
										</div>
										${block->description:default(0):arg_name(With description):arg_section(5, 0, 'Text', 'align-justify')}
										<div data-style="margin:auto; box-sizing:border-box; width:${args->img_width:html}">
											<div data-style="display:inline-block; ${args->a_css_3:html}; padding-bottom:0">
												${p->description:arg_name(Item text):arg_section(5, 4, 'Text', 'align-justify')}
											</div>
										</div>
									</td>
								</tr>
							</table>
							<div style="${args->total_price_style:html:default('white-space: nowrap;
font-size: 13px;
font-weight: bold;
color: #d00000;
padding-top: 25px;
padding-right: 1px;
padding-bottom: 1px;
padding-left: 25px;
text-align: left;'):input_type(css):arg_name(Total Price style):arg_section(7, 3, 'Price', 'dollar')}">
								${args->total_price:default('Total price:'):arg_name(Total Price Text):arg_section(7, 2, 'Price', 'dollar')}
								<span style="${args->total_price_n_style:html:default('font-size:20px; font-weight:normal'):input_type(css):arg_name(Total Price Number style):arg_section(7, 4, 'Price', 'dollar')}" ontplready='
									var pp=${p->price:html:json}-0, ps=${p->sale_price:html:json}-0, cp=${c->price:html:json}-0, cs=${c->sale_price:html:json}-0, sum=Math.round((Math.min(pp || Infinity, ps || Infinity) + Math.min(cp || Infinity, cs || Infinity))*1000)/1000;
									if (isFinite(sum))
									{	var fmt_e = this.parentNode.parentNode.parentNode.querySelector(".st_price");
										if (fmt_e)
										{	function text_l0(elem)
											{	var t = "";
												for (var e=elem.firstChild; e; e=e.nextSibling)
												{	if (e.nodeType == 3) t += e.data;
												}
												return t;
											}
											var d, fmt = text_l0(fmt_e).trim().replace(/[\d,]+\.(\d+)/, function(a, m) {d=m.length; return "~`"});
											if (d) sum = fmt.replace("~`", sum.toFixed(d));
										}
										this.textContent = sum;
									}
								'></span>
								<div>
									<button class="$flat_btn" style="${args->add_btn_style:html:default('padding: 8px;
outline: none;
border: none;
font-size: 13px;
font-weight: normal;
border-radius: 3px;
white-space: nowrap;
color: white;
background-color: #ff9400;
text-align: center;
margin-top: 13px;
margin-right: 0px;
margin-bottom: 0px;
margin-left: 0px;
width: 120px;'):input_type(css):arg_name(Button style):arg_section(9, 1, 'Add to cart button', 'mouse-pointer')}" hover_style="${args->add_btn_hover_style:html:default('color: white;
background-color: rgb(167, 225, 19);'):input_type(css):arg_name('Button style: hover'):arg_section(9, 3, 'Add to cart button', 'mouse-pointer')}" data-added-msg="${args->added_msg:html:default(Product was added):arg_name(Text when Added to Cart):arg_section(9, 6, 'Add to cart button', 'mouse-pointer')}" onclick="
										var added_msg=this.dataset.addedMsg, list=[], a = this.parentNode.parentNode.parentNode.querySelectorAll('a[data-emarketer-click-target]');
										for (var i=0; i!=a.length; i++)
										{	list[i] = {pid: a[i].dataset.emarketerClickTarget.replace(/^\w+\s+/, ''), href: a[i].href};
										}
										${args->js:html:default('for (var i=0; i!=list.length; i++)
{	var rec = list[i];
emarketer.push([''Product Added to cart'', rec.pid, ''action_id'', ${action_id}]);
addToCart(''https://''+location.hostname+''/checkout/cart/add/uenc/''+btoa(rec.href)+''/product/''+rec.pid+''/form_key/GeqOmF0Go43U0pMh/'', ''crt'', rec.pid);
}'):input_type(source_javascript):arg_name(Add button Javascript Action):arg_section(9, 8, 'Add to cart button', 'mouse-pointer')}
									">
										${args->add_btn_text:default(Add all to cart):arg_name(Text):arg_section(9, 0, 'Add to cart button', 'mouse-pointer')}
									</button>
								</div>
							</div>
						${end}
					</div>
				</td>
			${end}
		</tr>
	</table>
	${block->pagination:default(0):arg_name(With slider pagination):arg_section(1, 10, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}
	<div id="st_tsp" class="$table_slider_pagination" slider_id="st_ts" selected_color="${args->pagination_color_on:html:input_type(color):arg_name(Bullet Selected Color):arg_section(1, 11, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" style="${args->pagination_color:html:input_type(css):arg_name(Bullet style):arg_section(1, 12, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}"></div>
</div>
```


## Multiple images + hover shadow



```
<div class="$responsive" data-style="display:inline-block; position:relative; ${args->style:html:default('text-align: left;
font-family: ''Roboto'',sans-serif;
margin-top: 15px;
margin-right: -20px;
margin-bottom: 15px;
margin-left: 0px;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(0, 1, 'Frame', 'th-large')}" onupdate="
	var
		w=Math.min(ns.joyquery('ancestor::table:limit(1) parent::div parent::div', by_id.ts).get(0).offsetWidth, document.documentElement.clientWidth-1),
		b=12,
		a=ns.joyquery('parent::*>tr>td>*', by_id.ts).get(),
		d=a[0].parentNode,
		t=d.offsetWidth,
		n=Math.max(Math.round((w-b)/(t+b)), Math.min(2, by_id.ts.children.length)),
		T=Math.round((w-b)/n-b-parseFloat(d.style.borderLeftWidth)*2);
	for (i=0; i!=a.length; i++) if (a[i].style.display!='inline-block') a[i].style.width=T+'px'
">
	${block->title:default(1):arg_name(With title bar):arg_section(2, 0, 'Title', 'bookmark')}
	<table data-style="width:100%; border-collapse:collapse; border:none; ${args->title_bg:html:default('margin-top: 5px;
margin-right: 0px;
margin-bottom: 5px;
margin-left: 20px;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(2, 2, 'Title', 'bookmark')}">
		<tr>
			<td data-style="vertical-align:middle; ${args->title_style:html:default('background: #FFFFFF;
display: inline-block;
padding-top: 0px;
padding-right: 15px;
padding-bottom: 0px;
padding-left: 0px;
margin-top: 0px;
margin-right: 0px;
margin-bottom: 10px;
margin-left: 0px;
border-bottom: 1px;
font-size: 16px;
color: #393939;
text-transform: uppercase;
border-color: rgba(0, 0, 0, 1);
font-weight: bold;'):input_type(css):input_props('with_responsive=1'):arg_name(Title style):arg_section(2, 3, 'Title', 'bookmark')}">
				${args->title:default(Customers Also Viewed):arg_name(Text):arg_section(2, 1, 'Title', 'bookmark')}
			</td>
			${block->with_arrows:default(0):arg_name(With arrow buttons):arg_section(1, 0, 'With slider', 'arrow-right')}
			<td style="width:1px; white-space:nowrap; vertical-align:middle">
				<a id="button_back" class="$flat_btn" style="${args->btn_style:html:input_type(css):arg_name(Arrow button style):arg_section(1, 1, 'With slider', 'arrow-right')}" hover_style="${args->btn_hover_style:html:input_type(css):arg_name('Arrow button style: hover'):arg_section(1, 2, 'With slider', 'arrow-right')}"><</a>
				<a id="button_forward" class="$flat_btn" style="${args->btn_style:html}" hover_style="${args->btn_hover_style:html}">></a>
			</td>
			${block->x:default(0):arg_name(With close button):arg_section(3, 0, 'Close button', 'close')}
			<td style="width:1px; white-space:nowrap; ${args->x_style:html:input_type(css):arg_name(Close button position):arg_section(3, 2, 'Close button', 'close')}">
				${args->x:input_type(dontshowagain):input_props('style=cursor:pointer; vertical-align:middle'):arg_name(Close button):arg_section(3, 1, 'Close button', 'close')}
			</td>
		</tr>
	</table>
	<table data-style="width:100%; border-collapse:separate; border-spacing:12px 8px; margin-bottom:1.2em; height:${args->img_max_height:html:default('sel(220px, 30vw)'):input_type(css_length):input_props('with_responsive=1'):arg_name(Image maximum height):arg_section(0, 5, 'Frame', 'th-large')}">
		<tr id="ts" class="$table_slider" data-disabled="${args->with_slider:html:input_type(checkbox):input_props('value_off=1','value_on='):arg_name(Use slider widget):arg_section(1, 4, 'With slider', 'arrow-right'):onchange('if (args.with_slider==1) block.with_arrows = block.pagination = 0')}" style="height:100%; border:none; max-width:${args->width:html:default(1060px):input_type(css_length):input_props('with_options=none'):arg_name(Widget maximum width):arg_section(0, 0, 'Frame', 'th-large')}" for_max_vw="${args->for_max_vw:html:default(always):input_type(css_length):input_props('with_options=always'):arg_name(Slider widget only if screen width is less than or equal to):arg_section(1, 5, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" eq_cell_width="${args->eq_cell_width:html:default(1):input_type(checkbox):input_props('value_off=','value_on=1'):arg_name(Equal cell width):arg_section(0, 2, 'Frame', 'th-large')}" arrows_line="${args->arrows_line:html:default(0):input_type(checkbox):input_props('value_off=-1','value_on=0'):arg_name(Arrows in the middle of images):arg_section(1, 9, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" arrow_back_img="${args->arrow_back_img:html:default('https://static.emarketer.com/upload/4545/96b6126f483ffd5a.png'):input_type(emarketer_media_url):arg_name(Left arrow image):arg_section(1, 6, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" arrow_style="${args->arrow_style:html:default('box-shadow: 0px 8px 6px 8px rgba(0, 0, 0, 0.23);
background-color: rgba(256, 256, 256, 0.56);'):input_type(css):arg_name(Arrows style):arg_section(1, 7, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" pagination_id="tsp" arrow_back_id="button_back" arrow_forward_id="button_forward" arrows_offset="${args->arrows_offset:html:default(0):input_type(number):arg_name(Slider arrows offset):arg_section(1, 8, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" hide_buttons="${args->hide_buttons:html:input_type(checkbox):input_props('value_off=','value_on=1'):arg_name(Hide arrow buttons when nothing to scroll):arg_section(1, 3, 'With slider', 'arrow-right'):visible_if('block.title-0 && block.with_arrows-0')}">
			${foreach recom_products_viewed_viewed_for_last as p order by p->recom_rate_n_transactions desc limit 18}
				<td style="height:100%; width:${args->img_width:html:default('sel(200px, 28vw)'):input_type(css_length):input_props('with_responsive=1'):arg_name(Cell width):arg_section(0, 3, 'Frame', 'th-large')}; padding:0; text-align:center; background-color:white; border:solid ${args->border_color:html:default(white):input_type(color):arg_name(Border color):arg_section(0, 4, 'Frame', 'th-large')} 1px; transition: all .3s ease-in-out" onmouseenter="this.style.boxShadow='0 0 20px rgba(0,0,0,.2)'" onmouseleave="this.style.boxShadow=''">
					<div data-style="height:100%; width:${args->img_width:html}; display:flex; flex-direction:column">
						<a data-emarketer-click-target="products ${p->internal_id:html}" href="${p->cart_url:html:arg_name(Link target URL):arg_section(5, 0, 'Link target URL', 'link'):column_tags('url','custom text')}" target="${args->target:html:default(_self):input_type(a_target):arg_name(Open link in):arg_section(5, 1, 'Link target URL', 'link')}" data-style="flex-grow:100; display:flex; justify-content:center; align-items:center; margin:auto; box-sizing:border-box">
							<div style="position:relative; display:inline-block" onmouseenter="this.children[0].style.opacity=0; this.children[1].children[0].style.opacity=1" onmouseleave="this.children[0].style.opacity=1; this.children[1].children[0].style.opacity=0">
								<img src="${p->image_big_url:html}" data-style="width:auto; height:auto; max-width:100%; max-height:${args->img_max_height:html}; opacity:1; transition:opacity ease 0.4s">
								${if p->image_medium_url != ''}
									<div style="position:absolute; left:0; top:0; width:100%; height:100%; display:flex; justify-content:center; align-items:center">
										<img src="${p->image_big_url:html}" style="width:auto; height:auto; max-width:100%; max-height:100%; opacity:0; transition:opacity ease 0.4s">
									</div>
								${end}
							</div>
						</a>
						<div data-style="margin:auto; box-sizing:border-box; width:100%">
							<div data-style="${args->a_css:html:default('font-size: 16px;
font-weight: 700;
font-family: Montserrat,sans-serif;
text-align: start;
margin: 10px;
text-transform: none;
color: #333;
min-width: 100%;'):input_type(css):input_props('with_responsive=1'):arg_name(Text color):arg_section(4, 3, 'Text', 'align-justify')}">
								${p->title:arg_name(Item text):arg_section(4, 1, 'Text', 'align-justify')}
							</div>
						</div>
						${block->price:default(1):arg_name(With price):arg_section(6, 0, 'Price', 'dollar')}
						<div data-style="margin:auto; box-sizing:border-box; ${args->price_style:html:default('color: #333;
text-align: start;
padding: 10px;
font-size: 17px;
font-weight: 700;
margin-top: 01px;
margin-right: 01px;
margin-bottom: 41px;
margin-left: 01px;'):input_type(css):input_props('with_responsive=1'):arg_name(Price style):arg_section(6, 1, 'Price', 'dollar')}">
							${if p->price}
								${args->before_price:arg_name(Text before price):arg_section(6, 2, 'Price', 'dollar')}
								${if p->sale_price and p->sale_price < p->price}
									<span style="${args->sale_style:html:default('text-decoration:line-through'):input_type(css):input_props('with_responsive=1'):arg_name('Price before discount: style'):arg_section(6, 5, 'Price', 'dollar')}">
										${p->price:truncate('2'):sprintf('£%s'):arg_name(Price):arg_section(6, 4, 'Price', 'dollar')}
									</span>
									${args->before_sale_price:default('Nu:'):arg_name(Text before sale price):arg_section(6, 3, 'Price', 'dollar')}
									${p->sale_price:truncate('2'):sprintf('£%s'):arg_name(Price):arg_section(6, 7, 'Price', 'dollar')}
								${end}
								${if not p->sale_price or p->sale_price >= p->price}
									${p->price:truncate('2'):sprintf('£%s')}
								${end}
								${args->after_price:arg_name(Text after price):arg_section(6, 6, 'Price', 'dollar')}
							${end}
						</div>
						${block->description:default(0):arg_name(With description):arg_section(4, 0, 'Text', 'align-justify')}
						<div data-style="margin:auto; box-sizing:border-box">
							<div data-style="display:inline-block; ${args->a_css_3:html:input_type(css):input_props('with_responsive=1'):arg_name(Text color):arg_section(4, 4, 'Text', 'align-justify')}; padding-bottom:0">
								${p->description:arg_name(Item text):arg_section(4, 2, 'Text', 'align-justify')}
							</div>
						</div>
						${block->button:default(0):arg_name(With button):arg_section(7, 0, 'Second line', 'text-height')}
						<a data-emarketer-click-target="products ${p->internal_id:html}" href="${p->cart_url:html}" target="${args->target:html}" data-style="position:relative; top:1.3em; text-decoration:none; transition: font-size 0.3s ease; background-color:${args->border_color:html}; ${args->a_css_4:html:input_type(css):input_props('with_responsive=1'):arg_name(Button style):arg_section(7, 2, 'Second line', 'text-height')}" onmouseenter="var t=this; s=t.style, f=s.fontSize, p=f.match(/^([\d\.]+)(\w+)$/); if (!t._b) t._b=[s.backgroundColor, s.color, f]; s.backgroundColor=t._b[1]; s.color=t._b[0]; if (p) if (!t._p) {s.fontSize=(p[1]*0.9)+p[2]; t._p=1; setTimeout(function() {s.fontSize=t._b[2]; t._p=0;}, 300)}" onmouseleave="var s=this.style, b=this._b; s.backgroundColor=b[0]; s.color=b[1]">
							<div data-style="border:solid 1px; ${args->a_css_5:html:input_type(css):input_props('with_responsive=1'):arg_name(Button style):arg_section(7, 3, 'Second line', 'text-height')}">
								${args->button_text:arg_name(Button text):arg_section(7, 1, 'Second line', 'text-height')}
							</div>
						</a>
						<div style="margin-top:0.4em">
							<a data-emarketer-click-target="products ${p->internal_id:html}" onclick="
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
								_S_T.add_to_cart(${p->internal_id:json:html}, ${action_id:json:html}, this.dataset.arg).then(gf(this.dataset.yes), gf(this.dataset.no))
							" href="javascript:" data-arg="${args->cart_arg:html:arg_name(Argument to pass to your defined Add to Cart function):arg_section(8, 2, 'Add to cart button', 'cart-plus')}" data-yes="${args->cart_yes:html:default('new _S_T.ElemsAnnotator(''info'').add(this, ''Product added!'').annotate(6000);'):input_type(source_javascript):arg_name(Javascript on complete):arg_section(8, 3, 'Add to cart button', 'cart-plus')}" data-no="${args->cart_no:html:default('new _S_T.ElemsAnnotator(''error'').add(this, "Couldn''t add. Please try adding from the product page.").annotate(6000);'):input_type(source_javascript):arg_name(Javascript on error):arg_section(8, 4, 'Add to cart button', 'cart-plus')}" data-style="${args->button_style:html:default('padding: 8px;
border: none;
font-size: 13px;
font-weight: bold;
border-radius: 1px;
color: white;
background-color: rgb(96, 136, 78);
text-align: center;
margin-top: 13px;
margin-right: 0px;
margin-bottom: 0px;
margin-left: 0px;
width: 120px;
text-transform: uppercase;'):input_type(css):input_props('with_responsive=1'):arg_name(Button style):arg_section(8, 1, 'Add to cart button', 'cart-plus')}">
								${args->button:default(Add To cart):arg_name('Text', 'Button text'):arg_section(8, 0, 'Add to cart button', 'cart-plus')}
							</a>
						</div>
					</div>
				</td>
			${end}
		</tr>
	</table>
	${block->pagination:default(0):arg_name(With slider pagination):arg_section(1, 10, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}
	<div id="tsp" class="$table_slider_pagination" slider_id="ts" selected_color="${args->pagination_color_on:html:input_type(color):arg_name(Bullet Selected Color):arg_section(1, 11, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" style="${args->pagination_color:html:input_type(css):arg_name(Bullet style):arg_section(1, 12, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}"></div>
</div>
```


## Multiple products attributes, quick add to cart JS

Multiple products attributes, quick add to cart JS

```
<div class="$responsive" data-style="display:inline-block; position:relative; ${args->style:html:default('border: none;
text-align: left;
min-width: 99%;
width: 99%;
font-family: ''Roboto'',sans-serif;
margin-top: 15px;
margin-right: 1px;
margin-bottom: 15px;
margin-left: 1px;
overflow: hidden;
border: solid 1px rgb(237, 223, 223);'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(0, 1, 'Frame', 'th-large')}" onupdate="
	var
		w=Math.min(ns.joyquery('ancestor::table:limit(1) parent::div parent::div', by_id.ts).get(0).offsetWidth, document.documentElement.clientWidth-1),
		b=12,
		a=ns.joyquery('parent::*>tr>td>*', by_id.ts).get(),
		d=a[0].parentNode,
		t=d.offsetWidth,
		n=Math.max(Math.round((w-b)/(t+b)), Math.min(2, by_id.ts.children.length)),
		T=(w-b)/n-b-parseFloat(d.style.borderLeftWidth)*2;
	for (i=0; i!=a.length; i++) if (a[i].style.display!='inline-block') a[i].style.width=T+'px'
">
	${block->title:default(1):arg_name(With title bar):arg_section(2, 0, 'Title', 'bookmark')}
	<table data-style="width:100%; border-collapse:collapse; border:none; ${args->title_bg:html:default('margin-top: 5px;
margin-right: 0px;
margin-bottom: 5px;
margin-left: 20px;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(2, 2, 'Title', 'bookmark')}">
		<tr>
			<td data-style="vertical-align:middle; ${args->title_style:html:default('text-align: start;
margin-top: 10px;
margin-right: 10px;
margin-bottom: 10px;
margin-left: 1px;
text-overflow: ellipsis;
text-transform: capitalize;
white-space: nowrap;
overflow: hidden;
color: inherit;
line-height: 21px;
font-weight: 500;
font-size: 16px !important;
padding-top: 3px;
padding-right: 0;
padding-bottom: 0;
padding-left: 10px;'):input_type(css):input_props('with_responsive=1'):arg_name(Title style):arg_section(2, 3, 'Title', 'bookmark')}">
				${args->title:default(Your Recent Views):arg_name(Text):arg_section(2, 1, 'Title', 'bookmark')}
			</td>
			${block->with_arrows:default(0):arg_name(With arrow buttons):arg_section(1, 0, 'With slider', 'arrow-right')}
			<td style="width:1px; white-space:nowrap; vertical-align:middle">
				<a id="button_back" class="$flat_btn" style="${args->btn_style:html:input_type(css):arg_name(Arrow button style):arg_section(1, 1, 'With slider', 'arrow-right')}" hover_style="${args->btn_hover_style:html:input_type(css):arg_name('Arrow button style: hover'):arg_section(1, 2, 'With slider', 'arrow-right')}"><</a>
				<a id="button_forward" class="$flat_btn" style="${args->btn_style:html}" hover_style="${args->btn_hover_style:html}">></a>
			</td>
			${block->x:default(0):arg_name(With close button):arg_section(3, 0, 'Close button', 'close')}
			<td style="width:1px; white-space:nowrap; ${args->x_style:html:input_type(css):arg_name(Close button position):arg_section(3, 2, 'Close button', 'close')}">
				${args->x:input_type(dontshowagain):input_props('style=cursor:pointer; vertical-align:middle'):arg_name(Close button):arg_section(3, 1, 'Close button', 'close')}
			</td>
		</tr>
	</table>
	<table data-style="width:100%; border-collapse:separate; border-spacing:12px 8px; margin-bottom:1.2em; height:${args->img_max_height:html:default('sel(228px, 30vw)'):input_type(css_length):input_props('with_responsive=1'):arg_name(Image maximum height):arg_section(0, 5, 'Frame', 'th-large')}">
		<tr id="ts" class="$table_slider" data-disabled="${args->with_slider:html:input_type(checkbox):input_props('value_off=1','value_on='):arg_name(Use slider widget):arg_section(1, 4, 'With slider', 'arrow-right'):onchange('if (args.with_slider==1) block.with_arrows = block.pagination = 0')}" style="height:100%; border:none; max-width:${args->width:html:default(1080px):input_type(css_length):input_props('with_options=none'):arg_name(Widget maximum width):arg_section(0, 0, 'Frame', 'th-large')}" for_max_vw="${args->for_max_vw:html:default(always):input_type(css_length):input_props('with_options=always'):arg_name(Slider widget only if screen width is less than or equal to):arg_section(1, 5, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" eq_cell_width="${args->eq_cell_width:html:default(1):input_type(checkbox):input_props('value_off=','value_on=1'):arg_name(Equal cell width):arg_section(0, 2, 'Frame', 'th-large')}" arrows_line="${args->arrows_line:html:default(0):input_type(checkbox):input_props('value_off=-1','value_on=0'):arg_name(Arrows in the middle of images):arg_section(1, 9, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" arrow_back_img="${args->arrow_back_img:html:default('https://static.emarketer.com/upload/4545/96b6126f483ffd5a.png'):input_type(emarketer_media_url):arg_name(Left arrow image):arg_section(1, 6, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" arrow_style="${args->arrow_style:html:default('box-shadow: 0px 8px 6px 8px rgba(0, 0, 0, 0.23);
background-color: rgba(256, 256, 256, 0.56);'):input_type(css):arg_name(Arrows style):arg_section(1, 7, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" pagination_id="tsp" arrow_back_id="button_back" arrow_forward_id="button_forward" arrows_offset="${args->arrows_offset:html:default(0):input_type(number):arg_name(Slider arrows offset):arg_section(1, 8, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" hide_buttons="${args->hide_buttons:html:input_type(checkbox):input_props('value_off=','value_on=1'):arg_name(Hide arrow buttons when nothing to scroll):arg_section(1, 3, 'With slider', 'arrow-right'):visible_if('block.title-0 && block.with_arrows-0')}">
			${foreach products_interactions as p where p->interaction_status in ('viewed','extra','favorite') order by p->interaction_time desc limit 18}
				<td style="position:relative; height:100%; width:${args->img_width:html:default('sel(220px, 28vw)'):input_type(css_length):input_props('with_responsive=1'):arg_name(Cell width):arg_section(0, 3, 'Frame', 'th-large')}; padding:0; text-align:center; background-color:white; border:solid ${args->border_color:html:default(white):input_type(color):arg_name(Border color):arg_section(0, 4, 'Frame', 'th-large')} 1px; transition: all .3s ease-in-out" onmouseenter="this.style.boxShadow='0 0 20px rgba(0,0,0,.2)'; var i=this.getElementsByTagName('a')[0].getElementsByTagName('img'); if (i[1]) {i[0].style.opacity=0; i[1].style.opacity=1}" onmouseleave="this.style.boxShadow=''; var i=this.getElementsByTagName('a')[0].getElementsByTagName('img'); if (i[1]) {i[0].style.opacity=1; i[1].style.opacity=0}">
					<div data-style="height:100%; width:${args->img_width:html}; display:flex; flex-direction:column">
						<a data-emarketer-click-target="products ${p->internal_id:html}" href="${p->cart_url:html:arg_name(Link target URL):arg_section(5, 0, 'Link target URL', 'link'):column_tags('url','custom text')}" target="${args->target:html:default(_self):input_type(a_target):arg_name(Open link in):arg_section(5, 1, 'Link target URL', 'link')}" data-style="flex-grow:100; display:flex; justify-content:center; align-items:center; margin:auto; box-sizing:border-box">
							<div style="position:relative; display:inline-block">
								<img data-src="${p->image_big_url:html}" alt="" data-style="width:auto; height:auto; max-width:100%; max-height:${args->img_max_height:html}; opacity:1; transition:opacity ease 0.4s">
								${if p->image_medium_url != ''}
									${block->with_2_img:default(1):arg_name(With 2 Pictures):arg_section(0, 6, 'Frame', 'th-large')}
									<div style="position:absolute; left:0; top:0; width:100%; height:100%; display:flex; justify-content:center; align-items:center">
										<img data-src="${p->image_medium_url:html}" style="width:auto; height:auto; max-width:100%; max-height:100%; opacity:0; transition:opacity ease 0.4s">
									</div>
								${end}
							</div>
						</a>
						<div data-style="margin:auto; box-sizing:border-box; width:100%">
							<div data-style="${args->a_css:html:default('font-size: 14px;
color: #000;
font-weight: normal;
margin: 24px 0 2px 0;
font-family: Roboto, sans-serif;
text-align: start;
text-overflow: ellipsis;
text-transform: none;
white-space: nowrap;
overflow: hidden;'):input_type(css):input_props('with_responsive=1'):arg_name(Text color):arg_section(4, 4, 'Text', 'align-justify')}">
								${p->title:arg_name(Item text):arg_section(4, 1, 'Text', 'align-justify')}
							</div>
						</div>
						<div data-style="margin:auto; box-sizing:border-box; width:100%">
							<div data-style="${args->a_css2:html:default('font-size: 14px;
color: #000;
font-weight: normal;
margin: 0 0 10px 0;
font-family: Roboto, sans-serif;
text-align: start;
text-overflow: ellipsis;
text-transform: none;
white-space: nowrap;
overflow: hidden;'):input_type(css):input_props('with_responsive=1'):arg_name(Text 2 color):arg_section(4, 5, 'Text', 'align-justify')}">
								${p->description_short:sprintf('%s '):arg_name(Item text):arg_section(4, 2, 'Text', 'align-justify')}
							</div>
						</div>
						${block->price:default(1):arg_name(With price):arg_section(6, 0, 'Price', 'dollar')}
						<div>
							${if p->price_before_discount}
								${if p->price_after_discount and p->price_after_discount < p->price_before_discount}
									<div style="${args->before_sale_price_style:html:default('text-align:left; font-size: 12px;
color: #000;
font-weight: 600;
font-family: Arial,Helvetica,sans-serif'):input_type(css):input_props('with_responsive=1'):arg_name(Price style):arg_section(6, 1, 'Price', 'dollar')}">
										${args->before_sale_price:default('MSRP Pricing:'):arg_name(Text before price):arg_section(6, 3, 'Price', 'dollar')}
										<span style="${args->sale_style:html:default('font-weight: normal;'):input_type(css):input_props('with_responsive=1'):arg_name('Price before discount: style'):arg_section(6, 6, 'Price', 'dollar')}">
											${p->price_after_discount:truncate('2'):sprintf('$%[,###,##0.##]f'):arg_name(Price):arg_section(6, 8, 'Price', 'dollar')}
										</span>
									</div>
								${end}
								<div style="${args->before_price_style:html:default('text-align:left; font-size: 12px;
color: #000;
font-weight: 600;
font-family: Arial,Helvetica,sans-serif'):input_type(css):input_props('with_responsive=1'):arg_name(Price style):arg_section(6, 2, 'Price', 'dollar')}">
									${args->before_price:arg_name(Text before price):arg_section(6, 4, 'Price', 'dollar')}
									<span style="${args->price_style2:html:input_type(css):input_props('with_responsive=1'):arg_name('Price before discount: style'):arg_section(6, 7, 'Price', 'dollar')}">
										${p->price_before_discount:truncate('2'):sprintf('$%[,###,##0.##]f'):arg_name(Price):arg_section(6, 5, 'Price', 'dollar')}
									</span>
								</div>
							${end}
						</div>
						${block->description:default(0):arg_name(With description):arg_section(4, 0, 'Text', 'align-justify')}
						<div data-style="margin:auto; box-sizing:border-box">
							<div data-style="display:inline-block; ${args->a_css_3:html:input_type(css):input_props('with_responsive=1'):arg_name(Text color):arg_section(4, 6, 'Text', 'align-justify')}; padding-bottom:0">
								${p->description:arg_name(Item text):arg_section(4, 3, 'Text', 'align-justify')}
							</div>
						</div>
						${block->button:default(0):arg_name(With button):arg_section(7, 0, 'Second line', 'text-height')}
						<a data-emarketer-click-target="products ${p->internal_id:html}" href="${p->cart_url:html}" target="${args->target:html}" data-style="position:relative; top:1.3em; text-decoration:none; transition: font-size 0.3s ease; background-color:${args->border_color:html}; ${args->a_css_4:html:input_type(css):input_props('with_responsive=1'):arg_name(Button style):arg_section(7, 2, 'Second line', 'text-height')}" onmouseenter="var t=this; s=t.style, f=s.fontSize, p=f.match(/^([\d\.]+)(\w+)$/); if (!t._b) t._b=[s.backgroundColor, s.color, f]; s.backgroundColor=t._b[1]; s.color=t._b[0]; if (p) if (!t._p) {s.fontSize=(p[1]*0.9)+p[2]; t._p=1; setTimeout(function() {s.fontSize=t._b[2]; t._p=0;}, 300)}" onmouseleave="var s=this.style, b=this._b; s.backgroundColor=b[0]; s.color=b[1]">
							<div data-style="border:solid 1px; ${args->a_css_5:html:input_type(css):input_props('with_responsive=1'):arg_name(Button style):arg_section(7, 3, 'Second line', 'text-height')}">
								${args->button_text:arg_name(Button text):arg_section(7, 1, 'Second line', 'text-height')}
							</div>
						</a>
						${block->with_cart:default(1):arg_name(With add to cart):arg_section(8, 0, 'Add to cart button', 'cart-plus')}
						<div>
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
							" href="javascript:" data-arg="${args->cart_arg:html:arg_name(Argument to pass to your defined Add to Cart function):arg_section(8, 4, 'Add to cart button', 'cart-plus')}" data-yes="${args->cart_yes:html:input_type(source_javascript):arg_name(Javascript on complete):arg_section(8, 5, 'Add to cart button', 'cart-plus')}" data-no="${args->cart_no:html:input_type(source_javascript):arg_name(Javascript on error):arg_section(8, 6, 'Add to cart button', 'cart-plus')}" data-style="box-sizing:border-box; ${args->button_style:html:input_type(css):input_props('with_responsive=1'):arg_name(Button style):arg_section(8, 2, 'Add to cart button', 'cart-plus')}" hover_style="${args->button_style_hover:html:input_type(css):arg_name(Button hover style):arg_section(8, 3, 'Add to cart button', 'cart-plus')}">
								${args->button:arg_name('Text', 'Button text'):arg_section(8, 1, 'Add to cart button', 'cart-plus')}
							</a>
						</div>
						${block->with_wishlist:default(0):arg_name(With wishlist):arg_section(9, 0, 'Wishlist', 'heart')}
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
						" href="javascript:" data-arg="${args->wishlist_arg:html:arg_name(Argument to pass to your defined Add to Wishlist function):arg_section(9, 3, 'Wishlist', 'heart')}" data-yes="${args->wishlist_yes:html:input_type(source_javascript):arg_name(Javascript on complete):arg_section(9, 4, 'Wishlist', 'heart')}" data-no="${args->wishlist_no:html:input_type(source_javascript):arg_name(Javascript on error):arg_section(9, 5, 'Wishlist', 'heart')}" style="position:absolute; ${args->div_wishlist:html:input_type(css):input_props('with_responsive=1'):arg_name(Wishlist style):arg_section(9, 1, 'Wishlist', 'heart')}" hover_style="background-color: transparent">
							<img src="${args->wishlist_src:html:input_type(emarketer_media_url):arg_name(Add to wishlist image):arg_section(9, 2, 'Wishlist', 'heart')}">
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


## Click to view on mouse hover



```
<div class="$responsive" data-style="display:inline-block; position:relative; ${args->style:html:default('padding-right: 0px;
padding-left: 0px;
border: none;
text-align: left;
font-weight: bold;
font-size: 17px;
box-sizing: border-box;
width: sel(auto, auto);
font-family: Roboto,sans-serif;
box-shadow: 0 0px 0px 0 rgba(0,0,0,0.08);
background-color: rgba(0, 0, 0, 0);
margin-top: 40px;
margin-right: 0px;
margin-bottom: 1px;
margin-left: 0px;
min-width: 98%;
width: 98%;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(0, 1, 'Frame', 'th-large')}" onupdate="
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
	${block->title:default(1):arg_name(With title bar):arg_section(2, 0, 'Title', 'bookmark')}
	<table data-style="width:98%; margin-right: 1%; margin-left: 1%; border-collapse:collapse; border:none; ${args->title_bg:html:default('background-color: rgba(0, 0, 0, 0);
margin-top: 0px;
margin-right: 0;
margin-bottom: 25px;
padding-top: 0px;
padding-right: 0;
padding-bottom: 0px;
padding-left: 0;
border-bottom: none;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(2, 2, 'Title', 'bookmark')}">
		<tr>
			<td data-style="vertical-align:middle; ${args->title_style:html:default('text-align: left;
font-family: "Source Sans Pro",sans-serif;
font-weight: 700;
padding-top: 10px;
padding-right: 0px;
padding-bottom: 5px;
padding-left: 15px;
font-size: 32px;
line-height: 20px;
text-transform: uppercase;
color: #333;'):input_type(css):input_props('with_responsive=1'):arg_name(Title style):arg_section(2, 3, 'Title', 'bookmark')}">
				${args->title:default(Your title):arg_name(Text):arg_section(2, 1, 'Title', 'bookmark')}
			</td>
			${block->with_arrows:default(0):arg_name(With arrow buttons):arg_section(1, 0, 'With slider', 'arrow-right')}
			<td style="width:1px; white-space:nowrap; vertical-align:middle">
				<a id="button_back" class="$flat_btn" style="${args->btn_style:html:input_type(css):arg_name(Arrow button style):arg_section(1, 1, 'With slider', 'arrow-right')}" hover_style="${args->btn_hover_style:html:input_type(css):arg_name('Arrow button style: hover'):arg_section(1, 2, 'With slider', 'arrow-right')}"><</a>
				<a id="button_forward" class="$flat_btn" style="${args->btn_style:html}" hover_style="${args->btn_hover_style:html}">></a>
			</td>
			${block->x:default(0):arg_name(With close button):arg_section(3, 0, 'Close button', 'close')}
			<td style="width:1px; white-space:nowrap; ${args->x_style:html:input_type(css):arg_name(Close button position):arg_section(3, 2, 'Close button', 'close')}">
				${args->x:input_type(dontshowagain):input_props('style=cursor:pointer; vertical-align:middle'):arg_name(Close button):arg_section(3, 1, 'Close button', 'close')}
			</td>
		</tr>
	</table>
	<table style="width:100%; border-collapse:separate; border-spacing:12px 0">
		<tr id="ts" class="$table_slider" data-disabled="${args->with_slider:html:input_type(checkbox):input_props('value_off=1','value_on='):arg_name(Use slider widget):arg_section(1, 4, 'With slider', 'arrow-right'):onchange('if (args.with_slider==1) block.with_arrows = block.pagination = 0')}" style="width: 100%; padding: 0 1%; box-sizing: border-box; border:none; max-width:${args->width:html:default(none):input_type(css_length):input_props('with_options=none'):arg_name(Widget maximum width):arg_section(0, 0, 'Frame', 'th-large')}" for_max_vw="${args->for_max_vw:html:input_type(css_length):input_props('with_options=always'):arg_name(Slider widget only if screen width is less than or equal to):arg_section(1, 5, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" eq_cell_width="${args->eq_cell_width:html:default(1):input_type(checkbox):input_props('value_off=','value_on=1'):arg_name(Equal cell width):arg_section(0, 2, 'Frame', 'th-large')}" arrows_line="${args->arrows_line:html:default(-1):input_type(checkbox):input_props('value_off=-1','value_on=0'):arg_name(Arrows in the middle of images):arg_section(1, 9, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" arrow_back_img="${args->arrow_back_img:html:default('https://cdn.e-marketer.io/upload/4975/fb528ff235cc14c7.png'):input_type(emarketer_media_url):arg_name(Left arrow image):arg_section(1, 6, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" arrow_style="${args->arrow_style:html:default('background-color: rgba(256, 256, 256, 0.63);
box-shadow: 0px 1px 6px -1px rgba(0, 0, 0, .3);
height: 24px;
padding: 4px;'):input_type(css):arg_name(Arrows style):arg_section(1, 7, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" pagination_id="tsp" arrow_back_id="button_back" arrow_forward_id="button_forward" arrows_offset="${args->arrows_offset:html:input_type(number):arg_name(Slider arrows offset):arg_section(1, 8, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" hide_buttons="${args->hide_buttons:html:input_type(checkbox):input_props('value_off=','value_on=1'):arg_name(Hide arrow buttons when nothing to scroll):arg_section(1, 3, 'With slider', 'arrow-right'):visible_if('block.title-0 && block.with_arrows-0')}">
			${foreach sum_last_viewed_categories_products as p order by p->n_viewed desc limit 12}
				<td style="position:relative; padding:0; text-align:center; background-color:white; vertical-align:top; border:solid ${args->border_color:html:default('rgba(178, 32, 32, 0)'):input_type(color):arg_name(Border color):arg_section(0, 4, 'Frame', 'th-large')} 1px">
					<a data-emarketer-click-target="products ${p->internal_id:html}" href="${p->cart_url:html:arg_name(Link target URL):arg_section(6, 0, 'Link target URL', 'link'):column_tags('url','custom text')}" target="${args->target:html:default(_self):input_type(a_target):arg_name(Open link in):arg_section(6, 1, 'Link target URL', 'link')}" data-style="display:block; margin:auto; box-sizing:border-box; width:${args->img_width:html:default('sel(180px, 52vw)'):input_type(css_length):input_props('with_responsive=1'):arg_name(Cell width):arg_section(0, 3, 'Frame', 'th-large')}">
						<img src="${p->image_big_url:html:arg_name(Item image):arg_section(4, 0, 'Image', 'image'):column_tags(image)}" data-style="width:auto; height:auto; max-width:100%; max-height:${args->img_max_height:html:default('sel(146px, 30vw)'):input_type(css_length):input_props('with_responsive=1'):arg_name(Image maximum height):arg_section(0, 5, 'Frame', 'th-large')}">
					</a>
					<div data-style="margin:auto; box-sizing:border-box; width:${args->img_width:html}">
						<div data-style="${args->a_css:html:default('padding: 1px;
text-transform: none;
color: #333;
font-family: "Source Sans Pro",sans-serif;
font-weight: 300;
font-size: 14px;
margin: 10px;
text-overflow: clip;
max-height: 90px;
overflow: hidden;
text-align: left;
height: 70px;'):input_type(css):input_props('with_responsive=1'):arg_name(Text color):arg_section(5, 3, 'Text', 'align-justify')}">
							${p->title:arg_name(Item text):arg_section(5, 1, 'Text', 'align-justify')}
						</div>
					</div>
					${block->rating:default(0):arg_name(With rating):arg_section(7, 0, 'Rating', 'star')}
					<div style="margin: auto; margin-bottom: .6em; line-height: 12px">
						<div style="width: 69px; height: 13px; font-size: 0; line-height: 0; background: url(https://skin.christys-hats.com/frontend/ultimo/totalRecall/images/img/rating.png) 0 0 repeat-x; text-indent: -999em; overflow: hidden; margin-left: 0; margin-right: 0; display: inline-block; vertical-align: middle;">
							<div style="float: left; height: 13px; background: url(https://skin.christys-hats.com/frontend/ultimo/totalRecall/images/img/rating.png) 0 100% repeat-x; width: ${p->rank:html:default(0):arg_name(Rating):arg_section(7, 1, 'Rating', 'star')}%">
							</div>
						</div>
					</div>
					<div style="clear:left;"></div>
					${block->price:default(1):arg_name(With price):arg_section(8, 0, 'Price', 'dollar')}
					<div data-style="margin:auto; box-sizing:border-box; width:${args->img_width:html}; ${args->price_style:html:default('font-size: 14px;
color: #333;
line-height: 20px;
font-weight: 700;'):input_type(css):input_props('with_responsive=1'):arg_name(Price style):arg_section(8, 5, 'Price', 'dollar')}">
						${if p->price}
							${args->before_price:arg_name(Text before price):arg_section(8, 1, 'Price', 'dollar')}
							${if p->sale_price and p->sale_price < p->price}
								${p->sale_price:truncate(2):sprintf($%s):arg_name(Price):arg_section(8, 6, 'Price', 'dollar')}
								<div style="${args->sale_style:html:input_type(css):input_props('with_responsive=1'):arg_name('Price before discount: style'):arg_section(8, 3, 'Price', 'dollar')}">
									${p->price:truncate(2):sprintf($%s):arg_name(Price):arg_section(8, 2, 'Price', 'dollar')}
								</div>
							${end}
							${if not p->sale_price or p->sale_price >= p->price}
								${p->price:truncate(2):sprintf($%s)}
							${end}
							${args->after_price:arg_name(Text after price):arg_section(8, 4, 'Price', 'dollar')}
						${end}
					</div>
					<div style="margin:auto; box-sizing:border-box; font-size:1px">
						<div data-style="display:inline-block; background-color:${args->border_color:html}; ${args->a_css_2:html:default('width:100px; height:3px; max-width:80%'):input_type(css):input_props('with_responsive=1'):arg_name(Ruler):arg_section(5, 5, 'Text', 'align-justify')}"></div>
					</div>
					${block->description:default(0):arg_name(With description):arg_section(5, 0, 'Text', 'align-justify')}
					<div data-style="margin:auto; box-sizing:border-box; width:${args->img_width:html}">
						<div data-style="display:inline-block; ${args->a_css_3:html:input_type(css):input_props('with_responsive=1'):arg_name(Text color):arg_section(5, 4, 'Text', 'align-justify')}; padding-bottom:0">
							${p->description:arg_name(Item text):arg_section(5, 2, 'Text', 'align-justify')}
						</div>
					</div>
					${block->button:default(1):arg_name(With button):arg_section(9, 0, 'Button', 'hand-pointer-o')}
					<div data-style="${args->button_spacer:html:default('height: 1.6em;'):input_type(css):input_props('with_responsive=1'):arg_name(Button reserved space):arg_section(9, 5, 'Button', 'hand-pointer-o')}">
						<a data-emarketer-click-target="products ${p->internal_id:html}" href="${p->cart_url:html}" target="${args->target:html}" data-style="display:block; box-sizing:border-box; position:absolute; width:100%; height:0; display:none; left:0; bottom:0; ${args->a_css_4:html:default('margin-top: 1.3em;
background-color: #FAC200;
color: #333;
text-decoration: none;
padding-top: 0.3em;
padding-right: 0.5em;
padding-bottom: 0.3em;
padding-left: 0.5em;
font-weight: 300;'):input_type(css):input_props('with_responsive=1'):arg_name(Button style):arg_section(9, 3, 'Button', 'hand-pointer-o')}" ontplready="
							var a=ns.new_elem(this), p=this.parentNode.parentNode;
							p.onmouseenter = p.onmouseleave = function(e)
							{	var on = e.type == 'mouseenter';
								a.add_style({height: on ? 'auto' : '0', display: on ? '' : 'none'}, {});
							};
						">
							<div style="display:inline-block; width:1em; height:1em; line-height:1; border-radius:50%; ${args->plus_style:html:default('color: #FAC200;
background-color: #333;'):input_type(css):input_props('with_responsive=1'):arg_name(Button style):arg_section(9, 4, 'Button', 'hand-pointer-o')}">${args->button_add_plus:default(+):arg_name(Icon text):arg_section(9, 2, 'Button', 'hand-pointer-o')}</div>
							${args->button_add_text:default(Details):arg_name(Button text):arg_section(9, 1, 'Button', 'hand-pointer-o')}
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


## Category view



```
<div class="$responsive" data-style="box-sizing:border-box; background-color:${args->bg:html:default('rgba(0, 0, 0, 0)'):input_type(color):arg_name(Background color):arg_section(0, 0, 'Frame', 'th-large')}; ${args->style:html:default('max-width: 9990px;
border: none;
line-height: 1.42857143;
color: black;
font-family: Roboto,Arial,sans-serif;
font-weight: 500;
margin-top: 20px;
margin-right: 0px;
margin-bottom: 0px;
margin-left: 0px;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(0, 1, 'Frame', 'th-large')}">
	${block->title:default(1):arg_name(With title bar):arg_section(1, 0, 'Title', 'bookmark')}
	<div data-style="${args->title_style:html:default('padding: 16px;
font-family: "Roboto Condensed","Arial Narrow",Arial,sans-serif;
font-size: 20px;
font-weight: 700;
text-align: left;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(1, 2, 'Title', 'bookmark')}">
		${block->x:default(0):arg_name(With close button):arg_section(2, 0, 'Close button', 'close')}
		<div style="float:right; cursor:pointer; margin:0 0 .3em .3em">
			${args->x:input_type(dontshowagain):arg_name(Close button):arg_section(2, 1, 'Close button', 'close')}
		</div>
		${args->title:default(Recommended For You):arg_name(Text):arg_section(1, 1, 'Title', 'bookmark')}
		<div style="clear:both"></div>
	</div>
	<div style="display:flex; flex-flow:row; flex-wrap:wrap">
		${foreach sum_products as p where p->for_period='recently' order by p->n_viewed desc limit 12}
			<div style="box-sizing:border-box; width:${args->cell_width:html:default(350px):input_type(css_length):input_props('with_responsive=1'):arg_name(Cell width):arg_section(0, 2, 'Frame', 'th-large')}">
				<div data-style="display:flex; align-items:center; ${args->a_style:html:default('font-size:16px; margin:5px'):input_type(css):input_props('with_responsive=1'):arg_name(Cell style):arg_section(3, 2, 'Cell', 'bars')}" onmouseenter="this._s=this.style.cssText; this.style.cssText+=';'+this.dataset.hoverStyle; var i=this.getElementsByTagName('img'); if (i[1]) {i[0].style.opacity=0; i[1].style.opacity=1}" onmouseleave="if (this._s) this.style.cssText=this._s; var i=this.getElementsByTagName('a')[0].getElementsByTagName('img'); if (i[1]) {i[0].style.opacity=1; i[1].style.opacity=0}" data-hover-style="${args->a_hover_style:html:default('box-shadow: 0 0 10px #888;'):input_type(css):arg_name(Style):arg_section(3, 3, 'Cell', 'bars')}">
					<a data-emarketer-click-target="products ${p->internal_id:html}" href="${p->cart_url:html}" data-style="color:inherit; text-decoration:none; text-align:center; padding:${args->a_padding:html:default(16px):input_type(css_length):input_props('with_responsive=1'):arg_name(Padding):arg_section(3, 5, 'Cell', 'bars')}">
						${block->with_img:default(1):arg_name(With Picture):arg_section(6, 0, 'Picture', 'image')}
						<div style="position:relative; display:inline-block">
							<img src="${p->image_big_url:html:arg_name(Data source):arg_section(6, 1, 'Picture', 'image')}" data-style="width:auto; height:auto; ${args->img_style:html:default('max-width:100%; max-height:sel(300px, 150px); border-radius:4px'):input_type(css):input_props('with_responsive=1'):arg_name(Picture style):arg_section(6, 2, 'Picture', 'image')}; opacity:1; transition:opacity ease 0.4s">
							${if p->image_medium_url != ''}
								${block->with_2_img:default(1):arg_name(With 2 Pictures):arg_section(6, 3, 'Picture', 'image')}
								<div style="position:absolute; left:0; top:0; width:100%; height:100%; display:flex; justify-content:center; align-items:center">
									<img src="${p->image_big_url:html}" style="width:auto; height:auto; max-width:100%; max-height:100%; opacity:0; border-radius:4px; transition:opacity ease 0.4s">
								</div>
							${end}
						</div>

						<div data-style="${args->title_style2:html:input_type(css):input_props('with_responsive=1'):arg_name(Title style):arg_section(3, 1, 'Cell', 'bars')}">
							${p->title:arg_name(Item text):arg_section(3, 0, 'Cell', 'bars')}
						</div>

						${if p->price_after_discount or p->price_before_discount}
							${args->before_price:arg_name(Text before price):arg_section(3, 7, 'Cell', 'bars')}
							${if p->price_after_discount = p->price_before_discount}
								${p->price_after_discount:truncate(2):sprintf('$%s'):arg_name(Price after discount):arg_section(3, 9, 'Cell', 'bars')}
							${end}
							${if p->price_after_discount != p->price_before_discount}
								${p->price_after_discount:truncate(2):sprintf('$%s')}
								<span style="${args->sale_style:html:default('color:gray; text-decoration:line-through; font-size:85%'):input_type(css):arg_name('Price before discount: style'):arg_section(3, 11, 'Cell', 'bars')}">
									${p->price_before_discount:truncate(2):sprintf($%s):arg_name(Price before discount):arg_section(3, 10, 'Cell', 'bars')}
								</span>
							${end}
							${args->after_price:arg_name(Text after price):arg_section(3, 8, 'Cell', 'bars')}
						${end}

						${block->with_info1:default(0):arg_name(With Product info 1):arg_section(4, 0, 'Product info near price', 'info')}
						<span data-style="${args->info1_style:html:input_type(css):input_props('with_responsive=1'):arg_name(Product info 1 style):arg_section(4, 2, 'Product info near price', 'info')}">
							${p->custom_3:sprintf('%s'):arg_name(Product info 1):arg_section(4, 1, 'Product info near price', 'info')}
						</span>
						${block->with_info2:default(0):arg_name(With Product info 2):arg_section(4, 3, 'Product info near price', 'info')}
						<span data-style="${args->info2_style:html:input_type(css):input_props('with_responsive=1'):arg_name(Product info 2 style):arg_section(4, 5, 'Product info near price', 'info')}">
							${p->custom_2:sprintf('| %s miles'):arg_name(Product info 2):arg_section(4, 4, 'Product info near price', 'info')}
						</span>

						${block->rating:default(0):arg_name(With rating):arg_section(5, 0, 'Rating', 'star-half-empty')}
						<div data-style="${args->rating_style:html:input_type(css):input_props('with_responsive=1'):arg_name(Rating style):arg_section(5, 4, 'Rating', 'star-half-empty')}">
							<input class="$rating" value="${p->custom_1:html:default(0):arg_name(Rating):arg_section(5, 1, 'Rating', 'star-half-empty')}" max="${args->rank_max:html:default(5):input_type(number):arg_name(Maximum rating number that corresponds to 100%):arg_section(5, 3, 'Rating', 'star-half-empty')}" style="background-color:${args->bg:html}">
						</div>
						${block->rating_text:default(0):arg_name(With rating text):arg_section(5, 5, 'Rating', 'star-half-empty')}
						<div data-style="${args->rating_text_style:html:input_type(css):input_props('with_responsive=1'):arg_name(Rating text style):arg_section(5, 6, 'Rating', 'star-half-empty')}">
							${p->custom_1:html:default(0)}
							${args->of:arg_name(Of):arg_section(5, 2, 'Rating', 'star-half-empty')}
							${args->rank_max:html}

							${block->rating_votes:arg_name(With no. of votes):arg_section(5, 7, 'Rating', 'star-half-empty')}
							<span>
								${args->votes_before:arg_name('No. of votes: text before'):arg_section(5, 8, 'Rating', 'star-half-empty')}${p->custom_i_1:html:default(0):arg_name(No. of votes):arg_section(5, 9, 'Rating', 'star-half-empty')}${args->votes_after:arg_name('No. of votes: text after'):arg_section(5, 10, 'Rating', 'star-half-empty')}
							</span>
						</div>
					</a>
					${block->with_arrow:default(0):arg_name(With arrow):arg_section(3, 4, 'Cell', 'bars')}
					<div style="padding:${args->a_padding:html}; padding-left:0; padding-top:0; padding-bottom:0; text-align:right; ${args->arrow_style:html:input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(3, 6, 'Cell', 'bars')}">
						>
					</div>
				</div>
			</div>
		${end}
	</div>
</div>
```


## Product Recommendations

Product Reccomendation TIN

```
<div class="$responsive" data-style="display:inline-block; position:relative; ${args->style:html:default('padding-webkit-font-smoothing: antialiased;
line-height: 1.4;
color: #323f48;
font-family: "Open Sans", "Open Sans", sans-serif;
-webkit-tap-highlight-color: transparent;
user-select: none;
text-align: center;
box-sizing: inherit;
font-size: 16px;
font-weight: 700;
vertical-align: middle;
'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(0, 1, 'Frame', 'th-large')}" onupdate="
	var
		w=Math.min(ns.joyquery('ancestor::table:limit(1) parent::div parent::div', by_id.ts).get(0).offsetWidth, document.documentElement.clientWidth-1),
		b=12,
		a=ns.joyquery('parent::*>tr>td>*', by_id.ts).get(),
		d=a[0].parentNode,
		t=d.offsetWidth,
		n=Math.max(Math.round((w-b)/(t+b)), Math.min(2, by_id.ts.children.length)),
		T=(w-b)/n-b-parseFloat(d.style.borderLeftWidth)*2;
	for (i=0; i!=a.length; i++) if (a[i].style.display!='inline-block') a[i].style.width=T+'px'
">
	${block->title:default(1):arg_name(With title bar):arg_section(2, 0, 'Title', 'bookmark')}
	<table data-style="width:100%; border-collapse:collapse; border:none; ${args->title_bg:html:default('background-color: rgba(170, 76, 76, 0);
margin-top: 43px;
margin-right: 0px;
margin-bottom: 7px;
margin-left: 7px;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(2, 2, 'Title', 'bookmark')}">
		<tr>
			<td data-style="vertical-align:middle; ${args->title_style:html:default('-webkit-tap-highlight-color: transparent;
-webkit-font-smoothing: antialiased;
box-sizing: inherit;
margin-top: 0;
font-family: inherit;
color: #2d2d2d;
line-height: inherit;
border-bottom: 2px solid #FFD632;
font-size: 22px;
font-weight: 300;
position: relative;
overflow: hidden;
padding-bottom: 2px;
margin-bottom: 0;'):input_type(css):input_props('with_responsive=1'):arg_name(Title style):arg_section(2, 3, 'Title', 'bookmark')}">
				${args->title:default('<div>&Delta;&Epsilon;&Sigma; &Epsilon;&Pi;&Iota;&Sigma;&Eta;&Sigma;:</div>
'):arg_name(Text):arg_section(2, 1, 'Title', 'bookmark')}
			</td>
			${block->with_arrows:default(0):arg_name(With arrow buttons):arg_section(1, 0, 'With slider', 'arrow-right')}
			<td style="width:1px; white-space:nowrap; vertical-align:middle">
				<a id="button_back" class="$flat_btn" style="${args->btn_style:html:input_type(css):arg_name(Arrow button style):arg_section(1, 1, 'With slider', 'arrow-right')}" hover_style="${args->btn_hover_style:html:input_type(css):arg_name('Arrow button style: hover'):arg_section(1, 2, 'With slider', 'arrow-right')}"><</a>
				<a id="button_forward" class="$flat_btn" style="${args->btn_style:html}" hover_style="${args->btn_hover_style:html}">></a>
			</td>
			${block->x:default(0):arg_name(With close button):arg_section(3, 0, 'Close button', 'close')}
			<td style="width:1px; white-space:nowrap; ${args->x_style:html:input_type(css):arg_name(Close button position):arg_section(3, 2, 'Close button', 'close')}">
				${args->x:input_type(dontshowagain):input_props('style=cursor:pointer; vertical-align:middle'):arg_name(Close button):arg_section(3, 1, 'Close button', 'close')}
			</td>
		</tr>
	</table>
	<table style="width:100%; border-collapse:separate; border-spacing:12px 0; margin-bottom:1.2em">
		<tr id="ts" class="$table_slider" data-disabled="${args->with_slider:html:input_type(checkbox):input_props('value_off=1','value_on='):arg_name(Use slider widget):arg_section(1, 4, 'With slider', 'arrow-right'):onchange('if (args.with_slider==1) block.with_arrows = block.pagination = 0')}" style="border:none; max-width:${args->width:html:default(80vw):input_type(css_length):input_props('with_options=none'):arg_name(Widget maximum width):arg_section(0, 0, 'Frame', 'th-large')}" for_max_vw="${args->for_max_vw:html:default(always):input_type(css_length):input_props('with_options=always'):arg_name(Slider widget only if screen width is less than or equal to):arg_section(1, 5, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" eq_cell_width="${args->eq_cell_width:html:default(1):input_type(checkbox):input_props('value_off=','value_on=1'):arg_name(Equal cell width):arg_section(0, 2, 'Frame', 'th-large')}" eq_cell_height="1" arrows_line="${args->arrows_line:html:default(0):input_type(checkbox):input_props('value_off=-1','value_on=0'):arg_name(Arrows in the middle of images):arg_section(1, 9, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" arrow_back_img="${args->arrow_back_img:html:default('https://static.emarketer.com/upload/4035/3256192fabeef23a.png'):input_type(emarketer_media_url):arg_name(Left arrow image):arg_section(1, 6, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" arrow_forward_img="${args->arrow_forward_img:html:default('https://static.emarketer.com/upload/4035/6447f3eea66d7795.png'):input_type(emarketer_media_url):arg_name(Right arrow image):arg_section(1, 7, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" pagination_id="tsp" arrow_back_id="button_back" arrow_forward_id="button_forward" arrows_offset="${args->arrows_offset:html:default(-15):input_type(number):arg_name(Slider arrows offset):arg_section(1, 8, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" hide_buttons="${args->hide_buttons:html:input_type(checkbox):input_props('value_off=','value_on=1'):arg_name(Hide arrow buttons when nothing to scroll):arg_section(1, 3, 'With slider', 'arrow-right'):visible_if('block.title-0 && block.with_arrows-0')}">
			${foreach sum_products as p where p->for_period='recently' order by p->n_viewed desc limit 5}
				<td style="padding:0; text-align:center; background-color:white; border:solid ${args->border_color:html:default(white):input_type(color):arg_name(Border color):arg_section(0, 4, 'Frame', 'th-large')} 1px">
					<a data-emarketer-click-target="products ${p->internal_id:html}" href="${p->cart_url:html:arg_name(Link target URL):arg_section(6, 0, 'Link target URL', 'link'):column_tags('url','custom text')}" target="${args->target:html:default(_self):input_type(a_target):arg_name(Open link in):arg_section(6, 1, 'Link target URL', 'link')}" data-style="display:block; margin:auto; box-sizing:border-box; width:${args->img_width:html:default('sel(200px, 25vw)'):input_type(css_length):input_props('with_responsive=1'):arg_name(Cell width):arg_section(0, 3, 'Frame', 'th-large')}">
						<div data-style="background-image:url('${p->image_big_url:html:arg_name(Item image):arg_section(4, 0, 'Image', 'image'):column_tags(image)}'); background-repeat:no-repeat; background-position:center; background-size:100% 100%; transition: background-size 0.7s ease; width:100%" data-z='${args->zoom:html:default(105):input_type(number):arg_name('Image zoom on hover, %'):arg_section(4, 1, 'Image', 'image')}' onmouseover="var z=this.getAttribute('data-z'); this.style.backgroundSize=z+'% '+z+'%'" onmouseout="this.style.backgroundSize='100% 100%'">
							<img src="${p->image_big_url:html}" data-style="visibility:hidden; width:auto; height:auto; max-width:100%; max-height:${args->img_max_height:html:default('sel(300px, 30vw)'):input_type(css_length):input_props('with_responsive=1'):arg_name(Image maximum height):arg_section(0, 5, 'Frame', 'th-large')}">
						</div>
					</a>
					<div data-style="margin:auto; box-sizing:border-box; width:${args->img_width:html}">
						<div data-style="display:inline-block; ${args->a_css:html:default('-webkit-font-smoothing: antialiased;
-webkit-tap-highlight-color: transparent;
user-select: none;
text-align: center;
box-sizing: inherit;
margin: 0.67em 0;
margin-top: 0;
font-family: inherit;
color: #2d2d2d;
font-size: 14px;
line-height: 1.4;
margin-bottom: 16px;
text-transform: none;
font-weight: 400;'):input_type(css):input_props('with_responsive=1'):arg_name(Text color):arg_section(5, 3, 'Text', 'align-justify')}">
							${p->title:arg_name(Item text):arg_section(5, 1, 'Text', 'align-justify')}
						</div>
					</div>
					${block->price:default(1):arg_name(With price):arg_section(7, 0, 'Price', 'dollar')}
					<div data-style="margin:auto; box-sizing:border-box; width:${args->img_width:html}">
						${if p->price}
							${args->before_price:arg_name(Text before price):arg_section(7, 1, 'Price', 'dollar')}
							${if p->sale_price and p->sale_price < p->price}
								${p->sale_price:truncate(2):sprintf($%s):arg_name(Price):arg_section(7, 2, 'Price', 'dollar')}
								<div style="${args->sale_style:html:input_type(css):input_props('with_responsive=1'):arg_name('Price before discount: style'):arg_section(7, 5, 'Price', 'dollar')}">
									${p->price:truncate(2):sprintf($%s):arg_name(Price):arg_section(7, 4, 'Price', 'dollar')}
								</div>
							${end}
							${if not p->sale_price or p->sale_price >= p->price}
								${p->price:truncate(2):sprintf($%s)}
							${end}
							${args->after_price:arg_name(Text after price):arg_section(7, 3, 'Price', 'dollar')}
						${end}
					</div>
					<div style="margin:auto; box-sizing:border-box; font-size:1px">
						<div data-style="display:inline-block; background-color:${args->border_color:html}; ${args->a_css_2:html:default('width:100px; height:3px; max-width:80%'):input_type(css):input_props('with_responsive=1'):arg_name(Ruler):arg_section(5, 5, 'Text', 'align-justify')}"></div>
					</div>
					${block->description:default(0):arg_name(With description):arg_section(5, 0, 'Text', 'align-justify')}
					<div data-style="margin:auto; box-sizing:border-box; width:${args->img_width:html}">
						<div data-style="display:inline-block; ${args->a_css_3:html:input_type(css):input_props('with_responsive=1'):arg_name(Text color):arg_section(5, 4, 'Text', 'align-justify')}; padding-bottom:0">
							${p->description:arg_name(Item text):arg_section(5, 2, 'Text', 'align-justify')}
						</div>
					</div>
					${block->button:default(0):arg_name(With button):arg_section(8, 0, 'Button', 'hand-pointer-o')}
					<a data-emarketer-click-target="products ${p->internal_id:html}" href="${p->cart_url:html}" target="${args->target:html}" data-style="display:inline-block; position:relative; top:1.3em; text-decoration:none; transition: font-size 0.3s ease; background-color:${args->border_color:html}; ${args->a_css_4:html:input_type(css):input_props('with_responsive=1'):arg_name(Button style):arg_section(8, 2, 'Button', 'hand-pointer-o')}" onmouseenter="var t=this; s=t.style, f=s.fontSize, p=f.match(/^([\d\.]+)(\w+)$/); if (!t._b) t._b=[s.backgroundColor, s.color, f]; s.backgroundColor=t._b[1]; s.color=t._b[0]; if (p) if (!t._p) {s.fontSize=(p[1]*0.9)+p[2]; t._p=1; setTimeout(function() {s.fontSize=t._b[2]; t._p=0;}, 300)}" onmouseleave="var s=this.style, b=this._b; s.backgroundColor=b[0]; s.color=b[1]">
						<div data-style="border:solid 1px; ${args->a_css_5:html:input_type(css):input_props('with_responsive=1'):arg_name(Button style):arg_section(8, 3, 'Button', 'hand-pointer-o')}">
							${args->button_text:arg_name(Button text):arg_section(8, 1, 'Button', 'hand-pointer-o')}
						</div>
					</a>
				</td>
			${end}
		</tr>
	</table>
	${block->pagination:default(0):arg_name(With slider pagination):arg_section(1, 10, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}
	<div id="tsp" class="$table_slider_pagination" slider_id="ts" selected_color="${args->pagination_color_on:html:input_type(color):arg_name(Bullet Selected Color):arg_section(1, 11, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" style="${args->pagination_color:html:input_type(css):arg_name(Bullet style):arg_section(1, 12, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}"></div>
</div>
```


## Tall Banner Products TIN



```
<div class="$responsive" data-style="display:inline-block; ${args->style:html:default('color: rgb(90, 128, 39);
background-color: white;
border: none;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(0, 0, 'Frame', 'th-large')}">
	${block->title:default(1):arg_name(With title bar):arg_section(2, 0, 'Title', 'bookmark')}
	<div style="${args->title_style:html:default('-webkit-tap-highlight-color: transparent;
-webkit-font-smoothing: antialiased;
visibility: visible;
box-sizing: inherit;
margin-top: 0;
font-family: inherit;
color: #2d2d2d;
line-height: inherit;
font-size: 22px;
font-weight: 100;
text-align: center;
border-bottom: 1px solid #FFCC00;'):input_type(css):arg_name(Style):arg_section(2, 2, 'Title', 'bookmark')}">
		${block->x:default(1):arg_name(With close button):arg_section(3, 0, 'Close button', 'close')}
		<div style="float:right; cursor:pointer; margin:0 0 .3em .3em">
			${args->x:default('<img src="//counter.e-marketer.io/images/close-buttons/round-transparent-black-16x16.png" style="width:16px; height:16px" class="$emarketer_button_dont_show_again" data-action_id="${action_id}">'):input_type(dontshowagain):arg_name(Close button):arg_section(3, 1, 'Close button', 'close')}
		</div>
		${args->title:default('Δημοφιλή'):arg_name(Text):arg_section(2, 1, 'Title', 'bookmark')}
		<div style="clear:both"></div>
	</div>
	<table style="height:100%; border-collapse:collapse">
		<tbody class="$table_slider" data-disabled="${args->with_slider:html:input_type(checkbox):input_props('value_off=1','value_on='):arg_name(Use slider widget):arg_section(1, 0, 'With slider', 'arrow-right')}" style="border:none; height:${args->height:html:default(550px):input_type(css_length):arg_name(Widget height):arg_section(1, 1, 'With slider', 'arrow-right')}" arrow_back_img="${args->arrow_back_img:html:default('https://static.emarketer.com/upload/362/3644becd0404ff8d.png'):input_type(emarketer_media_url):arg_name(Up arrow image):arg_section(1, 2, 'With slider', 'arrow-right')}" arrow_forward_img="${args->arrow_forward_img:html:default('https://static.emarketer.com/upload/362/12bddb03dee50eed.png'):input_type(emarketer_media_url):arg_name(Down arrow image):arg_section(1, 3, 'With slider', 'arrow-right')}">
			${foreach sum_viewed_categories_products as p where p->for_period='all' order by p->n_viewed desc limit 2}
				<tr style="border:none">
					<td data-style="${args->td_style:html:default('text-align: center;
vertical-align: top;
padding: 5px;
border: none;
width: 250px;;
height: 100%;'):input_type(css):input_props('with_responsive=1'):arg_name(Cell style):arg_section(0, 1, 'Frame', 'th-large')}">
						<a data-emarketer-click-target="products ${p->internal_id:html}" href="${p->cart_url:html:arg_name(Link target URL):arg_section(6, 0, 'Link target URL', 'link'):column_tags('url','custom text')}" target="${args->target:html:default(_self):input_type(a_target):arg_name(Open link in):arg_section(6, 1, 'Link target URL', 'link')}" style="${args->link_style:html:default('color:'):input_type(css):arg_name(Link style):arg_section(5, 2, 'Product name', 'text-height')}">
							<img src="${p->image_big_url:html:arg_name(Item image):arg_section(4, 0, 'Image', 'image'):column_tags(image)}" data-style="${args->img_style:html:default('border: double white 5px;
width: sel(130px, 20vw);
height: sel(130px, 20vw)margin-left: auto;
margin: auto;'):input_type(css):input_props('with_responsive=1'):arg_name(Item image style):arg_section(4, 1, 'Image', 'image')}" onerror="this.parentNode.parentNode.parentNode.style.display='none'">
							${block->p_title:default(1):arg_name(With product name):arg_section(5, 0, 'Product name', 'text-height')}
							<div>${p->title:arg_name(Product name):arg_section(5, 1, 'Product name', 'text-height')}</div>
						</a>
						${block->n_viewed:default(0):arg_name(With site statistics):arg_section(7, 0, 'Site statistics', 'bar-chart')}
						<div>${args->n_viewed_text:arg_name(Text):arg_section(7, 1, 'Site statistics', 'bar-chart')} ${foreach sum_products_all as s where s->internal_id = p->internal_id limit 1}${s->n_viewed:arg_name(Number):arg_section(7, 2, 'Site statistics', 'bar-chart')}${end}</div>
						<div style="margin-top:0.4em">
							${block->price:default(1):arg_name(With price):arg_section(8, 0, 'Second line', 'text-height'):onchange('args.rating_style = block.price ? ''float:right'' : '''';')}
							<div style="${args->price_style:html:input_type(css):arg_name(Price position):arg_section(8, 4, 'Second line', 'text-height')}">
								${if p->price}
									${args->before_price:arg_name(Text before price):arg_section(8, 1, 'Second line', 'text-height')}
									${if p->sale_price}
										${p->sale_price:truncate(2):sprintf($%s):arg_name(Price):arg_section(8, 2, 'Second line', 'text-height')}
										<div style="${args->sale_style:html:default('color:gray; text-decoration:line-through; font-size:85%'):input_type(css):input_props('with_responsive=1'):arg_name('Price before discount: style'):arg_section(8, 6, 'Second line', 'text-height')}">
											${p->price:truncate(2):sprintf($%s):arg_name(Price):arg_section(8, 5, 'Second line', 'text-height')}
										</div>
									${end}
									${if not p->sale_price}
										${p->price:truncate(2):sprintf($%s)}
									${end}
									${args->after_price:arg_name(Text after price):arg_section(8, 3, 'Second line', 'text-height')}
								${end}
							</div>
							${block->rating:default(0):arg_name(With rating):arg_section(8, 7, 'Second line', 'text-height'):onchange('args.price_style = block.rating ? ''float:left'' : '''';')}
							<div style="${args->rating_style:html:input_type(css):arg_name(Rating position):arg_section(8, 10, 'Second line', 'text-height')}">
								<input class="$rating" value="${p->rank:html:arg_name(Rating):arg_section(8, 8, 'Second line', 'text-height')}" max="${args->rank_max:html:input_type(number):arg_name(Maximum rating number that corresponds to 100%):arg_section(8, 9, 'Second line', 'text-height')}">
							</div>
							<div style="clear:both"></div>
						</div>
						${block->button:default(1):arg_name(With button):arg_section(9, 0, 'Add to cart button', 'plus-square')}
						<div style="margin-top:0.4em">
							<a data-emarketer-click-target="products ${p->internal_id:html}" href="${p->cart_url:html}" data-style="${args->button_style:html:default('padding-top: 2%;
-webkit-font-smoothing: antialiased;
visibility: visible;
-webkit-tap-highlight-color: transparent;
box-sizing: inherit;
font-family: sans-serif;
margin: 0;
overflow: visible;
text-transform: none;
-webkit-appearance: button;
touch-action: manipulation;
outline: none !important;
font-weight: normal;
text-align: center;
vertical-align: middle;
user-select: none;
background: #ffcc00;
border: none;
border-radius: 35px;
color: #515558;
display: inline-block;
font-size: 15px;
padding: 0.9em 2.5em;
position: relative;
line-height: 1.25;
cursor: pointer;
white-space: normal;
transition: background .2s, color .2s, border-color .2s;'):input_type(css):input_props('with_responsive=1'):arg_name(Button style):arg_section(9, 2, 'Add to cart button', 'plus-square')}">${args->button:default('Αγόρασε τώρα'):arg_name('Text', 'Link target URL'):arg_section(9, 1, 'Add to cart button', 'plus-square')}</a>
						</div>
					</td>
				</tr>
			${end}
		</tbody>
	</table>
</div>
```


## Product Recom Admiral



```
<div class="$responsive" data-style="display:inline-block; position:relative; ${args->style:html:default('padding-top: 5%;
text-align: center;
font-weight: bold;
font-size: 17px;
box-sizing: border-box;
width: 98%;
font-family: Roboto,sans-serif;
box-shadow: 0 0px 0px 0 rgba(0,0,0,0.08);
background-color: rgba(0, 0, 0, 0);
min-width: 98%;
font-family: Helvetica Neue,Helvetica,Arial,sans-serif;
line-height: 1.25;
text-rendering: optimizeLegibility;
font-feature-settings: "kern" 1;
font-kerning: normal;
-webkit-font-smoothing: antialiased;
-webkit-box-direction: normal;
color: #272727;
font-size: 0;
width: 288px;
box-sizing: inherit;
height: auto;
max-width: 100%;
border: 0;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(0, 1, 'Frame', 'th-large')}" onupdate="
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
	${block->title:default(1):arg_name(With title bar):arg_section(2, 0, 'Title', 'bookmark')}
	<table data-style="width:98%; margin-right: 1%; margin-left: 1%; border-collapse:collapse; border:none; ${args->title_bg:html:default('background-color: rgba(0, 0, 0, 0);
margin-top: 0px;
margin-right: 0;
margin-bottom: 25px;
padding-top: 0px;
padding-right: 0;
padding-bottom: 0px;
padding-left: 0;
border-bottom: none;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(2, 2, 'Title', 'bookmark')}">
		<tr>
			<td data-style="vertical-align:middle; ${args->title_style:html:default('font-family: Helvetica Neue,Helvetica,Arial,sans-serif;
text-rendering: optimizeLegibility;
font-feature-settings: "kern" 1;
font-kerning: normal;
-webkit-font-smoothing: antialiased;
box-sizing: inherit;
padding: 0;
color: #272727;
line-height: 1em;
display: block;
margin: 0 auto 35px;
background: #fff;
font-size: 28px;
text-align: center;
font-weight: 700;
width: 400px;
max-width: 100%;
z-index: 2;'):input_type(css):input_props('with_responsive=1'):arg_name(Title style):arg_section(2, 3, 'Title', 'bookmark')}">
				${args->title:default('<span>&Pi;&alpha;&rho;ό&mu;&omicron;&iota;&alpha; &Delta;&eta;&mu;&omicron;&phi;&iota;&lambda;ή</span>'):arg_name(Text):arg_section(2, 1, 'Title', 'bookmark')}
			</td>
			${block->with_arrows:default(0):arg_name(With arrow buttons):arg_section(1, 0, 'With slider', 'arrow-right')}
			<td style="width:1px; white-space:nowrap; vertical-align:middle">
				<a id="button_back" class="$flat_btn" style="${args->btn_style:html:input_type(css):arg_name(Arrow button style):arg_section(1, 1, 'With slider', 'arrow-right')}" hover_style="${args->btn_hover_style:html:input_type(css):arg_name('Arrow button style: hover'):arg_section(1, 2, 'With slider', 'arrow-right')}"><</a>
				<a id="button_forward" class="$flat_btn" style="${args->btn_style:html}" hover_style="${args->btn_hover_style:html}">></a>
			</td>
			${block->x:default(0):arg_name(With close button):arg_section(3, 0, 'Close button', 'close')}
			<td style="width:1px; white-space:nowrap; ${args->x_style:html:input_type(css):arg_name(Close button position):arg_section(3, 2, 'Close button', 'close')}">
				${args->x:input_type(dontshowagain):input_props('style=cursor:pointer; vertical-align:middle'):arg_name(Close button):arg_section(3, 1, 'Close button', 'close')}
			</td>
		</tr>
	</table>
	<table style="width:100%; border-collapse:separate; border-spacing:12px 0">
		<tr id="ts" class="$table_slider" data-disabled="${args->with_slider:html:default(1):input_type(checkbox):input_props('value_off=1','value_on='):arg_name(Use slider widget):arg_section(1, 4, 'With slider', 'arrow-right'):onchange('if (args.with_slider==1) block.with_arrows = block.pagination = 0')}" style="width: 100%; padding: 0 1%; box-sizing: border-box; border:none; max-width:${args->width:html:default(none):input_type(css_length):input_props('with_options=none'):arg_name(Widget maximum width):arg_section(0, 0, 'Frame', 'th-large')}" for_max_vw="${args->for_max_vw:html:input_type(css_length):input_props('with_options=always'):arg_name(Slider widget only if screen width is less than or equal to):arg_section(1, 5, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" eq_cell_width="${args->eq_cell_width:html:default(1):input_type(checkbox):input_props('value_off=','value_on=1'):arg_name(Equal cell width):arg_section(0, 2, 'Frame', 'th-large')}" arrows_line="${args->arrows_line:html:input_type(checkbox):input_props('value_off=-1','value_on=0'):arg_name(Arrows in the middle of images):arg_section(1, 9, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" arrow_back_img="${args->arrow_back_img:html:input_type(emarketer_media_url):arg_name(Left arrow image):arg_section(1, 6, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" arrow_style="${args->arrow_style:html:input_type(css):arg_name(Arrows style):arg_section(1, 7, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" pagination_id="tsp" arrow_back_id="button_back" arrow_forward_id="button_forward" arrows_offset="${args->arrows_offset:html:input_type(number):arg_name(Slider arrows offset):arg_section(1, 8, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" hide_buttons="${args->hide_buttons:html:input_type(checkbox):input_props('value_off=','value_on=1'):arg_name(Hide arrow buttons when nothing to scroll):arg_section(1, 3, 'With slider', 'arrow-right'):visible_if('block.title-0 && block.with_arrows-0')}">
			${foreach sum_last_viewed_categories_products as p where p->for_period='recently' order by p->n_viewed desc limit 4}
				<td style="position:relative; padding:0; text-align:center; background-color:white; vertical-align:top; border:solid ${args->border_color:html:default('rgb(5, 4, 4)'):input_type(color):arg_name(Border color):arg_section(0, 4, 'Frame', 'th-large')} 1px">
					<a data-emarketer-click-target="products ${p->internal_id:html}" href="${p->cart_url:html:arg_name(Link target URL):arg_section(6, 0, 'Link target URL', 'link'):column_tags('url','custom text')}" target="${args->target:html:default(_self):input_type(a_target):arg_name(Open link in):arg_section(6, 1, 'Link target URL', 'link')}" data-style="display:block; margin:auto; box-sizing:border-box; width:${args->img_width:html:default('sel(180px, 52vw)'):input_type(css_length):input_props('with_responsive=1'):arg_name(Cell width):arg_section(0, 3, 'Frame', 'th-large')}">
						<img src="${p->image_big_url:html:arg_name(Item image):arg_section(4, 0, 'Image', 'image'):column_tags(image)}" data-style="width:auto; height:auto; max-width:100%; max-height:${args->img_max_height:html:default('sel(146px, 30vw)'):input_type(css_length):input_props('with_responsive=1'):arg_name(Image maximum height):arg_section(0, 5, 'Frame', 'th-large')}">
					</a>
					<div data-style="margin:auto; box-sizing:border-box; width:${args->img_width:html}">
						<div data-style="${args->a_css:html:default('font-family: Helvetica Neue,Helvetica,Arial,sans-serif;
text-rendering: optimizeLegibility;
font-feature-settings: "kern" 1;
font-kerning: normal;
-webkit-font-smoothing: antialiased;
-webkit-box-direction: normal;
font-size: 18px;
line-height: 18px;
box-sizing: inherit;
background-color: transparent;
text-decoration: none;
color: #272727;
font-weight: 600;'):input_type(css):input_props('with_responsive=1'):arg_name(Text color):arg_section(5, 3, 'Text', 'align-justify')}">
							${p->title:arg_name(Item text):arg_section(5, 1, 'Text', 'align-justify')}
						</div>
					</div>
					${block->rating:default(0):arg_name(With rating):arg_section(7, 0, 'Rating', 'star')}
					<div style="margin: auto; margin-bottom: .6em; line-height: 12px">
						<div style="width: 69px; height: 13px; font-size: 0; line-height: 0; background: url(https://skin.christys-hats.com/frontend/ultimo/totalRecall/images/img/rating.png) 0 0 repeat-x; text-indent: -999em; overflow: hidden; margin-left: 0; margin-right: 0; display: inline-block; vertical-align: middle;">
							<div style="float: left; height: 13px; background: url(https://skin.christys-hats.com/frontend/ultimo/totalRecall/images/img/rating.png) 0 100% repeat-x; width: ${p->rank:html:default(0):arg_name(Rating):arg_section(7, 1, 'Rating', 'star')}%">
							</div>
						</div>
					</div>
					<div style="clear:left;"></div>
					${block->price:default(1):arg_name(With price):arg_section(8, 0, 'Price', 'dollar')}
					<div data-style="margin:auto; box-sizing:border-box; width:${args->img_width:html}; ${args->price_style:html:default('font-family: Helvetica Neue,Helvetica,Arial,sans-serif;
line-height: 1.25;
text-rendering: optimizeLegibility;
font-feature-settings: "kern" 1;
font-kerning: normal;
margin-bottom: 5%;
-webkit-font-smoothing: antialiased;
-webkit-box-direction: normal;
font-size: 30px;
font-weight: 700;
color: #272727;
border: none;
box-sizing: inherit;
display: block;
padding-top: 10%;'):input_type(css):input_props('with_responsive=1'):arg_name(Price style):arg_section(8, 5, 'Price', 'dollar')}">
						${if p->price}
							${args->before_price:arg_name(Text before price):arg_section(8, 1, 'Price', 'dollar')}
							${if p->sale_price and p->sale_price < p->price}
								${p->sale_price:truncate(2):sprintf('€%s'):arg_name(Price):arg_section(8, 6, 'Price', 'dollar')}
								<div style="${args->sale_style:html:default('font-family: Helvetica Neue,Helvetica,Arial,sans-serif;
text-rendering: optimizeLegibility;
font-feature-settings: "kern" 1;
font-kerning: normal;
-webkit-font-smoothing: antialiased;
-webkit-box-direction: normal;
padding-top: 2%;
font-weight: 700;
box-sizing: inherit;
text-decoration: line-through;
display: block;
color: #999;
font-size: 18px;
line-height: 16px;
margin-right: 5px;'):input_type(css):input_props('with_responsive=1'):arg_name('Price before discount: style'):arg_section(8, 3, 'Price', 'dollar')}">
									${p->price:truncate(2):sprintf('€%s'):arg_name(Price):arg_section(8, 2, 'Price', 'dollar')}
								</div>
							${end}
							${if not p->sale_price or p->sale_price >= p->price}
								${p->price:truncate(2):sprintf('€%s')}
							${end}
							${args->after_price:arg_name(Text after price):arg_section(8, 4, 'Price', 'dollar')}
						${end}
					</div>
					<div style="margin:auto; box-sizing:border-box; font-size:1px">
						<div data-style="display:inline-block; background-color:${args->border_color:html}; ${args->a_css_2:html:default('width: 0px;
height: 3px;
max-width: 80%;'):input_type(css):input_props('with_responsive=1'):arg_name(Ruler):arg_section(5, 5, 'Text', 'align-justify')}"></div>
					</div>
					${block->description:default(0):arg_name(With description):arg_section(5, 0, 'Text', 'align-justify')}
					<div data-style="margin:auto; box-sizing:border-box; width:${args->img_width:html}">
						<div data-style="display:inline-block; ${args->a_css_3:html:input_type(css):input_props('with_responsive=1'):arg_name(Text color):arg_section(5, 4, 'Text', 'align-justify')}; padding-bottom:0">
							${p->description:arg_name(Item text):arg_section(5, 2, 'Text', 'align-justify')}
						</div>
					</div>
					${block->button:default(1):arg_name(With button):arg_section(9, 0, 'Button', 'hand-pointer-o')}
					<div data-style="${args->button_spacer:html:default('height: 1.6em;'):input_type(css):input_props('with_responsive=1'):arg_name(Button reserved space):arg_section(9, 5, 'Button', 'hand-pointer-o')}">
						<a data-emarketer-click-target="products ${p->internal_id:html}" href="${p->cart_url:html}" target="${args->target:html}" data-style="display:block; box-sizing:border-box; position:absolute; width:100%; height:0; display:none; left:0; bottom:0; ${args->a_css_4:html:default('margin-top: 1.3em;
background-color: rgb(2, 2, 2);
color: rgb(253, 253, 253);
text-decoration: none;
padding-top: 0.3em;
padding-right: 0.5em;
padding-bottom: 0.3em;
padding-left: 0.5em;
font-weight: 300;'):input_type(css):input_props('with_responsive=1'):arg_name(Button style):arg_section(9, 3, 'Button', 'hand-pointer-o')}" ontplready="
							var a=ns.new_elem(this), p=this.parentNode.parentNode;
							p.onmouseenter = p.onmouseleave = function(e)
							{	var on = e.type == 'mouseenter';
								a.add_style({height: on ? 'auto' : '0', display: on ? '' : 'none'}, {});
							};
						">
							<div style="display:inline-block; width:1em; height:1em; line-height:1; border-radius:50%; ${args->plus_style:html:default('color: rgb(251, 250, 250);
background-color: rgb(5, 4, 4);'):input_type(css):input_props('with_responsive=1'):arg_name(Button style):arg_section(9, 4, 'Button', 'hand-pointer-o')}">${args->button_add_plus:default(+):arg_name(Icon text):arg_section(9, 2, 'Button', 'hand-pointer-o')}</div>
							${args->button_add_text:default('Πληροφορίες'):arg_name(Button text):arg_section(9, 1, 'Button', 'hand-pointer-o')}
						</a>
					</div>
				</td>
			${end}
		</tr>
	</table>
	${block->pagination:arg_name(With slider pagination):arg_section(1, 10, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}
	<div id="tsp" class="$table_slider_pagination" slider_id="ts" selected_color="${args->pagination_color_on:html:input_type(color):arg_name(Bullet Selected Color):arg_section(1, 11, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" style="${args->pagination_color:html:input_type(css):arg_name(Bullet style):arg_section(1, 12, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}"></div>
</div>
```


## Admiral Recommendation



```
<div class="$responsive" data-style="display:inline-block; position:relative; ${args->style:html:default('padding-top: 5%;
text-align: center;
font-weight: bold;
min-height: 288px;
font-size: 0;
box-sizing: inherit;
width: 288px;
font-family: Helvetica Neue,Helvetica,Arial,sans-serif;
box-shadow: 0 0px 0px 0 rgba(0,0,0,0.08);
background-color: rgba(0, 0, 0, 0);
min-width: 98%;
line-height: 1.25;
text-rendering: optimizeLegibility;
font-feature-settings: "kern" 1;
font-kerning: normal;
-webkit-font-smoothing: antialiased;
-webkit-box-direction: normal;
color: #272727;
height: auto;
max-width: 25%;
border: 0;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(0, 1, 'Frame', 'th-large')}" onupdate="
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
	${block->title:default(1):arg_name(With title bar):arg_section(2, 0, 'Title', 'bookmark')}
	<table data-style="width:98%; margin-right: 1%; margin-left: 1%; border-collapse:collapse; border:none; ${args->title_bg:html:default('background-color: rgba(0, 0, 0, 0);
margin-top: 0px;
margin-right: 0;
margin-bottom: 25px;
padding-top: 0px;
padding-right: 0;
padding-bottom: 0px;
padding-left: 0;
border-bottom: none;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(2, 2, 'Title', 'bookmark')}">
		<tr>
			<td data-style="vertical-align:middle; ${args->title_style:html:default('font-family: Helvetica Neue,Helvetica,Arial,sans-serif;
text-rendering: optimizeLegibility;
font-feature-settings: "kern" 1;
font-kerning: normal;
-webkit-font-smoothing: antialiased;
box-sizing: inherit;
padding: 0;
color: #272727;
line-height: 1em;
display: block;
margin: 0 auto 35px;
background: #fff;
font-size: 28px;
text-align: center;
font-weight: 700;
width: 400px;
max-width: 100%;
z-index: 2;'):input_type(css):input_props('with_responsive=1'):arg_name(Title style):arg_section(2, 3, 'Title', 'bookmark')}">
				${args->title:default('<span>&Pi;&alpha;&rho;ό&mu;&omicron;&iota;&alpha; &Delta;&eta;&mu;&omicron;&phi;&iota;&lambda;ή</span>'):arg_name(Text):arg_section(2, 1, 'Title', 'bookmark')}
			</td>
			${block->with_arrows:default(0):arg_name(With arrow buttons):arg_section(1, 0, 'With slider', 'arrow-right')}
			<td style="width:1px; white-space:nowrap; vertical-align:middle">
				<a id="button_back" class="$flat_btn" style="${args->btn_style:html:input_type(css):arg_name(Arrow button style):arg_section(1, 1, 'With slider', 'arrow-right')}" hover_style="${args->btn_hover_style:html:input_type(css):arg_name('Arrow button style: hover'):arg_section(1, 2, 'With slider', 'arrow-right')}"><</a>
				<a id="button_forward" class="$flat_btn" style="${args->btn_style:html}" hover_style="${args->btn_hover_style:html}">></a>
			</td>
			${block->x:default(0):arg_name(With close button):arg_section(3, 0, 'Close button', 'close')}
			<td style="width:1px; white-space:nowrap; ${args->x_style:html:input_type(css):arg_name(Close button position):arg_section(3, 2, 'Close button', 'close')}">
				${args->x:input_type(dontshowagain):input_props('style=cursor:pointer; vertical-align:middle'):arg_name(Close button):arg_section(3, 1, 'Close button', 'close')}
			</td>
		</tr>
	</table>
	<table style="width:100%; border-collapse:separate; border-spacing:12px 0">
		<tr id="ts" class="$table_slider" data-disabled="${args->with_slider:html:default(1):input_type(checkbox):input_props('value_off=1','value_on='):arg_name(Use slider widget):arg_section(1, 4, 'With slider', 'arrow-right'):onchange('if (args.with_slider==1) block.with_arrows = block.pagination = 0')}" style="width: 100%; padding: 0 1%; box-sizing: border-box; border:none; max-width:${args->width:html:default(none):input_type(css_length):input_props('with_options=none'):arg_name(Widget maximum width):arg_section(0, 0, 'Frame', 'th-large')}" for_max_vw="${args->for_max_vw:html:input_type(css_length):input_props('with_options=always'):arg_name(Slider widget only if screen width is less than or equal to):arg_section(1, 5, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" eq_cell_width="${args->eq_cell_width:html:default(1):input_type(checkbox):input_props('value_off=','value_on=1'):arg_name(Equal cell width):arg_section(0, 2, 'Frame', 'th-large')}" arrows_line="${args->arrows_line:html:input_type(checkbox):input_props('value_off=-1','value_on=0'):arg_name(Arrows in the middle of images):arg_section(1, 9, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" arrow_back_img="${args->arrow_back_img:html:input_type(emarketer_media_url):arg_name(Left arrow image):arg_section(1, 6, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" arrow_style="${args->arrow_style:html:input_type(css):arg_name(Arrows style):arg_section(1, 7, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" pagination_id="tsp" arrow_back_id="button_back" arrow_forward_id="button_forward" arrows_offset="${args->arrows_offset:html:input_type(number):arg_name(Slider arrows offset):arg_section(1, 8, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" hide_buttons="${args->hide_buttons:html:input_type(checkbox):input_props('value_off=','value_on=1'):arg_name(Hide arrow buttons when nothing to scroll):arg_section(1, 3, 'With slider', 'arrow-right'):visible_if('block.title-0 && block.with_arrows-0')}">
			${foreach products_interactions as p where p->interaction_status in ('viewed','extra','favorite') order by p->interaction_time desc limit 4}
				<td style="position:relative; padding:0; text-align:center; background-color:white; vertical-align:top; border:solid ${args->border_color:html:default('rgba(5, 4, 4, 0.18)'):input_type(color):arg_name(Border color):arg_section(0, 4, 'Frame', 'th-large')} 1px">
					<a data-emarketer-click-target="products ${p->internal_id:html}" href="${p->cart_url:html:arg_name(Link target URL):arg_section(6, 0, 'Link target URL', 'link'):column_tags('url','custom text')}" target="${args->target:html:default(_self):input_type(a_target):arg_name(Open link in):arg_section(6, 1, 'Link target URL', 'link')}" data-style="display:block; margin:auto; box-sizing:border-box; width:${args->img_width:html:default('sel(180px, 52vw)'):input_type(css_length):input_props('with_responsive=1'):arg_name(Cell width):arg_section(0, 3, 'Frame', 'th-large')}">
						<img src="${p->image_big_url:html:arg_name(Item image):arg_section(4, 0, 'Image', 'image'):column_tags(image)}" data-style="width:auto; height:auto; max-width:100%; max-height:${args->img_max_height:html:default('sel(200px, 30vw)'):input_type(css_length):input_props('with_responsive=1'):arg_name(Image maximum height):arg_section(0, 5, 'Frame', 'th-large')}">
					</a>
					<div data-style="margin:auto; box-sizing:border-box; width:${args->img_width:html}">
						<div data-style="${args->a_css:html:default('font-family: Helvetica Neue,Helvetica,Arial,sans-serif;
text-rendering: optimizeLegibility;
font-feature-settings: "kern" 1;
font-kerning: normal;
-webkit-font-smoothing: antialiased;
-webkit-box-direction: normal;
font-size: 18px;
line-height: 18px;
box-sizing: inherit;
background-color: transparent;
text-decoration: none;
color: #272727;
font-weight: 600;'):input_type(css):input_props('with_responsive=1'):arg_name(Text color):arg_section(5, 3, 'Text', 'align-justify')}">
							${p->title:arg_name(Item text):arg_section(5, 1, 'Text', 'align-justify')}
						</div>
					</div>
					${block->rating:default(0):arg_name(With rating):arg_section(7, 0, 'Rating', 'star')}
					<div style="margin: auto; margin-bottom: .6em; line-height: 12px">
						<div style="width: 69px; height: 13px; font-size: 0; line-height: 0; background: url(https://skin.christys-hats.com/frontend/ultimo/totalRecall/images/img/rating.png) 0 0 repeat-x; text-indent: -999em; overflow: hidden; margin-left: 0; margin-right: 0; display: inline-block; vertical-align: middle;">
							<div style="float: left; height: 13px; background: url(https://skin.christys-hats.com/frontend/ultimo/totalRecall/images/img/rating.png) 0 100% repeat-x; width: ${p->rank:html:default(0):arg_name(Rating):arg_section(7, 1, 'Rating', 'star')}%">
							</div>
						</div>
					</div>
					<div style="clear:left;"></div>
					${block->price:default(1):arg_name(With price):arg_section(8, 0, 'Price', 'dollar')}
					<div data-style="margin:auto; box-sizing:border-box; width:${args->img_width:html}; ${args->price_style:html:default('font-family: Helvetica Neue,Helvetica,Arial,sans-serif;
line-height: 1.25;
text-rendering: optimizeLegibility;
font-feature-settings: "kern" 1;
font-kerning: normal;
margin-bottom: 5%;
-webkit-font-smoothing: antialiased;
-webkit-box-direction: normal;
font-size: 30px;
font-weight: 700;
color: #272727;
border: none;
box-sizing: inherit;
display: block;
padding-top: 10%;'):input_type(css):input_props('with_responsive=1'):arg_name(Price style):arg_section(8, 5, 'Price', 'dollar')}">
						${if p->price}
							${args->before_price:arg_name(Text before price):arg_section(8, 1, 'Price', 'dollar')}
							${if p->sale_price and p->sale_price < p->price}
								${p->sale_price:truncate(2):sprintf('€%s'):arg_name(Price):arg_section(8, 6, 'Price', 'dollar')}
								<div style="${args->sale_style:html:default('font-family: Helvetica Neue,Helvetica,Arial,sans-serif;
text-rendering: optimizeLegibility;
font-feature-settings: "kern" 1;
font-kerning: normal;
-webkit-font-smoothing: antialiased;
-webkit-box-direction: normal;
padding-top: 2%;
font-weight: 700;
box-sizing: inherit;
text-decoration: line-through;
display: block;
color: #999;
font-size: 18px;
line-height: 16px;
margin-right: 5px;'):input_type(css):input_props('with_responsive=1'):arg_name('Price before discount: style'):arg_section(8, 3, 'Price', 'dollar')}">
									${p->price:truncate(2):sprintf('€%s'):arg_name(Price):arg_section(8, 2, 'Price', 'dollar')}
								</div>
							${end}
							${if not p->sale_price or p->sale_price >= p->price}
								${p->price:truncate(2):sprintf('€%s')}
							${end}
							${args->after_price:arg_name(Text after price):arg_section(8, 4, 'Price', 'dollar')}
						${end}
					</div>
					<div style="margin:auto; box-sizing:border-box; font-size:1px">
						<div data-style="display:inline-block; background-color:${args->border_color:html}; ${args->a_css_2:html:default('width: 0px;
height: 3px;
max-width: 80%;'):input_type(css):input_props('with_responsive=1'):arg_name(Ruler):arg_section(5, 5, 'Text', 'align-justify')}"></div>
					</div>
					${block->description:default(0):arg_name(With description):arg_section(5, 0, 'Text', 'align-justify')}
					<div data-style="margin:auto; box-sizing:border-box; width:${args->img_width:html}">
						<div data-style="display:inline-block; ${args->a_css_3:html:input_type(css):input_props('with_responsive=1'):arg_name(Text color):arg_section(5, 4, 'Text', 'align-justify')}; padding-bottom:0">
							${p->description:arg_name(Item text):arg_section(5, 2, 'Text', 'align-justify')}
						</div>
					</div>
					${block->button:default(1):arg_name(With button):arg_section(9, 0, 'Button', 'hand-pointer-o')}
					<div data-style="${args->button_spacer:html:default('height: 1.6em;'):input_type(css):input_props('with_responsive=1'):arg_name(Button reserved space):arg_section(9, 5, 'Button', 'hand-pointer-o')}">
						<a data-emarketer-click-target="products ${p->internal_id:html}" href="${p->cart_url:html}" target="${args->target:html}" data-style="display:block; box-sizing:border-box; position:absolute; width:100%; height:0; display:none; left:0; bottom:0; ${args->a_css_4:html:default('margin-top: 1.3em;
background-color: rgb(2, 2, 2);
color: rgb(253, 253, 253);
text-decoration: none;
padding-top: 0.3em;
padding-right: 0.5em;
padding-bottom: 0.3em;
padding-left: 0.5em;
font-weight: 300;'):input_type(css):input_props('with_responsive=1'):arg_name(Button style):arg_section(9, 3, 'Button', 'hand-pointer-o')}" ontplready="
							var a=ns.new_elem(this), p=this.parentNode.parentNode;
							p.onmouseenter = p.onmouseleave = function(e)
							{	var on = e.type == 'mouseenter';
								a.add_style({height: on ? 'auto' : '0', display: on ? '' : 'none'}, {});
							};
						">
							<div style="display:inline-block; width:1em; height:1em; line-height:1; border-radius:50%; ${args->plus_style:html:default('color: rgb(251, 250, 250);
background-color: rgb(5, 4, 4);'):input_type(css):input_props('with_responsive=1'):arg_name(Button style):arg_section(9, 4, 'Button', 'hand-pointer-o')}">${args->button_add_plus:default(+):arg_name(Icon text):arg_section(9, 2, 'Button', 'hand-pointer-o')}</div>
							${args->button_add_text:default('Πληροφορίες'):arg_name(Button text):arg_section(9, 1, 'Button', 'hand-pointer-o')}
						</a>
					</div>
				</td>
			${end}
		</tr>
	</table>
	${block->pagination:arg_name(With slider pagination):arg_section(1, 10, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}
	<div id="tsp" class="$table_slider_pagination" slider_id="ts" selected_color="${args->pagination_color_on:html:input_type(color):arg_name(Bullet Selected Color):arg_section(1, 11, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" style="${args->pagination_color:html:input_type(css):arg_name(Bullet style):arg_section(1, 12, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}"></div>
</div>
```


## Template Admiral Final



```
<div class="$responsive" data-style="display:inline-block; position:relative; ${args->style:html:default('padding: 5%;
text-align: center;
font-weight: bold;
min-height: 288px;
font-size: 0;
box-sizing: inherit;
width: 288px;
font-family: Helvetica Neue,Helvetica,Arial,sans-serif;
box-shadow: 0 0px 0px 0 rgba(0,0,0,0.08);
background-color: rgba(0, 0, 0, 0);
min-width: 98%;
line-height: 1.25;
text-rendering: optimizeLegibility;
font-feature-settings: "kern" 1;
font-kerning: normal;
-webkit-font-smoothing: antialiased;
-webkit-box-direction: normal;
color: #272727;
height: auto;
max-width: 25%;
border: 0;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(0, 1, 'Frame', 'th-large')}" onupdate="
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
	${block->title:default(1):arg_name(With title bar):arg_section(2, 0, 'Title', 'bookmark')}
	<table data-style="width:98%; margin-right: 1%; margin-left: 1%; border-collapse:collapse; border:none; ${args->title_bg:html:default('background-color: rgba(0, 0, 0, 0);
margin-top: 0px;
margin-right: 0;
margin-bottom: 25px;
padding-top: 0px;
padding-right: 0;
padding-bottom: 0px;
padding-left: 0;
border-bottom: none;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(2, 2, 'Title', 'bookmark')}">
		<tr>
			<td data-style="vertical-align:middle; ${args->title_style:html:default('font-family: Helvetica Neue,Helvetica,Arial,sans-serif;
text-rendering: optimizeLegibility;
font-feature-settings: "kern" 1;
font-kerning: normal;
-webkit-font-smoothing: antialiased;
box-sizing: inherit;
padding: 0;
color: #272727;
line-height: 1em;
display: block;
margin: 0 auto 35px;
background: #fff;
font-size: 28px;
text-align: center;
font-weight: 700;
width: 400px;
max-width: 100%;
z-index: 2;'):input_type(css):input_props('with_responsive=1'):arg_name(Title style):arg_section(2, 3, 'Title', 'bookmark')}">
				${args->title:default('<span>&Pi;&alpha;&rho;ό&mu;&omicron;&iota;&alpha; &Delta;&eta;&mu;&omicron;&phi;&iota;&lambda;ή</span>'):arg_name(Text):arg_section(2, 1, 'Title', 'bookmark')}
			</td>
			${block->with_arrows:default(0):arg_name(With arrow buttons):arg_section(1, 0, 'With slider', 'arrow-right')}
			<td style="width:1px; white-space:nowrap; vertical-align:middle">
				<a id="button_back" class="$flat_btn" style="${args->btn_style:html:input_type(css):arg_name(Arrow button style):arg_section(1, 1, 'With slider', 'arrow-right')}" hover_style="${args->btn_hover_style:html:input_type(css):arg_name('Arrow button style: hover'):arg_section(1, 2, 'With slider', 'arrow-right')}"><</a>
				<a id="button_forward" class="$flat_btn" style="${args->btn_style:html}" hover_style="${args->btn_hover_style:html}">></a>
			</td>
			${block->x:default(0):arg_name(With close button):arg_section(3, 0, 'Close button', 'close')}
			<td style="width:1px; white-space:nowrap; ${args->x_style:html:input_type(css):arg_name(Close button position):arg_section(3, 2, 'Close button', 'close')}">
				${args->x:input_type(dontshowagain):input_props('style=cursor:pointer; vertical-align:middle'):arg_name(Close button):arg_section(3, 1, 'Close button', 'close')}
			</td>
		</tr>
	</table>
	<table style="width:100%; border-collapse:separate; border-spacing:12px 0">
		<tr id="ts" class="$table_slider" data-disabled="${args->with_slider:html:default(1):input_type(checkbox):input_props('value_off=1','value_on='):arg_name(Use slider widget):arg_section(1, 4, 'With slider', 'arrow-right'):onchange('if (args.with_slider==1) block.with_arrows = block.pagination = 0')}" style="width: 100%; padding: 0 1%; box-sizing: border-box; border:none; max-width:${args->width:html:default(none):input_type(css_length):input_props('with_options=none'):arg_name(Widget maximum width):arg_section(0, 0, 'Frame', 'th-large')}" for_max_vw="${args->for_max_vw:html:input_type(css_length):input_props('with_options=always'):arg_name(Slider widget only if screen width is less than or equal to):arg_section(1, 5, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" eq_cell_width="${args->eq_cell_width:html:default(1):input_type(checkbox):input_props('value_off=','value_on=1'):arg_name(Equal cell width):arg_section(0, 2, 'Frame', 'th-large')}" arrows_line="${args->arrows_line:html:input_type(checkbox):input_props('value_off=-1','value_on=0'):arg_name(Arrows in the middle of images):arg_section(1, 9, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" arrow_back_img="${args->arrow_back_img:html:input_type(emarketer_media_url):arg_name(Left arrow image):arg_section(1, 6, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" arrow_style="${args->arrow_style:html:input_type(css):arg_name(Arrows style):arg_section(1, 7, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" pagination_id="tsp" arrow_back_id="button_back" arrow_forward_id="button_forward" arrows_offset="${args->arrows_offset:html:input_type(number):arg_name(Slider arrows offset):arg_section(1, 8, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" hide_buttons="${args->hide_buttons:html:input_type(checkbox):input_props('value_off=','value_on=1'):arg_name(Hide arrow buttons when nothing to scroll):arg_section(1, 3, 'With slider', 'arrow-right'):visible_if('block.title-0 && block.with_arrows-0')}">
			${foreach sum_last_viewed_categories_products as p where p->for_period='recently' order by p->n_viewed desc limit 3}
				<td style="position:relative; padding:0; text-align:center; background-color:white; vertical-align:top; border:solid ${args->border_color:html:default('rgba(5, 4, 4, 0.13)'):input_type(color):arg_name(Border color):arg_section(0, 4, 'Frame', 'th-large')} 1px">
					<a data-emarketer-click-target="products ${p->internal_id:html}" href="${p->cart_url:html:arg_name(Link target URL):arg_section(6, 0, 'Link target URL', 'link'):column_tags('url','custom text')}" target="${args->target:html:default(_self):input_type(a_target):arg_name(Open link in):arg_section(6, 1, 'Link target URL', 'link')}" data-style="display:block; margin:auto; box-sizing:border-box; width:${args->img_width:html:default('sel(180px, 52vw)'):input_type(css_length):input_props('with_responsive=1'):arg_name(Cell width):arg_section(0, 3, 'Frame', 'th-large')}">
						<img src="${p->image_big_url:html:arg_name(Item image):arg_section(4, 0, 'Image', 'image'):column_tags(image)}" data-style="width:auto; height:auto; max-width:100%; max-height:${args->img_max_height:html:default('sel(200px, 30vw)'):input_type(css_length):input_props('with_responsive=1'):arg_name(Image maximum height):arg_section(0, 5, 'Frame', 'th-large')}">
					</a>
					<div data-style="margin:auto; box-sizing:border-box; width:${args->img_width:html}">
						<div data-style="${args->a_css:html:default('font-family: Helvetica Neue,Helvetica,Arial,sans-serif;
text-rendering: optimizeLegibility;
font-feature-settings: "kern" 1;
font-kerning: normal;
-webkit-font-smoothing: antialiased;
-webkit-box-direction: normal;
font-size: 18px;
line-height: 18px;
box-sizing: inherit;
background-color: transparent;
text-decoration: none;
color: #272727;
font-weight: 600;'):input_type(css):input_props('with_responsive=1'):arg_name(Text color):arg_section(5, 3, 'Text', 'align-justify')}">
							${p->title:arg_name(Item text):arg_section(5, 1, 'Text', 'align-justify')}
						</div>
					</div>
					${block->rating:default(0):arg_name(With rating):arg_section(7, 0, 'Rating', 'star')}
					<div style="margin: auto; margin-bottom: .6em; line-height: 12px">
						<div style="width: 69px; height: 13px; font-size: 0; line-height: 0; background: url(https://skin.christys-hats.com/frontend/ultimo/totalRecall/images/img/rating.png) 0 0 repeat-x; text-indent: -999em; overflow: hidden; margin-left: 0; margin-right: 0; display: inline-block; vertical-align: middle;">
							<div style="float: left; height: 13px; background: url(https://skin.christys-hats.com/frontend/ultimo/totalRecall/images/img/rating.png) 0 100% repeat-x; width: ${p->rank:html:default(0):arg_name(Rating):arg_section(7, 1, 'Rating', 'star')}%">
							</div>
						</div>
					</div>
					<div style="clear:left;"></div>
					${block->price:default(1):arg_name(With price):arg_section(8, 0, 'Price', 'dollar')}
					<div data-style="margin:auto; box-sizing:border-box; width:${args->img_width:html}; ${args->price_style:html:default('font-family: Helvetica Neue,Helvetica,Arial,sans-serif;
line-height: 1.25;
text-rendering: optimizeLegibility;
font-feature-settings: "kern" 1;
font-kerning: normal;
margin-bottom: 5%;
-webkit-font-smoothing: antialiased;
-webkit-box-direction: normal;
font-size: 20px;
font-weight: 700;
color: #272727;
border: none;
box-sizing: inherit;
display: block;
padding-top: 10%;'):input_type(css):input_props('with_responsive=1'):arg_name(Price style):arg_section(8, 5, 'Price', 'dollar')}">
						${if p->price}
							${args->before_price:arg_name(Text before price):arg_section(8, 1, 'Price', 'dollar')}
							${if p->sale_price and p->sale_price < p->price}
								${p->sale_price:truncate(2):sprintf('€%s'):arg_name(Price):arg_section(8, 6, 'Price', 'dollar')}
								<div style="${args->sale_style:html:default('font-family: Helvetica Neue,Helvetica,Arial,sans-serif;
text-rendering: optimizeLegibility;
font-feature-settings: "kern" 1;
font-kerning: normal;
-webkit-font-smoothing: antialiased;
-webkit-box-direction: normal;
padding-top: 2%;
font-weight: 700;
box-sizing: inherit;
text-decoration: line-through;
display: block;
color: #999;
font-size: 18px;
line-height: 16px;
margin-right: 5px;'):input_type(css):input_props('with_responsive=1'):arg_name('Price before discount: style'):arg_section(8, 3, 'Price', 'dollar')}">
									${p->price:truncate(2):sprintf('€%s'):arg_name(Price):arg_section(8, 2, 'Price', 'dollar')}
								</div>
							${end}
							${if not p->sale_price or p->sale_price >= p->price}
								${p->price:truncate(2):sprintf('€%s')}
							${end}
							${args->after_price:arg_name(Text after price):arg_section(8, 4, 'Price', 'dollar')}
						${end}
					</div>
					<div style="margin:auto; box-sizing:border-box; font-size:1px">
						<div data-style="display:inline-block; background-color:${args->border_color:html}; ${args->a_css_2:html:default('width: 0px;
height: 3px;
max-width: 80%;'):input_type(css):input_props('with_responsive=1'):arg_name(Ruler):arg_section(5, 5, 'Text', 'align-justify')}"></div>
					</div>
					${block->description:default(0):arg_name(With description):arg_section(5, 0, 'Text', 'align-justify')}
					<div data-style="margin:auto; box-sizing:border-box; width:${args->img_width:html}">
						<div data-style="display:inline-block; ${args->a_css_3:html:input_type(css):input_props('with_responsive=1'):arg_name(Text color):arg_section(5, 4, 'Text', 'align-justify')}; padding-bottom:0">
							${p->description:arg_name(Item text):arg_section(5, 2, 'Text', 'align-justify')}
						</div>
					</div>
					${block->button:default(1):arg_name(With button):arg_section(9, 0, 'Button', 'hand-pointer-o')}
					<div data-style="${args->button_spacer:html:default('height: 1.6em;'):input_type(css):input_props('with_responsive=1'):arg_name(Button reserved space):arg_section(9, 5, 'Button', 'hand-pointer-o')}">
						<a data-emarketer-click-target="products ${p->internal_id:html}" href="${p->cart_url:html}" target="${args->target:html}" data-style="display:block; box-sizing:border-box; position:absolute; width:100%; height:0; display:none; left:0; bottom:0; ${args->a_css_4:html:default('margin-top: 1.3em;
background-color: rgb(2, 2, 2);
color: rgb(253, 253, 253);
text-decoration: none;
padding-top: 0.3em;
padding-right: 0.5em;
padding-bottom: 0.3em;
padding-left: 0.5em;
font-weight: 300;'):input_type(css):input_props('with_responsive=1'):arg_name(Button style):arg_section(9, 3, 'Button', 'hand-pointer-o')}" ontplready="
							var a=ns.new_elem(this), p=this.parentNode.parentNode;
							p.onmouseenter = p.onmouseleave = function(e)
							{	var on = e.type == 'mouseenter';
								a.add_style({height: on ? 'auto' : '0', display: on ? '' : 'none'}, {});
							};
						">
							<div style="display:inline-block; width:1em; height:1em; line-height:1; border-radius:50%; ${args->plus_style:html:default('color: rgb(251, 250, 250);
background-color: rgb(5, 4, 4);'):input_type(css):input_props('with_responsive=1'):arg_name(Button style):arg_section(9, 4, 'Button', 'hand-pointer-o')}">${args->button_add_plus:default(+):arg_name(Icon text):arg_section(9, 2, 'Button', 'hand-pointer-o')}</div>
							${args->button_add_text:default('Πληροφορίες'):arg_name(Button text):arg_section(9, 1, 'Button', 'hand-pointer-o')}
						</a>
					</div>
				</td>
			${end}
		</tr>
	</table>
	${block->pagination:arg_name(With slider pagination):arg_section(1, 10, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}
	<div id="tsp" class="$table_slider_pagination" slider_id="ts" selected_color="${args->pagination_color_on:html:input_type(color):arg_name(Bullet Selected Color):arg_section(1, 11, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" style="${args->pagination_color:html:input_type(css):arg_name(Bullet style):arg_section(1, 12, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}"></div>
</div>
```


## View - Purchase Counter



```
<div id=st_w class="$responsive" data-style="display:inline-block; position:relative; ${args->style:html:default('padding: 15px;
text-align: left;
font-weight: bold;
font-size: 16px;
box-sizing: border-box;
width: 190px;
font-family: Roboto,sans-serif;
box-shadow: 0 0px 0px 0 rgba(0,0,0,0.08);
background-color: #333333;
margin-top: 00px;
margin-right: 0px;
margin-bottom: 1px;
margin-left: 0px;
color: rgb(255, 256, 256);
border-top-left-radius: 0px;
border-top-right-radius: 30px;
border-bottom-right-radius: 30px;
border-bottom-left-radius: 0px;
line-height: 20px;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(0, 1, 'Frame', 'th-large')}" onupdate="
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
	${block->title:default(1):arg_name(With title bar):arg_section(2, 0, 'Title', 'bookmark')}
	<table data-style="width:98%; margin-right: 1%; margin-left: 1%; border-collapse:collapse; border:none; ${args->title_bg:html:default('background-color: rgba(0, 0, 0, 0);
margin-top: 0px;
margin-right: 0;
margin-bottom: 0px;
padding-top: 0px;
padding-right: 0;
padding-bottom: 0px;
padding-left: 0;
border-bottom: none;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(2, 2, 'Title', 'bookmark')}">
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
color: #FAC200;'):input_type(css):input_props('with_responsive=1'):arg_name(Title style):arg_section(2, 3, 'Title', 'bookmark')}">
				${args->title:arg_name(Text):arg_section(2, 1, 'Title', 'bookmark')}
			</td>
			${block->with_arrows:default(0):arg_name(With arrow buttons):arg_section(1, 0, 'With slider', 'arrow-right')}
			<td style="width:1px; white-space:nowrap; vertical-align:middle">
				<a id="button_back" class="$flat_btn" style="${args->btn_style:html:input_type(css):arg_name(Arrow button style):arg_section(1, 1, 'With slider', 'arrow-right')}" hover_style="${args->btn_hover_style:html:input_type(css):arg_name('Arrow button style: hover'):arg_section(1, 2, 'With slider', 'arrow-right')}"><</a>
				<a id="button_forward" class="$flat_btn" style="${args->btn_style:html}" hover_style="${args->btn_hover_style:html}">></a>
			</td>
			${block->x:default(1):arg_name(With close button):arg_section(3, 0, 'Close button', 'close')}
			<td style="width:1px; white-space:nowrap; ${args->x_style:html:input_type(css):arg_name(Close button position):arg_section(3, 2, 'Close button', 'close')}">
				${args->x:default('<a href="javascript:" style="font-size: 18px; color: rgb(253, 253, 253); font-weight: bold; line-height: 1; text-decoration: none;" class="$personyze_button_dont_show_again" data-action_id="${action_id}">×</a>'):input_type(dontshowagain):input_props('style=cursor:pointer; vertical-align:middle'):arg_name(Close button):arg_section(3, 1, 'Close button', 'close')}
			</td>
		</tr>
	</table>
	<table style="width:100%; border-collapse:separate; border-spacing:12px 0">
		<tr id="ts" class="$table_slider" data-disabled="${args->with_slider:html:default(1):input_type(checkbox):input_props('value_off=1','value_on='):arg_name(Use slider widget):arg_section(1, 4, 'With slider', 'arrow-right'):onchange('if (args.with_slider==1) block.with_arrows = block.pagination = 0')}" style="width: 100%; padding: 0 1%; box-sizing: border-box; border:none; max-width:${args->width:html:default(none):input_type(css_length):input_props('with_options=none'):arg_name(Widget maximum width):arg_section(0, 0, 'Frame', 'th-large')}" for_max_vw="${args->for_max_vw:html:input_type(css_length):input_props('with_options=always'):arg_name(Slider widget only if screen width is less than or equal to):arg_section(1, 5, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" eq_cell_width="${args->eq_cell_width:html:default(1):input_type(checkbox):input_props('value_off=','value_on=1'):arg_name(Equal cell width):arg_section(0, 2, 'Frame', 'th-large')}" arrows_line="${args->arrows_line:html:input_type(checkbox):input_props('value_off=-1','value_on=0'):arg_name(Arrows in the middle of images):arg_section(1, 9, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" arrow_back_img="${args->arrow_back_img:html:input_type(personyze_media_url):arg_name(Left arrow image):arg_section(1, 6, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" arrow_style="${args->arrow_style:html:input_type(css):arg_name(Arrows style):arg_section(1, 7, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" pagination_id="tsp" arrow_back_id="button_back" arrow_forward_id="button_forward" arrows_offset="${args->arrows_offset:html:input_type(number):arg_name(Slider arrows offset):arg_section(1, 8, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" hide_buttons="${args->hide_buttons:html:input_type(checkbox):input_props('value_off=','value_on=1'):arg_name(Hide arrow buttons when nothing to scroll):arg_section(1, 3, 'With slider', 'arrow-right'):visible_if('block.title-0 && block.with_arrows-0')}">
			${foreach products_interactions as p where p->interaction_status in ('viewed','extra','favorite') order by p->interaction_time desc limit 1}
				<td style="position:relative; padding:0; text-align:center; vertical-align:top; border:solid ${args->border_color:html:default('rgba(178, 32, 32, 0)'):input_type(color):arg_name(Border color):arg_section(0, 4, 'Frame', 'th-large')} 1px">
					${block->img:default(0):arg_name(With image):arg_section(4, 0, 'Image', 'image')}
					<a data-personyze-click-target="products ${p->internal_id:html}" href="${p->cart_url:html:arg_name(Link target URL):arg_section(6, 0, 'Link target URL', 'link'):column_tags('url','custom text')}" target="${args->target:html:default(_self):input_type(a_target):arg_name(Open link in):arg_section(6, 1, 'Link target URL', 'link')}" data-style="display:block; margin:auto; box-sizing:border-box; width:${args->img_width:html:default('sel(0px, 0vw)'):input_type(css_length):input_props('with_responsive=1'):arg_name(Cell width):arg_section(0, 3, 'Frame', 'th-large')}">
						<img src="${p->image_big_url:html:arg_name(Item image):arg_section(4, 1, 'Image', 'image'):column_tags(image)}" data-style="width:auto; height:auto; max-width:100%; max-height:${args->img_max_height:html:input_type(css_length):input_props('with_responsive=1'):arg_name(Image maximum height):arg_section(0, 5, 'Frame', 'th-large')}">
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
background-color: rgba(29, 17, 17, 0);'):input_type(css):input_props('with_responsive=1'):arg_name(Text color):arg_section(5, 3, 'Text', 'align-justify')}">
							${p->age_to:arg_name(Item text):arg_section(5, 1, 'Text', 'align-justify')}
						</div>
					</div>
					${block->rating:default(0):arg_name(With rating):arg_section(7, 0, 'Rating', 'star')}
					<div style="margin: auto; margin-bottom: .6em; line-height: 12px">
						<div style="width: 69px; height: 13px; font-size: 0; line-height: 0; background: url(https://skin.christys-hats.com/frontend/ultimo/totalRecall/images/img/rating.png) 0 0 repeat-x; text-indent: -999em; overflow: hidden; margin-left: 0; margin-right: 0; display: inline-block; vertical-align: middle;">
							<div style="float: left; height: 13px; background: url(https://skin.christys-hats.com/frontend/ultimo/totalRecall/images/img/rating.png) 0 100% repeat-x; width: ${p->rank:html:default(0):arg_name(Rating):arg_section(7, 1, 'Rating', 'star')}%">
							</div>
						</div>
					</div>
					<div style="clear:left;"></div>

					${block->n_viewed:default(1):arg_name(With site statistics):arg_section(8, 0, 'Site statistics: week', 'bar-chart')}
					<div>
						${foreach sum_products_week as s where s->internal_id = p->internal_id limit 1}
							${block->hide_no_view:default(0):arg_name(Hide the widget if no views):arg_section(8, 2, 'Site statistics: week', 'bar-chart')}
							<span ontplready="if ('${s->n_viewed:html}' == 0) _S_T.dismiss_action(${action_id:html})"></span>
							${block->hide_no_goal:default(1):arg_name(Hide the widget if no purchases):arg_section(8, 3, 'Site statistics: week', 'bar-chart')}
							<span ontplready="if ('${s->n_goal:html}' == 0) _S_T.dismiss_action(${action_id:html})"></span>
							${args->n_viewed_text:default('<span style="font-size:14px;">Good choice! This product has been popular in the last week!</span><br />
&nbsp;
<div><span style="color:#fac200;"><strong>${s->n_viewed} viewed</strong></span></div>

<div><span style="color:#fac200;"><strong>${s->n_goal} purchased</strong></span></div>
'):arg_name(Text):arg_section(8, 1, 'Site statistics: week', 'bar-chart')}
						${end}
					</div>

					${block->price:default(0):arg_name(With price):arg_section(9, 0, 'Price', 'dollar')}
					<div data-style="margin:auto; box-sizing:border-box; width:${args->img_width:html}; ${args->price_style:html:input_type(css):input_props('with_responsive=1'):arg_name(Price style):arg_section(9, 5, 'Price', 'dollar')}">
						${if p->price}
							${args->before_price:arg_name(Text before price):arg_section(9, 1, 'Price', 'dollar')}
							${if p->sale_price and p->sale_price < p->price}
								${p->sale_price:truncate(2):sprintf($%s):arg_name(Price):arg_section(9, 6, 'Price', 'dollar')}
								<div style="${args->sale_style:html:input_type(css):input_props('with_responsive=1'):arg_name('Price before discount: style'):arg_section(9, 3, 'Price', 'dollar')}">
									${p->price:truncate(2):sprintf($%s):arg_name(Price):arg_section(9, 2, 'Price', 'dollar')}
								</div>
							${end}
							${if not p->sale_price or p->sale_price >= p->price}
								${p->price:truncate(2):sprintf($%s)}
							${end}
							${args->after_price:arg_name(Text after price):arg_section(9, 4, 'Price', 'dollar')}
						${end}
					</div>
					<div style="margin:auto; box-sizing:border-box; font-size:1px">
						<div data-style="display:inline-block; background-color:${args->border_color:html}; ${args->a_css_2:html:default('width:100px; height:3px; max-width:80%'):input_type(css):input_props('with_responsive=1'):arg_name(Ruler):arg_section(5, 5, 'Text', 'align-justify')}"></div>
					</div>
					${block->description:default(0):arg_name(With description):arg_section(5, 0, 'Text', 'align-justify')}
					<div data-style="margin:auto; box-sizing:border-box; width:${args->img_width:html}">
						<div data-style="display:inline-block; ${args->a_css_3:html:input_type(css):input_props('with_responsive=1'):arg_name(Text color):arg_section(5, 4, 'Text', 'align-justify')}; padding-bottom:0">
							${p->description:arg_name(Item text):arg_section(5, 2, 'Text', 'align-justify')}
						</div>
					</div>
					${block->button:default(0):arg_name(With button):arg_section(10, 0, 'Button', 'hand-pointer-o')}
					<div data-style="${args->button_spacer:html:input_type(css):input_props('with_responsive=1'):arg_name(Button reserved space):arg_section(10, 5, 'Button', 'hand-pointer-o')}">
						<a data-personyze-click-target="products ${p->internal_id:html}" href="${p->cart_url:html}" target="${args->target:html}" data-style="display:block; box-sizing:border-box; position:absolute; width:100%; height:0; display:none; left:0; bottom:0; ${args->a_css_4:html:input_type(css):input_props('with_responsive=1'):arg_name(Button style):arg_section(10, 3, 'Button', 'hand-pointer-o')}" ontplready="
							var a=ns.new_elem(this), p=this.parentNode.parentNode;
							p.onmouseenter = p.onmouseleave = function(e)
							{	var on = e.type == 'mouseenter';
								a.add_style({height: on ? 'auto' : '0', display: on ? '' : 'none'}, {});
							};
						">
							<div style="display:inline-block; width:1em; height:1em; line-height:1; border-radius:50%; ${args->plus_style:html:input_type(css):input_props('with_responsive=1'):arg_name(Button style):arg_section(10, 4, 'Button', 'hand-pointer-o')}">${args->button_add_plus:arg_name(Icon text):arg_section(10, 2, 'Button', 'hand-pointer-o')}</div>
							${args->button_add_text:arg_name(Button text):arg_section(10, 1, 'Button', 'hand-pointer-o')}
						</a>
					</div>
				</td>
			${end}
		</tr>
	</table>
	${block->pagination:arg_name(With slider pagination):arg_section(1, 10, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}
	<div id="tsp" class="$table_slider_pagination" slider_id="ts" selected_color="${args->pagination_color_on:html:input_type(color):arg_name(Bullet Selected Color):arg_section(1, 11, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" style="${args->pagination_color:html:input_type(css):arg_name(Bullet style):arg_section(1, 12, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}"></div>
</div>
```


## Social Proofing - Counters



```
<div id=st_w class="$responsive" data-style="display:inline-block; position:relative; ${args->style:html:default('padding: 15px;
text-align: left;
font-weight: bold;
font-size: 16px;
box-sizing: border-box;
width: 190px;
font-family: Roboto,sans-serif;
box-shadow: 0 0px 0px 0 rgba(0,0,0,0.08);
background-color: #333333;
margin-top: 00px;
margin-right: 0px;
margin-bottom: 1px;
margin-left: 0px;
color: rgb(255, 256, 256);
border-top-left-radius: 0px;
border-top-right-radius: 30px;
border-bottom-right-radius: 30px;
border-bottom-left-radius: 0px;
line-height: 20px;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(0, 1, 'Frame', 'th-large')}" onupdate="
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
	${block->title:default(1):arg_name(With title bar):arg_section(2, 0, 'Title', 'bookmark')}
	<table data-style="width:98%; margin-right: 1%; margin-left: 1%; border-collapse:collapse; border:none; ${args->title_bg:html:default('background-color: rgba(0, 0, 0, 0);
margin-top: 0px;
margin-right: 0;
margin-bottom: 0px;
padding-top: 0px;
padding-right: 0;
padding-bottom: 0px;
padding-left: 0;
border-bottom: none;'):input_type(css):input_props('with_responsive=1'):arg_name(Style):arg_section(2, 2, 'Title', 'bookmark')}">
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
color: #FAC200;'):input_type(css):input_props('with_responsive=1'):arg_name(Title style):arg_section(2, 3, 'Title', 'bookmark')}">
				${args->title:arg_name(Text):arg_section(2, 1, 'Title', 'bookmark')}
			</td>
			${block->with_arrows:default(0):arg_name(With arrow buttons):arg_section(1, 0, 'With slider', 'arrow-right')}
			<td style="width:1px; white-space:nowrap; vertical-align:middle">
				<a id="button_back" class="$flat_btn" style="${args->btn_style:html:input_type(css):arg_name(Arrow button style):arg_section(1, 1, 'With slider', 'arrow-right')}" hover_style="${args->btn_hover_style:html:input_type(css):arg_name('Arrow button style: hover'):arg_section(1, 2, 'With slider', 'arrow-right')}"><</a>
				<a id="button_forward" class="$flat_btn" style="${args->btn_style:html}" hover_style="${args->btn_hover_style:html}">></a>
			</td>
			${block->x:default(1):arg_name(With close button):arg_section(3, 0, 'Close button', 'close')}
			<td style="width:1px; white-space:nowrap; ${args->x_style:html:input_type(css):arg_name(Close button position):arg_section(3, 2, 'Close button', 'close')}">
				${args->x:default('<a href="javascript:" style="font-size: 18px; color: rgb(253, 253, 253); font-weight: bold; line-height: 1; text-decoration: none;" class="$personyze_button_dont_show_again" data-action_id="${action_id}">×</a>'):input_type(dontshowagain):input_props('style=cursor:pointer; vertical-align:middle'):arg_name(Close button):arg_section(3, 1, 'Close button', 'close')}
			</td>
		</tr>
	</table>
	<table style="width:100%; border-collapse:separate; border-spacing:12px 0">
		<tr id="ts" class="$table_slider" data-disabled="${args->with_slider:html:default(1):input_type(checkbox):input_props('value_off=1','value_on='):arg_name(Use slider widget):arg_section(1, 4, 'With slider', 'arrow-right'):onchange('if (args.with_slider==1) block.with_arrows = block.pagination = 0')}" style="width: 100%; padding: 0 1%; box-sizing: border-box; border:none; max-width:${args->width:html:default(none):input_type(css_length):input_props('with_options=none'):arg_name(Widget maximum width):arg_section(0, 0, 'Frame', 'th-large')}" for_max_vw="${args->for_max_vw:html:input_type(css_length):input_props('with_options=always'):arg_name(Slider widget only if screen width is less than or equal to):arg_section(1, 5, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" eq_cell_width="${args->eq_cell_width:html:default(1):input_type(checkbox):input_props('value_off=','value_on=1'):arg_name(Equal cell width):arg_section(0, 2, 'Frame', 'th-large')}" arrows_line="${args->arrows_line:html:input_type(checkbox):input_props('value_off=-1','value_on=0'):arg_name(Arrows in the middle of images):arg_section(1, 9, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" arrow_back_img="${args->arrow_back_img:html:input_type(personyze_media_url):arg_name(Left arrow image):arg_section(1, 6, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" arrow_style="${args->arrow_style:html:input_type(css):arg_name(Arrows style):arg_section(1, 7, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" pagination_id="tsp" arrow_back_id="button_back" arrow_forward_id="button_forward" arrows_offset="${args->arrows_offset:html:input_type(number):arg_name(Slider arrows offset):arg_section(1, 8, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" hide_buttons="${args->hide_buttons:html:input_type(checkbox):input_props('value_off=','value_on=1'):arg_name(Hide arrow buttons when nothing to scroll):arg_section(1, 3, 'With slider', 'arrow-right'):visible_if('block.title-0 && block.with_arrows-0')}">
			${foreach products_interactions as p where p->interaction_status in ('viewed','extra','favorite') order by p->interaction_time desc limit 1}
				<td style="position:relative; padding:0; text-align:center; vertical-align:top; border:solid ${args->border_color:html:default('rgba(178, 32, 32, 0)'):input_type(color):arg_name(Border color):arg_section(0, 4, 'Frame', 'th-large')} 1px">
					${block->img:default(0):arg_name(With image):arg_section(4, 0, 'Image', 'image')}
					<a data-personyze-click-target="products ${p->internal_id:html}" href="${p->cart_url:html:arg_name(Link target URL):arg_section(6, 0, 'Link target URL', 'link'):column_tags('url','custom text')}" target="${args->target:html:default(_self):input_type(a_target):arg_name(Open link in):arg_section(6, 1, 'Link target URL', 'link')}" data-style="display:block; margin:auto; box-sizing:border-box; width:${args->img_width:html:default('sel(0px, 0vw)'):input_type(css_length):input_props('with_responsive=1'):arg_name(Cell width):arg_section(0, 3, 'Frame', 'th-large')}">
						<img src="${p->image_big_url:html:arg_name(Item image):arg_section(4, 1, 'Image', 'image'):column_tags(image)}" data-style="width:auto; height:auto; max-width:100%; max-height:${args->img_max_height:html:input_type(css_length):input_props('with_responsive=1'):arg_name(Image maximum height):arg_section(0, 5, 'Frame', 'th-large')}">
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
background-color: rgba(29, 17, 17, 0);'):input_type(css):input_props('with_responsive=1'):arg_name(Text color):arg_section(5, 3, 'Text', 'align-justify')}">
							${p->age_to:arg_name(Item text):arg_section(5, 1, 'Text', 'align-justify')}
						</div>
					</div>
					${block->rating:default(0):arg_name(With rating):arg_section(7, 0, 'Rating', 'star')}
					<div style="margin: auto; margin-bottom: .6em; line-height: 12px">
						<div style="width: 69px; height: 13px; font-size: 0; line-height: 0; background: url(https://skin.christys-hats.com/frontend/ultimo/totalRecall/images/img/rating.png) 0 0 repeat-x; text-indent: -999em; overflow: hidden; margin-left: 0; margin-right: 0; display: inline-block; vertical-align: middle;">
							<div style="float: left; height: 13px; background: url(https://skin.christys-hats.com/frontend/ultimo/totalRecall/images/img/rating.png) 0 100% repeat-x; width: ${p->rank:html:default(0):arg_name(Rating):arg_section(7, 1, 'Rating', 'star')}%">
							</div>
						</div>
					</div>
					<div style="clear:left;"></div>

					${block->n_viewed:default(1):arg_name(With site statistics):arg_section(8, 0, 'Site statistics: week', 'bar-chart')}
					<div>
						${foreach sum_products_week as s where s->internal_id = p->internal_id limit 1}
							${block->hide_no_view:default(0):arg_name(Hide the widget if no views):arg_section(8, 2, 'Site statistics: week', 'bar-chart')}
							<span ontplready="if ('${s->n_viewed:html}' == 0) _S_T.dismiss_action(${action_id:html})"></span>
							${block->hide_no_goal:default(1):arg_name(Hide the widget if no purchases):arg_section(8, 3, 'Site statistics: week', 'bar-chart')}
							<span ontplready="if ('${s->n_goal:html}' == 0) _S_T.dismiss_action(${action_id:html})"></span>
							${args->n_viewed_text:default('<span style="font-size:14px;">Good choice! This product has been popular in the last week!</span><br />
&nbsp;
<div><span style="color:#fac200;"><strong>${s->n_viewed} viewed</strong></span></div>

<div><span style="color:#fac200;"><strong>${s->n_goal} purchased</strong></span></div>
'):arg_name(Text):arg_section(8, 1, 'Site statistics: week', 'bar-chart')}
						${end}
					</div>

					${block->price:default(0):arg_name(With price):arg_section(9, 0, 'Price', 'dollar')}
					<div data-style="margin:auto; box-sizing:border-box; width:${args->img_width:html}; ${args->price_style:html:input_type(css):input_props('with_responsive=1'):arg_name(Price style):arg_section(9, 5, 'Price', 'dollar')}">
						${if p->price}
							${args->before_price:arg_name(Text before price):arg_section(9, 1, 'Price', 'dollar')}
							${if p->sale_price and p->sale_price < p->price}
								${p->sale_price:truncate(2):sprintf($%s):arg_name(Price):arg_section(9, 6, 'Price', 'dollar')}
								<div style="${args->sale_style:html:input_type(css):input_props('with_responsive=1'):arg_name('Price before discount: style'):arg_section(9, 3, 'Price', 'dollar')}">
									${p->price:truncate(2):sprintf($%s):arg_name(Price):arg_section(9, 2, 'Price', 'dollar')}
								</div>
							${end}
							${if not p->sale_price or p->sale_price >= p->price}
								${p->price:truncate(2):sprintf($%s)}
							${end}
							${args->after_price:arg_name(Text after price):arg_section(9, 4, 'Price', 'dollar')}
						${end}
					</div>
					<div style="margin:auto; box-sizing:border-box; font-size:1px">
						<div data-style="display:inline-block; background-color:${args->border_color:html}; ${args->a_css_2:html:default('width:100px; height:3px; max-width:80%'):input_type(css):input_props('with_responsive=1'):arg_name(Ruler):arg_section(5, 5, 'Text', 'align-justify')}"></div>
					</div>
					${block->description:default(0):arg_name(With description):arg_section(5, 0, 'Text', 'align-justify')}
					<div data-style="margin:auto; box-sizing:border-box; width:${args->img_width:html}">
						<div data-style="display:inline-block; ${args->a_css_3:html:input_type(css):input_props('with_responsive=1'):arg_name(Text color):arg_section(5, 4, 'Text', 'align-justify')}; padding-bottom:0">
							${p->description:arg_name(Item text):arg_section(5, 2, 'Text', 'align-justify')}
						</div>
					</div>
					${block->button:default(0):arg_name(With button):arg_section(10, 0, 'Button', 'hand-pointer-o')}
					<div data-style="${args->button_spacer:html:input_type(css):input_props('with_responsive=1'):arg_name(Button reserved space):arg_section(10, 5, 'Button', 'hand-pointer-o')}">
						<a data-personyze-click-target="products ${p->internal_id:html}" href="${p->cart_url:html}" target="${args->target:html}" data-style="display:block; box-sizing:border-box; position:absolute; width:100%; height:0; display:none; left:0; bottom:0; ${args->a_css_4:html:input_type(css):input_props('with_responsive=1'):arg_name(Button style):arg_section(10, 3, 'Button', 'hand-pointer-o')}" ontplready="
							var a=ns.new_elem(this), p=this.parentNode.parentNode;
							p.onmouseenter = p.onmouseleave = function(e)
							{	var on = e.type == 'mouseenter';
								a.add_style({height: on ? 'auto' : '0', display: on ? '' : 'none'}, {});
							};
						">
							<div style="display:inline-block; width:1em; height:1em; line-height:1; border-radius:50%; ${args->plus_style:html:input_type(css):input_props('with_responsive=1'):arg_name(Button style):arg_section(10, 4, 'Button', 'hand-pointer-o')}">${args->button_add_plus:arg_name(Icon text):arg_section(10, 2, 'Button', 'hand-pointer-o')}</div>
							${args->button_add_text:arg_name(Button text):arg_section(10, 1, 'Button', 'hand-pointer-o')}
						</a>
					</div>
				</td>
			${end}
		</tr>
	</table>
	${block->pagination:arg_name(With slider pagination):arg_section(1, 10, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}
	<div id="tsp" class="$table_slider_pagination" slider_id="ts" selected_color="${args->pagination_color_on:html:input_type(color):arg_name(Bullet Selected Color):arg_section(1, 11, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}" style="${args->pagination_color:html:input_type(css):arg_name(Bullet style):arg_section(1, 12, 'With slider', 'arrow-right'):visible_if('args.with_slider!=1')}"></div>
</div>
```


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


## Buy together slider

This widget can work only on the product page. The quick add to cart button need to be configured in account "Add to cart:" setting 

```
<div class="$responsive $a_add_params" data-json-params="${args->url_params:html}" data-style="display:block; position:relative; ${args->style:html:default('padding-right: 0px;
padding-left: 0px;
border: none;
text-align: left;
font-weight: 400;
font-size: 18px;
box-sizing: border-box;
width: sel(auto, auto);
background-color: white;
margin-top: 10px;
margin-right: 0px;
margin-bottom: 2px;
margin-left: 0px;
min-width: 98%;
')}">
	${block->title:default(1)}
	<table data-style="width:100%; border-collapse:collapse; border:none; ${args->title_bg:html:default('background-color: rgb(75, 103, 129);
margin: 0px;
padding-top: 0px;
padding-right: 0;
padding-bottom: 0px;
padding-left: 0;
border-bottom: solid 1px #eaeaea;')}">
		<tr>
			<td data-style="vertical-align:middle; ${args->title_style:html:default('text-align: left;
font-family: Roboto, Sans-Serif;
padding: 15px;
font-weight: 500;
font-size: 18px;
line-height: 1.2222em;
text-transform: capitalize;
color: rgb(3, 1, 1);
background-color: #ffffff;
')}">
				${args->title:default(Buy together)}
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
	<style>
		@media (max-width: 799px)
		{	.st_flex_wrap_nar {flex-wrap:wrap}
			.st_flex_wrap_nar a[data-personyze-click-target] > img {max-width:40vw !important}
		}
	</style>
	<table style="width:100%; border-collapse:separate; border-spacing:8px 0; margin-bottom:1.2em">
		<tr id="st_ts" class="$table_slider" data-disabled="${args->with_slider:html}" data-round="${args->round:html:default(1)}" data-with_scrollbar="${args->with_scrollbar:html}" data-scrollbar_style="${args->scrollbar_style:html:default('background-color: #D8D8D8;
color: #999999;
height: 12px;
')}" data-hide_scrollbar="${args->hide_scrollbar:html}" style="margin-top:20px; width: 100%; padding: 0; box-sizing: border-box; border:none; max-width:${args->width:html:default(none)}" for_max_vw="${args->for_max_vw:html:default(0)}" eq_cell_width="${args->eq_cell_width:html:default(1)}" arrows_line="${args->arrows_line:html:default(-1)}" arrow_back_img="${args->arrow_back_img:html:default('<svg viewBox="0 0 54 54" width="24" height="24"><path style="fill:#4FBA6F" d="M27,1L27,1c14.359,0,26,11.641,26,26v0c0,14.359-11.641,26-26,26h0C12.641,53,1,41.359,1,27v0 C1,12.641,12.641,1,27,1z"/><path style="fill:#4FBA6F" d="M27,54C12.112,54,0,41.888,0,27S12.112,0,27,0s27,12.112,27,27S41.888,54,27,54z M27,2 C13.215,2,2,13.215,2,27s11.215,25,25,25s25-11.215,25-25S40.785,2,27,2z"/><path style="fill:#FFFFFF" d="M31.706,40c-0.256,0-0.512-0.098-0.707-0.293L19.501,28.209c-0.667-0.667-0.667-1.751,0-2.418 l11.498-11.498c0.391-0.391,1.023-0.391,1.414,0s0.391,1.023,0,1.414L21.12,27l11.293,11.293c0.391,0.391,0.391,1.023,0,1.414 C32.218,39.902,31.962,40,31.706,40z"/></svg>')}" arrow_style="${args->arrow_style:html:default('background-color: rgb(239, 231, 231);
box-shadow: 0px 1px 6px -1px rgba(0, 0, 0, .3);
')}" pagination_id="st_tsp" arrow_back_id="button_back" arrow_forward_id="button_forward" arrows_offset="${args->arrows_offset:html}" hide_buttons="${args->hide_buttons:html}">
			${foreach products as p where (p->image_big_url IS NOT NULL AND p->image_big_url!='') order by p->time_created desc limit 12}
				<td style="padding:0; background-color:white; border:solid ${args->border_color:html:default('rgba(178, 32, 32, 0)')} 1px">
					<div class="st_flex_wrap_nar" style="display:flex; height:100%">
						${foreach products_interactions as c where c->last_interaction_time >= tm order by c->last_interaction_time desc limit 1}
							<table style="height:100%; border-collapse:separate; border-spacing:12px 0">
								<tr>
									<td>
										<a data-personyze-click-target="products ${c->internal_id:html}" href="${c->cart_url:html}" target="${args->target:html:default(_self)}" data-style="display:block; margin:auto; box-sizing:border-box; width:${args->img_width:html:default(150px)}">
											<img src="${c->image_big_url:html}" data-style="width:auto; height:auto; max-width:100%; max-height:${args->img_max_height:html:default(130px)}">
										</a>
									</td>

<td>
<div style="top:50%; left:-0.8em; width:1em; height:1em; line-height:1em; margin-top:-0.5em; text-align: center; ${args->plus_style:html:default('color: gray;
font-size: 20px;
')}">+</div>
</td>
									<td style="position:relative">
										<a data-personyze-click-target="products ${p->internal_id:html}" href="${p->cart_url:html}" target="${args->target:html}" data-style="display:block; margin:auto; box-sizing:border-box; width:${args->img_width:html}">
											<img src="${p->image_big_url:html}" data-style="width:auto; height:auto; max-width:100%; max-height:${args->img_max_height:html}">
										</a>

									</td>
								</tr>
								<tr>
									<td style="vertical-align:top;">
										<div data-style="margin:auto; box-sizing:border-box; width:${args->img_width:html}">
											<div data-style="${args->a_css:html:default('margin-bottom: 10px;
text-transform: none;
vertical-align: top;
color: #333;
font-family: Roboto,sans-serif;
font-size: 16px;
line-height: 1.6em;
text-align: left;
overflow: hidden;
text-overflow: ellipsis;
display: -webkit-box;
-webkit-box-orient: vertical;
-webkit-line-clamp: 3;
max-height: 4.8em;
')}">
												${c->title}
											</div>
										</div>
									</td>

<td>

</td>
									<td style="vertical-align:top;">
										<div data-style="margin:auto; box-sizing:border-box; width:${args->img_width:html}">
											<div class="perso" data-style="${args->a_css:html}">										${p->title}
											</div>
										</div>
									</td>
								</tr>
								<tr>
									<td style="vertical-align:top;">
										${block->price:default(1)}
										<div class="st_price" data-style="margin:auto; box-sizing:border-box; width:${args->img_width:html}; ${args->price_style:html:default('color: #d32f2f;
font-size: 16px;
font-weight: 500;
text-align: start;
vertical-align: top;
display: block;
')}">
											${if c->price_after_discount}
												${args->before_price}
												${c->price_after_discount:truncate(3):sprintf('%s')}
												${args->after_price}
												${if c->custom_1}
													<span style="${args->sale_style:html:default('color: #333;
text-decoration: line-through;
font-size: 85%;
display: block;
font-weight: 400;
')}">
														${c->custom_1:truncate('3'):sprintf('%s KD')}
													</span>
												${end}
											${end}
										</div>
										${block->description:default(0)}
										<div data-style="margin:auto; box-sizing:border-box; width:${args->img_width:html}">
											<div data-style="display:inline-block; ${args->a_css_3:html}; padding-bottom:0">
												${c->description}
											</div>
										</div>
									</td>

<td></td>
									<td style="vertical-align:top;">
										${block->price:default(1)}
										<div data-style="margin:auto; box-sizing:border-box; width:${args->img_width:html}; ${args->price_style:html}">
											${if p->price_after_discount}
												${args->before_price}
												${p->price_after_discount:truncate(3):sprintf('%s $')}
												${args->after_price}
												${if p->custom_1}
													<span style="${args->sale_style:html}">
														${p->custom_1:truncate(3):sprintf('%s $')}
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
									</td>
								</tr>
							</table>
							<div style="${args->total_price_style:html:default('white-space: nowrap;
font-size: 13px;
font-weight: bold;
color: #333;
padding-top: 24px;
padding-right: 1px;
padding-bottom: 1px;
padding-left: 25px;
text-align: left;
')}">
								${args->total_price:default('Total:')}
								<span style="${args->total_price_n_style:html:default('font-size: 18px;
font-weight: normal;
')}" ontplready='
									var pp=this.dataset.price-0, ps=this.dataset.salePrice-0, cp=this.dataset.cPrice-0, cs=this.dataset.cSalePrice-0, sum=Math.round((Math.min(pp || Infinity, ps || Infinity) + Math.min(cp || Infinity, cs || Infinity))*1000)/1000, sum_before_sale=Math.round((Math.max(pp || 0, ps || 0) + Math.max(cp || 0, cs || 0))*1000)/1000;
									if (sum_before_sale == sum) sum_before_sale = 0;
									if (isFinite(sum))
									{	var fmt_e = this.parentNode.parentNode.parentNode.querySelector(".st_price");
										if (fmt_e)
										{	function text_l0(elem)
											{	var t = "";
												for (var e=elem.firstChild; e; e=e.nextSibling)
												{	if (e.nodeType == 3) t += e.data;
												}
												return t;
											}
											var d, fmt = text_l0(fmt_e).trim().replace(/[\d,]+\.(\d+)/, function(a, m) {d=m.length; return "~`"});
											if (d)
											{	sum = fmt.replace("~`", sum.toFixed(d));
												sum_before_sale = sum_before_sale &amp;&amp; fmt.replace("~`", sum_before_sale.toFixed(d));
											}
										}
										this.children[0].textContent = sum;
										if (sum_before_sale) this.children[1].textContent = sum_before_sale;
									}
								' data-price="${p->price_after_discount:html}" data-sale-price="${p->custom_1:html}" data-c-price="${c->price_after_discount:html}" data-c-sale-price="${c->custom_1:html}">
									<span></span>
									<span style="${args->sale_style:html}; ${args->total_sale_style:html}"></span>
								</span>
								<div>
									<button class="$flat_btn" style="${args->add_btn_style:html:default('padding: 8px;
outline: none;
border: none;
font-size: 13px;
font-weight: normal;
border-radius: 3px;
white-space: nowrap;
color: white;
background-color: #789900;
text-align: center;
margin-top: 13px;
margin-right: 0px;
margin-bottom: 0px;
margin-left: 0px;
width: 110px;
')}" hover_style="${args->add_btn_hover_style:html:default('color: white;
background-color: #e67f15;;')}" data-added-msg="${args->added_msg:html:default(Product was added)}" onclick="
										var added_msg=this.dataset.addedMsg, list=[], a = this.parentNode.parentNode.parentNode.querySelectorAll('a[data-personyze-click-target]');
										for (var i=0; i!=a.length; i++)
										{	list[i] = {pid: a[i].dataset.personyzeClickTarget.replace(/^\w+\s+/, ''), href: a[i].href};
										}
										new Function('list', this.dataset.js).call(this, list);
									"
									data-js="${args->js:html:default('for (var i=0; i!=list.length; i++)
{	var rec = list[i];
personyze.push([''Product Added to cart'', rec.pid, ''action_id'', ${action_id}]);
addToCart(''https://''+location.hostname+''/checkout/cart/add/uenc/''+btoa(rec.href)+''/product/''+rec.pid+''/form_key/GeqOmF0Go43U0pMh/'', ''crt'', rec.pid);
}')}">
										${args->add_btn_text:default(Add all to cart)}
									</button>
								</div>
							</div>
						${end}
					</div>
				</td>
			${end}
		</tr>
	</table>
	${block->pagination:default(0)}
	<div id="st_tsp" class="$table_slider_pagination" slider_id="st_ts" selected_color="${args->pagination_color_on:html:default('rgb(102, 125, 84)')}" style="${args->pagination_color:html}"></div>
</div>

${menu name='Frame', icon='th-large'}
	${menu args->width name='Widget maximum width', type='css_length', param='with_options=none'}
	${menu args->style name='Style', type='css', param='with_responsive=1'}
	${menu args->eq_cell_width name='Equal cell width', type='checkbox', param='value_off=', param='value_on=1'}
	${menu args->round name='No cut cell', type='checkbox', param='value_off=', param='value_on=1'}
	${menu args->img_width name='Cell width', type='css_length', param='with_responsive=1'}
	${menu args->border_color name='Border color', type='color'}
	${menu args->img_max_height name='Image maximum height', type='css_length', param='with_responsive=1'}
	${menu args->url_params name='URL additional parameters', type='external_media_url_params'}
${menu name='With slider', icon='arrow-right'}
	${menu block->with_arrows name='With arrow buttons'}
	${menu args->btn_style name='Arrow button style', type='css'}
	${menu args->btn_hover_style name='Arrow button style: hover', type='css'}
	${menu args->hide_buttons name='Hide arrow buttons when nothing to scroll', type='checkbox', param='value_off=', param='value_on=1'}
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
	${menu c->image_big_url name='Item image', column_tags='image'}
	${menu p->image_big_url name='Item image', column_tags='image'}
${menu name='Text', icon='align-justify'}
	${menu block->description name='With description'}
	${menu c->title name='Item text'}
	${menu p->title name='Item text'}
	${menu c->description name='Item text'}
	${menu p->description name='Item text'}
	${menu args->a_css name='Text color', type='css', param='with_responsive=1'}
	${menu args->a_css_3 name='Text color', type='css', param='with_responsive=1'}
${menu name='Link target URL', icon='link'}
	${menu c->cart_url name='Link target URL', column_tags='url, custom text'}
	${menu p->cart_url name='Link target URL', column_tags='url, custom text'}
	${menu args->target name='Open link in', type='a_target'}
${menu name='Price', icon='dollar'}
	${menu block->price name='With price'}
	${menu args->price_style name='Price style', type='css', param='with_responsive=1'}
	${menu args->total_price name='Total Price Text'}
	${menu args->total_price_style name='Total Price style', type='css'}
	${menu args->total_price_n_style name='Total Price Number style', type='css'}
	${menu args->total_sale_style name='Total price before discount style', type='css', param='with_responsive=1'}
${menu name='Plus sign', icon='plus'}
	${menu args->plus_style name='Plus sign style', type='css'}
${menu name='Add to cart button', icon='mouse-pointer'}
	${menu args->add_btn_text name='Text'}
	${menu args->add_btn_style name='Button style', type='css'}
	${menu args->before_price name='Text before price'}
	${menu args->add_btn_hover_style name='Button style: hover', type='css'}
	${menu c->price_after_discount:truncate(3):sprintf('%s') name='Price'}
	${menu p->price_after_discount:truncate(3):sprintf('%s $') name='Price'}
	${menu args->added_msg name='Text when Added to Cart'}
	${menu args->after_price name='Text after price'}
	${menu args->js name='Add button Javascript Action', type='source_javascript'}
	${menu c->custom_1:truncate('3'):sprintf('%s KD') name='Price'}
	${menu p->custom_1:truncate(3):sprintf('%s $') name='Price'}
	${menu args->sale_style name='Price before discount: style', type='css', param='with_responsive=1'}
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
margin: 19px;
font-family: "Heebo", sans-serif;
line-height: 29px;
')}">
	${block->title:default(1)}
	<table data-style="width:100%; border-collapse:collapse; border:none; ${args->title_bg:html:default('margin-top: 0px;
margin-right: 0px;
margin-bottom: 19px;
margin-left: 0px;')}">
		<tr>
			<td data-style="vertical-align:middle; ${args->title_style:html:default('font-size: sel(24px, 16px);
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
width: 100%;
')}">
				${args->title:default(Usually bought together)}
			</td>
			${block->x:default(0)}
			<td style="width:1px; white-space:nowrap; ${args->x_style:html}">
				${args->x}
			</td>
		</tr>
	</table>
	<style>
		/* + between products */
		.st_t .st_plus {display: none !important}
		.st_t td.st_vis ~ td .st_plus {display: block !important}

		tr > td > span.st_th {display: block !important}
		tr + tr + tr > td > span.st_th {display: none !important}
	</style>
	${block->with_table_border:default(0)}
	<style>
		/* round border table */
		.st_f
		{	border: 2px solid #DDDDDD;
			border-left: 0;
			border-radius: 6px;
		}
		.st_f > * > * > *
		{	padding: 1em !important;
			border-top: 2px solid #DDDDDD !important;
			border-left: 2px solid #DDDDDD !important;
		}
		.st_f > *:first-child > *:first-child > * {border-top: 0 !important}
		.st_f > *:first-child > *:first-child > *:first-child {border-top-left-radius: 6px !important}
		.st_f > *:first-child > *:first-child > *:last-child {border-top-right-radius: 6px !important}
		.st_f > *:last-child > *:last-child > *:first-child {border-bottom-left-radius: 6px !important}
		.st_f > *:last-child > *:last-child > *:last-child {border-bottom-right-radius: 6px !important}
	</style>
	<script ontplready="
		window._s_t_numfmt = function(v)
		{	try
			{	var locale = new Intl.Locale(${args->num_locale:json:html:default(en)});
			}
			catch (e)
			{	locale = new Intl.Locale('en-US');
			}
			var fmt = ${args->num_frac:json:html:default(3)};
			return new Intl.NumberFormat(locale, {minimumFractionDigits: Number.isInteger(v) ? 0 : fmt, maximumFractionDigits: fmt}).format(v);
		};
	"></script>
	<div style="display:flex; flex-wrap:wrap; ${args->flex_style:html:default('align-items: flex-start;
justify-content: flex-start;
')}">
		<table id="st_t" class="st_t" style="width:100%; border-collapse:collapse; border:none">
			<tr class="$table_slider" data-disabled="${args->with_slider:html:default(1)}" style="border:none; max-width:${args->width:html:default(98vw)}">
				${foreach products_interactions as c where c->last_interaction_time >= tm order by c->last_interaction_time desc limit 1}
					<td data-style="position:relative; ${args->td_style:html:default('text-align: center;
vertical-align: middle;
padding: sel(5px, 0);
border: none;
')}">
						<span>
							<input class="st_internal_id" type="hidden" value="${c->internal_id:html}" data-json-add_to_cart_columns="${c->add_to_cart_columns:html}">
							<a data-personyze-click-target="products ${c->internal_id:html}" href="${c->cart_url:html}" target="${args->target:html:default(_self)}" style="${args->c_link_style:html:default('color: rgb(41, 24, 24);
text-decoration: none;
max-width: 79px;
font-weight: bold;
')}">
								<img src="${c->image_big_url:html}" data-style="${args->main_img_style:html:default('border: double rgb(116, 176, 105) 0px;
width: sel(auto, auto);
height: sel(auto, auto);
max-width: sel(130px, 20vw);
max-height: 200px;
padding-top: sel(15px, );
padding-right: sel(15px, 0);
padding-bottom: sel(15px, 0);
padding-left: sel(15px, 0);
')}" onerror="this.parentNode.parentNode.style.display='none'" alt="${c->title:html:ellipsis(90):html}">
							</a>
						</span>

						<a class="st_title" data-personyze-click-target="products ${c->internal_id:html}" href="${c->cart_url:html}" target="${args->target:html}" style="${args->c_link_style:html}; display:${args->with_product_name:html:default(none)}">
							${c->title:ellipsis(90)}
						</a>

						<div class="st_price" data-price="${c->price_after_discount:html}" data-price-crazy="${c->price_before_discount:html}" style="display:${args->with_price:html:default(none)}; ${args->price_style:html:default('margin-top: 0.4em;
color: #d00;
')}">
							${if c->price_after_discount}
								${if c->price_after_discount >= c->price_before_discount}
									<span style="white-space:nowrap; ${args->c_price_without_discount_style:html:default('color: #191919;
')}">
										${args->c_price_symbol_pre:default($)}<span ontplready="this.textContent = _s_t_numfmt(this.textContent)">${c->price_before_discount}</span>${args->c_price_symbol_post}
									</span>
								${else}
									${if c->price_after_discount = 0}
										${args->c_free:default(FREE)}
									${else}
										<span style="white-space:nowrap; ${args->c_price_after_discount_style:html:default('color: rgb(40, 121, 254);
')}">
											${args->c_discount_text:default('<span style="display:inline-block; font-size:50%; line-height:1; font-weight: 300; font-size:50%">Discounted<br />
price</span>')}
											${args->c_price_symbol_pre}<span ontplready="this.textContent = _s_t_numfmt(this.textContent)">${c->price_after_discount}</span>${args->c_price_symbol_post}
										</span>
										<span style="white-space:nowrap; ${args->c_price_before_discount_style:html:default('text-decoration: line-through;
color: rgb(75, 75, 75);
')}">
											${args->c_price_symbol_pre}<span ontplready="this.textContent = _s_t_numfmt(this.textContent)">${c->price_before_discount}</span>${args->c_price_symbol_post}
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

					${foreach products as main where (main->image_big_url IS NOT NULL AND main->image_big_url!='') order by main->time_created desc limit 2}
						<td data-style="position:relative; ${args->td_style:html}">
							<span>
								<div class="st_plus" style="position:absolute; top:50%; left:-0.5em; width:1em; height:1em; line-height:1em; margin-top:-0.5em; text-align: center; ${args->plus_style:html:default('color: #ff6700;
font-size: 26px;
margin-top: -29px;
margin-right: 7px;
margin-bottom: 0px;
margin-left: 0px;
')}">+</div>
								<input class="st_internal_id" type="hidden" value="${main->internal_id:html}" data-json-add_to_cart_columns="${main->add_to_cart_columns:html}">
								<a data-personyze-click-target="products ${main->internal_id:html}" href="${main->cart_url:html}" target="${args->target:html}" style="${args->link_style:html:default('color: rgb(41, 24, 24);
text-decoration: none;
max-width: 79px;
')}">
									<img src="${main->image_big_url:html}" data-style="${args->img_style:html:default('border: double rgb(235, 220, 220) 0px;
width: sel(auto, auto);
height: sel(auto, auto);
max-height: 100px;
max-width: sel(150px, 15vw);
padding-top: sel(10px, );
padding-right: sel(10px, 0);
padding-bottom: sel(10px, 0);
padding-left: sel(10px, 0);
')}" onerror="this.parentNode.parentNode.style.display='none'" alt="${main->title:html:ellipsis(90):html}">
								</a>
							</span>

							<a class="st_title" data-personyze-click-target="products ${main->internal_id:html}" href="${main->cart_url:html}" target="${args->target:html}" style="${args->link_style:html}; display:${args->with_product_name:html}">
								${main->title:ellipsis(90)}
							</a>

							<div class="st_price" data-price="${discount(main->prices, c->internal_id)}" data-price-crazy="${main->price_before_discount:html}" style="display:${args->with_price:html}; ${args->price_style:html}">
								${if main->price_after_discount}
									${if discount(main->prices, c->internal_id) >= main->price_before_discount}
										<span style="white-space:nowrap; ${args->price_without_discount_style:html:default('color: #191919;
')}">
											${args->c_price_symbol_pre}<span ontplready="this.textContent = _s_t_numfmt(this.textContent)">${main->price_before_discount}</span>${args->c_price_symbol_post}
										</span>
									${else}
										${if discount(main->prices, c->internal_id) = 0}
											${args->c_free}
										${else}
											<span style="white-space:nowrap; ${args->price_after_discount_style:html:default('color: rgb(40, 121, 254);
')}">
												${args->c_discount_text}
												${args->c_price_symbol_pre}<span ontplready="this.textContent = _s_t_numfmt(this.textContent)">${discount(main->prices, c->internal_id)}</span>${args->c_price_symbol_post}
											</span>
											<span style="white-space:nowrap; ${args->price_before_discount_style:html:default('text-decoration: line-through;
color: rgb(75, 75, 75);
')}">
												${args->c_price_symbol_pre}<span ontplready="this.textContent = _s_t_numfmt(this.textContent)">${main->price_before_discount}</span>${args->c_price_symbol_post}
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

				${end}
			</tr>
		</table>
		<div style="${args->tot_td_style:html:default('vertical-align: middle;
white-space: nowrap;
margin-top: 0em;
margin-right: 0em;
margin-bottom: 1em;
margin-left: 0em;
')}">
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
			<a href="javascript:" id="st_btn1" class="$flat_btn" style="${args->add_btn_style:html:default('font-weight: normal;
border-radius: 6px;
color: white;
background-color: rgb(40, 121, 254);
text-align: center;
margin-top: 13px;
margin-right: 11px;
margin-left: 11px;
text-decoration: none;
padding-top: 8px;
padding-right: 26px;
padding-bottom: 8px;
padding-left: 26px;
')}" hover_style="${args->add_btn_hover_style:html:default('font-weight: normal;
color: white;
background-color: #fc9234;
text-align: center;
text-decoration: none;
')}" onclick="
	var btn=this;
	btn._load_begin();
	personyze.add_to_cart(this._list, ${action_id:json:html}, ${args->js:json:html}).then
	(	function()
		{	btn._load_end();
			new Function(btn.dataset.yes).call(btn);
		},
		function()
		{	btn._load_end();
			new Function(btn.dataset.no).call(btn);
		}
	)
" data-yes="${args->cart_yes:html:default('location.href=location.href')}" data-no="${args->cart_no:html:default('new _S_T.ElemsAnnotator(''error'').add(this, ''Couldn\''t add this product. Please, try from the product page.'').annotate()')}">
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
background-color: rgba(119, 119, 119, 0.76);')}" data-added-msg="${args->added:html:default(Products added to wishlist)}">
					${args->fvt_btn_text:default('<span style="font-size:0px;">Add to wishlist</span>')}
				</button>
			</div>
		</div>
	</div>
	<table class="st_f" style="width:100%; border-collapse:separate; border-spacing:0; margin:5px" data-price-pre="${args->c_price_symbol_pre:html}" data-price-post="${args->c_price_symbol_post:html}" ontplready="
		var tr=by_id.st_tr, tbody=by_id.st_t.children[0], n=tbody.children[0].children.length, price_pre=this.dataset.pricePre, price_post=this.dataset.pricePost, add_to_cart_columns=[];
		if (tr) for (var i=0; i!=n; i++)
		{	tr.set_length(n);
			var t_by_id = tr[i].by_id;
			function gt(i, name)
			{	return ns.joyquery('td:nth-child('+(i+1)+') [class~=\'st_'+name+'\']', tbody).get(0);
			}
			var ii = gt(i, 'internal_id');
			try
			{	add_to_cart_columns[i] = JSON.parse(ii.getAttribute('data-json-add_to_cart_columns'));
			}
			catch (e)
			{
			}
			if (!add_to_cart_columns[i] || typeof(add_to_cart_columns[i])!='object') add_to_cart_columns[i] = {};
			add_to_cart_columns[i].internal_id = ii.value;
			t_by_id.st_for_internal_id.value = ii.value;
			var title = gt(i, 'title').cloneNode(true);
			title.style.display = '';
			if (i != 0) t_by_id.st_for_title.innerHTML = '';
			t_by_id.st_for_title.appendChild(title);
			var price = gt(i, 'price');
			t_by_id.st_for_price.innerHTML = price ? price.innerHTML : '';
			t_by_id.st_for_price.style.cssText = price ? price.style.cssText : '';
			t_by_id.st_for_price.style.display = '';
			function ch()
			{	var tot=0, tot_c=0, v, list=[], vis=0;
				for (var i=0; i!=tr.length; i++)
				{	var price = gt(i, 'price');
					var price_c = price ? parseFloat(price.dataset.priceCrazy) : NaN;
					price = price ? parseFloat(price.dataset.price) : NaN;
					if (isNaN(price)) return;
					var t_by_id = tr[i].by_id;
					v = t_by_id.st_for_internal_id.checked;
					if (v)
					{	tot += parseFloat(price);
						tot_c += parseFloat(price_c);
						list.push(add_to_cart_columns[i]);
						vis++;
					}
					for (var e, it=ns.joyquery('td:nth-child('+(i+1)+')', tbody); e=it();)
					{	e.className = v ? 'st_vis' : '';
						ns.new_elem(e).add_style({opacity: +v, display: v ? '' : 'none'}, {});
					}
				}
				by_id.st_tot.innerHTML = price_pre + _s_t_numfmt(tot) + price_post;
				by_id.st_tot_crazy.innerHTML = tot==tot_c ? '' : price_pre + _s_t_numfmt(tot_c) + price_post;
				by_id.st_btn1._list = list;
				by_id.st_btn1.style.display = vis ? 'block' : 'none';
				if (by_id.st_btn2) by_id.st_btn2.style.display = vis ? '' : 'none';
			}
			this.onclick = ch;
			setTimeout(ch, 0);

			if (by_id.st_btn2)
			{	by_id.st_btn2.onclick = function()
				{	var vis=0;
					for (var i=0; i!=tr.length; i++)
					{	var t_by_id = tr[i].by_id;
						if (t_by_id.st_for_internal_id.checked)
						{	ns.push(['Product Liked', t_by_id.st_for_internal_id.value]);
							vis++;
						}
					}
					if (vis)
					{	new ns.ElemsAnnotator('info').add(this, this.getAttribute('data-added-msg')).annotate(3000);
					}
				};
			}
		}
	">
		<tr id="st_tr" class="$repeat-elem">
			<td style="width:1px; vertical-align:top"><input id="st_for_internal_id" type="checkbox" checked="1"></td>
			<td style="padding:0 5px; vertical-align:top" id="st_for_title">
				${args->this_pr:default('<b>This product:</b>')}
			</td>
			<td id="st_for_price" style="vertical-align:top" onclick="this.previousElementSibling.onclick()"></td>
		</tr>
	</table>

</div>

${menu name='Frame', icon='th-large'}
	${menu args->width name='Widget maximum width', type='css_length', param='with_options=none'}
	${menu args->style name='Style', type='css', param='with_responsive=1'}
	${menu args->td_style name='Cell style', type='css', param='with_responsive=1'}
	${menu block->with_table_border name='With table border'}
	${menu args->flex_style name='Layout style', type='css'}
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
	${menu c->image_big_url name='Item image', column_tags='image'}
	${menu args->main_img_style name='Main image style', type='css', param='with_responsive=1'}
	${menu args->img_style name='Item image style', type='css', param='with_responsive=1'}
${menu name='Link target URL', icon='link'}
	${menu c->cart_url name='Link target URL', column_tags='url, custom text'}
	${menu args->target name='Open link in', type='a_target'}
${menu name='Product name', icon='text-height'}
	${menu args->with_product_name name='With product name', type='checkbox', param='value_off=none', param='value_on='}
	${menu c->title:html:ellipsis(90) name='Product name'}
	${menu c->title:ellipsis(90) name='Product name'}
	${menu args->c_link_style name='Link style (first item)', type='css'}
	${menu args->link_style name='Link style', type='css'}
${menu name='Price', icon='text-height'}
	${menu args->with_price name='With price', type='checkbox', param='value_off=none', param='value_on=block'}
	${menu args->num_locale name='Price locale'}
	${menu args->num_frac name='Price fractional digits', type='number'}
	${menu args->price_style name='Price style', type='css', visible_if='args.with_price!="none"'}
	${menu args->c_price_symbol_pre name='Price symbol before price'}
	${menu args->c_price_symbol_post name='Price symbol after price'}
	${menu args->c_free name='If free product'}
	${menu args->c_discount_text name='Discount text'}
	${menu args->c_price_without_discount_style name='Price without discount - Style (first item)', type='css'}
	${menu args->c_price_before_discount_style name='Price before discount - Style (first item)', type='css'}
	${menu args->c_price_after_discount_style name='Price after discount - Style (first item)', type='css'}
	${menu args->price_without_discount_style name='Price without discount - Style', type='css'}
	${menu args->price_before_discount_style name='Price before discount - Style', type='css'}
	${menu args->price_after_discount_style name='Price after discount - Style', type='css'}
	${menu args->this_pr name='"This product" text'}
${menu name='Rating', icon='star'}
	${menu block->rating name='With rating'}
	${menu c->rank name='Rating'}
	${menu args->rank_max name='Maximum rating number that corresponds to 100%', type='number'}
	${menu args->rating_style name='Rating block style', type='css'}
${menu name='Plus sign', icon='plus'}
	${menu args->plus_style name='Plus sign style', type='css'}
${menu name='Add to cart button', icon='mouse-pointer'}
	${menu args->add_btn_text name='Text'}
	${menu args->add_btn_style name='Button style', type='css'}
	${menu args->add_btn_hover_style name='Button style: hover', type='css'}
	${menu args->js name='Optional argument to pass to your Add to Cart implementation defined in product interactions settings'}
	${menu args->tot_text name='Total price text'}
	${menu args->tot_td_style name='Total price box style', type='css'}
	${menu args->tot_text_style name='Total price text style', type='css'}
	${menu args->tot_style name='Total price style', type='css'}
	${menu args->tot_crazy_style name='Total price before discount style', type='css'}
	${menu args->cart_yes name='Javascript on complete', type='source_javascript'}
	${menu args->cart_no name='Javascript on error', type='source_javascript'}
${menu name='Add to favorites', icon='heart'}
	${menu block->with_fav name='With Add to favorites'}
	${menu args->fvt_btn_text name='Text'}
	${menu args->fvt_btn_style name='Button style', type='css'}
	${menu args->fvt_btn_hover_style name='Button style: hover', type='css'}
	${menu args->added name='Added to wishlist message'}
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
${menu name='Product title', icon='align-justify'}
	${menu block->with_title name='With title'}
	${menu p->title name='Item text'}
	${menu args->title_max_lines name='Title max lines', type='number', param='min=1'}
${menu name='Product text/desc', icon='align-justify'}
	${menu block->description name='With description'}
	${menu p->description name='Item text'}
	${menu args->a_css name='Text style', type='css', param='with_responsive=1'}
	${menu args->a_hover_color name='Text on hover color', type='color'}
	${menu args->a_css_3 name='Text color', type='css', param='with_responsive=1'}
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


## With Hover shadow



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
				img.st-zoom:hover {transform: scale(calc(${args->img_zoom_on_hover:default(120)} / 100))}

				.st-hov:hover {color: ${args->a_hover_color:html:default('#3b3b3b')} !important}
			</style>

			${block->with_hover_image:default(0)}
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

			${block->with_hover_shadow:default(1)}
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
				<div data-style="flex-grow:1000; ${args->title_style:html:default('text-align: left;
font-size: sel(1.75rem, 18px);
font-weight: 700;
letter-spacing: 0.25px;
color: black;
padding-top: 0rem;
padding-right: 0;
padding-bottom: 3rem;
padding-left: 0;
')}">
					${args->title:default(Your title)}
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
						${foreach products as p order by p->time_created desc limit 12}
							<td style="position:relative; height:100%; padding:0; text-align:center; background-color:white; vertical-align:top; border:solid ${args->border_color:html:default(transparent)} 1px">
								<div style="display:block; overflow:visible; position:absolute; z-index:1; left:0; top:0; width:100%; height:var(--st-tab-rnd-height); pointer-events:none; transform:translate(0, 0)">
									<div class="st-tab-rnd-cell" style="${args->cell_border:html:default('box-shadow: 0 0.0714285714em 0.2142857143em 0 rgba(0,0,0,0.2)')}; position:fixed; left:0; top:0; width:100%; height:100%" ontplready="this.parentNode.parentNode.style.overflow='visible'"></div>
								</div>
								<div data-personyze-click-target="products ${p->internal_id:html}" onclick="for (let e=event.target; e &amp;&amp; e!=this; e=e.parentNode) if (e.nodeName == 'A') return; var a=_S_T.new_elem('a', this, {href: ${p->cart_url:json:html}, target: ${args->target:json:html:default(_blank)}, style: 'position:absolute; visibility:hidden'}); a.click(); setTimeout(function() {a.parentNode.removeChild(a)}, 100)" data-style="cursor:pointer; width:${args->img_width:html:default('sel(295px, 44vw)')}; height:100%; position:relative; overflow:hidden; box-sizing:border-box">
									<div data-style="position:relative; display:flex; width:100%; height:100%; max-width:100%; margin:auto; box-sizing:border-box; overflow:hidden; text-decoration:none; ${args->img_alignment:html:default('align-items: baseline;
		')}">
										<img class="st-zoom" data-src="${p->image_big_url:html}" data-style="margin:auto; width:auto; height:auto; max-width:100%; max-height:${args->img_max_height:html:default('sel(300px, 80vh)')}; border:none" alt="${p->title:html}">

										${if p->image_medium_url <> ''}
											${block->with_hover_image:default(0)}
											<div class="st-zoom-b" style="position:absolute; background-color:white; display:flex; left:0; top: 0; width:100%; height:100%; justify-content:center; ${args->img_alignment:html}">
												<img data-src="${p->image_medium_url:html}" data-style="width:auto; height:auto; max-width:100%; max-height:${args->img_max_height:html}; border:none" alt="${p->title:html}">
											</div>
										${end}
									</div>

									${block->with_sc:default(0)}
									<div class="$info_lines_scroller" data-without_close="${args->sc_without_close:html:default(1)}" data-no_dismiss_action="1" style="${args->sc_style:html:default('background-color: black;
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
										${foreach sum_products_week as s where s->internal_id = p->internal_id limit 1}
											${if s->n_viewed >= args->sc_min_views:json:html:default(50)}
												${block->sc_with_views}
												<div>
													<hr class="$icon ${args->sc_icon_views:html:default(user)}" style="${args->sc_icon_views_style:html:default('font-size: 100%;
')}">&nbsp;
													${args->sc_text_views:default('<strong>Trending now!</strong>&nbsp;${s->n_viewed}&nbsp;others have looked at this recently&nbsp;')}
												</div>
											${end}
											${if s->n_goal >= args->sc_min_goals:json:html:default(2)}
												${block->sc_with_goals}
												<div>
													<hr class="$icon ${args->sc_icon_goals:html:default(shopping-cart)}" style="${args->sc_icon_goals_style:html:default('font-size: 100%;
')}">&nbsp;
													${args->sc_text_goals:default('<strong>Popular!</strong> Sold ${s->n_goal}&nbsp;times recently')}
												</div>
											${end}
											${if p->inventory between 1 and args->sc_min_inventory:html:default(300)}
												${if s->n_goal >= args->sc_min_goals_for_inventory:json:html:default(0)}
													${block->sc_with_inventory}
													<div>
														<hr class="$icon ${args->sc_icon_inventory:html:default(redo)}" style="${args->sc_icon_inventory_style:html}">&nbsp;
														${args->sc_text_inventory:default('<strong>Only&nbsp;${p->inventory}&nbsp; </strong>left in stock!')}
													</div>
												${end}
											${end}
										${end}
										${if (p->prev_price - p->price_after_discount) * 100 / p->prev_price >= args->sc_min_price_drop:html:default(6)}
											${if p->time_price_changed >= unix_timestamp() - 24*60*60*args->sc_min_price_drop_days:html:default(500)}
												${block->sc_with_price_drop}
												<div ontplload="by_id.st_root._tr(this, n => {n.data = n.data.replace(/\{D\}/g, this.dataset.days).replace(/\{P\}/g, this.dataset.prc)})" data-days="${ceil(greatest(1, unix_timestamp() - p->time_price_changed) / (24*60*60))}" data-prc="${floor((p->prev_price - p->price_after_discount) * 100 / p->prev_price)}">
													<hr class="$icon ${args->sc_icon_price_drop:html:default(tag)}" style="${args->sc_icon_price_drop_style:html:default('font-size: 100%;
')}">&nbsp;
													${args->sc_text_price_drop:default('Price dropped by {P}% in last {D} days')}
												</div>
											${end}
										${end}
										${if (p->price_before_discount - p->price_after_discount) * 100 / p->price_before_discount >= args->sc_min_discount:html:default(1)}
											${block->sc_with_discount}
											<div ontplload="by_id.st_root._tr(this, n => {n.data = n.data.replace(/\{P\}/g, this.dataset.prc)})" data-prc="${floor((p->price_before_discount - p->price_after_discount) * 100 / p->price_before_discount)}">
												<hr class="$icon ${args->sc_icon_discount:html:default(tag)}" style="${args->sc_icon_discount_style:html:default('font-size: 100%;
')}">&nbsp;
												${args->sc_text_discount:default('<strong>Sale!</strong> {P}% discount')}
											</div>
										${end}
										${if p->time_created > unix_timestamp() - 24*60*60*args->sc_min_new_days:html:default(30)}
											${block->sc_with_new}
											<div ontplload="by_id.st_root._tr(this, n => {n.data = n.data.replace(/\{D\}/g, this.dataset.days)})" data-days="${ceil(greatest(1, unix_timestamp() - p->time_created) / (24*60*60))}">
												<hr class="$icon ${args->sc_icon_new:html:default(fire)}" style="${args->sc_icon_new_style:html:default('font-size: 100%;
')}">&nbsp;
												${args->sc_text_new:default('<strong>New in stock.</strong> Added before {D} days')}
											</div>
										${end}
										${block->sc_with_free1}
										<div>
											<hr class="$icon ${args->sc_icon_free1:html:default(fire)}" style="${args->sc_icon_free1_style:html:default('font-size: 100%;
')}">&nbsp;
											${args->sc_text_free1:default(Time limited special offer)}
										</div>
										${block->sc_with_free2}
										<div>
											<hr class="$icon ${args->sc_icon_free2:html:default(fire)}" style="${args->sc_icon_free2_style:html:default('font-size: 100%;
')}">&nbsp;
											${args->sc_text_free2:default(Time limited special offer2)}
										</div>
										${block->sc_with_free3}
										<div>
											<hr class="$icon ${args->sc_icon_free3:html:default(fire)}" style="${args->sc_icon_free3_style:html:default('font-size: 100%;
')}">&nbsp;
											${args->sc_text_free3:default(Time limited special offer3)}
										</div>
									</div>

									${block->with_discount_badge:default(1)}
									<span>
										${if p->discount_percent >= args->min_discount_percent:default(10)}
											<div data-style="position: absolute; ${args->discount_badge_style:html:default('top: 0;
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
												<span data-style="${args->discount_badge_text_style:html:default('line-height: 1.25;
font-size: 9px;
font-weight: 600;
')}">${args->discount_badge_text:default('<div style="font-size:14px">${p->discount_percent:floor}%</div>
Discount')}</span>
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
										${if p->inventory between 1 and args->badge_if_less_stock:default(300)}
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
font-size: 15px;
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
										${if s->n_viewed >= args->hide_no_view_week:default(3)}
											${if s->n_goal >= args->hide_no_goal_week:default(0)}
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
														${args->n_viewed_week:default('This product has been popular&nbsp;${s->n_viewed*1}&nbsp; views recently.
')}
													</div>
												${end}
												${if s->n_goal > 0}
													<div style="${args->text_style_week:html}">
														<hr class="$icon ${args->icon_n_goal_week:html:default(users)}" style="${args->icon_style_n_goal_week:html:default('padding-right: 0.5em;
font-size: 100%;
color: inherit;
')}">
														${args->n_goal_week:default('This product has been popular&nbsp;${s->n_goal}&nbsp; purchases recently.
')}
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
													${args->old_price_before}${args->p_price_before_discount:default('$${p->price_before_discount:price('''')}')}${args->old_price_after}
												</span>
											</span>
											<span style="white-space:nowrap">
												<span style="${args->new_price_style:html:default('font-size: 17px;
font-weight: 500;
color: black;
')}">
													${args->old_price_before)}${args->p_price_after_discount:default('$${p->price_after_discount:price('''')}')}${args->old_price_after}
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

								${block->rating:default(1)}
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

								${block->payment:default(1)}
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

								${block->with_link_button:default(1)}
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

								${block->with_cart:default(1)}
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

${menu name='Frame', icon='th-large'}
	${menu args->style name='Style', type='css', param='with_responsive=1'}
	${menu args->content_padding name='Content box padding', type='css', param='with_responsive=1'}
	${menu args->round name='No cut cell', type='checkbox', param='value_off=', param='value_on=1'}
	${menu args->eq_cell_width name='Equal cell width', type='checkbox', param='value_off=', param='value_on=1'}
	${menu args->eq_cell_height name='Equal cell height', type='checkbox', param='value_off=', param='value_on=1'}
	${menu args->space_between_items name='Space between items', type='css_length', param='with_responsive=1'}
	${menu args->border_color name='Border color', type='color'}
	${menu args->cell_border name='Shadow', type='css'}
	${menu args->round_border name='Round border', type='css_length'}
	${menu args->direction name='Localization settings', type='select', param='options=[["Left to right","ltr"],["Right to left","rtl"]]'}
	${menu args->url_params name='URL additional parameters', type='external_media_url_params'}
${menu name='Hover shadow', icon='clone'}
	${menu block->with_hover_shadow name='With hover shadow'}
	${menu args->hover_shadow name='Shadow', type='css'}
${menu name='Hover overlay', icon='mouse-pointer'}
	${menu block->with_hover_overlay name='With hover overlay'}
	${menu args->hover_overlay_style name='Style', type='css'}
	${menu args->hover_opacity name='Hover opacity', type='css'}
	${menu args->hover_overlay_text name='Text'}
	${menu block->with_hover_overlay_a name='With link 1'}
	${menu args->hover_overlay_a_block_style name='Link 1 block style', type='css'}
	${menu args->hover_overlay_a_text name='Link 1 text'}
	${menu args->hover_overlay_a_href name='Link 1 URL'}
	${menu args->hover_overlay_a_style name='Link 1 style', type='css'}
	${menu args->hover_overlay_a_style_hover name='Link 1 hover style', type='css'}
	${menu block->with_hover_overlay_a2 name='With link 2'}
	${menu args->hover_overlay_a2_block_style name='Link 2 block style', type='css'}
	${menu args->hover_overlay_a2_text name='Link 2 text'}
	${menu args->hover_overlay_a2_href name='Link 2 URL'}
	${menu args->hover_overlay_a2_style name='Link 2 style', type='css'}
	${menu args->hover_overlay_a2_style_hover name='Link 2 hover style', type='css'}
${menu name='Hover overlay from bottom', icon='mouse-pointer'}
	${menu block->with_ovy2 name='With hover overlay'}
	${menu args->hover_ovy2_shad_style name='Shadow', type='css'}
	${menu args->hover_ovy2_style name='Style', type='css'}
	${menu args->hover_ovy2_text name='Text'}
	${menu args->hover_ovy2_style2 name='Text style', type='css'}
	${menu block->with_hover_ovy2_a name='With link 1'}
	${menu args->hover_ovy2_a_block_style name='Link 1 block style', type='css'}
	${menu args->hover_ovy2_a_text name='Link 1 text'}
	${menu args->hover_ovy2_a_href name='Link 1 URL'}
	${menu args->hover_ovy2_a_style name='Link 1 style', type='css'}
	${menu args->hover_ovy2_a_style_hover name='Link 1 hover style', type='css'}
	${menu block->with_hover_ovy2_a2 name='With link 2'}
	${menu args->hover_ovy2_a2_block_style name='Link 2 block style', type='css'}
	${menu args->hover_ovy2_a2_text name='Link 2 text'}
	${menu args->hover_ovy2_a2_href name='Link 2 URL'}
	${menu args->hover_ovy2_a2_style name='Link 2 style', type='css'}
	${menu args->hover_ovy2_a2_style_hover name='Link 2 hover style', type='css'}
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
${menu name='Discount badge', icon='align-justify', description='Set discount badge to appear for a discounted product, you may choose to set it to show only if the discount is greater than X.'}
	${menu block->with_discount_badge name='With new badge'}
	${menu args->min_discount_percent name='Show discount badge if % ≥', type='number', param='min=1'}
	${menu args->discount_badge_style name='Badge style', type='css', param='with_responsive=1'}
	${menu args->discount_badge_text_style name='Badge text style', type='css', param='with_responsive=1'}
	${menu args->discount_badge_text name='Text'}
${menu name='Price drop badge', icon='tag'}
	${menu block->with_price_drop_badge name='With price drop badge'}
	${menu args->min_price_drop name='Show if drop percent at least', type='number', param='min=1'}
	${menu args->min_price_drop_days name='Show if drop was before N days or less', type='number', param='min=1'}
	${menu args->price_drop_badge_style name='Badge style', type='css', param='with_responsive=1'}
	${menu args->price_drop_badge_text_style name='Badge text style', type='css', param='with_responsive=1'}
	${menu args->text_price_drop name='Text. Use {P} for percent, and {D} for no. of days'}
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
	${menu args->db_badge_text name='Badge text'}
	${menu args->db_badge_text_style name='Badge text style', type='css'}
${menu name='Options link', icon='external-link'}
	${menu block->with_options_link name='With options link'}
	${menu args->options_link_href name='Link URL'}
	${menu args->options_link_style name='Link style', type='css'}
	${menu args->options_link_text name='Link text'}
${menu name='Custom column', icon='database', description='Select additional field to show.'}
	${menu block->with_custom_column name='With custom column'}
	${menu args->custom_column name='Date column'}
	${menu args->custom_column_style name='Style', type='css'}
${menu name='Product title', icon='align-justify'}
	${menu block->with_title name='With title'}
	${menu p->title name='Item text'}
	${menu args->title_max_lines name='Title max lines', type='number', param='min=1'}
${menu name='Product text/desc', icon='align-justify'}
	${menu block->description name='With description'}
	${menu p->description name='Item text'}
	${menu args->a_css name='Text style', type='css', param='with_responsive=1'}
	${menu args->a_hover_color name='Text on hover color', type='color'}
	${menu args->a_css_3 name='Text color', type='css', param='with_responsive=1'}
${menu name='Payments', icon='bars'}
	${menu block->payment name='With payments'}
	${menu args->payment_style name='Style', type='css'}
	${menu args->payment_min name='Minimum order amount'}
	${menu args->payment_n name='Number of payments'}
	${menu args->payment_text_yes name='Text if payments available'}
	${menu args->payment_text_no name='Text if payments not available'}
	${menu args->payment_text_2 name='Text below'}
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
	${menu args->n_reviews name='No. of reviews'}
	${menu args->n_reviews_style name='No. of reviews style', type='css'}
${menu name='Site statistics: 1-day', icon='bar-chart', description='Show number of viewed or purchases in the last 24 hours for a given item as tracked by Personyze. You can set a condition not to show if the number of views/purchases is below X number.'}
	${menu block->stats_1day name='Site statistics: 1day'}
	${menu args->hide_no_view_1day name='Hide statistics if less views than', type='number', param='min=0'}
	${menu args->hide_no_goal_1day name='Hide statistics if less purchases than', type='number', param='min=0'}
	${menu args->text_style_1day name='Style', type='css'}
	${menu args->icon_n_viewed_1day name='Icon on button', type='icon'}
	${menu args->icon_style_n_viewed_1day name='Icon on button style', type='css'}
	${menu args->n_viewed_1day name='Text'}
	${menu args->icon_n_goal_1day name='Icon on button', type='icon'}
	${menu args->icon_style_n_goal_1day name='Icon on button style', type='css'}
	${menu args->n_goal_1day name='Text'}
${menu name='Site statistics: week', icon='bar-chart', description='Show number of viewed or purchases in the last week for a given item as tracked by Personyze. You can set a condition not to show if the number of views/purchases is below X number.'}
	${menu block->stats_week name='Site statistics: week'}
	${menu args->hide_no_view_week name='Hide statistics if less views than', type='number', param='min=0'}
	${menu args->hide_no_goal_week name='Hide statistics if less purchases than', type='number', param='min=0'}
	${menu args->text_style_week name='Style', type='css'}
	${menu args->icon_n_viewed_week name='Icon on button', type='icon'}
	${menu args->icon_style_n_viewed_week name='Icon on button style', type='css'}
	${menu args->n_viewed_week name='Text'}
	${menu args->icon_n_goal_week name='Icon on button', type='icon'}
	${menu args->icon_style_n_goal_week name='Icon on button style', type='css'}
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
${menu name='Lines scroller', icon='film'}
	${menu block->with_sc name='With lines scroller'}
	${menu args->sc_style name='Style', type='css'}
	${menu args->sc_without_close name='Leave info box open at the end of the animation', type='checkbox', param='value_on=1', param='value_off='}
	${menu block->sc_with_views name='With views'}
	${menu args->sc_min_views name='Dont show if less views', type='number', param='min=0'}
	${menu args->sc_icon_views name='Icon for views', type='icon'}
	${menu args->sc_icon_views_style name='Icon for views: style', type='css'}
	${menu args->sc_text_views name='Line 1: views'}
	${menu block->sc_with_goals name='With goals'}
	${menu args->sc_min_goals name='Dont show if less purchases', type='number', param='min=0'}
	${menu args->sc_icon_goals name='Icon for purchases', type='icon'}
	${menu args->sc_icon_goals_style name='Icon for purchases: style', type='css'}
	${menu args->sc_text_goals name='Line 2: purchases'}
	${menu block->sc_with_inventory name='With inventory'}
	${menu args->sc_min_inventory name='Dont show if more items in stock than', type='number', param='min=0'}
	${menu args->sc_min_goals_for_inventory name='Dont show if less purchases', type='number', param='min=0'}
	${menu args->sc_icon_inventory name='Icon for inventory', type='icon'}
	${menu args->sc_icon_inventory_style name='Icon for inventory: style', type='css'}
	${menu args->sc_text_inventory name='Line 3: inventory'}
	${menu block->sc_with_price_drop name='With price drop'}
	${menu args->sc_min_price_drop name='Show if drop percent at least', type='number', param='min=1'}
	${menu args->sc_min_price_drop_days name='Show if drop was before N days or less', type='number', param='min=1'}
	${menu args->sc_icon_price_drop name='Icon for price drop', type='icon'}
	${menu args->sc_icon_price_drop_style name='Icon for price drop: style', type='css'}
	${menu args->sc_text_price_drop name='Line 4: text. Use {P} for percent, and {D} for no. of days'}
	${menu block->sc_with_discount name='With discount'}
	${menu args->sc_min_discount name='Show if discount % is at least', type='number', param='min=1'}
	${menu args->sc_icon_discount name='Icon for discount', type='icon'}
	${menu args->sc_icon_discount_style name='Icon for discount: style', type='css'}
	${menu args->sc_text_discount name='Line 5: text. Use {P} for discount percent'}
	${menu block->sc_with_new name='With new in stock'}
	${menu args->sc_min_new_days name='Show if product appeared this no. of days ago', type='number', param='min=1'}
	${menu args->sc_icon_new name='Icon for new in stock', type='icon'}
	${menu args->sc_icon_new_style name='Icon for new in stock: style', type='css'}
	${menu args->sc_text_new name='Line 6: text. Use {D} for no. of days'}
	${menu block->sc_with_free1 name='With free text 1'}
	${menu args->sc_icon_free1 name='Icon for free text 1', type='icon'}
	${menu args->sc_icon_free1_style name='Icon for free text 1: style', type='css'}
	${menu args->sc_text_free1 name='Free text 1'}
	${menu block->sc_with_free2 name='With free text 2'}
	${menu args->sc_icon_free2 name='Icon for free text 2', type='icon'}
	${menu args->sc_icon_free2_style name='Icon for free text 2: style', type='css'}
	${menu args->sc_text_free2 name='Free text 2'}
	${menu block->sc_with_free3 name='With free text 3'}
	${menu args->sc_icon_free3 name='Icon for free text 3', type='icon'}
	${menu args->sc_icon_free3_style name='Icon for free text 3: style', type='css'}
	${menu args->sc_text_free3 name='Free text 3'}
${menu name='Countdown', icon='clock-o'}
	${menu block->with_timer name='With countdown'}
	${menu args->value name='Type', type='timer_custom_params'}
	${menu args->timersubstrate_style name='Substrate', type='css', param='with_responsive=1'}
	${menu args->timer_background_style name='Background style', type='css', param='with_responsive=1'}
	${menu args->timer_box_style name='Box style', type='css', param='with_responsive=1'}
	${menu args->timer_caption_days name='Caption days'}
	${menu args->timer_caption_hours name='Caption days'}
	${menu args->timer_caption_minutes name='Caption days'}
	${menu args->timer_caption_seconds name='Caption days'}
	${menu args->timer_caption_style name='Caption style', type='css', param='with_responsive=1'}
	${menu args->timer_number_style name='Number style', type='css', param='with_responsive=1'}
	${menu block->with_left_text name='With left text'}
	${menu args->left_text name='Left text'}
	${menu args->left_style name='Left text style', type='css', param='with_responsive=1'}
	${menu block->with_right_button name='With right button'}
	${menu args->right_button_text name='Text'}
	${menu args->right_href name='URL', type='a_attrs'}
	${menu args->right_button_style name='Style', type='css', param='with_responsive=1'}
```


## With hover shadow



```
<div class="$responsive $a_add_params" data-style="display:inline-block; position:relative; display:flex; flex-direction:column; justify-content:stretch; ${args->style:html:default('padding: 0px;
border: none;
margin-top: 0px;
margin-right: auto;
margin-bottom: 60px;
margin-left: auto;
width: 100%;
height: 100%;
background-color: transparent;
')}; direction: ${args->direction:html:default(ltr)};" data-json-params="${args->url_params:html}">
		${block->with_logo:default(0)}
		<div style="${args->logo_block_style:html:default('text-align: center;
')}">
			<img src="${args->logo_src:html:default('https://counter-backend.emarketer.com/upload/362/18a94c1299224ec8-th.jpeg')}">
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
				img.st-zoom {transition:transform ease 0.3s; transform: scale(1)}
				img.st-zoom:hover {transform: scale(calc(${args->img_zoom_on_hover:default(120)} / 100))}

				.st-hov:hover {color: ${args->a_hover_color:html:default('#3b3b3b')} !important}
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
				.st-tab-rnd > * > tr > *
				{   overflow: visible !important;
				}
				.st-tab-rnd > *:first-child > tr:first-child > .st-td-hover::before
				{   content: "";
					display: block;
					position: absolute;
					z-index: 1;
					left: 0;
					top: 0;
					width: 100%;
					height: var(--st-tab-rnd-height);
					pointer-events: none;
					${args->hover_shadow:default('box-shadow: 0px 0px 13px 1px rgb(0 0 0/.33);
padding: 0px;
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
				{   opacity: 0.6;
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
				<div data-style="flex-grow:1000; ${args->title_style:html:default('text-align: left;
font-size: sel(1.75rem, 18px);
font-weight: 700;
font-family: "Bodoni Moda",serif;
letter-spacing: 0.25px;
color: black;
padding-top: 0rem;
padding-right: 0;
padding-bottom: 3rem;
padding-left: 0;
')}">
					${args->title:default(Your title)}
				</div>
				${block->with_arrows:default(0)}
				<div>
					<a id="button_back" class="$flat_btn" href="javascript:" style="${args->btn_style:html}" hover_style="${args->btn_hover_style:html}"><</a>
					<a id="button_forward" class="$flat_btn" href="javascript:" style="${args->btn_style:html}" hover_style="${args->btn_hover_style:html}">></a>
				</div>
				${block->x:default(0)}
				<div style="${args->x_style:html}">
					${args->x:default('<div onmouseenter="this.style.backgroundColor=this.style.outlineColor" onmouseleave="this.style.backgroundColor=this.style.textDecorationColor" style="display: inline-block; vertical-align: text-bottom; width: 24px; height: 24px; box-sizing: border-box; border-radius: 50%; border: 0px solid; -webkit-box-shadow: none; padding: 2px; background-color: rgba(0, 0, 0, 0); text-decoration-color: rgba(0, 0, 0, 0); outline-color: rgb(206, 54, 64); outline-width: 15px; color: rgb(10, 4, 4); cursor: pointer; transition: all 0.3s ease 0s;" class="$emarketer_button_dont_show_again" data-action_id="${action_id}"><div style="display: block; width: 100%; height: 100%; transition: all 0.3s ease 0s; border-radius: 50%; background-image: linear-gradient(-45deg, transparent 0%, transparent 43%, currentcolor 43%, currentcolor 59%, transparent 59%, transparent 100%), linear-gradient(45deg, transparent 0%, transparent 43%, currentcolor 43%, currentcolor 59%, transparent 59%, transparent 100%);"></div></div>')}
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
					${args->left_text:default('<img src="https://cdn.emarketer.com/upload/5506/610fad918b0b9980.png" style="width:102px; float:left" />')}
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

			<div data-style="${args->content_padding:html:default('width: 100%;
margin: auto;
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
')}" pagination_id="tsp" arrow_back_id="button_back" arrow_forward_id="button_forward" arrows_offset="${args->arrows_offset:html:default(-8)}" hide_buttons="${args->hide_buttons:html}" buttons_always="${args->buttons_always:html:default(1)}">
						${foreach products as p order by p->time_created desc limit 12}
							<td style="position:relative; height:1px; padding:0; text-align:center; background-color:white; vertical-align:top; border:solid ${args->border_color:html:default(transparent)} 1px">
								<div style="width:${args->img_width:html:default('sel(295px, 44vw)')}; height:100%; box-sizing:border-box">
									<a data-emarketer-click-target="products ${p->internal_id:html}" href="${p->cart_url:html}" target="${args->target:html:default(_self)}" data-style="position:relative; display:flex; width:100%; height:100%; margin:auto; box-sizing:border-box; overflow:hidden; text-decoration:none; ${args->img_alignment:html:default('align-items: baseline;
		')}">
										<img class="st-zoom" src="${p->image_big_url:html}" data-style="margin:auto; width:auto; height:auto; max-width:100%; max-height:${args->img_max_height:html:default('sel(300px, 80vh)')}; border:none">

										${if p->image_medium_url <> ''}
											${block->with_hover_image:default(0)}
											<div style="position:absolute; display:flex; left:0; top: 0; width:100%; height:100%; ${args->img_alignment:html}">
												<img src="${p->image_medium_url:html}" data-style="width:auto; height:auto; max-width:100%; max-height:${args->img_max_height:html}; border:none">
											</div>
										${end}
									</a>

									${block->with_discount_badge:default(1)}
									<span>
										${if p->discount_percent >= args->min_discount_percent:default(10)}
											<div data-style="position: absolute; ${args->discount_badge_style:html:default('top: 0;
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
										${if unix_timestamp() - p->time_created <= args->badge_if_newer:default(604800)}
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
										${if p->inventory between 1 and args->badge_if_less_stock:default(300)}
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

									${block->with_hover_overlay:default(0)}
									<div class="st-tab-ovy" style="${args->hover_overlay_style:html:default('background-color: transparent;')}">
										${args->hover_overlay_text}

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
										<a class="$flat_btn" data-emarketer-click-target="products ${p->internal_id:html}" href="${args->hover_overlay_a2_href:html:default('${p->cart_url}')}" data-style="box-sizing:border-box; ${args->hover_overlay_a2_style:html:default('color: rgb(39, 36, 70);
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

								${block->with_options_link:default(1)}
								<a data-emarketer-click-target="products ${p->internal_id:html}" href="${args->options_link_href:html:default('${p->cart_url:html}')}" target="${args->target:html}" data-style="${args->options_link_style:html:default('padding-top: 15px;
padding-right: 0px;
padding-bottom: 0px;
padding-left: 0px;
')}; display:block; margin:auto; box-sizing:border-box; width:${args->img_width:html}; text-decoration:none">
									${args->options_link_text:default(+ See options)}
								</a>

								<a data-emarketer-click-target="products ${p->internal_id:html}" href="${p->cart_url:html}" target="${args->target:html}" data-style="display:block; margin:auto; box-sizing:border-box; width:${args->img_width:html}; text-decoration:none">
									<div class="st-hov" data-style="${args->a_css:html:default('padding: 1px;
text-transform: none;
color: black;
font-size: 15px;
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

								${block->stats_week:default(1)}
								<span>
									${foreach sum_products_week as s where s->internal_id = p->internal_id limit 1}
										${if s->n_viewed >= args->hide_no_view_week:default(3)}
											${if s->n_goal >= args->hide_no_goal_week:default(0)}
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
													${if s->n_viewed > 0}
														${args->n_viewed_week:default('<div>This product has been popular&nbsp;${s->n_viewed*1}&nbsp; views recently.</div>
')}
													${end}
													${if s->n_goal > 0}
														${args->n_goal_week}
													${end}
												</div>
											${end}
										${end}
									${end}
								</span>

								<div style="clear:left;"></div>
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
													${args->old_price_before}${args->p_price_before_discount:default('$${p->price_before_discount:sprintf(''%[#,###.#]f'')}')}${args->old_price_after}
												</span>
											</span>
											<span style="white-space:nowrap">
												<span style="${args->new_price_style:html:default('font-size: 17px;
font-weight: 500;
color: black;
')}">
													${args->old_price_before)}${args->p_price_after_discount:default('$${p->price_after_discount:sprintf(''%[#,###.#]f'')}')}${args->old_price_after}
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

								${block->rating:default(1)}
								<span>
									<hr class="$rating" data-value="${p->rank:html:default(0)}" style="${args->rating_style:html:default('color: #631d85;
--bgcolor: white;
--border-color: rgba(225, 214, 214, 0.87);
width: 120px;
height: 16px;
')}">
								</span>

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

								${block->payment:default(1)}
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

								${block->with_link_button:default(1)}
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
										data-emarketer-click-target="products ${p->internal_id:html}"
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
												<a class="$flat_btn" data-emarketer-click-target="products ${p->internal_id:html}" href="${args->hover_ovy2_a2_href:html:default('${p->cart_url}')}" data-style="box-sizing:border-box; ${args->hover_ovy2_a2_style:html:default('color: rgb(39, 36, 70);
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
${menu name='Hover shadow', icon='box'}
	${menu block->with_hover_shadow name='With hover shadow'}
	${menu args->hover_shadow name='Shadow', type='css'}
${menu name='Hover overlay', icon='mouse-pointer'}
	${menu block->with_hover_overlay name='With hover overlay'}
	${menu args->hover_overlay_style name='Style', type='css'}
	${menu args->hover_overlay_text name='Text'}
	${menu block->with_hover_overlay_a name='With link 1'}
	${menu args->hover_overlay_a_block_style name='Link 1 block style', type='css'}
	${menu args->hover_overlay_a_text name='Link 1 text'}
	${menu args->hover_overlay_a_href name='Link 1 URL'}
	${menu args->hover_overlay_a_style name='Link 1 style', type='css'}
	${menu args->hover_overlay_a_style_hover name='Link 1 hover style', type='css'}
	${menu block->with_hover_overlay_a2 name='With link 2'}
	${menu args->hover_overlay_a2_block_style name='Link 2 block style', type='css'}
	${menu args->hover_overlay_a2_text name='Link 2 text'}
	${menu args->hover_overlay_a2_href name='Link 2 URL'}
	${menu args->hover_overlay_a2_style name='Link 2 style', type='css'}
	${menu args->hover_overlay_a2_style_hover name='Link 2 hover style', type='css'}
${menu name='Hover overlay from bottom', icon='mouse-pointer'}
	${menu block->with_ovy2 name='With hover overlay'}
	${menu args->hover_ovy2_shad_style name='Shadow', type='css'}
	${menu args->hover_ovy2_style name='Style', type='css'}
	${menu args->hover_ovy2_text name='Text'}
	${menu args->hover_ovy2_style2 name='Text style', type='css'}
	${menu block->with_hover_ovy2_a name='With link 1'}
	${menu args->hover_ovy2_a_block_style name='Link 1 block style', type='css'}
	${menu args->hover_ovy2_a_text name='Link 1 text'}
	${menu args->hover_ovy2_a_href name='Link 1 URL'}
	${menu args->hover_ovy2_a_style name='Link 1 style', type='css'}
	${menu args->hover_ovy2_a_style_hover name='Link 1 hover style', type='css'}
	${menu block->with_hover_ovy2_a2 name='With link 2'}
	${menu args->hover_ovy2_a2_block_style name='Link 2 block style', type='css'}
	${menu args->hover_ovy2_a2_text name='Link 2 text'}
	${menu args->hover_ovy2_a2_href name='Link 2 URL'}
	${menu args->hover_ovy2_a2_style name='Link 2 style', type='css'}
	${menu args->hover_ovy2_a2_style_hover name='Link 2 hover style', type='css'}
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
${menu name='Add to wishlist', icon='bars', description='Show save to wishlist icon, on click item will be saved to emarketer wishlist. Items can be included in email/site widgets when using the wishlist algorithm. You can also set JS to report to your site when a visitor is saving an item to a wishlist.'}
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
${menu name='Options link', icon='external-link'}
	${menu block->with_options_link name='With options link'}
	${menu args->options_link_href name='Link URL'}
	${menu args->options_link_style name='Link style', type='css'}
	${menu args->options_link_text name='Link text'}
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
${menu name='Payments', icon='bars'}
	${menu block->payment name='With payments'}
	${menu args->payment_style name='Style', type='css'}
	${menu args->payment_min name='Minimum order amount'}
	${menu args->payment_n name='Number of payments'}
	${menu args->payment_text_yes name='Text if payments available'}
	${menu args->payment_text_no name='Text if payments not available'}
	${menu args->payment_text_2 name='Text below'}
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
${menu name='Site statistics: 1-day', icon='bar-chart', description='Show number of viewed or purchases in the last 24 hours for a given item as tracked by emarketer. You can set a condition not to show if the number of views/purchases is below X number.'}
	${menu block->stats_1day name='Site statistics: 1day'}
	${menu args->hide_no_view_1day name='Hide statistics if less views than', type='number', param='min=0'}
	${menu args->hide_no_goal_1day name='Hide statistics if less purchases than', type='number', param='min=0'}
	${menu args->text_style_1day name='Style', type='css'}
	${menu args->n_viewed_1day name='Text'}
	${menu args->n_goal_1day name='Text'}
${menu name='Site statistics: week', icon='bar-chart', description='Show number of viewed or purchases in the last week for a given item as tracked by emarketer. You can set a condition not to show if the number of views/purchases is below X number.'}
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
${menu name='Countdown', icon='clock-o'}
	${menu block->with_timer name='With countdown'}
	${menu args->value name='Type', type='timer_custom_params'}
	${menu args->timersubstrate_style name='Substrate', type='css', param='with_responsive=1'}
	${menu args->timer_background_style name='Background style', type='css', param='with_responsive=1'}
	${menu args->timer_box_style name='Box style', type='css', param='with_responsive=1'}
	${menu args->timer_caption_days name='Caption days'}
	${menu args->timer_caption_hours name='Caption days'}
	${menu args->timer_caption_minutes name='Caption days'}
	${menu args->timer_caption_seconds name='Caption days'}
	${menu args->timer_caption_style name='Caption style', type='css', param='with_responsive=1'}
	${menu args->timer_number_style name='Number style', type='css', param='with_responsive=1'}
	${menu block->with_left_text name='With left text'}
	${menu args->left_text name='Left text'}
	${menu args->left_style name='Left text style', type='css', param='with_responsive=1'}
	${menu block->with_right_button name='With right button'}
	${menu args->right_button_text name='Text'}
	${menu args->right_href name='URL', type='a_attrs'}
	${menu args->right_button_style name='Style', type='css', param='with_responsive=1'}
```


## With messaging animation



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

			${block->with_hover_shadow:default(1)}
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
						${foreach sum_products as p where p->for_period='recently' and p->n_goal>0 order by p->n_goal desc union sum_last_interested_products order by p->n_viewed desc limit 12}
							<td style="position:relative; height:100%; padding:0; text-align:center; background-color:white; vertical-align:top; border:solid ${args->border_color:html:default(transparent)} 1px">
								<div style="display:block; overflow:visible; position:absolute; z-index:1; left:0; top:0; width:100%; height:var(--st-tab-rnd-height); pointer-events:none; transform:translate(0, 0)">
									<div class="st-tab-rnd-cell" style="${args->cell_border:html}; position:fixed; left:0; top:0; width:100%; height:100%" ontplready="this.parentNode.parentNode.style.overflow='visible'"></div>
								</div>
								<div data-personyze-click-target="products ${p->internal_id:html}" onclick="for (let e=event.target; e &amp;&amp; e!=this; e=e.parentNode) if (e.nodeName == 'A') return; var a=_S_T.new_elem('a', this, {href: ${p->cart_url:json:html}, target: ${args->target:json:html:default(_self)}, style: 'position:absolute; visibility:hidden'}); a.click(); setTimeout(function() {a.parentNode.removeChild(a)}, 100)" data-style="cursor:pointer; width:${args->img_width:html:default('sel(344px, 44vw)')}; height:100%; position:relative; overflow:hidden; box-sizing:border-box">
									<div data-style="position:relative; display:flex; width:100%; height:100%; max-width:100%; margin:auto; box-sizing:border-box; overflow:hidden; text-decoration:none; ${args->img_alignment:html:default('align-items: baseline;
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

${menu name='Frame', icon='th-large'}
	${menu args->style name='Style', type='css', param='with_responsive=1'}
	${menu args->content_padding name='Content box padding', type='css', param='with_responsive=1'}
	${menu args->round name='No cut cell', type='checkbox', param='value_off=', param='value_on=1'}
	${menu args->eq_cell_width name='Equal cell width', type='checkbox', param='value_off=', param='value_on=1'}
	${menu args->eq_cell_height name='Equal cell height', type='checkbox', param='value_off=', param='value_on=1'}
	${menu args->space_between_items name='Space between items', type='css_length', param='with_responsive=1'}
	${menu args->border_color name='Border color', type='color'}
	${menu args->cell_border name='Shadow', type='css'}
	${menu args->round_border name='Round border', type='css_length'}
	${menu args->direction name='Localization settings', type='select', param='options=[["Left to right","ltr"],["Right to left","rtl"]]'}
	${menu args->url_params name='URL additional parameters', type='external_media_url_params'}
${menu name='Hover shadow', icon='clone'}
	${menu block->with_hover_shadow name='With hover shadow'}
	${menu args->hover_shadow name='Shadow', type='css'}
${menu name='Hover overlay', icon='mouse-pointer'}
	${menu block->with_hover_overlay name='With hover overlay'}
	${menu args->hover_overlay_style name='Style', type='css'}
	${menu args->hover_opacity name='Hover opacity', type='css'}
	${menu args->hover_overlay_text name='Text'}
	${menu block->with_hover_overlay_a name='With link 1'}
	${menu args->hover_overlay_a_block_style name='Link 1 block style', type='css'}
	${menu args->hover_overlay_a_text name='Link 1 text'}
	${menu args->hover_overlay_a_href name='Link 1 URL'}
	${menu args->hover_overlay_a_style name='Link 1 style', type='css'}
	${menu args->hover_overlay_a_style_hover name='Link 1 hover style', type='css'}
	${menu block->with_hover_overlay_a2 name='With link 2'}
	${menu args->hover_overlay_a2_block_style name='Link 2 block style', type='css'}
	${menu args->hover_overlay_a2_text name='Link 2 text'}
	${menu args->hover_overlay_a2_href name='Link 2 URL'}
	${menu args->hover_overlay_a2_style name='Link 2 style', type='css'}
	${menu args->hover_overlay_a2_style_hover name='Link 2 hover style', type='css'}
${menu name='Hover overlay from bottom', icon='mouse-pointer'}
	${menu block->with_ovy2 name='With hover overlay'}
	${menu args->hover_ovy2_shad_style name='Shadow', type='css'}
	${menu args->hover_ovy2_style name='Style', type='css'}
	${menu args->hover_ovy2_text name='Text'}
	${menu args->hover_ovy2_style2 name='Text style', type='css'}
	${menu block->with_hover_ovy2_a name='With link 1'}
	${menu args->hover_ovy2_a_block_style name='Link 1 block style', type='css'}
	${menu args->hover_ovy2_a_text name='Link 1 text'}
	${menu args->hover_ovy2_a_href name='Link 1 URL'}
	${menu args->hover_ovy2_a_style name='Link 1 style', type='css'}
	${menu args->hover_ovy2_a_style_hover name='Link 1 hover style', type='css'}
	${menu block->with_hover_ovy2_a2 name='With link 2'}
	${menu args->hover_ovy2_a2_block_style name='Link 2 block style', type='css'}
	${menu args->hover_ovy2_a2_text name='Link 2 text'}
	${menu args->hover_ovy2_a2_href name='Link 2 URL'}
	${menu args->hover_ovy2_a2_style name='Link 2 style', type='css'}
	${menu args->hover_ovy2_a2_style_hover name='Link 2 hover style', type='css'}
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
${menu name='Discount badge', icon='align-justify', description='Set discount badge to appear for a discounted product, you may choose to set it to show only if the discount is greater than X.'}
	${menu block->with_discount_badge name='With new badge'}
	${menu args->min_discount_percent name='Show discount badge if % ≥', type='number', param='min=1'}
	${menu args->discount_badge_style name='Badge style', type='css', param='with_responsive=1'}
	${menu args->discount_badge_text_style name='Badge text style', type='css', param='with_responsive=1'}
	${menu args->discount_badge_text name='Text'}
${menu name='Price drop badge', icon='tag'}
	${menu block->with_price_drop_badge name='With price drop badge'}
	${menu args->min_price_drop name='Show if drop percent at least', type='number', param='min=1'}
	${menu args->min_price_drop_days name='Show if drop was before N days or less', type='number', param='min=1'}
	${menu args->price_drop_badge_style name='Badge style', type='css', param='with_responsive=1'}
	${menu args->price_drop_badge_text_style name='Badge text style', type='css', param='with_responsive=1'}
	${menu args->text_price_drop name='Text. Use {P} for percent, and {D} for no. of days'}
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
	${menu args->db_badge_text name='Badge text'}
	${menu args->db_badge_text_style name='Badge text style', type='css'}
${menu name='Options link', icon='external-link'}
	${menu block->with_options_link name='With options link'}
	${menu args->options_link_href name='Link URL'}
	${menu args->options_link_style name='Link style', type='css'}
	${menu args->options_link_text name='Link text'}
${menu name='Custom column', icon='database', description='Select additional field to show.'}
	${menu block->with_custom_column name='With custom column'}
	${menu args->custom_column name='Date column'}
	${menu args->custom_column_style name='Style', type='css'}
${menu name='Product title', icon='align-justify'}
	${menu block->with_title name='With title'}
	${menu p->title name='Item text'}
	${menu args->title_max_lines name='Title max lines', type='number', param='min=1'}
${menu name='Product text/desc', icon='align-justify'}
	${menu block->description name='With description'}
	${menu p->description name='Item text'}
	${menu args->a_css name='Text style', type='css', param='with_responsive=1'}
	${menu args->a_hover_color name='Text on hover color', type='color'}
	${menu args->a_css_3 name='Text color', type='css', param='with_responsive=1'}
${menu name='Payments', icon='bars'}
	${menu block->payment name='With payments'}
	${menu args->payment_style name='Style', type='css'}
	${menu args->payment_min name='Minimum order amount'}
	${menu args->payment_n name='Number of payments'}
	${menu args->payment_text_yes name='Text if payments available'}
	${menu args->payment_text_no name='Text if payments not available'}
	${menu args->payment_text_2 name='Text below'}
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
	${menu args->n_reviews name='No. of reviews'}
	${menu args->n_reviews_style name='No. of reviews style', type='css'}
${menu name='Site statistics: 1-day', icon='bar-chart', description='Show number of viewed or purchases in the last 24 hours for a given item as tracked by Personyze. You can set a condition not to show if the number of views/purchases is below X number.'}
	${menu block->stats_1day name='Site statistics: 1day'}
	${menu args->hide_no_view_1day name='Hide statistics if less views than', type='number', param='min=0'}
	${menu args->hide_no_goal_1day name='Hide statistics if less purchases than', type='number', param='min=0'}
	${menu args->text_style_1day name='Style', type='css'}
	${menu args->icon_n_viewed_1day name='Icon on button', type='icon'}
	${menu args->icon_style_n_viewed_1day name='Icon on button style', type='css'}
	${menu args->n_viewed_1day name='Text'}
	${menu args->icon_n_goal_1day name='Icon on button', type='icon'}
	${menu args->icon_style_n_goal_1day name='Icon on button style', type='css'}
	${menu args->n_goal_1day name='Text'}
${menu name='Site statistics: week', icon='bar-chart', description='Show number of viewed or purchases in the last week for a given item as tracked by Personyze. You can set a condition not to show if the number of views/purchases is below X number.'}
	${menu block->stats_week name='Site statistics: week'}
	${menu args->hide_no_view_week name='Hide statistics if less views than', type='number', param='min=0'}
	${menu args->hide_no_goal_week name='Hide statistics if less purchases than', type='number', param='min=0'}
	${menu args->text_style_week name='Style', type='css'}
	${menu args->icon_n_viewed_week name='Icon on button', type='icon'}
	${menu args->icon_style_n_viewed_week name='Icon on button style', type='css'}
	${menu args->n_viewed_week name='Text'}
	${menu args->icon_n_goal_week name='Icon on button', type='icon'}
	${menu args->icon_style_n_goal_week name='Icon on button style', type='css'}
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
${menu name='Lines scroller', icon='film'}
	${menu block->with_sc name='With lines scroller'}
	${menu args->sc_style name='Style', type='css'}
	${menu args->sc_without_close name='Leave info box open at the end of the animation', type='checkbox', param='value_on=1', param='value_off='}
	${menu block->sc_with_views name='With views'}
	${menu args->sc_min_views name='Dont show if less views', type='number', param='min=0'}
	${menu args->sc_icon_views name='Icon for views', type='icon'}
	${menu args->sc_icon_views_style name='Icon for views: style', type='css'}
	${menu args->sc_text_views name='Line 1: views'}
	${menu block->sc_with_goals name='With goals'}
	${menu args->sc_min_goals name='Dont show if less purchases', type='number', param='min=0'}
	${menu args->sc_icon_goals name='Icon for purchases', type='icon'}
	${menu args->sc_icon_goals_style name='Icon for purchases: style', type='css'}
	${menu args->sc_text_goals name='Line 2: purchases'}
	${menu block->sc_with_inventory name='With inventory'}
	${menu args->sc_min_inventory name='Dont show if more items in stock than', type='number', param='min=0'}
	${menu args->sc_min_goals_for_inventory name='Dont show if less purchases', type='number', param='min=0'}
	${menu args->sc_icon_inventory name='Icon for inventory', type='icon'}
	${menu args->sc_icon_inventory_style name='Icon for inventory: style', type='css'}
	${menu args->sc_text_inventory name='Line 3: inventory'}
	${menu block->sc_with_price_drop name='With price drop'}
	${menu args->sc_min_price_drop name='Show if drop percent at least', type='number', param='min=1'}
	${menu args->sc_min_price_drop_days name='Show if drop was before N days or less', type='number', param='min=1'}
	${menu args->sc_icon_price_drop name='Icon for price drop', type='icon'}
	${menu args->sc_icon_price_drop_style name='Icon for price drop: style', type='css'}
	${menu args->sc_text_price_drop name='Line 4: text. Use {P} for percent, and {D} for no. of days'}
	${menu block->sc_with_discount name='With discount'}
	${menu args->sc_min_discount name='Show if discount % is at least', type='number', param='min=1'}
	${menu args->sc_icon_discount name='Icon for discount', type='icon'}
	${menu args->sc_icon_discount_style name='Icon for discount: style', type='css'}
	${menu args->sc_text_discount name='Line 5: text. Use {P} for discount percent'}
	${menu block->sc_with_new name='With new in stock'}
	${menu args->sc_min_new_days name='Show if product appeared this no. of days ago', type='number', param='min=1'}
	${menu args->sc_icon_new name='Icon for new in stock', type='icon'}
	${menu args->sc_icon_new_style name='Icon for new in stock: style', type='css'}
	${menu args->sc_text_new name='Line 6: text. Use {D} for no. of days'}
	${menu block->sc_with_free1 name='With free text 1'}
	${menu args->sc_icon_free1 name='Icon for free text 1', type='icon'}
	${menu args->sc_icon_free1_style name='Icon for free text 1: style', type='css'}
	${menu args->sc_text_free1 name='Free text 1'}
	${menu block->sc_with_free2 name='With free text 2'}
	${menu args->sc_icon_free2 name='Icon for free text 2', type='icon'}
	${menu args->sc_icon_free2_style name='Icon for free text 2: style', type='css'}
	${menu args->sc_text_free2 name='Free text 2'}
	${menu block->sc_with_free3 name='With free text 3'}
	${menu args->sc_icon_free3 name='Icon for free text 3', type='icon'}
	${menu args->sc_icon_free3_style name='Icon for free text 3: style', type='css'}
	${menu args->sc_text_free3 name='Free text 3'}
${menu name='Countdown', icon='clock-o'}
	${menu block->with_timer name='With countdown'}
	${menu args->value name='Type', type='timer_custom_params'}
	${menu args->timersubstrate_style name='Substrate', type='css', param='with_responsive=1'}
	${menu args->timer_background_style name='Background style', type='css', param='with_responsive=1'}
	${menu args->timer_box_style name='Box style', type='css', param='with_responsive=1'}
	${menu args->timer_caption_days name='Caption days'}
	${menu args->timer_caption_hours name='Caption days'}
	${menu args->timer_caption_minutes name='Caption days'}
	${menu args->timer_caption_seconds name='Caption days'}
	${menu args->timer_caption_style name='Caption style', type='css', param='with_responsive=1'}
	${menu args->timer_number_style name='Number style', type='css', param='with_responsive=1'}
	${menu block->with_left_text name='With left text'}
	${menu args->left_text name='Left text'}
	${menu args->left_style name='Left text style', type='css', param='with_responsive=1'}
	${menu block->with_right_button name='With right button'}
	${menu args->right_button_text name='Text'}
	${menu args->right_href name='URL', type='a_attrs'}
	${menu args->right_button_style name='Style', type='css', param='with_responsive=1'}
```
