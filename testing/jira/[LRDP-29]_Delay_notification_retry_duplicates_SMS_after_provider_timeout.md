---
id: jira-LRDP-29
source: jira
title: [LRDP-29] Delay notification retry duplicates SMS after provider timeout
url: https://erfwagvbe.atlassian.net/browse/LRDP-29
info_type: testing
updated_at: 2026-06-17T20:51:16.547000+05:30
metadata:
  project_key: LRDP
  issue_key: LRDP-29
  status: To Do
  issue_type: Bug
  priority: Highest
---
# [LRDP-29] Delay notification retry duplicates SMS after provider timeout

**Type:** Bug  
**Status:** To Do  
**Priority:** Highest  
**Assignee:** Asmeet Singh  
**Reporter:** Asmeet Singh  
**Labels:** bug, notifications  

## Description

Mock source key: LRDP-152

 

When the notification provider times out but later accepts the request, retry can send a duplicate customer SMS.

 

Acceptance Criteria:

Retry uses provider idempotency key and customer receives at most one message per delay event.

 

Sprint: Sprint 15 - Operational Exception Handling

Epic Name: 

Epic Link: LRDP-130

Story Points: 

Labels: bug,notifications

Linked Issues: relates LRDP-133

Fix Version: Beta 0.9

