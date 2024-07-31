---
layout: page
permalink: /publikationen/
title: Publikationen
description: Alle Publikationen im Rahmen des DAKODA-Projekts.
years: [2024,2023, 2022, 2021, 2020, 2019, 2018, 2017]
nav: true
#nav_rank:
---

<div class="publications">

{%- for y in page.years %}
  <h2 class="year">{{y}}</h2>
  {% bibliography -f dakoda-papers -q @*[year={{y}}]* %}
{% endfor %}

</div>
