---
title: Team
nav:
  order: 3
  tooltip: Meet the lab
---

# {% include icon.html icon="fa-solid fa-users" %}Meet The Lab

The Peters Lab is a group of undergraduate and post-baccalaureate researchers at
the University of Richmond. Students in the lab gain experience in molecular
cloning, protein purification, introductory computational structural biology, and
confocal and electron microscopy.

{% include section.html %}

{% include list.html data="members" component="portrait" filter="role == 'principal-investigator'" %}

{% comment %}
  Current members, grouped by class year (soonest to graduate first) and
  alphabetical by name within each year.
{% endcomment %}
{% assign current = site.members | where_exp: "m", "m.role != 'principal-investigator'" | where_exp: "m", "m.group != 'alum'" %}
{% assign years = current | group_by: "class-year" | sort: "name" %}
{% for year in years %}
  {% assign people = year.items | sort: "name" %}
  {% for member in people %}
    {% include portrait.html lookup=member.slug %}
  {% endfor %}
{% endfor %}

{% include section.html %}

## Lab Alums

{% assign alums = site.members | where_exp: "m", "m.group == 'alum'" %}
{% assign alum_years = alums | group_by: "class-year" | sort: "name" | reverse %}
<ul class="alums">
{% for year in alum_years %}
  {% assign people = year.items | sort: "name" %}
  {% for member in people %}
  <li>
    <a href="{{ member.url | relative_url }}">{{ member.name }}</a>{% if member.class-year %} <span class="alum-year">Class of {{ member.class-year }}</span>{% endif %}
  </li>
  {% endfor %}
{% endfor %}
</ul>

{% include section.html background="images/background.jpg" dark=true %}

## Join us

We are always glad to hear from University of Richmond students interested in
structural biology, neuroscience, and learning and memory. Get in touch to talk
about research opportunities in the lab.

{%
  include button.html
  link="contact"
  text="Contact us"
  icon="fa-solid fa-envelope"
%}
