---
layout: default
title: News
permalink: /news/
---

# News

{% assign news = site.data.news | sort: "date" | reverse %}
{% for item in news %}
<div class="news-item">
  <div class="news-date">{{ item.date | date_to_long_string }}</div>
  <h3>{{ item.title }}</h3>
  <p>{{ item.summary }}</p>
  {% if item.link %}<p><a href="{{ item.link }}">Read more &rarr;</a></p>{% endif %}
</div>
{% endfor %}
