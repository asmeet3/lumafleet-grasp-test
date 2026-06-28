---
id: jira-LRDP-11
type: projects
title: [LRDP-11] Sync driver task updates after offline period
date: 2026-06-17
status: active
supersedes: null
superseded_by: null
tags: ["jira", "lrdp", "sync", "driver", "task", "updates"]
owner: 
sources:
  - type: jira
    ref: sources/jira/LRDP/[LRDP-11]_Sync_driver_task_updates_after_offline_period.md
    url: https://erfwagvbe.atlassian.net/browse/LRDP-11
related: []
freshness_check: null
confidence: medium
---
# [LRDP-11] Sync driver task updates after offline period

**Type:** Story  
**Status:** To Do  
**Priority:** Highest  
**Assignee:** Asmeet Singh  
**Reporter:** Asmeet Singh  
**Labels:** mobile, offline-sync  

## Description

Mock source key: LRDP-113

 

As a driver, I want completed tasks to sync after I regain connectivity so that dispatch sees accurate progress even if I lost signal.

 

Acceptance Criteria:

Offline queue persists completed tasks; reconnect triggers ordered sync; duplicate sync requests do not create duplicate proof records; conflicts show a recoverable state to the driver and an audit event to dispatch.

 

Sprint: Sprint 15 - Operational Exception Handling

Epic Name: 

Epic Link: LRDP-110

Story Points: 8

Labels: mobile,offline-sync

Linked Issues: is blocked by LRDP-111; relates BUG-003

Fix Version: Beta 0.9

