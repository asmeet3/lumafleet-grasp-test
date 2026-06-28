---
id: jira-LRDP-37
source: jira
title: [LRDP-37] Expired ETA portal token displays generic 500 error page
url: https://erfwagvbe.atlassian.net/browse/LRDP-37
ingested_at: 2026-06-28T19:16:54.038246+00:00
updated_at: 2026-06-17T20:54:35.421000+05:30
metadata:
  project_key: LRDP
  issue_key: LRDP-37
  status: To Do
  issue_type: Bug
  priority: Medium
---
# [LRDP-37] Expired ETA portal token displays generic 500 error page

**Type:** Bug  
**Status:** To Do  
**Priority:** Medium  
**Assignee:** Asmeet Singh  
**Reporter:** Asmeet Singh  
**Labels:** bug, sev-3  

## Description

Mock source key: BUG-007

 

Bug log id: BUG-007

 

Environment:

QA Chrome 125 private window

 

Linked story:

LRDP-131

 

Steps to reproduce:

1. Open ETA link with expired token; 2. Observe portal response

 

Expected result:

User sees friendly expired link page with support contact and no stack details

 

Actual result:

Portal displays generic 500 error page

 

Business impact:

Poor customer experience and possible support escalation

 

Workaround:

Generate a new ETA link from stop detail

 

Target fix:

Sprint 15

 

Acceptance Criteria:

User sees friendly expired link page with support contact and no stack details

 

Sprint: Sprint 15 - Operational Exception Handling

Epic Name: 

Epic Link: LRDP-131

Story Points: 

Labels: bug,sev-3

Linked Issues: relates LRDP-131

Fix Version: Beta 0.9

