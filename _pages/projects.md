---
layout: page
title: Projects
permalink: /projects/
description: My research projects.
nav: true
nav_order: 3
display_categories: [work, fun]
horizontal: false
---

## A glimpse at my work 📖

The main question I tackle is the following : Can an impacting urban network disruption emerge from a simple and decentralized collective action ?

In other words, imagine people following the same walking rules. Can they spontaneously gather and move in mobile groups that will block roads and disturb traffic?
Have I aroused your curiosity ? Then you can download my intership thesis presenting our first investigations regarding the quantitative impact of protests. Our job has mainly been to establish the state of the art concerning this question. More precisly, we connected it with an already existing litterature regarding random walks and city models.

<!-- pages/projects.md -->
<div class="projects">
{% if site.enable_project_categories and page.display_categories %}
  <!-- Display categorized projects -->
  {% for category in page.display_categories %}
  <a id="{{ category }}" href=".#{{ category }}">
    <h2 class="category">{{ category }}</h2>
  </a>
  {% assign categorized_projects = site.projects | where: "category", category %}
  {% assign sorted_projects = categorized_projects | sort: "importance" %}
  <!-- Generate cards for each project -->
  {% if page.horizontal %}
  <div class="container">
    <div class="row row-cols-2">
    {% for project in sorted_projects %}
      {% include projects_horizontal.liquid %}
    {% endfor %}
    </div>
  </div>
  {% else %}
  <div class="grid">
    {% for project in sorted_projects %}
      {% include projects.liquid %}
    {% endfor %}
  </div>
  {% endif %}
  {% endfor %}

{% else %}

<!-- Display projects without categories -->

{% assign sorted_projects = site.projects | sort: "importance" %}

  <!-- Generate cards for each project -->

{% if page.horizontal %}

  <div class="container">
    <div class="row row-cols-2">
    {% for project in sorted_projects %}
      {% include projects_horizontal.liquid %}
    {% endfor %}
    </div>
  </div>
  {% else %}
  <div class="grid">
    {% for project in sorted_projects %}
      {% include projects.liquid %}
    {% endfor %}
  </div>
  {% endif %}
{% endif %}
</div>
