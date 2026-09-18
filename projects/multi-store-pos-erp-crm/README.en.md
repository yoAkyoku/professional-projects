# Multi-store POS / ERP / CRM Integration Platform

[繁體中文](README.md)

**Period:** 2026/03 – 2026/09<br>
**Type:** Commercial / Full-time<br>
**Role:** Full-stack Engineer<br>
**Focus:** Catalog and inventory modeling · BOM / manufacturing · Multi-store · POS / CRM integration

## Where I started

The POS already had a substantial amount of working functionality. I continued from the existing Laravel structure while the scope expanded to multiple stores, warehouse transfers, variants, BOMs, manufacturing and CRM synchronization. A large part of the work was untangling old assumptions between products, ingredients and stock records rather than simply adding new screens.

## What I worked on

- Reworked the relationships between products, ingredients, categories and variants
- Expanded multi-level BOMs into manufacturing and inventory workflows
- Maintained purchasing, receiving, sales, returns, shipping, transfers and multi-warehouse stock changes
- Added cost history, inventory-change records, barcode receiving and master-data imports
- Maintained employee, reporting, accounting and multi-store operations screens
- Synchronized catalog, category, ingredient and transaction data from POS to CRM
- Worked on deployment scripts, queues, scheduled tasks, troubleshooting and test verification

## Problems I ran into

### Products, ingredients and stock were not interchangeable

The existing flows made different assumptions about items, products, ingredients and variants. Adding another field at the screen level would only move the inconsistency elsewhere. I traced how each type entered purchasing, manufacturing, inventory, cost and synchronization, then adjusted the write boundaries around those flows.

### A BOM is part of the stock workflow, not just a tree

Expanding a BOM affects work-order materials, required quantities, issuing and the final warehouse receipt. Flat query ordering was not enough for nested or repeated components, so I used tree traversal and ordering and added protection against circular relationships.

### POS should not wait for CRM

If every POS change waits for CRM, a temporary CRM failure becomes a store-operations failure. I separated the local transaction from background synchronization with an Outbox and queue flow, then added retry/backoff, idempotency, dead-letter handling, HMAC validation and circuit-breaker boundaries. A retry should not create the same catalog record or transaction twice.

## Architecture and selected flows

![POS / ERP / CRM architecture](diagrams/system-architecture.svg)

- [POS-to-CRM synchronization](diagrams/pos-crm-sync.svg)
- [Item / BOM domain](diagrams/item-bom-domain.svg)
  - [Manufacturing flow](diagrams/manufacturing-flow.svg)
  - [Mermaid source](diagrams/system-architecture.mmd)

  ## Screenshots

  These screenshots show selected functional boundaries only. Brand names, tenant identifiers, internal IDs and other identifying details have been removed.

  ![POS sales operation](screenshots/pos-sales-screen.png)

  ![ERP product and inventory](screenshots/erp-product-detail.png)

  ![ERP inventory movements and cost history](screenshots/erp-inventory-movements.png)

  ![CRM dashboard and customer analysis](screenshots/crm-dashboard.png)

  ## Technology and integrations

The backend uses Laravel and PHP; the frontend is HTML, JavaScript and Bootstrap-based operational UI backed by MySQL. The runtime includes Apache, scheduled tasks, a database queue, queue workers and print adapters.

**skills:** PHP, Laravel, JavaScript, MySQL, REST API, Multi-tenant, RBAC, Outbox Pattern, Queue, Idempotency, HMAC

External workflows include two-way Google Calendar booking, e-commerce order import, barcode receiving, LINE OA attendance, e-invoices and USB / Wi-Fi receipt printing.

## Trade-offs and public scope

The public version only describes selected commercial functionality. Production hostnames, source code, credentials, customer data and deployment evidence are excluded. RFID reader input and payment flows remain documented as integration boundaries; they are not presented as completed physical-device or formal payment UAT.
