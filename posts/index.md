---
layout: homepage
title: Notes & Posts
permalink: /posts/
---

## Notes & Posts

I use this space to stash quick observations, tools I find helpful, and any other bite-sized updates that do not quite fit on the main page.

{% if site.posts and site.posts != empty %}
<div class="posts-list">
  {% for post in site.posts %}
  <article class="post-card">
    <p class="post-card-date">{{ post.date | date: "%b %-d, %Y" }}</p>
    <h3 class="post-card-title"><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h3>
    {% assign summary = post.summary | default: post.description | default: post.excerpt %}
    <p class="post-card-summary">{{ summary | strip_html | truncate: 220 }}</p>
    {% if post.tags %}
    <p class="post-card-tags">
      {% for tag in post.tags %}
      <span>{{ tag }}</span>
      {% endfor %}
    </p>
    {% endif %}
  </article>
  {% endfor %}
</div>
{% else %}
<p>No posts yet — check back soon!</p>
{% endif %}
