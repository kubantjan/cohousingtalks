---
layout: page
title: Zapojené cohousingy
permalink: /zapojene-cohousingy/
---

![Zapojené cohousingy]({{ site.baseurl }}/assets/images/zapojene-1024x675.png)

## Aktivní komunity

<div class="community-list">
{% assign active = site.data.communities | where: "status", "active" %}
{% for c in active %}
{% if c.slug %}
<a href="{{ site.baseurl }}/{{ c.slug }}/" class="community-card">
  <h3>{{ c.name }}</h3>
  <p class="location">{{ c.location }}</p>
</a>
{% else %}
<div class="community-card">
  <h3>{{ c.name }}</h3>
  <p class="location">{{ c.location }}</p>
  <p class="no-page">bez vlastní stránky</p>
</div>
{% endif %}
{% endfor %}
</div>

## Vzpomínáme

<div class="community-list memorial">
{% assign memorial = site.data.communities | where: "status", "memorial" %}
{% for c in memorial %}
{% if c.slug %}
<a href="{{ site.baseurl }}/{{ c.slug }}/" class="community-card">
  <h3>{{ c.name }}</h3>
  <p class="location">{{ c.location }}</p>
</a>
{% else %}
<div class="community-card">
  <h3>{{ c.name }}</h3>
  <p class="location">{{ c.location }}</p>
  <p class="no-page">bez vlastní stránky</p>
</div>
{% endif %}
{% endfor %}
</div>
