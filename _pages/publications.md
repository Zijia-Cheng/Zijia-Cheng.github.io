---
layout: archive
title: "Publications"
permalink: /publications/
author_profile: true
---

Below is a selected set of papers and research summaries that reflect the main threads of my work:
topological quantum materials, kagome systems, correlated electronic structure, and spectroscopy-driven discovery.
For a broader publication list, please see my <a href="https://scholar.google.com.sg/citations?user=KNUkxEgAAAAJ&hl=en">Google Scholar profile</a>.

## Selected Publications

{% assign selected_talks = site.talks | sort: "date" | reverse %}
{% for post in selected_talks limit:5 %}
  {% include archive-single-talk.html %}
{% endfor %}

## Additional Work

Other publications and collaborations include work on unconventional photocurrents from surface Fermi arcs,
electronic structure in correlated superconductors, and related spectroscopy studies across topological materials.
