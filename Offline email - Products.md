## Email



```
<div style="${args->style:html:default('border: none;
text-align: center;
width: 800px;
background-color: white;
color: #0A4A34;
font-size: 14px;
margin-top: 1px;
margin-right: auto;
margin-bottom: 1px;
margin-left: auto;')}">
	<table style="width:100%; border-collapse:collapse; border:none; ${args->logo_table_style:html:default('border-bottom:solid #FEFDA4 4px')}">
		<tr>
			${block->with_logo:default(1)}
			<td style="${args->logo_td_style:html:default('vertical-align: middle;
text-align: center;
padding-top: 1em;
padding-right: 2em;
padding-bottom: 1em;
padding-left: 0em;')}">
				<img src="${args->logo_src:html:default('https://cdn.personyze.com/upload/362/185f3236b1b4ab52.png')}" style="border:none; ${args->logo_img_style:html:default('width: 270px;
height: auto;')}">
			</td>
			${block->with_top_right:default(1)}
			<td style="${args->top_right_td_style:html:default('vertical-align: middle;
text-align: left;
padding-top: 0em;
padding-right: 1em;
padding-bottom: 0em;
padding-left: 0em;')}">
				${args->top_right:default('<div><strong>EUROPA&#39;S GROOTSTE<br />
OUTDOOR LIVING MALL</strong></div>
')}
			</td>
		</tr>
	</table>
	<table style="width:100%; border-collapse:collapse; border:none">
		<tr>
			${block->li1:default(1)}
			<td style="${args->li:html:default('vertical-align:middle; text-align:center; padding:0.6em; font-weight:bold; color:black')}">
				<a href="${args->li1_href:html}" target="_blank" style="color:inherit; text-decoration:inherit">${args->li1_text:default(SHOP)}</a>
			</td>
			${block->li2:default(1)}
			<td style="${args->li:html}">
				<a href="${args->li2_href:html}" target="_blank" style="color:inherit; text-decoration:inherit">${args->li2_text:default(BLOGS)}</a>
			</td>
			${block->li3:default(1)}
			<td style="${args->li:html}">
				<a href="${args->li3_href:html}" target="_blank" style="color:inherit; text-decoration:inherit">${args->li3_text:default(STORE)}</a>
			</td>
			${block->li4:default(1)}
			<td style="${args->li:html}">
				<a href="${args->li4_href:html}" target="_blank" style="color:inherit; text-decoration:inherit">${args->li4_text:default(SHOWROOM)}</a>
			</td>
			${block->li5:default(1)}
			<td style="${args->li:html}">
				<a href="${args->li5_href:html}" target="_blank" style="color:inherit; text-decoration:inherit">${args->li5_text:default(CONTACT)}</a>
			</td>
		</tr>
	</table>
	${block->with_img:default(1)}
	<img src="${args->img_src:html:default('https://cdn.personyze.com/upload/4054/e648f93960a53241.jpeg')}" style="border:none; ${args->img_style:html:default('width: 100%;
height: auto;')}">
	<h1 style="${args->h1_style:html:default('font-size: 0px;')}">
		${args->h1:default('<img src="https://cdn.personyze.com/upload/4054/b57f02953130159f.png" />')}
	</h1>
	${args->p:default('<p style="margin:0 4em"><font face="Verdana, Geneva, sans-serif" size="3">text text</font></p>
')}
	${block->with_button:default(1)}
	<a href="${args->button_href:html:default('https://www.fonteyn.nl/wishlist/index/index/wishlist_id/${wishlist_id}')}" target="_blank" style="display:inline-block; ${args->button_style:html:default('background-color:#0A4A34; color:white; padding:0.6em 1.2em; margin:1em; text-decoration:none; font-weight:bold; margin-bottom:2em')}">
		${args->button_text:default(Go to Cart)}
	</a>
	<table style="width:100%; border-collapse:collapse">
		${foreach products_interactions as p where p->interaction_status in ('viewed') order by p->interaction_time desc limit 3}
			<tr>
				<td style="text-align:left">
					<a href="${p->cart_url:html}" target="_blank">
						<img src="${p->image_big_url:html}" style="${args->img_size:html:default('width: 200px;
height: auto;
margin: 10px;')}">
					</a>
				</td>
				<td style="text-align:right; vertical-align:top">
					<div style="${args->name_style:html:default('text-align:left; margin:10px')}">
						<a href="${p->cart_url:html}" target="_blank" style="text-decoration:none">
							<div style="${args->p_title_style:html:default('font-size: 18px;
font-weight: bold;
color: #0A4A34;')}">
								${p->title}
							</div>
							${block->with_desc:default(1)}
							<div style="${args->p_desc_style:html:default('font-size: 18px;
color: #0A4A34;')}">
								${p->description_long}
							</div>
						</a>
						<table style="width:100%; border-collapse:collapse; margin-top:1em">
							<tr>
								${block->price:default(1)}
								<td style="${args->price_style:html:default('font-size: 22px;
font-weight: bold;
color: red;
padding-right: 10px;
')}">
									${if p->price_before_discount}
                                        ${args->before_price}
                                        ${if p->price_after_discount and p->price_after_discount < p->price_before_discount}
                                            <span style="${args->sale_style:html:default('text-decoration: line-through;
font-size: 85%;
')}">
                                                ${args->p_price_before_discount:default('&pound;${p->price_before_discount:price('''')}')}
                                            </span>
                                            ${args->p_price_after_discount:default('&pound;${p->price_after_discount:price('''')}')}
                                        ${end}
                                        ${if not p->price_after_discount or p->price_after_discount >= p->price_before_discount}
                                            ${args->p_price_before_discount}
                                        ${end}
                                        ${args->after_price}
                                    ${end}
								</td>
								<td>
									<a href="${p->cart_url:html}" target="_blank" style="display:inline-block; text-decoration:none; ${args->text_6_style:html:default('text-align: center;
background-color: #0A4A34;
color: white;
font-size: 16px;
font-weight: bold;
padding-top: 0.5em;
padding-right: 1em;
padding-bottom: 0.5em;
padding-left: 1em;
')}">
										${args->text_6:default(View)}
									</a>
								</td>
							</tr>
						</table>
					</div>
				</td>
			</tr>
			<tr>
				<td colspan="2">
					<div style="box-sizing:border-box; ${args->hr:html}"></div>
				</td>
			</tr>
		${end}
	</table>
	${args->p2:default('<p style="margin:4em 4em 2em 4em"><span style="color:#0a4a34;">Text text</span></p>
')}
	${block->with_button2:default(1)}
	<a href="${args->button2_href:html:default('https://www.fonteyn.nl/')}" target="_blank" style="display:inline-block; ${args->button2_style:html:default('background-color:#0A4A34; color:white; padding:0.6em 1.2em; margin:1em; text-decoration:none; font-weight:bold')}">
		${args->button2_text:default(Homopage)}
	</a>
	${block->with_button3:default(1)}
	<a href="${args->button3_href:html:default('https://www.fonteyn.nl/contact/')}" target="_blank" style="display:inline-block; ${args->button3_style:html:default('background-color:#0A4A34; color:white; padding:0.6em 1.2em; margin:1em; text-decoration:none; font-weight:bold')}">
		${args->button3_text:default(Cart)}
	</a>
	<div>
		<div style="display:inline-block">
			${args->p3:default('<br />
&nbsp;')}
		</div>
	</div>
	${block->with_button4:default(1)}
	<div>
		<div style="${args->button4_text_style:html:default('padding-top: 0.6em;
padding-right: 1.2em;
padding-bottom: 0.6em;
padding-left: 1.2em;
margin-top: 2em;
margin-right: 0;
margin-bottom: 1em;
margin-left: 0;
font-size: 20px;')}">
			${args->button4_line_text:default(Unsubscribe)}
		</div>
		<a href="http://pic.personyze.com/unsubscribe/k=${action_key:html}/u=${id:html}" target="_blank" style="display:inline-block; ${args->button4_style:html:default('background-color:#0A4A34; color:white; padding:0.6em 1.2em; margin:1em 0 2em; text-decoration:none; font-weight:bold')}">
			${args->button4_text:default('Unsubscribe &gt;')}
		</a>
	</div>
</div>

${menu name='Frame', icon='th-large'}
	${menu args->style name='Style', type='css'}
${menu name='Logo Line', icon='image'}
	${menu block->with_logo name='With Logo'}
	${menu block->li2 name='With Menu Item 2'}
	${menu block->li3 name='With Menu Item 3'}
	${menu block->li4 name='With Menu Item 4'}
	${menu block->li5 name='With Menu Item 5'}
	${menu args->logo_src name='Logo URL', type='personyze_media_url'}
	${menu args->logo_img_style name='Logo Size', type='css'}
	${menu args->logo_td_style name='Logo Position', type='css'}
	${menu block->with_top_right name='With Top-Right Text'}
	${menu args->top_right_td_style name='Top-Right Text Position', type='css'}
	${menu args->logo_table_style name='Logo Position', type='css'}
${menu name='Top Menu', icon='bars'}
	${menu block->li1 name='With Menu Item 1'}
	${menu args->li name='Menu Item Style', type='css'}
	${menu args->top_right name='Top-Right Text'}
	${menu args->li1_text name='Menu Item 1 Text'}
	${menu args->li1_href name='Menu Item 1 Link URL'}
	${menu args->li2_text name='Menu Item 2 Text'}
	${menu args->li2_href name='Menu Item 2 Link URL'}
	${menu args->li3_text name='Menu Item 3 Text'}
	${menu args->li3_href name='Menu Item 3 Link URL'}
	${menu args->li4_text name='Menu Item 4 Text'}
	${menu args->li4_href name='Menu Item 4 Link URL'}
	${menu args->li5_text name='Menu Item 5 Text'}
	${menu args->li5_href name='Menu Item 5 Link URL'}
${menu name='Picture', icon='image'}
	${menu block->with_img name='With Picture'}
	${menu args->img_src name='Picture URL', type='personyze_media_url'}
	${menu args->img_style name='Picture Size', type='css'}
${menu name='Text', icon='font'}
	${menu args->h1 name='Header'}
	${menu args->h1_style name='Header Style', type='css'}
	${menu args->p name='Text'}
${menu name='Button', icon='mouse-pointer'}
	${menu block->with_button name='With Button'}
	${menu args->button_text name='Button Text'}
	${menu args->button_href name='Button Link URL'}
	${menu args->button_style name='Menu Item Style', type='css'}
${menu name='Product image', icon='image'}
	${menu p->image_big_url name='Image', column_tags='image'}
	${menu args->img_size name='Product Image Size', type='css'}
	${menu p->cart_url name='Link target URL', column_tags='url, custom text'}
${menu name='Product name', icon='text-height'}
	${menu p->title name='Product name'}
	${menu args->name_style name='Product Name Alignment', type='css'}
	${menu args->p_title_style name='Product Name Style', type='css'}
	${menu block->with_desc name='With Description'}
	${menu p->description_long name='Product name'}
	${menu args->p_desc_style name='Product name style', type='css'}
${menu name='Second line', icon='text-height'}
	${menu block->price name='With price'}
	${menu args->before_price name='Text before price'}
	${menu args->p_price_after_discount name='Price after discount'}
	${menu args->after_price name='Text after price'}
	${menu args->price_style name='Price position', type='css'}
	${menu args->p_price_before_discount name='Price before discount'}
	${menu args->sale_style name='Price before discount: style', type='css', param='with_responsive=1'}
	${menu args->text_6 name='Button Text'}
	${menu args->text_6_style name='Text size', type='css'}
${menu name='Bottom Text', icon='font'}
	${menu args->p2 name='Text'}
${menu name='Button', icon='mouse-pointer'}
	${menu block->with_button2 name='With Button 1'}
	${menu args->button2_text name='Button 1 Text'}
	${menu args->button2_href name='Button Link URL'}
	${menu args->button2_style name='Menu Item Style', type='css'}
	${menu block->with_button3 name='With Button 2'}
	${menu args->button3_text name='Button 2 Text'}
	${menu args->button3_href name='Button Link URL'}
	${menu args->button3_style name='Menu Item Style', type='css'}
${menu name='Bottom Text 2', icon='font'}
	${menu args->p3 name='Text'}
${menu name='With Unsubscribe', icon='ban'}
	${menu block->with_button4 name='With Button 1'}
	${menu args->button4_line_text name='Text Line'}
	${menu args->button4_text_style name='Text Line Style', type='css'}
	${menu args->button4_text name='Button Text'}
	${menu args->button4_style name='Button Style', type='css'}
```


## Email



```
<div style="${args->style:html:default('border: none;
text-align: center;
width: 800px;
background-color: white;
color: #0A4A34;
font-size: 14px;
margin-top: 1px;
margin-right: auto;
margin-bottom: 1px;
margin-left: auto;')}">
	<table style="width:100%; border-collapse:collapse; border:none; ${args->logo_table_style:html:default('border-bottom:solid #FEFDA4 4px')}">
		<tr>
			${block->with_logo:default(1)}
			<td style="${args->logo_td_style:html:default('vertical-align: middle;
text-align: center;
padding-top: 1em;
padding-right: 2em;
padding-bottom: 1em;
padding-left: 0em;')}">
				<img src="${args->logo_src:html:default('https://cdn.personyze.com/upload/362/185f3236b1b4ab52.png')}" style="border:none; ${args->logo_img_style:html:default('width: 200px;
height: auto;')}">
			</td>
			${block->with_top_right:default(1)}
			<td style="${args->top_right_td_style:html:default('vertical-align: middle;
text-align: left;
padding-top: 0em;
padding-right: 1em;
padding-bottom: 0em;
padding-left: 0em;')}">
				${args->top_right:default('<div><strong>EUROPA&#39;S GROOTSTE<br />
OUTDOOR LIVING MALL</strong></div>
')}
			</td>
		</tr>
	</table>
	<table style="width:100%; border-collapse:collapse; border:none">
		<tr>
			${block->li1:default(1)}
			<td style="${args->li:html:default('vertical-align:middle; text-align:center; padding:0.6em; font-weight:bold; color:black')}">
				<a href="${args->li1_href:html}" target="_blank" style="color:inherit; text-decoration:inherit">${args->li1_text:default(SHOP NU)}</a>
			</td>
			${block->li2:default(1)}
			<td style="${args->li:html}">
				<a href="${args->li2_href:html}" target="_blank" style="color:inherit; text-decoration:inherit">${args->li2_text:default(BLOGS)}</a>
			</td>
			${block->li3:default(1)}
			<td style="${args->li:html}">
				<a href="${args->li3_href:html}" target="_blank" style="color:inherit; text-decoration:inherit">${args->li3_text:default(COLLECTIE)}</a>
			</td>
			${block->li4:default(1)}
			<td style="${args->li:html}">
				<a href="${args->li4_href:html}" target="_blank" style="color:inherit; text-decoration:inherit">${args->li4_text:default(SHOWROOM)}</a>
			</td>
			${block->li5:default(1)}
			<td style="${args->li:html}">
				<a href="${args->li5_href:html}" target="_blank" style="color:inherit; text-decoration:inherit">${args->li5_text:default(CONTACT)}</a>
			</td>
		</tr>
	</table>
	${block->with_img:default(1)}
	<img src="${args->img_src:html:default('https://static.personyze.com/upload/362/9021b00a37b389c0.jpeg')}" style="border:none; ${args->img_style:html:default('width: 100%;
height: auto;')}">
	<h1 style="${args->h1_style:html:default('font-size: 0px;')}">
		${args->h1:default('<img src="https://static.personyze.com/upload/4054/b57f02953130159f.png" />')}
	</h1>
	${args->p:default('<p style="margin:0 4em">Text&nbsp;Text Text&nbsp;Text TextText TextvText TextText Text v v v&nbsp;Text Text vText TextvText&nbsp;Text Text&nbsp;Text TextText TextText TextText TextText&nbsp;Text TextText Text</p>
')}
	${block->with_button:default(1)}
	<a href="${args->button_href:html}" target="_blank" style="display:inline-block; ${args->button_style:html:default('background-color:#0A4A34; color:white; padding:0.6em 1.2em; margin:1em; text-decoration:none; font-weight:bold; margin-bottom:2em')}">
		${args->button_text:default(View site)}
	</a>
	<table style="width:100%; border-collapse:collapse">
		${foreach products_interactions as p where p->interaction_status in ('extra') order by p->interaction_time desc limit 3}
			<tr>
				<td style="text-align:left">
					<a href="${p->cart_url:html}" target="_blank">
						<img src="${p->image_big_url:html}" style="${args->img_size:html:default('width:200px; height:200px; margin:10px')}">
					</a>
				</td>
				<td style="text-align:right; vertical-align:top">
					<div style="${args->name_style:html:default('text-align:left; margin:10px')}">
						<a href="${p->cart_url:html}" target="_blank" style="text-decoration:none">
							<div style="${args->p_title_style:html:default('font-size: 18px;
font-weight: bold;
color: #0A4A34;')}">
								${p->title}
							</div>
							${block->with_desc:default(1)}
							<div style="${args->p_desc_style:html:default('font-size: 18px;
color: #0A4A34;')}">
								${p->description_long}
							</div>
						</a>
						<table style="width:100%; border-collapse:collapse; margin-top:1em">
							<tr>
								${block->price:default(1)}
								<td style="${args->price_style:html:default('font-size: 22px;
font-weight: bold;
color: red;
padding-right: 10px;
')}">
									${if p->price_before_discount}
                                        ${args->before_price}
                                        ${if p->price_after_discount and p->price_after_discount < p->price_before_discount}
                                            <span style="${args->sale_style:html:default('text-decoration: line-through;
font-size: 85%;
')}">
                                                ${args->p_price_before_discount:default('&pound;${p->price_before_discount:price('''')}')}
                                            </span>
                                            ${args->p_price_after_discount:default('&pound;${p->price_after_discount:price('''')}')}
                                        ${end}
                                        ${if not p->price_after_discount or p->price_after_discount >= p->price_before_discount}
                                            ${args->p_price_before_discount}
                                        ${end}
                                        ${args->after_price}
                                    ${end}
								</td>
								<td>
									<a href="${p->cart_url:html}" target="_blank" style="display:inline-block; text-decoration:none; ${args->text_6_style:html:default('text-align: center;
background-color: #0A4A34;
color: white;
font-size: 16px;
font-weight: bold;
padding-top: 0.5em;
padding-right: 1em;
padding-bottom: 0.5em;
padding-left: 1em;
')}">
										${args->text_6:default(Buy)}
									</a>
								</td>
							</tr>
						</table>
					</div>
				</td>
			</tr>
			<tr>
				<td colspan="2">
					<div style="box-sizing:border-box; ${args->hr:html}"></div>
				</td>
			</tr>
		${end}
	</table>
	${args->p2:default('<p style="margin:4em 4em 2em 4em"><span style="color:#0a4a34;">Text Text&nbsp;Text Text&nbsp;Text Text</span></p>
')}
	${block->with_button2:default(1)}
	<a href="${args->button2_href:html}" target="_blank" style="display:inline-block; ${args->button2_style:html:default('background-color:#0A4A34; color:white; padding:0.6em 1.2em; margin:1em; text-decoration:none; font-weight:bold')}">
		${args->button2_text:default(Button)}
	</a>
	${block->with_button3:default(1)}
	<a href="${args->button3_href:html}" target="_blank" style="display:inline-block; ${args->button3_style:html:default('background-color:#0A4A34; color:white; padding:0.6em 1.2em; margin:1em; text-decoration:none; font-weight:bold')}">
		${args->button3_text:default(Option 2)}
	</a>
	<div>
		<div style="display:inline-block">
			${args->p3:default('<br />
&nbsp; &nbsp; Text TextText TextText TextText TextText TextText TextText TextText TextText TextText TextText TextText TextText TextText TextText TextText TextText TextText TextText TextText TextText TextText TextText Text')}
		</div>
	</div>
</div>

${menu name='Frame', icon='th-large'}
	${menu args->style name='Style', type='css'}
${menu name='Logo Line', icon='image'}
	${menu block->with_logo name='With Logo'}
	${menu block->li2 name='With Menu Item 2'}
	${menu block->li3 name='With Menu Item 3'}
	${menu block->li4 name='With Menu Item 4'}
	${menu block->li5 name='With Menu Item 5'}
	${menu args->logo_src name='Logo URL', type='personyze_media_url'}
	${menu args->logo_img_style name='Logo Size', type='css'}
	${menu args->logo_td_style name='Logo Position', type='css'}
	${menu block->with_top_right name='With Top-Right Text'}
	${menu args->top_right_td_style name='Top-Right Text Position', type='css'}
	${menu args->logo_table_style name='Logo Position', type='css'}
${menu name='Top Menu', icon='bars'}
	${menu block->li1 name='With Menu Item 1'}
	${menu args->li name='Menu Item Style', type='css'}
	${menu args->top_right name='Top-Right Text'}
	${menu args->li1_text name='Menu Item 1 Text'}
	${menu args->li1_href name='Menu Item 1 Link URL'}
	${menu args->li2_text name='Menu Item 2 Text'}
	${menu args->li2_href name='Menu Item 2 Link URL'}
	${menu args->li3_text name='Menu Item 3 Text'}
	${menu args->li3_href name='Menu Item 3 Link URL'}
	${menu args->li4_text name='Menu Item 4 Text'}
	${menu args->li4_href name='Menu Item 4 Link URL'}
	${menu args->li5_text name='Menu Item 5 Text'}
	${menu args->li5_href name='Menu Item 5 Link URL'}
${menu name='Picture', icon='image'}
	${menu block->with_img name='With Picture'}
	${menu args->img_src name='Picture URL', type='personyze_media_url'}
	${menu args->img_style name='Picture Size', type='css'}
${menu name='Text', icon='font'}
	${menu args->h1 name='Header'}
	${menu args->h1_style name='Header Style', type='css'}
	${menu args->p name='Text'}
${menu name='Button', icon='mouse-pointer'}
	${menu block->with_button name='With Button'}
	${menu args->button_text name='Button Text'}
	${menu args->button_href name='Button Link URL'}
	${menu args->button_style name='Menu Item Style', type='css'}
${menu name='Product image', icon='image'}
	${menu p->image_big_url name='Image', column_tags='image'}
	${menu args->img_size name='Product Image Size', type='css'}
	${menu p->cart_url name='Link target URL', column_tags='url, custom text'}
${menu name='Product name', icon='text-height'}
	${menu p->title name='Product name'}
	${menu args->name_style name='Product Name Alignment', type='css'}
	${menu args->p_title_style name='Product Name Style', type='css'}
	${menu block->with_desc name='With Description'}
	${menu p->description_long name='Product name'}
	${menu args->p_desc_style name='Product name style', type='css'}
${menu name='Second line', icon='text-height'}
	${menu block->price name='With price'}
	${menu args->before_price name='Text before price'}
	${menu args->after_price name='Text after price'}
	${menu args->price_style name='Price position', type='css'}
	${menu args->p_price_after_discount name='Price after discount'}
	${menu args->p_price_before_discount name='Price before discount'}
	${menu args->sale_style name='Price before discount: style', type='css', param='with_responsive=1'}
	${menu args->text_6 name='Button Text'}
	${menu args->text_6_style name='Text size', type='css'}
${menu name='Bottom Text', icon='font'}
	${menu args->p2 name='Text'}
${menu name='Button', icon='mouse-pointer'}
	${menu block->with_button2 name='With Button 1'}
	${menu args->button2_text name='Button 1 Text'}
	${menu args->button2_href name='Button Link URL'}
	${menu args->button2_style name='Menu Item Style', type='css'}
	${menu block->with_button3 name='With Button 2'}
	${menu args->button3_text name='Button 2 Text'}
	${menu args->button3_href name='Button Link URL'}
	${menu args->button3_style name='Menu Item Style', type='css'}
${menu name='Bottom Text 2', icon='font'}
	${menu args->p3 name='Text'}
```


## Email



```

<table style="border-collapse:collapse; background-color:white; ${args->wrapper_style:html:default('width:600px; max-width:90vw; font-family:sans-serif; color:#2E3234'):input_type(css):arg_name(Logo alignment):arg_section(0, 0, 'Logo', 'image')}">
	<tr>
		<td style="${args->logo_div_style:html:default('text-align:center'):input_type(css):arg_name(Logo alignment):arg_section(0, 3, 'Logo', 'image')}">
			<img src="${args->link_image:html:default('https://cdn.personyze.com/upload/362/185f3236b1b4ab52.png'):input_type(personyze_media_url):arg_name(Logo URL):arg_section(0, 1, 'Logo', 'image')}" style="${args->image_style:html:default('width:auto; height:auto'):input_type(css):arg_name(Logo size):arg_section(0, 2, 'Logo', 'image')}">
			<div style="box-sizing:border-box; ${args->hr:html:default('width:100%; height:1px; background-color:gray; margin:0.5em'):input_type(css):arg_name(Ruler):arg_section(0, 4, 'Logo', 'image')}"></div>
		</td>
	</tr>
	<tr>
		<td>
			<div style="${args->text_1_style:html:default('text-align:center; color:#7B7F7E; font-size:28px; padding-top:0.5em'):input_type(css):arg_name(Text size):arg_section(1, 2, 'Text', 'bars')}">
				${args->text_1:default('Hey,'):arg_name(Text):arg_section(1, 0, 'Text', 'bars')}
				${first_name:default(dear Customer)}
				${args->text_1a:default(you forgot something):arg_name(Text):arg_section(1, 1, 'Text', 'bars')}
			</div>
			<div style="${args->text_1b_style:html:default('text-align:center; font-size:18px; padding-bottom:2em'):input_type(css):arg_name(Text size):arg_section(1, 5, 'Text', 'bars')}">
				${args->text_1b:default(You left these items in your cart. Still want them?):arg_name(Text):arg_section(1, 4, 'Text', 'bars')}
			</div>
			<div style="box-sizing:border-box; ${args->hr:html}"></div>
		</td>
	</tr>
	<tr>
		<td>
			<table style="width:100%; border-collapse:collapse">
				${foreach products_interactions as p where p->interaction_status in ('extra') order by p->interaction_time desc limit 25}
					<tr>
						<td style="text-align:left">
							<a href="${p->cart_url:html:arg_name(Link target URL):arg_section(3, 1, 'Product image', 'image'):column_tags('url','custom text')}" target="_blank">
								<img src="${p->image_big_url:html:arg_name(Image):arg_section(3, 0, 'Product image', 'image'):column_tags(image)}" style="width:${args->img_width:html:default(200px):input_type(css_length):arg_name(Image width):arg_section(3, 2, 'Product image', 'image')}; height:${args->img_height:html:default(200px):input_type(css_length):arg_name(Image width):arg_section(3, 3, 'Product image', 'image')}" onerror="this.parentNode.style.display='none'">
							</a>
						</td>
						<td style="text-align:right">
							<a href="${p->cart_url:html}" target="_blank">
								<div style="${args->p_title_style:html:default('color:gray; font-size:18px; font-style:italic'):input_type(css):arg_name(Product name style):arg_section(4, 1, 'Product name', 'text-height')}">
									${p->title:arg_name(Product name):arg_section(4, 0, 'Product name', 'text-height')}
								</div>
							</a>
							${block->price:default(1):arg_name(With price):arg_section(5, 0, 'Second line', 'text-height')}
							<div style="${args->price_style:html:default('color:black; font-size:22px; font-weight:bold; color:#196590'):input_type(css):arg_name(Price position):arg_section(5, 4, 'Second line', 'text-height')}">
								${if p->price}
									${args->before_price:arg_name(Text before price):arg_section(5, 1, 'Second line', 'text-height')}
								${end}
								${p->price:sprintf($%s):arg_name(Price):arg_section(5, 2, 'Second line', 'text-height')}
								${if p->price}
									${args->after_price:arg_name(Text after price):arg_section(5, 3, 'Second line', 'text-height')}
								${end}
							</div>
							<a href="${p->cart_url:html}" target="_blank">
								<div style="display:inline-block; ${args->text_6_style:html:default('text-align:center; background-color:#196590; color:white; font-size:16px; font-weight:bold; padding:0.5em 1em'):input_type(css):arg_name(Text size):arg_section(1, 3, 'Text', 'bars')}">
									${args->text_6:default('BUY NOW >'):arg_name(Button Text):arg_section(5, 5, 'Second line', 'text-height')}
								</div>
							</a>
						</td>
					</tr>
					<tr>
						<td colspan="2">
							<div style="box-sizing:border-box; ${args->hr:html}"></div>
						</td>
					</tr>
				${end}
			</table>
		</td>
	</tr>
	<tr>
		<td style="text-align:center">
			<a href="${args->button_url:html:arg_name(Buy all target URL):arg_section(6, 0, 'Text', 'bars')}" target="_blank">
				<div style="display:inline-block; ${args->text_6b_style:html:default('text-align:center; background-color:white; color:#196590; border:solid 1px; font-size:16px; font-weight:bold; padding:0.5em 1em'):input_type(css):arg_name(Text size):arg_section(6, 1, 'Text', 'bars')}">
					${args->text_6b:default('BUY ALL ABOVE LISTED PRODUCTS >'):arg_name(Button Buy All Text):arg_section(6, 2, 'Text', 'bars')}
				</div>
			</a>
			<div style="box-sizing:border-box; ${args->hr:html}"></div>
		</td>
	</tr>
	<tr>
		<td style="text-align:center">
			<div style="${args->text_6c_style:html:default('text-align:center; color:#7B7F7E; font-size:18px; padding-top:0.5em'):input_type(css):arg_name(Text size):arg_section(7, 1, 'Text', 'bars')}">
				${args->text_6c:default(Have questions or need help with your purchases?):arg_name(Text):arg_section(7, 0, 'Text', 'bars')}
			</div>
			<table style="margin:auto">
				<tr>
					<td>
						<a style="display:inline-block; ${args->email_style:html:default('text-align:center; background-color:#F0F0F0; color:#196590; border:solid 1px; font-size:16px; font-weight:bold; padding:0.5em 2em; text-decoration:none; margin:0 1em'):input_type(css):arg_name(Email button style):arg_section(8, 1, 'Email', 'envelope')}">
							${args->text8:html:default('+1(844) 111-1111'):arg_name(Phone):arg_section(8, 0, 'Email', 'envelope')}
						</a>
					</td>
					<td>
						<a href="mailto:${args->email:html:default('youremailaddress@here.com'):arg_name(Email address):arg_section(8, 3, 'Email', 'envelope')}?subject=${args->subject:html:default(Contact form):arg_name(Default subject):arg_section(8, 4, 'Email', 'envelope')}" style="display:inline-block; ${args->email_style:html}">
							${args->text7:html:default(Email Us):arg_name(Email text):arg_section(8, 2, 'Email', 'envelope')}
						</a>
					</td>
				</tr>
			</table>
			<div style="box-sizing:border-box; ${args->hr:html}"></div>
		</td>
	</tr>
	<tr>
		<td style="text-align:center">
			<div style="display:flex; flex-wrap:wrap; justify-content:space-around; align-items:center">
				<div>
					<a href="${args->li_1_href:html:default('#'):arg_name(Menu Item 1 URL):arg_section(2, 1, 'Bottom Menu', 'bars')}">
						${args->li_1:default(Menu Item 1):arg_name(Menu Item 1):arg_section(2, 0, 'Bottom Menu', 'bars')}
					</a>
				</div>
				<div>
					<a href="${args->li_2_href:html:default('#'):arg_name(Menu Item 2 URL):arg_section(2, 3, 'Bottom Menu', 'bars')}">
						${args->li_2:default(Menu Item 2):arg_name(Menu Item 2 Text):arg_section(2, 2, 'Bottom Menu', 'bars')}
					</a>
				</div>
				<div>
					<a href="${args->li_3_href:html:default('#'):arg_name(Menu Item 3 URL):arg_section(2, 5, 'Bottom Menu', 'bars')}">
						${args->li_3:default(Menu Item 3):arg_name(Menu Item 3 Text):arg_section(2, 4, 'Bottom Menu', 'bars')}
					</a>
				</div>
				<div>
					<a href="${args->li_4_href:html:default('#'):arg_name(Menu Item 4 URL):arg_section(2, 7, 'Bottom Menu', 'bars')}">
						${args->li_4:default(Menu Item 4):arg_name(Menu Item 4 Text):arg_section(2, 6, 'Bottom Menu', 'bars')}
					</a>
				</div>
				<div>
					<a href="${args->li_5_href:html:default('#'):arg_name(Menu Item 5 URL):arg_section(2, 9, 'Bottom Menu', 'bars')}">
						${args->li_5:default(Menu Item 5):arg_name(Menu Item 5 Text):arg_section(2, 8, 'Bottom Menu', 'bars')}
					</a>
				</div>
				<div>
					<a href="${args->li_6_href:html:default('#'):arg_name(Menu Item 6 URL):arg_section(2, 11, 'Bottom Menu', 'bars')}">
						${args->li_6:default(Menu Item 6):arg_name(Menu Item 6 Text):arg_section(2, 10, 'Bottom Menu', 'bars')}
					</a>
				</div>
			</div>
			<div style="box-sizing:border-box; ${args->hr:html}"></div>
		</td>
	</tr>
</table>
</body>
</html>
```


## Email



```

<table style="border-collapse:collapse; background-color:white; font-size:14px">
	<tr>
		<td style="text-align:center; padding:0.8em">
			${args->line_1:default(Enjoy 10% off your next order -):arg_name(Text):arg_section(0, 0, 'Line 1', 'bars')}
			<a href="${args->line_1_href:html:default('#'):arg_name(Link target URL):arg_section(0, 1, 'Line 1', 'bars')}" target="_blank" style="${args->line_1_a_style:html:default('color:black; text-decoration:none'):input_type(css):arg_name(Link style):arg_section(0, 2, 'Line 1', 'bars')}">
				${args->line_1_a:default(view online):arg_name(Link text):arg_section(0, 3, 'Line 1', 'bars')}
			</a>
		</td>
	</tr>
	<tr>
		<td style="text-align:center; background-color:#ECECEC; font-size:16px; padding:0.8em">
			<span style="padding:0 1em">
				<span style="${args->line_2_style:html:default('color:#E40E7D'):input_type(css):arg_name(Link style):arg_section(1, 0, 'Line 2', 'bars')}">
					${args->line_2_1:default('✔'):arg_name(Link text):arg_section(1, 1, 'Line 2', 'bars')}
				</span>
				${args->line_2_1t:default(12 Months Warranty):arg_name(Link text):arg_section(1, 2, 'Line 2', 'bars')}
			</span>
			<span style="padding:0 1em">
				<span style="${args->line_2_style:html}">
					${args->line_2_2:default('✔ FREE'):arg_name(Link text):arg_section(1, 3, 'Line 2', 'bars')}
				</span>
				${args->line_2_2t:default(Returns):arg_name(Link text):arg_section(1, 4, 'Line 2', 'bars')}
			</span>
			<span style="padding:0 1em">
				<span style="${args->line_2_style:html}">
					${args->line_2_3:default('✔ FREE'):arg_name(Link text):arg_section(1, 5, 'Line 2', 'bars')}
				</span>
				${args->line_2_3t:default(Next Day Delivery):arg_name(Link text):arg_section(1, 6, 'Line 2', 'bars')}
			</span>
		</td>
	</tr>
	<tr>
		<td style="text-align:center">
			<img src="${args->link_image:html:default('https://cdn.personyze.com/upload/362/185f3236b1b4ab52.png'):input_type(personyze_media_url):arg_name(Image URL):arg_section(2, 0, 'Image 1', 'image')}" style="${args->image_style:html:default('width: 300px;
height: auto;'):input_type(css):arg_name(Image size):arg_section(2, 1, 'Image 1', 'image')}">
		</td>
	</tr>
	<tr>
		<td style="text-align:center">
			<img src="${args->link_image2:html:default('https://cdn.personyze.com/upload/362/9021b00a37b389c0.jpeg'):input_type(personyze_media_url):arg_name(Image URL):arg_section(3, 0, 'Image 2', 'image')}" style="${args->image_style2:html:default('width: 800px;'):input_type(css):arg_name(Image size):arg_section(3, 1, 'Image 2', 'image')}">
		</td>
	</tr>
	<tr>
		<td>
			<br>
		</td>
	</tr>
	<tr>
		<td style="text-align:center; background-color:#ECECEC; color:#747474; font-size:32px; padding:0.3em">
			${args->coupon:default(Use code):arg_name(Text):arg_section(4, 0, 'Line 3', 'bars')}
			<span style="${args->line_2_style:html}">
				${args->coupon2:default(THANKYOU10):arg_name(Text):arg_section(4, 1, 'Line 3', 'bars')}
			</span>
			${args->coupon3:default(at checkout):arg_name(Text):arg_section(4, 2, 'Line 3', 'bars')}
			<div>
				<a href="${args->coupon_a:html:default('#'):arg_name(Link target URL):arg_section(4, 3, 'Line 3', 'bars')}" target="_blank" style="display:inline-block; ${args->coupon_a_style:html:default('color: white;
background-color: rgb(14, 228, 74);
border-radius: 12px;
padding-top: 0.2em;
padding-right: 0.8em;
padding-bottom: 0.2em;
padding-left: 0.8em;
text-decoration: none;
box-shadow: 1px 2px 1px rgb(239, 231, 231);
margin: 0.4em;'):input_type(css):arg_name(Link style):arg_section(4, 4, 'Line 3', 'bars')}">
					${args->coupon_a_text:default(Shop Now):arg_name(Link text):arg_section(4, 5, 'Line 3', 'bars')}
				</a>
			</div>
		</td>
	</tr>
	<tr>
		<td style="text-align:center; background-color:#6F6E6F; color:white; font-size:16px; padding:0.3em">
			We recommend for you
		</td>
	</tr>
	<tr>
		<td style="padding:1.5em 0">
			<table style="width:100%; border-collapse:collapse">
				<tr>
					${foreach recom_products as p limit 25}
						<td style="text-align:center">
							<a href="${p->cart_url:html:arg_name(Link target URL):arg_section(5, 1, 'Product image', 'image'):column_tags('url','custom text')}" target="_blank">
								<img src="${p->image_big_url:html:arg_name(Image):arg_section(5, 0, 'Product image', 'image'):column_tags(image)}" style="width:${args->img_width:html:default(200px):input_type(css_length):arg_name(Image width):arg_section(5, 2, 'Product image', 'image')}; height:${args->img_height:html:default(200px):input_type(css_length):arg_name(Image width):arg_section(5, 3, 'Product image', 'image')}" onerror="this.parentNode.style.display='none'">
								<div style="${args->p_title_style:html:default('color:black; font-size:16px'):input_type(css):arg_name(Product name style):arg_section(6, 1, 'Product name', 'text-height')}">
									${p->title:arg_name(Product name):arg_section(6, 0, 'Product name', 'text-height')}
								</div>
								${block->price:default(1):arg_name(With price):arg_section(7, 0, 'Second line', 'text-height')}
								<div style="${args->price_style:html:default('color:black; font-size:16px; font-weight:bold'):input_type(css):arg_name(Price position):arg_section(7, 4, 'Second line', 'text-height')}">
									${if p->price}
										${args->before_price:arg_name(Text before price):arg_section(7, 1, 'Second line', 'text-height')}
									${end}
									${p->price:sprintf($%s):arg_name(Price):arg_section(7, 2, 'Second line', 'text-height')}
									${if p->price}
										${args->after_price:arg_name(Text after price):arg_section(7, 3, 'Second line', 'text-height')}
									${end}
								</div>
							</a>
						</td>
					${end}
				</tr>
			</table>
		</td>
	</tr>
	<tr>
		<td style="text-align:center; background-color:#ECECEC; color:#747474; font-size:32px; padding:0.3em">
			${args->line_4:default('Keep an eye on our <b>latest ranges</b> and <b>special offer</b> prices...'):arg_name(Text):arg_section(8, 0, 'Line 4', 'bars')}
		</td>
	</tr>
</table>
</body>
</html>
```


## Email



```
<div style="${args->style:html:default('border: none;
text-align: center;
width: 600px;
background-color: white;
color: #0A4A34;
font-size: 14px;
margin-top: 1px;
margin-right: auto;
margin-bottom: 1px;
margin-left: auto;')}">
	<table style="width:100%; border-collapse:collapse; border:none; ${args->logo_table_style:html:default('border-bottom: solid #4c6330 4px;')}">
		<tr>
			${block->with_logo:default(1)}
			<td style="${args->logo_td_style:html:default('vertical-align: middle;
text-align: center;
padding-top: 1em;
padding-right: 2em;
padding-bottom: 1em;
padding-left: 0em;')}">
				<img src="${args->logo_src:html:default('https://cdn.personyze.com/upload/362/18a94c1299224ec8.png')}" style="border:none; ${args->logo_img_style:html:default('width: 270px;
height: auto;')}">
			</td>
			${block->with_top_right:default(0)}
			<td style="${args->top_right_td_style:html}">
				${args->top_right}
			</td>
		</tr>
	</table>
	<table style="width:100%; border-collapse:collapse; border:none">
		<tr>
			${block->li1:default(0)}
			<td style="${args->li:html:default('vertical-align:middle; text-align:center; padding:0.6em; font-weight:bold; color:black')}">
				<a href="${args->li1_href:html}" target="_blank" style="color:inherit; text-decoration:inherit">${args->li1_text}</a>
			</td>
			${block->li2:default(1)}
			<td style="${args->li:html}">
				<a href="${args->li2_href:html}" target="_blank" style="color:inherit; text-decoration:inherit">${args->li2_text:default(Homepage)}</a>
			</td>
			${block->li3:default(1)}
			<td style="${args->li:html}">
				<a href="${args->li3_href:html}" target="_blank" style="color:inherit; text-decoration:inherit">${args->li3_text:default(Cart)}</a>
			</td>
			${block->li4:default(1)}
			<td style="${args->li:html}">
				<a href="${args->li4_href:html}" target="_blank" style="color:inherit; text-decoration:inherit">${args->li4_text:default(Alert)}</a>
			</td>
			${block->li5:default(0)}
			<td style="${args->li:html}">
				<a href="${args->li5_href:html}" target="_blank" style="color:inherit; text-decoration:inherit">${args->li5_text}</a>
			</td>
		</tr>
	</table>
	${block->with_img:default(1)}
	<img src="${args->img_src:html}" style="border:none; ${args->img_style:html:default('width: 0px;
height: auto;')}">
	<h1 style="${args->h1_style:html:default('font-size: 0px;')}">
		${args->h1}
	</h1>
	${args->p:default('<p style="margin:0 4em">Free text &nbsp;Free text &nbsp;Free text&nbsp;Free text&nbsp;<br />
<br />
&nbsp;Free text &nbsp;Free text &nbsp;Free text&nbsp;</p>
')}
	${block->with_button:default(0)}
	<a href="${args->button_href:html}" target="_blank" style="display:inline-block; ${args->button_style:html}">
		${args->button_text}
	</a>
	<table style="width:100%; border-collapse:collapse">
		${foreach recom_products as p limit 3}
			<tr>
				<td style="text-align:left">
					<a href="${p->cart_url:html}" target="_blank">
						<img src="${p->image_big_url:html}" style="${args->img_size:html:default('width: 100px;
height: auto;
margin-top: 0px;
margin-right: 0px;
margin-bottom: 0px;
margin-left: 33px;')}">
					</a>
				</td>
				<td style="text-align:right; vertical-align:top">
					<div style="${args->name_style:html:default('text-align: right;
margin-top: 24px;
margin-right: 11px;
margin-bottom: 0px;
margin-left: 0px;
border: solid 0px #ededed;
border-width: 0px;')}">
						<a href="${p->cart_url:html}" target="_blank" style="text-decoration:none">
							<div style="${args->p_title_style:html:default('margin-top: 24px;
margin-right: 0;
margin-bottom: 20px;
margin-left: 0px;
font-family: Roboto, sans-serif;
text-align: left;
text-transform: none;
font-weight: 800;
font-size: 1.18571429em;
line-height: 1.71428571em;
color: rgba(0, 0, 0, 0.7);
min-width: sel(100px, 50px);
text-decoration: none;')}">
								${p->title}
							</div>
							${block->with_desc:default(1)}
							<div style="${args->p_desc_style:html:default('margin-top: auto;
border-top: .0625rem solid #ededed;
padding-top: 1.25rem;
padding-right: 1.5rem;
padding-bottom: 1.25rem;
padding-left: 0rem;
color: #9b9b9b;
text-align: left;
font-size: 018px;
font-weight: lighter;
font-style: normal;
text-decoration: none;')}">
								${p->description_short}
							</div>
						</a>
						<table style="width:100%; border-collapse:collapse; margin-top:1em">
							<tr>
								${block->price:default(1)}
								<td style="${args->price_style:html:default('font-size: 0px;
font-weight: bold;
color: red;
padding-right: 0px;')}">
									${if p->price_before_discount}
                                        ${args->before_price}
                                        ${if p->price_after_discount and p->price_after_discount < p->price_before_discount}
                                            <span style="${args->sale_style:html:default('text-decoration:line-through')}">
                                                ${args->p_price_before_discount:default('&pound;${p->price_before_discount:price('''')}')}
                                            </span>
                                            ${args->p_price_after_discount:default('&pound;${p->price_after_discount:price('''')}')}
                                        ${end}
                                        ${if not p->price_after_discount or p->price_after_discount >= p->price_before_discount}
                                            ${args->p_price_before_discount}
                                        ${end}
                                        ${args->after_price}
                                    ${end}
								</td>
								<td>
									<a href="${p->cart_url:html}" target="_blank" style="display:inline-block; text-decoration:none; ${args->text_6_style:html:default('background-color: #e23943;
color: white;
padding-top: 11px;
padding-right: 2.5rem;
padding-bottom: 11px;
padding-left: 2.5rem;
margin-top: 1em;
margin-right: 1em;
margin-bottom: 2em;
margin-left: 1em;
text-decoration: none;
font-weight: bold;
border-radius: 2.8125rem;')}">
										${args->text_6:default(View)}
									</a>
								</td>
							</tr>
						</table>
					</div>
				</td>
			</tr>
			<tr>
				<td colspan="2">
					<div style="box-sizing:border-box; ${args->hr:html}"></div>
				</td>
			</tr>
		${end}
	</table>
	${args->p2:default('<p style="margin:4em 4em 2em 4em"><span style="color:#0a4a34;">Staat jouw gewenste vacature er niet bij? Bekijk dan onze vacature pagina.&nbsp;</span></p>
')}
	${block->with_button2:default(0)}
	<a href="${args->button2_href:html}" target="_blank" style="display:inline-block; ${args->button2_style:html}">
		${args->button2_text}
	</a>
	${block->with_button3:default(0)}
	<a href="${args->button3_href:html}" target="_blank" style="display:inline-block; ${args->button3_style:html}">
		${args->button3_text}
	</a>
	<div>
		<div style="display:inline-block">
			${args->p3:default('<br />
&nbsp;')}
		</div>
	</div>
	${block->with_button4:default(1)}
	<div>
		<div style="${args->button4_text_style:html:default('padding-top: 0.6em;
padding-right: 1.2em;
padding-bottom: 0.6em;
padding-left: 1.2em;
margin-top: 2em;
margin-right: 0;
margin-bottom: 1em;
margin-left: 0;
font-size: 12px;')}">
			${args->button4_line_text:default(Text)}
		</div>
		<a href="http://pic.personyze.com/unsubscribe/k=${action_key:html}/u=${id:html}" target="_blank" style="display:inline-block; ${args->button4_style:html:default('background-color: rgba(178, 144, 144, 0.62);
color: white;
padding-top: 0.6em;
padding-right: 1.2em;
padding-bottom: 0.6em;
padding-left: 1.2em;
margin-top: 1em;
margin-right: 0;
margin-bottom: 2em;
margin-left: 0;
text-decoration: none;
font-weight: bold;')}">
			${args->button4_text:default(Unsubscribe)}
		</a>
	</div>
</div>

${menu name='Frame', icon='th-large'}
	${menu args->style name='Style', type='css'}
${menu name='Logo Line', icon='image'}
	${menu block->with_logo name='With Logo'}
	${menu block->li2 name='With Menu Item 2'}
	${menu block->li3 name='With Menu Item 3'}
	${menu block->li4 name='With Menu Item 4'}
	${menu block->li5 name='With Menu Item 5'}
	${menu args->logo_src name='Logo URL', type='personyze_media_url'}
	${menu args->logo_img_style name='Logo Size', type='css'}
	${menu args->logo_td_style name='Logo Position', type='css'}
	${menu block->with_top_right name='With Top-Right Text'}
	${menu args->top_right_td_style name='Top-Right Text Position', type='css'}
	${menu args->logo_table_style name='Logo Position', type='css'}
${menu name='Top Menu', icon='bars'}
	${menu block->li1 name='With Menu Item 1'}
	${menu args->li name='Menu Item Style', type='css'}
	${menu args->top_right name='Top-Right Text'}
	${menu args->li1_text name='Menu Item 1 Text'}
	${menu args->li1_href name='Menu Item 1 Link URL'}
	${menu args->li2_text name='Menu Item 2 Text'}
	${menu args->li2_href name='Menu Item 2 Link URL'}
	${menu args->li3_text name='Menu Item 3 Text'}
	${menu args->li3_href name='Menu Item 3 Link URL'}
	${menu args->li4_text name='Menu Item 4 Text'}
	${menu args->li4_href name='Menu Item 4 Link URL'}
	${menu args->li5_text name='Menu Item 5 Text'}
	${menu args->li5_href name='Menu Item 5 Link URL'}
${menu name='Picture', icon='image'}
	${menu block->with_img name='With Picture'}
	${menu args->img_src name='Picture URL', type='personyze_media_url'}
	${menu args->img_style name='Picture Size', type='css'}
${menu name='Text', icon='font'}
	${menu args->h1 name='Header'}
	${menu args->h1_style name='Header Style', type='css'}
	${menu args->p name='Text'}
${menu name='Button', icon='mouse-pointer'}
	${menu block->with_button name='With Button'}
	${menu args->button_text name='Button Text'}
	${menu args->button_href name='Button Link URL'}
	${menu args->button_style name='Menu Item Style', type='css'}
${menu name='Product image', icon='image'}
	${menu p->image_big_url name='Image', column_tags='image'}
	${menu args->img_size name='Product Image Size', type='css'}
	${menu p->cart_url name='Link target URL', column_tags='url, custom text'}
${menu name='Product name', icon='text-height'}
	${menu p->title name='Product name'}
	${menu args->name_style name='Product Name Alignment', type='css'}
	${menu args->p_title_style name='Product Name Style', type='css'}
	${menu block->with_desc name='With Description'}
	${menu p->description_short name='Product name'}
	${menu args->p_desc_style name='Product name style', type='css'}
${menu name='Second line', icon='text-height'}
	${menu block->price name='With price'}
	${menu args->before_price name='Text before price'}
	${menu args->after_price name='Text after price'}
	${menu args->price_style name='Price position', type='css'}
	${menu args->sale_style name='Price before discount: style', type='css', param='with_responsive=1'}
	${menu args->text_6 name='Button Text'}
	${menu args->text_6_style name='Text size', type='css'}
	${menu args->p_price_after_discount name='Price after discount'}
	${menu args->p_price_before_discount name='Price before discount'}
${menu name='Bottom Text', icon='font'}
	${menu args->p2 name='Text'}
${menu name='Button', icon='mouse-pointer'}
	${menu block->with_button2 name='With Button 1'}
	${menu args->button2_text name='Button 1 Text'}
	${menu args->button2_href name='Button Link URL'}
	${menu args->button2_style name='Menu Item Style', type='css'}
	${menu block->with_button3 name='With Button 2'}
	${menu args->button3_text name='Button 2 Text'}
	${menu args->button3_href name='Button Link URL'}
	${menu args->button3_style name='Menu Item Style', type='css'}
${menu name='Bottom Text 2', icon='font'}
	${menu args->p3 name='Text'}
${menu name='With Unsubscribe', icon='ban'}
	${menu block->with_button4 name='With Button 1'}
	${menu args->button4_line_text name='Text Line'}
	${menu args->button4_text_style name='Text Line Style', type='css'}
	${menu args->button4_text name='Button Text'}
	${menu args->button4_style name='Button Style', type='css'}
```


## Email



```
<div style="${args->style:html:default('border: none;
text-align: center;
width: 800px;
background-color: white;
color: #0A4A34;
font-size: 14px;
margin-top: 1px;
margin-right: auto;
margin-bottom: 1px;
margin-left: auto;'):input_type(css):arg_name(Style):arg_section(0, 0, 'Frame', 'th-large')}">
	<table style="width:100%; border-collapse:collapse; border:none; ${args->logo_table_style:html:default('border-bottom:solid #FEFDA4 4px'):input_type(css):arg_name(Logo Position):arg_section(1, 10, 'Logo Line', 'image')}">
		<tr>
			${block->with_logo:default(1):arg_name(With Logo):arg_section(1, 0, 'Logo Line', 'image')}
			<td style="${args->logo_td_style:html:default('vertical-align: middle;
text-align: center;
padding-top: 1em;
padding-right: 2em;
padding-bottom: 1em;
padding-left: 0em;'):input_type(css):arg_name(Logo Position):arg_section(1, 7, 'Logo Line', 'image')}">
				<img src="${args->logo_src:html:default('https://cdn.e-marketer.io/upload/362/185f3236b1b4ab52.png'):input_type(emarketer_media_url):arg_name(Logo URL):arg_section(1, 5, 'Logo Line', 'image')}" style="border:none; ${args->logo_img_style:html:default('width: 270px;
height: auto;'):input_type(css):arg_name(Logo Size):arg_section(1, 6, 'Logo Line', 'image')}">
			</td>
			${block->with_top_right:default(1):arg_name(With Top-Right Text):arg_section(1, 8, 'Logo Line', 'image')}
			<td style="${args->top_right_td_style:html:default('vertical-align: middle;
text-align: left;
padding-top: 0em;
padding-right: 1em;
padding-bottom: 0em;
padding-left: 0em;'):input_type(css):arg_name(Top-Right Text Position):arg_section(1, 9, 'Logo Line', 'image')}">
				${args->top_right:default('<div><strong>EUROPA&#39;S GROOTSTE<br />
OUTDOOR LIVING MALL</strong></div>
'):arg_name(Top-Right Text):arg_section(2, 2, 'Top Menu', 'bars')}
			</td>
		</tr>
	</table>
	<table style="width:100%; border-collapse:collapse; border:none">
		<tr>
			${block->li1:default(1):arg_name(With Menu Item 1):arg_section(2, 0, 'Top Menu', 'bars')}
			<td style="${args->li:html:default('vertical-align:middle; text-align:center; padding:0.6em; font-weight:bold; color:black'):input_type(css):arg_name(Menu Item Style):arg_section(2, 1, 'Top Menu', 'bars')}">
				<a href="${args->li1_href:html:arg_name(Menu Item 1 Link URL):arg_section(2, 4, 'Top Menu', 'bars')}" target="_blank" style="color:inherit; text-decoration:inherit">${args->li1_text:default(SHOP):arg_name(Menu Item 1 Text):arg_section(2, 3, 'Top Menu', 'bars')}</a>
			</td>
			${block->li2:default(1):arg_name(With Menu Item 2):arg_section(1, 1, 'Logo Line', 'image')}
			<td style="${args->li:html}">
				<a href="${args->li2_href:html:arg_name(Menu Item 2 Link URL):arg_section(2, 6, 'Top Menu', 'bars')}" target="_blank" style="color:inherit; text-decoration:inherit">${args->li2_text:default(BLOGS):arg_name(Menu Item 2 Text):arg_section(2, 5, 'Top Menu', 'bars')}</a>
			</td>
			${block->li3:default(1):arg_name(With Menu Item 3):arg_section(1, 2, 'Logo Line', 'image')}
			<td style="${args->li:html}">
				<a href="${args->li3_href:html:arg_name(Menu Item 3 Link URL):arg_section(2, 8, 'Top Menu', 'bars')}" target="_blank" style="color:inherit; text-decoration:inherit">${args->li3_text:default(STORE):arg_name(Menu Item 3 Text):arg_section(2, 7, 'Top Menu', 'bars')}</a>
			</td>
			${block->li4:default(1):arg_name(With Menu Item 4):arg_section(1, 3, 'Logo Line', 'image')}
			<td style="${args->li:html}">
				<a href="${args->li4_href:html:arg_name(Menu Item 4 Link URL):arg_section(2, 10, 'Top Menu', 'bars')}" target="_blank" style="color:inherit; text-decoration:inherit">${args->li4_text:default(SHOWROOM):arg_name(Menu Item 4 Text):arg_section(2, 9, 'Top Menu', 'bars')}</a>
			</td>
			${block->li5:default(1):arg_name(With Menu Item 5):arg_section(1, 4, 'Logo Line', 'image')}
			<td style="${args->li:html}">
				<a href="${args->li5_href:html:arg_name(Menu Item 5 Link URL):arg_section(2, 12, 'Top Menu', 'bars')}" target="_blank" style="color:inherit; text-decoration:inherit">${args->li5_text:default(CONTACT):arg_name(Menu Item 5 Text):arg_section(2, 11, 'Top Menu', 'bars')}</a>
			</td>
		</tr>
	</table>
	${block->with_img:default(1):arg_name(With Picture):arg_section(3, 0, 'Picture', 'image')}
	<img src="${args->img_src:html:default('https://cdn.e-marketer.io/upload/4054/e648f93960a53241.jpeg'):input_type(emarketer_media_url):arg_name(Picture URL):arg_section(3, 1, 'Picture', 'image')}" style="border:none; ${args->img_style:html:default('width: 100%;
height: auto;'):input_type(css):arg_name(Picture Size):arg_section(3, 2, 'Picture', 'image')}">
	<h1 style="${args->h1_style:html:default('font-size: 0px;'):input_type(css):arg_name(Header Style):arg_section(4, 1, 'Text', 'font')}">
		${args->h1:default('<img src="https://cdn.e-marketer.io/upload/4054/b57f02953130159f.png" />'):arg_name(Header):arg_section(4, 0, 'Text', 'font')}
	</h1>
	${args->p:default('<p style="margin:0 4em"><font face="Verdana, Geneva, sans-serif" size="3">text text</font></p>
'):arg_name(Text):arg_section(4, 2, 'Text', 'font')}
	${block->with_button:default(1):arg_name(With Button):arg_section(5, 0, 'Button', 'mouse-pointer')}
	<a href="${args->button_href:html:default('https://www.fonteyn.nl/wishlist/index/index/wishlist_id/${wishlist_id}'):arg_name(Button Link URL):arg_section(5, 2, 'Button', 'mouse-pointer')}" target="_blank" style="display:inline-block; ${args->button_style:html:default('background-color:#0A4A34; color:white; padding:0.6em 1.2em; margin:1em; text-decoration:none; font-weight:bold; margin-bottom:2em'):input_type(css):arg_name(Menu Item Style):arg_section(5, 3, 'Button', 'mouse-pointer')}">
		${args->button_text:default(Go to Cart):arg_name(Button Text):arg_section(5, 1, 'Button', 'mouse-pointer')}
	</a>
	<table style="width:100%; border-collapse:collapse">
		${foreach products_interactions as p where p->interaction_status in ('viewed') order by p->interaction_time desc limit 3}
			<tr>
				<td style="text-align:left">
					<a href="${p->cart_url:html:arg_name(Link target URL):arg_section(6, 2, 'Product image', 'image'):column_tags('url','custom text')}" target="_blank">
						<img src="${p->image_big_url:html:arg_name(Image):arg_section(6, 0, 'Product image', 'image'):column_tags(image)}" style="${args->img_size:html:default('width: 200px;
height: auto;
margin: 10px;'):input_type(css):arg_name(Product Image Size):arg_section(6, 1, 'Product image', 'image')}">
					</a>
				</td>
				<td style="text-align:right; vertical-align:top">
					<div style="${args->name_style:html:default('text-align:left; margin:10px'):input_type(css):arg_name(Product Name Alignment):arg_section(7, 1, 'Product name', 'text-height')}">
						<a href="${p->cart_url:html}" target="_blank" style="text-decoration:none">
							<div style="${args->p_title_style:html:default('font-size: 18px;
font-weight: bold;
color: #0A4A34;'):input_type(css):arg_name(Product Name Style):arg_section(7, 2, 'Product name', 'text-height')}">
								${p->title:arg_name(Product name):arg_section(7, 0, 'Product name', 'text-height')}
							</div>
							${block->with_desc:default(1):arg_name(With Description):arg_section(7, 3, 'Product name', 'text-height')}
							<div style="${args->p_desc_style:html:default('font-size: 18px;
color: #0A4A34;'):input_type(css):arg_name(Product name style):arg_section(7, 5, 'Product name', 'text-height')}">
								${p->description_long:arg_name(Product name):arg_section(7, 4, 'Product name', 'text-height')}
							</div>
						</a>
						<table style="width:100%; border-collapse:collapse; margin-top:1em">
							<tr>
								${block->price:default(1):arg_name(With price):arg_section(8, 0, 'Second line', 'text-height')}
								<td style="${args->price_style:html:default('font-size:22px; font-weight:bold; color:red; padding-right:10px'):input_type(css):arg_name(Price position):arg_section(8, 4, 'Second line', 'text-height')}">
									${if p->price}
										${args->before_price:arg_name(Text before price):arg_section(8, 1, 'Second line', 'text-height')}
										${if p->sale_price and p->sale_price < p->price}
											${p->sale_price:truncate('2'):sprintf('€%s'):arg_name(Price):arg_section(8, 2, 'Second line', 'text-height')}
											<span style="${args->sale_style:html:default('color:gray; text-decoration:line-through; font-size:85%'):input_type(css):input_props('with_responsive=1'):arg_name('Price before discount: style'):arg_section(8, 6, 'Second line', 'text-height')}">
												${p->price:truncate('2'):sprintf('€%s'):arg_name(Price):arg_section(8, 5, 'Second line', 'text-height')}
											</span>
										${end}
										${if not p->sale_price or p->sale_price >= p->price}
											${p->price:truncate('2'):sprintf('€%s')}
										${end}
										${args->after_price:arg_name(Text after price):arg_section(8, 3, 'Second line', 'text-height')}
									${end}
								</td>
								<td>
									<a href="${p->cart_url:html}" target="_blank" style="display:inline-block; text-decoration:none; ${args->text_6_style:html:default('text-align:center; background-color:#0A4A34; color:white; font-size:16px; font-weight:bold; padding:0.5em 1em'):input_type(css):arg_name(Text size):arg_section(8, 8, 'Second line', 'text-height')}">
										${args->text_6:default(View):arg_name(Button Text):arg_section(8, 7, 'Second line', 'text-height')}
									</a>
								</td>
							</tr>
						</table>
					</div>
				</td>
			</tr>
			<tr>
				<td colspan="2">
					<div style="box-sizing:border-box; ${args->hr:html}"></div>
				</td>
			</tr>
		${end}
	</table>
	${args->p2:default('<p style="margin:4em 4em 2em 4em"><span style="color:#0a4a34;">Text text</span></p>
'):arg_name(Text):arg_section(9, 0, 'Bottom Text', 'font')}
	${block->with_button2:default(1):arg_name(With Button 1):arg_section(10, 0, 'Button', 'mouse-pointer')}
	<a href="${args->button2_href:html:default('https://www.fonteyn.nl/'):arg_name(Button Link URL):arg_section(10, 2, 'Button', 'mouse-pointer')}" target="_blank" style="display:inline-block; ${args->button2_style:html:default('background-color:#0A4A34; color:white; padding:0.6em 1.2em; margin:1em; text-decoration:none; font-weight:bold'):input_type(css):arg_name(Menu Item Style):arg_section(10, 3, 'Button', 'mouse-pointer')}">
		${args->button2_text:default(Homopage):arg_name(Button 1 Text):arg_section(10, 1, 'Button', 'mouse-pointer')}
	</a>
	${block->with_button3:default(1):arg_name(With Button 2):arg_section(10, 4, 'Button', 'mouse-pointer')}
	<a href="${args->button3_href:html:default('https://www.fonteyn.nl/contact/'):arg_name(Button Link URL):arg_section(10, 6, 'Button', 'mouse-pointer')}" target="_blank" style="display:inline-block; ${args->button3_style:html:default('background-color:#0A4A34; color:white; padding:0.6em 1.2em; margin:1em; text-decoration:none; font-weight:bold'):input_type(css):arg_name(Menu Item Style):arg_section(10, 7, 'Button', 'mouse-pointer')}">
		${args->button3_text:default(Cart):arg_name(Button 2 Text):arg_section(10, 5, 'Button', 'mouse-pointer')}
	</a>
	<div>
		<div style="display:inline-block">
			${args->p3:default('<br />
&nbsp;'):arg_name(Text):arg_section(11, 0, 'Bottom Text 2', 'font')}
		</div>
	</div>
	${block->with_button4:default(1):arg_name(With Button 1):arg_section(12, 0, 'With Unsubscribe', 'ban')}
	<div>
		<div style="${args->button4_text_style:html:default('padding-top: 0.6em;
padding-right: 1.2em;
padding-bottom: 0.6em;
padding-left: 1.2em;
margin-top: 2em;
margin-right: 0;
margin-bottom: 1em;
margin-left: 0;
font-size: 20px;'):input_type(css):arg_name(Text Line Style):arg_section(12, 2, 'With Unsubscribe', 'ban')}">
			${args->button4_line_text:default(Unsubscribe):arg_name(Text Line):arg_section(12, 1, 'With Unsubscribe', 'ban')}
		</div>
		<a href="http://pic.emarketer.com/unsubscribe/k=${action_key:html}/u=${id:html}" target="_blank" style="display:inline-block; ${args->button4_style:html:default('background-color:#0A4A34; color:white; padding:0.6em 1.2em; margin:1em 0 2em; text-decoration:none; font-weight:bold'):input_type(css):arg_name(Button Style):arg_section(12, 4, 'With Unsubscribe', 'ban')}">
			${args->button4_text:default('Unsubscribe &gt;'):arg_name(Button Text):arg_section(12, 3, 'With Unsubscribe', 'ban')}
		</a>
	</div>
</div>
```


## Email



```
<div style="${args->style:html:default('border: none;
text-align: center;
width: 800px;
background-color: white;
color: #0A4A34;
font-size: 14px;
margin-top: 1px;
margin-right: auto;
margin-bottom: 1px;
margin-left: auto;'):input_type(css):arg_name(Style):arg_section(0, 0, 'Frame', 'th-large')}">
	<table style="width:100%; border-collapse:collapse; border:none; ${args->logo_table_style:html:default('border-bottom:solid #FEFDA4 4px'):input_type(css):arg_name(Logo Position):arg_section(1, 10, 'Logo Line', 'image')}">
		<tr>
			${block->with_logo:default(1):arg_name(With Logo):arg_section(1, 0, 'Logo Line', 'image')}
			<td style="${args->logo_td_style:html:default('vertical-align: middle;
text-align: center;
padding-top: 1em;
padding-right: 2em;
padding-bottom: 1em;
padding-left: 0em;'):input_type(css):arg_name(Logo Position):arg_section(1, 7, 'Logo Line', 'image')}">
				<img src="${args->logo_src:html:default('https://cdn.e-marketer.io/upload/362/185f3236b1b4ab52.png'):input_type(emarketer_media_url):arg_name(Logo URL):arg_section(1, 5, 'Logo Line', 'image')}" style="border:none; ${args->logo_img_style:html:default('width: 200px;
height: auto;'):input_type(css):arg_name(Logo Size):arg_section(1, 6, 'Logo Line', 'image')}">
			</td>
			${block->with_top_right:default(1):arg_name(With Top-Right Text):arg_section(1, 8, 'Logo Line', 'image')}
			<td style="${args->top_right_td_style:html:default('vertical-align: middle;
text-align: left;
padding-top: 0em;
padding-right: 1em;
padding-bottom: 0em;
padding-left: 0em;'):input_type(css):arg_name(Top-Right Text Position):arg_section(1, 9, 'Logo Line', 'image')}">
				${args->top_right:default('<div><strong>EUROPA&#39;S GROOTSTE<br />
OUTDOOR LIVING MALL</strong></div>
'):arg_name(Top-Right Text):arg_section(2, 2, 'Top Menu', 'bars')}
			</td>
		</tr>
	</table>
	<table style="width:100%; border-collapse:collapse; border:none">
		<tr>
			${block->li1:default(1):arg_name(With Menu Item 1):arg_section(2, 0, 'Top Menu', 'bars')}
			<td style="${args->li:html:default('vertical-align:middle; text-align:center; padding:0.6em; font-weight:bold; color:black'):input_type(css):arg_name(Menu Item Style):arg_section(2, 1, 'Top Menu', 'bars')}">
				<a href="${args->li1_href:html:arg_name(Menu Item 1 Link URL):arg_section(2, 4, 'Top Menu', 'bars')}" target="_blank" style="color:inherit; text-decoration:inherit">${args->li1_text:default(SHOP NU):arg_name(Menu Item 1 Text):arg_section(2, 3, 'Top Menu', 'bars')}</a>
			</td>
			${block->li2:default(1):arg_name(With Menu Item 2):arg_section(1, 1, 'Logo Line', 'image')}
			<td style="${args->li:html}">
				<a href="${args->li2_href:html:arg_name(Menu Item 2 Link URL):arg_section(2, 6, 'Top Menu', 'bars')}" target="_blank" style="color:inherit; text-decoration:inherit">${args->li2_text:default(BLOGS):arg_name(Menu Item 2 Text):arg_section(2, 5, 'Top Menu', 'bars')}</a>
			</td>
			${block->li3:default(1):arg_name(With Menu Item 3):arg_section(1, 2, 'Logo Line', 'image')}
			<td style="${args->li:html}">
				<a href="${args->li3_href:html:arg_name(Menu Item 3 Link URL):arg_section(2, 8, 'Top Menu', 'bars')}" target="_blank" style="color:inherit; text-decoration:inherit">${args->li3_text:default(COLLECTIE):arg_name(Menu Item 3 Text):arg_section(2, 7, 'Top Menu', 'bars')}</a>
			</td>
			${block->li4:default(1):arg_name(With Menu Item 4):arg_section(1, 3, 'Logo Line', 'image')}
			<td style="${args->li:html}">
				<a href="${args->li4_href:html:arg_name(Menu Item 4 Link URL):arg_section(2, 10, 'Top Menu', 'bars')}" target="_blank" style="color:inherit; text-decoration:inherit">${args->li4_text:default(SHOWROOM):arg_name(Menu Item 4 Text):arg_section(2, 9, 'Top Menu', 'bars')}</a>
			</td>
			${block->li5:default(1):arg_name(With Menu Item 5):arg_section(1, 4, 'Logo Line', 'image')}
			<td style="${args->li:html}">
				<a href="${args->li5_href:html:arg_name(Menu Item 5 Link URL):arg_section(2, 12, 'Top Menu', 'bars')}" target="_blank" style="color:inherit; text-decoration:inherit">${args->li5_text:default(CONTACT):arg_name(Menu Item 5 Text):arg_section(2, 11, 'Top Menu', 'bars')}</a>
			</td>
		</tr>
	</table>
	${block->with_img:default(1):arg_name(With Picture):arg_section(3, 0, 'Picture', 'image')}
	<img src="${args->img_src:html:default('https://static.emarketer.com/upload/362/9021b00a37b389c0.jpeg'):input_type(emarketer_media_url):arg_name(Picture URL):arg_section(3, 1, 'Picture', 'image')}" style="border:none; ${args->img_style:html:default('width: 100%;
height: auto;'):input_type(css):arg_name(Picture Size):arg_section(3, 2, 'Picture', 'image')}">
	<h1 style="${args->h1_style:html:default('font-size: 0px;'):input_type(css):arg_name(Header Style):arg_section(4, 1, 'Text', 'font')}">
		${args->h1:default('<img src="https://static.emarketer.com/upload/4054/b57f02953130159f.png" />'):arg_name(Header):arg_section(4, 0, 'Text', 'font')}
	</h1>
	${args->p:default('<p style="margin:0 4em">Text&nbsp;Text Text&nbsp;Text TextText TextvText TextText Text v v v&nbsp;Text Text vText TextvText&nbsp;Text Text&nbsp;Text TextText TextText TextText TextText&nbsp;Text TextText Text</p>
'):arg_name(Text):arg_section(4, 2, 'Text', 'font')}
	${block->with_button:default(1):arg_name(With Button):arg_section(5, 0, 'Button', 'mouse-pointer')}
	<a href="${args->button_href:html:arg_name(Button Link URL):arg_section(5, 2, 'Button', 'mouse-pointer')}" target="_blank" style="display:inline-block; ${args->button_style:html:default('background-color:#0A4A34; color:white; padding:0.6em 1.2em; margin:1em; text-decoration:none; font-weight:bold; margin-bottom:2em'):input_type(css):arg_name(Menu Item Style):arg_section(5, 3, 'Button', 'mouse-pointer')}">
		${args->button_text:default(View site):arg_name(Button Text):arg_section(5, 1, 'Button', 'mouse-pointer')}
	</a>
	<table style="width:100%; border-collapse:collapse">
		${foreach products_interactions as p where p->interaction_status in ('extra') order by p->interaction_time desc limit 3}
			<tr>
				<td style="text-align:left">
					<a href="${p->cart_url:html:arg_name(Link target URL):arg_section(6, 2, 'Product image', 'image'):column_tags('url','custom text')}" target="_blank">
						<img src="${p->image_big_url:html:arg_name(Image):arg_section(6, 0, 'Product image', 'image'):column_tags(image)}" style="${args->img_size:html:default('width:200px; height:200px; margin:10px'):input_type(css):arg_name(Product Image Size):arg_section(6, 1, 'Product image', 'image')}">
					</a>
				</td>
				<td style="text-align:right; vertical-align:top">
					<div style="${args->name_style:html:default('text-align:left; margin:10px'):input_type(css):arg_name(Product Name Alignment):arg_section(7, 1, 'Product name', 'text-height')}">
						<a href="${p->cart_url:html}" target="_blank" style="text-decoration:none">
							<div style="${args->p_title_style:html:default('font-size: 18px;
font-weight: bold;
color: #0A4A34;'):input_type(css):arg_name(Product Name Style):arg_section(7, 2, 'Product name', 'text-height')}">
								${p->title:arg_name(Product name):arg_section(7, 0, 'Product name', 'text-height')}
							</div>
							${block->with_desc:default(1):arg_name(With Description):arg_section(7, 3, 'Product name', 'text-height')}
							<div style="${args->p_desc_style:html:default('font-size: 18px;
color: #0A4A34;'):input_type(css):arg_name(Product name style):arg_section(7, 5, 'Product name', 'text-height')}">
								${p->description_long:arg_name(Product name):arg_section(7, 4, 'Product name', 'text-height')}
							</div>
						</a>
						<table style="width:100%; border-collapse:collapse; margin-top:1em">
							<tr>
								${block->price:default(1):arg_name(With price):arg_section(8, 0, 'Second line', 'text-height')}
								<td style="${args->price_style:html:default('font-size:22px; font-weight:bold; color:red; padding-right:10px'):input_type(css):arg_name(Price position):arg_section(8, 4, 'Second line', 'text-height')}">
									${if p->price}
										${args->before_price:arg_name(Text before price):arg_section(8, 1, 'Second line', 'text-height')}
										${if p->sale_price and p->sale_price < p->price}
											${p->sale_price:truncate('2'):sprintf('$%s'):arg_name(Price):arg_section(8, 2, 'Second line', 'text-height')}
											<span style="${args->sale_style:html:default('color:gray; text-decoration:line-through; font-size:85%'):input_type(css):input_props('with_responsive=1'):arg_name('Price before discount: style'):arg_section(8, 6, 'Second line', 'text-height')}">
												${p->price:truncate('2'):sprintf('$%s'):arg_name(Price):arg_section(8, 5, 'Second line', 'text-height')}
											</span>
										${end}
										${if not p->sale_price or p->sale_price >= p->price}
											${p->price:truncate('2'):sprintf('$%s')}
										${end}
										${args->after_price:arg_name(Text after price):arg_section(8, 3, 'Second line', 'text-height')}
									${end}
								</td>
								<td>
									<a href="${p->cart_url:html}" target="_blank" style="display:inline-block; text-decoration:none; ${args->text_6_style:html:default('text-align:center; background-color:#0A4A34; color:white; font-size:16px; font-weight:bold; padding:0.5em 1em'):input_type(css):arg_name(Text size):arg_section(8, 8, 'Second line', 'text-height')}">
										${args->text_6:default(Buy):arg_name(Button Text):arg_section(8, 7, 'Second line', 'text-height')}
									</a>
								</td>
							</tr>
						</table>
					</div>
				</td>
			</tr>
			<tr>
				<td colspan="2">
					<div style="box-sizing:border-box; ${args->hr:html}"></div>
				</td>
			</tr>
		${end}
	</table>
	${args->p2:default('<p style="margin:4em 4em 2em 4em"><span style="color:#0a4a34;">Text Text&nbsp;Text Text&nbsp;Text Text</span></p>
'):arg_name(Text):arg_section(9, 0, 'Bottom Text', 'font')}
	${block->with_button2:default(1):arg_name(With Button 1):arg_section(10, 0, 'Button', 'mouse-pointer')}
	<a href="${args->button2_href:html:arg_name(Button Link URL):arg_section(10, 2, 'Button', 'mouse-pointer')}" target="_blank" style="display:inline-block; ${args->button2_style:html:default('background-color:#0A4A34; color:white; padding:0.6em 1.2em; margin:1em; text-decoration:none; font-weight:bold'):input_type(css):arg_name(Menu Item Style):arg_section(10, 3, 'Button', 'mouse-pointer')}">
		${args->button2_text:default(Button):arg_name(Button 1 Text):arg_section(10, 1, 'Button', 'mouse-pointer')}
	</a>
	${block->with_button3:default(1):arg_name(With Button 2):arg_section(10, 4, 'Button', 'mouse-pointer')}
	<a href="${args->button3_href:html:arg_name(Button Link URL):arg_section(10, 6, 'Button', 'mouse-pointer')}" target="_blank" style="display:inline-block; ${args->button3_style:html:default('background-color:#0A4A34; color:white; padding:0.6em 1.2em; margin:1em; text-decoration:none; font-weight:bold'):input_type(css):arg_name(Menu Item Style):arg_section(10, 7, 'Button', 'mouse-pointer')}">
		${args->button3_text:default(Option 2):arg_name(Button 2 Text):arg_section(10, 5, 'Button', 'mouse-pointer')}
	</a>
	<div>
		<div style="display:inline-block">
			${args->p3:default('<br />
&nbsp; &nbsp; Text TextText TextText TextText TextText TextText TextText TextText TextText TextText TextText TextText TextText TextText TextText TextText TextText TextText TextText TextText TextText TextText TextText Text'):arg_name(Text):arg_section(11, 0, 'Bottom Text 2', 'font')}
		</div>
	</div>
</div>
```


## Email



```

<table style="border-collapse:collapse; background-color:white; ${args->wrapper_style:html:default('width:600px; max-width:90vw; font-family:sans-serif; color:#2E3234'):input_type(css):arg_name(Logo alignment):arg_section(0, 0, 'Logo', 'image')}">
	<tr>
		<td style="${args->logo_div_style:html:default('text-align:center'):input_type(css):arg_name(Logo alignment):arg_section(0, 3, 'Logo', 'image')}">
			<img src="${args->link_image:html:default('https://cdn.e-marketer.io/upload/362/185f3236b1b4ab52.png'):input_type(emarketer_media_url):arg_name(Logo URL):arg_section(0, 1, 'Logo', 'image')}" style="${args->image_style:html:default('width:auto; height:auto'):input_type(css):arg_name(Logo size):arg_section(0, 2, 'Logo', 'image')}">
			<div style="box-sizing:border-box; ${args->hr:html:default('width:100%; height:1px; background-color:gray; margin:0.5em'):input_type(css):arg_name(Ruler):arg_section(0, 4, 'Logo', 'image')}"></div>
		</td>
	</tr>
	<tr>
		<td>
			<div style="${args->text_1_style:html:default('text-align:center; color:#7B7F7E; font-size:28px; padding-top:0.5em'):input_type(css):arg_name(Text size):arg_section(1, 2, 'Text', 'bars')}">
				${args->text_1:default('Hey,'):arg_name(Text):arg_section(1, 0, 'Text', 'bars')}
				${first_name:default(dear Customer)}
				${args->text_1a:default(you forgot something):arg_name(Text):arg_section(1, 1, 'Text', 'bars')}
			</div>
			<div style="${args->text_1b_style:html:default('text-align:center; font-size:18px; padding-bottom:2em'):input_type(css):arg_name(Text size):arg_section(1, 5, 'Text', 'bars')}">
				${args->text_1b:default(You left these items in your cart. Still want them?):arg_name(Text):arg_section(1, 4, 'Text', 'bars')}
			</div>
			<div style="box-sizing:border-box; ${args->hr:html}"></div>
		</td>
	</tr>
	<tr>
		<td>
			<table style="width:100%; border-collapse:collapse">
				${foreach products_interactions as p where p->interaction_status in ('extra') order by p->interaction_time desc limit 25}
					<tr>
						<td style="text-align:left">
							<a href="${p->cart_url:html:arg_name(Link target URL):arg_section(3, 1, 'Product image', 'image'):column_tags('url','custom text')}" target="_blank">
								<img src="${p->image_big_url:html:arg_name(Image):arg_section(3, 0, 'Product image', 'image'):column_tags(image)}" style="width:${args->img_width:html:default(200px):input_type(css_length):arg_name(Image width):arg_section(3, 2, 'Product image', 'image')}; height:${args->img_height:html:default(200px):input_type(css_length):arg_name(Image width):arg_section(3, 3, 'Product image', 'image')}" onerror="this.parentNode.style.display='none'">
							</a>
						</td>
						<td style="text-align:right">
							<a href="${p->cart_url:html}" target="_blank">
								<div style="${args->p_title_style:html:default('color:gray; font-size:18px; font-style:italic'):input_type(css):arg_name(Product name style):arg_section(4, 1, 'Product name', 'text-height')}">
									${p->title:arg_name(Product name):arg_section(4, 0, 'Product name', 'text-height')}
								</div>
							</a>
							${block->price:default(1):arg_name(With price):arg_section(5, 0, 'Second line', 'text-height')}
							<div style="${args->price_style:html:default('color:black; font-size:22px; font-weight:bold; color:#196590'):input_type(css):arg_name(Price position):arg_section(5, 4, 'Second line', 'text-height')}">
								${if p->price}
									${args->before_price:arg_name(Text before price):arg_section(5, 1, 'Second line', 'text-height')}
								${end}
								${p->price:sprintf($%s):arg_name(Price):arg_section(5, 2, 'Second line', 'text-height')}
								${if p->price}
									${args->after_price:arg_name(Text after price):arg_section(5, 3, 'Second line', 'text-height')}
								${end}
							</div>
							<a href="${p->cart_url:html}" target="_blank">
								<div style="display:inline-block; ${args->text_6_style:html:default('text-align:center; background-color:#196590; color:white; font-size:16px; font-weight:bold; padding:0.5em 1em'):input_type(css):arg_name(Text size):arg_section(1, 3, 'Text', 'bars')}">
									${args->text_6:default('BUY NOW >'):arg_name(Button Text):arg_section(5, 5, 'Second line', 'text-height')}
								</div>
							</a>
						</td>
					</tr>
					<tr>
						<td colspan="2">
							<div style="box-sizing:border-box; ${args->hr:html}"></div>
						</td>
					</tr>
				${end}
			</table>
		</td>
	</tr>
	<tr>
		<td style="text-align:center">
			<a href="${args->button_url:html:arg_name(Buy all target URL):arg_section(6, 0, 'Text', 'bars')}" target="_blank">
				<div style="display:inline-block; ${args->text_6b_style:html:default('text-align:center; background-color:white; color:#196590; border:solid 1px; font-size:16px; font-weight:bold; padding:0.5em 1em'):input_type(css):arg_name(Text size):arg_section(6, 1, 'Text', 'bars')}">
					${args->text_6b:default('BUY ALL ABOVE LISTED PRODUCTS >'):arg_name(Button Buy All Text):arg_section(6, 2, 'Text', 'bars')}
				</div>
			</a>
			<div style="box-sizing:border-box; ${args->hr:html}"></div>
		</td>
	</tr>
	<tr>
		<td style="text-align:center">
			<div style="${args->text_6c_style:html:default('text-align:center; color:#7B7F7E; font-size:18px; padding-top:0.5em'):input_type(css):arg_name(Text size):arg_section(7, 1, 'Text', 'bars')}">
				${args->text_6c:default(Have questions or need help with your purchases?):arg_name(Text):arg_section(7, 0, 'Text', 'bars')}
			</div>
			<table style="margin:auto">
				<tr>
					<td>
						<a style="display:inline-block; ${args->email_style:html:default('text-align:center; background-color:#F0F0F0; color:#196590; border:solid 1px; font-size:16px; font-weight:bold; padding:0.5em 2em; text-decoration:none; margin:0 1em'):input_type(css):arg_name(Email button style):arg_section(8, 1, 'Email', 'envelope')}">
							${args->text8:html:default('+1(844) 111-1111'):arg_name(Phone):arg_section(8, 0, 'Email', 'envelope')}
						</a>
					</td>
					<td>
						<a href="mailto:${args->email:html:default('youremailaddress@here.com'):arg_name(Email address):arg_section(8, 3, 'Email', 'envelope')}?subject=${args->subject:html:default(Contact form):arg_name(Default subject):arg_section(8, 4, 'Email', 'envelope')}" style="display:inline-block; ${args->email_style:html}">
							${args->text7:html:default(Email Us):arg_name(Email text):arg_section(8, 2, 'Email', 'envelope')}
						</a>
					</td>
				</tr>
			</table>
			<div style="box-sizing:border-box; ${args->hr:html}"></div>
		</td>
	</tr>
	<tr>
		<td style="text-align:center">
			<div style="display:flex; flex-wrap:wrap; justify-content:space-around; align-items:center">
				<div>
					<a href="${args->li_1_href:html:default('#'):arg_name(Menu Item 1 URL):arg_section(2, 1, 'Bottom Menu', 'bars')}">
						${args->li_1:default(Menu Item 1):arg_name(Menu Item 1):arg_section(2, 0, 'Bottom Menu', 'bars')}
					</a>
				</div>
				<div>
					<a href="${args->li_2_href:html:default('#'):arg_name(Menu Item 2 URL):arg_section(2, 3, 'Bottom Menu', 'bars')}">
						${args->li_2:default(Menu Item 2):arg_name(Menu Item 2 Text):arg_section(2, 2, 'Bottom Menu', 'bars')}
					</a>
				</div>
				<div>
					<a href="${args->li_3_href:html:default('#'):arg_name(Menu Item 3 URL):arg_section(2, 5, 'Bottom Menu', 'bars')}">
						${args->li_3:default(Menu Item 3):arg_name(Menu Item 3 Text):arg_section(2, 4, 'Bottom Menu', 'bars')}
					</a>
				</div>
				<div>
					<a href="${args->li_4_href:html:default('#'):arg_name(Menu Item 4 URL):arg_section(2, 7, 'Bottom Menu', 'bars')}">
						${args->li_4:default(Menu Item 4):arg_name(Menu Item 4 Text):arg_section(2, 6, 'Bottom Menu', 'bars')}
					</a>
				</div>
				<div>
					<a href="${args->li_5_href:html:default('#'):arg_name(Menu Item 5 URL):arg_section(2, 9, 'Bottom Menu', 'bars')}">
						${args->li_5:default(Menu Item 5):arg_name(Menu Item 5 Text):arg_section(2, 8, 'Bottom Menu', 'bars')}
					</a>
				</div>
				<div>
					<a href="${args->li_6_href:html:default('#'):arg_name(Menu Item 6 URL):arg_section(2, 11, 'Bottom Menu', 'bars')}">
						${args->li_6:default(Menu Item 6):arg_name(Menu Item 6 Text):arg_section(2, 10, 'Bottom Menu', 'bars')}
					</a>
				</div>
			</div>
			<div style="box-sizing:border-box; ${args->hr:html}"></div>
		</td>
	</tr>
</table>
</body>
</html>
```


## Email



```

<table style="border-collapse:collapse; background-color:white; font-size:14px">
	<tr>
		<td style="text-align:center; padding:0.8em">
			${args->line_1:default(Enjoy 10% off your next order -):arg_name(Text):arg_section(0, 0, 'Line 1', 'bars')}
			<a href="${args->line_1_href:html:default('#'):arg_name(Link target URL):arg_section(0, 1, 'Line 1', 'bars')}" target="_blank" style="${args->line_1_a_style:html:default('color:black; text-decoration:none'):input_type(css):arg_name(Link style):arg_section(0, 2, 'Line 1', 'bars')}">
				${args->line_1_a:default(view online):arg_name(Link text):arg_section(0, 3, 'Line 1', 'bars')}
			</a>
		</td>
	</tr>
	<tr>
		<td style="text-align:center; background-color:#ECECEC; font-size:16px; padding:0.8em">
			<span style="padding:0 1em">
				<span style="${args->line_2_style:html:default('color:#E40E7D'):input_type(css):arg_name(Link style):arg_section(1, 0, 'Line 2', 'bars')}">
					${args->line_2_1:default('✔'):arg_name(Link text):arg_section(1, 1, 'Line 2', 'bars')}
				</span>
				${args->line_2_1t:default(12 Months Warranty):arg_name(Link text):arg_section(1, 2, 'Line 2', 'bars')}
			</span>
			<span style="padding:0 1em">
				<span style="${args->line_2_style:html}">
					${args->line_2_2:default('✔ FREE'):arg_name(Link text):arg_section(1, 3, 'Line 2', 'bars')}
				</span>
				${args->line_2_2t:default(Returns):arg_name(Link text):arg_section(1, 4, 'Line 2', 'bars')}
			</span>
			<span style="padding:0 1em">
				<span style="${args->line_2_style:html}">
					${args->line_2_3:default('✔ FREE'):arg_name(Link text):arg_section(1, 5, 'Line 2', 'bars')}
				</span>
				${args->line_2_3t:default(Next Day Delivery):arg_name(Link text):arg_section(1, 6, 'Line 2', 'bars')}
			</span>
		</td>
	</tr>
	<tr>
		<td style="text-align:center">
			<img src="${args->link_image:html:default('https://cdn.e-marketer.io/upload/362/185f3236b1b4ab52.png'):input_type(emarketer_media_url):arg_name(Image URL):arg_section(2, 0, 'Image 1', 'image')}" style="${args->image_style:html:default('width: 300px;
height: auto;'):input_type(css):arg_name(Image size):arg_section(2, 1, 'Image 1', 'image')}">
		</td>
	</tr>
	<tr>
		<td style="text-align:center">
			<img src="${args->link_image2:html:default('https://cdn.e-marketer.io/upload/362/9021b00a37b389c0.jpeg'):input_type(emarketer_media_url):arg_name(Image URL):arg_section(3, 0, 'Image 2', 'image')}" style="${args->image_style2:html:default('width: 800px;'):input_type(css):arg_name(Image size):arg_section(3, 1, 'Image 2', 'image')}">
		</td>
	</tr>
	<tr>
		<td>
			<br>
		</td>
	</tr>
	<tr>
		<td style="text-align:center; background-color:#ECECEC; color:#747474; font-size:32px; padding:0.3em">
			${args->coupon:default(Use code):arg_name(Text):arg_section(4, 0, 'Line 3', 'bars')}
			<span style="${args->line_2_style:html}">
				${args->coupon2:default(THANKYOU10):arg_name(Text):arg_section(4, 1, 'Line 3', 'bars')}
			</span>
			${args->coupon3:default(at checkout):arg_name(Text):arg_section(4, 2, 'Line 3', 'bars')}
			<div>
				<a href="${args->coupon_a:html:default('#'):arg_name(Link target URL):arg_section(4, 3, 'Line 3', 'bars')}" target="_blank" style="display:inline-block; ${args->coupon_a_style:html:default('color: white;
background-color: rgb(14, 228, 74);
border-radius: 12px;
padding-top: 0.2em;
padding-right: 0.8em;
padding-bottom: 0.2em;
padding-left: 0.8em;
text-decoration: none;
box-shadow: 1px 2px 1px rgb(239, 231, 231);
margin: 0.4em;'):input_type(css):arg_name(Link style):arg_section(4, 4, 'Line 3', 'bars')}">
					${args->coupon_a_text:default(Shop Now):arg_name(Link text):arg_section(4, 5, 'Line 3', 'bars')}
				</a>
			</div>
		</td>
	</tr>
	<tr>
		<td style="text-align:center; background-color:#6F6E6F; color:white; font-size:16px; padding:0.3em">
			We recommend for you
		</td>
	</tr>
	<tr>
		<td style="padding:1.5em 0">
			<table style="width:100%; border-collapse:collapse">
				<tr>
					${foreach recom_products as p limit 25}
						<td style="text-align:center">
							<a href="${p->cart_url:html:arg_name(Link target URL):arg_section(5, 1, 'Product image', 'image'):column_tags('url','custom text')}" target="_blank">
								<img src="${p->image_big_url:html:arg_name(Image):arg_section(5, 0, 'Product image', 'image'):column_tags(image)}" style="width:${args->img_width:html:default(200px):input_type(css_length):arg_name(Image width):arg_section(5, 2, 'Product image', 'image')}; height:${args->img_height:html:default(200px):input_type(css_length):arg_name(Image width):arg_section(5, 3, 'Product image', 'image')}" onerror="this.parentNode.style.display='none'">
								<div style="${args->p_title_style:html:default('color:black; font-size:16px'):input_type(css):arg_name(Product name style):arg_section(6, 1, 'Product name', 'text-height')}">
									${p->title:arg_name(Product name):arg_section(6, 0, 'Product name', 'text-height')}
								</div>
								${block->price:default(1):arg_name(With price):arg_section(7, 0, 'Second line', 'text-height')}
								<div style="${args->price_style:html:default('color:black; font-size:16px; font-weight:bold'):input_type(css):arg_name(Price position):arg_section(7, 4, 'Second line', 'text-height')}">
									${if p->price}
										${args->before_price:arg_name(Text before price):arg_section(7, 1, 'Second line', 'text-height')}
									${end}
									${p->price:sprintf($%s):arg_name(Price):arg_section(7, 2, 'Second line', 'text-height')}
									${if p->price}
										${args->after_price:arg_name(Text after price):arg_section(7, 3, 'Second line', 'text-height')}
									${end}
								</div>
							</a>
						</td>
					${end}
				</tr>
			</table>
		</td>
	</tr>
	<tr>
		<td style="text-align:center; background-color:#ECECEC; color:#747474; font-size:32px; padding:0.3em">
			${args->line_4:default('Keep an eye on our <b>latest ranges</b> and <b>special offer</b> prices...'):arg_name(Text):arg_section(8, 0, 'Line 4', 'bars')}
		</td>
	</tr>
</table>
</body>
</html>
```


## Email



```
<div style="${args->style:html:default('border: none;
text-align: center;
width: 600px;
background-color: white;
color: #0A4A34;
font-size: 14px;
margin-top: 1px;
margin-right: auto;
margin-bottom: 1px;
margin-left: auto;'):input_type(css):arg_name(Style):arg_section(0, 0, 'Frame', 'th-large')}">
	<table style="width:100%; border-collapse:collapse; border:none; ${args->logo_table_style:html:default('border-bottom: solid #4c6330 4px;'):input_type(css):arg_name(Logo Position):arg_section(1, 10, 'Logo Line', 'image')}">
		<tr>
			${block->with_logo:default(1):arg_name(With Logo):arg_section(1, 0, 'Logo Line', 'image')}
			<td style="${args->logo_td_style:html:default('vertical-align: middle;
text-align: center;
padding-top: 1em;
padding-right: 2em;
padding-bottom: 1em;
padding-left: 0em;'):input_type(css):arg_name(Logo Position):arg_section(1, 7, 'Logo Line', 'image')}">
				<img src="${args->logo_src:html:default('https://cdn.e-marketer.io/upload/362/18a94c1299224ec8.png'):input_type(emarketer_media_url):arg_name(Logo URL):arg_section(1, 5, 'Logo Line', 'image')}" style="border:none; ${args->logo_img_style:html:default('width: 270px;
height: auto;'):input_type(css):arg_name(Logo Size):arg_section(1, 6, 'Logo Line', 'image')}">
			</td>
			${block->with_top_right:default(0):arg_name(With Top-Right Text):arg_section(1, 8, 'Logo Line', 'image')}
			<td style="${args->top_right_td_style:html:input_type(css):arg_name(Top-Right Text Position):arg_section(1, 9, 'Logo Line', 'image')}">
				${args->top_right:arg_name(Top-Right Text):arg_section(2, 2, 'Top Menu', 'bars')}
			</td>
		</tr>
	</table>
	<table style="width:100%; border-collapse:collapse; border:none">
		<tr>
			${block->li1:default(0):arg_name(With Menu Item 1):arg_section(2, 0, 'Top Menu', 'bars')}
			<td style="${args->li:html:default('vertical-align:middle; text-align:center; padding:0.6em; font-weight:bold; color:black'):input_type(css):arg_name(Menu Item Style):arg_section(2, 1, 'Top Menu', 'bars')}">
				<a href="${args->li1_href:html:arg_name(Menu Item 1 Link URL):arg_section(2, 4, 'Top Menu', 'bars')}" target="_blank" style="color:inherit; text-decoration:inherit">${args->li1_text:arg_name(Menu Item 1 Text):arg_section(2, 3, 'Top Menu', 'bars')}</a>
			</td>
			${block->li2:default(1):arg_name(With Menu Item 2):arg_section(1, 1, 'Logo Line', 'image')}
			<td style="${args->li:html}">
				<a href="${args->li2_href:html:default():arg_name(Menu Item 2 Link URL):arg_section(2, 6, 'Top Menu', 'bars')}" target="_blank" style="color:inherit; text-decoration:inherit">${args->li2_text:default(Homepage):arg_name(Menu Item 2 Text):arg_section(2, 5, 'Top Menu', 'bars')}</a>
			</td>
			${block->li3:default(1):arg_name(With Menu Item 3):arg_section(1, 2, 'Logo Line', 'image')}
			<td style="${args->li:html}">
				<a href="${args->li3_href:html:default():arg_name(Menu Item 3 Link URL):arg_section(2, 8, 'Top Menu', 'bars')}" target="_blank" style="color:inherit; text-decoration:inherit">${args->li3_text:default(Cart):arg_name(Menu Item 3 Text):arg_section(2, 7, 'Top Menu', 'bars')}</a>
			</td>
			${block->li4:default(1):arg_name(With Menu Item 4):arg_section(1, 3, 'Logo Line', 'image')}
			<td style="${args->li:html}">
				<a href="${args->li4_href:html:default():arg_name(Menu Item 4 Link URL):arg_section(2, 10, 'Top Menu', 'bars')}" target="_blank" style="color:inherit; text-decoration:inherit">${args->li4_text:default(Alert):arg_name(Menu Item 4 Text):arg_section(2, 9, 'Top Menu', 'bars')}</a>
			</td>
			${block->li5:default(0):arg_name(With Menu Item 5):arg_section(1, 4, 'Logo Line', 'image')}
			<td style="${args->li:html}">
				<a href="${args->li5_href:html:arg_name(Menu Item 5 Link URL):arg_section(2, 12, 'Top Menu', 'bars')}" target="_blank" style="color:inherit; text-decoration:inherit">${args->li5_text:arg_name(Menu Item 5 Text):arg_section(2, 11, 'Top Menu', 'bars')}</a>
			</td>
		</tr>
	</table>
	${block->with_img:default(1):arg_name(With Picture):arg_section(3, 0, 'Picture', 'image')}
	<img src="${args->img_src:html:input_type(emarketer_media_url):arg_name(Picture URL):arg_section(3, 1, 'Picture', 'image')}" style="border:none; ${args->img_style:html:default('width: 0px;
height: auto;'):input_type(css):arg_name(Picture Size):arg_section(3, 2, 'Picture', 'image')}">
	<h1 style="${args->h1_style:html:default('font-size: 0px;'):input_type(css):arg_name(Header Style):arg_section(4, 1, 'Text', 'font')}">
		${args->h1:arg_name(Header):arg_section(4, 0, 'Text', 'font')}
	</h1>
	${args->p:default('<p style="margin:0 4em">Free text &nbsp;Free text &nbsp;Free text&nbsp;Free text&nbsp;<br />
<br />
&nbsp;Free text &nbsp;Free text &nbsp;Free text&nbsp;</p>
'):arg_name(Text):arg_section(4, 2, 'Text', 'font')}
	${block->with_button:default(0):arg_name(With Button):arg_section(5, 0, 'Button', 'mouse-pointer')}
	<a href="${args->button_href:html:arg_name(Button Link URL):arg_section(5, 2, 'Button', 'mouse-pointer')}" target="_blank" style="display:inline-block; ${args->button_style:html:input_type(css):arg_name(Menu Item Style):arg_section(5, 3, 'Button', 'mouse-pointer')}">
		${args->button_text:arg_name(Button Text):arg_section(5, 1, 'Button', 'mouse-pointer')}
	</a>
	<table style="width:100%; border-collapse:collapse">
		${foreach recom_products as p limit 3}
			<tr>
				<td style="text-align:left">
					<a href="${p->cart_url:html:arg_name(Link target URL):arg_section(6, 2, 'Product image', 'image'):column_tags('url','custom text')}" target="_blank">
						<img src="${p->image_big_url:html:arg_name(Image):arg_section(6, 0, 'Product image', 'image'):column_tags(image)}" style="${args->img_size:html:default('width: 100px;
height: auto;
margin-top: 0px;
margin-right: 0px;
margin-bottom: 0px;
margin-left: 33px;'):input_type(css):arg_name(Product Image Size):arg_section(6, 1, 'Product image', 'image')}">
					</a>
				</td>
				<td style="text-align:right; vertical-align:top">
					<div style="${args->name_style:html:default('text-align: right;
margin-top: 24px;
margin-right: 11px;
margin-bottom: 0px;
margin-left: 0px;
border: solid 0px #ededed;
border-width: 0px;'):input_type(css):arg_name(Product Name Alignment):arg_section(7, 1, 'Product name', 'text-height')}">
						<a href="${p->cart_url:html}" target="_blank" style="text-decoration:none">
							<div style="${args->p_title_style:html:default('margin-top: 24px;
margin-right: 0;
margin-bottom: 20px;
margin-left: 0px;
font-family: Roboto, sans-serif;
text-align: left;
text-transform: none;
font-weight: 800;
font-size: 1.18571429em;
line-height: 1.71428571em;
color: rgba(0, 0, 0, 0.7);
min-width: sel(100px, 50px);
text-decoration: none;'):input_type(css):arg_name(Product Name Style):arg_section(7, 2, 'Product name', 'text-height')}">
								${p->title:arg_name(Product name):arg_section(7, 0, 'Product name', 'text-height')}
							</div>
							${block->with_desc:default(1):arg_name(With Description):arg_section(7, 3, 'Product name', 'text-height')}
							<div style="${args->p_desc_style:html:default('margin-top: auto;
border-top: .0625rem solid #ededed;
padding-top: 1.25rem;
padding-right: 1.5rem;
padding-bottom: 1.25rem;
padding-left: 0rem;
color: #9b9b9b;
text-align: left;
font-size: 018px;
font-weight: lighter;
font-style: normal;
text-decoration: none;'):input_type(css):arg_name(Product name style):arg_section(7, 5, 'Product name', 'text-height')}">
								${p->description_short:arg_name(Product name):arg_section(7, 4, 'Product name', 'text-height')}
							</div>
						</a>
						<table style="width:100%; border-collapse:collapse; margin-top:1em">
							<tr>
								${block->price:default(1):arg_name(With price):arg_section(8, 0, 'Second line', 'text-height')}
								<td style="${args->price_style:html:default('font-size: 0px;
font-weight: bold;
color: red;
padding-right: 0px;'):input_type(css):arg_name(Price position):arg_section(8, 4, 'Second line', 'text-height')}">
									${if p->price}
										${args->before_price:arg_name(Text before price):arg_section(8, 1, 'Second line', 'text-height')}
										${if p->sale_price and p->sale_price < p->price}
											${p->sale_price:truncate('2'):sprintf('€%s'):arg_name(Price):arg_section(8, 2, 'Second line', 'text-height')}
											<span style="${args->sale_style:html:default('color:gray; text-decoration:line-through; font-size:85%'):input_type(css):input_props('with_responsive=1'):arg_name('Price before discount: style'):arg_section(8, 6, 'Second line', 'text-height')}">
												${p->price:truncate('2'):sprintf('€%s'):arg_name(Price):arg_section(8, 5, 'Second line', 'text-height')}
											</span>
										${end}
										${if not p->sale_price or p->sale_price >= p->price}
											${p->price:truncate('2'):sprintf('€%s')}
										${end}
										${args->after_price:arg_name(Text after price):arg_section(8, 3, 'Second line', 'text-height')}
									${end}
								</td>
								<td>
									<a href="${p->cart_url:html}" target="_blank" style="display:inline-block; text-decoration:none; ${args->text_6_style:html:default('background-color: #e23943;
color: white;
padding-top: 11px;
padding-right: 2.5rem;
padding-bottom: 11px;
padding-left: 2.5rem;
margin-top: 1em;
margin-right: 1em;
margin-bottom: 2em;
margin-left: 1em;
text-decoration: none;
font-weight: bold;
border-radius: 2.8125rem;'):input_type(css):arg_name(Text size):arg_section(8, 8, 'Second line', 'text-height')}">
										${args->text_6:default(View):arg_name(Button Text):arg_section(8, 7, 'Second line', 'text-height')}
									</a>
								</td>
							</tr>
						</table>
					</div>
				</td>
			</tr>
			<tr>
				<td colspan="2">
					<div style="box-sizing:border-box; ${args->hr:html}"></div>
				</td>
			</tr>
		${end}
	</table>
	${args->p2:default('<p style="margin:4em 4em 2em 4em"><span style="color:#0a4a34;">Staat jouw gewenste vacature er niet bij? Bekijk dan onze vacature pagina.&nbsp;</span></p>
'):arg_name(Text):arg_section(9, 0, 'Bottom Text', 'font')}
	${block->with_button2:default(0):arg_name(With Button 1):arg_section(10, 0, 'Button', 'mouse-pointer')}
	<a href="${args->button2_href:html:arg_name(Button Link URL):arg_section(10, 2, 'Button', 'mouse-pointer')}" target="_blank" style="display:inline-block; ${args->button2_style:html:input_type(css):arg_name(Menu Item Style):arg_section(10, 3, 'Button', 'mouse-pointer')}">
		${args->button2_text:arg_name(Button 1 Text):arg_section(10, 1, 'Button', 'mouse-pointer')}
	</a>
	${block->with_button3:default(0):arg_name(With Button 2):arg_section(10, 4, 'Button', 'mouse-pointer')}
	<a href="${args->button3_href:html:arg_name(Button Link URL):arg_section(10, 6, 'Button', 'mouse-pointer')}" target="_blank" style="display:inline-block; ${args->button3_style:html:input_type(css):arg_name(Menu Item Style):arg_section(10, 7, 'Button', 'mouse-pointer')}">
		${args->button3_text:arg_name(Button 2 Text):arg_section(10, 5, 'Button', 'mouse-pointer')}
	</a>
	<div>
		<div style="display:inline-block">
			${args->p3:default('<br />
&nbsp;'):arg_name(Text):arg_section(11, 0, 'Bottom Text 2', 'font')}
		</div>
	</div>
	${block->with_button4:default(1):arg_name(With Button 1):arg_section(12, 0, 'With Unsubscribe', 'ban')}
	<div>
		<div style="${args->button4_text_style:html:default('padding-top: 0.6em;
padding-right: 1.2em;
padding-bottom: 0.6em;
padding-left: 1.2em;
margin-top: 2em;
margin-right: 0;
margin-bottom: 1em;
margin-left: 0;
font-size: 12px;'):input_type(css):arg_name(Text Line Style):arg_section(12, 2, 'With Unsubscribe', 'ban')}">
			${args->button4_line_text:default(Text):arg_name(Text Line):arg_section(12, 1, 'With Unsubscribe', 'ban')}
		</div>
		<a href="http://pic.emarketer.com/unsubscribe/k=${action_key:html}/u=${id:html}" target="_blank" style="display:inline-block; ${args->button4_style:html:default('background-color: rgba(178, 144, 144, 0.62);
color: white;
padding-top: 0.6em;
padding-right: 1.2em;
padding-bottom: 0.6em;
padding-left: 1.2em;
margin-top: 1em;
margin-right: 0;
margin-bottom: 2em;
margin-left: 0;
text-decoration: none;
font-weight: bold;'):input_type(css):arg_name(Button Style):arg_section(12, 4, 'With Unsubscribe', 'ban')}">
			${args->button4_text:default(Unsubscribe):arg_name(Button Text):arg_section(12, 3, 'With Unsubscribe', 'ban')}
		</a>
	</div>
</div>
```


## Email



```
<div style="${args->style:html:default('border: none;
text-align: center;
width: 600px;
background-color: white;
color: #0A4A34;
font-size: 14px;
margin-top: 1px;
margin-right: auto;
margin-bottom: 1px;
margin-left: auto;')}">
	<table style="width:100%; border-collapse:collapse; border:none; ${args->logo_table_style:html:default('border-bottom: solid #4848a1 4px;')}">
		<tr>
			${block->with_logo:default(1)}
			<td style="${args->logo_td_style:html:default('vertical-align: middle;
text-align: center;
padding-top: 1em;
padding-right: 2em;
padding-bottom: 1em;
padding-left: 0em;')}">
				<img src="${args->logo_src:html:default('https://cdn.personyze.com/upload/362/4c53a78c4a0882c4.png')}" style="border:none; ${args->logo_img_style:html:default('width: 140px;
height: auto;')}">
			</td>
			${block->with_top_right:default(0)}
			<td style="${args->top_right_td_style:html}">
				${args->top_right}
			</td>
		</tr>
	</table>
	<table style="width:100%; border-collapse:collapse; border:none">
		<tr>
			${block->li1:default(0)}
			<td style="${args->li:html:default('vertical-align:middle; text-align:center; padding:0.6em; font-weight:bold; color:black')}">
				<a href="${args->li1_href:html}" target="_blank" style="color:inherit; text-decoration:inherit">${args->li1_text}</a>
			</td>
			${block->li2:default(1)}
			<td style="${args->li:html}">
				<a href="${args->li2_href:html}" target="_blank" style="color:inherit; text-decoration:inherit">${args->li2_text}</a>
			</td>
			${block->li3:default(0)}
			<td style="${args->li:html}">
				<a href="${args->li3_href:html}" target="_blank" style="color:inherit; text-decoration:inherit">${args->li3_text}</a>
			</td>
			${block->li4:default(0)}
			<td style="${args->li:html}">
				<a href="${args->li4_href:html}" target="_blank" style="color:inherit; text-decoration:inherit">${args->li4_text}</a>
			</td>
			${block->li5:default(0)}
			<td style="${args->li:html}">
				<a href="${args->li5_href:html}" target="_blank" style="color:inherit; text-decoration:inherit">${args->li5_text}</a>
			</td>
		</tr>
	</table>
	${block->with_img:default(1)}
	<img src="${args->img_src:html}" style="border:none; ${args->img_style:html:default('width: 0px;
height: auto;')}">
	<h1 style="${args->h1_style:html:default('font-size: 0px;')}">
		${args->h1}
	</h1>
	${args->p:default('<p style="margin:0 4em"><b>Text</b></p>
')}
	${block->with_button:default(0)}
	<a href="${args->button_href:html}" target="_blank" style="display:inline-block; ${args->button_style:html}">
		${args->button_text}
	</a>
	<table style="width:100%; border-collapse:collapse">
		${foreach products_interactions as p where p->interaction_status in ('viewed') order by p->interaction_time desc limit 3}
			<tr>
				<td style="text-align:left">
					<a href="${p->cart_url:html}" target="_blank">
						<img src="${p->image_big_url:html}" style="${args->img_size:html:default('width: 100px;
height: auto;
margin: 0px;')}">
					</a>
				</td>
				<td style="text-align:right; vertical-align:top">
					<div style="${args->name_style:html:default('text-align: right;
margin-top: 0px;
margin-right: 11px;
margin-bottom: 0px;
margin-left: 0px;
border: solid 0px #ededed;
border-width: 0px;')}">
						<a href="${p->cart_url:html}" target="_blank" style="text-decoration:none">
							<div style="${args->p_title_style:html:default('margin-top: 30px;
margin-right: 0;
margin-bottom: 0px;
margin-left: 0px;
font-family: Roboto, sans-serif;
text-align: left;
text-transform: none;
font-weight: 400;
font-size: 15px;
line-height: 1.71428571em;
color: rgba(0, 0, 0, 0.7);
text-decoration: none;')}">
								${p->title}
							</div>
							${block->with_desc:default(1)}
							<div style="${args->p_desc_style:html:default('margin-top: auto;
border-top: .0625rem solid #ededed;
padding-top: nullrem;
padding-right: 1.5rem;
padding-bottom: 0rem;
padding-left: 0rem;
color: #9b9b9b;
text-align: left;
font-size: 018px;
font-weight: lighter;
font-style: normal;
text-decoration: none;')}">
								${p->description_short}
							</div>
						</a>
						<table style="width:100%; border-collapse:collapse; margin-top:1em">
							<tr>
								${block->price:default(1)}
								<td style="${args->price_style:html:default('font-size: 0px;
font-weight: bold;
color: red;
padding-right: 0px;')}">
									${if p->price_before_discount}
                                        ${args->before_price}
                                        ${if p->price_after_discount and p->price_after_discount < p->price_before_discount}
                                            <span style="${args->sale_style:html:default('text-decoration:line-through')}">
                                                ${args->p_price_before_discount:default('&pound;${p->price_before_discount:price('''')}')}
                                            </span>
                                            ${args->p_price_after_discount:default('&pound;${p->price_after_discount:price('''')}')}
                                        ${end}
                                        ${if not p->price_after_discount or p->price_after_discount >= p->price_before_discount}
                                            ${args->p_price_before_discount}
                                        ${end}
                                        ${args->after_price}
                                    ${end}
								</td>
								<td>
									<a href="${p->cart_url:html}" target="_blank" style="display:inline-block; text-decoration:none; ${args->text_6_style:html:default('background: #4848a1;
    border-color: #4848a1;
    color: #ffffff;
    font-size: 12px;
    font-family: arial, helvetica, sans-serif;


color: white;
padding-top: 11px;
padding-right: 2.5rem;
padding-bottom: 11px;
padding-left: 2.5rem;
margin-top: 1em;
margin-right: 1em;
margin-bottom: 2em;
margin-left: 1em;
text-decoration: none;
font-weight: bold;
border-radius: 2.8125rem;')}">
										${args->text_6:default(View)}
									</a>
								</td>
							</tr>
						</table>
					</div>
				</td>
			</tr>
			<tr>
				<td colspan="2">
					<div style="box-sizing:border-box; ${args->hr:html}"></div>
				</td>
			</tr>
		${end}
	</table>
	${args->p2:default('<p style="margin: 4em 4em 2em;"><font color="#0a4a34"><span style="caret-color: rgb(10, 74, 52);">Text</span></font></p>
')}
	${block->with_button2:default(0)}
	<a href="${args->button2_href:html}" target="_blank" style="display:inline-block; ${args->button2_style:html}">
		${args->button2_text}
	</a>
	${block->with_button3:default(0)}
	<a href="${args->button3_href:html}" target="_blank" style="display:inline-block; ${args->button3_style:html}">
		${args->button3_text}
	</a>
	<div>
		<div style="display:inline-block">
			${args->p3}
		</div>
	</div>
	${block->with_button4:default(1)}
	<div>
		<div style="${args->button4_text_style:html}">
			${args->button4_line_text:default(Unsubscribes text)}
		</div>
		<a href="http://pic.personyze.com/unsubscribe/k=${action_key:html}/u=${id:html}" target="_blank" style="display:inline-block; ${args->button4_style:html}">
			${args->button4_text:default(Unsubscribes)}
		</a>
	</div>
</div>

${menu name='Frame', icon='th-large'}
	${menu args->style name='Style', type='css'}
${menu name='Logo Line', icon='image'}
	${menu block->with_logo name='With Logo'}
	${menu block->li2 name='With Menu Item 2'}
	${menu block->li3 name='With Menu Item 3'}
	${menu block->li4 name='With Menu Item 4'}
	${menu block->li5 name='With Menu Item 5'}
	${menu args->logo_src name='Logo URL', type='personyze_media_url'}
	${menu args->logo_img_style name='Logo Size', type='css'}
	${menu args->logo_td_style name='Logo Position', type='css'}
	${menu block->with_top_right name='With Top-Right Text'}
	${menu args->top_right_td_style name='Top-Right Text Position', type='css'}
	${menu args->logo_table_style name='Logo Position', type='css'}
${menu name='Top Menu', icon='bars'}
	${menu block->li1 name='With Menu Item 1'}
	${menu args->li name='Menu Item Style', type='css'}
	${menu args->top_right name='Top-Right Text'}
	${menu args->li1_text name='Menu Item 1 Text'}
	${menu args->li1_href name='Menu Item 1 Link URL'}
	${menu args->li2_text name='Menu Item 2 Text'}
	${menu args->li2_href name='Menu Item 2 Link URL'}
	${menu args->li3_text name='Menu Item 3 Text'}
	${menu args->li3_href name='Menu Item 3 Link URL'}
	${menu args->li4_text name='Menu Item 4 Text'}
	${menu args->li4_href name='Menu Item 4 Link URL'}
	${menu args->li5_text name='Menu Item 5 Text'}
	${menu args->li5_href name='Menu Item 5 Link URL'}
${menu name='Picture', icon='image'}
	${menu block->with_img name='With Picture'}
	${menu args->img_src name='Picture URL', type='personyze_media_url'}
	${menu args->img_style name='Picture Size', type='css'}
${menu name='Text', icon='font'}
	${menu args->h1 name='Header'}
	${menu args->h1_style name='Header Style', type='css'}
	${menu args->p name='Text'}
${menu name='Button', icon='mouse-pointer'}
	${menu block->with_button name='With Button'}
	${menu args->button_text name='Button Text'}
	${menu args->button_href name='Button Link URL'}
	${menu args->button_style name='Menu Item Style', type='css'}
${menu name='Product image', icon='image'}
	${menu p->image_big_url name='Image', column_tags='image'}
	${menu args->img_size name='Product Image Size', type='css'}
	${menu p->cart_url name='Link target URL', column_tags='url, custom text'}
${menu name='Product name', icon='text-height'}
	${menu p->title name='Product name'}
	${menu args->name_style name='Product Name Alignment', type='css'}
	${menu args->p_title_style name='Product Name Style', type='css'}
	${menu block->with_desc name='With Description'}
	${menu p->description_short name='Product name'}
	${menu args->p_desc_style name='Product name style', type='css'}
${menu name='Second line', icon='text-height'}
	${menu block->price name='With price'}
	${menu args->before_price name='Text before price'}
	${menu args->p_price_after_discount name='Price after discount'}
	${menu args->after_price name='Text after price'}
	${menu args->price_style name='Price position', type='css'}
	${menu args->p_price_before_discount name='Price before discount'}
	${menu args->sale_style name='Price before discount: style', type='css', param='with_responsive=1'}
	${menu args->text_6 name='Button Text'}
	${menu args->text_6_style name='Text size', type='css'}
${menu name='Bottom Text', icon='font'}
	${menu args->p2 name='Text'}
${menu name='Button', icon='mouse-pointer'}
	${menu block->with_button2 name='With Button 1'}
	${menu args->button2_text name='Button 1 Text'}
	${menu args->button2_href name='Button Link URL'}
	${menu args->button2_style name='Menu Item Style', type='css'}
	${menu block->with_button3 name='With Button 2'}
	${menu args->button3_text name='Button 2 Text'}
	${menu args->button3_href name='Button Link URL'}
	${menu args->button3_style name='Menu Item Style', type='css'}
${menu name='Bottom Text 2', icon='font'}
	${menu args->p3 name='Text'}
${menu name='With Unsubscribe', icon='ban'}
	${menu block->with_button4 name='With Button 1'}
	${menu args->button4_line_text name='Text Line'}
	${menu args->button4_text_style name='Text Line Style', type='css'}
	${menu args->button4_text name='Button Text'}
	${menu args->button4_style name='Button Style', type='css'}
```


## Cart Abandonment - LTR



```
<html>
<head>
    <meta name="x-apple-disable-message-reformatting">
</head>
<body style="${args->style:html:default('font-family: Verdana, ''Open Sans'', Helvetica, Arial, sans-serif; font-size: 14px; line-height: 1.6; color: #354052; background-color: #f1f1f1; font-weight: 400;')}; width:${args->width:html:default(600px)}">
<table border="0" cellpadding="0" cellspacing="0" align="center" style="border-collapse:collapse; width:${args->width:html}; margin: 0 auto; background-color: #f9f9f9; direction:${args->direction:html:default(ltr)};">
    <tr>
        <td style="text-align:center; vertical-align:top">
            <table border="0" cellpadding="0" cellspacing="0" style="width:100%; border-collapse: collapse; border: 0; ">
                <tr>
                    ${block->with_lefttopblock:default(1)}
                    <td style="${args->lefttopblock_style:html:default('text-align: left; vertical-align: middle; background-color: #00365c;')}">
                        <a ${args->logo_link:default('href="" data-personyze-click-target=""')} style="text-decoration:none;">
                            <img src="${args->logo_url:html:default('https://cdn.personyze.com/upload/4241/6c55bdb6d91d8035.jpeg')}" style="${args->titlelogo_style:html:default('display: block; width: 120px; height: 40px; padding: 10px;')}">
                        </a>
                    </td>
                    ${block->with_righttopblock:default(1)}
                    <td style="${args->righttopblock_style:html:default('text-align: right; vertical-align: middle; background-color: #00365c; padding: 15px;')}">
                        ${args->topbar_right:default('<a href="https://" style="text-decoration:none; background-color: #ffe500; padding: 5px; color: #000000; font-family: verdana, Arial, sans-serif; font-size:15px; font-weight:normal; font-style:normal;" target="_blank">Flash Deals</a>')}</td>
                </tr>
            </table>

            ${block->with_bannerblock:default(1)}
            <table border="0" cellpadding="0" cellspacing="0" style="width:100%; border-collapse: collapse; border: 0; ${args->bannerblock_style:html:default('background:#ebebeb;')}">
                <tr>
                    <td>
                        <img src="${args->banner_url:html:default('https://cdn.personyze.com/upload/4241/db3af990fcf1cdbc.jpeg')}"
                            style="${args->banner_style:html:default('display: block; width: 100%; height: 50%;')}">
                    </td>
                </tr>
            </table>

            ${block->with_discountblock:default(1)}
            <table border="0" cellpadding="0" cellspacing="0" style="width:100%; border-collapse: collapse; border: 0; ${args->discountblock_style:html:default('text-align: center;
font-size: 13px;
background: rgb(0, 152, 86);')}">
                <tr>
                    <td style="font-family:inherit;font-weight:normal;text-align: center;padding-top:20px;padding-bottom:10px;">
                        ${args->discounttextbeforeimage}

                        <img alt="" border="0" src="${args->discountimage_url:html:default('https://cdn.personyze.com/upload/4241/34524b04c9ca8681.jpeg')}" style="${args->discountimage_style:html:default('width: 35%;')}">

                        ${args->discounttextafterimage:default('<p style="color:#ffffff;text-align:center;font-size:20px;font-family: Verdana, ''Open Sans'', Helvetica, Arial, sans-serif; font-weight:500; font-style:normal;  line-height:30px; text-transformorm:none; margin:0;padding-top:30px;padding-right:15px;padding-bottom:30px;padding-left:15px;">Having doubts? Here&rsquo;s a little something to make your cart irresistible!</p>

<h1 style="color:#FFD800;text-align:center;font-family: Verdana, ''Open Sans'', Helvetica, Arial, sans-serif; font-weight:600;margin:0;padding-top: 10px;">Get Extra 5% OFF on your cart!</h1>

<p style="color:#ffffff;text-align:center;font-size:18px;font-family: Verdana, ''Open Sans'', Helvetica, Arial, sans-serif; font-size:18px; font-weight:500; font-style:normal; letter-spacing:normal; line-height:20px; text-transform:none; text-align:center; margin:0;padding-bottom: 15px;">~ Hurry! Limited Time only. ~</p>
')}

                        ${args->discounttextbeforepromo:default('<p style="color:#ffffff;text-align:center;font-size:18px;font-family: Verdana, ''Open Sans'', Helvetica, Arial, sans-serif; font-size:18px; font-weight:500; font-style:normal; letter-spacing:normal; line-height:20px; text-transform:none; margin:0;padding-top:20px;">Use Promo Code:</p>
')}

                        <div style="${args->promoblock_style:html:default('padding-bottom:30px;padding-top:15px;')}">
                            <div style="${args->promocode_style:html:default('display:inline-block; padding: 2px 35px; border-radius:3px; color: #FFD800; font-family: verdana, Arial, sans-serif; font-size:35px; font-weight:400; font-style:normal; letter-spacing:10px; border:3px dashed #ffffff')}">
                                ${args->promocode:default(MAILOFF5)}
                            </div>
                        </div>

                        ${args->discounttextafterpromo}

                        <div style="${args->discountbuttonblock_style:html:default('padding-bottom:30px;padding-top:30px;')}">
                            <a ${args->discountbutton_link:default('href="" data-personyze-click-target=""')} style="${args->discountbutton_style:html:default('text-decoration:none; background-color: #FF9900; padding: 10px;border-radius:3px; color: #ffffff; font-family: verdana, Arial, sans-serif; font-size:15px; font-weight:600; font-style:normal;')}">${args->discountbutton_text:default(Go Back To Cart)}</a>
                        </div>

                    </td>
                </tr>
            </table>

            ${block->with_n_items:default(0)}
            <h3 style="${args->n_items_style:html}">
                ${foreach products_interactions_sum_extra_last_session as p limit 1}
                    ${p->interaction_count:sprintf('You have %s items in your cart:')}
                ${end}
            </h3>

            ${block->with_tabletitles:default(0)}
            <table border="0" cellpadding="0" cellspacing="0" style="width:100%; border-collapse: collapse; border: 0; ${args->tabletitle_style:html}">
                <tr>
                    <td style="${args->tabletitle1_style:html}">
                        ${args->tabletitle1_text}
                    </td>
                    <td style="${args->tabletitle2_style:html}">
                        ${args->tabletitle2_text}
                    </td>
                    <td style="${args->tabletitle3_style:html}">
                        ${args->tabletitle3_text}
                    </td>
                </tr>
            </table>

            ${foreach products_interactions as p where p->interaction_status='extra' and p->interaction_is_last_session order by p->interaction_time desc}
            <table border="0" cellpadding="0" cellspacing="0" width="100%" style="width:100%; border-collapse: collapse; border: 0; ${args->purchasedblock_style:html:default('background:#fff;')}">
                <tr>
                    <td style="${args->itemtablecolumn1_style:html:default('width:150px; padding: 16px 8px; text-align:center; vertical-align:top;')}">
                        <a href="${p->cart_url:html}" target="_blank">
                            <img src="${p->image_big_url:html}" style="${args->itemimage_style:html:default('width:75px; border:none')}">
                        </a>
                    </td>
                    <td style="${args->itemtablecolumn2_style:html:default('width:200px; padding: 16px 8px 0; text-align:left; vertical-align:top;')}">
                        <a href="${p->cart_url:html}" target="_blank">
                            ${p->itemtitle}
                            <br>
                            <div style="${args->itemlinktext_style:html:default('font-size: 12px; font-weight: 600; color: #354052; padding-top:5px; padding-bottom: 10px; text-decoration: none;')}">
                                ${args->itemlinktext:default(VIEW YOUR ITEM)}
                            </div>
                        </a>
                    </td>
                    <td style="${args->itemtablecolumn3_style:html:default('width:100px; padding: 16px 8px 0; text-align:center; vertical-align:top;')}">
                        ${p->interaction_quantity}
                    </td>
                    ${if p->price_after_discount}
                        <td style="${args->itemtablecolumn4_style:html:default('width:150px; padding: 16px 8px; text-align:center; vertical-align:top;')}">
                            ${if p->price_after_discount < p->price_before_discount}
                                <span style="white-space:nowrap">
                                    <span style="${args->old_price_style:html:default('font-size: 17px;
font-weight: 500;
text-decoration: line-through;
')}">
                                        ${args->old_price_before}${args->extra_price_before_discount:default('$${p->price_before_discount:price('''')}')}${args->old_price_after}
                                    </span>
                                </span>
                                <span style="white-space:nowrap">
                                    <span style="${args->new_price_style:html:default('font-size: 17px;
font-weight: 500;
color: black;
')}">
                                        ${args->old_price_before)}${args->extra_price_after_discount:default('$${p->price_after_discount:price('''')}')}${args->old_price_after}
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
                                    ${args->old_price_before}${args->extra_price_before_discount}${args->old_price_after}
                                </span>
                            ${end}
                        </td>
                    ${end}
                </tr>
            </table>
            ${end}

            ${block->with_totalprice:default(1)}
            <div style="width:100%; ${args->totalpriceblock_style:html:default('background:#fff; font-size: 16px; font-weight: 600; color: #DE1F1F; padding-top:5px; padding-right:20px; text-decoration: none; text-align:right; box-sizing: border-box;')}">
                ${args->total:default('TOTAL:')}
                ${foreach products_interactions_sum_extra_last_session as p limit 1}
                    ${p->price:price('')}
                    ${args->currency:html}
                ${end}
            </div>

            ${block->with_tocart:default(1)}
            <div style="width:100%; ${args->tocartblock_style:html:default('background:#fff; padding-top: 30px; padding-bottom: 40px;box-sizing: border-box;')}">
                <a ${args->tocartbutton_link:default('href="" data-personyze-click-target=""')} style="${args->tocartbutton_style:html:default('text-decoration:none; background-color: #FF9900; padding: 10px;border-radius:3px; color: #ffffff; font-family: verdana, Arial, sans-serif; font-size:15px; font-weight:600; font-style:normal;')}">${args->tocartbutton_text:default(Go Back To Cart)}</a>
            </div>

            <div style="width:100%; ${args->recommendedtitle_style:html:default('font-size: 16px; font-weight: 600; color: #fff; padding:10px; text-decoration: none;text-align:center;background: #00365c; box-sizing: border-box;')};">
                ${args->recommendedtitle:default('Not sure what to get? Here are some recommendations:')}
            </div>

            <table border="0" cellpadding="0" cellspacing="0" width="100%" style="width:100%; border-collapse: collapse;">
                <tr>
                    ${foreach products as main order by main->time_created desc limit 5}
                    <td style="width:200px; ${args->itemblock_style:html:default('vertical-align: middle; padding-top:15px')};">
                        <img src="${main->image_big_url:html}" style="${args->itemimage_style:html};">

                        <p style="${args->itemtitle_style:html:default('font-size:12px; text-align:left; padding-left:15px; padding-right:15px;')};">
                            ${args->itemtitle:default('${main->title}')}
                        </p>

                        ${block->price:default(1)}
                        <div style="${args->itemprice_style:html:default('font-size:12px; font-weight:bold; color:#DE1F1F; text-align:left; padding-left:15px; padding-right:15px; padding-top:0; margin-top:0;')};">
                            ${if main->price_after_discount}
                                ${if main->price_after_discount < main->price_before_discount}
                                    <span style="white-space:nowrap">
                                        <span style="${args->old_price_style:html}">
                                            ${args->old_price_before}${args->p_price_before_discount:default('$${main->price_before_discount:price('''')}')}${args->old_price_after}
                                        </span>
                                    </span>
                                    <span style="white-space:nowrap">
                                        <span style="${args->new_price_style:html}">
                                            ${args->old_price_before)}${args->p_price_after_discount:default('$${main->price_after_discount:price('''')}')}${args->old_price_after}
                                        </span>
                                    </span>
                                    <div style="${args->sale_text_style:html}">
                                        ${args->sale_text}
                                    </div>
                                ${else}
                                    <span style="white-space:nowrap; ${args->nosale_price_style:html}">
                                        ${args->old_price_before}${args->p_price_before_discount}${args->old_price_after}
                                    </span>
                                ${end}
                            ${end}
                        </div>

                        ${block->with_buttonblock:default(1)}
                        <p style="${args->itembuttonblock_style:html:default('padding-top: 20px; padding-bottom: 20px;')};">
                            <a href="${main->cart_url:html}" target="_blank" style="${args->itembutton_style:html:default('text-decoration:none; background-color: #FF9900; padding: 5px 10px; border-radius:3px; color: #ffffff; font-family: verdana, Arial, sans-serif; font-size:13px; font-weight:400; font-style:normal;')};">${args->link_text:default(Buy Now)}
                            </a>
                        </p>
                    </td>
                    ${end}
                </tr>
            </table>

            ${block->with_continue:default(1)}
            <div style="width:100%; ${args->continue_style:html:default('background:#fff; padding-top: 30px; padding-bottom: 40px;box-sizing: border-box;')}">
                <a ${args->continuebutton_link:default('href="" data-personyze-click-target=""')} style="${args->continuebutton_style:html:default('text-decoration:none; background-color: #2688DA; padding: 10px;border-radius:3px; color: #ffffff; font-family: verdana, Arial, sans-serif; font-size:15px; font-weight:600; font-style:normal;')}">${args->continuebutton_text:default(Continue Shopping)}</a>
            </div>

            ${block->with_footerblock:default(1)}
            <table border="0" cellpadding="0" cellspacing="0" width="100%" style="width:100%; border-collapse:collapse; border:0;">
                <tr>
                    <td style="${args->footerblock_style:html:default('padding: 20px; font-family: Verdana, ''Open Sans'', Helvetica, Arial, sans-serif; font-size:12px; font-weight:400; font-style:normal; letter-spacing:normal; background-color:rgb(235, 235, 235); color:#343434; text-transform:none; text-align:center;')};">
                        ${args->before_unsubscribe}
                        ${block->with_unsubscribe:default(1)}
                        <span>
                            <a href="http://pic.personyze.com/unsubscribe/k=${action_key:html}/u=${id:html}" style="${args->unsubscribe_style:html:default('color:#343434; text-decoration:underline;')};" target="_blank">
                                ${args->unsubscribe:default(Unsubscribe)}
                            </a>
                        </span>
                        ${args->after_unsubscribe}
                    </td>
                </tr>
            </table>
        </td>
    </tr>
</table>
</body>
</html>

${menu name='Frame', icon='bookmark'}
	${menu args->width name='Width', type='css_length'}
	${menu args->style name='Style', type='css'}
	${menu args->currency name='Currency symbol'}
	${menu args->direction name='Localization settings', type='select', param='options=[["Left to right","ltr"],["Right to left","rtl"]]'}
${menu name='Left top', icon='bookmark'}
	${menu block->with_lefttopblock name='With left top block'}
	${menu args->lefttopblock_style name='Block style', type='css'}
	${menu args->logo_url name='Logo image URL', type='personyze_media_url'}
	${menu args->titlelogo_style name='Logo style', type='css'}
	${menu args->logo_link name='Link URL', type='a_attrs'}
${menu name='Right top', icon='bookmark'}
	${menu block->with_righttopblock name='With right top block'}
	${menu args->righttopblock_style name='Block style', type='css'}
	${menu args->topbar_right name='Label'}
${menu name='Banner', icon='bookmark'}
	${menu block->with_bannerblock name='With banner block'}
	${menu args->bannerblock_style name='Block style', type='css'}
	${menu args->banner_url name='Banner image URL', type='personyze_media_url'}
	${menu args->banner_style name='Banner style', type='css'}
${menu name='Discount', icon='bookmark'}
	${menu block->with_discountblock name='With discount block'}
	${menu args->discountblock_style name='Block style', type='css'}
	${menu args->discounttextbeforeimage name='Text before image'}
	${menu args->discountimage_url name='Image URL', type='personyze_media_url'}
	${menu args->discountimage_style name='Image style', type='css'}
	${menu args->discounttextafterimage name='Text after image'}
	${menu args->discounttextbeforepromo name='Text before promo'}
	${menu args->promoblock_style name='Promo block style', type='css'}
	${menu args->promocode name='Promo code'}
	${menu args->promocode_style name='Promo code style', type='css'}
	${menu args->discounttextafterpromo name='Text after promo'}
	${menu args->discountbuttonblock_style name='Button block style', type='css'}
	${menu args->discountbutton_link name='Button URL', type='a_attrs'}
	${menu args->discountbutton_text name='Button text'}
	${menu args->discountbutton_style name='Button style', type='css'}
${menu name='Number of items header', icon='hashtag'}
	${menu block->with_n_items name='With Number of items header'}
	${menu p->interaction_count:sprintf('You have %s items in your cart:') name='Number of items header'}
	${menu args->n_items_style name='Number of items header: style', type='css'}
${menu name='Table titles', icon='list'}
	${menu block->with_tabletitles name='With table titles'}
	${menu args->tabletitle_style name='Block style', type='css'}
	${menu args->tabletitle1_text name='Item'}
	${menu args->tabletitle1_style name='Title 1 style', type='css'}
	${menu args->tabletitle2_text name='Quantity'}
	${menu args->tabletitle2_style name='Title 2 style', type='css'}
	${menu args->tabletitle3_text name='Price'}
	${menu args->tabletitle3_style name='Title 3 style', type='css'}
${menu name='Item table', icon='font'}
	${menu args->purchasedblock_style name='Block style', type='css'}
	${menu args->itemtablecolumn1_style name='Item table column 1 style', type='css'}
	${menu p->image_big_url name='Item image'}
	${menu args->itemimage_style name='Item image style', type='css'}
	${menu p->cart_url name='Item link URL', column_tags='url, custom text'}
	${menu args->itemtablecolumn2_style name='Item table column 2 style', type='css'}
	${menu p->itemtitle name='Item title'}
	${menu args->itemlinktext name='Item link text'}
	${menu args->itemlinktext_style name='Item link text style', type='css'}
	${menu args->itemtablecolumn3_style name='Item table column 3 style', type='css'}
	${menu p->interaction_quantity name='Item quantity'}
	${menu args->itemtablecolumn4_style name='Item table column 4 style', type='css'}
${menu name='Total price', icon='money'}
	${menu block->with_totalprice name='With total price'}
	${menu args->totalpriceblock_style name='Block style', type='css'}
	${menu args->total name='Total caption'}
${menu name='Go to cart button', icon='hand-pointer-o'}
	${menu block->with_tocart name='With go to cart button'}
	${menu args->tocartblock_style name='Block style', type='css'}
	${menu args->tocartbutton_link name='Button URL', type='a_attrs'}
	${menu args->tocartbutton_text name='Button text'}
	${menu args->tocartbutton_style name='Button style', type='css'}
${menu name='Recommended products', icon='font'}
	${menu args->recommendedtitle name='Title'}
	${menu args->itemblock_style name='Block style', type='css'}
	${menu args->recommendedtitle_style name='Title style', type='css'}
	${menu args->itemtitle name='Title'}
	${menu args->itemtitle_style name='Title style', type='css'}
	${menu main->image_big_url name='Image URL'}
	${menu args->itemprice_style name='Style', type='css'}
	${menu block->with_buttonblock name='With button block'}
	${menu args->itembuttonblock_style name='Style', type='css'}
	${menu args->link_text name='Link text'}
	${menu main->cart_url name='Link URL'}
	${menu args->itembutton_style name='Link style', type='css'}
	${menu args->extra_price_before_discount name='Price before discount'}
	${menu args->extra_price_after_discount name='Price after discount'}
${menu name='Price', icon='dollar'}
	${menu block->price name='With price'}
	${menu args->old_price_style name='Price before discount - style', type='css'}
	${menu args->old_price_before name='Price before discount - text before'}
	${menu args->p_price_before_discount name='Price before discount'}
	${menu args->old_price_after name='Price before discount - text before'}
	${menu args->p_price_after_discount name='Price after discount'}
	${menu args->new_price_style name='Price after discount - style', type='css'}
	${menu args->sale_text_style name='Sale text style', type='css'}
	${menu args->sale_text name='Sale text'}
	${menu args->nosale_price_style name='Price without discount - style', type='css'}
${menu name='Continue Shopping button', icon='hand-pointer-o'}
	${menu block->with_continue name='With Continue Shopping button'}
	${menu args->continue_style name='Block style', type='css'}
	${menu args->continuebutton_link name='Button URL', type='a_attrs'}
	${menu args->continuebutton_text name='Button text'}
	${menu args->continuebutton_style name='Button style', type='css'}
${menu name='With footer block', icon='ban'}
	${menu block->with_footerblock name='With footer block'}
	${menu args->footerblock_style name='Block style', type='css'}
	${menu args->before_unsubscribe name='Text before unsubscribe'}
	${menu block->with_unsubscribe name='With Unsubscribe'}
	${menu args->unsubscribe name='Link text'}
	${menu args->unsubscribe_style name='Link style', type='css'}
	${menu args->after_unsubscribe name='Text after unsubscribe'}
```


## Recent purchase cross-sell

Show the last purchase item with recommended items to buy together

```
<html>
<head>
    <meta name="x-apple-disable-message-reformatting">
</head>
<body style="${args->style:html:default('font-family: Verdana, ''Open Sans'', Helvetica, Arial, sans-serif;
font-size: 14px;
line-height: 1.6;
color: #354052;
background-color: #f1f1f1;
font-weight: 400;
')}; width:${args->width:html:default(600px)}">
<table border="0" cellpadding="0" cellspacing="0" align="center" style="border-collapse:collapse; width:${args->width:html}; margin: 0 auto; background-color: #f9f9f9; direction:${args->direction:html:default(ltr)};">
    <tr>
        <td style="text-align:center; vertical-align:top">
            <table border="0" cellpadding="0" cellspacing="0" style="width:100%; border-collapse:collapse; border:0">
                <tr>

                    <td style="${args->lefttopblock_style:html:default('text-align: left; vertical-align: middle; background-color: #00365c;')}">
                        <a href="${args->logo_link:html}" target="${args->title_target:html:default(_blank)}"
                            style="text-decoration:none;">
                            <img src="${args->logo_url:html:default('https://cdn.personyze.com/upload/4241/6c55bdb6d91d8035.jpeg')}"
                                style="${args->titlelogo_style:html:default('display: block; width: 120px; height: 40px; padding: 10px;')}">
                        </a>
                    </td>

                    <td style="${args->righttopblock_style:html:default('text-align: right; vertical-align: middle; background-color: #00365c; padding: 15px;')}">
                        ${args->topbar_right:default('<a href="https://" style="text-decoration:none; background-color: #ffe500; padding: 5px; color: #000000; font-family: verdana, Arial, sans-serif; font-size:15px; font-weight:normal; font-style:normal;" target="_blank">Flash Deals</a>')}
                    </td>
                </tr>
            </table>


            <table border="0" cellpadding="0" cellspacing="0" style="width:100%; border-collapse:collapse; border:0; ${args->bannerblock_style:html:default('background:#ebebeb;')}">
                <tr>
                    <td>
                        <img src="${args->banner_url:html:default('https://cdn.personyze.com/upload/4241/db3af990fcf1cdbc.jpeg')}"
                            style="${args->banner_style:html:default('display: block; width: 100%; height: 50%;')}">
                    </td>
                </tr>
            </table>

            <div style="${args->extra_title_style:html:default('font-size: 16px;
font-weight: 400;
color: #fff;
padding: 10px;
text-decoration: none;
text-align: center;
background: #00365c;
')}">
                ${args->extra_title:default(You added to cart)}
            </div>

            <table border="0" cellpadding="0" cellspacing="0" width="100%" style="width:100%; border-collapse:collapse; border:0; ${args->extra_block_style:html:default('background-color:#ebebeb;')}">
                ${foreach products_interactions as main where main->interaction_status in ('extra') order by main->interaction_time desc limit 3}
                    <tr>
                        <td style="vertical-align: middle; text-align:left; ${args->extra_left_column:html:default('padding:0 1em')};">
                            <img src="${main->image_big_url:html}"
                                style="${args->extra_image_style:html:default('width: auto;
height: auto;
max-width: 75px;
padding: 20px;
')}">
                        </td>
                        <td style="vertical-align:middle; text-align:center; ${args->extra_product_name_style:html}">
                            ${args->extra_product_name:default('${main->title}')}
                        </td>
                        ${block->price:default(1)}
                        <td style="vertical-align:middle; text-align:right; ${args->extra_product_price_style:html:default('padding:0 1em')}">
                            ${if main->price_after_discount}
                                ${if main->price_after_discount < main->price_before_discount}
                                    <span style="white-space:nowrap">
                                        <span style="${args->old_price_style:html}">
                                            ${args->old_price_before}${args->extra_price_before_discount:default('$${main->price_before_discount:price('''')}')}${args->old_price_after}
                                        </span>
                                    </span>
                                    <span style="white-space:nowrap">
                                        <span style="${args->new_price_style:html}">
                                            ${args->old_price_before)}${args->extra_price_after_discount:default('$${main->price_after_discount:price('''')}')}${args->old_price_after}
                                        </span>
                                    </span>
                                    <div style="${args->sale_text_style:html}">
                                        ${args->sale_text}
                                    </div>
                                ${else}
                                    <span style="white-space:nowrap; ${args->nosale_price_style:html}">
                                        ${args->old_price_before}${args->extra_price_before_discount}${args->old_price_after}
                                    </span>
                                ${end}
                            ${end}
                        </td>
                    </tr>
                ${end}
            </table>

            ${block->with_gotocart:default(1)}
            <div style="${args->gotocart_block_style:html:default('background-color:#ebebeb')}">
                <a ${args->gotocart_attrs} style="display:inline-block; ${args->gotocart_style:html:default('text-decoration: none;
background-color: #FF9900;
padding-top: 5px;
padding-right: 10px;
padding-bottom: 5px;
padding-left: 10px;
margin: 1em;
border-radius: 3px;
color: #ffffff;
font-family: verdana, Arial, sans-serif;
font-size: 13px;
font-weight: 400;
font-style: normal;
')};">
                    ${args->gotocart_text:default(Go to cart)}
                </a>
            </div>

            ${block->with_recom1:default(1)}
            <table border="0" cellpadding="0" cellspacing="0" width="100%" style="width:100%; border-collapse: collapse;">
                <caption style="${args->recom1_recommendedtitle_style:html:default('font-size: 16px;
font-weight: 400;
color: #fff;
padding: 10px;
text-decoration: none;
text-align: center;
background: #00365c;
')}">
                    ${args->recom1_recommendedtitle:default(Recommended Products)}
                </caption>
                <tr>
                    ${foreach recom_products_viewed_viewed_for_extra as recom1 where (recom1->image_big_url IS NOT NULL AND recom1->image_big_url!='') and (recom1->title IS NOT NULL AND recom1->title!='') union recom_products_filled limit 3}
                        <td style="width:33.3333%; ${args->recom1_itemblock_style:html:default('vertical-align: middle;
padding-top: 15px;
')};">
                            <img src="${recom1->image_big_url:html}" style="${args->recom1_itemimage_style:html:default('width: 100px;
')};">

                            <p style="${args->recom1_itemtitle_style:html:default('font-size: 12px;
text-align: left;
padding-right: 15px;
padding-left: 15px;
')};">
                                ${args->recom1_itemtitle:default('${recom1->title}')}
                            </p>

                            ${if recom1->price_after_discount}
                                ${block->price:default(1)}
                                <div style="${args->price_style:html:default('font-size: 12px;
font-weight: bold;
color: #DE1F1F;
text-align: left;
padding-top: 0;
padding-right: 15px;
padding-left: 15px;
margin-top: 0;
')}">
                                    ${if recom1->price_after_discount < recom1->price_before_discount}
                                        <span style="white-space:nowrap">
                                            <span style="${args->old_price_style:html}">
                                                ${args->old_price_before}${args->recom1_price_before_discount:default('$${recom1->price_before_discount:price('''')}')}${args->old_price_after}
                                            </span>
                                        </span>
                                        <span style="white-space:nowrap">
                                            <span style="${args->new_price_style:html}">
                                                ${args->old_price_before)}${args->recom1_price_after_discount:default('$${recom1->price_after_discount:price('''')}')}${args->old_price_after}
                                            </span>
                                        </span>
                                        <div style="${args->sale_text_style:html}">
                                            ${args->sale_text}
                                        </div>
                                    ${else}
                                        <span style="white-space:nowrap; ${args->nosale_price_style:html}">
                                            ${args->old_price_before}${args->recom1_price_before_discount}${args->old_price_after}
                                        </span>
                                    ${end}
                                </div>
                            ${end}


                            <p style="${args->recom1_itembuttonblock_style:html:default('padding-top: 20px;
padding-bottom: 20px;
')};">
                                <a href="${recom1->cart_url:html}" target="_blank" style="display:inline-block; ${args->recom1_itembutton_style:html:default('text-decoration: none;
background-color: #FF9900;
padding-top: 5px;
padding-right: 10px;
padding-bottom: 5px;
padding-left: 10px;
border-radius: 3px;
color: #ffffff;
font-family: verdana, Arial, sans-serif;
font-size: 13px;
font-weight: 400;
font-style: normal;
')};">${args->recom1_link_text:default(Buy Now)}
                                </a>
                            </p>
                        </td>
                    ${end}
                </tr>
            </table>

            ${block->with_recom2:default(0)}
            <table border="0" cellpadding="0" cellspacing="0" width="100%" style="width:100%; border-collapse: collapse;">
                <caption style="${args->recom2_recommendedtitle_style:html:default('font-size: 16px;
font-weight: 400;
color: #fff;
padding: 10px;
text-decoration: none;
text-align: center;
background: #00365c;
')}">
                    ${args->recom2_recommendedtitle:default(Recommended Products)}
                </caption>
                <tr>
                    ${foreach recom_products_goal_goal_for_goal as recom2 where (recom2->image_big_url IS NOT NULL AND recom2->image_big_url!='') and (recom2->title IS NOT NULL AND recom2->title!='') union recom_products_filled limit 3}
                        <td style="width:33.3333%; ${args->recom2_itemblock_style:html:default('vertical-align: middle;
padding-top: 15px;
')};">
                            <img src="${recom2->image_big_url:html}" style="${args->recom2_itemimage_style:html:default('width: 100px;
')};">

                            <p style="${args->recom2_itemtitle_style:html:default('font-size: 12px;
text-align: left;
padding-right: 15px;
padding-left: 15px;
')};">
                                ${args->recom2_itemtitle:default('${recom2->title}')}
                            </p>

                            ${if recom2->price_after_discount}
                                ${block->price:default(1)}
                                <div style="${args->price_style:html}">
                                    ${if recom2->price_after_discount < recom2->price_before_discount}
                                        <span style="white-space:nowrap">
                                            <span style="${args->old_price_style:html}">
                                                ${args->old_price_before}${args->recom2_price_before_discount:default('$${recom2->price_before_discount:price('''')}')}${args->old_price_after}
                                            </span>
                                        </span>
                                        <span style="white-space:nowrap">
                                            <span style="${args->new_price_style:html}">
                                                ${args->old_price_before)}${args->recom2_price_after_discount:default('$${recom2->price_after_discount:price('''')}')}${args->old_price_after}
                                            </span>
                                        </span>
                                        <div style="${args->sale_text_style:html}">
                                            ${args->sale_text}
                                        </div>
                                    ${else}
                                        <span style="white-space:nowrap; ${args->nosale_price_style:html}">
                                            ${args->old_price_before}${args->recom2_price_before_discount}${args->old_price_after}
                                        </span>
                                    ${end}
                                </div>
                            ${end}


                            <p style="${args->recom2_itembuttonblock_style:html:default('padding-top: 20px;
padding-bottom: 20px;
')};">
                                <a href="${recom2->cart_url:html}" target="_blank" style="display:inline-block; ${args->recom2_itembutton_style:html:default('text-decoration: none;
background-color: #FF9900;
padding-top: 5px;
padding-right: 10px;
padding-bottom: 5px;
padding-left: 10px;
border-radius: 3px;
color: #ffffff;
font-family: verdana, Arial, sans-serif;
font-size: 13px;
font-weight: 400;
font-style: normal;
')};">${args->recom2_link_text:default(Buy Now)}
                                </a>
                            </p>
                        </td>
                    ${end}
                </tr>
            </table>

            ${block->with_recom3:default(0)}
            <table border="0" cellpadding="0" cellspacing="0" width="100%" style="width:100%; border-collapse: collapse;">
                <caption style="${args->recom3_recommendedtitle_style:html:default('font-size: 16px;
                    font-weight: 400;
                    color: #fff;
                    padding: 10px;
                    text-decoration: none;
                    text-align: center;
                    background: #00365c;
                    ')}">
                    ${args->recom3_recommendedtitle:default(Recommended Products)}
                </caption>
                <tr>
                    ${foreach recom_products_for_favorite as recom3 where (recom3->image_big_url IS NOT NULL AND recom3->image_big_url!='') and (recom3->title IS NOT NULL AND recom3->title!='') union recom_products_filled limit 3}
                        <td style="width:33.3333%; ${args->recom3_itemblock_style:html:default('vertical-align: middle;
padding-top: 15px;
')};">
                            <img src="${recom3->image_big_url:html}" style="${args->recom3_itemimage_style:html:default('width: 100px;
')};">

                            <p style="${args->recom3_itemtitle_style:html:default('font-size: 12px;
text-align: left;
padding-right: 15px;
padding-left: 15px;
')};">
                                ${args->recom3_itemtitle:default('${recom3->title}')}
                            </p>

                            ${if recom3->price_after_discount}
                                ${block->price:default(1)}
                                <div style="${args->price_style:html}">
                                    ${if recom3->price_after_discount < recom3->price_before_discount}
                                        <span style="white-space:nowrap">
                                            <span style="${args->old_price_style:html}">
                                                ${args->old_price_before}${args->recom3_price_before_discount:default('$${recom3->price_before_discount:price('''')}')}${args->old_price_after}
                                            </span>
                                        </span>
                                        <span style="white-space:nowrap">
                                            <span style="${args->new_price_style:html}">
                                                ${args->old_price_before)}${args->recom3_price_after_discount:default('$${recom3->price_after_discount:price('''')}')}${args->old_price_after}
                                            </span>
                                        </span>
                                        <div style="${args->sale_text_style:html}">
                                            ${args->sale_text}
                                        </div>
                                    ${else}
                                        <span style="white-space:nowrap; ${args->nosale_price_style:html}">
                                            ${args->old_price_before}${args->recom3_price_before_discount}${args->old_price_after}
                                        </span>
                                    ${end}
                                </div>
                            ${end}


                            <p style="${args->recom3_itembuttonblock_style:html:default('padding-top: 20px;
padding-bottom: 20px;
')};">
                                <a href="${recom3->cart_url:html}" target="_blank" style="display:inline-block; ${args->recom3_itembutton_style:html:default('text-decoration: none;
background-color: #FF9900;
padding-top: 5px;
padding-right: 10px;
padding-bottom: 5px;
padding-left: 10px;
border-radius: 3px;
color: #ffffff;
font-family: verdana, Arial, sans-serif;
font-size: 13px;
font-weight: 400;
font-style: normal;
')};">${args->recom3_link_text:default(Buy Now)}
                                </a>
                            </p>
                        </td>
                    ${end}
                </tr>
            </table>

            ${block->with_recom4:default(0)}
            <table border="0" cellpadding="0" cellspacing="0" width="100%" style="width:100%; border-collapse: collapse;">
                <caption style="${args->recom4_recommendedtitle_style:html:default('font-size: 16px;
                    font-weight: 400;
                    color: #fff;
                    padding: 10px;
                    text-decoration: none;
                    text-align: center;
                    background: #00365c;
                    ')}">
                    ${args->recom4_recommendedtitle:default(Recommended Products)}
                </caption>
                <tr>
                    ${foreach recom_products_viewed_viewed_for_last as recom4 where (recom4->image_big_url IS NOT NULL AND recom4->image_big_url!='') and (recom4->title IS NOT NULL AND recom4->title!='') order by recom4->recom_rate_n_transactions desc limit 3}
                        <td style="width:33.3333%; ${args->recom4_itemblock_style:html:default('vertical-align: middle;
padding-top: 15px;
')};">
                            <img src="${recom4->image_big_url:html}" style="${args->recom4_itemimage_style:html:default('width: 100px;
')};">

                            <p style="${args->recom4_itemtitle_style:html:default('font-size: 12px;
text-align: left;
padding-right: 15px;
padding-left: 15px;
')};">
                                ${args->recom4_itemtitle:default('${recom4->title}')}
                            </p>

                            ${if recom4->price_after_discount}
                                ${block->price:default(1)}
                                <div style="${args->price_style:html}">
                                    ${if recom4->price_after_discount < recom4->price_before_discount}
                                        <span style="white-space:nowrap">
                                            <span style="${args->old_price_style:html}">
                                                ${args->old_price_before}${args->recom4_price_before_discount:default('$${recom4->price_before_discount:price('''')}')}${args->old_price_after}
                                            </span>
                                        </span>
                                        <span style="white-space:nowrap">
                                            <span style="${args->new_price_style:html}">
                                                ${args->old_price_before)}${args->recom4_price_after_discount:default('$${recom4->price_after_discount:price('''')}')}${args->old_price_after}
                                            </span>
                                        </span>
                                        <div style="${args->sale_text_style:html}">
                                            ${args->sale_text}
                                        </div>
                                    ${else}
                                        <span style="white-space:nowrap; ${args->nosale_price_style:html}">
                                            ${args->old_price_before}${args->recom4_price_before_discount}${args->old_price_after}
                                        </span>
                                    ${end}
                                </div>
                            ${end}


                            <p style="${args->recom4_itembuttonblock_style:html:default('padding-top: 20px;
padding-bottom: 20px;
')};">
                                <a href="${recom4->cart_url:html}" target="_blank" style="display:inline-block; ${args->recom4_itembutton_style:html:default('text-decoration: none;
background-color: #FF9900;
padding-top: 5px;
padding-right: 10px;
padding-bottom: 5px;
padding-left: 10px;
border-radius: 3px;
color: #ffffff;
font-family: verdana, Arial, sans-serif;
font-size: 13px;
font-weight: 400;
font-style: normal;
')};">${args->recom4_link_text:default(Buy Now)}
                                </a>
                            </p>
                        </td>
                    ${end}
                </tr>
            </table>


            <table border="0" cellpadding="0" cellspacing="0" width="100%" style="width:100%; border-collapse:collapse; border:0;">
                <tr>
                    <td style="${args->footerblock_style:html:default('padding: 20px;
font-family: Verdana, ''Open Sans'', Helvetica, Arial, sans-serif;
font-size: 12px;
font-weight: 400;
font-style: normal;
letter-spacing: normal;
background-color: rgb(235, 235, 235);
color: #343434;
text-transform: none;
text-align: center;
')};">
                        ${args->before_unsubscribe}

                        <span>
                            <a href="http://pic.personyze.com/unsubscribe/k=${action_key:html}/u=${id:html}" style="${args->unsubscribe_style:html:default('color: #343434;
text-decoration: underline;
')};" target="_blank">
                                ${args->unsubscribe:default(Unsubscribe)}
                            </a>
                        </span>
                        ${args->after_unsubscribe}
                    </td>
                </tr>
            </table>
        </td>
    </tr>
</table>
</body>
</html>

${menu name='Frame', icon='bookmark'}
	${menu args->width name='Width', type='css_length'}
	${menu args->style name='Style', type='css'}
	${menu args->direction name='Localization settings', type='select', param='options=[["Left to right","ltr"],["Right to left","rtl"]]'}
${menu name='Left top', icon='bookmark'}
	${menu args->lefttopblock_style name='Block style', type='css'}
	${menu args->logo_url name='Logo image URL', type='personyze_media_url'}
	${menu args->titlelogo_style name='Logo style', type='css'}
	${menu args->logo_link name='Link target URL'}
	${menu args->title_target name='Open link in', type='a_target'}
${menu name='Right top', icon='bookmark'}
	${menu args->righttopblock_style name='Block style', type='css'}
	${menu args->topbar_right name='Label'}
${menu name='Banner', icon='bookmark'}
	${menu args->bannerblock_style name='Block style', type='css'}
	${menu args->banner_url name='Banner image URL', type='personyze_media_url'}
	${menu args->banner_style name='Banner style', type='css'}
${menu name='Added to cart items', icon='font'}
	${menu args->extra_block_style name='Block style', type='css'}
	${menu args->extra_title name='Title'}
	${menu args->extra_title_style name='Title style', type='css'}
	${menu args->extra_left_column name='Left column style', type='css'}
	${menu args->extra_product_name name='Product name'}
	${menu args->extra_product_name_style name='Product name style', type='css'}
	${menu args->extra_image_style name='Image style', type='css'}
	${menu args->extra_product_price_style name='Product price style', type='css'}
	${menu main->image_big_url name='Image URL'}
${menu name='Go to cart button', icon='font'}
	${menu block->with_gotocart name='With Go to cart button'}
	${menu args->gotocart_text name='Button text'}
	${menu args->gotocart_attrs name='Button link', type='a_attrs'}
	${menu args->gotocart_style name='Button style', type='css'}
	${menu args->gotocart_block_style name='Button block style', type='css'}
${menu name='Recommendation based on items in cart', icon='font'}
	${menu block->with_recom1 name='With Recommendation based on items in cart'}
	${menu args->recom1_recommendedtitle name='Title'}
	${menu args->recom1_recommendedtitle_style name='Title style', type='css'}
	${menu args->recom1_itemblock_style name='Block style', type='css'}
	${menu args->recom1_itemtitle name='Title'}
	${menu args->recom1_itemtitle_style name='Title style', type='css'}
	${menu recom1->image_big_url name='Image URL'}
	${menu args->recom1_itemimage_style name='Image style', type='css'}
	${menu args->recom1_itembuttonblock_style name='Style', type='css'}
	${menu args->recom1_link_text name='Link text'}
	${menu recom1->cart_url name='Link URL'}
	${menu args->recom1_itembutton_style name='Link style', type='css'}
	${menu args->recom1_price_before_discount name='Price before discount'}
	${menu args->recom1_price_after_discount name='Price after discount'}
${menu name='Recommendation based on recent purchase', icon='font'}
	${menu block->with_recom2 name='With Recommendation based on recent purchase'}
	${menu args->recom2_recommendedtitle name='Title'}
	${menu args->recom2_recommendedtitle_style name='Title style', type='css'}
	${menu args->recom2_itemblock_style name='Block style', type='css'}
	${menu args->recom2_itemtitle name='Title'}
	${menu args->recom2_itemtitle_style name='Title style', type='css'}
	${menu recom2->image_big_url name='Image URL'}
	${menu args->recom2_itemimage_style name='Image style', type='css'}
	${menu args->recom2_itembuttonblock_style name='Style', type='css'}
	${menu args->recom2_link_text name='Link text'}
	${menu recom2->cart_url name='Link URL'}
	${menu args->recom2_itembutton_style name='Link style', type='css'}
	${menu args->recom2_price_before_discount name='Price before discount'}
	${menu args->recom2_price_after_discount name='Price after discount'}
${menu name='Recommendation based on wishlist', icon='font'}
	${menu block->with_recom3 name='With Recommendation based on wishlist'}
	${menu args->recom3_recommendedtitle name='Title'}
	${menu args->recom3_recommendedtitle_style name='Title style', type='css'}
	${menu args->recom3_itemblock_style name='Block style', type='css'}
	${menu args->recom3_itemtitle name='Title'}
	${menu args->recom3_itemtitle_style name='Title style', type='css'}
	${menu recom3->image_big_url name='Image URL'}
	${menu args->recom3_itemimage_style name='Image style', type='css'}
	${menu args->recom3_itembuttonblock_style name='Style', type='css'}
	${menu args->recom3_link_text name='Link text'}
	${menu recom3->cart_url name='Link URL'}
	${menu args->recom3_itembutton_style name='Link style', type='css'}
	${menu args->recom3_price_before_discount name='Price before discount'}
	${menu args->recom3_price_after_discount name='Price after discount'}
${menu name='Recommendation based on recent views', icon='font'}
	${menu block->with_recom4 name='With Recommendation based on recent views'}
	${menu args->recom4_recommendedtitle name='Title'}
	${menu args->recom4_recommendedtitle_style name='Title style', type='css'}
	${menu args->recom4_itemblock_style name='Block style', type='css'}
	${menu args->recom4_itemtitle name='Title'}
	${menu args->recom4_itemtitle_style name='Title style', type='css'}
	${menu recom4->image_big_url name='Image URL'}
	${menu args->recom4_itemimage_style name='Image style', type='css'}
	${menu args->recom4_itembuttonblock_style name='Style', type='css'}
	${menu args->recom4_link_text name='Link text'}
	${menu recom4->cart_url name='Link URL'}
	${menu args->recom4_itembutton_style name='Link style', type='css'}
	${menu args->recom4_price_before_discount name='Price before discount'}
	${menu args->recom4_price_after_discount name='Price after discount'}
${menu name='Price', icon='dollar'}
	${menu block->price name='With price'}
	${menu args->price_style name='Price style', type='css', param='with_responsive=1'}
	${menu args->old_price_style name='Price before discount - style', type='css'}
	${menu args->old_price_before name='Price before discount - text before'}
	${menu args->old_price_after name='Price before discount - text before'}
	${menu args->new_price_style name='Price after discount - style', type='css'}
	${menu args->sale_text_style name='Sale text style', type='css'}
	${menu args->sale_text name='Sale text'}
	${menu args->nosale_price_style name='Price without discount - style', type='css'}
${menu name='With footer block', icon='ban'}
	${menu args->footerblock_style name='Block style', type='css'}
	${menu args->before_unsubscribe name='Text before unsubscribe'}
	${menu args->unsubscribe name='Link text'}
	${menu args->unsubscribe_style name='Link style', type='css'}
	${menu args->after_unsubscribe name='Text after unsubscribe'}
```


## Email with dynamic products



```
<html>

<head>
    <meta name="x-apple-disable-message-reformatting">
    <style>
        .prod-content-wrapper {width: 234px!important; margin: 0 auto!important; padding: 9px 0px 10px 0px!important; text-align: left!important;}
        .product-container {margin: 10px!important; }
    </style>
</head>

<body>

    <div style="box-sizing:border-box; ${args->page_width:html:default('max-width: 650px;
width: 100%;
margin-top: 0;
margin-right: auto;
margin-bottom: 0;
margin-left: auto;
')}">

        <table style="border-collapse:collapse; width:100%; ${args->page_style:html:default('font-family: ''Roboto'', ''Open Sans'', Helvetica, Arial, sans-serif;
font-size: 14px;
line-height: 1.6;
color: rgb(234, 231, 231);
background-color: #F8F8F8;
font-weight: 400;
margin-top: 1px;
margin-right: auto;
margin-bottom: 1px;
margin-left: auto;
')}">


            <!-- Start of Header Image -->

            ${block->with_top:default(1)}
            <tr>
                <td style="position:relative;background-position: center; background-size: cover; background-repeat: no-repeat; border-top-left-radius: 10px; border-top-right-radius: 10px; background-color: #017EDB;">
                    <div style="width:100%; height:100%; min-height: 115px;">
                        <table style="width:100%; height:100%; border-collapse:collapse">
                            <tr>
                                <td style="text-align:center; vertical-align: top;">
                                    <div style="display:inline-block; ${args->caption_style:html:default('padding: 30px;
color: rgb(251, 250, 250);
')}">
                                        ${args->caption:default('Hi&nbsp;${first_name},<br />
Here are some of your recently viewed')}
                                    </div>
                                </td>
                            </tr>
                        </table>
                    </div>
                </td>
            </tr>


            <!-- Start of Header Image -->


            <!-- Start of Intro Text -->

            <tr>
                <td>
                    <div style="${args->text_1_style:html:default('text-align: left;
color: #404846;
font-size: 16px;
font-family: Roboto;
padding: 30px;
font-weight: regular;
')}">
                        ${args->text_1:default(You visited our website earlier and entered your details for us to send you some of your recently viewed items.)}
                    </div>
                </td>
            </tr>


            <!-- End of Intro Text -->


            <!-- Start of Products -->


            <tr>
                <td style="${args->cells_style:html:default('text-align: center;
padding-bottom: 30px;
display: inline-block;
')}">
                    ${foreach products_interactions as p where p->interaction_status in ('viewed') order by p->interaction_time desc limit 4}
                    <a class="product-container" href="${if p->cart_url:substr(0, 1) != '/'}${p->cart_url:html}${end}${if p->cart_url:substr(0, 1) = '/'}https://${last_domain:html:default(macklinmotors.co.uk)}${p->cart_url:html}${end}" target="_blank" style="display:inline-block; vertical-align:top; ${args->cell_style:html:default('text-decoration: none;
border: 1px solid #80808038;
border-radius: 5px;
min-height: 260px!important;
background-color: #fff;
')}">

                        <div style="position:relative">
                            <img src="${if p->image_big_url:substr(0, 1) != '/'}${p->image_big_url:html}${end}${if p->image_big_url:substr(0, 1) = '/'}https://${last_domain:html:default(macklinmotors.co.uk)}${p->image_big_url:html}${end}" style="${args->img_style:html:default('border-top-left-radius: 5px;border-top-right-radius: 5px;border-bottom-right-radius: 0px;border-bottom-left-radius: 0px;')}; width:${args->img_width:html:default(260px)}; height:${args->img_height:html:default(auto)}" onerror="this.parentNode.style.display='none'">

                            ${block->with_discount_badge:default(1)}
                            <span>
                                ${if p->discount_percent >= args->min_discount_percent:default(1)}
                                    <div style="position: absolute; ${args->discount_badge_style:html:default('top: 0;
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
                                        <span style="${args->discount_badge_text_style:html:default('line-height: 1.25;
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
                                    <div style="position: absolute; ${args->new_badge_style:html:default('top: 0;
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
                                        <span style="${args->new_badge_text_style:html:default('font-size: 16px;
font-weight: 600;
')}">${args->new_badge_text:default(NEW)}</span>
                                    </div>
                                ${end}
                            </span>

                            ${block->with_time_badge:default(1)}
                            <span>
                                ${if p->custom_i_1 - unix_timestamp() >= 0}
                                    <div style="position: absolute; ${args->time_badge_style:html:default('top: 0;
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
                                        <span style="${args->time_badge_text_style:html:default('font-size: 16px;
font-weight: 600;
')}">${args->time_badge_text:default(Special offer till)}</span>
                                    </div>
                                ${end}
                            </span>

                            ${block->with_stock_badge:default(1)}
                            <span>
                                ${if p->inventory between 1 and args->badge_if_less_stock:default(3)}
                                    <div style="position: absolute; ${args->stock_badge_style:html:default('bottom: 0;
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
                                        <span style="${args->stock_badge_text_style:html:default('font-size: 16px;
font-weight: 500;
')}">${args->stock_badge_text:default('${p->inventory}&nbsp;left in stock')}</span>
                                    </div>
                                ${end}
                            </span>

                            ${block->with_db_badge:default(0)}
                            <span>
                                <div style="position: absolute; ${args->db_badge_style:html:default('top: 0;
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
                                    <span style="${args->db_badge_text_style:html:default('font-size: 16px;
font-weight: 600;
')}">${args->db_badge_text:default('${p->custom_2}')}</span>
                                </div>
                            </span>
                        </div>

                        <div class="prod-content-wrapper">

                            <div style="box-sizing:border-box; max-width:${args->img_width:html}; ${args->p_title_style:html:default('font-size: 16px;
font-weight: 700;
text-overflow: ellipsis;
text-transform: none;
white-space: normal;
overflow: hidden;
color: #333;
')}">

                                ${block->with_info1:default(0)}
                                <span style="${args->info1_style:html}">
                                    ${p->c2:sprintf('%s')}
                                </span>
                                ${block->with_info2:default(0)}
                                <span style="${args->info2_style:html}">
                                    ${p->custom_2:sprintf('| %s miles')}
                                </span>

                                <br />
                                ${p->title}
                            </div>

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

                        </div>
                    </a>
                    ${end}
                </td>
            </tr>


            <!-- End of Products -->


            <!-- Start of Footer -->


            <tr>
                <td style="text-align:center">
                    ${block->with_hr:default(0)}
                    <div style="${args->hr_style:html}"></div>
                    ${block->with_link:default(0)}
                    <div>
                        <a href="${args->href:html}" target="${args->target:html:default(_self)}" style="${args->button_text_style:html}">
                            ${args->link_text}
                        </a>
                    </div>
                    ${block->with_text_2:default(0)}
                    <div style="${args->text_2_style:html}">
                        ${args->text_2}
                    </div>
                    ${block->with_text_3:default(1)}
                    <div style="${args->text_3_style:html:default('color: rgb(233, 227, 227);
font-size: 19px;
font-weight: normal;
text-align: left;
background-color: #194679;
padding: 30px;
line-height: 1em;
border-bottom-right-radius: 10px;
border-bottom-left-radius: 10px;
')}">
                        ${args->text_3:default('<p style="margin-bottom: 0px;"><span style="font-size:11px;">This communication has been sent to you from information provided by you and held on our database.</span><br />
<span style="font-size:11px; padding-top: 10px; display: inline-block;">No longer want to receive emails from us, <a href="http://pic.personyze.com/unsubscribe/k=${action_key:html}/u=${id:html}" style="color: #fff;" target="_blank">unsubscribe here or change your preferences</a></span></p>
')}
                    </div>
                    ${block->with_email:default(0)}
                    <a href="mailto:${args->email:html}?subject=${args->subject:html}" style="${args->email_style:html:default('margin-top: 1em;
margin-right: 0;
margin-bottom: 1em;
margin-left: 0;
color: #3B6886;
font-size: 55px;
font-weight: normal;
text-decoration: none;
')}">
                        ${args->email:html}
                    </a>
                </td>
            </tr>

            <!-- End of Footer -->

        </table>
    </div>
</body>

</html>

${menu name='Page', icon='file-o'}
	${menu args->page_width name='Page width', type='css'}
	${menu args->page_style name='Page foreground style', type='css'}
${menu name='Top part', icon='image'}
	${menu block->with_top name='With top part'}
	${menu args->caption name='Caption'}
	${menu args->caption_style name='Caption style', type='css'}
${menu name='Text', icon='bars'}
	${menu args->text_1 name='Text'}
	${menu args->text_1_style name='Text size', type='css'}
${menu name='Products cells', icon='th'}
	${menu args->cells_style name='Style', type='css'}
${menu name='Product image', icon='image'}
	${menu args->cell_style name='Style', type='css'}
	${menu p->image_big_url name='Image', column_tags='image'}
	${menu p->cart_url name='Link target URL', column_tags='url, custom text'}
	${menu args->img_width name='Image width', type='css_length'}
	${menu args->img_height name='Image height', type='css_length', param='with_options=[" auto"]'}
	${menu args->img_style name='Style', type='css'}
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
${menu name='Stock badge', icon='align-justify', description='Set "Low in stock" badge to appear for low stock items.
In addition, you can set the quantity number below it a product is considered to be low in stock.  This requires you to populate "quantity" on your product feed.'}
	${menu block->with_stock_badge name='With stock badge'}
	${menu args->badge_if_less_stock name='Show stock badge if items less than', type='number', param='min=1'}
	${menu args->stock_badge_style name='Badge style', type='css', param='with_responsive=1'}
	${menu args->stock_badge_text_style name='Badge text style', type='css', param='with_responsive=1'}
	${menu args->stock_badge_text name='Text'}
${menu name='Icon or text badge', icon='star', description='Show text taken from catalog field'}
	${menu block->with_db_badge name='With db badge'}
	${menu args->db_badge_style name='Block style', type='css'}
	${menu block->with_db_badge_icon name='With icon'}
	${menu args->db_badge_text_icon name='Icon', type='icon'}
	${menu args->db_badge_text_style name='Icon style', type='css'}
	${menu args->db_badge_text name='Text'}
${menu name='Product name', icon='text-height'}
	${menu p->title name='Product name'}
	${menu args->p_title_style name='Product name style', type='css'}
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
${menu name='Product info near price', icon='info'}
	${menu block->with_info1 name='With Product info 1'}
	${menu p->c2:sprintf('%s') name='Product info 1'}
	${menu args->info1_style name='Product info 1 style', type='css'}
	${menu block->with_info2 name='With Product info 2'}
	${menu p->custom_2:sprintf('| %s miles') name='Product info 2'}
	${menu args->info2_style name='Product info 2 style', type='css'}
${menu name='Separator', icon='minus'}
	${menu block->with_hr name='With separator'}
	${menu args->hr_style name='Separator', type='css'}
${menu name='Button', icon='hand-o-up'}
	${menu block->with_link name='With button'}
	${menu args->link_text name='Button text'}
	${menu args->href name='Link target URL'}
	${menu args->button_text_style name='Button text style', type='css'}
	${menu args->target name='Open link in', type='a_target'}
${menu name='Signature', icon='bars'}
	${menu block->with_text_2 name='With signature'}
	${menu args->text_2 name='Signature'}
	${menu args->text_2_style name='Signature style', type='css'}
${menu name='Footer', icon='bars'}
	${menu block->with_text_3 name='With company name'}
	${menu args->text_3 name='Company name'}
	${menu args->text_3_style name='Company name style', type='css'}
${menu name='Email', icon='envelope'}
	${menu block->with_email name='With email'}
	${menu args->email name='Email address'}
	${menu args->subject name='Default subject'}
	${menu args->email_style name='Company name style', type='css'}
```


