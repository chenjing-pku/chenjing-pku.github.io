---
title: Resources
nav:
  order: 2
  tooltip: Software, datasets, and more
---

# {% include icon.html icon="fa-solid fa-wrench" %}Resources

## Code

{% include list.html component="card" data="resources" filter="group == 'code'" %}

{% include section.html %}

## Data

{% include list.html component="card" data="resources" filter="!group" style="small" %}
