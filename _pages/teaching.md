---
layout: page
permalink: /teaching/
title: Teaching
description:
nav: true
nav_order: 2
display_categories: [Certificates, Supervision, Courses and seminars]
---

<div class="projects">
  {% for category in page.display_categories %}
  <a id="{{ category }}" href=".#{{ category }}">
    <h2 class="category">{{ category }}</h2>
  </a>
  {% assign categorized_teaching = site.teaching | where: "category", category %}
  {% assign sorted_teaching = categorized_teaching | sort: "number" | reverse %}
  <!-- Generate cards for each course -->
  <div class="row row-cols-1 row-cols-md-1">
    {% for teaching in sorted_teaching %}
      {% include teaching.liquid %}
    {% endfor %}
  </div>
  {% endfor %}
</div>
