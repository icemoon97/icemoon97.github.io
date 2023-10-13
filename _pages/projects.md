---
title:
layout: default
permalink: /projects/
published: true
---


<div class="ProjectContainer">

	<div class="gallery">

  {% for project in site.projects %}


  <div class="projectTile">
    {% if project.redirect %}
    <a href="{{ project.redirect }}" target="_blank">
    {% else %}
    <a href="{{ project.url | prepend: site.baseurl | prepend: site.url }}">
    {% endif %}
    {% if project.thumbnail %}
    <div class="thumbnail">
      <img src="{{ project.thumbnail | prepend: '/assets/images/' | relative_url }}">
    </div>
    {% endif %}
    <div class="tileBody">
      <h2>{{ project.title }}</h2>
      <p>{{ project.description }}</p>
    </div>
    </a>
  </div>

  {% endfor %}

	</div>

</div>
