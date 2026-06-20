---
id: confluence-524290
source: confluence
title: API & Integration Overview
url: https://erfwagvbe.atlassian.net/wiki/spaces/LFE/pages/524290/API+Integration+Overview
info_type: architecture
updated_at: 2026-06-17T15:23:11.051000+00:00
metadata:
  space_key: LFE
  page_id: 524290
---
# API & Integration Overview

# API & Integration Overview

**Owner:** Nora Blake

**Purpose:** Document the main API and external integration boundaries.

### Internal API Groups

| API Group | Example Endpoint | Used By | Related Jira |
| --- | --- | --- | --- |
| Route Import | `POST /api/routes/import` | Dispatch Web App | LRDP-101 |
| Route Score | `GET /api/routes/{routeId}/score` | Dispatch Web App | LRDP-102 |
| Driver Tasks | `GET /api/mobile/routes/today` | Driver Mobile App | LRDP-111 |
| Proof of Delivery | `POST /api/mobile/stops/{stopId}/proofs` | Driver Mobile App | LRDP-112 |
| Telemetry Ingest | `POST /api/telemetry/readings` | Sensor Gateway | LRDP-121 |
| Exceptions | `POST /api/exceptions/{id}/acknowledge` | Dispatch Dashboard | LRDP-123, LRDP-143 |
| ETA Portal | `GET /eta/{token}` | Customer Portal | LRDP-131 |
| Compliance Export | `GET /api/routes/{routeId}/compliance-export` | Compliance UI | LRDP-153 |

### External Integrations

| Integration | Purpose | Resilience Requirement |
| --- | --- | --- |
| Sensor gateway | Sends temperature readings during active routes | Idempotent ingestion and stale sensor detection |
| Mapping provider | Provides travel time and route matrix | Cache route calculations and degrade ETA confidence |
| Notification provider | Sends SMS/email delay notices | Provider idempotency key and retry log |
| Customer order system | Provides daily route manifest | Row-level validation and idempotent route import |

---
