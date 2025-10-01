---
layout: default
title: Blog
permalink: /blog/
---

<div class="hero">
  <div class="hero-content">
    <h1 class="hero-title">{{ page.title }}</h1>
    <p class="hero-subtitle">Thoughts, insights, and stories from my journey in technology</p>
  </div>
</div>

<div class="container">
  <div class="blog-posts">
    {% assign blog_posts = site.posts | where_exp: "post", "post.categories contains 'blog'" %}
    {% if blog_posts.size > 0 %}
      {% for post in blog_posts %}
        <article class="blog-post-card">
          <div class="post-meta">
            <time datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: "%B %d, %Y" }}</time>
            {% if post.tags %}
              <div class="post-tags">
                {% for tag in post.tags %}
                  <span class="tag">{{ tag }}</span>
                {% endfor %}
              </div>
            {% endif %}
          </div>
          <h2><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h2>
          <p class="post-excerpt">{{ post.excerpt | strip_html | truncate: 200 }}</p>
          <a href="{{ post.url | relative_url }}" class="btn btn-secondary">Read More</a>
        </article>
      {% endfor %}
    {% else %}
      <div class="empty-state">
        <h3>No blog posts yet</h3>
        <p>Check back soon for thoughts, insights, and stories from my journey in technology.</p>
      </div>
    {% endif %}
  </div>
</div>

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