---
title: Projects
nav:
  order: 2
  tooltip: Research projects in the lab
---

# {% include icon.html icon="fa-solid fa-wrench" %}Projects

Ongoing research projects in the lab.

{% include search-info.html %}

{% include section.html %}

{% include list.html component="card" data="projects" filter="group == 'featured'" %}

{% include section.html %}

## More

{% include list.html component="card" data="projects" filter="!group" style="small" %}
