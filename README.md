# Professional Project Case Studies

[繁體中文](README.zh-TW.md)

Commercial software engineering case studies from full-time work, freelance projects, and client engagements.

This repository focuses on selected features and engineering decisions rather than complete source code:

- Enterprise systems
- AI and Agent applications
- System integrations
- Multi-tenancy and authorization
- Reliability and security
- Data and domain modeling
- Production-oriented development

The case studies cover work from **May 2026 to the present**.

> Commercial source code and production data are not publicly available.
> All materials have been simplified and anonymized for portfolio presentation.

## Selected Projects

| Project | Role | Main Engineering Focus |
| --- | --- | --- |
| POS / ERP / CRM | Full-stack Engineer | Domain Modeling, BOM, Inventory, Outbox |
| AI Customer Service | AI / Backend Engineer | LangGraph, RAG, Hybrid Retrieval |
| Memoa | Full-stack / AI Engineer | Realtime Voice Agent, WebSocket |
| Smart Travel | Full-stack Engineer | Web / Mobile, Dispatch, GPS |
| Factory Pro Chinese | Full-stack Engineer | Multi-tenant Learning Platform |
| Shared AI Search | Platform Engineer | Search Gateway, SearXNG, Crawl4AI |

### POS / ERP / CRM Platform

Selected features from a multi-store POS, inventory, manufacturing, finance and CRM platform.

**Focus:**  
Legacy modernization · Domain modeling · BOM · Inventory · Manufacturing ·
Multi-tenancy · POS-to-CRM integration · Reliability

[View Case Study](./projects/pos-erp-crm/README.md)

### Multi-tenant AI Customer Service

LINE-based AI customer service with LangGraph, RAG and hybrid retrieval.

**Focus:**  
AI Agent · RAG · PostgreSQL · Vector Search · BM25 · LINE ·
Knowledge Base · Human Escalation

[View Case Study](./projects/ai-customer-service/README.md)

### Memoa AI Voice Agent

Realtime voice companion and care platform with STT, LLM and TTS.

**Focus:**  
Voice AI · WebSocket · Agent Runtime · Memory · Privacy · Search ·
Reconnect Handling

[View Case Study](./projects/memoa-ai-agent/README.md)

### Smart Travel Platform

Travel operations and dispatch platform for staff, drivers and customers.

**Focus:**  
Next.js · Expo · Dispatch · GPS · Mobile · Authentication ·
Order Lifecycle · AI Assistance

[View Case Study](./projects/smart-travel/README.md)

### Factory Pro Chinese

Multi-tenant learning platform for factory workers and enterprise administrators.

**Focus:**  
Next.js · NestJS · PostgreSQL · Learning Platform · Analytics ·
OCR · Speech · Import Workflows

[View Case Study](./projects/factory-pro-chinese/README.md)

## Platform Engineering

### Shared AI Search Infrastructure

Shared search and web-content infrastructure used by multiple AI applications.

[View Case Study](./platforms/shared-ai-search/README.md)

## How to Read a Case Study

Each case study documents selected functionality instead of the entire application:

1. Project context
2. My responsibilities
3. Selected feature scope
4. Architecture diagram
5. Important flow
6. Engineering challenges
7. Technical decisions
8. Reliability and security considerations
9. Trade-offs and limitations

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
- Unmasked screenshots or logs

Architecture diagrams, screenshots and implementation descriptions have been simplified or anonymized for portfolio presentation.
