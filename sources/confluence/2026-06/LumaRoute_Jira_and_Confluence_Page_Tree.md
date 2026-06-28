---
id: confluence-720897
source: confluence
title: LumaRoute Jira and Confluence Page Tree
url: https://erfwagvbe.atlassian.net/wiki/spaces/LFE/pages/720897/LumaRoute+Jira+and+Confluence+Page+Tree
ingested_at: 2026-06-28T19:15:46.194306+00:00
updated_at: 2026-06-17T15:22:09.414000+00:00
metadata:
  space_key: LFE
  page_id: 720897
---
# LumaRoute Jira and Confluence Page Tree

# Confluence Page Tree: LumaFleet Engineering (`LFE`)

This file contains copy-ready Markdown for the suggested Confluence space **LumaFleet Engineering**. Each section below represents a page. Owners and Jira references are included so the content can be pasted into Confluence pages and linked to Jira issues in project `LRDP`.

## Page Tree

* LumaRoute Product & Engineering Hub

- Product Vision & North Star Metrics

- Personas and User Journeys

- Release Roadmap

- System Architecture

- Service Ownership Matrix

- API & Integration Overview

- Data Model Overview

- Sprint 14 Plan

- Sprint 14 Review & Retro

- Sprint 15 Plan

- Sprint 15 Review & Retro

- QA Strategy

- Test Case Catalog

- Bug Triage Log

- Runbook: Temperature Alert Incident

- Observability Dashboard Guide

- Deployment Checklist

---

## Page: LumaRoute Product & Engineering Hub

**Owner:** Amara Singh

**Audience:** Product, engineering, QA, support, and pilot stakeholders

**Related Jira Project:** `LRDP`

**Purpose:** Provide the central Confluence landing page for the LumaRoute beta release.

### Overview

LumaRoute is the core LumaFleet Systems platform for cold-chain delivery operations. It helps regional food and medical distributors plan reliable routes, monitor temperature compliance, guide drivers through delivery tasks, and communicate accurate ETAs to customers.

### Current Release Theme

**Beta readiness for cold-chain delivery visibility.** The current release focuses on active route visibility, temperature telemetry, driver proof of delivery, exception triage, and customer ETA transparency.

### Active Sprints

| Sprint | Dates | Goal | Primary Jira Scope |
| --- | --- | --- | --- |
| Sprint 14 - Cold Chain Visibility Foundation | 2026-06-22 to 2026-07-03 | Establish route, driver, telemetry, and dashboard foundation | LRDP-101, LRDP-102, LRDP-111, LRDP-112, LRDP-121, LRDP-122, LRDP-141 |
| Sprint 15 - Operational Exception Handling | 2026-07-06 to 2026-07-17 | Add exception workflows, ETA updates, notifications, and compliance exports | LRDP-103, LRDP-113, LRDP-123, LRDP-131, LRDP-132, LRDP-133, LRDP-142, LRDP-143, LRDP-153 |

### Quick Links

| Area | Page |
| --- | --- |
| Product direction | Product Vision & North Star Metrics |
| Architecture | System Architecture |
| Quality | QA Strategy and Test Case Catalog |
| Delivery | Sprint 14 Plan and Sprint 15 Plan |
| Operations | Runbook: Temperature Alert Incident |

---

## Page: Product Vision & North Star Metrics

**Owner:** Amara Singh

**Purpose:** Align the team on customer outcomes and measurable success.

### Vision

LumaRoute should become the daily operating system for regional cold-chain delivery teams that need to protect product quality while meeting tight delivery windows.

### North Star Metric

**Protected on-time delivery rate:** Percentage of cold-chain shipments delivered inside the promised window with no unresolved temperature excursion.

### Supporting Metrics

| Metric | Baseline | Beta Target | Related Jira |
| --- | --- | --- | --- |
| Temperature excursion acknowledgement within SLA | 62 percent | 90 percent under 5 minutes | LRDP-123, LRDP-143 |
| On-time stop completion | 89 percent | 96 percent | LRDP-102, LRDP-132 |
| Manual route edits per 100 stops | 18 | 11 or fewer | LRDP-103 |
| Inbound ETA support tickets | 100 index | 65 index | LRDP-131, LRDP-133 |
| Compliance export generation time | 20 minutes manual | Under 3 minutes | LRDP-153 |

### Product Principles

* Dispatchers should see the most urgent operational risk first.
* Drivers should be able to complete delivery work even when connectivity is poor.
* Compliance evidence should be generated from the operational record, not reconstructed after the fact.
* Customers should receive proactive ETA updates before they need to call support.

---

## Page: Personas and User Journeys

**Owner:** Amara Singh

**Purpose:** Keep implementation decisions grounded in realistic user workflows.

### Primary Personas

| Persona | Role | Key Need | Related Work |
| --- | --- | --- | --- |
| Maya Chen | Dispatch Manager | Prioritize route exceptions and publish route changes | LRDP-102, LRDP-103, LRDP-141, LRDP-142 |
| Rafael Ortiz | Driver | Complete route tasks with reliable scan and sync | LRDP-111, LRDP-112, LRDP-113 |
| Priya Nair | Compliance Manager | Prove temperature compliance during audits | LRDP-121, LRDP-123, LRDP-153 |
| Jordan Ellis | Customer Success Lead | Share accurate ETA and delay reason with customers | LRDP-131, LRDP-132, LRDP-133 |

### Journey: Temperature Exception

1. Sensor reading exceeds the configured chilled threshold for the required duration.
2. Telemetry service creates a temperature excursion alert.
3. Exception queue shows the alert as Sev 2 and assigns it to dispatch triage.
4. Dispatcher contacts driver, confirms cooler door is secured, and acknowledges the alert.
5. Compliance manager exports route evidence showing readings, alert, acknowledgement, and resolution.

### Journey: Customer Delay

1. Route falls more than 10 minutes behind projected arrival.
2. ETA service recalculates stop ETA windows.
3. Customer ETA portal displays revised ETA and last-updated timestamp.
4. Customer success sends notification with reason code `TRAFFIC\_INCIDENT`.
5. Notification provider status is stored for support review.

---

## Page: Release Roadmap

**Owner:** Mateo Ruiz

**Purpose:** Show the near-term sequencing for the beta release.

| Release Increment | Target | Theme | Included Work |
| --- | --- | --- | --- |
| Beta 0.8 | Completed before Sprint 14 | Tenant setup and route skeleton | Authentication, base route board, pilot tenant records |
| Beta 0.9 | Sprint 14 and Sprint 15 | Cold-chain visibility and exception handling | LRDP-101 through LRDP-155 |
| Beta 1.0 | Next planned increment | Pilot launch hardening | Alert escalation rules, provider sandbox automation, support playbooks |

### Beta 0.9 Exit Criteria

* All Sev 1 bugs closed.
* No open Sev 2 bugs without approved workaround.
* Driver offline sync passes TC-LR-011 on iOS and Android.
* Customer ETA portal passes token access tests.
* Compliance export includes route, shipment, telemetry, alert, and acknowledgement data.

---

## Page: System Architecture

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

## Page: Service Ownership Matrix

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

## Page: API & Integration Overview

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

## Page: Data Model Overview

**Owner:** Nora Blake

**Purpose:** Explain the core operational objects used across Jira stories and test cases.

| Entity | Description | Important Relationships |
| --- | --- | --- |
| Tenant | Customer account using LumaRoute | Owns users, routes, sensors, shipments |
| Route | Daily assigned delivery run | Has stops, driver, vehicle, route score |
| Stop | Location visited during route | Has tasks, shipments, ETA snapshots |
| Shipment | Deliverable item or package | Has barcode and temperature range |
| Sensor | Physical temperature sensor | Assigned to vehicle, shipment, or route |
| TelemetryReading | Sensor reading at a point in time | Belongs to sensor, tenant, and active route |
| Exception | Operational issue needing triage | May be created from telemetry, ETA, or driver report |
| EtaSnapshot | Current ETA state for a stop | Updated by route progress and delay events |
| ComplianceExport | Generated route evidence file | Includes route, telemetry, alert, and audit data |

---

## Page: Sprint 14 Plan

**Owner:** Mateo Ruiz

**Purpose:** Define Sprint 14 commitments and delivery focus.

### Sprint Goal

Dispatchers and drivers can see a coherent active route state with temperature readings, route health, and driver task progress for pilot tenants.

### Committed Issues

LRDP-101, LRDP-102, LRDP-111, LRDP-112, LRDP-121, LRDP-122, LRDP-141, LRDP-145, LRDP-146.

### Acceptance Focus

* Route import creates valid route, stop, shipment, and temperature data.
* Driver app shows assigned route and supports barcode proof of delivery.
* Telemetry readings appear on route timeline.
* Dispatch route cards sort active risk correctly.
* Observability dashboard surfaces telemetry freshness.

---

## Page: Sprint 14 Review & Retro

**Owner:** Mateo Ruiz

**Purpose:** Capture stakeholder review and retrospective outcomes.

### Review Highlights

* Route health cards reduced dispatcher context switching.
* Temperature timeline made sensor data understandable in route context.
* QA seed data allowed repeatable safe, delayed, stale, and excursion scenarios.

### Retrospective Actions

| Action | Owner | Follow-up |
| --- | --- | --- |
| Keep synthetic fixtures in QA package | Hana Kim | Used by TC-LR-007 through TC-LR-010 |
| Add sync contract review before mobile stories | Mateo Ruiz | Applied to LRDP-113 |
| Standardize acceptance criteria format | Amara Singh | Applied to Sprint 15 stories |

---

## Page: Sprint 15 Plan

**Owner:** Mateo Ruiz

**Purpose:** Define Sprint 15 commitments and scope tradeoffs.

### Sprint Goal

Dispatchers can triage exceptions, customers can see updated ETAs, and compliance managers can export route evidence for pilot deliveries.

### Committed Issues

LRDP-103, LRDP-113, LRDP-123, LRDP-131, LRDP-132, LRDP-133, LRDP-142, LRDP-143, LRDP-147, LRDP-153.

### Scope Tradeoff

Sprint 15 is above normal capacity because driver sync and alert acknowledgement are beta blockers. If LRDP-113 or LRDP-123 overruns, LRDP-153 is the first planned scope tradeoff.

### Acceptance Focus

* Offline driver updates sync without duplicate proof records.
* Temperature excursions create one active alert and preserve acknowledgement audit.
* Customer ETA portal uses expiring stop-specific tokens.
* Delay notifications include reason code and provider status.
* Exception queue supports severity, owner, status, and route filtering.

---

## Page: Sprint 15 Review & Retro

**Owner:** Mateo Ruiz

**Purpose:** Provide a realistic placeholder for Sprint 15 review and retrospective documentation.

### Draft Review Agenda

1. Demo temperature excursion acknowledgement using LRDP-123 and LRDP-143.
2. Demo customer ETA portal and notification flow using LRDP-131, LRDP-132, and LRDP-133.
3. Review open bugs LRDP-151 and LRDP-152.
4. Confirm whether compliance export LRDP-153 remains in sprint scope.

### Draft Retro Prompts

* Did the team manage the intentional sprint stretch transparently?
* Were cross-service workflows tested early enough?
* Did bug severity and priority help triage effectively?
* What should become a release-blocking automated test?

---

## Page: QA Strategy

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

## Page: Test Case Catalog

**Owner:** Hana Kim

**Purpose:** Summarize QA coverage and link to the importable test case CSV.

### Coverage Matrix

| Capability | Test Cases | Jira Stories |
| --- | --- | --- |
| Route import and scoring | TC-LR-001, TC-LR-002, TC-LR-003 | LRDP-101, LRDP-102 |
| Driver workflow | TC-LR-004, TC-LR-005, TC-LR-006, TC-LR-011 | LRDP-111, LRDP-112, LRDP-113 |
| Telemetry and alerts | TC-LR-007, TC-LR-008, TC-LR-009, TC-LR-012, TC-LR-013 | LRDP-121, LRDP-122, LRDP-123, LRDP-124 |
| Customer ETA | TC-LR-014, TC-LR-015, TC-LR-016 | LRDP-131, LRDP-132, LRDP-133 |
| Dispatch exceptions | TC-LR-010, TC-LR-017, TC-LR-018 | LRDP-141, LRDP-142, LRDP-143 |
| Compliance and security | TC-LR-019, TC-LR-020 | LRDP-147, LRDP-153 |

### Import Source

Use `jira_test_cases.csv` as the source for manual QA test records or an Xray/Zephyr import mapping.

---

## Page: Bug Triage Log

**Owner:** Hana Kim

**Purpose:** Track current beta defects and triage decisions.

### Severity Definitions

| Severity | Definition | Example |
| --- | --- | --- |
| Sev 1 | Blocks beta release or can cause customer harm, compliance failure, or duplicate external communication | BUG-008 duplicate SMS |
| Sev 2 | Major workflow broken or misleading operational state with workaround | BUG-003 offline sync retry loop |
| Sev 3 | Usability issue or localized defect with workaround | BUG-002 filter state loss |
| Sev 4 | Cosmetic or low-risk documentation defect | Not currently present |

### Active Triage

| Bug | Severity | Owner | Decision |
| --- | --- | --- | --- |
| BUG-008 / LRDP-152 | Sev 1 | Dev Patel | Release blocker; implement notification idempotency before Beta 0.9 |
| BUG-003 | Sev 2 | Elena Vos | Fix in Sprint 15 before driver pilot |
| BUG-006 / LRDP-151 | Sev 2 | Nora Blake | Fix projection lag or hide stale queue state |
| BUG-004 / LRDP-155 | Sev 2 | Elena Vos | Sprint 14 hotfix due tenant validation concern |

---

## Page: Runbook: Temperature Alert Incident

**Owner:** Theo Martin

**Purpose:** Guide support and operations during a temperature excursion incident.

### Trigger

An active route receives out-of-range sensor readings for the configured duration and creates a Sev 1 or Sev 2 temperature exception.

### Response Steps

1. Open Dispatch Dashboard and filter exception queue by temperature severity.
2. Confirm route id, driver, vehicle, sensor id, shipment temperature range, and latest reading.
3. Contact driver and ask for cooler status, door status, and shipment handling conditions.
4. Acknowledge alert in LumaRoute with factual note.
5. If temperature remains out of range, escalate to compliance manager and customer success.
6. After route completion, export compliance report and attach it to customer support case if needed.

### Escalation

| Condition | Escalate To | SLA |
| --- | --- | --- |
| Sev 1 medical shipment excursion | Compliance manager and operations director | Immediate |
| Sev 2 chilled food excursion over 10 minutes | Dispatch manager | 5 minutes |
| Sensor stale for more than 15 minutes | SRE and dispatcher | 10 minutes |

### Related Jira

LRDP-121, LRDP-123, LRDP-143, LRDP-146, LRDP-153.

---

## Page: Observability Dashboard Guide

**Owner:** Theo Martin

**Purpose:** Explain the telemetry and route operations dashboards.

### Dashboard Panels

| Panel | Description | Alert Threshold |
| --- | --- | --- |
| Telemetry ingest rate | Readings accepted per minute by tenant | Drops below expected route count for 5 minutes |
| Stale sensor count | Active route sensors without readings | Any Sev 1 route stale for 5 minutes |
| Duplicate reading count | Idempotency suppression volume | Sudden spike above baseline |
| Alert creation latency | Time from threshold breach to alert record | Above 30 seconds p95 |
| ETA recalculation latency | Time from delay event to portal update | Above 60 seconds p95 |
| Notification failure rate | Provider failure percentage | Above 3 percent for 10 minutes |

### Incident Correlation

Use route id and tenant id to correlate logs across telemetry ingestion, alert creation, dispatch UI, notification service, and compliance export.

---

## Page: Deployment Checklist

**Owner:** Mateo Ruiz

**Purpose:** Provide a release checklist for Beta 0.9 deployment.

### Pre-Deployment

* Confirm feature flags for pilot tenants.
* Run tenant-aware API contract tests from LRDP-116.
* Run QA smoke tests TC-LR-001, TC-LR-007, TC-LR-010, TC-LR-014, and TC-LR-020.
* Confirm no open Sev 1 bugs.
* Confirm workarounds for any open Sev 2 bugs are documented.

### Deployment

* Apply backward-compatible migrations.
* Deploy services using blue/green rollout.
* Enable `temperatureTimeline` and `exceptionQueueV2` for pilot tenants.
* Keep `driverOfflineSync` limited to QA until LRDP-113 passes acceptance.
* Monitor telemetry freshness and notification failure panels for 30 minutes.

### Post-Deployment

* Run synthetic telemetry seed scenario from LRDP-145.
* Verify route board loads active route health cards.
* Verify expired ETA portal token shows friendly error page after BUG-007 is fixed.
* Capture release notes and link Jira fix version `Beta 0.9`.
