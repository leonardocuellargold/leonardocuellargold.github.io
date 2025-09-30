---
layout: default
title: Certifications
permalink: /certifications/
---

{% include section-title.html id="certs" title="Certifications" subtitle="Verified skills and course work." %}
<ul>
{% for c in site.data.certs %}
  <li>
    <strong>{{ c.name }}</strong> — {{ c.org }} ({{ c.year }})
    {% if c.link %} • <a href="{{ c.link }}" target="_blank">Verify</a>{% endif %}
  </li>
{% endfor %}
</ul>
