---
id: confluence-884737
source: confluence
title: Personas and User Journeys
url: https://erfwagvbe.atlassian.net/wiki/spaces/LFE/pages/884737/Personas+and+User+Journeys
ingested_at: 2026-06-28T19:16:17.041298+00:00
updated_at: 2026-06-17T15:23:07.329000+00:00
metadata:
  space_key: LFE
  page_id: 884737
---
# Personas and User Journeys

# Personas and User Journeys

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
