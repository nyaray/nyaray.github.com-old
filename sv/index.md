---
layout: post
title: På svenska
---

Här samlar jag texter jag skrivit mer för att jag velat än behövt eller varit
tvungen.

**OBS!** Något strular med min bloggplattform och jag har inte orkat städa upp
det, så inläggen ser skadade ut, men det mesta borde ändå gå att läsa fram
tills att jag reder ut problemet.

<ul class="posts">
    {% for post in site.categories.sv %}
    <li><span>{{ post.date | date_to_string }}</span> &raquo; <a href="{{ post.url }}">{{ post.title }}</a></li>
    {% endfor %}
</ul>

Klicka på eller kopiera <a href="feed.xml"><img class="icon-inline"
src="/gfx/icon-feed.png" />prenumerationslänken</a> till din RSS-läsare för att
göra ditt liv lite enklare och lite roligare.

