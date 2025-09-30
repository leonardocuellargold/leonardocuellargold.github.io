---
layout: default
title: Blog
permalink: /blog/
---

{% include section-title.html id="blog" title="Blog" subtitle="Thoughts on technology, data, and professional development." %}

<div class="posts-list">
  {% for post in site.posts %}
    <article class="post-preview card">
      <h2><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h2>
      <p class="post-meta small">
        {{ post.date | date: "%B %-d, %Y" }}
        {% if post.author %} • {{ post.author }}{% endif %}
      </p>
      {% if post.excerpt %}
        <p>{{ post.excerpt | strip_html | truncatewords: 30 }}</p>
      {% endif %}
      <p><a href="{{ post.url | relative_url }}" class="read-more">Read more &rarr;</a></p>
    </article>
  {% endfor %}
  
  {% if site.posts.size == 0 %}
    <p class="small muted">No blog posts yet. Check back soon!</p>
  {% endif %}
</div>