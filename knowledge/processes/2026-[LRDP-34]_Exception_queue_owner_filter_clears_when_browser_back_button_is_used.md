---
id: jira-LRDP-34
type: processes
title: [LRDP-34] Exception queue owner filter clears when browser back button is used
date: 2026-06-17
status: active
supersedes: null
superseded_by: null
tags: ["jira", "lrdp", "exception", "queue", "owner", "filter"]
owner: 
sources:
  - type: jira
    ref: sources/jira/LRDP/[LRDP-34]_Exception_queue_owner_filter_clears_when_browser_back_button_is_used.md
    url: https://erfwagvbe.atlassian.net/browse/LRDP-34
related: []
freshness_check: null
confidence: medium
---
# [LRDP-34] Exception queue owner filter clears when browser back button is used

**Type:** Bug  
**Status:** To Do  
**Priority:** Medium  
**Assignee:** Asmeet Singh  
**Reporter:** Asmeet Singh  
**Labels:** bug, sev-3  

## Description

Mock source key: BUG-002

 

Bug log id: BUG-002

 

Environment:

QA Chrome 125

 

Linked story:

LRDP-142

 

Steps to reproduce:

1. Filter exception queue by owner Maya; 2. Open an exception detail; 3. Click browser back; 4. Observe filter chips and result list

 

Expected result:

Owner filter remains applied after returning to queue

 

Actual result:

Filter chip disappears and queue shows all owners

 

Business impact:

Dispatcher may lose triage context during busy shift

 

Workaround:

Use in-app breadcrumb instead of browser back

 

Target fix:

Sprint 15

 

Acceptance Criteria:

Owner filter remains applied after returning to queue

 

Sprint: Sprint 15 - Operational Exception Handling

Epic Name: 

Epic Link: LRDP-142

Story Points: 

Labels: bug,sev-3

Linked Issues: relates LRDP-142

Fix Version: Beta 0.9

