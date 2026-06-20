---
id: confluence-131074
source: confluence
title: Bug Triage Log
url: https://erfwagvbe.atlassian.net/wiki/spaces/LFE/pages/131074/Bug+Triage+Log
info_type: testing
updated_at: 2026-06-17T15:23:19.397000+00:00
metadata:
  space_key: LFE
  page_id: 131074
---
# Bug Triage Log

# Bug Triage Log

**Owner:** Hana Kim

**Purpose:** Track current beta defects and triage decisions.

### Severity Definitions

| Severity | Definition | Example |
| --- | --- | --- |
| Sev 1 | Blocks beta release or can cause customer harm, compliance failure, or duplicate external communication | BUG-008 duplicate SMS |
| Sev 2 | Major workflow broken or misleading operational state with workaround | BUG-003 offline sync retry loop |
| Sev 3 | Usability issue or localized defect with workaround | BUG-002 filter state loss |
| Sev 4 | Cosmetic or low-risk documentation defect | Not currently present |

### Active Triage

| Bug | Severity | Owner | Decision |
| --- | --- | --- | --- |
| BUG-008 / LRDP-152 | Sev 1 | Dev Patel | Release blocker; implement notification idempotency before Beta 0.9 |
| BUG-003 | Sev 2 | Elena Vos | Fix in Sprint 15 before driver pilot |
| BUG-006 / LRDP-151 | Sev 2 | Nora Blake | Fix projection lag or hide stale queue state |
| BUG-004 / LRDP-155 | Sev 2 | Elena Vos | Sprint 14 hotfix due tenant validation concern |

---
