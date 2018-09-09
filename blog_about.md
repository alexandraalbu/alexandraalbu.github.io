---
layout: default
permalink: /blog_about.html
---

This is the place where I write about problems or topics I find interesting.

<ul>
  {% for post in site.posts %}
    <li>
      <a href="{{ post.url }}">{{ post.title }}</a>
    </li>
  {% endfor %}
</ul>