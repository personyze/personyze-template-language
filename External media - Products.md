## Horizontal display



```
${foreach products as p order by p->time_created desc limit 3}
<div>
	<div class="paddingboth">
		<table class="resize" style="width: 680px;" border="0" cellspacing="0" cellpadding="0" align="center">
			<tbody>
				<tr>
					<td height="195">
						<table class="resize heightchange" style="height: 195px; width: 260px;" border="0"
							cellspacing="0" cellpadding="0" align="left">
							<tbody>
								<tr>
									<td align="left" valign="top"><a style="text-decoration: none;"
											href="${p->cart_url:html}"
											target="_blank" rel="noopener"><img class="resize"
												src="${p->image_big_url:html}"
												width="260" /></a></td>
								</tr>
							</tbody>
						</table>
						<!-- [if !mso]><!-->
						<div class="mobilecontent" style="display: none; max-height: 0px; overflow: hidden;">
							<table class="resize" border="0" cellspacing="0" cellpadding="0" align="left">
								<tbody>
									<tr>
										<td style="font-size: 0px; line-height: 20px;" align="left" height="20">&nbsp;
										</td>
									</tr>
								</tbody>
							</table>
						</div>
						<!--<![endif]-->
						<table class="resize heightchange" style="height: 195px; width: 400px;" border="0"
							cellspacing="0" cellpadding="0" align="right">
							<tbody>
								<tr>
									<td style="line-height: 23px;" align="left" valign="top"><span
											style="font-family: 'Open Sans', sans-serif; font-size: 17px; line-height: 23px; color: #333333; font-weight: 600;"><a
												style="text-decoration: none; color: #333333;"
												href="${p->cart_url:html}" target="_blank"
												rel="noopener">${args->p_title:default('${p->title}&nbsp;')}</a></span></td>
								</tr>
								<tr>
									<td style="font-size: 0px; line-height: 10px;" align="left" valign="top"
										height="10">&nbsp;</td>
								</tr>
								${if p->custom_1 != ''}
								<tr>
									<td style="padding: 4px 0px;" align="left" valign="top"><img
											style="display: inline-block;"
											src="https://oad.effectiveprofiles.com/admin/addons/feedtonewsletter/htmltemplates/3/icon_check_yellow.png"
											width="11" /><span
											style="font-family: 'Open Sans', sans-serif; font-size: 15px; line-height: 17px; color: #333333; font-weight: 300;">
											${p->cart_url}
										</span></td>
								</tr>
								${end}
								${if p->custom_2 != ''}
								<tr>
									<td style="padding: 4px 0px;" align="left" valign="top"><img
											style="display: inline-block;"
											src="https://oad.effectiveprofiles.com/admin/addons/feedtonewsletter/htmltemplates/3/icon_check_yellow.png"
											width="11" /><span
											style="font-family: 'Open Sans', sans-serif; font-size: 15px; line-height: 17px; color: #333333; font-weight: 300;">
											${p->guide_url}
										</span></td>
								</tr>
								${end}
								${if p->custom_3 != ''}
								<tr>
									<td style="padding: 4px 0px;" align="left" valign="top"><img
											style="display: inline-block;"
											src="https://oad.effectiveprofiles.com/admin/addons/feedtonewsletter/htmltemplates/3/icon_check_yellow.png"
											width="11" /><span
											style="font-family: 'Open Sans', sans-serif; font-size: 15px; line-height: 17px; color: #333333; font-weight: 300;">
											${args->p_custom_6}
										</span></td>
								</tr>
								${end}
								<tr>
									<td style="font-size: 0px; line-height: 10px;" align="left" valign="top"
										height="10">&nbsp; </td>
								</tr>
								<tr>
									<td style="font-size: 0px; line-height: 21px;" valign="middle" height="21"><a
											style="text-decoration: none;" href="${p->cart_url:html}" target="_blank"
											rel="noopener"><img class="" style="display: inline-block;"
												src="https://oad.effectiveprofiles.com/admin/addons/feedtonewsletter/htmltemplates/3/_1.png" /></a>
									</td>
								</tr>
								<tr>
									<td style="font-size: 0px; line-height: 15px;" align="left" valign="top"
										height="15">&nbsp;</td>
								</tr>
								<tr>
									<td align="left" valign="bottom" height="35">
										<table style="width: 100%;" border="0" cellspacing="0" cellpadding="0"
											align="left">
											<tbody>
												<tr>
													<td style="padding-left: 10px;" align="left" valign="middle"
														bgcolor="#E7E6E6" height="35"><span
															style="font-family: 'Open Sans', sans-serif; font-size: 15px; line-height: 17px; color: #333333; font-weight: 300;">${p->brand} Price <span
																style="font-size: 25px; font-weight: 600;">${p->price},-</span></span></td>
													<td class="width_auto" style="width: 165px;" align="left">
														<table
															style="line-height: 0px; border-collapse: collapse; width: 100%;"
															border="0" cellspacing="0" cellpadding="0" align="left">
															<tbody>
																<tr>
																	<td style="line-height: 0px;" align="center"
																		bgcolor="#FFEE3F"><span
																			style="font-size: 14px; font-family: 'Open Sans', sans-serif; font-weight: 600; color: #000000; text-decoration: none; line-height: 30px;"><a
																				style="color: #000000; display: block; text-decoration: none; line-height: 30px;"
																				href="${p->cart_url:html}"
																				target="_blank" rel="noopener">${args->text_5:default(Buy Now)}</a></span></td>
																	<td style="font-size: 0px; line-height: 0px; width: 23px;"
																		align="left"><a href="${p->cart_url:html}"
																			target="_blank" rel="noopener"><img
																				style="display: block; float: left; max-height: 35px;"
																				src="https://oad.effectiveprofiles.com/admin/addons/feedtonewsletter/htmltemplates/3/_2.png"
																				height="35" border="0" /></a></td>
																</tr>
															</tbody>
														</table>
													</td>
												</tr>
											</tbody>
										</table>
									</td>
								</tr>
							</tbody>
						</table>
					</td>
				</tr>
			</tbody>
		</table>
	</div>
	</div>
${end}

${menu name='Cell', icon='font'}
	${menu p->cart_url name='Link URL'}
	${menu args->text_5 name='Button', description='Button text'}
	${menu p->image_big_url name='Image'}
	${menu args->p_title name='Title'}
	${menu p->guide_url name='Check Line 2'}
	${menu args->p_custom_6 name='Check Line 3'}
	${menu p->brand name='brand'}
	${menu p->price name='Price'}
```


## Round look



```
${foreach products as p order by p->time_created desc limit 4}<table style="border-collapse:collapse; margin:15px; width:${args->img_width:html:default(225px)}">
    <tr style="height:${args->img_height:html:default(250px)}">
        <td style="text-align:center; padding:0; height: ${args->img_height:html};">
            <div style="height: ${args->img_height:html}; overflow:hidden; position:relative">
                <img src="${p->image_big_url:html}" style="width:auto; height:auto; max-width:${args->img_width:html}; max-height:${args->img_height:html}">

                ${block->with_discount_badge:default(1)}
                <span>
                    ${if p->discount_percent >= args->min_discount_percent:default(1)}
                        <div style="position: absolute; ${args->discount_badge_style:html:default('top: 0;
right: 0px;
width: 6em;
height: 6em;
font-size: 8px;
background-color: #ff4142;
color: rgb(252, 249, 249);
border-radius: 100%;
display: flex;
justify-content: center;
align-items: center;
padding: 1px;
')}">
                            <span style="${args->discount_badge_text_style:html:default('line-height: 1.20;
font-size: 8px;
font-weight: 600;
')}">${args->discount_badge_text:default('<div style="font-size:14px">${p->discount_percent:floor}%</div>
Discount')}</span>
                        </div>
                    ${end}
                </span>

                ${block->with_new_badge:default(1)}
                <span>
                    ${if unix_timestamp() - p->time_created <= args->badge_if_newer:default(34473600)}
                        <div style="position: absolute; ${args->new_badge_style:html:default('top: 0;
left: 0;
font-size: 10px;
background-color: rgb(82, 2, 105);
color: rgb(250, 246, 246);
display: flex;
justify-content: center;
align-items: center;
padding: 0.5em;
font-weight: 300;
')}">
                            <span style="${args->new_badge_text_style:html:default('font-size: 13px;
font-weight: 500;
padding: 5px;
')}">${args->new_badge_text:default(NEW)}</span>
                        </div>
                    ${end}
                </span>

                ${block->with_time_badge:default(0)}
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
                    ${if p->inventory between 1 and args->badge_if_less_stock:default(300000)}
                        <div style="position: absolute; ${args->stock_badge_style:html:default('bottom: 20px;
left: 0px;
font-size: 14px;
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

                <div style="box-sizing:border-box; max-width:${args->img_width:html}; ${args->p_title_style:html:default('padding: 1px;
text-transform: none;
color: black;
font-size: 15px;
font-weight: 100;
margin-top: 0px;
margin-right: 10px;
margin-bottom: 0px;
margin-left: 10px;
text-align: center;
line-height: 1.3;
transition: color .15s ease;
')}">
                    ${block->with_title:default(1)}
                    <div style="overflow:hidden; text-overflow:ellipsis; display:-webkit-box; -webkit-box-orient:vertical; -webkit-line-clamp:${args->title_max_lines:html:default(3)}; line-clamp:${args->title_max_lines:html}; line-height:1.3; height:calc(${args->title_max_lines:html}em * 1.3)">
                        ${args->p_title:default('${p->title}')}
                    </div>

                    ${block->with_info1:default(0)}
                    <span style="${args->info1_style:html}">
                        ${p->c2:sprintf('%s')}
                    </span>
                    ${block->with_info2:default(0)}
                    <span style="${args->info2_style:html}">
                        ${p->custom_2:sprintf('| %s')}
                    </span>
                </div>

                ${block->stats_1day:default(0)}
                <div style="${args->text_style_1day:html:default('padding-top: 1em;
padding-right: 0;
padding-bottom: 1em;
padding-left: 0;
font-weight: 600;
height: 4em;
')}">
                    ${foreach sum_products_1day as s where s->internal_id = p->internal_id limit 1}
                        ${if s->n_viewed >= args->hide_no_view_1day:html:default(3)}
                            ${if s->n_goal >= args->hide_no_goal_1day:html:default(1)}
                                ${args->n_viewed_1day:default('${s->n_viewed*1} viewed today ${if s-&gt;n_goal &gt; 0}
<div>${s->n_goal*1}&nbsp; purchased today</div>
${end}')}
                            ${end}
                        ${end}
                    ${end}
                </div>

                ${block->stats_week:default(0)}
                <div style="${args->text_style_week:html:default('padding-top: 1em;
padding-right: 0;
padding-bottom: 1em;
padding-left: 0;
font-weight: 600;
height: 4em;
')}">
                    ${foreach sum_products_week as s where s->internal_id = p->internal_id limit 1}
                        ${if s->n_viewed >= args->hide_no_view_week:html:default(20)}
                            ${if s->n_goal >= args->hide_no_goal_week:html:default(1)}
                                ${args->n_viewed_week:default('<span style="font-size:14px;">This product has been popular in the last week!</span>&nbsp;&nbsp;<span style="color:#d61e26;"><strong>${s->n_viewed*1}&nbsp;views</strong></span>')}
                            ${end}
                        ${end}
                    ${end}
                </div>

                ${block->price:default(1)}
                <div style="box-sizing:border-box; max-width:${args->img_width:html}; ${args->price_style:html:default('font-size: 17px;
font-weight: 500;
color: black;
margin-top: 0px;
margin-right: 0px;
margin-bottom: 20px;
margin-left: 0px;
')}">
                    ${if p->price_after_discount}
                        ${if p->price_after_discount < p->price_before_discount}
                            <span style="white-space:nowrap">
                                <span style="${args->old_price_style:html:default('margin-top: auto;
margin-right: auto;
margin-bottom: 0.4em;
margin-left: 10px;
text-decoration: line-through;
font-size: 14px;
color: #333333;
font-weight: 400;
')}">
                                    ${args->old_price_before}${args->p_price_before_discount:default('$${p->price_before_discount:sprintf(''%[#,###.##]f'')}')}${args->old_price_after}
                                </span>
                            </span>
                            <span style="white-space:nowrap">
                                <span style="${args->new_price_style:html:default('margin-top: auto;
margin-right: auto;
margin-bottom: auto;
margin-left: 10px;
display: inline-block;
border-radius: 4px;
padding-top: 3px;
padding-right: 7px;
padding-bottom: 3px;
padding-left: 7px;
background-color: red;
color: white;
font-size: 24px;
font-family: ''Roboto Slab'', ''Roboto'',Gotham, ''Helvetica Neue'', Helvetica, Arial, sans-serif;
')}">
                                    ${args->old_price_before)}${args->p_price_after_discount:default('$${p->price_after_discount:sprintf(''%[#,###.##]f'')}')}${args->old_price_after}
                                </span>
                            </span>
                            <div style="${args->sale_text_style:html:default('display: inline-block;
font-size: 50%;
line-height: 1;
')}">
                                ${args->sale_text}
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
        </td>
    </tr>
    ${block->with_button:default(1)}
    <tr>
        <td style="text-align:center; padding:0">
            <a href="javascript:" style="display:inline-block; ${args->button_style:html:default('background-color: #005091;
padding-top: 10px;
padding-right: 18px;
padding-bottom: 10px;
padding-left: 18px;
display: inline-block;
font-family: ''Roboto'',Gotham, ''Helvetica Neue'', Helvetica, Arial, sans-serif;
font-size: 16px;
color: #ffffff;
font-weight: 400;
text-decoration: none;
text-align: center;
border-radius: 4px;
border: 2px #005091 solid;
margin-top: 0;
margin-right: auto;
margin-bottom: 10px;
margin-left: auto;
')}">
                ${args->button_text:default(Shop Now)}
            </a>
        </td>
    </tr>
</table>
${end}

${menu name='Image', icon='image'}
	${menu p->image_big_url name='Item image', column_tags='image'}
	${menu args->img_width name='Picture Maximum Width', type='css_length'}
	${menu args->img_height name='Picture Maximum Height', type='css_length'}
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
${menu name='First line', icon='bars'}
	${menu block->with_title name='With product title'}
	${menu args->p_title name='Product title'}
	${menu args->p_title_style name='Product title style', type='css'}
	${menu args->title_max_lines name='Title no. of lines', type='number', param='min=1'}
	${menu block->with_info1 name='With custom column 1'}
	${menu args->info1_style name='Custom column 1 style', type='css'}
	${menu p->c2:sprintf('%s') name=''}
	${menu block->with_info2 name='With custom column 2'}
	${menu args->info2_style name='Custom column 1 style', type='css'}
	${menu p->custom_2:sprintf('| %s') name=''}
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
${menu name='Site statistics: 1-day', icon='bar-chart', description='Show number of viewed or purchases in the last 24 hours for a given item as tracked by Personyze. You can set a condition not to show if the number of views/purchases is below X number.'}
	${menu block->stats_1day name='Site statistics: 1day'}
	${menu args->text_style_1day name='Style', type='css'}
	${menu args->n_viewed_1day name='Text'}
	${menu args->hide_no_view_1day name='Hide statistics if less views than', type='number', param='min=0'}
	${menu args->hide_no_goal_1day name='Hide statistics if less purchases than', type='number', param='min=0'}
${menu name='Site statistics: week', icon='bar-chart', description='Show number of viewed or purchases in the last week for a given item as tracked by Personyze. You can set a condition not to show if the number of views/purchases is below X number.'}
	${menu block->stats_week name='Site statistics: week'}
	${menu args->text_style_week name='Style', type='css'}
	${menu args->n_viewed_week name='Text'}
	${menu args->hide_no_view_week name='Hide statistics if less views than', type='number', param='min=0'}
	${menu args->hide_no_goal_week name='Hide statistics if less purchases than', type='number', param='min=0'}
${menu name='Button', icon='mouse-pointer'}
	${menu block->with_button name='With button'}
	${menu args->button_text name='Button Text'}
	${menu args->button_style name='Menu Item Style', type='css'}
```


## Squre look



```
${foreach products as p order by p->time_created desc limit 4}<table style="border-collapse:collapse; margin:15px; width:${args->img_width:html:default(225px)}">
    <tr style="height:${args->img_height:html:default(250px)}">
        <td style="text-align:center; padding:0; height: ${args->img_height:html};">
            <div style="height: ${args->img_height:html}; overflow:hidden; position:relative">
                <img src="${p->image_big_url:html}" style="width:auto; height:auto; max-width:${args->img_width:html}; max-height:${args->img_height:html}">

                ${block->with_discount_badge:default(1)}
                <span>
                    ${if p->discount_percent >= args->min_discount_percent:default(1)}
                        <div style="position: absolute; ${args->discount_badge_style:html:default('top: 0;
right: 0px;
width: 8em;
height: nullem;
font-size: 8px;
background-color: #ff4142;
color: rgb(252, 249, 249);
border-radius: 0%;
display: flex;
justify-content: center;
align-items: center;
padding: 3px;
')}">
                            <span style="${args->discount_badge_text_style:html:default('line-height: 1.20;
font-size: 8px;
font-weight: 600;
')}">${args->discount_badge_text:default('<div style="font-size:14px">${p->discount_percent:floor}%</div>
Discount')}</span>
                        </div>
                    ${end}
                </span>

                ${block->with_new_badge:default(1)}
                <span>
                    ${if unix_timestamp() - p->time_created <= args->badge_if_newer:default(34473600)}
                        <div style="position: absolute; ${args->new_badge_style:html:default('top: 0;
left: 0;
font-size: 10px;
background-color: rgb(82, 2, 105);
color: rgb(250, 246, 246);
display: flex;
justify-content: center;
align-items: center;
padding: 0.5em;
font-weight: 300;
')}">
                            <span style="${args->new_badge_text_style:html:default('font-size: 13px;
font-weight: 500;
padding: 5px;
')}">${args->new_badge_text:default(NEW)}</span>
                        </div>
                    ${end}
                </span>

                ${block->with_time_badge:default(0)}
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
                    ${if p->inventory between 1 and args->badge_if_less_stock:default(300000)}
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

                <div style="box-sizing:border-box; max-width:${args->img_width:html}; ${args->p_title_style:html:default('padding: 1px;
text-transform: none;
color: black;
font-size: 15px;
font-weight: 100;
margin-top: 0px;
margin-right: 10px;
margin-bottom: 0px;
margin-left: 10px;
text-align: center;
line-height: 1.3;
transition: color .15s ease;
')}">
                    ${block->with_title:default(1)}
                    <div style="overflow:hidden; text-overflow:ellipsis; display:-webkit-box; -webkit-box-orient:vertical; -webkit-line-clamp:${args->title_max_lines:html:default(3)}; line-clamp:${args->title_max_lines:html}; line-height:1.3; height:calc(${args->title_max_lines:html}em * 1.3)">
                        ${args->p_title:default('${p->title}')}
                    </div>

                    ${block->with_info1:default(0)}
                    <span style="${args->info1_style:html}">
                        ${p->c2:sprintf('%s')}
                    </span>
                    ${block->with_info2:default(0)}
                    <span style="${args->info2_style:html}">
                        ${p->custom_2:sprintf('| %s')}
                    </span>
                </div>

                ${block->stats_1day:default(0)}
                <div style="${args->text_style_1day:html:default('padding-top: 1em;
padding-right: 0;
padding-bottom: 1em;
padding-left: 0;
font-weight: 600;
height: 4em;
')}">
                    ${foreach sum_products_1day as s where s->internal_id = p->internal_id limit 1}
                        ${if s->n_viewed >= args->hide_no_view_1day:html:default(3)}
                            ${if s->n_goal >= args->hide_no_goal_1day:html:default(1)}
                                ${args->n_viewed_1day:default('${s->n_viewed*1} viewed today ${if s-&gt;n_goal &gt; 0}
<div>${s->n_goal*1}&nbsp; purchased today</div>
${end}')}
                            ${end}
                        ${end}
                    ${end}
                </div>

                ${block->stats_week:default(0)}
                <div style="${args->text_style_week:html:default('padding-top: 1em;
padding-right: 0;
padding-bottom: 1em;
padding-left: 0;
font-weight: 600;
height: 4em;
')}">
                    ${foreach sum_products_week as s where s->internal_id = p->internal_id limit 1}
                        ${if s->n_viewed >= args->hide_no_view_week:html:default(20)}
                            ${if s->n_goal >= args->hide_no_goal_week:html:default(1)}
                                ${args->n_viewed_week:default('<span style="font-size:14px;">This product has been popular in the last week!</span>&nbsp;&nbsp;<span style="color:#d61e26;"><strong>${s->n_viewed*1}&nbsp;views</strong></span>')}
                            ${end}
                        ${end}
                    ${end}
                </div>

                ${block->price:default(1)}
                <div style="box-sizing:border-box; max-width:${args->img_width:html}; ${args->price_style:html:default('font-size: 17px;
font-weight: 500;
color: black;
margin-top: 0px;
margin-right: 0px;
margin-bottom: 20px;
margin-left: 0px;
')}">
                    ${if p->price_after_discount}
                        ${if p->price_after_discount < p->price_before_discount}
                            <span style="white-space:nowrap">
                                <span style="${args->old_price_style:html:default('font-size: 17px;
font-weight: 500;
text-decoration: line-through;
')}">
                                    ${args->old_price_before}${args->p_price_before_discount:default('$${p->price_before_discount:sprintf(''%[#,###.##]f'')}')}${args->old_price_after}
                                </span>
                            </span>
                            <span style="white-space:nowrap">
                                <span style="${args->new_price_style:html:default('font-size: 17px;
font-weight: 500;
color: red;
')}">
                                    ${args->old_price_before)}${args->p_price_after_discount:default('$${p->price_after_discount:sprintf(''%[#,###.##]f'')}')}${args->old_price_after}
                                </span>
                            </span>
                            <div style="${args->sale_text_style:html:default('display: inline-block;
font-size: 50%;
line-height: 1;
')}">
                                ${args->sale_text}
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
        </td>
    </tr>
    ${block->with_button:default(1)}
    <tr>
        <td style="text-align:center; padding:0">
            <a href="javascript:" style="display:inline-block; ${args->button_style:html:default('color: #fff;
border-radius: 0rem;
order-style: solid;
border-width: 1px;
cursor: pointer;
font-family: Arimo, Arial;
font-weight: 300;
margin: 0;
padding-top: 0.85714rem;
padding-right: 1.71429rem;
padding-bottom: 0.85714rem;
padding-left: 1.71429rem;
min-width: 10.71429rem;
text-transform: uppercase;
text-decoration: none;
background-color: #631d85;
')}">
                ${args->button_text:default(Shop Now)}
            </a>
        </td>
    </tr>
</table>
${end}

${menu name='Image', icon='image'}
	${menu p->image_big_url name='Item image', column_tags='image'}
	${menu args->img_width name='Picture Maximum Width', type='css_length'}
	${menu args->img_height name='Picture Maximum Height', type='css_length'}
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
${menu name='First line', icon='bars'}
	${menu block->with_title name='With product title'}
	${menu args->p_title name='Product title'}
	${menu args->p_title_style name='Product title style', type='css'}
	${menu args->title_max_lines name='Title no. of lines', type='number', param='min=1'}
	${menu block->with_info1 name='With custom column 1'}
	${menu args->info1_style name='Custom column 1 style', type='css'}
	${menu p->c2:sprintf('%s') name=''}
	${menu block->with_info2 name='With custom column 2'}
	${menu args->info2_style name='Custom column 1 style', type='css'}
	${menu p->custom_2:sprintf('| %s') name=''}
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
${menu name='Site statistics: 1-day', icon='bar-chart', description='Show number of viewed or purchases in the last 24 hours for a given item as tracked by Personyze. You can set a condition not to show if the number of views/purchases is below X number.'}
	${menu block->stats_1day name='Site statistics: 1day'}
	${menu args->text_style_1day name='Style', type='css'}
	${menu args->n_viewed_1day name='Text'}
	${menu args->hide_no_view_1day name='Hide statistics if less views than', type='number', param='min=0'}
	${menu args->hide_no_goal_1day name='Hide statistics if less purchases than', type='number', param='min=0'}
${menu name='Site statistics: week', icon='bar-chart', description='Show number of viewed or purchases in the last week for a given item as tracked by Personyze. You can set a condition not to show if the number of views/purchases is below X number.'}
	${menu block->stats_week name='Site statistics: week'}
	${menu args->text_style_week name='Style', type='css'}
	${menu args->n_viewed_week name='Text'}
	${menu args->hide_no_view_week name='Hide statistics if less views than', type='number', param='min=0'}
	${menu args->hide_no_goal_week name='Hide statistics if less purchases than', type='number', param='min=0'}
${menu name='Button', icon='mouse-pointer'}
	${menu block->with_button name='With button'}
	${menu args->button_text name='Button Text'}
	${menu args->button_style name='Menu Item Style', type='css'}
```


## With social proof / scarcity



```
${foreach recom_products_filled as p union sum_products where p->for_period='recently' order by p->n_viewed desc limit 6}<table style="border-collapse:collapse; width:${args->img_width:html:default(300px)}">
    <tr style="height:${args->img_height:html:default(270px)}">
        <td style="text-align:center; padding:0; height: ${args->img_height:html};">
            <div style="height: ${args->img_height:html}; overflow:hidden; position:relative">
                <img src="${p->image_big_url:html}" style="width:auto; height:auto; max-width:${args->img_width:html}; max-height:${args->img_height:html}">

                ${block->with_discount_badge:default(1)}
                <span>
                    ${if p->discount_percent >= args->min_discount_percent:default(1)}
                        <div style="position: absolute; ${args->discount_badge_style:html:default('top: 0;
right: 30px;
width: 5em;
height: 5em;
font-size: 7px;
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

                ${block->with_new_badge:default(0)}
                <span>
                    ${if unix_timestamp() - p->time_created <= args->badge_if_newer:default(2851200)}
                        <div style="position: absolute; ${args->new_badge_style:html:default('top: 0;
left: 48px;
font-size: 14px;
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

                ${block->with_time_badge:default(0)}
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
                    ${if p->inventory between 1 and args->badge_if_less_stock:default(10)}
                        <div style="position: absolute; ${args->stock_badge_style:html:default('padding-top: 8px;
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
width: 215px;
margin-top: -33px;
margin-right: 22px;
margin-bottom: 20px;
margin-left: 21px;
font-size: 12px;
position: absolute;
top: 260px;
text-transform: lowercase;
')}">
                            <span style="${args->stock_badge_text_style:html:default('font-size: 12px;
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
background-color: rgb(255, 255, 255);
color: rgb(250, 246, 246);
display: flex;
justify-content: center;
align-items: center;
padding: 0.3em;
background-image: url(''https://cdn.personyze.com/upload/6330/a385cde820b25335.png'');
')}">
                        ${block->with_db_badge_icon}
                        <hr class="$icon ${args->db_badge_text_icon:html:default(new)}">
                        <span style="${args->db_badge_text_style:html:default('font-size: 16px;
font-weight: 600;
')}">${args->db_badge_text:default('${p->custom_2}')}</span>
                    </div>
                </span>
            </div>

            <div class="prod-content-wrapper">

                <div style="box-sizing:border-box; max-width:${args->img_width:html}; ${args->p_title_style:html:default('padding: 1px;
text-transform: uppercase;
color: #434343;
font-weight: 500;
margin-top: 0px;
margin-right: 20px;
margin-bottom: 10px;
margin-left: 20px;
text-align: center;
line-height: 1.3;
max-height: none;
overflow: hidden;
min-height: 0;
text-decoration: none;
max-width: none;
font-size: 1rem;
font-family: Avenir;
')}">
${block->stats_1day:default(0)}
                <div>
                    ${foreach sum_products_1day as s where s->internal_id = p->internal_id limit 1}
                        ${if s->n_viewed >= args->hide_no_view_1day:html:default(3)}
                            ${if s->n_goal >= args->hide_no_goal_1day:html:default(1)}
                                <div style="${args->text_style_1day:html:default('padding-top: 1em;
padding-right: 0;
padding-bottom: 1em;
padding-left: 0;
font-weight: 600;
')}">
                                    ${args->n_viewed_1day:default('${s->n_viewed*1} viewed today ${if s-&gt;n_goal &gt; 0}
<div>${s->n_goal*1}&nbsp; purchased today</div>
${end}')}
                                </div>
                            ${end}
                        ${end}
                    ${end}
                </div>

                ${block->stats_week:default(1)}
                <div>
                    ${foreach sum_products_week as s where s->internal_id = p->internal_id limit 1}
                        ${if s->n_viewed >= args->hide_no_view_week:html:default(20)}
                            ${if s->n_goal >= args->hide_no_goal_week:html:default(3)}
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
width: 215px;
margin-top: -33px;
margin-right: 22px;
margin-bottom: 20px;
margin-left: 0px;
font-size: 12px;
position: absolute;
top: 260px;
text-transform: lowercase;
')}">
                                    <img src="${args->n_viewed_week_icon:html:default('https://cdn.personyze.com/upload/6330/ae4189d997db10ab.png')}" style="width:auto; height:auto; ${args->n_viewed_week_icon_style:html:default('max-width: 1.3em;
max-height: 1.3em;
background-color: rgb(0, 0, 0);
')}">
                                    ${args->n_viewed_week:default('${s->n_viewed*1}&nbsp;viewed this recently!')}
                                </div>


                            ${end}
                        ${end}
                    ${end}
                </div>

                ${block->with_title:default(1)}
                <div style="overflow:hidden; text-overflow:ellipsis; display:-webkit-box; -webkit-box-orient:vertical; -webkit-line-clamp:${args->title_max_lines:html:default(2)}; line-clamp:${args->title_max_lines:html}">

                    <div>
                        ${args->p_title:default('${p->title}')}
                    </div>

                    ${block->with_info1:default(0)}
                    <span style="${args->info1_style:html}">
                        ${args->p_c2}
                    </span>
                    ${block->with_info2:default(0)}
                    <span style="${args->info2_style:html}">
                        ${p->custom_2:sprintf('| %s')}
                    </span>
                </div>

                ${block->price:default(1)}
                <div style="box-sizing:border-box; max-width:${args->img_width:html}; ${args->price_style:html:default('color: #585858;
font-size: 1.2rem;
font-weight: 400;
text-transform: none;
margin-top: 15px;
margin-right: 0px;
margin-bottom: 0px;
margin-left: 0px;
')}">
                    ${if p->price_after_discount}
                        ${if p->price_after_discount < p->price_before_discount}
                            <span style="white-space:nowrap">
                                <span style="${args->old_price_style:html:default('font-size: 13px;
font-weight: 400;
text-decoration: line-through;
')}">
                                    ${args->old_price_before}${args->p_price_before_discount:default('$${p->price_before_discount:sprintf(''%[#,###.##]f'')}')}${args->old_price_after}
                                </span>
                            </span>
                            <span style="white-space:nowrap">
                                <span style="${args->new_price_style:html:default('font-size: 15px;
font-weight: 400;
color: #434343;
')}">
                                    ${args->old_price_before)}${args->p_price_after_discount:default('&nbsp; $${p->price_after_discount:sprintf(''%[#,###.##]f'')}&nbsp;<span style="color:#e74c3c;">-</span><span style="color:#c0392b;">${sprintf(round((p->price_before_discount - p->price_after_discount) / p->price_before_discount * 100), ''%s%%'')}</span>')}${args->old_price_after}
                                </span>
                            </span>
                            <div style="${args->sale_text_style:html:default('display: inline-block;
font-size: 50%;
line-height: 1;
')}">
                                ${args->sale_text}
                            </div>
                        ${else}
                            <span style="white-space:nowrap; ${args->nosale_price_style:html:default('font-size: 15px;
font-weight: 700;
')}">
                                ${args->old_price_before}${args->p_price_before_discount}${args->old_price_after}
                            </span>
                        ${end}
                    ${end}

                </div>
            </div>
        </td>
    </tr>
    ${block->with_button:default(0)}
    <tr>
        <td style="text-align:center; padding:0">
            <a href="javascript:" style="display:inline-block; ${args->button_style:html:default('color: rgb(253, 252, 252);
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
')}">
                ${args->button_text:default(See more)}
            </a>
        </td>
    </tr>
</table>
${end}

${menu name='Image', icon='image'}
	${menu p->image_big_url name='Item image', column_tags='image'}
	${menu args->img_width name='Picture Maximum Width', type='css_length'}
	${menu args->img_height name='Picture Maximum Height', type='css_length'}
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
${menu name='First line', icon='bars'}
	${menu args->p_title name='Title'}
	${menu block->with_title name='With product title'}
	${menu args->title_max_lines name='Title max lines', type='number', param='min=1'}
	${menu args->p_title_style name='Product title style', type='css'}
	${menu block->with_info1 name='With custom column 1'}
	${menu args->info1_style name='Custom column 1 style', type='css'}
	${menu args->p_c2 name=''}
	${menu block->with_info2 name='With custom column 2'}
	${menu args->info2_style name='Custom column 1 style', type='css'}
	${menu p->custom_2:sprintf('| %s') name=''}
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
${menu name='Site statistics: 1-day', icon='bar-chart', description='Show number of viewed or purchases in the last 24 hours for a given item as tracked by Personyze. You can set a condition not to show if the number of views/purchases is below X number.'}
	${menu block->stats_1day name='Site statistics: 1day'}
	${menu args->text_style_1day name='Style', type='css'}
	${menu args->n_viewed_1day name='Text'}
	${menu args->hide_no_view_1day name='Hide statistics if less views than', type='number', param='min=0'}
	${menu args->hide_no_goal_1day name='Hide statistics if less purchases than', type='number', param='min=0'}
${menu name='Site statistics: week', icon='bar-chart', description='Show number of viewed or purchases in the last week for a given item as tracked by Personyze. You can set a condition not to show if the number of views/purchases is below X number.'}
	${menu block->stats_week name='Site statistics: week'}
	${menu args->text_style_week name='Style', type='css'}
	${menu args->n_viewed_week_icon name='Icon', type='media_url'}
	${menu args->n_viewed_week_icon_style name='Icon style', type='css'}
	${menu args->n_viewed_week name='Text'}
	${menu args->hide_no_view_week name='Hide statistics if less views than', type='number', param='min=0'}
	${menu args->hide_no_goal_week name='Hide statistics if less purchases than', type='number', param='min=0'}
${menu name='Button', icon='mouse-pointer'}
	${menu block->with_button name='With button'}
	${menu args->button_text name='Button Text'}
	${menu args->button_style name='Menu Item Style', type='css'}
```


