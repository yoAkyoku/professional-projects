# Travel Operations & Dispatch Platform

[繁體中文](README.md)

**Period:** 2026/06 – 2026/07<br>
**Type:** Commercial / Full-time<br>
**Role:** Full-stack Engineer<br>
**Focus:** Next.js · Expo · Dispatch · GPS · Authentication

## What the system has to coordinate

A single travel order moves between the customer, operations staff and driver. The customer books and follows a trip, operations assigns and monitors it, and the driver accepts the job, reports location and completes the trip. The difficult part is keeping those views consistent when each role changes the order at a different time.

## What I worked on

I joined a project where some screens already existed but were not fully connected to APIs or edge-case behavior. My work covered:

- Customer booking, account and order flows.
- Driver login, profile, settings, income, online, accept and reject flows.
- Dispatch assignment, batch dispatch, filters and order-state operations.
- Synchronization between order, dispatch and driver-execution states.
- Map markers, navigation, trip sharing, GPS reporting and public tracking.
- Customer reviews, exception reporting, notifications and deep links.
- AI-assisted order parsing, dispatch suggestions, exception classification and operational risk prompts.
- Expo web routing, subpath deployment, JWT, rate-limit and proxy-header fixes.

## Where the work got tricky

### One order, several people changing it

An order can be pending, assigned, accepted, rejected, in progress or completed. I treated order status as the shared business state, then let each client derive its allowed actions from that state instead of maintaining separate guesses in the customer, dispatch and driver screens.

Dispatch is also more than choosing a driver. The operations screen filters by date, store, driver, vehicle type and status, checks roughly three-hour schedule conflicts, and can use an AI suggestion before a dispatcher confirms the assignment.

### GPS access needs a boundary

The map needs a recent driver position, but tracking should not be public before or after the service window. I kept service time, share links and role permissions separate, and only exposed locations when the access rules allowed it. The first implementation uses timed polling because it is easier to operate; the map refreshes the relevant locations instead of introducing a full real-time event layer.

### Web and native clients behave differently

The operations console, customer experience and driver app share backend services, but their API origins, routes and logout behavior are not identical. I kept those runtime settings separate and completed the surrounding loading, error, refresh, empty-state and session-cleanup behavior.

## Architecture and selected flows

![Travel operations and dispatch architecture](diagrams/system-architecture.svg)

- [Mermaid source](diagrams/system-architecture.mmd)
- [Order lifecycle](diagrams/order-lifecycle.svg)
  - [GPS tracking](diagrams/gps-tracking.svg)
  - [Authorization scope](diagrams/authorization-scope.svg)

  ## Screenshots

  These screenshots show dispatch operations, AI-assisted assignment and driver location tracking. Customer, store, driver and trip identifiers have been de-identified.

  ![Dispatch overview](screenshots/dispatch-overview.png)

  ![AI dispatch suggestion](screenshots/ai-dispatch-modal.png)

  ![Driver GPS tracking](screenshots/driver-gps-map.png)

  ## Technology and integrations

**Web / Mobile:** Next.js, React, Expo, React Native<br>
**Backend / Data:** API services, Prisma, PostgreSQL and JSON-backed data<br>
**Integrations:** Maps, GPS, SMS, push notifications, Slack and LLM services<br>
**Deployment:** Docker and CI workflows

**Skills:** TypeScript, Next.js, React Native, Expo, Prisma, PostgreSQL, JWT, REST API, GPS, Push Notification, LLM

## Trade-offs and public scope

Polling kept the first version understandable and maintainable. If concurrent usage grows, selected high-value status changes could move to SSE or WebSocket events.

This case study covers selected booking, dispatch, tracking and access-control work. It does not claim a production mobile-store release or a third-party provider SLA. Production source code, credentials, customer data and proprietary business rules are excluded.

## Confidentiality

This is a commercial project. Architecture and implementation details have been simplified or anonymized for portfolio presentation.
