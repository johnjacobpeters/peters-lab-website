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
{% include list.html data="members" component="portrait" filter="role != 'principal-investigator' and group != 'alum'" %}

{% include section.html %}

## Lab Alums

{% include list.html data="members" component="portrait" filter="group == 'alum'" style="small" %}

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
