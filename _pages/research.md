---
layout: archive
title: "Research"
permalink: /research/
author_profile: true
---

*How Do Natural Gas Pipeline Networks Affect Emissions From Drilling and Flaring?* (Job Market Paper)

[Download](http://lbeatty1.github.io/files/Beatty_JMP.pdf)


{% if author.googlescholar %}
  You can also find my articles on <u><a href="{{author.googlescholar}}">my Google Scholar profile</a>.</u>
{% endif %}

{% include base_path %}

{% for post in site.publications reversed %}
  {% include archive-single.html %}
{% endfor %}
