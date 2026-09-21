---
layout: default
title: Data
permalink: /data/
---

# Data & Code

In support of open science, we share raw data and analysis code for
our published work below where available. If a dataset isn't listed
or the link is missing, please reach out to **{{ site.email }}** —
we're happy to share data on request.

<div class="dataset-list">
{% for d in site.data.datasets %}
  <div class="dataset-card">
    <h3>{{ d.title }}</h3>
    <p class="pub-authors">{{ d.authors }}</p>
    <p class="pub-venue">{{ d.venue }}</p>
    <div class="dataset-links">
      {% if d.doi_url and d.doi_url != "" %}<a href="https://doi.org/{{ d.doi_url }}">Paper (DOI)</a>{% endif %}
      {% if d.repo_url and d.repo_url != "" %}<a href="{{ d.repo_url }}">Code repository (GitHub)</a>{% endif %}
      {% if d.raw_data_file and d.raw_data_file != "" %}<a href="{{ d.raw_data_file | relative_url }}">Raw data (XLSX)</a>{% endif %}
      {% if d.code_file and d.code_file != "" %}<a href="{{ d.code_file | relative_url }}">Analysis code (TXT)</a>{% endif %}
    </div>
    {% if d.notes and d.notes != "" %}<p class="dataset-notes">{{ d.notes }}</p>{% endif %}
  </div>
{% endfor %}
</div>
