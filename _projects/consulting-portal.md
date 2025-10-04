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

## From Prototype to Production — In the Cloud, Securely

This was one of those projects that started from a simple idea: build a portal where consulting projects, clients, milestones, and invoices could be easily tracked. But the execution had to be clean, fast, and *secure*.

No hardcoded tokens. No clunky interfaces. And definitely no skipping dev best practices.

I built this portal using Go for the backend (yes, *Golang* still slaps), Firebase for auth and storage, and deployed it all on Cloud Run and GCP Buckets. The frontend is statically hosted and optimized for speed, while the backend handles all logic and sensitive interactions like Firebase Admin SDK usage, hidden behind secrets.

---

## The Stack I Assembled

- **Backend in Go**: Built with clear modularity under `cmd/server/main.go`, serving routes and managing sessions.
- **Firebase Auth + Admin SDK**: Login, protected project routes, and write access all verified securely.
- **Cloud Run**: Handles backend traffic behind HTTPS with secret-managed tokens.
- **GCP Secret Manager**: Firebase service account lives here — no credentials in sight.
- **Static Bucket Deployment**: All HTML, CSS, and JS assets are served via GCP's global CDN.
- **CI/CD via Cloud Build**: One command, no drama.

---

## Key Highlights

### Firebase Secrets with Cloud Run

I didn’t want to ever worry about accidentally exposing my Firebase private key. Using **GCP Secrets**, I stored the entire service account as a secret, and injected it into the container during build-time.

In my `cloudbuild.yaml`, it looks like this:

```yaml
--set-secrets=FIREBASE_CONFIG=firebase-service-account:latest
```

Then, in Go, I pulled it using `secretmanager.NewClient` and unmarshalled it into the Firebase admin config. No `.json` files anywhere in the repo.

---

### 🛠️ Clean Frontend–Backend Separation

My HTML and JS files live in the `/web` folder and get deployed to the GCP bucket with:

```bash
gsutil rsync -R ./web gs://www.b1tsolutions.com
```

All `fetch()` calls were updated to use a single global `API_BASE_URL` declared in `config.js`, making it easy to switch environments or test locally.

```js
const API_BASE_URL = "https://b1t-backend-584702183583.us-central1.run.app";
```

### 🧠 Lessons & Breakthroughs

- **CORS Pain**: Needed to allow the bucket domain to call the backend. Easy fix with headers on Go side.
- **Static Routing in Buckets**: When a user visited `/login`, the bucket didn’t resolve it to `login.html`. Solution? A `meta redirect` in JavaScript or explicit links with `.html`.
- **Missing Token**: Solved by setting `credentials: 'include'` in every `fetch()` and properly forwarding cookies in Cloud Run.
- **Reversible Static Hosting**: With `gsutil rsync`, I could always sync to/from my local machine in seconds.

## Why I’m Proud of This One

This wasn’t just a school project or a test run. This is a real system I can hand to a small agency or freelancer group and say: “Here’s your portal. It’s secure. It works. And it’s yours.”

Everything is streamlined — from cloud-native security to scalable architecture.

And it’s just the start.

## More Coming Soon

I’m planning to expand this with:
- Admin-only analytics dashboards
- Email triggers on invoice approvals
- Multi-tenant support for other consulting groups