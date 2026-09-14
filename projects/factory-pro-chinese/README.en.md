# Factory Pro Chinese

[繁體中文](README.md)

**Period:** 2026/06 – 2026/07<br>
**Type:** Commercial / Full-time<br>
**Role:** Full-stack Engineer<br>
**Focus:** Next.js · NestJS · Learning Platform · Multi-tenancy · Analytics

## 1. Overview

A multi-tenant learning platform for enterprise training, course delivery, learning progress and administrative analytics.

## 2. Project Context

Factory training involves different enterprises, administrators and learners. The platform needed a consistent learning flow while supporting localized content, progress tracking, engagement features and administrative operations.

## 3. My Role

**Full-stack Engineer**

I worked across:

- Student and administrator interfaces
- Backend API integration
- Learning-domain logic
- Multi-tenant authentication
- Localization
- Analytics and reporting
- Import workflows
- Docker build and deployment troubleshooting

## 4. Scope & Responsibilities

Selected responsibilities included:

- Completing unfinished learner and management pages
- Implementing course, lesson and progress behavior
- Handling experience, streak, recommendation, badge and certificate flows
- Connecting reports to real analytics data
- Adding learner participation and engagement views
- Building bulk import and administrative content workflows
- Adding localization and multilingual seed content
- Fixing authentication, API route and tenant-isolation issues
- Improving validation and replacing ambiguous browser confirmations with modal flows
- Fixing responsive layouts and mobile navigation
- Maintaining container build, health route and deployment configuration

## 5. Tech Stack

**Frontend**  
Next.js, React, Tailwind-style UI

**Backend**  
NestJS, Node.js

**Database and Runtime**  
PostgreSQL, Redis

**Integrations**  
Translation, speech, OCR, Zalo and push notification services

**Infrastructure**  
Docker and CI-oriented deployment workflows

## 6. System Architecture

![Factory Pro Chinese architecture](diagrams/system-architecture.svg)

[View Mermaid source](diagrams/system-architecture.mmd)

## 7. Key Engineering Challenges

### Keeping learning progress consistent

Course completion, lesson progress, experience and streak behavior depend on the same learner actions. I traced these rules across frontend and backend so the interface and analytics represent the same learning state.

### Supporting enterprise separation

Different companies require independent users, content and reports. I implemented tenant-aware authentication and data boundaries for learner and administrator workflows.

### Connecting reporting to real data

Reports should describe actual learner behavior rather than static placeholders. I connected analytics APIs and added participation-oriented views for administrators.

### Importing operational content safely

Bulk content and learner imports can contain incomplete or inconsistent data. I added validation and administrative flows that make the import outcome visible and easier to recover.

## 8. Technical Decisions

- Keep learner progress as a domain state rather than a frontend-only display value.
- Carry tenant context through authentication, API access and reporting.
- Use explicit import validation instead of silently accepting malformed content.
- Separate learner interaction from administrative analytics.
- Keep localization close to the content and interface workflow.

## 9. Important Flows

- Learning and progress: [Learning flow](diagrams/learning-flow.svg)
- Content and learner import: [Content import](diagrams/content-import.svg)
- Enterprise access boundaries: [Tenant and RBAC](diagrams/tenant-rbac.svg)

## 10. Reliability & Security

- Authentication and tenant isolation
- API route and identity validation
- Input validation
- Progress and streak consistency
- Safe administrative imports
- Container health checks
- Build and deployment troubleshooting

## 11. External Integrations

- Translation and speech services
- OCR processing
- Zalo
- Push notifications
- Analytics APIs

## 12. Screenshots

Only sanitized learner, lesson and administrator screens will be included.

## 13. Trade-offs & Limitations

The case study focuses on selected learning and administration features. Production learner data, enterprise identities and provider credentials are excluded.

## 14. Outcome

The selected work completed the learning and administration paths needed to operate an enterprise training platform, including progress, analytics, localization and import workflows.

## 15. What I Learned

This project strengthened my understanding of learning-domain modeling, multi-tenant product behavior and the difference between a visually complete page and a workflow that is connected to real data.

## 16. Confidentiality

This is a commercial project.

Production source code, credentials, customer data and proprietary business information are not included. Architecture and implementation details have been simplified or anonymized for portfolio presentation.
