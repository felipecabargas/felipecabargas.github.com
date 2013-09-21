---
layout: page
title: Hacking for food
tagline: blog de Felipe Cabargas
---
{% include JB/setup %}

<!-- <p>{{ post.content | strip_html | truncatewords: 30 }}...</p> -->
<!-- <hr> -->

<div class="posts">
  <ul class="block-grid two-up">
    {% for post in site.posts %}
      <li style="height: 150px; width: 420px; margin:25px; border-bottom: 1px solid #0480be; border-radius: 5px;">
        <h4><a href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a>
        <h4 class="subheader"><span class="subheader label">{{ post.date | date_to_string }}</span></h4>
        </h4>
      </li>
  {% endfor %}
</ul>
</div>