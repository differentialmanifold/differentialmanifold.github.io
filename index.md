---
layout: page
title: Yi Dai 
tag: Home Page 
---
{% include JB/setup %}

<img style="margin-top: auto;float: right;display: inline;" src="{{ BASE_PATH }}images/Totoro.jpeg" title="Totoro" alt="photo of Totoro" width="240px" />
    
## About me

My name is Yi Dai.I'm interested in physics and machine learning,and wish to demonstrate them through programming.
You're most likely to find me on [GitHub](https://github.com/differentialmanifold),and contact me at *differentialmanifold@gmail.com*.

## Demo

[a crawler from lagou](http://blogmongo-differentialmanifold.herokuapp.com/)  *a simple crawler from lagou, and show on heroku through nodejs with mongodb database*

[a multi-blog system](http://blog-differentialmanifold.herokuapp.com/)  *a simple multi-blog system built on express and mongodb,show on heroku*

[Brownian movement](http://jsfiddle.net/everybody76/8oj3f1eb/embedded/result/)  *a interesting simulation of rigid body collision using D3*

## Sample Posts

Here's a sample "posts list".

<ul class="posts">
  {% for post in site.posts %}
    <li><span>{{ post.date | date_to_string }}</span> &raquo; <a href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a></li>
  {% endfor %}
</ul>

