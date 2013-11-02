---
layout: post
title: In Swedish
---

These posts are in swedish. Så nu vet du det.

Klicka på eller kopiera <a href="feed.xml"><img class="icon-inline"
src="/gfx/icon-feed.png" />prenumerationslänken</a> till din RSS-läsare för att
göra ditt liv lite enklare och lite roligare.

<ul class="posts">
    {% for post in site.categories.sv %}
    <li><span>{{ post.date | date_to_string }}</span> &raquo; <a href="{{ post.url }}">{{ post.title }}</a></li>
    {% endfor %}
</ul>

