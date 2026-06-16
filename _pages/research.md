---
layout: archive
title: ""
permalink: /research/
author_profile: true
---

## Working Papers

**"Pricing the Social Cost of Flaring: Composition, Location, and Policy Implications."** With Mark Agerton, Wesley Blundell, Ben Gilbert, and Sophia Salzer. Submitted, February 2026. Available on [SSRN](https://dx.doi.org/10.2139/ssrn.6313938).

**"Pipelines, Drilling, and Environmental Externalities: Insights from a Dynamic Model of Natural Gas Flaring."** Draft Available Upon Request.

## Works in Progress

**"Cleanup Delay and Second-Best Environmental Policy: Structural Estimates from Texas Oil & Gas Wells"** With Mark Agerton and Diógenes Cruz.

**"Learning about Greenhouse Gas Emissions from Atmospheric Inversion Data: Insights from MethaneSAT."** With Ben Gilbert and Eric Lewis.

## Resting Papers

**"How Do Natural Gas Pipeline Networks Affect Emissions From Drilling and Flaring?"** [Download](http://lbeatty1.github.io/files/Beatty_JMP.pdf)

*An earlier version of my working paper "Pipelines, Drilling, and Environmental Externalities" (above). I've revised the project substantially since, and keep this draft available for reference.*



{% if author.googlescholar %}
  You can also find my articles on <u><a href="{{author.googlescholar}}">my Google Scholar profile</a>.</u>
{% endif %}

{% include base_path %}

{% for post in site.publications reversed %}
  {% include archive-single.html %}
{% endfor %}
