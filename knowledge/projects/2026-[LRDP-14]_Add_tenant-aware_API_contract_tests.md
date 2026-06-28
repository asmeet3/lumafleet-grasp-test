---
id: jira-LRDP-14
type: projects
title: [LRDP-14] Add tenant-aware API contract tests
date: 2026-06-17
status: active
supersedes: null
superseded_by: null
tags: ["jira", "lrdp", "add", "tenant", "aware", "api"]
owner: 
sources:
  - type: jira
    ref: sources/jira/LRDP/[LRDP-14]_Add_tenant-aware_API_contract_tests.md
    url: https://erfwagvbe.atlassian.net/browse/LRDP-14
related: []
freshness_check: null
confidence: medium
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

