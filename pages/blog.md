---
layout: default
title: Blog
permalink: /blog/
---
<br>
<div class="container">
  <!-- Page Header -->
  <section class="section-header animate-fade-up">
    <h1 class="section-title">Blog</h1>
    <p class="section-subtitle">
      Thoughts, insights, and stories from my journey in technology consulting, 
      cloud infrastructure, and professional development.
    </p>
  </section>

  <!-- Blog Posts -->
  <section class="blog-posts animate-fade-up" style="animation-delay: 0.2s">
    {% assign blog_posts = site.posts | where_exp: "post", "post.categories contains 'blog'" %}
    {% if blog_posts.size > 0 %}
      {% for post in blog_posts %}
        <article class="blog-post-card card">
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
  </section>
</div>