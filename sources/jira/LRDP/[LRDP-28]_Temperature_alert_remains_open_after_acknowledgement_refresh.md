---
id: jira-LRDP-28
source: jira
title: [LRDP-28] Temperature alert remains open after acknowledgement refresh
url: https://erfwagvbe.atlassian.net/browse/LRDP-28
ingested_at: 2026-06-28T19:16:28.511428+00:00
updated_at: 2026-06-17T20:51:15.317000+05:30
metadata:
  project_key: LRDP
  issue_key: LRDP-28
  status: To Do
  issue_type: Bug
  priority: High
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

