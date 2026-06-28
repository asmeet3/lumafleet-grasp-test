---
id: confluence-720929
source: confluence
title: Runbook: Temperature Alert Incident
url: https://erfwagvbe.atlassian.net/wiki/spaces/LFE/pages/720929/Runbook+Temperature+Alert+Incident
ingested_at: 2026-06-28T19:15:55.514809+00:00
updated_at: 2026-06-17T15:23:20.290000+00:00
metadata:
  space_key: LFE
  page_id: 720929
---
# Runbook: Temperature Alert Incident

# Runbook: Temperature Alert Incident

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
