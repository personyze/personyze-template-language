## Picture and text



```
${foreach sum_articles as p where p->for_period='recently' and p->n_favorite>0 order by p->n_favorite desc union sum_articles where p->for_period='recently' order by p->n_viewed desc limit 4}
<table style="background-color:#2e876b; border-collapse:collapse; width:${args->img_width:html:default(272px)}">
	<tr>
		<td style="text-align:center; ${args->td0_style:html:default('padding: 0; background-color: white;')}">
			<style>body {background-color:#2e876b}</style>
			<img src="${p->image_big_url:html}" style="width:auto; height:auto; max-width:${args->img_width:html}">
		</td>
	</tr>
	${block->with_button:default(1)}
	<tr>
		<td style="${args->button_style:html:default('font-family: Arial,Helvetica,sans-serif;
font-size: 16px;
font-weight: 400;
color: rgb(248, 242, 242);
text-align: center;
padding: 1em;
background-color: rgb(36, 24, 19);
')}">
			${args->button_text:default('${p->title}')}
		</td>
	</tr>
</table>
${end}

${menu name='Image', icon='image'}
	${menu p->image_big_url name='Item image', column_tags='image'}
	${menu args->img_width name='Picture Maximum Width', type='css_length'}
	${menu args->td0_style name='Image cell style', type='css'}
${menu name='Button', icon='mouse-pointer'}
	${menu block->with_button name='With Button'}
	${menu args->button_text name='Button Text'}
	${menu args->button_style name='Menu Item Style', type='css'}
```


## Default



```
${foreach articles_interactions as p where p->interaction_status in ('viewed','extra','favorite') and Locate('yes', p->is_in_stock) order by p->interaction_time desc limit 6}<table style="vertical-align:top; border-collapse:collapse; width:${args->img_width:html:default(150px)}">
	<tr>
		<td style="text-align:center; vertical-align:top; padding:0">
			<img src="${p->image_big_url:html}" style="width:auto; height:auto; max-width:${args->img_width:html}">
		</td>
	</tr>
	<tr>
		<td style="${args->p_title_style:html:default('text-align: center;
padding-top: 0.5em;
padding-right: 0em;
padding-bottom: 0.5em;
padding-left: 0em;
')}">
			${p->title:text_before(' - ')}
		</td>
	</tr>
</table>${end}

${menu name='Image', icon='image'}
	${menu p->image_big_url name='Item image', column_tags='image'}
	${menu args->img_width name='Picture Maximum Width', type='css_length'}
${menu name='Second line', icon='bars'}
	${menu p->title:text_before(' - ') name='Article title'}
	${menu args->p_title_style name='Article title style', type='css'}
```


## With badges



```
${foreach recom_articles_filled as p union recom_articles_filled limit 4}<table style="border-collapse:collapse; width:${args->img_width:html:default(192px)}">
    <tr style="height:${args->img_height:html:default(140px)}">
        <td style="text-align:center; padding:0; height: ${args->img_height:html};">
            <div style="height: ${args->img_height:html}; overflow:hidden; position:relative">
                <img src="${p->image_big_url:html}" style="width:auto; height:auto; max-width:${args->img_width:html}; max-height:${args->img_height:html}">

                ${block->with_new_badge:default(1)}
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
color: #333;
font-size: 12px;
font-weight: 400;
margin: 10px;
text-align: center;
line-height: 1.3;
max-height: 5.2em;
overflow: hidden;
min-height: 0;
text-decoration: none;
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
                    ${foreach sum_articles_1day as s where s->internal_id = p->internal_id limit 1}
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
                    ${foreach sum_articles_week as s where s->internal_id = p->internal_id limit 1}
                        ${if s->n_viewed >= args->hide_no_view_week:html:default(20)}
                            ${if s->n_goal >= args->hide_no_goal_week:html:default(1)}
                                ${args->n_viewed_week:default('<span style="font-size:14px;">This article has been popular in the last week!</span>&nbsp;&nbsp;<span style="color:#d61e26;"><strong>${s->n_viewed*1}&nbsp;views</strong></span>')}
                            ${end}
                        ${end}
                    ${end}
                </div>
            </div>
        </td>
    </tr>
    ${block->with_button:default(1)}
    <tr>
        <td style="text-align:center; padding:0">
            <a href="${args->button_href:html:default('${p->content_url}')}?utm_source=smartweb&utm_medium=email&utm_campaign=aanbevelingen" target="_blank" style="display:inline-block; ${args->button_style:html:default('border-color: rgba(214, 30, 30, 0);
border-radius: 1.42857rem;
color: #fff;
font-weight: 700;
height: auto;
margin: 0;
padding-top: 0.85714rem;
padding-right: 1.71429rem;
padding-bottom: 0.85714rem;
padding-left: 1.71429rem;
min-width: 4.71429rem;
text-transform: uppercase;
background-color: rgba(214, 30, 30, 0.94);
text-decoration: none;
font-size: 10px;
')}">
                ${args->button_text:default('More ❯')}
            </a>
        </td>
    </tr>
</table>
${end}

${menu name='Image', icon='image'}
	${menu p->image_big_url name='Item image', column_tags='image'}
	${menu args->img_width name='Picture Maximum Width', type='css_length'}
	${menu args->img_height name='Picture Maximum Height', type='css_length'}
${menu name='New badge', icon='align-justify', description='Set "New" badge to appear for items debut recently.
You may choose a time frame for an item to be considered new. * For new accounts/articles feed, all articles are new until the day setting condition has been met.'}
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
${menu name='Icon or text badge', icon='star', description='Show text taken from catalog field'}
	${menu block->with_db_badge name='With db badge'}
	${menu args->db_badge_style name='Block style', type='css'}
	${menu block->with_db_badge_icon name='With icon'}
	${menu args->db_badge_text_icon name='Icon', type='icon'}
	${menu args->db_badge_text_style name='Icon style', type='css'}
	${menu args->db_badge_text name='Text'}
${menu name='First line', icon='bars'}
	${menu block->with_title name='With article title'}
	${menu args->p_title name='Article title'}
	${menu args->p_title_style name='Article title style', type='css'}
	${menu args->title_max_lines name='Title no. of lines', type='number', param='min=1'}
	${menu block->with_info1 name='With custom column 1'}
	${menu args->info1_style name='Custom column 1 style', type='css'}
	${menu p->c2:sprintf('%s') name=''}
	${menu block->with_info2 name='With custom column 2'}
	${menu args->info2_style name='Custom column 1 style', type='css'}
	${menu p->custom_2:sprintf('| %s') name=''}
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
	${menu args->button_href name='Button Link URL'}
	${menu args->button_style name='Menu Item Style', type='css'}
```


