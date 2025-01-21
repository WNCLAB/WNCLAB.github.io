---
layout: page
title: team
permalink: /team/
# description: Lab Members
nav: true
nav-order: 1
# display_categories: [Lab Directors, Postdoctoral Fellows, PhD Students, MSc Students, Research Associates, Undergraduates, Collaborators, Alumni]
# display_categories: [Lab Directors, PhD Students, MSc Students, Research Assistants, Undergraduates, High School, Alumni]
display_categories: [Lab Directors, Current Students, Alumni]
horizontal: false
---
<!-- pages/people.md -->
<div class="people">
  <!-- Display categorized people -->
  {%- for category in page.display_categories %}
  <h2 class="category">{{ category }}</h2>
  {%- assign categorized_people = site.people | where: "category", category -%}
  {%- assign sorted_people = categorized_people | sort: "rank" %}
  <!-- Generate cards for each person -->
  <div class="grid">
    {%- for person in sorted_people -%}
      {%- if person.show -%}
        {% include people.html %}
      {%- endif -%}
    {%- endfor %}
  </div>
  {% endfor %}
</div>