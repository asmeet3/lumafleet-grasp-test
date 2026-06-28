---
id: confluence-1015809
type: projects
title: Sprint 15 Plan
date: 2026-06-17
status: active
supersedes: null
superseded_by: null
tags: ["confluence", "sprint", "plan"]
owner: 
sources:
  - type: confluence
    ref: sources/confluence/2026-06/Sprint_15_Plan.md
    url: https://erfwagvbe.atlassian.net/wiki/spaces/LFE/pages/1015809/Sprint+15+Plan
related: []
freshness_check: null
confidence: medium
---
# Sprint 15 Plan

# Sprint 15 Plan

**Owner:** Mateo Ruiz

**Purpose:** Define Sprint 15 commitments and scope tradeoffs.

### Sprint Goal

Dispatchers can triage exceptions, customers can see updated ETAs, and compliance managers can export route evidence for pilot deliveries.

### Committed Issues

LRDP-103, LRDP-113, LRDP-123, LRDP-131, LRDP-132, LRDP-133, LRDP-142, LRDP-143, LRDP-147, LRDP-153.

### Scope Tradeoff

Sprint 15 is above normal capacity because driver sync and alert acknowledgement are beta blockers. If LRDP-113 or LRDP-123 overruns, LRDP-153 is the first planned scope tradeoff.

### Acceptance Focus

* Offline driver updates sync without duplicate proof records.
* Temperature excursions create one active alert and preserve acknowledgement audit.
* Customer ETA portal uses expiring stop-specific tokens.
* Delay notifications include reason code and provider status.
* Exception queue supports severity, owner, status, and route filtering.

---
