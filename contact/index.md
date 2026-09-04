---
title: Contact
nav:
  order: 5
  tooltip: Email, address, and location
---

# {% include icon.html icon="fa-regular fa-envelope" %}Contact

Interested in joining the lab, collaborating, or learning more about our work?
We would love to hear from you.

{%
  include button.html
  type="email"
  text="john.peters@richmond.edu"
  link="john.peters@richmond.edu"
%}
{%
  include button.html
  type="address"
  tooltip="Our location on Google Maps"
  link="https://www.google.com/maps/search/?api=1&query=Gottwald+Center+for+the+Sciences+University+of+Richmond"
%}

{% include section.html dark=true %}

{% capture col1 %}
**Peters Lab**  
Department of Biology  
University of Richmond
{% endcapture %}

{% capture col2 %}
Gottwald Science Center  
138 UR Drive  
University of Richmond, VA 23173
{% endcapture %}

{% include cols.html col1=col1 col2=col2 %}
