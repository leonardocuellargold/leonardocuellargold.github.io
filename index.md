---
layout: default
title: Home
---

{% include section-title.html id="intro" title="Hi, I'm Leonardo" subtitle="MIS & Accounting • Cloud • Data • Consulting" %}

I build practical solutions at the intersection of **cloud**, **data**, and **automation**. Below are highlights. See full sections via the top nav.

### Featured Projects
<div class="grid">
  {% assign featured = site.data.projects | slice: 0, 3 %}
  {% for p in featured %}
    {% include project-card.html project=p %}
  {% endfor %}
</div>

### Recent Experience
{% for item in site.data.experience %}
  {% include timeline-item.html item=item %}
{% endfor %}

### Certifications
{% for c in site.data.certs %}
  <span class="badge">{{ c.name }}</span>
{% endfor %}
