---
layout: page
title: Writings
background: '/img/bg-post.jpg'
---

{% for post in site.categories.Writings %}
 <article class="post-preview">
  <a href="{{ post.url | prepend: site.baseurl | replace: '//', '/' }}">
    <h2 class="post-title">{{ post.title }}</h2>
    {% if post.subtitle %}
    <h4 class="post-subtitle">{{ post.subtitle }}</h4>
    {% else %}
    <h4 class="post-subtitle">{{ post.excerpt | strip_html | truncatewords: 15 }}</h4>
    {% endif %}
  </a>
  <p class="post-meta">{{ post.date | date: '%B %d, %Y' }} &middot; {% include read_time.html content=post.content %}
  </p>
</article>
{% endfor %}