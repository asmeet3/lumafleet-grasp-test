---
id: confluence-163975
source: confluence
title: LumaRoute Sprint Plan
url: https://erfwagvbe.atlassian.net/wiki/spaces/LFE/pages/163975/LumaRoute+Sprint+Plan
ingested_at: 2026-06-28T19:15:18.549728+00:00
updated_at: 2026-06-17T15:22:08.481000+00:00
metadata:
  space_key: LFE
  page_id: 163975
---
# LumaRoute Sprint Plan

# LumaRoute Two-Sprint Delivery Plan

## Program Context

**Project:** LumaRoute Delivery Platform (`LRDP`)

**Release Theme:** Beta readiness for cold-chain delivery visibility

**Team Capacity Assumption:** 42-46 story points per sprint across backend, frontend, mobile, QA, and SRE

**Definition of Ready:** Story has user value, acceptance criteria, data/test needs, dependencies, and target component.

**Definition of Done:** Code merged, unit and integration checks passing, QA test cases executed, feature flag reviewed, observability updated, and Confluence page updated when workflow changes.

## Sprint 14: Cold Chain Visibility Foundation

**Dates:** 2026-06-22 to 2026-07-03

**Sprint Goal:** Dispatchers and drivers can see a coherent active route state with temperature readings, route health, and driver task progress for pilot tenants.

### Committed Scope

| Issue | Type | Summary | Points | Owner |
| --- | --- | --- | --- | --- |
| LRDP-101 | Story | Import daily route manifest with shipment temperature requirements | 5 | Nora Blake |
| LRDP-102 | Story | Calculate route score using service windows and cold-chain risk | 8 | Nora Blake |
| LRDP-111 | Story | Display today's route and stop checklist in driver mobile app | 5 | Elena Vos |
| LRDP-112 | Story | Capture barcode scan proof of delivery | 5 | Elena Vos |
| LRDP-121 | Story | Ingest temperature sensor readings for active routes | 8 | Nora Blake |
| LRDP-122 | Story | Show route temperature timeline in dispatch dashboard | 5 | Dev Patel |
| LRDP-141 | Story | Display active route health cards on dispatch dashboard | 5 | Dev Patel |
| LRDP-145 | Task | Add synthetic telemetry seed data for QA | 3 | Hana Kim |
| LRDP-146 | Task | Create observability dashboard for telemetry freshness | 3 | Theo Martin |

**Committed Points:** 47

### Dependencies and Risks

| Item | Risk | Mitigation |
| --- | --- | --- |
| Sensor gateway payload | Pilot sensors may send duplicate readings | Use idempotency key and timestamp tolerance in LRDP-121 |
| Mobile connectivity | Drivers may lose signal during scan workflow | Defer full offline sync to LRDP-113 in Sprint 15, but persist in-progress task state |
| Route scoring | Mapping provider limits may affect batch scoring | Cache matrix lookups and cap recalculation frequency |
| Dashboard load | Active route cards may be noisy for large tenants | Show top severity route status and allow detail drawer drill-down |

### Demo Script

1. Import a daily route manifest for tenant `NORTHSTAR\_FOODS`.
2. Open dispatch dashboard and confirm route health cards show pending, active, and at-risk routes.
3. Start a route in the driver app and complete a barcode scan for stop `NSF-STOP-004`.
4. Stream synthetic temperature readings and show the route temperature timeline.
5. Trigger a high temperature reading and confirm the route card changes to at-risk.

### Sprint 14 Review Notes

* Stakeholders liked the route health card because it reduced scanning across multiple tabs.
* Compliance users requested clearer threshold labels on the temperature timeline.
* Drivers requested an offline indicator before barcode scan submission.

### Sprint 14 Retrospective

| Went Well | Could Improve | Action |
| --- | --- | --- |
| Route, telemetry, and dashboard work stayed connected through shared fixtures | Test data setup took longer than expected | Keep synthetic route fixtures in QA seed package |
| QA found duplicate sensor events before release | Mobile and backend sync assumptions were discovered late | Add sync contract review to story kickoff |
| Observability dashboard made telemetry freshness visible | Acceptance criteria varied in detail | Use a standard AC format for Sprint 15 stories |

## Sprint 15: Operational Exception Handling

**Dates:** 2026-07-06 to 2026-07-17

**Sprint Goal:** Dispatchers can triage exceptions, customers can see updated ETAs, and compliance managers can export route evidence for pilot deliveries.

### Committed Scope

| Issue | Type | Summary | Points | Owner |
| --- | --- | --- | --- | --- |
| LRDP-103 | Story | Compare optimized route with dispatcher manual edits | 5 | Dev Patel |
| LRDP-113 | Story | Sync driver task updates after offline period | 8 | Elena Vos |
| LRDP-123 | Story | Create temperature excursion alert with acknowledgement workflow | 8 | Nora Blake |
| LRDP-131 | Story | Generate customer ETA portal link per stop | 5 | Dev Patel |
| LRDP-132 | Story | Update ETA when route delay exceeds threshold | 8 | Nora Blake |
| LRDP-133 | Story | Send customer delay notification with reason code | 5 | Dev Patel |
| LRDP-142 | Story | Add exception queue filters for severity and owner | 5 | Dev Patel |
| LRDP-143 | Story | Assign exception to dispatcher and record resolution note | 5 | Dev Patel |
| LRDP-153 | Story | Export route compliance report as CSV | 5 | Nora Blake |
| LRDP-147 | Task | Add role permission matrix for dispatch and compliance users | 3 | Mateo Ruiz |

**Committed Points:** 57

**Capacity Note:** Sprint 15 is intentionally stretched in the mock data because LRDP-113 and LRDP-123 are high-value beta blockers. LRDP-153 is the planned scope tradeoff if alert workflow overruns.

### Dependencies and Risks

| Item | Risk | Mitigation |
| --- | --- | --- |
| ETA provider latency | ETA updates could be delayed during peak route recalculation | Use async recalculation and show last updated timestamp |
| Notification provider | SMS delivery failures could create customer confusion | Store provider status and retry failed notifications |
| Exception permissions | Compliance users may need read access but not assignment rights | Implement role matrix in LRDP-147 before final QA |
| Offline sync conflicts | Driver may edit stop status while dispatcher resolves exception | Server keeps audit trail and applies last valid state transition |

### Demo Script

1. Start route `RT-2026-0710-NF-022` with one active temperature sensor.
2. Simulate a temperature excursion above configured threshold.
3. Confirm exception appears in queue, assign it to Maya, acknowledge it, and add resolution note.
4. Delay a route by 18 minutes and show customer ETA portal updating.
5. Send customer delay notification with reason code `TRAFFIC\_INCIDENT`.
6. Export route compliance CSV and verify it includes sensor timeline and acknowledgement history.

### Sprint 15 Review Notes

* Customer ETA portal reduced support escalation during pilot simulation.
* Exception queue filters made Sev 1 and Sev 2 work more visible.
* Stakeholders requested future escalation rules for unacknowledged alerts.

### Sprint 15 Retrospective

| Went Well | Could Improve | Action |
| --- | --- | --- |
| End-to-end alert workflow helped product and QA align quickly | Sprint commitment exceeded normal capacity | Use explicit tradeoff candidate during sprint planning |
| ETA portal was demo-ready with realistic delay data | Notification retries need deeper automated coverage | Add provider sandbox test suite next sprint |
| Compliance export connected product value to audit workflow | Role permissions were reviewed late | Schedule permissions review before implementation starts |
