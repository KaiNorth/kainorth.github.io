---
layout: page
title: Projects
permalink: /Projects/
description: A growing collection of your cool Projects.
nav: true
nav_order: 2
display_categories: [work, fun]
horizontal: false
---

<!-- pages/Projects.md -->
<div class="Projects">
{%- if site.enable_project_categories and page.display_categories %}
  <!-- Display categorized Projects -->
  {%- for category in page.display_categories %}
  <h2 class="category">{{ category }}</h2>
  {%- assign categorized_Projects = site.Projects | where: "category", category -%}
  {%- assign sorted_Projects = categorized_Projects | sort: "importance" %}
  <!-- Generate cards for each project -->
  {% if page.horizontal -%}
  <div class="container">
    <div class="row row-cols-2">
    {%- for project in sorted_Projects -%}
      {% include Projects_horizontal.html %}
    {%- endfor %}
    </div>
  </div>
  {%- else -%}
  <div class="grid">
    {%- for project in sorted_Projects -%}
      {% include Projects.html %}
    {%- endfor %}
  </div>
  {%- endif -%}
  {% endfor %}

{%- else -%}
<!-- Display Projects without categories -->
  {%- assign sorted_Projects = site.Projects | sort: "importance" -%}
  <!-- Generate cards for each project -->
  {% if page.horizontal -%}
  <div class="container">
    <div class="row row-cols-2">
    {%- for project in sorted_Projects -%}
      {% include Projects_horizontal.html %}
    {%- endfor %}
    </div>
  </div>
  {%- else -%}
  <div class="grid">
    {%- for project in sorted_Projects -%}
      {% include Projects.html %}
    {%- endfor %}
  </div>
  {%- endif -%}
{%- endif -%}
</div>
