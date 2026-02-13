---
layout: page
title: projects
permalink: /projects/
description: A collection of projects.
nav: true
nav_order: 3
display_categories: []
horizontal: false
---

<!-- pages/projects.md -->
<div class="projects">
{% assign sorted_projects = site.projects | sort: "importance" %}
{% if sorted_projects.size > 0 %}
  <div class="row row-cols-1 row-cols-md-3">
    {% for project in sorted_projects %}
      {% include projects.liquid %}
    {% endfor %}
  </div>
{% else %}
  <p>Projects coming soon.</p>
{% endif %}
</div>
