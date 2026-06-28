---
id: jira-LRDP-15
type: projects
title: [LRDP-15] Ingest temperature sensor readings for active routes
date: 2026-06-17
status: active
supersedes: null
superseded_by: null
tags: ["jira", "lrdp", "ingest", "temperature", "sensor", "readings"]
owner: 
sources:
  - type: jira
    ref: sources/jira/LRDP/[LRDP-15]_Ingest_temperature_sensor_readings_for_active_routes.md
    url: https://erfwagvbe.atlassian.net/browse/LRDP-15
related: []
freshness_check: null
confidence: medium
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

