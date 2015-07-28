---
layout: page
title: Welcome to my blog!
---
{% include JB/setup %}

Hello, my name is Chen Peiyu.

You can follow me at [Github](https://github.com/CherryCHan)


<img src="/assets/images/index/11378803_851535998233189_656081922_n.jpg" alt="img" style="width:300px"/>

## My Posts

Here's a simple posts list.

<ul class="posts">
  {% for post in site.posts %}
    <li><span>{{ post.date | date_to_string }}</span> &raquo; <a href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a></li>
  {% endfor %}
</ul>



