## Email event invitation



```
<div class="$responsive" data-style="${args->style:html:default('margin:0 auto; width:640px; font-family:''Helvetica Neue'',Helvetica,Arial,sans-serif; font-size:13px; background-color:#F5F8F7'):input_type(css):arg_name(Style):arg_section(0, 0, 'Box', 'th-large')}">
    <style>table th, table td { border:0 }</style>
    <div style="position:relative; padding:40px 40px 0 40px">
        <div style="padding:5px 29px; background-color:#F7F7F7; color:#404040; border:1px solid #DEDEDE; border-radius:5px">
            <div style="text-align:center; margin-top:30px; margin-bottom:0px;">
                <p style="font-size:17px; line-height:21px;" class="">
                    <strong id="invite_body_salutation_all" style="display:inline">
                        <span id="invite_body_salutation" data-style="${args->call_style:html:default('color:#404040'):input_type(css):arg_name(Style):arg_section(1, 1, 'Call', 'bookmark')}">${args->call_text:default('Hello,'):arg_name(Text):arg_section(1, 0, 'Call', 'bookmark')}</span>
                    </strong>
                    <br>
                    <span data-style="${args->call2_style:html:default('font-size:13px; font-weight:400px; line-height:18px; margin-top:0; color: #404040'):input_type(css):arg_name(Subtext style):arg_section(1, 3, 'Call', 'bookmark')}">${args->call2_text:default('You are invited to the following event:'):arg_name(Subtext):arg_section(1, 2, 'Call', 'bookmark')}</span>
                </p>
                <a data-style="${args->event_style:html:default('font-size:24px; line-height:26px; text-transform:uppercase; color: #0f90ba; text-decoration: none'):input_type(css):arg_name(Style):arg_section(2, 2, 'Event', 'bookmark')}" href="${args->event_link:html:default('https://www.eventbrite.com/e/twin-cities-code-camp-17-tickets-12383133285?ref=enivtefor001&amp;invite=NjMyODYyOS9lbmdzdHJvbS56YWNoQGdtYWlsLmNvbS8w&amp;utm_source=eb_email&amp;utm_medium=email&amp;utm_campaign=inviteformal001&amp;utm_term=eventpage'):input_type(url):arg_name(Link):arg_section(2, 1, 'Event', 'bookmark')}">${args->event_text:default(Twin Cities Code Camp 17):arg_name(Text):arg_section(2, 0, 'Event', 'bookmark')}</a>
            </div>
            <div style="margin-top:24px;">
                <img src="https://ebmedia.eventbrite.com/s3-s3/marketing/emails/invites/lottering.png" alt="divider" width="500" height="8" onerror="this.src='//counter.personyze.com/images/image-not-avail.jpg'">
            </div>
            <div style="margin-top:24px;">
                <p data-style="${args->location_description_style:html:default('line-height:18px; margin-top:0px; color:#404040'):input_type(css):arg_name(Description style):arg_section(3, 1, 'Location', 'map-marker')}">${args->location_description_text:default('Event to be held at the following time, date, and location:'):arg_name(Description text):arg_section(3, 0, 'Location', 'map-marker')}</p>
            </div>
            <table width="500" border="0" cellspacing="0" cellpadding="0">
                <tbody><tr>
                    <td style="display:inline; width:250px; vertical-align:top">
                        <a href="${args->location_image_link:html:default('https://www.eventbrite.com/e/twin-cities-code-camp-17-tickets-12383133285?ref=enivtefor001&amp;invite=NjMyODYyOS9lbmdzdHJvbS56YWNoQGdtYWlsLmNvbS8w&amp;utm_source=eb_email&amp;utm_medium=email&amp;utm_campaign=invitenew&amp;utm_term=eventimage&amp;ref=enivtefor001'):input_type(url):arg_name(Image link):arg_section(3, 3, 'Location', 'map-marker')}" target="_blank">
                             <img style="border: 1px solid #cac4c4" src="${args->location_image_url:html:default('https://www.eventbrite.com/staticmap_https_proxy?center=44.974237,-93.232282&amp;zoom=16&amp;markers=label:A|44.974237,-93.232282&amp;size=220x145&amp;sensor=true'):input_type(personyze_media_url):arg_name(Image url):arg_section(3, 2, 'Location', 'map-marker')}" onerror="this.src=&quot;//counter.personyze.com/images/image-not-avail.jpg&quot;">
                        </a>
                    </td>
                    <td style="font-size:13px; line-height:18px; width:250px; vertical-align:top">${args->location_address_text:default('<p style="color:#404040; width: 200px;">Saturday, October 4, 2014 from 8:30 AM to 5:00 PM (CDT)</p><p style="color:#404040;"><b>University of Minnesota - Keller Hall</b><br />EE/CS Building<br />200 Union Street SE<br />Minneapolis, MN 55455<br /><br /><a href="https://maps.google.com/maps?q=EE%2FCS+Building,+Minneapolis,+MN+55455+United+States&amp;hl=en" style="color:#0f90ba; text-decoration:none;" target="_blank">View Map</a></p>'):arg_name(Address):arg_section(3, 4, 'Location', 'map-marker')}
                    </td>
                </tr>
            </tbody></table>
            <table width="500" border="0" cellpadding="0" cellspacing="0" style="font-size:14px; line-height:18px; margin:20px 0 24px 0;">
                <tbody><tr>
                    <td width="250">
                        <p id="invite_rsvp_off" style="">
                            <a href="${args->attend_event_link:html:default('https://www.eventbrite.com/e/twin-cities-code-camp-17-tickets-12383133285?ref=enivtefor001&amp;invite=NjMyODYyOS9lbmdzdHJvbS56YWNoQGdtYWlsLmNvbS8w&amp;utm_source=eb_email&amp;utm_medium=email&amp;utm_campaign=inviteformalv2&amp;utm_term=attend&amp;ref=enivtefor001'):input_type(url):arg_name(Link):arg_section(4, 1, 'Attend event', 'check')}" data-style="${args->attend_event_style:html:default('display:inline-block; margin:4px 0; padding:12px 18px; background:url(''https://evbdn.eventbrite.com/s3-s3/static/images/django/background/glass_light-trans.png'') 0 50% repeat-x #e4e4e4;background-color:#95c033; font-size:15px; font-weight:bold; line-height:14px; text-decoration:none; border:1px solid #8bae42; border-radius:5px; text-shadow:0 1px 0 #6b8e4a; font-family:Helvetica, Arial, sans-serif'):input_type(css):arg_name(Style):arg_section(4, 2, 'Attend event', 'check')}" target="_blank">
                                <strong style="color:#fff;">${args->attend_event_text:default(Attend Event):arg_name(Text):arg_section(4, 0, 'Attend event', 'check')}</strong>
                            </a>
                        </p>
                    </td>
                    <td width="250">
                        <p style="font-size:13px; line-height:18px;">
                            <strong id="invite_share_event" style="color:#404040;display:inline">Share this event:</strong><br>
                            <a id="invite_body_facebook_share_icon" href="${args->facebook_share_link:html:default('https://www.facebook.com/share.php?u=https%3A%2F%2Fwww.eventbrite.com%2Fe%2Ftwin-cities-code-camp-17-tickets-12383133285%3Fref%3Desfb%26utm_campaign%3D201308%26utm_source%3DFacebookenivtefor001'):input_type(url):arg_name(Facebook link):arg_section(5, 0, 'Event share', 'share-alt')}" style="text-decoration:none; display:inline">
                                <img src="${args->facebook_image_url:html:default('https://ebmedia.eventbrite.com/s3-s3/marketing/emails/invites/facebook-share.png'):input_type(personyze_media_url):arg_name(Facebook image url):arg_section(5, 1, 'Event share', 'share-alt')}" alt="Facebook" title="Facebook" style="border: 0;" onerror="this.src=&quot;//counter.personyze.com/images/image-not-avail.jpg&quot;">
                            </a>
                            <a id="invite_body_twitter_share_icon" href="${args->twitter_share_link:html:default('https://twitter.com/home?status=I%27m+attending+Twin+Cities+Code+Camp+17+--+https%3A%2F%2Ftccc17.eventbrite.com%2F%3Fref%3Destwenivtefor001'):input_type(url):arg_name(Twitter link):arg_section(5, 2, 'Event share', 'share-alt')}" style="text-decoration:none; display:inline">
                                <img src="${args->twitter_image_url:html:default('https://ebmedia.eventbrite.com/s3-s3/marketing/emails/invites/twitter-share.png'):input_type(personyze_media_url):arg_name(Twitter image url):arg_section(5, 3, 'Event share', 'share-alt')}" alt="Twitter" title="Twitter" style="border: 0;" onerror="this.src=&quot;//counter.personyze.com/images/image-not-avail.jpg&quot;">
                            </a>
                            <a id="invite_body_linkedin_share_icon" href="${args->linkedin_share_link:html:default('https://www.linkedin.com/shareArticle?mini=true&amp;url=https%3A%2F%2Ftccc17.eventbrite.com%2F%3Fref%3Desli%26utm_campaign%3D201308%26utm_source%3DLinkedInenivtefor001&amp;title=Twin+Cities+Code+Camp+17&amp;summary=%5BOct+4%2C+2014%5D+-+%5BUniversity+of+Minnesota+-+Keller+Hall+-+EE%2FCS+Building+-+200+Union+Street+SE+-+Minneapolis%2C+MN+55455%5D+-+%5BTwin+Cities+Code+Camp%5D&amp;source=Eventbrite'):input_type(url):arg_name(Linkedin link):arg_section(5, 4, 'Event share', 'share-alt')}" style="text-decoration:none; display:inline">
                                <img src="${args->linkedin_image_url:html:default('https://ebmedia.eventbrite.com/s3-s3/marketing/emails/invites/linkedin-share.png'):input_type(personyze_media_url):arg_name(Linkedin image url):arg_section(5, 5, 'Event share', 'share-alt')}" alt="LinkedIn" title="LinkedIn" style="border: 0;" onerror="this.src=&quot;//counter.personyze.com/images/image-not-avail.jpg&quot;">
                            </a>
                        </p>
                    </td>
                </tr>
            </tbody></table>
            <img src="https://ebmedia.eventbrite.com/s3-s3/marketing/emails/invites/lottering.png" alt="divider" width="500" height="8" onerror="this.src=&quot;//counter.personyze.com/images/image-not-avail.jpg&quot;">
            <table width="500" border="0" cellpadding="0" cellspacing="0" style="font-size:13px; line-height:18px; margin:20px 0 24px 0;">
                <tbody><tr>
                    <td>
                        <div id="invite_body_custom_message">
                            <div data-style="${args->description_style:html:default('color:#404040'):input_type(css):arg_name(Style):arg_section(6, 1, 'Description', 'info')}">${args->description_text:default('Twin Cities Code Camp 17 is happening on October 4th, 2014 at the University of Minnesota! The Twin Cities Code Camp is a FREE, biannual coding conference held in the Minneapolis / St. Paul area. TCCC is full of content from great local and regional speakers across all stacks and styles of software development. It&#39;s by devs for devs! Be prepared, you will learn a ton! TCCC follows the guidelines...<br /><br /><br />Share this event on <a href="https://www.facebook.com/share.php?u=https%3A//tccc17.eventbrite.com/%3Fref%3Desfb" style="color: #0f90ba; text-decoration: none;">Facebook</a> and <a href="https://twitter.com/home?status=https%3A//tccc17.eventbrite.com/%3Fref%3Destw" style="color: #0f90ba; text-decoration: none;">Twitter</a><br /><br />We hope you can make it!<br /><br />Cheers,<br />Twin Cities Code Camp'):arg_name(Text):arg_section(6, 0, 'Description', 'info')}</div>
                        </div>
                    </td>
                </tr>
            </tbody></table>
        </div>
        <p style="text-align:center">
            <a href="${args->logo_link:html:default('http://www.eventbrite.com/r/enivtefor001?utm_source=eb_email&amp;utm_medium=email&amp;utm_campaign=inviteformal&amp;utm_term=eblogofooter'):input_type(url):arg_name(Link):arg_section(7, 1, 'Logo', 'image')}" target="_blank">
                <img src="${args->logo_url:html:default('https://ebmedia.eventbrite.com/s3-s3/marketing/emails/invites/LogoBadge.png'):input_type(personyze_media_url):arg_name(Image):arg_section(7, 0, 'Logo', 'image')}" alt="Eventbrite" border="0" data-style="${args->logo_style:html:default('margin:20px 0 30px 0'):input_type(css):arg_name(Style):arg_section(7, 2, 'Logo', 'image')}" onerror="this.src=&quot;//counter.personyze.com/images/image-not-avail.jpg&quot;">
            </a>
        </p>
    </div>
    <div style="background-color:#F5F8F7">
        <hr style="width:600px; margin: 0 0 10px 20px; border-color:#DEDEDE">
        <table width="580" id="footer_container" style="margin-left: 20px;padding-bottom: 25px;">
            <tbody><tr>
                <td data-style="${args->footer_text_style:html:default('padding: 0 10px; font-size:11px; color: #666; line-height:20px; padding-bottom:2px'):input_type(css):arg_name(Text style):arg_section(8, 1, 'Footer', 'info')}">${args->footer_text:default('<span style="width:300px; word-wrap: break-word;">This invitation was sent to you by <a href="http://www.eventbrite.com/org/1810127815" style="color: #666;">Twin Cities Code Camp</a> the organizer. </span>'):arg_name(Text):arg_section(8, 0, 'Footer', 'info')}</td>
                <td align="center" rowspan="3">
                    <a href="${args->footer_logo_link:html:default('http://www.eventbrite.com/home/?ref=eemail&amp;utm_source=eb_email&amp;utm_medium=email&amp;utm_campaign=invite&amp;utm_term=footer_invite'):input_type(url):arg_name(Link):arg_section(8, 3, 'Footer', 'info')}" style="text-decoration: none;">
                        <img src="${args->footer_logo_url:html:default('https://ebmedia.eventbrite.com/s3-s3/marketing/emails/invites/registration_by-logo.png'):input_type(personyze_media_url):arg_name(Image):arg_section(8, 2, 'Footer', 'info')}" alt="Eventbrite" border="0" onerror="this.src=&quot;//counter.personyze.com/images/image-not-avail.jpg&quot;">
                    </a>
                </td>
            </tr>
            <tr>
                <td data-style="${args->footer_address_style:html:default('padding: 0 10px; font-size:11px; color: #666; line-height:20px;; padding: 8px 0 10px 10px'):input_type(css):arg_name(Address style):arg_section(8, 5, 'Footer', 'info')}">${args->footer_address:default('<span style="padding: 0">Eventbrite </span> | <span style="padding: 0 3px;"> 155 5th St, 7th Floor </span> | <span style="padding: 0 3px;"> San Francisco, CA 94103 </span>'):arg_name(Address):arg_section(8, 4, 'Footer', 'info')}</td>
            </tr>
        </tbody></table>
    </div>
</div>
```


## Simple email



```
<div class="$responsive" style="box-sizing:border-box; ${args->style:html:default('margin-top: 0;
margin-right: auto;
margin-bottom: 0;
margin-left: auto;
padding: 20px;
width: 600px;
background-color: rgb(90, 107, 155);'):input_type(css):arg_name(Style):arg_section(0, 0, 'Box', 'th-large')}">
	<link href="https://fonts.googleapis.com/css?family=Open+Sans:300,400,600,700" rel="stylesheet">
	<div style="${args->title_style:html:default('font-family:Open Sans, Helvetica Neue, Helvetica, sans-serif; font-size:26px; font-weight:700; line-height:125%; letter-spacing:normal; color:white; text-align:center'):input_type(css):arg_name(Style):arg_section(1, 1, 'Title', 'bars')}">${args->title_text:default(Email Template):arg_name(Text):arg_section(1, 0, 'Title', 'bars')}</div>
	<img style="display:block; ${args->image_style:html:default('width:100%; height:auto; margin-top:50px; box-sizing:border-box'):input_type(css):arg_name(Style):arg_section(2, 1, 'Image', 'image')}" src="${args->image_url:html:default('https://images.unsplash.com/photo-1493939189225-ac796f2c2108?ixlib=rb-0.3.5&amp;q=80&amp;fm=jpg&amp;crop=entropy&amp;cs=tinysrgb&amp;w=1080&amp;fit=max&amp;s=c65dac902c6818a361d8a115a3f2c7f9'):input_type(personyze_media_url):arg_name(URL):arg_section(2, 0, 'Image', 'image')}">
	<div style="${args->content_style:html:default('margin-top: 50px;
font-family: Open Sans, Helvetica Neue, Helvetica, sans-serif;
font-size: 16px;
color: rgb(237, 234, 234);'):input_type(css):arg_name(Text style before button):arg_section(3, 1, 'Info', 'bars')}">${args->content_text:default('<p style="font-size:30px">Hello, User</p>

<p style="line-height:200%; padding-bottom:10px">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Donec libero purus, efficitur dictum dolor nec, malesuada vestibulum lorem. Quisque imperdiet pharetra nunc et rutrum.</p>

<p style="line-height:200%; padding-bottom:10px">Quisque at augue et neque rhoncus dictum. Suspendisse risus magna, tempus quis rutrum in, pulvinar a est. Sed egestas scelerisque rutrum.</p>
'):arg_name(Text before button):arg_section(3, 0, 'Info', 'bars')}</div>
	<a href="${args->button_link:html:default('#'):input_type(url):arg_name(Link):arg_section(4, 1, 'Action button', 'check')}" style="${args->button_style:html:default('display:block; margin-top:15px; padding:15px; background-color:#2980b9; color:white; border-radius:5px; font-family:Open Sans, Helvetica Neue, Helvetica, sans-serif; font-size:18px; font-weight:600; text-decoration:none; text-align:center'):input_type(css):arg_name(Style):arg_section(4, 2, 'Action button', 'check')}">${args->button_text:default(Example of button):arg_name(Text):arg_section(4, 0, 'Action button', 'check')}</a>
	<div style="${args->content2_style:html:default('margin-top: 20px;
font-family: Open Sans, Helvetica Neue, Helvetica, sans-serif;
font-size: 16px;
color: rgb(237, 234, 234);'):input_type(css):arg_name(Text style after button):arg_section(3, 3, 'Info', 'bars')}">${args->content2_text:default('<p style="line-height:200%">Got any questions? Feel free to email us at <a href="#" style="color:white; text-decoration:none">help@emailtemplates.com</a></p>

<p style="line-height:200%; padding-bottom:10px">To stop receiving these email notifications, change your email settings that are located on the Manage Account page.</p>

<p style="line-height:180%">Thanks<br />
The Chemelle Team</p>
'):arg_name(Text after button):arg_section(3, 2, 'Info', 'bars')}</div>
	<div style="${args->footer_style:html:default('margin-top:50px; font-family:Open Sans, Helvetica Neue, Helvetica, sans-serif; font-size:10px; color:white; text-align:center'):input_type(css):arg_name(Style):arg_section(5, 1, 'Footer', 'bars')}">${args->footer_text:default('<p style="line-height:1.7;">Chemelle<br />
If you don&#39;t want to receive this email, you can <a href="#" style="font-weight:700; color:white; text-decoration:underline;">unsubscribe from our mailing list</a><br />
To update your email preferences <a href="#" style="font-weight:700; color:white; text-decoration:underline;">click here</a><br />
Chemelle, World, Universe</p>
'):arg_name(Text):arg_section(5, 0, 'Footer', 'bars')}</div>
</div>

```


## Simple email



```
<div class="$responsive" style="box-sizing:border-box; ${args->style:html:default('margin-top: 0;
margin-right: auto;
margin-bottom: 0;
margin-left: auto;
padding: 15px;
width: 600px;
background-color: white;'):input_type(css):arg_name(Style):arg_section(0, 0, 'Box', 'th-large')}">
	<link href="https://fonts.googleapis.com/css?family=Open+Sans:300,400,600,700" rel="stylesheet">

	<img style="display:block; ${args->image_style:html:default('width: 100%;
height: auto;
margin-top: 0px;
box-sizing: border-box;'):input_type(css):arg_name(Style):arg_section(1, 1, 'Image', 'image')}" src="${args->image_url:html:default('https://static.personyze.com/upload/362/7d0a26d42b6f9a72.jpeg'):input_type(personyze_media_url):arg_name(URL):arg_section(1, 0, 'Image', 'image')}">
	<div style="${args->content_style:html:default('margin-top: 50px;
font-family: Open Sans, Helvetica Neue, Helvetica, sans-serif;
font-size: 16px;
color: black;'):input_type(css):arg_name(Text style before button):arg_section(2, 1, 'Info', 'bars')}">${args->content_text:default('<p style="font-size:30px">Hello, User</p>

<p style="line-height:200%; padding-bottom:10px">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Donec libero purus, efficitur dictum dolor nec, malesuada vestibulum lorem. Quisque imperdiet pharetra nunc et rutrum.</p>

<p style="line-height:200%; padding-bottom:10px">Quisque at augue et neque rhoncus dictum. Suspendisse risus magna, tempus quis rutrum in, pulvinar a est. Sed egestas scelerisque rutrum.</p>
'):arg_name(Text before button):arg_section(2, 0, 'Info', 'bars')}</div>
	<a href="${args->button_link:html:default('#'):input_type(url):arg_name(Link):arg_section(3, 1, 'Action button', 'check')}" style="${args->button_style:html:default('display: block;
margin-top: 15px;
margin-right:auto;
margin-left:auto;
padding: 15px;
background-color: #2980b9;
color: white;
border-radius: 5px;
font-family: Open Sans, Helvetica Neue, Helvetica, sans-serif;
font-size: 18px;
font-weight: 600;
text-decoration: none;
text-align: center;
width: 70%;'):input_type(css):arg_name(Style):arg_section(3, 2, 'Action button', 'check')}">${args->button_text:default(Example of button):arg_name(Text):arg_section(3, 0, 'Action button', 'check')}</a>
	<div style="${args->content2_style:html:default('margin-top: 20px;
font-family: Open Sans, Helvetica Neue, Helvetica, sans-serif;
font-size: 16px;
color: rgb(64, 27, 27);'):input_type(css):arg_name(Text style after button):arg_section(2, 3, 'Info', 'bars')}">${args->content2_text:default('<p style="line-height: 200%;">Got any questions? Feel free to email us</p>

<p style="line-height: 200%; padding-bottom: 10px;">To stop receiving these email notifications, change your email settings that are located on the Manage Account page.</p>

<p style="line-height: 180%;">Thanks<br />
The Team</p>
'):arg_name(Text after button):arg_section(2, 2, 'Info', 'bars')}</div>
	<div style="${args->footer_style:html:default('margin-top: 50px;
font-family: Open Sans, Helvetica Neue, Helvetica, sans-serif;
font-size: 10px;
color: rgb(47, 39, 39);
text-align: center;'):input_type(css):arg_name(Style):arg_section(4, 1, 'Footer', 'bars')}">${args->footer_text:default('<p style="line-height:1.7;">&nbsp;</p>

<p style="font-weight:700;  text-decoration:underlinel; ine-height:200%; padding-bottom:10px">If you don&#39;t want to receive this email, you can&nbsp;unsubscribe from our mailing list <a href="https://pic.personyze.com/unsubscribe/k=${action_key:html}/u=${id:html}"><span style="">click here</span></a></p>
'):arg_name(Text):arg_section(4, 0, 'Footer', 'bars')}</div>
</div>
```


