---
title: "Building Modern Portfolio Sites with Jekyll"
date: 2025-01-15 10:30:00 -0500
author: Leonardo Cuellar
excerpt: "Lessons learned from creating a professional portfolio site using Jekyll, GitHub Pages, and modern CSS techniques."
---

Creating a professional portfolio site is essential for showcasing your work and establishing your online presence. Here's what I learned while building this site using Jekyll and GitHub Pages.

## Why Jekyll?

Jekyll offers the perfect balance of simplicity and power for portfolio sites:

- **Static Site Generation**: Fast loading times and excellent SEO
- **GitHub Pages Integration**: Free hosting with automatic deployment
- **Markdown Support**: Easy content management and writing workflow
- **Liquid Templates**: Powerful templating without complexity

## Design Philosophy

I focused on three core principles:

### 1. Content-First Approach
The design emphasizes readability and showcases work without distractions. Clean typography and generous whitespace let the content breathe.

### 2. Performance Optimization
- Minimal CSS and JavaScript
- Optimized images with lazy loading
- Fast font loading with preconnect
- Mobile-first responsive design

### 3. Accessibility & Usability
- Semantic HTML structure
- Proper color contrast ratios
- Keyboard navigation support
- Screen reader compatibility

## Technical Implementation

### Custom SCSS Architecture
```scss
:root {
  --accent: #ffd6e7;
  --text: #111111;
  --bg: #ffffff;
  /* ... more CSS variables */
}
```

CSS variables enable consistent theming and make dark mode implementation straightforward.

### Dynamic Navigation
Active page detection uses Jekyll's liquid templating:

```liquid
{% assign current = page.url | default: '/' %}
{% if current == item.url %}
  <a class="page-link active" href="{{ item.url }}">
{% else %}
  <a class="page-link" href="{{ item.url }}">
{% endif %}
```

### Project Collections
Jekyll collections organize project content separately from blog posts:

```yaml
collections:
  projects:
    output: true
    permalink: /projects/:name/
```

## Lessons Learned

1. **Start Simple**: Begin with core functionality, then enhance
2. **Mobile First**: Design for mobile devices from the beginning  
3. **Test Early**: Regular testing prevents major issues later
4. **Content Strategy**: Plan your content structure before coding

## Future Enhancements

- Dark mode toggle (currently uses system preference)
- Interactive project galleries with lightbox
- Search functionality for blog posts
- Performance monitoring and analytics

Building a portfolio site is an iterative process. Start with the essentials and enhance over time based on feedback and needs.

What aspects of portfolio development interest you most? Feel free to [reach out](/contact/) with questions or suggestions!