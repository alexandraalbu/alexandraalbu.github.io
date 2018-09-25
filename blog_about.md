---
layout: default
permalink: /blog_about.html
---
<div style="float:left;width:70%;">
This is the place where I write about problems or topics I like.

<ul>
  {% for post in site.posts %}
    <li>
      <a href="{{ post.url }}">{{ post.title }}</a>
    </li>
  {% endfor %}
</ul>
</div>
<div style="float:right;width:30%;">
    <p>
    Links to some very interesting blogs:
    <ul>
        <li><a href="http://bjlkeng.github.io/">Brian Keng</a></li>
        <li><a href="https://wiseodd.github.io/techblog/">Agustinus Kristiadi</a></li>
        <li><a href="http://ruishu.io/"></a>Rui Shu</li>
        <li><a href="https://mortendahl.github.io/">Morten Dahl</a></li>
    </ul>
    </p>
</div>