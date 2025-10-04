---
title: "Bloom — Shopify Inventory Web App"
subtitle: "Web application for product management and logistics tracking"
date: 2025-10-03
stack: [Go, Gorilla Sessions, MongoDB, Shopify Webhooks, Digital Ocean]
github: 
featured_image: /assets/img/projects/bloom-hero.jpg
hero_image: /assets/img/projects/bloom-detail-hero.jpg
gallery:
  - src: /assets/img/projects/bloom-1.jpg
    alt: "Bloom product dashboard"
    caption: "Centralized inventory management view"
  - src: /assets/img/projects/bloom-2.jpg
    alt: "Stock zones management"
    caption: "Stock zones management for logistics"
  - src: /assets/img/projects/bloom-3.jpg
    alt: "Login"
    caption: "Login page"
---

## The Problem We Solved

Before Bloom, the gallery’s staff relied on manual spreadsheets and emails to track products across multiple zones. This often led to duplicated entries, inventory errors, and slow resolution of issues. With Bloom, everything is centralized and automated.

## What Makes Bloom Different

- **Shopify-Connected**: Inventory syncs automatically the moment something changes in Shopify.
- **Zone-Level Tracking**: Each product is tied to a physical or logistical zone for real-time visibility.
- **Smart Issue Logging**: Problems can be flagged by staff directly in the dashboard and tracked until resolved.
- **Team-Specific Views**: Admins, managers, and staff see only what matters to them.

## How It Works Under the Hood

Bloom is powered by a Go backend with Gorilla sessions for secure logins and role-based access. Shopify webhooks trigger updates that are stored in a PostgreSQL database designed in third normal form (3NF) to keep data clean and reliable.  

On top of that, Google Cloud ensures uptime and scalability for the growing product catalog.

## Roadblocks & Breakthroughs

- **Webhook Reliability**: To prevent missed updates, Bloom logs webhook calls and retries failed ones automatically.  
- **Performance at Scale**: Indexing and query optimization in PostgreSQL allow smooth handling of large variant data.  
- **Security by Design**: Token and session management are fully handled on the backend, removing dependency on environment variables.

## Impact for the Gallery

With Bloom, the gallery gained:

- A single source of truth for products and variants.  
- Faster inventory audits across zones.  
- Reduced manual work and data-entry errors.  
- Better communication between staff and management.  

## Why It Matters

Bloom demonstrates how modern web technologies can streamline operations for small businesses. By combining Go, MongoDB, Shopify integration, and cloud deployment, it delivers a production-ready solution that not only saves time but also improves accuracy and business insight.