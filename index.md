---
layout:   default
title:    INDEX (ez egy teszt oldal)
author:   flex
category: Muzax
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
<a class="twitter-timeline" href="https://twitter.com/FleXoft?ref_src=twsrc%5Etfw" data-tweet-limit="5" data-dnt="true" data-chrome="noheader nofooter noscrollbar noborders transparent" data-lang="en"></a><script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script><center><i class="icon-star-empty-1" style="color: red;"></i> <i class="icon-star-empty-1" style="color: red;"></i> <i class="icon-star-empty-1" style="color: red;"></i></center>'
---

{% if page.disableContentTitle != 'yes' %}<h1>{{ page.title }}</h1>{% endif %}

<div class="rainbow"></div>

<p><div style="column-count: 2; column-gap: 50px; column-rule: 2px solid lightgrey;">
    {% assign sorted-posts = site.posts | reverse %}
	{% for post in sorted-posts %}
	
  		{% assign currentdate = post.date | date: "%Y" %}
	
  		{% if currentdate != date %}
			{% unless forloop.first %}</ul></div>{% endunless %}
			<div style="width: 100%; border: 0px solid; display: inline-block;">
			<hr width="100%">
			<div style="border: 0px solid;"><h1 id="y{{post.date | date: "%Y"}}">{{ currentdate }}</h1></div>
			<hr width="100%">
			<ul style="border: 0px solid;">
			{% assign date = currentdate %}
  		{% endif %}
  		
		<li><a href="{{ post.url }}">{{ post.date | date: "%m.%d." }} - {{ post.title }}</a></li>
  		
		{% if forloop.last %}</ul></div>{% endif %}
	
	{% endfor %}
</div></p>
<div class="rainbow"></div>