---
title: Team
nav:
  order: 3
  tooltip: About our team
---

# {% include icon.html icon="fa-solid fa-users" %}Team

The Peters Lab is a group of undergraduate researchers and faculty at the
University of Richmond. Students in the lab gain hands-on experience in
molecular cloning, protein purification, introductory computational structural
biology, and confocal and electron microscopy.

{% include section.html %}

{% include list.html data="members" component="portrait" filter="role == 'principal-investigator'" %}
{% include list.html data="members" component="portrait" filter="role != 'principal-investigator'" %}

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
