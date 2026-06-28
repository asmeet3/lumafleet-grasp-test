---
id: jira-LRDP-36
type: processes
title: [LRDP-36] Resolution note allows only 120 characters in UI despite API supporting 500
date: 2026-06-17
status: active
supersedes: null
superseded_by: null
tags: ["jira", "lrdp", "resolution", "note", "allows", "only"]
owner: 
sources:
  - type: jira
    ref: sources/jira/LRDP/[LRDP-36]_Resolution_note_allows_only_120_characters_in_UI_despite_API_supporting_500.md
    url: https://erfwagvbe.atlassian.net/browse/LRDP-36
related: []
freshness_check: null
confidence: medium
---
# [LRDP-36] Resolution note allows only 120 characters in UI despite API supporting 500

**Type:** Bug  
**Status:** To Do  
**Priority:** Medium  
**Assignee:** Asmeet Singh  
**Reporter:** Asmeet Singh  
**Labels:** bug, sev-3  

## Description

Mock source key: BUG-005

 

Bug log id: BUG-005

 

Environment:

QA Chrome 125

 

Linked story:

LRDP-143

 

Steps to reproduce:

1. Open Sev 2 exception; 2. Enter 250-character resolution note; 3. Attempt to save

 

Expected result:

UI accepts up to 500 characters and shows remaining count

 

Actual result:

UI blocks typing after 120 characters

 

Business impact:

Resolution notes may lack enough detail for shift handoff

 

Workaround:

Use short note and add detail in route comments

 

Target fix:

Sprint 15

 

Acceptance Criteria:

UI accepts up to 500 characters and shows remaining count

 

Sprint: Sprint 15 - Operational Exception Handling

Epic Name: 

Epic Link: LRDP-143

Story Points: 

Labels: bug,sev-3

Linked Issues: relates LRDP-143

Fix Version: Beta 0.9

