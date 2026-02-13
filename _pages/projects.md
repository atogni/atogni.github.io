---
layout: page
title: Projects
permalink: /projects/
description: A collection of projects.
nav: true
nav_order: 3
display_categories: [Science, Fun]
horizontal: true
---

<!-- pages/projects.md -->
<div class="projects">
{% for category in page.display_categories %}
  <h2 class="category">{{ category }}</h2>
  {% assign categorized_projects = site.projects | where: "category", category %}
  {% assign sorted_projects = categorized_projects | sort: "importance" %}
  {% if sorted_projects.size > 0 %}
    {% for project in sorted_projects %}
      <div class="row mb-3">
        <div class="col-sm-3">
          {% if project.img %}
            <a href="{% if project.redirect %}{{ project.redirect }}{% else %}{{ project.url | relative_url }}{% endif %}">
              {%
                include figure.liquid
                loading="eager"
                path=project.img
                sizes="150px"
                alt="project thumbnail"
                class="img-fluid rounded z-depth-1"
              %}
            </a>
          {% endif %}
        </div>
        <div class="col-sm-9">
          <a href="{% if project.redirect %}{{ project.redirect }}{% else %}{{ project.url | relative_url }}{% endif %}">
            <h5 class="font-weight-bold">{{ project.title }}</h5>
          </a>
          <p>{{ project.description }}</p>
        </div>
      </div>
    {% endfor %}
  {% else %}
    <p>Coming soon.</p>
  {% endif %}
{% endfor %}
</div>
