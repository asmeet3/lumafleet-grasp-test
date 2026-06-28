---
id: jira-LRDP-32
type: processes
title: [LRDP-32] Barcode scan accepts lowercase shipment prefix for another tenant
date: 2026-06-17
status: active
supersedes: null
superseded_by: null
tags: ["jira", "lrdp", "barcode", "scan", "accepts", "lowercase"]
owner: 
sources:
  - type: jira
    ref: sources/jira/LRDP/[LRDP-32]_Barcode_scan_accepts_lowercase_shipment_prefix_for_another_tenant.md
    url: https://erfwagvbe.atlassian.net/browse/LRDP-32
related: []
freshness_check: null
confidence: medium
---
# [LRDP-32] Barcode scan accepts lowercase shipment prefix for another tenant

**Type:** Bug  
**Status:** To Do  
**Priority:** High  
**Assignee:** Asmeet Singh  
**Reporter:** Asmeet Singh  
**Labels:** barcode, bug, tenant-isolation  

## Description

Mock source key: LRDP-155

 

A barcode with a lowercase tenant prefix can pass client-side validation and then fail server-side with a generic error.

 

Acceptance Criteria:

Invalid tenant prefix is rejected on client before submission; error message explains barcode does not belong to this route.

 

Sprint: Sprint 14 - Cold Chain Visibility Foundation

Epic Name: 

Epic Link: LRDP-110

Story Points: 

Labels: bug,barcode,tenant-isolation

Linked Issues: relates LRDP-112; relates LRDP-116

Fix Version: Beta 0.9

