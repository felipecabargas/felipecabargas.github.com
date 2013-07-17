---
layout: page
title: Hacking for food
tagline: blog de Felipe Cabargas
---
{% include JB/setup %}

<!-- <p>{{ post.content | strip_html | truncatewords: 30 }}...</p> -->
<!-- <hr> -->

<h3 style="text-align: center;">Artículos</h3>
<div class="posts">
  {% for post in site.posts %}
    <h5 class="subheader"><span class="subheader label">{{ post.date | date_to_string }}</span> <a href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a></h5>
    <hr />
  {% endfor %}
</div>

<div class="links panel">
  <h3 style="text-align: center;">Enlaces</h3>
  <ul class="button-group even two-up">
    <li>
      <a href="http://www.squape.com/" class="button">SQUAPE</a> 
    </li>
    <li>
      <a href="http://www.cabargas.cl/" class="button">Nicolás Cabargas</a>
    </li>
  </ul>
</div>