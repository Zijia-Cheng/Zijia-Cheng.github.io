---
layout: archive
title: "Publications"
permalink: /publications/
author_profile: false
---

This page highlights selected publications and research summaries available on this site.
For a more complete list, please see my <a href="https://scholar.google.com.sg/citations?user=KNUkxEgAAAAJ&hl=en">Google Scholar profile</a>.

## Selected Publications

{% assign selected_talks = site.talks | sort: "date" | reverse %}
{% for post in selected_talks limit:5 %}
  {% include archive-single-talk.html %}
{% endfor %}
