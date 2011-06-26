---
layout: default
title: julian gruber
---

<img src="/images/me.jpg" alt="me" id="me" />

hi, my name is julian gruber and i am a webarchitect and computer science student from munich, germany.

i found [mickey mouse in the gardens of versailles](/images/mickey-versailles.jpg).

reach me via [mail](mailto:julian@juliangruber.com) and check out my [github projects](http://github.com/juliangruber).

everything here is copyrighted 2011 because i haven't yet made up my mind about which license to choose.

this site is in a very early stage, so popular features like search, <del>feeds</del>, pagination and so forth are still missing.

proudly powered by: dreamhost, debian, nginx, ruby, jekyll, markdown, gsl, rdiscount, classifier, liquid, html5, css, javascript (for html5 support) and vim.

<hr />

###recent posts ([feed](/atom.xml))

<ul id="pls">
   {% for post in site.posts %}
   <li><a href="{{ post.url }}">{{ post.title }}</a> <span>{{ post.date | date_to_string }}</span></li>
   {% endfor %}
</ul>
