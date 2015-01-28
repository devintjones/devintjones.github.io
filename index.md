---
layout: page
title: Devin T Jones
tagline: This is my blog
---
{% include JB/setup %}

# Devin T Jones

Hi, this is my blog. I created it on 1/27 and it is under construction. 

I'm studying for my masters in CS at Columbia University and I plan to host my course notes here. Most of my projects can be found on my github account. 

Posts on the site:

<ul class="posts">
  {% for post in site.posts %}
    <li><span>{{ post.date | date_to_string }}</span> &raquo; <a href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a></li>
  {% endfor %}
</ul>


