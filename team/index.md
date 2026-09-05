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
  Current members, grouped by class year (soonest to graduate first) and sorted
  by surname within each year.

  The surname is the last word of the member's name. For a name where that is
  wrong (a compound surname, say), set `last-name` in that member's front
  matter and it is used instead.

  Note: a multi-line Liquid assign whose pipes sit on their own lines silently
  drops its filters, so the assigns below are kept on one line.
{% endcomment %}
{% assign current = site.members | where_exp: "m", "m.role != 'principal-investigator'" | where_exp: "m", "m.group != 'alum'" %}
{% assign years = current | group_by: "class-year" | sort: "name" %}
{% for year in years %}
  {% assign keys = "" | split: "" %}
  {% for member in year.items %}
    {% assign surname = member.last-name | default: member.name | split: " " | last %}
    {% assign key = surname | append: "|" | append: member.name | append: "|" | append: member.slug %}
    {% assign one = key | split: "~~" %}
    {% assign keys = keys | concat: one %}
  {% endfor %}
  {% assign keys = keys | sort %}
  {% for key in keys %}
    {% assign slug = key | split: "|" | last %}
    {% include portrait.html lookup=slug %}
  {% endfor %}
{% endfor %}

{% include section.html %}

## Lab Alums

{% assign alums = site.members | where_exp: "m", "m.group == 'alum'" %}
{% assign alum_years = alums | group_by: "class-year" | sort: "name" | reverse %}
<ul class="alums">
{% for year in alum_years %}
  {% assign keys = "" | split: "" %}
  {% for member in year.items %}
    {% assign surname = member.last-name | default: member.name | split: " " | last %}
    {% assign key = surname | append: "|" | append: member.name | append: "|" | append: member.slug %}
    {% assign one = key | split: "~~" %}
    {% assign keys = keys | concat: one %}
  {% endfor %}
  {% assign keys = keys | sort %}
  {% for key in keys %}
    {% assign slug = key | split: "|" | last %}
    {% assign member = site.members | where: "slug", slug | first %}
  <li>
    <a href="{{ member.url | relative_url }}">{{ member.name }}</a>{% if member.class-year %} <span class="alum-year">Class of {{ member.class-year }}</span>{% endif %}{% if member.links.linkedin %} <a class="alum-linkedin" href="https://www.linkedin.com/in/{{ member.links.linkedin }}" data-tooltip="LinkedIn" aria-label="{{ member.name }} on LinkedIn">{% include icon.html icon="fa-brands fa-linkedin" %}</a>{% endif %}
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
