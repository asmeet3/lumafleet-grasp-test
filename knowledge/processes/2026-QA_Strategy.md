---
id: confluence-65707
type: processes
title: QA Strategy
date: 2026-06-17
status: active
supersedes: null
superseded_by: null
tags: ["confluence", "strategy"]
owner: 
sources:
  - type: confluence
    ref: sources/confluence/2026-06/QA_Strategy.md
    url: https://erfwagvbe.atlassian.net/wiki/spaces/LFE/pages/65707/QA+Strategy
related: []
freshness_check: null
confidence: medium
---
# QA Strategy

# QA Strategy

**Owner:** Hana Kim

**Purpose:** Define the quality approach for the LumaRoute beta release.

### Test Layers

| Layer | Coverage |
| --- | --- |
| Unit tests | Route score factors, telemetry validation, ETA threshold logic, permission checks |
| API tests | Route import, telemetry idempotency, exception acknowledgement, compliance export |
| UI tests | Route dashboard, exception filters, ETA portal token behavior |
| Mobile tests | Route checklist, barcode scan, offline sync queue |
| Exploratory tests | Dispatcher triage workflow, stale sensor scenario, provider failure recovery |

### Release Gates

* All test cases TC-LR-001 through TC-LR-020 executed for Beta 0.9.
* Sev 1 bugs closed before beta release.
* Sev 2 bugs require product-approved workaround and Confluence note.
* Tenant isolation tests must pass before any pilot data is loaded.

---
