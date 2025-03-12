---
layout: page
title: Projects
permalink: /projects/
---

<ul>
  {% for project in site.projects %}
    <li>
      <a href="{{ project.url }}">{{ project.title }}</a>
      <small>{{ project.date | date: "%B %d, %Y" }}</small>
    </li>
  {% endfor %}
</ul>