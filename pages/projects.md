---
layout: default
title: Projects
permalink: /projects/
---

{% include section-title.html id="projects" title="Projects" subtitle="Case studies and code." %}
<div class="grid">
  {% for p in site.data.projects %}
    {% include project-card.html project=p %}
  {% endfor %}
</div>
