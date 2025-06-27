---
title: Projects
nav:
  order: 2
  tooltip: Software, datasets, and more
---

# {% include icon.html icon="fa-solid fa-wrench" %}Resources

## Featured

{% include list.html component="card" data="resources" filter="group == 'featured'" %}

{% include section.html %}

## More

{% include list.html component="card" data="resources" filter="!group" style="small" %}
