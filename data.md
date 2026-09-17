---
layout: default
title: Data
permalink: /data/
---

# News

{% assign news = site.data.news | sort: "date" | reverse %}
{% for item in news %}
<div class="news-item">
  <div class="news-date">{{ item.date | date_to_long_string }}</div>
  <h3>{{ Manuscript name }}</h3>
  <p>{{ file1, file 2 }}</p>
</div>
{% endfor %}
