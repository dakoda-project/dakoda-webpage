---
layout: page
permalink: /publications/
title: Publikationen
description: Alle Publikationen im Rahmen des DAKODA-Projekts.
years: [2023, 2022]
nav: true
---
<!-- _pages/publications.md -->
<!---{% bibliography -f labpapers -q @*[year={{y}}]* %} --->

<div class="publications">

{%- for y in page.years %}
  <h2 class="year">{{y}}</h2>
  {% bibliography -f dakoda-papers -q @*[year={{y}}]* %}
{% endfor %}

</div>
