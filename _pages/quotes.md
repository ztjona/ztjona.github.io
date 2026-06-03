---
layout: page
permalink: /quotes/
title: Quotes
description: Phrases that made me stop and think.
nav: true
nav_order: 7
---

<div class="quotes">
  {% assign sorted_quotes = site.data.quotes | sort: "date" | reverse %}
  {% for quote in sorted_quotes %}
  <div class="quote-entry mb-4">
    <blockquote class="blockquote">
      <p>{{ quote.text }}</p>
      <footer class="blockquote-footer">
        {{ quote.author }}
        {% if quote.source and quote.source != "" %}
          , <cite>{{ quote.source }}</cite>
        {% endif %}
      </footer>
    </blockquote>
  </div>
  {% endfor %}
</div>
