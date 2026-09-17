---
layout: default
title: Publications
permalink: /publications/
---

# Publications

{% assign pubs_by_year = site.data.publications | group_by: "year" | sort: "name" | reverse %}
{% for year_group in pubs_by_year %}
<h2 class="pub-year">{{ year_group.name }}</h2>
<ul class="pub-list">
  {% for pub in year_group.items %}
  <li>
    <div class="pub-title">{{ pub.title }}</div>
    <div class="pub-authors">{{ pub.authors }}</div>
    <div class="pub-venue">{{ pub.venue }}</div>
    <div class="pub-links">
      {% if pub.pdf_url != "" %}<a href="{{ pub.pdf_url }}">PDF</a>{% endif %}
      {% if pub.doi_url != "" %}<a href="{{ pub.doi_url }}">DOI</a>{% endif %}
    </div>
  </li>
  {% endfor %}
</ul>
{% endfor %}
