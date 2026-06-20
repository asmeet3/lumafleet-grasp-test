---
id: jira-LRDP-32
source: jira
title: [LRDP-32] Barcode scan accepts lowercase shipment prefix for another tenant
url: https://erfwagvbe.atlassian.net/browse/LRDP-32
info_type: testing
updated_at: 2026-06-17T20:51:20.774000+05:30
metadata:
  project_key: LRDP
  issue_key: LRDP-32
  status: To Do
  issue_type: Bug
  priority: High
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

