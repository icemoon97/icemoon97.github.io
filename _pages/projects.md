---
title:
layout: default
permalink: /projects/
published: true
display_categories: [Machine Learning, Data Visualization, Misc, Hackathon]
---

{%- for category in page.display_categories %}
<div class="projects-section">
  <h2 class="section-title">{{ category }}</h2>
  {%- assign categorized_projects = site.projects | where: "category", category -%}
  {%- assign sorted_projects = categorized_projects | sort: "order" %}

  {%- for project in sorted_projects -%}

  {% if project.redirect %}
  <a href="{{ project.redirect }}" target="_blank" class="project-card-link">
  {% else %}
  <a href="{{ project.url | prepend: site.baseurl | prepend: site.url }}" class="project-card-link">
  {% endif %}
    <div class="project-card">
      <img src="{{ project.thumbnail | prepend: '/assets/images/' | relative_url }}">
      <div class="project-details">
        <h2>{{ project.title }}</h2>
        <p>{{ project.description }}</p>
      </div>
    </div>
  </a>
  {%- endfor %}

</div>
{% endfor %}
