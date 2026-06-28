---
id: jira-LRDP-6
source: jira
title: [LRDP-6] Import daily route manifest with shipment temperature requirements
url: https://erfwagvbe.atlassian.net/browse/LRDP-6
ingested_at: 2026-06-28T19:15:04.903702+00:00
updated_at: 2026-06-17T20:50:46.114000+05:30
metadata:
  project_key: LRDP
  issue_key: LRDP-6
  status: To Do
  issue_type: Story
  priority: High
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

