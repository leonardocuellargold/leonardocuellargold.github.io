# Leonardo Cuellar - Professional Portfolio

A sophisticated, FAANG-grade portfolio website showcasing expertise in cloud infrastructure, data analytics, and strategic consulting. Built with Jekyll, featuring advanced design patterns, comprehensive project showcases, and professional presentation optimized for GitHub Pages deployment.

## ✨ Key Features

- **Professional Design System**: Charcoal & Coral color scheme with comprehensive CSS architecture
- **Interactive Project Showcase**: Functional filtering, detailed case studies with galleries
- **Rich Content Architecture**: Blog posts, project collections, experience timeline
- **Performance Optimized**: Critical CSS loading, font optimization, compressed assets  
- **SEO Enhanced**: Structured data, Open Graph tags, optimized meta information
- **Fully Responsive**: Mobile-first design with seamless cross-device experience
- **Accessibility Focused**: WCAG AA compliant with proper semantic markup and keyboard navigation

## 🎨 Design System & Color Scheme

### Color Palette
- **Primary**: #1C1C1E (Charcoal Black) - Headers, navigation, main text
- **Secondary**: #2C2C54 (Dark Indigo) - Section backgrounds, cards
- **Accent**: #FF6B6B (Coral Red) - Buttons, links, highlights, CTAs
- **Background**: #FAFAFA (Soft White) - Main background, clean canvas
- **Text**: #2E2E2E (Neutral Gray) - Body text, readable contrast

### Usage Guidelines
- **Headers/Navigation**: Use primary (#1C1C1E) for maximum readability
- **Section Backgrounds**: Apply secondary (#2C2C54) for visual hierarchy
- **Interactive Elements**: Accent (#FF6B6B) for buttons, links, and call-to-actions
- **Contrast**: All combinations meet WCAG AA standards (aim for AAA when possible)

## 🏗️ Architecture Overview

### File Structure
```
├── _config.yml           # Main Jekyll configuration + navigation
├── _layouts/             # Page templates (base, default, post, project)
├── _includes/            # Reusable components (header, footer, cards, etc.)
├── _data/                # Content data files (projects, experience, certifications)
├── _posts/               # Blog post content with front matter
├── _projects/            # Project case study pages with galleries
├── pages/                # Static pages (about, contact, projects, experience)
├── assets/main.scss      # Complete design system with new color scheme
├── assets/img/           # Image assets organized by type/project
└── README.md             # This comprehensive maintenance guide
```

## 🎯 Content Management & Maintenance

### Adding/Updating Projects
1. **Data Entry**: Update `_data/projects.yml` with project information:
   ```yaml
   - name: "Project Name"
     description: "Brief description for cards and SEO"
     stack: ["Technology", "Stack", "Used"]
     github: "https://github.com/username/repo"
     demo: "https://live-demo-url.com"
     featured: true
   ```

2. **Case Study Creation**: Create detailed page in `_projects/project-name.md`:
   ```markdown
   ---
   layout: project
   title: "Project Name"
   slug: project-name
   stack: ["React", "Node.js", "AWS"]
   featured_image: "/assets/img/projects/project-name/hero.jpg"
   gallery: ["image1.jpg", "image2.jpg", "image3.jpg"]
   ---
   Detailed project description, challenges, solutions...
   ```

3. **Images**: Add project images to `assets/img/projects/`
   - **Naming Convention**: Use project slug + descriptor
     - **Featured images** (for cards): `[project-slug]-hero.jpg`
     - **Project page hero** (optional): `[project-slug]-detail-hero.jpg`
     - **Gallery images**: `[project-slug]-1.jpg`, `[project-slug]-2.jpg`, etc.
   - **Image Specifications**: 
     - **Featured Images**: 1200x600px (2:1 ratio) - Used in project cards and listings
     - **Project Hero Images**: 1920x800px (2.4:1 ratio) - Background for project page header with overlay
     - **Gallery Images**: 800x600px (4:3 ratio) - Screenshots and additional visuals
     - **Format**: JPG for photos, PNG for screenshots with transparency
     - **Size**: Under 500KB for hero images, 300KB for others (optimized for web)
     - **Hero Image Guidelines**: High contrast, good focal point, works well with dark overlay
   - **Image Usage in Frontmatter**:
     ```yaml
     featured_image: /assets/img/projects/project-slug-hero.jpg      # For cards/listings
     hero_image: /assets/img/projects/project-slug-detail-hero.jpg   # Background header with overlay
     ```
   - **Hero Background Effects**:
     - Automatic dark gradient overlay (85% opacity)
     - Backdrop blur effect (2px)
     - White text with shadow for readability
     - Responsive height (400px desktop, 300px mobile)

#### � **Papers & Resources Integration**

Add research papers and external resources to enrich your project presentations.

**Research Papers**:
```yaml
# Simple paper link
paper: https://example.com/paper.pdf

# Enhanced paper with metadata
paper: https://example.com/paper.pdf
paper_title: "Custom Paper Title"
paper_description: "Brief description of the research and findings"
```

**Resources & External Links**:
```yaml
# Simple key-value format (legacy support)
resources:
  - Resource Name: https://example.com
  - Another Resource: https://example2.com

# Enhanced format with descriptions
resources:
  - name: "Resource Name"
    url: "https://example.com"
    description: "Brief description of what this resource provides"
  - name: "Another Resource"
    url: "https://example2.com"
    description: "Another helpful description"
```

**Features**:
- Papers display as prominent cards with custom titles and descriptions
- Resources appear as grid of linked cards with icons
- Both sections are optional - only appear if content exists
- Mobile responsive design
- Automatic icon integration for external links
- Paper button appears in project header navigation

#### �🔧 **Troubleshooting Image Issues**

**Images not appearing?** Check these common issues:

1. **Slug Mismatch**: Jekyll converts project names to slugs automatically
   ```bash
   # Test slug generation:
   echo "Your Project Name" | tr '[:upper:]' '[:lower:]' | sed 's/[^a-z0-9 ]//g' | tr ' ' '-'
   ```

2. **File Naming**: Ensure files match exactly:
   - Project file: `_projects/[exact-slug].md`  
   - Image file: `assets/img/projects/[exact-slug]-hero.jpg`
   - Frontmatter: `featured_image: /assets/img/projects/[exact-slug]-hero.jpg`

3. **Collection Setup**: Verify `_config.yml` has:
   ```yaml
   collections:
     projects:
       output: true
       permalink: /projects/:name/
   ```

**Quick Fix Template**:
```markdown
---
title: "Project Name"
featured_image: /assets/img/projects/project-slug-hero.jpg
---
```

#### 📊 **Project Status System**

Add visual status badges to your projects to indicate their current state.

**Available Status Options**:
| Status | YAML Value | Badge Color | Use Case |
|--------|------------|-------------|----------|
| 🟢 **Completed** | `status: completed` | Green | Finished projects |
| 🟡 **In Progress** | `status: in-progress` | Orange | Currently working |
| 🔵 **Planning** | `status: planning` | Blue | In design/planning phase |
| ⚫ **On Hold** | `status: on-hold` | Gray | Temporarily paused |
| ⚪ **Archived** | `status: archived` | Light Gray | Old/deprecated projects |

**Implementation**:
```yaml
# In _data/projects.yml
- name: "Your Project Name"
  summary: "Project description"
  stack: ["Tech", "Stack"] 
  github: "https://github.com/repo"
  status: in-progress  # Add status field
```

**Status Badge Features**:
- Appears in top-right corner of project cards
- Automatically styled with appropriate colors
- Defaults to "Completed" if no status specified
- Supports custom status values with fallback styling

**Quick Status Changes**:
```yaml
# Mark as In Progress
status: in-progress

# Mark as Planning Phase  
status: planning

# Mark as Complete (or omit status field)
status: completed
```

### Updating Experience & Certifications
- **Experience Timeline**: Modify `_data/experience.yml`
  ```yaml
  - company: "Company Name"
    position: "Job Title"
    duration: "2023 - Present"
    location: "City, State"
    description: "Key responsibilities and achievements"
    technologies: ["Tech1", "Tech2"]
  ```

- **Certifications**: Update `_data/certs.yml`
  ```yaml
  - name: "Certification Name"
    issuer: "Issuing Organization"
    date: "2025"
    credential_id: "ABC123"
    badge_url: "https://badge-link.com"
  ```

### Blog Post Management
1. **Create New Post**: Add to `_posts/` with Jekyll naming: `YYYY-MM-DD-post-title.md`
2. **Front Matter Template**:
   ```markdown
   ---
   layout: post
   title: "Your Post Title"
   date: 2025-01-15
   categories: [technology, consulting]
   tags: [cloud, aws, optimization]
   excerpt: "SEO-friendly description (155 chars max)"
   author: "Leonardo Cuellar"
   ---
   ```
3. **Content**: Use markdown with headers (##), code blocks, and images
4. **SEO**: Include relevant keywords naturally, optimize images with alt text

## 🛠️ Customization & Development

### Color Scheme Customization
**File**: `assets/main.scss` (lines 10-70)
```scss
:root {
  --primary: #1C1C1E;    /* Change header/nav color */
  --secondary: #2C2C54;  /* Update section backgrounds */
  --accent: #FF6B6B;     /* Modify button/link color */
  --bg-primary: #FAFAFA; /* Adjust main background */
  --text-primary: #2E2E2E; /* Change body text color */
}
```

**Critical CSS**: Update `_includes/head-custom.html` to match new colors

### Navigation & Menu
**File**: `_config.yml`
```yaml
nav:
  - title: "Home"
    url: "/"
  - title: "Experience" 
    url: "/experience/"
  # Add/remove/reorder menu items
```

### Social Links & Contact
**File**: `_config.yml`
```yaml
minima:
  social_links:
    - { platform: linkedin, user_url: "https://linkedin.com/in/your-profile" }
    - { platform: github, user_url: "https://github.com/your-username" }
    - { platform: x, user_url: "https://x.com/your-handle" }
```

### Project Filtering Categories
**File**: `pages/projects.md` - Update filter buttons and data-category attributes:
```html
<button class="category-filter" data-category="your-category">Category Name</button>
```

Match with project cards' `data-category` attributes in the project loop.

## 🚀 Development & Deployment

### Local Development Setup
```bash
# Install Ruby and Bundler first
gem install bundler jekyll

# Clone and setup
git clone https://github.com/username/portfolio.git
cd portfolio
bundle install

# Serve locally (auto-reload on changes)
bundle exec jekyll serve --livereload
# Site available at http://localhost:4000

# Build for production
bundle exec jekyll build
```

### GitHub Pages Deployment
1. **Push to Main**: All changes to `main` branch trigger automatic deployment
2. **Build Process**: GitHub Actions compiles SCSS, processes content, optimizes assets
3. **Live Site**: Available at `https://username.github.io` within 1-2 minutes
4. **Custom Domain**: Configure in repository Settings > Pages (optional)

### Performance Optimization
- **Images**: Compress before upload, use appropriate formats (WebP, PNG, JPG)
- **SCSS**: Builds are automatically compressed via `sass.style: compressed`
- **Critical CSS**: Essential styles load immediately in `head-custom.html`
- **Fonts**: Preconnected Google Fonts for faster loading

## 🔍 SEO & Analytics

### Built-in SEO Features
- **Structured Data**: Automatic JSON-LD markup for rich snippets
- **Meta Tags**: Dynamic Open Graph, Twitter Cards from front matter
- **Sitemap**: Auto-generated XML sitemap at `/sitemap.xml`
- **RSS Feed**: Blog feed available at `/feed.xml`

### Analytics Integration (Optional)
Add to `_includes/head-custom.html`:
```html
<!-- Google Analytics -->
<script async src="https://www.googletagmanager.com/gtag/js?id=GA_MEASUREMENT_ID"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'GA_MEASUREMENT_ID');
</script>
```

## 🛡️ Maintenance Checklist

### Weekly
- [ ] Review project filter functionality
- [ ] Check responsive design on mobile devices
- [ ] Verify all links work correctly
- [ ] Test contact forms and social links

### Monthly
- [ ] Update dependencies: `bundle update`
- [ ] Review and update project descriptions
- [ ] Add new blog posts or project updates
- [ ] Check site performance with Lighthouse

### Quarterly
- [ ] Update experience/certifications data
- [ ] Review color contrast with accessibility tools
- [ ] Backup repository and verify deployment
- [ ] Update professional headshot/images

### As Needed
- [ ] Add new projects with case studies
- [ ] Update contact information
- [ ] Modify navigation or add new pages
- [ ] Customize colors for rebranding

## 🔧 Troubleshooting

### Common Issues
1. **CSS Not Loading**: Verify `assets/main.scss` has front matter (`---` at top)
2. **Build Failures**: Check YAML syntax in `_config.yml` and data files
3. **Project Filters Not Working**: Ensure JavaScript is included in `projects.md`
4. **Images Not Displaying**: Verify file paths and ensure images are in `assets/img/`
5. **Navigation Issues**: Check menu URLs in `_config.yml` match actual page paths

### Validation Tools
- **HTML**: [W3C Markup Validator](https://validator.w3.org/)
- **CSS**: [W3C CSS Validator](https://jigsaw.w3.org/css-validator/)
- **Accessibility**: [WAVE Web Accessibility Validator](https://wave.webaim.org/)
- **Performance**: [Google PageSpeed Insights](https://pagespeed.web.dev/)
- **SEO**: [Google Search Console](https://search.google.com/search-console/)

## 📚 Additional Resources

### Jekyll & GitHub Pages
- [Jekyll Documentation](https://jekyllrb.com/docs/)
- [GitHub Pages Guide](https://docs.github.com/en/pages)
- [Liquid Template Language](https://shopify.github.io/liquid/)

### Design & Accessibility  
- [WebAIM Contrast Checker](https://webaim.org/resources/contrastchecker/)
- [WCAG Guidelines](https://www.w3.org/WAI/WCAG21/quickref/)
- [Color Theory for Developers](https://blog.datawrapper.de/colorguide/)

---

**Professional Portfolio** | Built with Jekyll & deployed via GitHub Pages  
**Author**: Leonardo Cuellar | **Color Scheme**: Charcoal & Coral | **License**: MIT
