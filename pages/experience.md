---
layout: default
title: Experience
permalink: /experience/
---

{% include section-title.html id="experience" title="Experience" subtitle="Roles, internships, leadership." %}
{% for item in site.data.experience %}
  {% include timeline-item.html item=item %}
{% endfor %}
