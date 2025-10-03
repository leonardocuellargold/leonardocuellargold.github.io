---
layout: default
title: Projects
permalink: /projects/
---
<br>

<div class="container">
  <!-- Page Header -->
  <section class="section-header animate-fade-up">
    <h1 class="section-title">Featured Projects</h1>
    <p class="section-subtitle">
      A comprehensive showcase of innovative solutions spanning cloud infrastructure, 
      data analytics, automation, and strategic consulting. Each project demonstrates 
      real-world impact through cutting-edge technology and strategic thinking.
    </p>
  </section>

  <!-- Project Categories Filter -->
  <div class="project-categories mb-12 animate-fade-up" style="animation-delay: 0.2s">
    <div class="category-filters">
      <button class="category-filter active" data-category="all">All Projects</button>
      <button class="category-filter" data-category="cloud">Cloud Infrastructure</button>
      <button class="category-filter" data-category="data">Data Analytics</button>
      <button class="category-filter" data-category="automation">Automation</button>
      <button class="category-filter" data-category="mobile">Mobile Development</button>
    </div>
  </div>

  <!-- Projects Grid -->
  <div class="project-grid">
    {% for p in site.data.projects %}
      {% assign project_slug = p.name | slugify %}
      {% assign project_post = site.projects | where: "slug", project_slug | first %}
      
      <article class="project-card card-interactive hover-lift animate-fade-up" 
               style="animation-delay: {{ forloop.index | times: 0.1 }}s"
               data-category="{% if p.stack contains 'Go' or p.stack contains 'Power Automate' %}automation{% elsif p.stack contains 'R' %}data{% elsif p.stack contains 'React Native' %}mobile{% else %}cloud{% endif %}">
        
        <!-- Project Image -->
        <div class="project-image-container">
          {% if project_post and project_post.featured_image %}
            <img src="{{ project_post.featured_image }}" alt="{{ p.name }}" class="project-image">
          {% else %}
            <div class="project-image placeholder-image">
              <div class="placeholder-content">
                <svg width="48" height="48" viewBox="0 0 24 24" fill="currentColor" opacity="0.5">
                  <path d="M12 2l3.09 6.26L22 9.27l-5 4.87 1.18 6.88L12 17.77l-6.18 3.25L7 14.14 2 9.27l6.91-1.01L12 2z"/>
                </svg>
                <span>{{ p.name | truncatewords: 2 }}</span>
              </div>
            </div>
          {% endif %}
          
          <!-- Project Status Badge -->
          {% if p.status %}
            <div class="project-status badge-{{ p.status }}">{{ p.status | capitalize }}</div>
          {% else %}
            <div class="project-status badge-success">Completed</div>
          {% endif %}
        </div>
        
        <!-- Project Content -->
        <div class="project-content">
          <div class="project-header-section">
            <h3 class="project-title">{{ p.name }}</h3>
            {% if project_post and project_post.subtitle %}
              <p class="project-subtitle">{{ project_post.subtitle }}</p>
            {% endif %}
          </div>
          
          <p class="project-description">{{ p.summary }}</p>
          
          <!-- Technology Stack -->
          <div class="project-tech">
            {% for tech in p.stack %}
              <span class="badge">{{ tech }}</span>
            {% endfor %}
          </div>
          
          <!-- Project Links -->
          <div class="project-links">
            {% if project_post %}
              <a href="{{ project_post.url | relative_url }}" class="btn btn-primary">
                <svg width="16" height="16" viewBox="0 0 24 24" fill="currentColor">
                  <path d="M14,3V5H17.59L7.76,14.83L9.17,16.24L19,6.41V10H21V3M19,19H5V5H12V3H5C3.89,3 3,3.9 3,5V19A2,2 0 0,0 5,21H19A2,2 0 0,0 21,19V12H19V19Z"/>
                </svg>
                Case Study
              </a>
            {% endif %}
            
            {% if p.github %}
              <a href="{{ p.github }}" target="_blank" class="btn btn-secondary">
                <svg width="16" height="16" viewBox="0 0 24 24" fill="currentColor">
                  <path d="M12,2A10,10 0 0,0 2,12C2,16.42 4.87,20.17 8.84,21.5C9.34,21.58 9.5,21.27 9.5,21C9.5,20.77 9.5,20.14 9.5,19.31C6.73,19.91 6.14,17.97 6.14,17.97C5.68,16.81 5.03,16.5 5.03,16.5C4.12,15.88 5.1,15.9 5.1,15.9C6.1,15.97 6.63,16.93 6.63,16.93C7.5,18.45 8.97,18 9.54,17.76C9.63,17.11 9.89,16.67 10.17,16.42C7.95,16.17 5.62,15.31 5.62,11.5C5.62,10.39 6,9.5 6.65,8.79C6.55,8.54 6.2,7.5 6.75,6.15C6.75,6.15 7.59,5.88 9.5,7.17C10.29,6.95 11.15,6.84 12,6.84C12.85,6.84 13.71,6.95 14.5,7.17C16.41,5.88 17.25,6.15 17.25,6.15C17.8,7.5 17.45,8.54 17.35,8.79C18,9.5 18.38,10.39 18.38,11.5C18.38,15.32 16.04,16.16 13.81,16.41C14.17,16.72 14.5,17.33 14.5,18.26C14.5,19.6 14.5,20.68 14.5,21C14.5,21.27 14.66,21.59 15.17,21.5C19.14,20.16 22,16.42 22,12A10,10 0 0,0 12,2Z"/>
                </svg>
                GitHub
              </a>
            {% endif %}
            
            {% if p.link %}
              <a href="{{ p.link }}" target="_blank" class="btn btn-ghost">
                <svg width="16" height="16" viewBox="0 0 24 24" fill="currentColor">
                  <path d="M14,3V5H17.59L7.76,14.83L9.17,16.24L19,6.41V10H21V3M19,19H5V5H12V3H5C3.89,3 3,3.9 3,5V19A2,2 0 0,0 5,21H19A2,2 0 0,0 21,19V12H19V19Z"/>
                </svg>
                Live Demo
              </a>
            {% endif %}
          </div>
        </div>
      </article>
    {% endfor %}
  </div>
  
  <!-- Call to Action -->
  <section class="cta-section text-center mt-20 animate-fade-up">
    <div class="card" style="max-width: 600px; margin: 0 auto;">
      <h3>Interested in Collaboration?</h3>
      <p class="text-secondary mb-6">
        I'm always excited to work on innovative projects that create real impact. 
        Let's discuss how we can bring your ideas to life.
      </p>
      <div class="flex gap-4 justify-center">
        <a href="/contact/" class="btn btn-primary">Start a Conversation</a>
        <a href="/about/" class="btn btn-secondary">Learn More About Me</a>
      </div>
    </div>
  </section>
</div>

<!-- Enhanced Project Styles -->
<style>
.project-categories {
  display: flex;
  justify-content: center;
  margin-bottom: var(--space-12);
}

.category-filters {
  display: flex;
  gap: var(--space-2);
  background: var(--bg-secondary);
  padding: var(--space-1);
  border-radius: var(--radius-xl);
  border: 1px solid var(--border-primary);
}

.category-filter {
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

.category-filter:hover,
.category-filter.active {
  background: var(--primary-500);
  color: white;
}

.project-image-container {
  position: relative;
  overflow: hidden;
  border-radius: var(--radius-xl) var(--radius-xl) 0 0;
  height: 200px;
}

.placeholder-image {
  display: flex;
  align-items: center;
  justify-content: center;
  height: 100%;
  background: linear-gradient(135deg, var(--primary-50), var(--primary-100));
  color: var(--primary-600);
}

.placeholder-content {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: var(--space-2);
  font-weight: 600;
  font-size: var(--text-sm);
}

.project-status {
  position: absolute;
  top: var(--space-3);
  right: var(--space-3);
  padding: var(--space-1) var(--space-2);
  font-size: var(--text-xs);
  font-weight: 600;
  border-radius: var(--radius-full);
}

.badge-completed {
  background: #dcfce7;
  color: #166534;
}

.badge-in-progress {
  background: #fef3c7;
  color: #92400e;
}

.badge-planning {
  background: #dbeafe;
  color: #1e40af;
}

.badge-on-hold {
  background: #f3f4f6;
  color: #4b5563;
}

.badge-archived {
  background: #f9fafb;
  color: #6b7280;
}

/* Legacy support */
.badge-success {
  background: #dcfce7;
  color: #166534;
}

.badge-warning {
  background: #fef3c7;
  color: #92400e;
}

.project-header-section {
  margin-bottom: var(--space-3);
}

.project-subtitle {
  font-size: var(--text-sm);
  color: var(--text-secondary);
  margin: var(--space-1) 0 0 0;
}

.cta-section {
  margin-top: var(--space-20);
}

@media (max-width: 768px) {
  .category-filters {
    flex-wrap: wrap;
    justify-content: center;
  }
  
  .project-links {
    flex-direction: column;
  }
  
  .project-links .btn {
    justify-content: center;
  }
}
</style>

<!-- Project Filter JavaScript -->
<script>
document.addEventListener('DOMContentLoaded', function() {
  const filterButtons = document.querySelectorAll('.category-filter');
  const projectCards = document.querySelectorAll('.project-card');
  
  filterButtons.forEach(button => {
    button.addEventListener('click', function() {
      const targetCategory = this.dataset.category;
      
      // Update active filter button
      filterButtons.forEach(btn => btn.classList.remove('active'));
      this.classList.add('active');
      
      // Filter project cards
      projectCards.forEach(card => {
        const cardCategory = card.dataset.category;
        
        if (targetCategory === 'all' || cardCategory === targetCategory) {
          card.style.display = 'block';
          card.style.animation = 'fadeInUp 0.6s ease forwards';
        } else {
          card.style.display = 'none';
        }
      });
    });
  });
});
</script>
