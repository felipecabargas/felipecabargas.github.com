---
layout: page
title: pase y lea... sin compromiso
tagline: Supporting tagline
---
{% include JB/setup %}

<!-- <p>{{ post.content | strip_html | truncatewords: 30 }}...</p> -->
<!-- <hr> -->

<h3 style="text-align: center;">Artículos</h3>
<ul class="posts">
  {% for post in site.posts %}
    <li>
      <span>{{ post.date | date_to_string }}</span> &raquo; <a href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a>
    </li>
  {% endfor %}
</ul>

<div class="links">
  <h3>Enlaces</h3>
  <span>Squape</span> &raquo; <a href="http://www.squape.com/">Ir</a> | <span>Blog de Nicolás Cabargas</span> &raquo; <a href="http://www.cabargas.cl/">Ir</a> | <span>Blog de Pía Gajardo</span> &raquo; <a href="http://haycachao.wordpress.com/">Ir</a>
</ul>