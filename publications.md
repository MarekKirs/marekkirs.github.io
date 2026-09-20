---
layout: default
title: Publications
permalink: /publications/
---

# Publications

{% assign pubs_by_group = site.data.publications | group_by: "group" | sort: "name" | reverse %}
{% for group in pubs_by_group %}
<h2 class="pub-year">{{ group.name }}</h2>
<ul class="pub-list">
  {% for pub in group.items %}
  <li>
    <div class="pub-title">{{ pub.title }}</div>
    <div class="pub-authors">{{ pub.authors }}</div>
    <div class="pub-venue">{{ pub.venue }}</div>
    <div class="pub-links">
      {% if pub.pdf_url != "" %}<a href="{{ pub.pdf_url }}">PDF</a>{% endif %}
      {% if pub.doi_url != "" %}<a href="https://doi.org/{{ pub.doi_url }}">DOI</a>{% endif %}
    </div>
  </li>
  {% endfor %}
</ul>
{% endfor %}
