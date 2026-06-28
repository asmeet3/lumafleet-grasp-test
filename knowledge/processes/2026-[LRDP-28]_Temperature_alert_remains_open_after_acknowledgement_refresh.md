---
id: jira-LRDP-28
type: processes
title: [LRDP-28] Temperature alert remains open after acknowledgement refresh
date: 2026-06-17
status: active
supersedes: null
superseded_by: null
tags: ["jira", "lrdp", "temperature", "alert", "remains", "open"]
owner: 
sources:
  - type: jira
    ref: sources/jira/LRDP/[LRDP-28]_Temperature_alert_remains_open_after_acknowledgement_refresh.md
    url: https://erfwagvbe.atlassian.net/browse/LRDP-28
related: []
freshness_check: null
confidence: medium
---
# [LRDP-28] Temperature alert remains open after acknowledgement refresh

**Type:** Bug  
**Status:** To Do  
**Priority:** High  
**Assignee:** Asmeet Singh  
**Reporter:** Asmeet Singh  
**Labels:** alerts, bug  

## Description

Mock source key: LRDP-151

 

After acknowledging a temperature excursion, refreshing the exception queue shows the alert as open again for approximately 30 seconds.

 

Acceptance Criteria:

Acknowledged alert remains acknowledged after page refresh; queue state matches audit history within 3 seconds.

 

Sprint: Sprint 15 - Operational Exception Handling

Epic Name: 

Epic Link: LRDP-120

Story Points: 

Labels: bug,alerts

Linked Issues: relates LRDP-123

Fix Version: Beta 0.9

