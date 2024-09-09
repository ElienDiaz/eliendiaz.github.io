---
layout: page
title: Music
permalink: /music/
description: >
  <p>Sometimes I make music!</p> 

  <p>I have experience with vocal music, piano, and some arranging! 
  These days, however, the bulk of my musical efforts goes into performing with 
  my quartet Mischief and with making Multitracks for part learning, recently collaborating with my friend 
  <a href='https://www.goldengroovemusic.com/'>Grant Goulding</a> to help create learning tracks for his new arrangements.</p>

  <p>Read on to find past performances I've been a part of with quartets and choruses, and 
  for some of the tracks I've created. Feel free to check out my <a href='https://soundcloud.com/elie-diaz-965006234'>soundcloud</a> for more!</p>

image: mischief_cover.jpg
image_circular: false
image_caption: This is my current quartet, <a href='https://www.facebook.com/Q.Mischief'> Mischief</a>!

nav: true
nav_order: 4
display_categories: [Performances, Tracks]
horizontal: false
---

<!-- pages/music.md -->
<div class="projects">
{%- if site.enable_project_categories and page.display_categories %}
  <!-- Display categorized projects -->
  {%- for category in page.display_categories %}
  <h2 class="category">{{ category }}</h2>
  {%- assign categorized_projects = site.music | where: "category", category -%}
  {%- assign sorted_projects = categorized_projects | sort: "importance" %}
  <!-- Generate cards for each project -->
  {% if page.horizontal -%}
  <div class="container">
    <div class="row row-cols-2">
    {%- for project in sorted_projects -%}
      {% include projects_horizontal.html %}
    {%- endfor %}
    </div>
  </div>
  {%- else -%}
  <div class="grid">
    {%- for project in sorted_projects -%}
      {% include projects.html %}
    {%- endfor %}
  </div>
  {%- endif -%}
  {% endfor %}

{%- else -%}
<!-- Display projects without categories -->
  {%- assign sorted_projects = site.music | sort: "importance" -%}
  <!-- Generate cards for each project -->
  {% if page.horizontal -%}
  <div class="container">
    <div class="row row-cols-2">
    {%- for project in sorted_projects -%}
      {% include projects_horizontal.html %}
    {%- endfor %}
    </div>
  </div>
  {%- else -%}
  <div class="grid">
    {%- for project in sorted_projects -%}
      {% include projects.html %}
    {%- endfor %}
  </div>
  {%- endif -%}
{%- endif -%}
</div>
