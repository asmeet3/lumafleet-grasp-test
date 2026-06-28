---
id: jira-LRDP-17
type: projects
title: [LRDP-17] Create temperature excursion alert with acknowledgement workflow
date: 2026-06-17
status: active
supersedes: null
superseded_by: null
tags: ["jira", "lrdp", "create", "temperature", "excursion", "alert"]
owner: 
sources:
  - type: jira
    ref: sources/jira/LRDP/[LRDP-17]_Create_temperature_excursion_alert_with_acknowledgement_workflow.md
    url: https://erfwagvbe.atlassian.net/browse/LRDP-17
related: []
freshness_check: null
confidence: medium
---
# [LRDP-17] Create temperature excursion alert with acknowledgement workflow

**Type:** Story  
**Status:** To Do  
**Priority:** Highest  
**Assignee:** Asmeet Singh  
**Reporter:** Asmeet Singh  
**Labels:** alerts, compliance, temperature  

## Description

Mock source key: LRDP-123

 

As a compliance manager, I want out-of-range temperature readings to create alerts that must be acknowledged so that excursions are not missed.

 

Acceptance Criteria:

Alert is created when threshold is breached for configured duration; duplicate alert is suppressed while active; dispatcher can acknowledge with note; acknowledgement is stored with user, timestamp, and route id.

 

Sprint: Sprint 15 - Operational Exception Handling

Epic Name: 

Epic Link: LRDP-120

Story Points: 8

Labels: alerts,temperature,compliance

Linked Issues: is blocked by LRDP-121; relates LRDP-143; relates BUG-006

Fix Version: Beta 0.9

