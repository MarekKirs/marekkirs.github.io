---
layout: default
title: Contact
permalink: /contact/
---

# Contact

<div class="contact-block">
  <h3>Address</h3>
  <p>{{ site.title }}<br>
  {{ site.department }}<br>
  {{ site.university }}<br>
  {{ site.address }}</p>
</div>

<div class="contact-block">
  <h3>Email</h3>
  <p><a href="mailto:{{ site.email }}">{{ site.email }}</a></p>
</div>

<div class="contact-block">
  <h3>Find us online</h3>
  <p>
    {% if site.twitter_url != "" %}<a href="{{ site.twitter_url }}">Twitter/X</a><br>{% endif %}
    {% if site.github_url != "" %}<a href="{{ site.github_url }}">GitHub</a><br>{% endif %}
    {% if site.scholar_url != "" %}<a href="{{ site.scholar_url }}">Google Scholar</a><br>{% endif %}
    {% if site.linkedin_url != "" %}<a href="{{ site.linkedin_url }}">LinkedIn</a>{% endif %}
  </p>
</div>

<!--
Optional: embed a Google Map by getting an embed iframe from
https://www.google.com/maps and pasting it here.
-->
