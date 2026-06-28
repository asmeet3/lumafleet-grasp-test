---
id: jira-LRDP-38
source: jira
title: [LRDP-38] Compliance export omits acknowledgement user display name
url: https://erfwagvbe.atlassian.net/browse/LRDP-38
ingested_at: 2026-06-28T19:16:55.848352+00:00
updated_at: 2026-06-17T20:54:37.142000+05:30
metadata:
  project_key: LRDP
  issue_key: LRDP-38
  status: To Do
  issue_type: Bug
  priority: Low
---
# [LRDP-38] Compliance export omits acknowledgement user display name

**Type:** Bug  
**Status:** To Do  
**Priority:** Low  
**Assignee:** Asmeet Singh  
**Reporter:** Asmeet Singh  
**Labels:** bug, sev-3  

## Description

Mock source key: BUG-009

 

Bug log id: BUG-009

 

Environment:

QA Chrome 125

 

Linked story:

LRDP-153

 

Steps to reproduce:

1. Acknowledge excursion as Maya; 2. Export route compliance CSV; 3. Inspect acknowledgement section

 

Expected result:

Export includes acknowledgement user id and display name

 

Actual result:

Export includes user id only

 

Business impact:

Audit reviewer may need extra lookup to identify responsible dispatcher

 

Workaround:

Use audit drawer in dashboard to identify user

 

Target fix:

Post-beta

 

Acceptance Criteria:

Export includes acknowledgement user id and display name

 

Sprint: Sprint 15 - Operational Exception Handling

Epic Name: 

Epic Link: LRDP-153

Story Points: 

Labels: bug,sev-3

Linked Issues: relates LRDP-153

Fix Version:

