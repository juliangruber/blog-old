---
layout: default
title: juliangruber
---

<ul id="pl">
   {% for post in site.posts %}
   <li><a href="{{ post.url }}" class="utitle"><span class="hash">#</span><span class="title">{{ post.title }}</span></a>
   {{ post.content }}
   </li>
   {% endfor %}
</ul>
