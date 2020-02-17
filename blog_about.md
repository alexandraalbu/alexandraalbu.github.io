---
layout: default
permalink: /blog_about.html
---
<div style="float:left;width:70%;">

This blog is a rather chaotic collection of short posts about problems or topics I like.

<ul>
  {% for post in site.posts %}
    <h3><a href="{{ post.url }}">{{ post.title }}</a></h3>
    <p><small><strong>{{ post.date | date: "%B %e, %Y" }}</strong> - {{ post.category }}</small></p>			
  {% endfor %}
</ul>
</div>
<div style="float:right;width:30%;">
    <p>
    Links to some very interesting blogs:
    <ul>
        <li><a href="http://bjlkeng.github.io/">Bounded Rationality (by Brian Keng)</a></li>
        <li><a href="https://wiseodd.github.io/techblog/">Agustinus Kristiadi</a></li>
        <li><a href="http://ruishu.io/">Rui Shu</a></li>
        <li><a href="https://mortendahl.github.io/">Cryptography and Machine Learning (by Morten Dahl)</a></li>
        <li><a href="https://chrisorm.github.io/">Infinite Norm</a></li>
        <li><a href="http://alexhwilliams.info/itsneuronalblog/">It's Neuronal</a></li>
    </ul>
    </p>
</div>