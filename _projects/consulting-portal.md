---
title: "Consulting Portal"
subtitle: "Backend & Static Web Deployment with Secure Firebase Integration on GCP"
date: 2025-10-04
stack: [Go, Firebase, IAM, Cloud Run, GCP Buckets, HTML/CSS/JS]
github: 
featured_image: /assets/img/projects/Consulting-Hero.jpg
hero_image: /assets/img/projects/Consulting-Detail-Hero.jpg
gallery:
  - src: /assets/img/projects/Consulting-Gallery-1.jpg
    alt: "Home page and login page"
    caption: "Home page and log in page for the consulting portal"
  - src: /assets/img/projects/Consulting-Gallery-2.jpg
    alt: "Client and admin dashboard interface"
    caption: "Client and admin view of the dashboard, client view of documents and admin view of onboarding clients"
  - src: /assets/img/projects/Consulting-Gallery-3.jpg
    alt: "Client dashboard interface"
    caption: "Client view with project meetings"
  - src: /assets/img/projects/Consulting-Gallery-4.jpg
    alt: "Admin dashboard interface"
    caption: "Admin view of Projects and upcoming meetings in calendar view"
  - src: /assets/img/projects/Consulting-Gallery-5.jpg
    alt: "Admin dashboard interface"
    caption: "Admin view to manage documents for projects"
---

## Why I Built This

During my consulting work, I found that many small agencies and freelancers — myself included — still juggle spreadsheets, Google Docs, and emails to track projects, invoices, and client communications. These tools are familiar, but they don’t scale well. There's always a risk of something slipping through the cracks.

The Consulting Portal was born out of the need for something simple, clean, and secure. I didn’t want to over-engineer a solution — just build a robust foundation to manage workflows, roles, and basic reporting across clients and projects.

---

## What It Does

This web application serves as an internal portal for consulting teams to:

- **Track ongoing projects**, including client details, status updates, and financials.
- **Manage invoices** and billing history in a secure interface.
- **Authenticate users via Firebase**, enabling role-based permissions for admins and contributors.
- **Leverage a Go backend**, hosted on Cloud Run, to handle secure API routing, token validation, and database interactions.
- **Serve a static frontend** from a GCP bucket for fast performance and low cost.

The result is a clean experience for both backend and frontend users — secure, fast, and focused.

---

## Key Highlights

### Secure and Token-Aware

Authentication and role management are handled via Firebase, with the backend validating tokens before any protected resource is returned. I used [Gorilla Sessions](https://www.gorillatoolkit.org/pkg/sessions) in the Go backend to manage user sessions cleanly, which was critical for avoiding issues like “missing token” errors and managing login state server-side.

### Cloud Native and Scalable

All backend services are deployed to Google Cloud Run, with Secret Manager providing secure key storage. This lets me keep sensitive credentials out of my environment and deploy updates confidently without hardcoding anything.

### Clean Separation of Frontend and Backend

The frontend is completely static — meaning it’s fast and deployable to a bucket with versioned control. All business logic is handled via fetch calls to the Cloud Run API endpoint, keeping things modular and scalable.

### Update-Friendly Static Hosting

Because the frontend is hosted in a GCP bucket, it’s easy to update with a single sync command. This has made testing and iteration faster, especially while refining login behavior and fetch credential policies.

---

## What I Learned

### CORS and Credential Handling

One of the trickiest aspects was ensuring the frontend and backend could talk to each other securely, without throwing CORS or session errors. Firebase Auth requires tokens to be passed explicitly in headers, and sessions must be managed consistently across environments.

After debugging credential handling for a while, I realized I needed to consistently pass `{ credentials: 'include' }` in all fetch calls and make sure the Cloud Run instance allowed the correct origins and headers.

### Structuring Go for Modular Services

I split the Go code into distinct packages under `cmd/` and `internal/`, which has made it much easier to maintain and expand. Using a router like `chi` helped keep the API routes clear and fast.

### Cloud Deployment ≠ Complexity

Deploying to Cloud Run was surprisingly smooth. Once I had my Dockerfile and `cloudbuild.yaml` pipeline ready, deployment became a single-command job. I now use Cloud Build substitutions for runtime variables like allowed origins and secret references — keeping things flexible across staging and production environments.

---

## Why It Matters

The Portal isn’t meant to replace a full CRM or ERP. It's intentionally minimal — built for clarity, not complexity.

But that’s exactly why it matters: it shows that small teams don’t need to compromise on security, scalability, or structure just because they’re small. With the right stack — Go, Firebase, GCP — you can build smart, reliable systems that grow with you.

This project also sets the foundation for future expansions: invoicing automations, time tracking integrations, or even a full dashboard for client self-service. But for now, it does exactly what it needs to: keep operations clean, secure, and centralized.

---

## Next Steps

I’m already planning a few additions:

- OAuth login support for clients
- Basic analytics dashboard
- Comment threads on projects for internal collaboration