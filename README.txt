MAGIC DRAGON PIN v0.10.57 — TEST

WHAT CHANGED IN v0.10.57
- First Complete App Data Transfer test build branched from the v0.10.55 solid save point.
- Backup & Recovery now presents Export Complete App Data / Import Complete App Data.
- Import opens a readable preview before any data changes: source version, products, aliases, Sunday reports, delivery dockets, invoices, payments and archived source files.
- Cancel from preview changes nothing.
- Before a committed import, the receiving device automatically creates and requires saving a complete PRE-IMPORT-SAFETY package.
- Import then replaces local app data and archived Sunday source files and runs post-import count verification before reload.
- Verification result persists across reload and is shown in Backup & Recovery status.
- Existing v0.10.55 operational workflows and the locked v0.10.47 Delivery form Lego block are unchanged.

TEST PROCEDURE
1. Open Settings > Backup & Recovery.
2. Tap Export Complete App Data and save/share the JSON file.
3. On a test/receiving device, choose Import Complete App Data and select that file.
4. Check preview counts. Tap Cancel once and confirm nothing changes.
5. Select the file again, tap Replace This Device's Data, and save/share the PRE-IMPORT-SAFETY file when prompted.
6. Confirm import verification succeeds and app reloads.
7. Compare key counts and open one Sunday report, one delivery docket and one invoice.
8. Reload once more and confirm imported state persists.

VERSION CHECK
- App badge: v0.10.57 TEST
- Service-worker cache: magic-pin-v0.10.57-test

Filename update v0.10.57: user-facing export/backup files use the short Magic-Pin-* naming convention for easier identification on iPhone.
