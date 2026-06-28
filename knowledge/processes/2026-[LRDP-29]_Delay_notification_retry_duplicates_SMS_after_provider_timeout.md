---
id: jira-LRDP-29
type: processes
title: [LRDP-29] Delay notification retry duplicates SMS after provider timeout
date: 2026-06-17
status: active
supersedes: null
superseded_by: null
tags: ["jira", "lrdp", "delay", "notification", "retry", "duplicates"]
owner: 
sources:
  - type: jira
    ref: sources/jira/LRDP/[LRDP-29]_Delay_notification_retry_duplicates_SMS_after_provider_timeout.md
    url: https://erfwagvbe.atlassian.net/browse/LRDP-29
related: []
freshness_check: null
confidence: medium
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

