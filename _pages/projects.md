---
layout: page
title: Skillset
permalink: /projects/
description: Attempting to summarise the work I do. 
nav: true
nav_order: 2
display_categories: [projects]
horizontal: false
---

<b> What is Actuarial Science about? </b>

Actuarial science is a discipline of measuring and managing financial risks in insurance, pensions, and finance. It blends mathematics, statistics, and economics to predict uncertain future events and develop strategies to mitigate potential financial losses. Actuaries play a crucial role in assessing risks related to life expectancy, accidents, natural disasters, and market fluctuations. This expertise helps businesses and governments make informed decisions, ensuring financial stability and long-term sustainability. 

For instance in insurance sector, actuarial science determines policy pricing, reserves for claims and risk management strategies. Regulatory frameworks like Solvency II and IFRS 17 guide actuarial work, ensuring companies maintain sufficient capital and comply with financial reporting standards. 

Beyond insurance, actuarial skills can be utlised in climate risk assessment, pension planning, risk management, healthcare analytics, investment risk management etc. Actuarial work thus finds a place of its own where uncertainty needs to be quantified and managed. 

This page should collect my actuarial work aperiodically.

<!-- pages/projects.md -->
<div class="projects">
{%- if site.enable_project_categories and page.display_categories %}
  <!-- Display categorized projects -->
  {%- for category in page.display_categories %}
  <h2 class="category">{{ category }}</h2>
  {%- assign categorized_projects = site.projects | where: "category", category -%}
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
  {%- assign sorted_projects = site.projects | sort: "importance" -%}
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
