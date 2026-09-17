---
layout: default
title: Team
permalink: /team/
---

# Team

{% assign groups = "pi,postdoc,grad,undergrad,staff" | split: "," %}
{% assign group_titles = "Principal Investigator,Postdoctoral Researchers,Graduate Students,Undergraduate Researchers,Lab Staff" | split: "," %}

{% for group in groups %}
  {% assign members = site.data.people | where: "group", group %}
  {% if members.size > 0 %}
  <h2>{{ group_titles[forloop.index0] }}</h2>
  <div class="people-grid">
    {% for person in members %}
    <div class="person-card">
      {% if person.photo != "" %}
      <img class="person-photo" src="{{ person.photo | relative_url }}" alt="{{ person.name }}">
      {% else %}
      <div class="person-photo"></div>
      {% endif %}
      <h3>{{ person.name }}</h3>
      <p class="person-role">{{ person.role }}</p>
      <p class="person-bio">{{ person.bio }}</p>
      {% if person.email != "" %}<p><a href="mailto:{{ person.email }}">{{ person.email }}</a></p>{% endif %}
      {% if person.website != "" %}<p><a href="{{ person.website }}">Website</a></p>{% endif %}
    </div>
    {% endfor %}
  </div>
  {% endif %}
{% endfor %}

{% assign alumni = site.data.people | where: "group", "alumni" %}
{% if alumni.size > 0 %}
<h2>Alumni</h2>
<ul>
  {% for person in alumni %}
  <li><strong>{{ person.name }}</strong>{% if person.role != "" %} — {{ person.role }}{% endif %}</li>
  {% endfor %}
</ul>
{% endif %}
