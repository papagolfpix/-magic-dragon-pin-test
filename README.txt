MAGIC DRAGON PIN v0.10.51 — TEST

WHAT CHANGED IN v0.10.51
- Added safety guardrails to Delete Sunday Report.
- A Sunday report is blocked from deletion when its date is already tied to a completed Sunday workflow, a live saved invoice, or unresolved financial correction.
- Blocked deletion changes nothing and directs the operator to Replace existing instead when the worksheet itself is wrong.
- For an unprotected report, the confirmation now states exactly what will be removed before deletion.
- Deletion removes the Sunday report, its linked Excel weekly record, its locally archived source workbook, and only unedited/undelivered calculated suggested dockets generated from that exact report.
- Delivered or manually edited dockets are preserved.
- Existing multi-week detection, duplicate Keep/Replace flow, catalogue integrity, mapping system, backup system and v0.10.47 Delivery form Lego block are unchanged.

TEST
1. Open Sunday Reports and expand a report in the archive.
2. Tap Delete on a report that is NOT part of a completed/invoiced week. Confirm the preview is clear, cancel once, then repeat and confirm deletion if it is safe test data.
3. Tap Delete on a completed/invoiced week. It should refuse and say nothing was deleted.
4. Confirm Delivery docket behaviour remains unchanged.

VERSION
- App badge: v0.10.51 TEST
- Service-worker cache: magic-pin-v0.10.51-test
