---
layout: default
title: Home
---

<!-- Hero Section -->
<section class="hero">
  <div class="container">
    <div class="hero-content animate-fade-up">
      <h1 class="hero-title">Leonardo Cuellar</h1>
      <p class="hero-subtitle">Transforming ideas into scalable solutions at the intersection of <strong>cloud infrastructure</strong>, <strong>data analytics</strong>, and <strong>strategic consulting</strong>.</p>
      
      <div class="hero-actions">
        <a href="#featured-work" class="btn btn-primary">View My Work</a>
        <a href="/contact/" class="btn btn-secondary">Get In Touch</a>
      </div>
      
      <!-- Stats Section -->
      <div class="stats-grid mt-16">
        <div class="stat-card animate-fade-up" style="animation-delay: 0.1s">
          <span class="stat-number">2+</span>
          <span class="stat-label">Years Experience</span>
        </div>
        <div class="stat-card animate-fade-up" style="animation-delay: 0.2s">
          <span class="stat-number">10+</span>
          <span class="stat-label">Projects Delivered</span>
        </div>
        <div class="stat-card animate-fade-up" style="animation-delay: 0.3s">
          <span class="stat-number">5+</span>
          <span class="stat-label">Certifications</span>
        </div>
        <div class="stat-card animate-fade-up" style="animation-delay: 0.4s">
          <span class="stat-number">8+</span>
          <span class="stat-label">Industries Served</span>
        </div>
      </div>
    </div>
  </div>
</section>

<div class="container">
  <div class="divider-section"></div>
  
  <!-- Featured Work Section -->
  <section id="featured-work" class="mb-20">
    <div class="section-header">
      <h2 class="section-title">Featured Projects</h2>
      <p class="section-subtitle">A showcase of innovative solutions that drive real business impact through cutting-edge technology and strategic thinking.</p>
    </div>
    
    <div class="project-grid">
      {% assign featured = site.data.projects | slice: 0, 3 %}
      {% for p in featured %}
        {% assign project_slug = p.name | slugify %}
        {% assign project_post = site.projects | where: "slug", project_slug | first %}
        
        <article class="project-card card-interactive hover-lift animate-fade-up" style="animation-delay: {{ forloop.index | times: 0.1 }}s">
          {% if project_post and project_post.featured_image %}
            <img src="{{ project_post.featured_image }}" alt="{{ p.name }}" class="project-image">
          {% else %}
            <div class="project-image" style="background: linear-gradient(135deg, var(--primary-100), var(--primary-200)); display: flex; align-items: center; justify-content: center; color: var(--primary-600); font-weight: 600;">{{ p.name | truncatewords: 2 }}</div>
          {% endif %}
          
          <div class="project-content">
            <h3 class="project-title">{{ p.name }}</h3>
            <p class="project-description">{{ p.summary }}</p>
            
            <div class="project-tech">
              {% for tech in p.stack %}
                <span class="badge">{{ tech }}</span>
              {% endfor %}
            </div>
            
            <div class="project-links">
              {% if project_post %}<a href="{{ project_post.url | relative_url }}" class="project-link">Case Study</a>{% endif %}
              {% if p.github %}<a href="{{ p.github }}" target="_blank" class="project-link">GitHub</a>{% endif %}
              {% if p.link %}<a href="{{ p.link }}" target="_blank" class="project-link">Live Demo</a>{% endif %}
            </div>
          </div>
        </article>
      {% endfor %}
    </div>
    
    <div class="text-center mt-12">
      <a href="/projects/" class="btn btn-secondary">View All Projects</a>
    </div>
  </section>
  
  <div class="divider-section"></div>
  
  <!-- Experience Highlights -->
  <section class="mb-20">
    <div class="section-header">
      <h2 class="section-title">Professional Journey</h2>
      <p class="section-subtitle">Building expertise through hands-on experience at leading technology companies and impactful organizations.</p>
    </div>
    
    <div class="timeline animate-fade-up">
      {% for item in site.data.experience limit: 3 %}
        {% include timeline-item.html item=item %}
      {% endfor %}
    </div>
    
    <div class="text-center mt-12">
      <a href="/experience/" class="btn btn-secondary">View Full Experience</a>
    </div>
  </section>
  
  <div class="divider-section"></div>
  
  <!-- Certifications & Skills -->
  <section class="mb-20">
    <div class="section-header">
      <h2 class="section-title">Certifications & Expertise</h2>
      <p class="section-subtitle">Validated skills and continuous learning in cloud technologies, data analytics, and enterprise solutions.</p>
    </div>
    
    <div class="grid grid-2 mb-12">
      <div class="card animate-slide-left">
        <h3>Cloud Platforms</h3>
        <div class="flex flex-col gap-3 mt-4">
          <div class="badge badge-info">Google Cloud Associate Engineer</div>
          <div class="badge badge-info">Microsoft Azure Fundamentals</div>
          <div class="badge badge-info">AWS Cloud Practitioner</div>
        </div>
      </div>
      
      <div class="card animate-slide-left" style="animation-delay: 0.2s">
        <h3>Data & Analytics</h3>
        <div class="flex flex-col gap-3 mt-4">
          <div class="badge badge-success">IBM Data Analyst Professional</div>
          <div class="badge badge-success">Power BI Data Analyst</div>
          <div class="badge badge-success">Tableau Desktop Specialist</div>
        </div>
      </div>
    </div>
    
    <div class="text-center">
      <a href="/certifications/" class="btn btn-secondary">View All Certifications</a>
    </div>
  </section>
</div>
