---
layout:   default
title:    Tartalomjegyzék / table of contents
author:   flex
category: index
tags:     [muzax, video]
comments: false

headerSIZE:       670px
headerBGimage:    'https://video-images.vice.com/articles/6259c2576032f900969ad342/lede/1650049778845-russiancruisermoskva.jpeg'
headerBGposition: 'background-position: center;'
headerLEFT:       '<h1>Start</h1>Valahol el kell kezdeni és ez most itt lesz a tartalomjegyzéknél...'
headerRIGHT:      '<h1 style="">⬅</h1>'
headerRIGHTbottom: '<div style="text-align: right"><div class="" style="display: inline-block; font-size: 50%; margin-bottom: 0px; background: black; color: white; padding: 7px;">Source: <a class="menu" href="https://www.vice.com/en/article/v7dkpx/a-piece-of-the-true-cross-may-have-sunk-with-russias-warship">"A Piece of the True Cross May Have Sunk with Russia’s Warship"</a></div></div>'

contentLEFT: '<center style="background-color: lightgrey; padding-top: 58px;"><a href="https://twitter.com/FleXoft"><img style="width: 80%; margin-bottom: 3%;" src="https://upload.wikimedia.org/wikipedia/en/thumb/4/47/Twitter_2010_logo_-_from_Commons.svg/1024px-Twitter_2010_logo_-_from_Commons.svg.png"></a></center>
<center style="background-color: lightgrey; padding: 20px;">
<a class="twitter-timeline" href="https://twitter.com/FleXoft?ref_src=twsrc%5Etfw" data-tweet-limit="5" data-dnt="true" data-chrome="noheader nofooter noscrollbar noborders transparent" data-lang="en"></a><script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script></center>'
contentLEFTDateStyleOverride: 'padding: 0px;'
contentLEFTStyleOverride:     'background: rgba( 211, 211, 211, 1 ); color: white;'

disableContentTitle: ''
xdisablecontentLEFT: true
xcontentRIGHTStyleOverride:       'width: 100%;'
contentpaddingRIGHTStyleOverride: 'padding-bottom: 0px;'
---

{% assign rawtags = "" %}
{% for post in site.posts %}
{% assign ttags = post.tags | join:'|' | append:'|' %}
{% assign rawtags = rawtags | append:ttags %}
{% endfor %}

{% assign rawtags = rawtags | split:'|' | sort %}

{% assign tags = "" %}

{% for tag in rawtags %}
{% if tag != "" %}

{% if tags == "" %}
{% assign tags = tag | split:'|' %}
{% endif %}

{% unless tags contains tag %}
{% assign tags = tags | join:'|' | append:'|' | append:tag | split:'|' %}
{% endunless %}
{% endif %}
{% endfor %}

<hr style="border-top: 5px solid red;">
{% if page.disableContentTitle != true %}<h1>{{ page.title }}</h1>{% endif %}
<hr style="border-top: 5px solid red;">

Nem biztos, hogy teljesen jó ötlet ez a [#hashtag](/tags)-elés, de egyelőre ez most még marad itt:

<div style="width: 65%; margin: auto; padding: 30px; text-align: center;">

{% assign tmptags = site.tags | sort %}
{% for tag in tmptags %}
{% assign fontsize = tag | last | size | times: 3 | plus: 80 %}
{% if fontsize > 225 %}
	{% assign fontsize = 225 %}
	{% assign boldfont = "font-weight: bold;" %}
{% endif %}
  <a href="tags#{{ tag | first | slugify }}" style="font-size: {{ fontsize }}%; {{ boldfont }}">{{ tag[0] }}{% if tag.last.size > 1 %}({{ tag | last | size }})
{% endif %}
  </a>
{% endfor %}

</div>

És akkor itt jön az igazi tartalomjegyzék:

<p></p><div class="tableofcontents">

{% assign tmpcategories = site.categories %}
{% for category in tmpcategories %}
	<div style="width: 100%; border: 0px solid; display: inline-block;">
	{% capture category_name %}{{ category | first }}{% endcapture %}
	<h2 style="margin: 0px">{{ category_name }}</h2>
	<hr width="100%" style="margin: 0px">
	<ul style="list-style-type: none; margin-top: 1rem; margin-bottom: 1rem;">
	{% assign site_list = site.categories[category_name] | sort:"date" %}
	{% for post in site_list %}
		<li><a href="{{ site.baseurl }}{{ post.url }}">> {{post.title}}</a></li>
	{% endfor %}
	</ul>
	</div>
{% endfor %}

</div>