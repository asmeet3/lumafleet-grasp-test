---
id: jira-LRDP-11
source: jira
title: [LRDP-11] Sync driver task updates after offline period
url: https://erfwagvbe.atlassian.net/browse/LRDP-11
info_type: features
updated_at: 2026-06-17T20:50:52.655000+05:30
metadata:
  project_key: LRDP
  issue_key: LRDP-11
  status: To Do
  issue_type: Story
  priority: Highest
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

