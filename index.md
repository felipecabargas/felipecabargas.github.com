---
layout: page
title: pase y lea... sin compromiso
tagline: Supporting tagline
---
{% include JB/setup %}

<h3>Artículos</h3>
<ul class="posts">
  {% for post in site.posts %}
    <li><span>{{ post.date | date_to_string }}</span> &raquo; <a href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a></li>
  {% endfor %}
</ul>

<h3>Enlaces</h3>
<ul class="links">
  <li><span>Squape</span> &raquo; <a href="http://www.squape.com/">Ir</a></li>
  <li><span>Blog de Nicolás Cabargas</span> &raquo; <a href="http://nicolascabargas.blogspot.com/">Ir</a></li>
  <li><span>Blog de Pía Gajardo P.</span> &raquo; <a href="http://pithaisautumn.wordpress.com/">Ir</a></li>
  <li><span>Proyecto Fedora en Español</span> &raquo; <a href="http://fedoraproject.org/es/">Ir</a></li>
  <li><span>Enlazar es Bueno</span> &raquo; <a href="http://www.enlazaresbueno.cl/">Ir</a></li>
</ul>