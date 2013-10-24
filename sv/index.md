---
layout: post
title: In Swedish
---

These posts are in swedish.

<ul class="posts">
    {% for post in site.posts %}
    {% if post.category == "sv" %}
    <li><span>{{ post.date | date_to_string }}</span> &raquo; <a href="{{ post.url }}">{{ post.title }}</a></li>
    {% endif %}
    {% endfor %}
</ul>

