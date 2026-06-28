---
id: jira-LRDP-13
type: projects
title: [LRDP-13] Create stop task local persistence model
date: 2026-06-17
status: active
supersedes: null
superseded_by: null
tags: ["jira", "lrdp", "create", "stop", "task", "local"]
owner: 
sources:
  - type: jira
    ref: sources/jira/LRDP/[LRDP-13]_Create_stop_task_local_persistence_model.md
    url: https://erfwagvbe.atlassian.net/browse/LRDP-13
related: []
freshness_check: null
confidence: medium
---
# [LRDP-13] Create stop task local persistence model

**Type:** Task  
**Status:** To Do  
**Priority:** High  
**Assignee:** Asmeet Singh  
**Reporter:** Asmeet Singh  
**Labels:** mobile, storage  

## Description

Mock source key: LRDP-115

 

Persist stop task completion locally with route id, stop id, task type, timestamp, and idempotency key.

 

Acceptance Criteria:

Local records survive app restart; completed tasks are removed only after confirmed server acknowledgement.

 

Sprint: Sprint 15 - Operational Exception Handling

Epic Name: 

Epic Link: LRDP-110

Story Points: 3

Labels: mobile,storage

Linked Issues: parent LRDP-113

Fix Version: Beta 0.9

