---
id: jira-LRDP-15
source: jira
title: [LRDP-15] Ingest temperature sensor readings for active routes
url: https://erfwagvbe.atlassian.net/browse/LRDP-15
ingested_at: 2026-06-28T19:15:35.079258+00:00
updated_at: 2026-06-17T20:50:58.175000+05:30
metadata:
  project_key: LRDP
  issue_key: LRDP-15
  status: To Do
  issue_type: Story
  priority: Highest
---
# [LRDP-15] Ingest temperature sensor readings for active routes

**Type:** Story  
**Status:** To Do  
**Priority:** Highest  
**Assignee:** Asmeet Singh  
**Reporter:** Asmeet Singh  
**Labels:** telemetry, temperature  

## Description

Mock source key: LRDP-121

 

As a compliance manager, I want sensor readings associated with active routes so that route temperature history is continuously captured.

 

Acceptance Criteria:

Telemetry endpoint validates sensor id and tenant; reading is associated to active route when device assignment exists; duplicate reading id is ignored; stale sensor metric is emitted after five minutes without readings.

 

Sprint: Sprint 14 - Cold Chain Visibility Foundation

Epic Name: 

Epic Link: LRDP-120

Story Points: 8

Labels: telemetry,temperature

Linked Issues: blocks LRDP-122; blocks LRDP-123

Fix Version: Beta 0.9

