# Shared AI Search Infrastructure

[繁體中文](README.zh-TW.md)

**Period:** 2026/05 – Present<br>
**Type:** Commercial / Platform Engineering<br>
**Role:** Platform / Integration Engineer<br>
**Focus:** Search Gateway · SearXNG · Crawl4AI · Request Policy

## 1. Overview

A shared search and web-content platform used by AI applications that need external discovery, page retrieval and normalized content access.

## 2. Project Context

Several applications needed search and web-content capabilities. Keeping provider-specific code inside every application would duplicate configuration, error handling and security decisions, so the common boundary was extracted into a shared platform.

## 3. My Role

**Platform / Integration Engineer**

I worked across:

- Docker Compose service design
- Search Gateway API
- Provider adapters
- SearXNG and Crawl4AI integration
- Network and environment configuration
- Host allowlisting and request limits
- Application integration and troubleshooting

## 4. Scope & Responsibilities

Selected responsibilities included:

- Defining the shared service boundary
- Building a gateway that normalizes search and page retrieval
- Connecting search results with rendered page content
- Adding API-key validation and host policy checks
- Limiting request timeout and response size
- Handling provider errors and unavailable services
- Moving search responsibilities out of application repositories
- Connecting POS and AI applications through a stable adapter
- Maintaining container networking and reverse-proxy configuration

## 5. Tech Stack

**Services**  
SearXNG, Crawl4AI

**Data and Cache**  
PostgreSQL, Redis

**Integration**  
HTTP APIs, Search Gateway, provider adapters

**Infrastructure**  
Docker Compose, reverse proxy and environment-based configuration

## 6. System Architecture

![Shared AI search architecture](diagrams/system-architecture.svg)

[View Mermaid source](diagrams/system-architecture.mmd)

## 7. Key Engineering Challenges

### Defining a stable integration boundary

Applications should not need to know which search provider or page renderer is currently active. I separated provider details from the application-facing gateway contract.

### Controlling external requests

Search and page retrieval can access arbitrary external hosts. I added host policy, authentication, timeout and response-size controls to make the boundary explicit.

### Sharing infrastructure without coupling applications

The platform needs to serve different consumers while keeping their configuration and failure handling understandable. I used adapters and environment-based routing rather than copying provider logic into each application.

## 8. Technical Decisions

- Use a gateway as the single application-facing search boundary.
- Keep provider-specific behavior behind adapters.
- Apply request policy before external network access.
- Keep search, rendering and application business logic separate.
- Use Docker Compose to make the service relationship reproducible for local and test environments.

## 9. Important Flows

- Search provider and rendered content path: [Search request flow](diagrams/search-request-flow.svg)

## 10. Reliability & Security

- API-key boundary
- Host allowlist policy
- Timeout and response-size limits
- Provider error handling
- Container network separation
- Environment-based service configuration
- No credentials or production hosts in this repository

## 11. External Integrations

- SearXNG
- Crawl4AI
- POS application
- AI customer service
- Memoa voice agent
- PostgreSQL and Redis

## 12. Screenshots

A service diagram is preferred over screenshots for this platform case study.

## 13. Trade-offs & Limitations

The platform simplifies application integration but adds a shared operational dependency. A production deployment would need explicit monitoring, capacity planning and provider-level availability evidence.

## 14. Outcome

The selected work established a reusable search boundary so AI applications can consume external information without embedding provider-specific networking logic in every product.

## 15. What I Learned

Platform work is primarily about boundaries: a good shared service reduces duplication only when its contract, failure modes and security policy are clear.

## 16. Confidentiality

This is a commercial platform component.

Production source code, credentials, customer data and proprietary infrastructure details are not included. Architecture and implementation details have been simplified or anonymized for portfolio presentation.
