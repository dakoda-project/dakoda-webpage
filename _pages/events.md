---
layout: page
title: Events
permalink: /events/
description: Events im Rahmen des DAKODA-Projekts.
nav: true
#nav_rank:

# Ehemals Projekte
display_categories: [2023]
horizontal: True

---

<!-- pages/projects.md -->
<div class="events">
{%- if site.enable_project_categories and page.display_categories %}
  <!-- Display categorized projects -->
  {%- for category in page.display_categories %}
  <h2 class="category">{{ category }}</h2>
  {%- assign categorized_events = site.events | where: "category", category -%}
  {%- assign sorted_events = categorized_events | sort: "importance" %}
  <!-- Generate cards for each project -->
  {% if page.horizontal -%}
  <div class="container">
    <div class="row row-cols-2">
    {%- for project in sorted_events -%}
      {% include events_horizontal.html %}
    {%- endfor %}
    </div>
  </div>
  {%- else -%}
  <div class="grid">
    {%- for project in sorted_events -%}
      {% include events.html %}
    {%- endfor %}
  </div>
  {%- endif -%}
  {% endfor %}

{%- else -%}
<!-- Display projects without categories -->
  {%- assign sorted_events = site.events | sort: "importance" -%}
  <!-- Generate cards for each project -->
  {% if page.horizontal -%}
  <div class="container">
    <div class="row row-cols-2">
    {%- for project in sorted_events -%}
      {% include events_horizontal.html %}
    {%- endfor %}
    </div>
  </div>
  {%- else -%}
  <div class="grid">
    {%- for project in sorted_events -%}
      {% include events.html %}
    {%- endfor %}
  </div>
  {%- endif -%}
{%- endif -%}
</div>
