---
layout:   default
title:    INDEX (ez egy teszt oldal)
author:   flex
category: index
tags:     [muzax, video]
comments: false

headerSIZE:       570px
headerBGimage:    'https://video-images.vice.com/articles/6259c2576032f900969ad342/lede/1650049778845-russiancruisermoskva.jpeg'
headerBGimagesrc: 'https://www.vice.com/en/article/v7dkpx/a-piece-of-the-true-cross-may-have-sunk-with-russias-warship'
headerBGposition: 'background-position: center;'
headerLEFTtext:   '<h1>Start</h1>Valahol el kell kezdeni.'
headerRIGHTtext:  '<h1>⬅</h1>'

disableContentTitle:   ''
disableContentPadding: ''
contentpaddingleftStyleOverride:  'padding: 0px;'

xbeforeContent:          '<div><div style="position: relative; width: 100%; height: 0; padding-bottom: 56.25%;"><iframe style="position: absolute; width: 100%; height: 100%;" src="https://www.youtube.com/embed/zcua9XzKVas" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe></div></div>'

contentLeft: '<center style="background-color: lightgrey; padding-top: 55px;"><a href="https://twitter.com/FleXoft"><img style="width: 80%; margin-bottom: 3%;" src="https://upload.wikimedia.org/wikipedia/en/thumb/4/47/Twitter_2010_logo_-_from_Commons.svg/1024px-Twitter_2010_logo_-_from_Commons.svg.png"></a></center>
<center style="background-color: lightgrey; padding: 20px;">
<a class="twitter-timeline" href="https://twitter.com/FleXoft?ref_src=twsrc%5Etfw" data-tweet-limit="3" data-dnt="true" data-chrome="noheader nofooter noscrollbar noborders transparent" data-lang="en"></a><script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script><center><i class="icon-star-empty-1" style="color: red;"></i> <i class="icon-star-empty-1" style="color: red;"></i> <i class="icon-star-empty-1" style="color: red;"></i></center>'
---

{% if page.disableContentTitle != 'yes' %}<h1>{{ page.title }}</h1>{% endif %}

<div class="rainbow"></div>

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

<div style="width: 65%; margin: auto; padding: 30px; text-align: center;">

{% assign tmptags = site.tags | sort %}
{% for tag in tmptags %}
{% assign fontsize = tag | last | size | times: 3 | plus: 80 %}
{% if fontsize > 225 %}
	{% assign fontsize = 225 %}
	{% assign boldfont = "font-weight: bold;" %}
{% endif %}
  <a href="#{{ tag | first | slugify }}" style="font-size: {{ fontsize }}%; {{ boldfont }}">{{ tag[0] }}{% if tag.last.size > 1 %}({{ tag | last | size }})
{% endif %}
  </a>
{% endfor %}

</div>

<p><div class="tableofcontents">

{% assign tmpcategories = site.categories %}
{% for category in tmpcategories %}
	<div style="width: 100%; border: 0px solid; display: inline-block;">
	{% capture category_name %}{{ category | first }}{% endcapture %}
	<hr width="100%" style="margin: 0px">
	<h2 style="margin: 0px">{{ category_name }}</h2>
	<hr width="100%" style="margin: 0px">
	<ul>
	{% assign site_list = site.categories[category_name] | sort:"date" %}
	{% for post in site_list %}
		<li><a href="{{ site.baseurl }}{{ post.url }}">{{post.title}}</a></li>
	{% endfor %}
	</ul>
	</div>
{% endfor %}

</div></p>
<div class="rainbow"></div>