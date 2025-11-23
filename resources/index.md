---
title: Resources
nav:
  order: 3
  tooltip: Software, datasets, and more
---

# {% include icon.html icon="fa-solid fa-wrench" %}Resources

## Code

<div class="card-container">
  {% assign code_items = site.data.projects | where: "group", "code" %}
  {% for item in code_items %}
    <div class="card">
      <div class="card-image">
         {% if item.img %}
           <img src="{{ item.img | relative_url }}" alt="{{ item.title }}">
         {% else %}
           <i class="fa-solid fa-flask" style="font-size: 64px; color: #e0e0e0;"></i>
         {% endif %}
      </div>
      <div class="card-text">
        <a href="{{ item.url | default: item.pdf }}">{{ item.title }}</a>
        <div class="card-subtitle">{{ item.venue }} {{ item.year }}</div>
      </div>
    </div>
  {% endfor %}
</div>

{% include section.html %}

## Data

<div class="card-container">
  {% assign data_items = site.data.projects | where: "group", "data" %}
  {% for item in data_items %}
    <div class="card">
      <div class="card-image">
         {% if item.img %}
           <img src="{{ item.img | relative_url }}" alt="{{ item.title }}">
         {% else %}
           <i class="fa-solid fa-flask" style="font-size: 64px; color: #e0e0e0;"></i>
         {% endif %}
      </div>
      <div class="card-text">
        <a href="{{ item.url | default: item.pdf }}">{{ item.title }}</a>
        <div class="card-subtitle">{{ item.venue }} {{ item.year }}</div>
      </div>
    </div>
  {% endfor %}
</div>
