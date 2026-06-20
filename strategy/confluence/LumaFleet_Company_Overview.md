---
id: confluence-655361
source: confluence
title: LumaFleet Company Overview
url: https://erfwagvbe.atlassian.net/wiki/spaces/LFE/pages/655361/LumaFleet+Company+Overview
info_type: strategy
updated_at: 2026-06-17T15:22:06.540000+00:00
metadata:
  space_key: LFE
  page_id: 655361
---
# LumaFleet Company Overview

# LumaFleet Systems Company Overview

## Company Profile

**Company:** LumaFleet Systems

**Industry:** Logistics technology for regional cold-chain delivery

**Core Product:** LumaRoute

**Product Type:** Multi-tenant SaaS platform for dispatchers, drivers, operations managers, and customer success teams

**Mock Jira Project:** LumaRoute Delivery Platform, key `LRDP`

**Mock Confluence Space:** LumaFleet Engineering, key `LFE`

LumaFleet Systems builds software for regional food distributors, specialty pharmacies, and medical logistics providers that must prove temperature compliance while delivering perishable or regulated goods on time. The company focuses on customers with fleets of 25-400 vehicles that need modern dispatch tooling without building a large in-house engineering team.

## Mission

LumaFleet helps regional distributors reduce spoilage, improve delivery reliability, and provide real-time compliance visibility across every cold-chain route.

## Core Product: LumaRoute

LumaRoute is a delivery operations platform that combines route planning, driver execution, sensor telemetry, customer ETA visibility, and exception management. It is designed for dispatch teams that need fast decisions when traffic changes, a cooler temperature rises, or a customer needs a revised delivery window.

### Primary Capabilities

* \*\*Route Optimization:\*\* Create efficient routes using shipment windows, vehicle capacity, service times, traffic buffers, and cold-chain constraints.
* \*\*Driver Mobile Workflow:\*\* Guide drivers through route tasks, capture proof of delivery, support exception reporting, and sync offline activity.
* \*\*Temperature Compliance Monitoring:\*\* Ingest IoT sensor readings, detect excursions, alert dispatchers, and maintain a route-level audit trail.
* \*\*Customer ETA Portal:\*\* Share live ETA windows and delay notifications with customer service teams and end customers.
* \*\*Dispatch Operations Dashboard:\*\* Provide real-time route health, exception queues, SLA status, and triage workflows.

## Target Customers

| Segment | Typical User | Pain Point | Desired Outcome |
| --- | --- | --- | --- |
| Regional food distributors | Dispatch manager | Manual route changes create late deliveries and spoilage risk | Reliable daily dispatch with real-time exception handling |
| Specialty pharmacies | Compliance manager | Temperature records are scattered across vendor portals | Continuous route-level proof of compliance |
| Medical courier networks | Operations director | Drivers call dispatch for every delivery problem | Self-service driver workflow with auditable issue reporting |
| Customer service teams | Account coordinator | Customers ask for ETAs that dispatch cannot confidently provide | Live ETA visibility and proactive delay messages |

## Personas

### Maya Chen, Dispatch Manager

* \*\*Goals:\*\* Release routes by 6:00 AM, monitor active routes, resolve exceptions quickly.
* \*\*Frustrations:\*\* Uses spreadsheets and driver calls to understand route health.
* \*\*LumaRoute Needs:\*\* Route comparison, live alerts, exception queue, clear driver status.
* \*\*Success Metric:\*\* 95 percent of routes dispatched without manual rework.

### Rafael Ortiz, Fleet Driver

* \*\*Goals:\*\* Complete stops in the correct order, keep deliveries within required temperature range, provide proof of delivery.
* \*\*Frustrations:\*\* App connectivity drops in loading docks and rural delivery zones.
* \*\*LumaRoute Needs:\*\* Offline route tasks, simple exception reporting, barcode scan confirmation.
* \*\*Success Metric:\*\* 98 percent task completion sync within 10 minutes of reconnecting.

### Priya Nair, Compliance Manager

* \*\*Goals:\*\* Prove route-level temperature compliance during audits.
* \*\*Frustrations:\*\* Sensor exports are not tied to shipment or delivery records.
* \*\*LumaRoute Needs:\*\* Continuous temperature timeline, threshold rules, excursion reports.
* \*\*Success Metric:\*\* Audit report generated in under 3 minutes.

### Jordan Ellis, Customer Success Lead

* \*\*Goals:\*\* Give customers accurate delivery windows and delay explanations.
* \*\*Frustrations:\*\* Customer portal data lags behind dispatch reality.
* \*\*LumaRoute Needs:\*\* Customer-facing ETA page, branded notifications, route delay reason codes.
* \*\*Success Metric:\*\* 35 percent fewer inbound "where is my delivery" calls.

## Product Goals

| Goal | KPI | Target |
| --- | --- | --- |
| Reduce spoilage risk | Temperature excursions acknowledged within SLA | 90 percent acknowledged in under 5 minutes |
| Improve on-time performance | Completed stops inside promised delivery window | 96 percent by end of beta |
| Improve dispatcher efficiency | Manual route edits per 100 stops | Reduce by 40 percent |
| Improve customer transparency | Inbound ETA support tickets | Reduce by 35 percent |
| Improve audit readiness | Time to produce route compliance report | Under 3 minutes |

## Release Context

The mock dataset represents two consecutive delivery-team sprints during a beta program for three pilot customers:

* \*\*Sprint 14: Cold Chain Visibility Foundation\*\*

- Focuses on ingesting temperature data, displaying route status, and giving drivers a reliable task list.

* \*\*Sprint 15: Operational Exception Handling\*\*

- Builds alert acknowledgement, ETA updates, customer notifications, and deeper dispatch triage.

## Product Vocabulary

| Term | Definition |
| --- | --- |
| Route | A planned sequence of stops assigned to a vehicle and driver for a delivery shift |
| Stop | A customer location or transfer point with delivery tasks |
| Shipment | One or more packages requiring delivery and optional temperature constraints |
| Excursion | A temperature reading outside the configured safe range |
| Exception | Any route event needing human attention, such as delay, failed scan, or sensor breach |
| ETA | Estimated arrival time for a route stop or customer delivery |
| Proof of Delivery | Evidence that a delivery was completed, such as signature, barcode, photo, or timestamp |

## Mock Team

| Name | Role | Jira Usage |
| --- | --- | --- |
| Amara Singh | Product Manager | Reporter for product stories and epic owner |
| Mateo Ruiz | Engineering Manager | Sprint planning, dependency owner |
| Nora Blake | Backend Engineer | Route, telemetry, and alert services |
| Dev Patel | Frontend Engineer | Dispatch dashboard and customer portal |
| Elena Vos | Mobile Engineer | Driver workflow and offline sync |
| Hana Kim | QA Lead | Test case ownership and bug triage |
| Theo Martin | SRE | Observability, deployment, and alert runbooks |
