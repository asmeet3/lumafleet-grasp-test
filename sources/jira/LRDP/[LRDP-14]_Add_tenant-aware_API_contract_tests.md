---
id: jira-LRDP-14
source: jira
title: [LRDP-14] Add tenant-aware API contract tests
url: https://erfwagvbe.atlassian.net/browse/LRDP-14
ingested_at: 2026-06-28T19:15:31.297145+00:00
updated_at: 2026-06-17T20:50:56.804000+05:30
metadata:
  project_key: LRDP
  issue_key: LRDP-14
  status: To Do
  issue_type: Task
  priority: Highest
---
# [LRDP-14] Add tenant-aware API contract tests

**Type:** Task  
**Status:** To Do  
**Priority:** Highest  
**Assignee:** Asmeet Singh  
**Reporter:** Asmeet Singh  
**Labels:** security, tenant-isolation  

## Description

Mock source key: LRDP-116

 

Add API tests proving route, stop, telemetry, and exception endpoints cannot access another tenant's records.

 

Acceptance Criteria:

Tests cover successful same-tenant access and rejected cross-tenant access for route, stop, telemetry, and exception APIs.

 

Sprint: Sprint 14 - Cold Chain Visibility Foundation

Epic Name: 

Epic Link: LRDP-110

Story Points: 3

Labels: security,tenant-isolation

Linked Issues: relates LRDP-101; relates LRDP-121

Fix Version: Beta 0.9

