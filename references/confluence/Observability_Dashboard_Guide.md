---
id: confluence-1081345
source: confluence
title: Observability Dashboard Guide
url: https://erfwagvbe.atlassian.net/wiki/spaces/LFE/pages/1081345/Observability+Dashboard+Guide
info_type: references
updated_at: 2026-06-17T15:23:21.172000+00:00
metadata:
  space_key: LFE
  page_id: 1081345
---
# Observability Dashboard Guide

# Observability Dashboard Guide

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
