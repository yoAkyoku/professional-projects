# Multi-tenant AI Customer Service

## 1. Overview

A LINE-based intelligent customer service platform that connects messaging, knowledge retrieval, AI agent orchestration and human escalation.

## 2. Project Context

Customer service questions often require organization-specific knowledge. A single generic chatbot cannot safely answer across different tenants, so the system needs tenant-aware knowledge retrieval, controlled tool usage and a clear fallback to human support.

## 3. My Role

**AI Application / Backend Engineer**

I worked across:

- LINE Webhook integration
- FastAPI service design
- LangGraph agent orchestration
- RAG and hybrid retrieval
- Knowledge-base workflows
- Tenant and permission boundaries
- Async error handling
- External AI and notification integrations

## 4. Scope & Responsibilities

Selected responsibilities included:

- Receiving and validating LINE messages
- Connecting conversations to the correct tenant and user context
- Building the agent flow for intent handling and response generation
- Implementing knowledge retrieval with vector and lexical search
- Supporting query rewriting and embedding generation
- Designing human escalation when the system cannot answer safely
- Managing knowledge content and administrative settings
- Handling webhook duplication and asynchronous failures
- Integrating notification and voice-related services

## 5. Tech Stack

**Backend**  
FastAPI, Python

**AI**  
LangGraph, LLM APIs, Embeddings

**Retrieval**  
PostgreSQL, pgvector, BM25-style lexical retrieval, RRF ranking

**Integration**  
LINE Messaging API, Webhook, notification and voice providers

**Infrastructure**  
Docker, background tasks and database migrations

## 6. System Architecture

![AI customer service architecture](diagrams/system-architecture.svg)

[View Mermaid source](diagrams/system-architecture.mmd)

## 7. Key Engineering Challenges

### Combining semantic and keyword retrieval

Semantic retrieval is useful for meaning, while lexical retrieval is important for product names, policy terms and organization-specific wording. I designed a hybrid retrieval flow so both types of evidence can participate in the answer.

### Keeping tenant knowledge isolated

The same question can have different answers for different organizations. Tenant context therefore needs to be carried through the webhook, retrieval, prompt construction and response path.

### Handling uncertain answers

An AI response should not appear authoritative when the system lacks enough evidence. I designed an escalation path and explicit no-answer behavior for cases requiring human handling.

### Recovering from external service failures

LLM, embedding and messaging services can fail independently. I added asynchronous error handling and clearer failure states so one provider failure does not silently become a misleading customer response.

## 8. Technical Decisions

- Use hybrid retrieval instead of relying on vector similarity alone.
- Keep knowledge retrieval tenant-scoped before the agent receives context.
- Separate webhook validation, conversation state, retrieval and response generation.
- Treat human escalation as a first-class workflow.
- Keep external provider credentials in configuration rather than application logic.

## 9. Important Flows

- LINE message to agent response: [LINE agent flow](diagrams/line-agent-flow.svg)
- Document query to ranked context: [RAG pipeline](diagrams/rag-pipeline.svg)
- Tenant and knowledge boundaries: [Multi-tenant model](diagrams/multi-tenant-model.svg)

## 10. Reliability & Security

- LINE signature verification
- Webhook deduplication
- Tenant-aware retrieval
- Permission checks for administrative actions
- Sensitive data handling
- Async exception handling
- Provider configuration isolation
- Safe fallback and human escalation

## 11. External Integrations

- LINE Messaging API
- LLM and embedding providers
- PostgreSQL / pgvector
- Notification services
- Optional text-to-speech services

## 12. Screenshots

Only sanitized conversation, knowledge-base and settings screens will be included.

## 13. Trade-offs & Limitations

The case study documents the application and retrieval design. Formal provider SLA, production traffic and customer-answer accuracy are not claimed here.

The background processing approach is suitable for the current scope; a larger ingestion workload may require a durable queue and dedicated workers.

## 14. Outcome

The selected features form a complete path from LINE message intake to knowledge-backed response, with tenant boundaries and human escalation included in the design.

## 15. What I Learned

This project deepened my understanding of RAG quality, AI workflow orchestration, tenant-aware context and the importance of designing safe behavior for uncertain model output.

## 16. Confidentiality

This is a commercial project.

Production source code, credentials, customer data and proprietary business information are not included. Architecture and implementation details have been simplified or anonymized for portfolio presentation.

