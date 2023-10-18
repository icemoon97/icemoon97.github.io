---
title:
layout: default
permalink: /projects/
published: true
display_categories: [Fun, Hackathon, Other]
---

<!-- <div class="ProjectContainer">

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

</div> -->

<style>

/* body {
    font-family: Arial, sans-serif;
    background-color: #f5f5f5;
    margin: 0;
    padding: 0;
} */

.projects-section {
    max-width: 1200px;
    margin: 50px auto;
    padding: 20px;
    background-color: #fff;
}

.projects-section h1 {
    text-align: center;
    margin-bottom: 50px;
}

.project-card-link {
    text-decoration: none;
}

.project-card {
    margin: 20px 0;
    display: flex;
    align-items: center;
    padding: 15px;
    border: 1px solid #e0e0e0;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
    transition: box-shadow 0.3s, transform 0.3s;
}

.project-card:hover {
    box-shadow: 0 6px 12px rgba(0, 0, 0, 0.15);
    transform: translateY(-5px);
}

.project-card img {
    width: 40%; 
    height: auto;
    margin-right: 20px;
}

.project-details h2 {
    margin: 0;
    color: #333;
    transition: color 0.3s;
}

.project-card:hover .project-details h2 {
    color: #007bff; /* Change this to your preferred highlight color */
}

.project-details p {
    margin: 10px 0;
    color: #777;
}

.section-title {
    font-size: 24px; /* Adjust based on your preference */
    text-transform: uppercase; /* Converts text to all capital letters */
    margin-bottom: 15px;
    position: relative;
    display: inline-block;
}

.section-title:after {
    content: "";
    position: absolute;
    left: 0;
    bottom: -10px;
    height: 3px;
    width: 100%;
    background-color: #333; /* Change to your preferred underline color */
}


</style>

{%- for category in page.display_categories %}
<div class="projects-section">
  <h2 class="section-title">{{ category }}</h2>
  {%- assign categorized_projects = site.projects | where: "category", category -%}
  <!-- {%- assign sorted_projects = categorized_projects | sort: "importance" %} -->

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

<!-- <div class="projects-section">
  <h2 class="section-title">Hackathons</h2>

  <a href="" class="project-card-link">
    <div class="project-card">
      <img src="{{ 'project-thumbnails/aoc.png' | prepend: '/assets/images/' | relative_url }}">
      <div class="project-details">
        <h2>Advent of Code</h2>
        <p>Participated in yearly programming challenge series since 2017</p>
      </div>
    </div>
  </a>

  <a href="https://github.com/icemoon97/web-assembly-redex" class="project-card-link">
    <div class="project-card">
      <img src="{{ 'project-thumbnails/webassembly_logo.jpg' | prepend: '/assets/images/' | relative_url }}">
      <div class="project-details">
        <h2>WASM Redex</h2>
        <p>Working WebAssembly specification built in PLT Redex</p>
      </div>
    </div>
  </a>

</div>

<div class="projects-section">
  <h2 class="section-title">Just for fun</h2>

  <a href="" class="project-card-link">
    <div class="project-card">
      <img src="{{ 'project-thumbnails/aoc.png' | prepend: '/assets/images/' | relative_url }}">
      <div class="project-details">
        <h2>Advent of Code</h2>
        <p>Participated in yearly programming challenge series since 2017</p>
      </div>
    </div>
  </a>

  <a href="https://github.com/icemoon97/web-assembly-redex" class="project-card-link">
    <div class="project-card">
      <img src="{{ 'project-thumbnails/webassembly_logo.jpg' | prepend: '/assets/images/' | relative_url }}">
      <div class="project-details">
        <h2>WASM Redex</h2>
        <p>Working WebAssembly specification built in PLT Redex</p>
      </div>
    </div>
  </a>

</div> -->
