---
id: confluence-884753
source: confluence
title: System Architecture
url: https://erfwagvbe.atlassian.net/wiki/spaces/LFE/pages/884753/System+Architecture
ingested_at: 2026-06-28T19:16:22.199083+00:00
updated_at: 2026-06-17T15:23:09.218000+00:00
metadata:
  space_key: LFE
  page_id: 884753
---
# System Architecture

# System Architecture

**Owner:** Mateo Ruiz

**Purpose:** Summarize the LumaRoute technical architecture for implementation and support teams.

### Architecture

LumaRoute has three primary clients: Dispatch Web App, Driver Mobile App, and Customer ETA Portal. These clients communicate through an API gateway to tenant-aware services for route planning, stop execution, telemetry ingestion, ETA calculation, alerts, notifications, and reporting.

### Service Map

| Service | Responsibility | Primary Jira Work |
| --- | --- | --- |
| Route Planning Service | Manifest import, route scoring, optimized route comparison | LRDP-101, LRDP-102, LRDP-103 |
| Stop Execution Service | Driver tasks, barcode proof, offline sync | LRDP-111, LRDP-112, LRDP-113 |
| Telemetry Ingest Service | Sensor validation, reading persistence, stale sensor metrics | LRDP-121, LRDP-124, LRDP-146 |
| Alert and Exception Service | Temperature excursion detection, acknowledgement, assignment | LRDP-123, LRDP-142, LRDP-143 |
| ETA Service | Delay detection and revised ETA windows | LRDP-131, LRDP-132 |
| Notification Service | Customer SMS/email delay notifications | LRDP-133, LRDP-152 |
| Reporting Service | Compliance CSV exports | LRDP-153 |

### Feature Flags

| Flag | Purpose | Initial State |
| --- | --- | --- |
| `temperatureTimeline` | Enables dispatch temperature timeline | On in QA and staging |
| `driverOfflineSync` | Enables persistent offline task queue | On in QA only |
| `customerEtaPortal` | Enables customer-facing ETA links | On for pilot tenants |
| `exceptionQueueV2` | Enables severity and owner filters | On in QA and staging |

---
