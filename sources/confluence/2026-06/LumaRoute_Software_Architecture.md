---
id: confluence-688129
source: confluence
title: LumaRoute Software Architecture
url: https://erfwagvbe.atlassian.net/wiki/spaces/LFE/pages/688129/LumaRoute+Software+Architecture
ingested_at: 2026-06-28T19:15:41.985771+00:00
updated_at: 2026-06-17T15:22:07.490000+00:00
metadata:
  space_key: LFE
  page_id: 688129
---
# LumaRoute Software Architecture

# LumaRoute High-Level Software Architecture

## Architecture Summary

LumaRoute is a cloud-hosted, multi-tenant SaaS platform with web, mobile, API, telemetry, and notification layers. The product is optimized for active delivery operations where dispatchers need live route health, drivers need resilient workflows, and compliance teams need auditable temperature history.

## Logical Architecture

```
flowchart LR
  DriverApp["Driver Mobile App"] --> APIGateway["API Gateway"]
  DispatchWeb["Dispatch Web App"] --> APIGateway
  CustomerPortal["Customer ETA Portal"] --> APIGateway
  Sensors["Bluetooth/LTE Temp Sensors"] --> TelemetryIngest["Telemetry Ingest Service"]
  APIGateway --> Auth["Identity and Tenant Service"]
  APIGateway --> RouteSvc["Route Planning Service"]
  APIGateway --> StopSvc["Stop Execution Service"]
  APIGateway --> AlertSvc["Alert and Exception Service"]
  APIGateway --> EtaSvc["ETA Service"]
  TelemetryIngest --> Stream["Event Stream"]
  Stream --> AlertSvc
  Stream --> EtaSvc
  RouteSvc --> Postgres["PostgreSQL"]
  StopSvc --> Postgres
  AlertSvc --> Postgres
  EtaSvc --> Redis["Redis Cache"]
  TelemetryIngest --> TimeSeries["Time-Series Store"]
  AlertSvc --> Notify["Notification Service"]
  Notify --> EmailSms["Email/SMS Provider"]
  Services["All Services"] --> Observability["Logs, Metrics, Traces"]
```

## Main Clients

### Dispatch Web App

* \*\*Technology assumption:\*\* React with TypeScript.
* \*\*Users:\*\* Dispatch managers, route coordinators, operations managers.
* \*\*Core screens:\*\* Route board, active route map, exception queue, temperature detail drawer, ETA override panel.
* \*\*Key sprint work:\*\* LRDP-141, LRDP-142, LRDP-143, LRDP-144.

### Driver Mobile App

* \*\*Technology assumption:\*\* React Native with local encrypted storage.
* \*\*Users:\*\* Delivery drivers.
* \*\*Core screens:\*\* Today's route, stop task checklist, barcode scan, exception report, sync status.
* \*\*Key sprint work:\*\* LRDP-111, LRDP-112, LRDP-113, LRDP-114.

### Customer ETA Portal

* \*\*Technology assumption:\*\* Server-rendered public token page backed by ETA APIs.
* \*\*Users:\*\* Customer service agents and delivery recipients.
* \*\*Core screens:\*\* Branded ETA page, stop status, delay reason, notification preference.
* \*\*Key sprint work:\*\* LRDP-131, LRDP-132, LRDP-133.

## Services

| Service | Responsibility | Primary Store | Relevant Issues |
| --- | --- | --- | --- |
| Identity and Tenant Service | Authentication, user roles, tenant isolation | PostgreSQL | LRDP-116, LRDP-147 |
| Route Planning Service | Route creation, stop sequencing, route score calculation | PostgreSQL | LRDP-101, LRDP-102, LRDP-103 |
| Stop Execution Service | Driver task state, proof of delivery, offline sync reconciliation | PostgreSQL, mobile local store | LRDP-111, LRDP-112, LRDP-113 |
| Telemetry Ingest Service | Receive sensor readings, validate device identity, publish telemetry events | Time-series store, event stream | LRDP-121, LRDP-122, LRDP-124 |
| Alert and Exception Service | Detect excursions, create alerts, assign and acknowledge exceptions | PostgreSQL, event stream | LRDP-123, LRDP-143, LRDP-151 |
| ETA Service | Calculate current ETAs using route progress, traffic buffer, and exceptions | Redis, PostgreSQL | LRDP-131, LRDP-132 |
| Notification Service | Send email/SMS ETA and alert notifications | Provider API logs | LRDP-133, LRDP-152 |
| Reporting Service | Generate compliance exports and operational reports | PostgreSQL, object storage | LRDP-153 |

## Data Model Overview

| Entity | Description | Important Fields |
| --- | --- | --- |
| Tenant | Customer organization using LumaRoute | tenant\_id, plan, compliance\_profile |
| Route | Daily delivery route assigned to a vehicle and driver | route\_id, route\_date, driver\_id, vehicle\_id, status |
| Stop | Delivery location within a route | stop\_id, route\_id, sequence, service\_window, status |
| Shipment | Deliverable package tied to a stop | shipment\_id, stop\_id, temperature\_range, barcode |
| Sensor | Temperature sensor associated with vehicle or shipment | sensor\_id, tenant\_id, calibration\_status |
| TelemetryReading | Point-in-time sensor reading | sensor\_id, route\_id, timestamp, temperature\_c |
| Exception | Operational event needing attention | exception\_id, type, severity, owner, status |
| EtaSnapshot | Current ETA calculation for a stop | stop\_id, eta\_start, eta\_end, confidence |

## Integration Points

| Integration | Direction | Usage | Failure Handling |
| --- | --- | --- | --- |
| Sensor gateway | Inbound | Receives temperature readings every 60 seconds during active route | Retry with idempotency key; flag stale sensor after 5 minutes |
| Mapping provider | Outbound | Distance, travel time, geocoding, traffic buffer | Cache last successful matrix; display degraded ETA confidence |
| Email/SMS provider | Outbound | Customer ETA messages and dispatcher alerts | Queue retry; surface failed notification in exception queue |
| Customer order system | Inbound batch/API | Imports shipments and service windows | Reject invalid payload with row-level validation report |
| SSO provider | Inbound/outbound | Enterprise identity via SAML/OIDC | Fall back to password login only for pilot tenants |

## Security and Compliance

* Tenant isolation is enforced at API middleware and database query scope.
* Driver app stores route data in encrypted local storage and purges completed route data after successful sync.
* Public customer ETA pages use expiring delivery tokens and never expose full route manifests.
* All compliance exports include route, shipment, sensor, alert, and acknowledgement audit events.
* PII fields are minimized in telemetry streams; sensor events use route and sensor identifiers.

## Observability

| Signal | Example Metric or Log |
| --- | --- |
| Availability | API success rate by tenant and client |
| Telemetry freshness | Seconds since last reading per active route |
| ETA reliability | ETA confidence and route delay prediction delta |
| Driver sync health | Offline queue length and sync failure count |
| Alert workflow | Excursion detected to acknowledgement duration |
| Notification delivery | Provider success, retry, and failure rates |

## Deployment Model

* \*\*Environments:\*\* dev, qa, staging, production.
* \*\*Release cadence:\*\* biweekly sprint release, hotfixes as needed for Sev 1 or Sev 2 bugs.
* \*\*Deployment strategy:\*\* Blue/green API deployment with feature flags for customer-facing features.
* \*\*Database changes:\*\* Backward-compatible migrations before application rollout.
* \*\*Feature flags:\*\* `temperatureTimeline`, `driverOfflineSync`, `customerEtaPortal`, `exceptionQueueV2`.

## Sprint Architecture Focus

### Sprint 14

Sprint 14 establishes the telemetry and dispatch visibility foundation. The main delivery thread connects route import, sensor readings, route health status, driver task execution, and baseline QA coverage.

### Sprint 15

Sprint 15 builds on the foundation by adding exception acknowledgement, customer ETA notifications, operational dashboards, and compliance exports. This sprint introduces more cross-service workflows and requires careful test coverage around event timing and notification retries.
