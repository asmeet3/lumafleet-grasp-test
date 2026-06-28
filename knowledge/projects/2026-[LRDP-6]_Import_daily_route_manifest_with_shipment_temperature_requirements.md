---
id: jira-LRDP-6
type: projects
title: [LRDP-6] Import daily route manifest with shipment temperature requirements
date: 2026-06-17
status: active
supersedes: null
superseded_by: null
tags: ["jira", "lrdp", "import", "daily", "route", "manifest"]
owner: 
sources:
  - type: jira
    ref: sources/jira/LRDP/[LRDP-6]_Import_daily_route_manifest_with_shipment_temperature_requirements.md
    url: https://erfwagvbe.atlassian.net/browse/LRDP-6
related: []
freshness_check: null
confidence: medium
---
# [LRDP-6] Import daily route manifest with shipment temperature requirements

**Type:** Story  
**Status:** To Do  
**Priority:** High  
**Assignee:** Asmeet Singh  
**Reporter:** Asmeet Singh  
**Labels:** import, routes, temperature  

## Description

Mock source key: LRDP-101

 

As a dispatch manager, I want to import a daily route manifest so that LumaRoute can create routes, stops, shipments, and temperature constraints from the customer order system.

 

Acceptance Criteria:

Given a valid CSV manifest when it is uploaded then routes, stops, shipments, and temperature ranges are created; invalid rows produce row-level errors without blocking valid rows; duplicate manifest upload is idempotent by external route id.

 

Sprint: Sprint 14 - Cold Chain Visibility Foundation

Epic Name: 

Epic Link: LRDP-100

Story Points: 5

Labels: import,routes,temperature

Linked Issues: blocks LRDP-102; relates LRDP-145

Fix Version: Beta 0.9

