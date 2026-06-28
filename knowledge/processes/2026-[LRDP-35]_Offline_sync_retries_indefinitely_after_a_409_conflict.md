---
id: jira-LRDP-35
type: processes
title: [LRDP-35] Offline sync retries indefinitely after a 409 conflict
date: 2026-06-17
status: active
supersedes: null
superseded_by: null
tags: ["jira", "lrdp", "offline", "sync", "retries", "indefinitely"]
owner: 
sources:
  - type: jira
    ref: sources/jira/LRDP/[LRDP-35]_Offline_sync_retries_indefinitely_after_a_409_conflict.md
    url: https://erfwagvbe.atlassian.net/browse/LRDP-35
related: []
freshness_check: null
confidence: medium
---
# [LRDP-35] Offline sync retries indefinitely after a 409 conflict

**Type:** Bug  
**Status:** To Do  
**Priority:** Highest  
**Assignee:** Asmeet Singh  
**Reporter:** Asmeet Singh  
**Labels:** bug, sev-2  

## Description

Mock source key: BUG-003

 

Bug log id: BUG-003

 

Environment:

Android 14 emulator, intermittent network profile

 

Linked story:

LRDP-113

 

Steps to reproduce:

1. Go offline; 2. Complete stop task; 3. Change same stop status from dispatch; 4. Reconnect mobile app; 5. Observe sync status

 

Expected result:

Conflict is shown to driver with retry or discard option and queue stops automatic retry

 

Actual result:

App continues retrying every 10 seconds and battery usage spikes

 

Business impact:

Driver may not trust task status and dispatch receives noisy sync failures

 

Workaround:

Force close app and ask dispatch to manually verify stop

 

Target fix:

Sprint 15

 

Acceptance Criteria:

Conflict is shown to driver with retry or discard option and queue stops automatic retry

 

Sprint: Sprint 15 - Operational Exception Handling

Epic Name: 

Epic Link: LRDP-113

Story Points: 

Labels: bug,sev-2

Linked Issues: relates LRDP-113

Fix Version: Beta 0.9

