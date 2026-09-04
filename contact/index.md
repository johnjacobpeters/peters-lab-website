---
title: Contact
nav:
  order: 5
  tooltip: Email, booking, and address
---

# {% include icon.html icon="fa-regular fa-envelope" %}Contact

I am looking forward to hearing from you!

If you would like to book a meeting with me, please use the link below.

{%
  include button.html
  type="email"
  text="john.peters@richmond.edu"
  link="john.peters@richmond.edu"
%}
{%
  include button.html
  icon="fa-regular fa-calendar"
  text="Book a meeting"
  link="https://johnpeters.youcanbook.me/"
%}
{%
  include button.html
  type="address"
  tooltip="Our location on Google Maps"
  link="https://www.google.com/maps/search/?api=1&query=Gottwald+Center+for+the+Sciences+University+of+Richmond"
%}

{% include section.html dark=true %}

{% capture col1 %}
**The Peters Lab**  
Department of Biology  
University of Richmond
{% endcapture %}

{% capture col2 %}
Gottwald Science Center  
138 UR Drive  
University of Richmond, VA 23173
{% endcapture %}

{% include cols.html col1=col1 col2=col2 %}
