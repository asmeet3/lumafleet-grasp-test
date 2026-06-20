---
id: jira-LRDP-18
source: jira
title: [LRDP-18] Add telemetry idempotency key handling
url: https://erfwagvbe.atlassian.net/browse/LRDP-18
info_type: features
updated_at: 2026-06-17T20:51:02.327000+05:30
metadata:
  project_key: LRDP
  issue_key: LRDP-18
  status: To Do
  issue_type: Task
  priority: High
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

