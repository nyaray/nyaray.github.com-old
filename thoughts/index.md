---
layout: post
title: From My Brain
---

Out of my mind. Onto the web.

Klick on or copy the <a href="feed.xml"><img class="icon-inline"
src="/gfx/icon-feed.png" />subscribe link</a> to your RSS-reader to
subscriiiibeeee.

<ul class="posts">
    {% for post in site.categories.thoughts %}
    <li><span>{{ post.date | date_to_string }}</span> &raquo; <a href="{{ post.url }}">{{ post.title }}</a></li>
    {% endfor %}
</ul>

