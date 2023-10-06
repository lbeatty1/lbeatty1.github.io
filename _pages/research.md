---
layout: archive
title: "Research"
permalink: /research/
author_profile: true
---

## How Do Natural Gas Pipeline Networks Affect Emissions From Drilling and Flaring? (Job Market Paper)

[Download](http://lbeatty1.github.io/files/Beatty_JMP.pdf)

*Most oil wells co-produce natural gas. Producers can choose to burn this valuable co-product on site (known as flaring) if the cost of connecting to the existing natural gas pipeline network is sufficiently high. While flaring is damaging to the climate, there exists surprisingly little research on the economics of flaring.  I construct and estimate a dynamic model of producer drilling and flaring decisions which depend on the current state of the pipeline network and expectations over its evolution.  My model also allows producers to internalize spillover effects for their neighbors -- any pipeline they build will extend the network and weakly decrease their neighbors' future pipeline connection costs.  Using my model estimates, I simulate pipeline development and flaring outcomes under counterfactual policies: a flaring tax, a flaring ban, and a gas subsidy.  My counterfactual simulations show that flaring abatement costs are higher than previous studies but suggest that a flaring tax could substantially reduce flaring.  A $5/Mcf tax reduces flaring by 39%.*

## Policy Options to Reduce State Liabilities from Orphaned Gas Wells

Draft available upon request

*There are hundreds of thousands of aging oil and gas wells scattered throughout the United States that pose serious environmental and safety risks.  These well sites will require billions of dollars of investment in remediation.  When producers go bankrupt before remediation is complete, the responsibility to clean up the site often lands with either the state or federal government.  These wells are known as orphan wells, and have received increasing attention in the scientific and policy literature.  In this paper, I estimate a model of well-level status transitions, then use my model to simulate how a policy requiring producers to either bring wells back into production or plug them after two years of inactivity would affect well orphan rates.  I find that since many wells are left inactive for years at a time, this simple policy would be an effective way to decrease government plugging responsibilities and prevent environmental damage without dramatically reducing oil and gas production.*



{% if author.googlescholar %}
  You can also find my articles on <u><a href="{{author.googlescholar}}">my Google Scholar profile</a>.</u>
{% endif %}

{% include base_path %}

{% for post in site.publications reversed %}
  {% include archive-single.html %}
{% endfor %}
