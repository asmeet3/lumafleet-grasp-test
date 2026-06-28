---
id: jira-LRDP-33
type: processes
title: [LRDP-33] Temperature timeline renders points one hour early during daylight savings transition
date: 2026-06-17
status: active
supersedes: null
superseded_by: null
tags: ["jira", "lrdp", "temperature", "timeline", "renders", "points"]
owner: 
sources:
  - type: jira
    ref: sources/jira/LRDP/[LRDP-33]_Temperature_timeline_renders_points_one_hour_early_during_daylight_savings_transition.md
    url: https://erfwagvbe.atlassian.net/browse/LRDP-33
related: []
freshness_check: null
confidence: medium
---
# [LRDP-33] Temperature timeline renders points one hour early during daylight savings transition

**Type:** Bug  
**Status:** To Do  
**Priority:** High  
**Assignee:** Asmeet Singh  
**Reporter:** Asmeet Singh  
**Labels:** bug, sev-2  

## Description

Mock source key: BUG-001

 

Bug log id: BUG-001

 

Environment:

QA Chrome 125, tenant timezone America/New_York

 

Linked story:

LRDP-122

 

Steps to reproduce:

1. Load route RT-DST-001 with readings around daylight savings boundary; 2. Open route detail temperature timeline; 3. Compare point labels with raw telemetry timestamps

 

Expected result:

Timeline labels match tenant timezone and raw telemetry converted time

 

Actual result:

Readings after the transition appear one hour earlier than expected

 

Business impact:

Compliance review may misinterpret excursion duration

 

Workaround:

Use raw telemetry export for audit review until fixed

 

Target fix:

Sprint 15

 

Acceptance Criteria:

Timeline labels match tenant timezone and raw telemetry converted time

 

Sprint: Sprint 14 - Cold Chain Visibility Foundation

Epic Name: 

Epic Link: LRDP-122

Story Points: 

Labels: bug,sev-2

Linked Issues: relates LRDP-122

Fix Version: Beta 0.9

