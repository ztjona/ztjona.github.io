---
layout: page
permalink: /events/
title: Events
description: Talks, mentoring, conferences, and other events I have participated in.
nav: true
nav_order: 4
display_categories: [speaker, mentor, organizer, attendee]
horizontal: false
---

<div class="events">
{% if site.enable_project_categories and page.display_categories %}
  {% for category in page.display_categories %}
  {% assign categorized = site.talks | where: "role", category %}
  {% assign sorted = categorized | sort: "date" | reverse %}
  {% if sorted.size > 0 %}
  <a id="{{ category }}" href=".#{{ category }}">
    <h2 class="category">{{ category }}</h2>
  </a>
  <div class="row row-cols-1 row-cols-md-2">
    {% for talk in sorted %}
      {% include projects.liquid project=talk %}
    {% endfor %}
  </div>
  {% endif %}
  {% endfor %}

{% else %}

{% assign sorted = site.talks | sort: "date" | reverse %}
<div class="row row-cols-1 row-cols-md-2">
  {% for talk in sorted %}
    {% include projects.liquid project=talk %}
  {% endfor %}
</div>

{% endif %}
</div>
