---
id: confluence-950273
type: processes
title: Service Ownership Matrix
date: 2026-06-17
status: active
supersedes: null
superseded_by: null
tags: ["confluence", "service", "ownership", "matrix"]
owner: 
sources:
  - type: confluence
    ref: sources/confluence/2026-06/Service_Ownership_Matrix.md
    url: https://erfwagvbe.atlassian.net/wiki/spaces/LFE/pages/950273/Service+Ownership+Matrix
related: []
freshness_check: null
confidence: medium
---
# Service Ownership Matrix

# Service Ownership Matrix

**Owner:** Mateo Ruiz

**Purpose:** Clarify who owns implementation, QA, support, and operational follow-up.

| Area | Primary Owner | Backup | QA Owner | Operational Signal |
| --- | --- | --- | --- | --- |
| Route Planning | Nora Blake | Mateo Ruiz | Hana Kim | Route import failures and route score latency |
| Driver Mobile | Elena Vos | Mateo Ruiz | Hana Kim | Sync queue depth and mobile crash-free sessions |
| Telemetry | Nora Blake | Theo Martin | Hana Kim | Sensor freshness and ingest error rate |
| Dispatch Dashboard | Dev Patel | Mateo Ruiz | Hana Kim | Route board load time and UI error rate |
| ETA and Notifications | Dev Patel | Nora Blake | Hana Kim | ETA recalculation latency and notification failure rate |
| Reporting | Nora Blake | Priya Nair | Hana Kim | Export duration and export error rate |
| Platform Security | Mateo Ruiz | Theo Martin | Hana Kim | 403 rate, tenant isolation test results |

---
