---
id: jira-LRDP-18
type: projects
title: [LRDP-18] Add telemetry idempotency key handling
date: 2026-06-17
status: active
supersedes: null
superseded_by: null
tags: ["jira", "lrdp", "add", "telemetry", "idempotency", "key"]
owner: 
sources:
  - type: jira
    ref: sources/jira/LRDP/[LRDP-18]_Add_telemetry_idempotency_key_handling.md
    url: https://erfwagvbe.atlassian.net/browse/LRDP-18
related: []
freshness_check: null
confidence: medium
---
# [LRDP-18] Add telemetry idempotency key handling

**Type:** Task  
**Status:** To Do  
**Priority:** High  
**Assignee:** Asmeet Singh  
**Reporter:** Asmeet Singh  
**Labels:** idempotency, telemetry  

## Description

Mock source key: LRDP-124

 

Prevent duplicate temperature readings from creating duplicate timeline points or alerts.

 

Acceptance Criteria:

Same tenant, sensor, timestamp, and reading id combination stores one reading; duplicate attempts return existing reading reference.

 

Sprint: Sprint 14 - Cold Chain Visibility Foundation

Epic Name: 

Epic Link: LRDP-120

Story Points: 3

Labels: telemetry,idempotency

Linked Issues: parent LRDP-121

Fix Version: Beta 0.9

