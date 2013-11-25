---
layout: post
title: Artsy
---

This is my collection of artsy stuff, be it written, sung, played or whatever.

If you want to keep track of this, you can always <a href="feed.xml"><img
class="icon-inline" src="/gfx/icon-feed.png" />subscribe</a>.

<ul class="posts">
    {% for post in site.categories.artsy %}
    <li><span>{{ post.date | date_to_string }}</span> &raquo; <a href="{{ post.url }}">{{ post.title }}</a></li>
    {% endfor %}
</ul>

