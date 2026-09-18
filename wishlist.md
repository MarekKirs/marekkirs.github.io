---
layout: default
title: Equipment Wishlist
permalink: /wishlist/
---

# Equipment Wishlist

Below is a running list of equipment and supplies that would directly
support our ongoing research. If you'd like to sponsor or donate any
of these items — new, used, or as an in-kind gift — please reach out
to **{{ site.email }}**.

<div class="wishlist-grid">
{% for w in site.data.wishlist %}
  <div class="wishlist-card">
    <div class="wishlist-header">
      <h3>{{ w.item }}</h3>
      {% if w.priority %}<span class="priority-badge priority-{{ w.priority }}">{{ w.priority }}</span>{% endif %}
    </div>
    <p>{{ w.description }}</p>
    <p class="wishlist-cost">{% if w.estimated_cost %}Estimated cost: {{ w.estimated_cost }}{% endif %}</p>
    {% if w.link and w.link != "" %}<p><a href="{{ w.link }}">View item &rarr;</a></p>{% endif %}
  </div>
{% endfor %}
</div>

<p><a href="{{ '/donate/' | relative_url }}">&larr; Back to Donate</a></p>
