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
  <span>Edoome</span> &raquo; <a href="http://www.edoome.com/">Ir</a> | <span>Blog de Nicolás Cabargas</span> &raquo; <a href="http://nicolascabargas.blogspot.com/">Ir</a> | <span>Blog de Pía Gajardo P.</span> &raquo; <a href="http://pithaisautumn.wordpress.com/">Ir</a> | <span>Proyecto Fedora en Español</span> &raquo; <a href="http://fedoraproject.org/es/">Ir</a> |<span>Enlazar es Bueno</span> &raquo; <a href="http://www.enlazaresbueno.cl/">Ir</a>
</ul>