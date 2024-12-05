---
title: Readings
layout: page
toc: true
category: collections
tag: resources
description: List of things I have already read, and things that I plan to read.
---

<div class="container">
  <div class="last-update">Last updated {{ site.data.reading.lastupdate }}</div>
  {% for entry in site.data.reading.list %}
  <div class="year-container">
    <div class="year">
      <h4>{{ entry.year }}</h4>
      <div class="number">{{ entry.planning | size }} planning</div>
    </div>
    <div class="planning">
      <ul class="reading-list {{ entry.year }}">
        {% for planning in entry.planning %}
        <li>
          <a href="{{ book.link }}" alt="_blank" rel="nofollow noopener">{{
            planning.title
          }}</a>
          <span class="author">by {{ planning.author }}</span
          >{% if planning.star %}<span class="star">★</span>{% endif %}
        </li>
        {% endfor %}
      </ul>
    </div>
  </div>
  {% endfor %}
</div>