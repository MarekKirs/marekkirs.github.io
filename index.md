---
layout: default
title: KirsLab
---

<div class="hero">
  <h1>{{ site.title }}</h1>
  <p class="tagline">{{ site.tagline }}</p>
  <p>{{ site.description }}</p>
</div>

<div class="hero-highlights">
  <div class="highlight-card">
    <h3>Research</h3>
    <p>We study [core question] using [key methods/model systems].</p>
    <a href="{{ '/research/' | relative_url }}">Learn more &rarr;</a>
  </div>
  <div class="highlight-card">
    <h3>Join the lab</h3>
    <p>We're always interested in hearing from motivated students and researchers.</p>
    <a href="{{ '/join/' | relative_url }}">Open positions &rarr;</a>
  </div>
  <div class="highlight-card">
    <h3>Recent news</h3>
    <p>See our latest publications, awards, and lab updates.</p>
    <a href="{{ '/news/' | relative_url }}">Read news &rarr;</a>
  </div>
</div>

## Latest news

{% assign news = site.data.news | sort: "date" | reverse %}
{% for item in news limit: 5 %}
<div class="news-item">
  <div class="news-date">{{ item.date }}</div>
  <strong>{{ item.title }}</strong>
  <p>{{ item.summary }}</p>
</div>
{% endfor %}

<p><a href="{{ '/news/' | relative_url }}">See all news &rarr;</a></p>
