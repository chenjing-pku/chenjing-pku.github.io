---
title: Resources
nav:
  order: 3
  tooltip: Software, datasets, and more
---

# {% include icon.html icon="fa-solid fa-wrench" %}Resources

## Code

<div class="custom-grid-container">
  {% assign code_items = site.data.projects | where: "group", "code" %}
  {% for item in code_items %}
    <div class="custom-resource-card">
      <div class="custom-card-content">
        <a href="{{ item.url | default: item.pdf | default: item.redirect | default: item.link | default: '#' }}" target="_blank">
          {{ item.title }}
        </a>
        
        <div class="custom-card-meta">
          {% assign venue_text = item.venue | default: item.publication | default: item.journal | default: item.conference %}
          
          {% if venue_text %}
            <span class="venue-badge">{{ venue_text }}</span>
          {% endif %}
          
          {% if item.year %}
            <span class="year-badge">{{ item.year }}</span>
          {% endif %}
        </div>
      </div>
    </div>
  {% endfor %}
</div>

{% include section.html %}

## Data

<div class="custom-grid-container">
  {% assign data_items = site.data.projects | where: "group", "data" %}
  {% for item in data_items %}
    <div class="custom-resource-card">
      <div class="custom-card-content">
        <a href="{{ item.url | default: item.pdf | default: item.redirect | default: item.link | default: '#' }}" target="_blank">
          {{ item.title }}
        </a>
        <div class="custom-card-meta">
          {% assign venue_text = item.venue | default: item.publication | default: item.journal | default: item.conference %}
          
          {% if venue_text %}
            <span class="venue-badge">{{ venue_text }}</span>
          {% endif %}
          
          {% if item.year %}
            <span class="year-badge">{{ item.year }}</span>
          {% endif %}
        </div>
      </div>
    </div>
  {% endfor %}
</div>
