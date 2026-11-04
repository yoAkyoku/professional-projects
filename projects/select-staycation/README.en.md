# Select Staycation Multi-site Hospitality Website and CMS

[繁體中文](README.md) · [Live site: Villa Samaya Awan](https://selectstaycation.com)

**Type:** Client project / hospitality website and CMS  
**Role:** Full-stack Engineer  
**Focus:** Multi-site content management · Stay filters · Chinese and English admin UI · Inquiry-based booking

## Overview

A website and content management system built to support multiple hospitality sites. The public link in this case study points to Villa Samaya Awan, a Select Staycation brand. The management platform supports site setup and day-to-day editing of stays, pages, media and marketing content.

## What I built

- A parent, template and child-site workflow. After creation, each child site can maintain its own content and settings.
- Stay listing and detail pages with room types, pricing text, facilities, FAQs, location and contact details, plus stay filters.
- Chinese and English admin UI. Site content is maintained separately; changing the admin UI language does not translate CMS content.
- CMS workflows for pages, banners, articles and media, with preview, review, publish and archive states.
- An inquiry-based booking flow. Guest requests enter an admin queue where staff can update status, add internal notes and export CSV.
- Newsletter subscriptions and a sending queue, with unsubscribe handling and per-site SMTP settings.

## Engineering decisions

### Booking requests go to an operations queue

The flow collects stay inquiries for staff follow-up. It does not reserve rooms in real time or handle room inventory, online payments, confirmed orders or cancellations; those are outside this release.

### Child sites stay independently editable

A new child site starts from a template, then its copy, images, SEO and settings can be maintained separately. This keeps a shared structure while allowing each brand to manage its own content.

## Technology

Next.js · TypeScript · React · FastAPI · SQLAlchemy · PostgreSQL · Alembic · Docker Compose

## Public scope

The public link shows the Villa Samaya Awan website. This case study describes selected multi-site CMS and inquiry features; it does not include production source code, databases, credentials, secrets or guest information.