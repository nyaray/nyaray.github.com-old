---
layout: post
title: In English
---

These are mostly things that I've written out of choice, rather than necessity.

Out of my mind.<br />
Onto the web.

**Beware!** Something has gone awry with my blogging software, making my posts
render in a strange way. I'm looking into what I can do to fix it.

<ul class="posts">
    {% for post in site.categories.thoughts %}
    <li><span>{{ post.date | date_to_string }}</span> &raquo; <a href="{{ post.url }}">{{ post.title }}</a></li>
    {% endfor %}
</ul>

Click on or copy the <a href="feed.xml"><img class="icon-inline"
src="/gfx/icon-feed.png" />subscribe link</a> to your RSS-reader to
subscriiiibeeee.

