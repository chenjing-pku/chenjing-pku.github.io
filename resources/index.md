---
title: Resources
nav:
  order: 3
  tooltip: Software, datasets, and more
---

# {% include icon.html icon="fa-solid fa-wrench" %}Resources

## Code

<div class="grid-container">
  {% assign code_items = site.data.projects | where: "group", "code" %}
  {% for item in code_items %}
    <div class="card-plain">
      <div class="card-text">
        <a href="{{ item.url | default: item.pdf }}">{{ item.title }}</a>
        <div class="card-subtitle">
           {% if item.venue %}{{ item.venue }}{% endif %}{% if item.venue and item.year %}, {% endif %}{% if item.year %}{{ item.year }}{% endif %}
        </div>
      </div>
    </div>
  {% endfor %}
</div>

{% include section.html %}

## Data

<div class="grid-container">
  {% assign data_items = site.data.projects | where: "group", "data" %}
  {% for item in data_items %}
    <div class="card-plain">
      <div class="card-text">
        <a href="{{ item.url | default: item.pdf }}">{{ item.title }}</a>
        <div class="card-subtitle">
           {% if item.venue %}{{ item.venue }}{% endif %}{% if item.venue and item.year %}, {% endif %}{% if item.year %}{{ item.year }}{% endif %}
        </div>
      </div>
    </div>
  {% endfor %}
</div>
