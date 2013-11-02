---
layout: post_index
title: From My Brain
---

Out of my mind. Onto the web.

<ul class="posts">
    {% for post in site.categories.thoughts %}
    <li><span>{{ post.date | date_to_string }}</span> &raquo; <a href="{{ post.url }}">{{ post.title }}</a></li>
    {% endfor %}
</ul>

