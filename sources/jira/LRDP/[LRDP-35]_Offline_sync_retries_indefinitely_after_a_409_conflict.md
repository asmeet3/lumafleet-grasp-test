---
id: jira-LRDP-35
source: jira
title: [LRDP-35] Offline sync retries indefinitely after a 409 conflict
url: https://erfwagvbe.atlassian.net/browse/LRDP-35
ingested_at: 2026-06-28T19:16:49.721409+00:00
updated_at: 2026-06-17T20:54:31.825000+05:30
metadata:
  project_key: LRDP
  issue_key: LRDP-35
  status: To Do
  issue_type: Bug
  priority: Highest
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

