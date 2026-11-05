# Select Staycation Multi-site Hospitality Website and CMS

[繁體中文](README.md) · [Live site: Select Staycation](https://selectstaycation.com)

![Select Staycation portfolio cover](../../assets/project-covers/select-staycation-cover.png)

**Type:** Client project / hospitality website and CMS  
**Role:** Full-stack Engineer  
**Focus:** Multi-site content management · Stay filters · Chinese and English admin UI · Inquiry-based booking

## Overview

A website and content management system built to support multiple hospitality sites. The public website presents Select Staycation's brand, stays and hospitality services. The management platform supports site setup and day-to-day editing of stays, pages, media and marketing content.

## Website screenshots

These screenshots show Select Staycation's homepage, stay filters, property imagery and dining services.

### 1. Brand homepage and booking entry points

Full-width property imagery with brand copy, site navigation and booking entry points.

![Select Staycation brand homepage and booking entry points](screenshots/01-home-hero.png)

### 2. Stay filters and brand introduction

Stay discovery by city, district, guest count, facilities and experiences, followed by an illustrated brand introduction.

![Select Staycation stay filters and brand introduction](screenshots/02-stay-search-and-brand.png)

### 3. Property gallery and contact guidance

Pool, bathroom and interior photography paired with contact guidance and a link to browse stays.

![Select Staycation property gallery and contact guidance](screenshots/03-gallery-and-contact.png)

### 4. Dining and service content

Categories and cards organize private dining, catering, barbecues and outdoor dining experiences.

![Select Staycation dining and service content](screenshots/04-dining-services.png)

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

The public link and screenshots show the Select Staycation website. This case study describes selected multi-site CMS and inquiry features; it does not include production source code, databases, credentials, secrets or guest information.
