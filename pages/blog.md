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

  <!-- Blog Filters -->
  <div class="blog-filters mb-12 animate-fade-up" style="animation-delay: 0.2s; display:flex; flex-direction:column; align-items:center;">
    <div class="filter-buttons">
      <button class="filter-btn active" data-filter="all">All Posts</button>
      <button class="filter-btn" data-filter="experience">Experience</button>
      <button class="filter-btn" data-filter="consulting">Consulting</button>
      <button class="filter-btn" data-filter="cloud">Cloud</button>
      <button class="filter-btn" data-filter="infrastructure">Infrastructure</button>
      <button class="filter-btn" data-filter="mentorship">Mentorship</button>
    </div>
  </div>

  <!-- Blog Posts -->
  <section class="blog-posts animate-fade-up" style="animation-delay: 0.2s">
    {% assign blog_posts = site.posts | where_exp: "post", "post.categories contains 'blog'" | reverse %}
    {% if blog_posts.size > 0 %}
      {% for post in blog_posts %}
        {% comment %}Build filter tags from post tags{% endcomment %}
        {% assign filter_tags = '' %}
        {% for tag in post.tags %}
          {% assign tag_lower = tag | downcase %}
          {% assign filter_tags = filter_tags | append: tag_lower | append: ' ' %}
        {% endfor %}
        {% if post.categories %}
          {% for cat in post.categories %}
            {% assign cat_lower = cat | downcase %}
            {% assign filter_tags = filter_tags | append: cat_lower | append: ' ' %}
          {% endfor %}
        {% endif %}
        
        <article class="blog-post-card card" data-tags="{{ filter_tags | strip }}">
          <div class="post-meta">
            <time datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: "%B %d, %Y" }}</time>
            {% if post.tags %}
              <div class="post-tags">
                {% for tag in post.tags limit:3 %}
                  <span class="tag">{{ tag }}</span>
                {% endfor %}
              </div>
            {% endif %}
          </div>
          <h2><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h2>
          {% if post.subtitle %}<p class="post-subtitle-preview">{{ post.subtitle }}</p>{% endif %}
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

<!-- Blog Styles -->
<style>
.blog-filters {
  margin-bottom: var(--space-12);
}

.filter-buttons {
  display: flex;
  gap: var(--space-2);
  background: var(--bg-secondary);
  padding: var(--space-1);
  border-radius: var(--radius-xl);
  border: 1px solid var(--border-primary);
  flex-wrap: wrap;
  justify-content: center;
}

.filter-btn {
  padding: var(--space-2) var(--space-4);
  border: none;
  background: transparent;
  color: var(--text-secondary);
  font-size: var(--text-sm);
  font-weight: 500;
  border-radius: var(--radius-lg);
  cursor: pointer;
  transition: all var(--duration-200) var(--ease-out);
  white-space: nowrap;
}

.filter-btn:hover,
.filter-btn.active {
  background: var(--accent);
  color: white;
}

.blog-posts {
  display: flex;
  flex-direction: column;
  gap: var(--space-8);
}

.blog-post-card {
  transition: all var(--duration-300) ease;
}

.blog-post-card.hidden {
  display: none;
}

.post-subtitle-preview {
  font-size: var(--text-lg);
  color: var(--text-secondary);
  margin-bottom: var(--space-3);
  font-weight: 500;
}

@media (max-width: 768px) {
  .filter-buttons {
    gap: var(--space-1);
  }
  
  .filter-btn {
    font-size: var(--text-xs);
    padding: var(--space-1) var(--space-3);
  }
}
</style>

<!-- Blog Filter Script -->
<script>
document.addEventListener('DOMContentLoaded', function() {
  const filterBtns = document.querySelectorAll('.filter-btn');
  const postCards = document.querySelectorAll('.blog-post-card');
  
  filterBtns.forEach(btn => {
    btn.addEventListener('click', function() {
      const filter = this.dataset.filter;
      
      // Update active state
      filterBtns.forEach(b => b.classList.remove('active'));
      this.classList.add('active');
      
      // Filter posts
      postCards.forEach(card => {
        const tags = (card.dataset.tags || '').toLowerCase().split(/\s+/).filter(Boolean);
        const match = filter === 'all' || tags.includes(filter);
        
        if (match) {
          card.classList.remove('hidden');
          card.style.animation = 'fadeInUp 0.5s ease forwards';
        } else {
          card.classList.add('hidden');
        }
      });
    });
  });
});
</script>