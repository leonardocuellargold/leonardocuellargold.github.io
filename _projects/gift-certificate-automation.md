---
title: "Gift Certificate Automation"
subtitle: "Automated donation certificate generation and distribution system"
date: 2024-11-20
stack: [Go, Power Automate, Optimy]
github: https://github.com/YOUR-USERNAME/gift-cert-automation
featured_image: /assets/img/projects/gift-cert-hero.jpg
gallery:
  - src: /assets/img/projects/gift-cert-1.jpg
    alt: "Certificate template design"
    caption: "Custom PDF certificate templates"
  - src: /assets/img/projects/gift-cert-2.jpg
    alt: "Power Automate workflow"
    caption: "Automated workflow in Power Automate"
---

## Overview

An end-to-end automation system that generates personalized donation certificates and automatically emails them to recipient organizations, built using Go backend services and Microsoft Power Automate workflows.

## Problem Statement

Manual certificate generation was time-consuming and error-prone, requiring significant administrative overhead for processing donations and creating personalized documents for each recipient organization.

## Solution Architecture

- **Go Backend**: Handles certificate generation, data processing, and PDF creation
- **Power Automate**: Orchestrates the workflow and manages email distribution
- **Optimy Integration**: Pulls donation data and recipient information
- **PDF Generation**: Custom templates with dynamic content insertion

## Key Features

- Automated data extraction from Optimy platform
- Dynamic PDF certificate generation with custom branding
- Bulk processing capabilities for multiple certificates
- Automated email distribution with tracking
- Error handling and retry mechanisms

## Technical Highlights

The Go application uses a template-based approach for PDF generation, allowing for easy customization of certificate designs. Integration with Power Automate enables seamless workflow automation within the existing Microsoft ecosystem.

## Impact

Reduced certificate processing time from hours to minutes, eliminated manual errors, and improved recipient experience with faster delivery of donation acknowledgments.