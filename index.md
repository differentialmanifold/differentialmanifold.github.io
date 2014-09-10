---
layout: page
title: Yi Dai 
tag: Home Page 
---
{% include JB/setup %}

<img style="margin-top: auto;float: right;display: inline;" src="{{ BASE_PATH }}images/butterfly.jpg" title="butterfly" alt="photo of butterfly" width="240px" />
    
## About me

My name is Yi Dai.I'm interested in physics and machine learning,and wish to demonstrate them through programming.
You're most likely to find me on [GitHub](https://github.com/differentialmanifold),and contact me at *daiyi_051@163.com*.

## Demo

[Brownian movement](http://jsfiddle.net/everybody76/8oj3f1eb/embedded/result/)
unfinished...

## Sample Posts

Here's a sample "posts list".

<ul class="posts">
  {% for post in site.posts %}
    <li><span>{{ post.date | date_to_string }}</span> &raquo; <a href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a></li>
  {% endfor %}
</ul>

