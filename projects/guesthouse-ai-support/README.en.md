# Guesthouse AI Support & Knowledge Platform

[繁體中文](README.md)

**Period:** 2026/05 – 2026/06<br>
**Type:** Commercial / Full-time<br>
**Role:** AI Application / Backend Engineer<br>
**Focus:** LINE OA · Intent Routing · RAG · Hybrid Retrieval · Multi-tenancy

## What the support flow handles

This is a LINE-based AI support service for a guesthouse. Users ask about room lists, room details, contact information, booking-related questions or general topics. When the user requests a human or the system does not have enough evidence, the flow hands the conversation to human support instead of forcing an answer.

## What I worked on

- Built the FastAPI LINE Webhook entrypoint and duplicate-event handling
- Routed messages with LangGraph across room list, room details, contact, booking, general and escalation intents
- Connected guesthouse data tools and a knowledge base instead of putting every answer into a prompt
- Implemented document parsing, chunking, PII masking, embedding and indexing flows
- Combined vector search with lexical / BM25 search and merged the results with Weighted RRF
- Carried tenant context, permissions and provider failure states through the request path

## Problems I ran into

### Vector search alone was not enough for exact names

Semantic search helped with meaning, but room names, policy names and property-specific terms still needed exact matching. I therefore combined vector and lexical retrieval and used RRF to merge the results. The point was to cover a weakness in semantic search, not to add complexity for its own sake.

### The same question can have a different answer per guesthouse

Tenant identity cannot be checked only at login. The webhook, user context, knowledge sources and tools all need to stay on the same routed path, otherwise one property can receive another property’s room or policy information.

### Missing evidence should lead to escalation

The agent routes to RAG, guesthouse data tools or human support based on intent. When retrieval is insufficient, a provider fails or the user asks for a person, the response enters a safe fallback instead of hiding the uncertainty behind confident text.

## Architecture and flows

![AI customer service architecture](diagrams/system-architecture.svg)

- [LINE agent flow](diagrams/line-agent-flow.svg)
- [RAG pipeline](diagrams/rag-pipeline.svg)
  - [Multi-tenant model](diagrams/multi-tenant-model.svg)
  - [Mermaid source](diagrams/system-architecture.mmd)

  ## Screenshots

  These screenshots keep the LINE guesthouse-support workflow visible while masking the property avatar, names and other identifying information.

  ![Room list and room details](screenshots/room-list.png)

  ![Hospitality reply with attractions, transport and check-in information](screenshots/hospitality-line-reply.png)

  ## Technology

The backend uses FastAPI and Python; the agent flow uses LangGraph; retrieval uses PostgreSQL, pgvector, BM25 and RRF; the entry point is the LINE Messaging API. Documents are split, checked for sensitive content and embedded before they enter the query path.

**skills:** Python, FastAPI, LangGraph, PostgreSQL, pgvector, RAG, Embedding, BM25, RRF, LINE Messaging API, LLM

## Trade-offs and public scope

The public version describes the application, routing and retrieval design. It does not claim production traffic, provider SLA or customer-answer accuracy. Guesthouse names, data, credentials and deployment details are excluded; if document ingestion grows, the current background processing approach would need a durable queue and dedicated workers.
