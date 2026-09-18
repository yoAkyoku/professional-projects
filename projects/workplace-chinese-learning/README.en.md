# Workplace Chinese Learning Platform

[繁體中文](README.md)

**Period:** 2026/06 – 2026/07<br>
**Type:** Commercial / Full-time<br>
**Role:** Full-stack Engineer<br>
**Focus:** Next.js · NestJS · Learning Platform · Multi-tenancy · Analytics

## What the platform supports

This is a workplace Chinese learning platform for factory and enterprise teams. Learners move through courses and lessons while administrators manage employees, learning content and participation data. The product also needs to keep each factory's users, content and reports separate, and present enough language context for Vietnamese learners.

## What I worked on

I worked across the learner experience, administration console and backend API integration. The main areas were:

- Course, lesson, content, progress and employee-management screens.
- Experience, streak, recommendation, badge and certificate behavior.
- HSK vocabulary, pinyin, zhuyin, Vietnamese approximations and factory-scenario content.
- Analytics APIs and administrator views for learner participation.
- Excel / CSV bulk employee import and its administrative workflow.
- Multilingual content, validation, modal confirmation, responsive layouts and mobile navigation.
- Authentication, API routes, factory-level data isolation and deployment configuration.
- Docker container builds, health routes and environment troubleshooting.

## Where the work got tricky

### Progress is not just a percentage on a page

Course completion, lesson progress, experience and streak behavior depend on the same learner actions. If the frontend only updates a percentage, a refresh or another screen can show a different answer. I traced the state across the client and API so learner pages and analytics use the same progress rules.

### One deployment, multiple factories

Users, content and reports must stay within the administrator's factory scope. This is not solved by adding a factory selector to the UI. Tenant context has to travel through authentication, API access and administration actions, with the server checking the actual access boundary.

### A successful upload can still contain bad rows

The administration console supports Excel / CSV employee imports. The useful part is not only accepting the file; it is handling missing fields, duplicate records and individual row failures. The import flow reports progress, created and failed counts, and row-level names and error messages so an administrator can correct and retry the data.

### Learning content needs more than one language field

A vocabulary item can include Traditional Chinese, Vietnamese, pinyin, zhuyin, an approximate pronunciation, part of speech, category, HSK level, industry and difficulty. These fields affect both the learner page and the administration/import flow, so they need to stay consistent in the content model and validation rules.

## Architecture and selected flows

![Workplace Chinese learning platform architecture](diagrams/system-architecture.svg)

- [Mermaid source](diagrams/system-architecture.mmd)
- [Learning flow](diagrams/learning-flow.svg)
  - [Content import](diagrams/content-import.svg)
  - [Tenant and RBAC](diagrams/tenant-rbac.svg)

  ## Screenshots

  These screenshots show the learner home and factory-scenario lesson. Branding, factory identifiers and the main foreground people have been de-identified. OCR and speech recognition were not implemented in this project.

  ![Learner home and daily learning](screenshots/learning-home.png)

  ![Factory-scenario lesson and pronunciation practice](screenshots/lesson-practice.png)

  ## Technology and integrations

**Frontend:** Next.js, React, Tailwind-style UI<br>
**Backend:** NestJS, Node.js<br>
**Data / Runtime:** PostgreSQL, Redis<br>
**Application:** Multilingual content, Excel / CSV bulk import, analytics APIs and push notifications<br>
**Infrastructure:** Docker and CI-oriented deployment workflows

**Skills:** TypeScript, Next.js, NestJS, PostgreSQL, Redis, Docker, Multi-tenant, RBAC, PWA

## Trade-offs and public scope

This case study covers selected course, progress, administration, localization and bulk-import work. OCR and speech recognition were not implemented in this project, so they are not presented as platform capabilities. Production learner data, enterprise identities, credentials and proprietary course material are excluded.

## Confidentiality

This is a commercial project. Architecture and implementation details have been simplified or anonymized for portfolio presentation.
