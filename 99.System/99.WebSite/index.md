---
layout: default
title: World: Ervindell
---

# Welcome to Ervindell

This is the chronicle of the world of **Ervindell**, where brave adventurers face forgotten ruins, ancient evils, and untold riches.

## Recent Adventures
<h2>{{ site.data.samplelist.docs_list_title }}</h2>
<ul>
   {% for item in site.data.samplelist.docs %}
      <li><a href="{{ item.url }}">{{ item.title }}</a></li>
   {% endfor %}
</ul>

## Explore

