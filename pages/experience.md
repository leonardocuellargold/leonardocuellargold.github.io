---
layout: default
title: Experience
permalink: /experience/
---
<br>

<div class="container">
  <!-- Page Header -->
  <section class="section-header animate-fade-up">
    <h1 class="section-title">Professional Experience</h1>
    <p class="section-subtitle">
      Building expertise through hands-on experience at leading technology companies, 
      impactful organizations, and innovative projects that drive real business results.
    </p>
  </section>

  <!-- Experience Stats -->
  <div class="stats-grid mb-16 animate-fade-up" style="animation-delay: 0.2s">
    <div class="stat-card">
      <span class="stat-number">3+</span>
      <span class="stat-label">Years Experience</span>
    </div>
    <div class="stat-card">
      <span class="stat-number">15+</span>
      <span class="stat-label">Projects Delivered</span>
    </div>
    <div class="stat-card">
      <span class="stat-number">5+</span>
      <span class="stat-label">Technologies Mastered</span>
    </div>
    <div class="stat-card">
      <span class="stat-number">100%</span>
      <span class="stat-label">Client Satisfaction</span>
    </div>
  </div>

  <!-- Professional Timeline -->
  <section class="timeline animate-fade-up" style="animation-delay: 0.4s">
    {% for item in site.data.experience %}
      {% include timeline-item.html item=item %}
    {% endfor %}
  </section>

  <!-- Skills & Technologies -->
  <section class="skills-section mt-20 animate-fade-up" style="animation-delay: 0.6s">
    <div class="section-header">
      <h2 class="section-title">Technical Expertise</h2>
      <p class="section-subtitle">
        Proficient in modern technologies and frameworks across cloud platforms, 
        data analytics, and full-stack development.
      </p>
    </div>

    <div class="skills-grid">
      <div class="skill-category card">
        <h3 class="skill-category-title">
          <svg width="24" height="24" viewBox="0 0 24 24" fill="currentColor" class="skill-icon">
            <path d="M12,1L21,5V9C21,16 16.5,21.78 12,23C7.5,21.78 3,16 3,9V5L12,1M12,7C10.89,7 10,7.89 10,9A2,2 0 0,0 12,11A2,2 0 0,0 14,9C14,7.89 13.1,7 12,7Z"/>
          </svg>
          Cloud Infrastructure
        </h3>
        <div class="skill-tags">
          <span class="badge badge-info">Google Cloud Platform</span>
          <span class="badge badge-info">Microsoft Azure</span>
          <span class="badge badge-info">AWS</span>
          <span class="badge badge-info">Docker</span>
          <span class="badge badge-info">Kubernetes</span>
        </div>
      </div>

      <div class="skill-category card">
        <h3 class="skill-category-title">
          <svg width="24" height="24" viewBox="0 0 24 24" fill="currentColor" class="skill-icon">
            <path d="M5,3H7V5H5V10A2,2 0 0,1 3,8V6A2,2 0 0,1 5,4V3M19,3V4A2,2 0 0,1 21,6V8A2,2 0 0,1 19,10V5H17V3H19M16,4H8V6H16V4M16,7H8V9H16V7M16,10H8V12H16V10M19,13V14A2,2 0 0,1 21,16V18A2,2 0 0,1 19,20V21H17V19H19V14H17V13H19M5,13H7V14H5V19H7V21H5V20A2,2 0 0,1 3,18V16A2,2 0 0,1 5,14V13M8,15H16V17H8V15M8,18H16V20H8V18Z"/>
          </svg>
          Data Analytics
        </h3>
        <div class="skill-tags">
          <span class="badge badge-success">Python</span>
          <span class="badge badge-success">R</span>
          <span class="badge badge-success">SQL</span>
          <span class="badge badge-success">Power BI</span>
          <span class="badge badge-success">Tableau</span>
        </div>
      </div>

      <div class="skill-category card">
        <h3 class="skill-category-title">
          <svg width="24" height="24" viewBox="0 0 24 24" fill="currentColor" class="skill-icon">
            <path d="M12,16A3,3 0 0,1 9,13C9,11.88 9.61,10.9 10.5,10.39L20.21,4.77L14.68,14.35C14.18,15.33 13.17,16 12,16M12,3C13.81,3 15.5,3.5 16.97,4.32L14.87,5.53C14,5.19 13,5 12,5A8,8 0 0,0 4,13C4,15.21 4.89,17.21 6.34,18.65H6.35C6.74,19.04 6.74,19.67 6.35,20.06C5.96,20.45 5.33,20.45 4.94,20.06C3.1,18.22 2,15.72 2,13A10,10 0 0,1 12,3M22,13C22,15.72 20.9,18.22 19.06,20.06C18.67,20.45 18.04,20.45 17.65,20.06C17.26,19.67 17.26,19.04 17.65,18.65C19.11,17.21 20,15.21 20,13C20,12 19.81,11 19.47,10.13L20.68,8.03C21.5,9.5 22,11.19 22,13Z"/>
          </svg>
          Development
        </h3>
        <div class="skill-tags">
          <span class="badge badge-warning">React Native</span>
          <span class="badge badge-warning">Go</span>
          <span class="badge badge-warning">JavaScript</span>
          <span class="badge badge-warning">Node.js</span>
          <span class="badge badge-warning">Git</span>
        </div>
      </div>

      <div class="skill-category card">
        <h3 class="skill-category-title">
          <svg width="24" height="24" viewBox="0 0 24 24" fill="currentColor" class="skill-icon">
            <path d="M17,14H19V17H22V19H19V22H17V19H14V17H17V14M5,3H19A2,2 0 0,1 21,5V12.8C20.39,12.45 19.72,12.2 19,12.08V5H5V19H12.08C12.2,19.72 12.45,20.39 12.8,21H5A2,2 0 0,1 3,19V5A2,2 0 0,1 5,3M7,7H17V9H7V7M7,11H17V12.08C16.15,12.22 15.37,12.54 14.69,13H7V11M7,15H12.08C12.03,15.33 12,15.66 12,16H7V15Z"/>
          </svg>
          Business Tools
        </h3>
        <div class="skill-tags">
          <span class="badge">Power Automate</span>
          <span class="badge">Optimy</span>
          <span class="badge">Firebase</span>
          <span class="badge">Expo</span>
          <span class="badge">Jekyll</span>
        </div>
      </div>
    </div>
  </section>

  <!-- Call to Action -->
  <section class="cta-section text-center mt-20 animate-fade-up">
    <div class="card" style="max-width: 600px; margin: 0 auto;">
      <h3>Ready to Collaborate?</h3>
      <p class="text-secondary mb-6">
        I bring a unique combination of technical expertise and strategic thinking 
        to every project. Let's discuss how we can work together.
      </p>
      <div class="flex gap-4 justify-center">
        <a href="/contact/" class="btn btn-primary">Get In Touch</a>
        <a href="/projects/" class="btn btn-secondary">View My Work</a>
      </div>
    </div>
  </section>
</div>

<!-- Enhanced Experience Styles -->
<style>
.skills-section {
  margin-top: var(--space-20);
}

.skills-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: var(--space-6);
  margin-top: var(--space-8);
}

.skill-category {
  padding: var(--space-6);
}

.skill-category-title {
  display: flex;
  align-items: center;
  gap: var(--space-3);
  font-size: var(--text-xl);
  font-weight: 600;
  margin-bottom: var(--space-4);
  color: var(--text-primary);
}

.skill-icon {
  color: var(--primary-500);
}

.skill-tags {
  display: flex;
  flex-wrap: wrap;
  gap: var(--space-2);
}

@media (max-width: 768px) {
  .skills-grid {
    grid-template-columns: 1fr;
  }
}
</style>
