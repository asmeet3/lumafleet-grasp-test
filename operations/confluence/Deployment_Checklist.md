---
id: confluence-1114113
source: confluence
title: Deployment Checklist
url: https://erfwagvbe.atlassian.net/wiki/spaces/LFE/pages/1114113/Deployment+Checklist
info_type: operations
updated_at: 2026-06-17T15:23:22.102000+00:00
metadata:
  space_key: LFE
  page_id: 1114113
---
# Deployment Checklist

# Deployment Checklist

**Owner:** Mateo Ruiz

**Purpose:** Provide a release checklist for Beta 0.9 deployment.

### Pre-Deployment

* Confirm feature flags for pilot tenants.
* Run tenant-aware API contract tests from LRDP-116.
* Run QA smoke tests TC-LR-001, TC-LR-007, TC-LR-010, TC-LR-014, and TC-LR-020.
* Confirm no open Sev 1 bugs.
* Confirm workarounds for any open Sev 2 bugs are documented.

### Deployment

* Apply backward-compatible migrations.
* Deploy services using blue/green rollout.
* Enable `temperatureTimeline` and `exceptionQueueV2` for pilot tenants.
* Keep `driverOfflineSync` limited to QA until LRDP-113 passes acceptance.
* Monitor telemetry freshness and notification failure panels for 30 minutes.

### Post-Deployment

* Run synthetic telemetry seed scenario from LRDP-145.
* Verify route board loads active route health cards.
* Verify expired ETA portal token shows friendly error page after BUG-007 is fixed.
* Capture release notes and link Jira fix version `Beta 0.9`.
