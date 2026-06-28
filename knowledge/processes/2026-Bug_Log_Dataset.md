---
id: confluence-720913
type: processes
title: Bug Log Dataset
date: 2026-06-17
status: active
supersedes: null
superseded_by: null
tags: ["confluence", "bug", "log", "dataset"]
owner: 
sources:
  - type: confluence
    ref: sources/confluence/2026-06/Bug_Log_Dataset.md
    url: https://erfwagvbe.atlassian.net/wiki/spaces/LFE/pages/720913/Bug+Log+Dataset
related: []
freshness_check: null
confidence: medium
---
# Bug Log Dataset

# Bug Log Dataset

```
"Bug ID","Jira Issue","Title","Severity","Priority","Status","Component","Sprint Found","Environment","Linked Story","Reporter","Owner","Steps to Reproduce","Expected Result","Actual Result","Business Impact","Workaround","Target Fix"
"BUG-001","LRDP-122","Temperature timeline renders points one hour early during daylight savings transition","Sev 2","High","Open","Dispatch Dashboard","Sprint 14 - Cold Chain Visibility Foundation","QA Chrome 125, tenant timezone America/New_York","LRDP-122","Hana Kim","Dev Patel","1. Load route RT-DST-001 with readings around daylight savings boundary; 2. Open route detail temperature timeline; 3. Compare point labels with raw telemetry timestamps","Timeline labels match tenant timezone and raw telemetry converted time","Readings after the transition appear one hour earlier than expected","Compliance review may misinterpret excursion duration","Use raw telemetry export for audit review until fixed","Sprint 15"
"BUG-002","LRDP-142","Exception queue owner filter clears when browser back button is used","Sev 3","Medium","Open","Dispatch Dashboard","Sprint 15 - Operational Exception Handling","QA Chrome 125","LRDP-142","Hana Kim","Dev Patel","1. Filter exception queue by owner Maya; 2. Open an exception detail; 3. Click browser back; 4. Observe filter chips and result list","Owner filter remains applied after returning to queue","Filter chip disappears and queue shows all owners","Dispatcher may lose triage context during busy shift","Use in-app breadcrumb instead of browser back","Sprint 15"
"BUG-003","LRDP-113","Offline sync retries indefinitely after a 409 conflict","Sev 2","Highest","Open","Driver Mobile","Sprint 15 - Operational Exception Handling","Android 14 emulator, intermittent network profile","LRDP-113","Hana Kim","Elena Vos","1. Go offline; 2. Complete stop task; 3. Change same stop status from dispatch; 4. Reconnect mobile app; 5. Observe sync status","Conflict is shown to driver with retry or discard option and queue stops automatic retry","App continues retrying every 10 seconds and battery usage spikes","Driver may not trust task status and dispatch receives noisy sync failures","Force close app and ask dispatch to manually verify stop","Sprint 15"
"BUG-004","LRDP-155","Barcode scan accepts lowercase shipment prefix for another tenant","Sev 2","High","In Progress","Driver Mobile","Sprint 14 - Cold Chain Visibility Foundation","iOS 18 simulator and Android 14 emulator","LRDP-112","Hana Kim","Elena Vos","1. Log in as Northstar driver; 2. Open active stop; 3. Scan barcode acme-chl-000184; 4. Submit proof","Client rejects barcode because tenant prefix does not match assigned route","Client allows submission and server returns generic validation failure","Slows driver workflow and creates tenant-isolation concern","Drivers can rescan correct barcode; dispatch can verify failed proof attempt","Sprint 14 hotfix"
"BUG-005","LRDP-143","Resolution note allows only 120 characters in UI despite API supporting 500","Sev 3","Medium","Open","Dispatch Dashboard","Sprint 15 - Operational Exception Handling","QA Chrome 125","LRDP-143","Hana Kim","Dev Patel","1. Open Sev 2 exception; 2. Enter 250-character resolution note; 3. Attempt to save","UI accepts up to 500 characters and shows remaining count","UI blocks typing after 120 characters","Resolution notes may lack enough detail for shift handoff","Use short note and add detail in route comments","Sprint 15"
"BUG-006","LRDP-151","Temperature alert remains open after acknowledgement refresh","Sev 2","High","Open","Telemetry","Sprint 15 - Operational Exception Handling","QA API and Chrome 125","LRDP-123","Hana Kim","Nora Blake","1. Trigger excursion alert; 2. Acknowledge with note; 3. Refresh exception queue immediately; 4. Wait 30 seconds and refresh again","Acknowledged status persists immediately after refresh","Status temporarily reverts to open for about 30 seconds","Could cause duplicate dispatcher work and false escalation","Wait for background projection update before rechecking","Sprint 15"
"BUG-007","LRDP-131","Expired ETA portal token displays generic 500 error page","Sev 3","Medium","Open","Customer Portal","Sprint 15 - Operational Exception Handling","QA Chrome 125 private window","LRDP-131","Hana Kim","Dev Patel","1. Open ETA link with expired token; 2. Observe portal response","User sees friendly expired link page with support contact and no stack details","Portal displays generic 500 error page","Poor customer experience and possible support escalation","Generate a new ETA link from stop detail","Sprint 15"
"BUG-008","LRDP-152","Delay notification retry duplicates SMS after provider timeout","Sev 1","Highest","Open","Notification Service","Sprint 15 - Operational Exception Handling","QA provider sandbox with timeout simulation","LRDP-133","Hana Kim","Dev Patel","1. Trigger delay notification; 2. Simulate provider timeout after provider accepted message; 3. Allow retry job to run; 4. Check notification log and customer phone","Customer receives one SMS per delay event due to idempotency key","Customer receives duplicate SMS messages","Customer trust risk and potential compliance problem for regulated deliveries","Temporarily disable automatic retry for provider timeout scenario","Sprint 15 blocker"
"BUG-009","","Compliance export omits acknowledgement user display name","Sev 3","Low","Triaged","Reporting","Sprint 15 - Operational Exception Handling","QA Chrome 125","LRDP-153","Hana Kim","Nora Blake","1. Acknowledge excursion as Maya; 2. Export route compliance CSV; 3. Inspect acknowledgement section","Export includes acknowledgement user id and display name","Export includes user id only","Audit reviewer may need extra lookup to identify responsible dispatcher","Use audit drawer in dashboard to identify user","Post-beta"
"BUG-010","","Route health card shows stale ETA after manual route edit","Sev 3","Medium","Open","Dispatch Dashboard","Sprint 15 - Operational Exception Handling","QA Chrome 125","LRDP-103","Hana Kim","Dev Patel","1. Open route health card; 2. Accept manual route edit that changes stop order; 3. Return to route board; 4. Compare route card ETA with detail drawer","Route card and detail drawer show same recalculated ETA without page reload","Route card shows old ETA until full reload","Dispatcher may make prioritization decision from stale ETA","Refresh browser after accepting manual edit","Sprint 15"
```
