# Professional Project Case Studies

[繁體中文](README.md)

Commercial software engineering case studies from full-time work, freelance projects, and client engagements.

This repository focuses on selected features and engineering decisions rather than complete source code:

- Enterprise systems
- AI and Agent applications
- System integrations
- Multi-tenancy and authorization
- Reliability and security
- Data and domain modeling
- Production-oriented development

The five enterprise-platform case studies cover commercial development work from **March 2026 to September 2026**. Website and CMS cases are documented by verified scope without inferring project dates.

> Commercial source code and production data are not publicly available.
> All materials have been simplified and anonymized for portfolio presentation.

## Selected Projects

| Project | Role | Main Engineering Focus |
| --- | --- | --- |
| Multi-store POS / ERP / CRM Integration Platform | Full-stack Engineer | Catalog, BOM, Inventory, Manufacturing, Sync |
| Guesthouse AI Support & Knowledge Platform | AI / Backend Engineer | LINE OA, Intent Routing, RAG, Hybrid Retrieval |
| Companion AI Voice & Agent Platform | Full-stack / AI Engineer | Realtime Voice, WebSocket, Agent Runtime |
| Travel Operations & Dispatch Platform | Full-stack Engineer | Orders, Dispatch, GPS, Mobile |
| Workplace Chinese Learning Platform | Full-stack Engineer | Multi-tenancy, Localization, Imports, Analytics |
| Slowfield Stays Multi-site Hospitality Website and CMS | Full-stack Engineer | Multi-site Content, Stay Filters, Inquiry Booking |
| Talk915TW Online Language Learning Service Website | Full-stack Engineer | CMS, Course Content, Trial and Consultation Flow |

### Multi-store POS / ERP / CRM Integration Platform

Selected features from a multi-store POS, inventory, manufacturing, finance and CRM platform.

**Focus:**  
Legacy modernization · Domain modeling · BOM · Inventory · Manufacturing ·
Multi-tenancy · POS-to-CRM integration · Reliability

[View Case Study](./projects/multi-store-pos-erp-crm/README.en.md)

### Guesthouse AI Support & Knowledge Platform

LINE-based AI support for guesthouse questions, room information and booking-related conversations.

**Focus:**  
AI Agent · RAG · PostgreSQL · Vector Search · BM25 · LINE ·
Knowledge Base · Human Escalation

[View Case Study](./projects/guesthouse-ai-support/README.en.md)

### Companion AI Voice & Agent Platform

Realtime companion voice application with STT, LLM, TTS and session-aware agent behavior.

**Focus:**  
Voice AI · WebSocket · Agent Runtime · Memory · Privacy · Search ·
Reconnect Handling

[View Case Study](./projects/companion-ai-platform/README.en.md)

### Travel Operations & Dispatch Platform

Travel operations and dispatch platform for staff, drivers and customers.

**Focus:**  
Next.js · Expo · Dispatch · GPS · Mobile · Authentication ·
Order Lifecycle · AI Assistance

[View Case Study](./projects/travel-operations-dispatch/README.en.md)

### Workplace Chinese Learning Platform

Multi-tenant Chinese learning platform for factory workers and enterprise administrators.

**Focus:**  
Next.js · NestJS · PostgreSQL · Learning Platform · Analytics ·
Multilingual Content · Import Workflows

[View Case Study](./projects/workplace-chinese-learning/README.en.md)

## Website & CMS Cases

### Slowfield Stays Multi-site Hospitality Website and CMS

A multi-site CMS for hospitality brands, with stay browsing and an inquiry-based booking flow. Built as a client project and now shown as Slowfield Stays, a fictional brand. There is no live site, so the source and walkthrough videos show it instead.

[View Case Study](./projects/slowfield-stays/README.en.md) · [Showcase source](https://github.com/yoAkyoku/slowfield-stays) · [Public-site video](https://github.com/yoAkyoku/slowfield-stays/blob/main/docs/videos/front-walkthrough.mp4) · [Admin video](https://github.com/yoAkyoku/slowfield-stays/blob/main/docs/videos/admin-walkthrough.mp4)

### Talk915TW Online Language Learning Service Website

A Taiwan-facing service website with course information, trial and consultation entry points, and CMS-managed content.

[View Case Study](./projects/talk915tw/README.en.md) · [Live Site](https://talk915tw.com)

## Independent Project

### SUCRÉ Patisserie WooCommerce Store

A self-initiated WordPress + WooCommerce portfolio build translating a design into a responsive storefront with a custom theme, custom plugin, Docker Compose, and a local checkout journey. This is an **independent demo, not a client engagement**.

**Focus:** WordPress · WooCommerce · Custom Theme / Plugin · Docker Compose · Responsive UI · Store API · Checkout Blocks

[View Case Study](./projects/sucre-woocommerce/README.en.md)

## How to Read a Case Study

Each case study documents selected work instead of the entire application. The structure varies by project, but usually covers:

1. Starting situation
2. What I worked on
3. Problems and decisions
4. Architecture, flows and recreated screens
5. Trade-offs, limitations and public-safe scope

Each Mermaid diagram has an accompanying SVG export:

```text
diagrams/system-architecture.mmd
diagrams/system-architecture.svg
```

The `.mmd` file is the editable source. The `.svg` file is used for GitHub, resumes and presentations.

## Confidentiality

These projects were developed in professional or commercial environments.

This repository does **not** contain:

- Production source code
- Credentials or API keys
- Production databases
- Customer information
- Internal infrastructure addresses
- Confidential business rules
- Unmasked production logs or data

Architecture diagrams and implementation descriptions have been simplified or anonymized for portfolio presentation.
