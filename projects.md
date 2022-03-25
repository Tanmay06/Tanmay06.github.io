---
layout: page
title: Projects
background: '/img/bg-projects.jpg'
---

{% for post in site.categories.Projects %}
 <article class="post-preview">
  <!-- <a href="{{ post.url | prepend: site.baseurl | replace: '//', '/' }}"> -->
    <h2 class="post-title">{{ post.title }}</h2>
    {% if post.subtitle %}
    <p class="post-subtitle">{{ post.subtitle }}</p>
    {% else %}
    <p class="post-subtitle">{{ post.excerpt | strip_html | truncatewords: 15 }}</p>
    {% endif %}
    <!-- <p><b>Role:</b>{{ post.role }}</p>
    <p><b>Why: </b>{{ post.why }}</p>
    <p><b>What: </b>{{ post.what }} </p>
    <p><b>Read More:</b>{{ post.link }}</p> -->
    {{ post.content }}
  <!-- </a> -->
  <p class="post-link">
  {% for link in post.links %}
    <a href="{{ link }}">{{ link | remove:'https://' | split:'/' | first | remove:'www.'}}</a>
  {% endfor %}
  
  </p>
  <p class="post-meta">{{ post.date | date: '%B %d, %Y' }}</p>
</article>
{% endfor %}