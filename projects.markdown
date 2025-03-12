---
layout: page
title: Projects
permalink: /projects/
---

<ul>
  {% assign sorted_projects = site.projects | sort: "date" %}
  {% for project in sorted_projects reversed %}
    <li>
      <a href="{{ project.url }}">{{ project.title }}</a>
      <small>{{ project.duration }}</small>
      <p>{{ project.summary }}</p>
    </li>
  {% endfor %}
</ul>