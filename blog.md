---
layout: page
title: Blog

weight: 3
---

<ul class="content-listing ">
  {% for post in site.categories.blog %}
      <li class="listing">
        <hr class="slender">
        <a href="{{ post.url | prepend: site.baseurl }}"><h2 class="larger">{{ post.title }}</h2></a>
        <br><span class="smaller">{{ post.date | date: "%B %-d, %Y" }}</span>  <br/>
        <div>{{ post.excerpt }}</div> 
      </li>
  {% endfor %}
</ul>