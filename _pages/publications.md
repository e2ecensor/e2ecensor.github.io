---
layout: page
permalink: /publications/
title: publications
description: publications produced by or related to the Disguiser project.
years: [2022, 2021]
nav: true
nav_order: 3
---
<!-- _pages/publications.md -->
<div class="publications">

{%- for y in page.years %}
  <h2 class="year">{{y}}</h2>
  {% bibliography -f papers -q @*[year={{y}}]* %}
{% endfor %}

</div>
