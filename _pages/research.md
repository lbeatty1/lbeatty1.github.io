---
layout: archive
title: "Research"
permalink: /research/
author_profile: true
---

*Endogenous Network Growth With Spillover Effects: The Effect of Pipeline Networks on Flaring* (Job Market Paper)

Coming Soon!

{% if author.googlescholar %}
  You can also find my articles on <u><a href="{{author.googlescholar}}">my Google Scholar profile</a>.</u>
{% endif %}

{% include base_path %}

{% for post in site.publications reversed %}
  {% include archive-single.html %}
{% endfor %}
