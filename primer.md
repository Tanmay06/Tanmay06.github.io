---
layout: page
title: Primer
background: '/img/bg-projects.jpg'
---
## Overview
- This section includes my notes and primers for the topics I'm studying or have studied.

{% for category in site.categories %}
{% assign cat_name=category[0] %}
{% if "Projects, Writings" contains cat_name %}
{% else %}
<h2 class="post-title">{{ cat_name }}</h2>
<ul>
{% for post in site.categories[cat_name] %}
    <li>{{ post.title }}</li>
{% endfor %}
</ul>
{% endif %}
{% endfor %}
