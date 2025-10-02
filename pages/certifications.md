---
layout: default
title: Certifications
permalink: /certifications/
---

<div class="container">
  <!-- Page Header -->
  <section class="section-header animate-fade-up">
    <h1 class="section-title">Certifications</h1>
    <p class="section-subtitle">
      Professional certifications and verified skills that demonstrate my commitment to 
      continuous learning and technical excellence across cloud platforms and data technologies.
    </p>
  </section>

  <!-- Certifications Grid -->
  <section class="certifications-grid animate-fade-up" style="animation-delay: 0.2s">
    {% for c in site.data.certs %}
      <div class="certification-card card">
        <h3>{{ c.name }}</h3>
        <p class="cert-org">{{ c.org }}</p>
        <p class="cert-year">{{ c.year }}</p>
        {% if c.link %}
          <a href="{{ c.link }}" target="_blank" class="btn btn-secondary">Verify Certificate</a>
        {% endif %}
      </div>
    {% endfor %}
  </section>
</div>
