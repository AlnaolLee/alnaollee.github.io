---
layout: page
title: Projects
permalink: /projects/
---

<ul>
  {% for project in site.projects %}
    <li>
      <a href="{{ project.url }}">{{ project.title }}</a>
      <small>2025</small>
      <p>{{ project.summary }}</p>
    </li>
  {% endfor %}
</ul>