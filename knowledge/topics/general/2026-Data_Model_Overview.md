---
id: confluence-983041
type: topics
title: Data Model Overview
date: 2026-06-17
status: active
supersedes: null
superseded_by: null
tags: ["confluence", "data", "model", "overview"]
owner: 
sources:
  - type: confluence
    ref: sources/confluence/2026-06/Data_Model_Overview.md
    url: https://erfwagvbe.atlassian.net/wiki/spaces/LFE/pages/983041/Data+Model+Overview
related: []
freshness_check: null
confidence: medium
---
# Data Model Overview

# Data Model Overview

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
