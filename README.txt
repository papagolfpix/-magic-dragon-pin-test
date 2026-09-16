MAGIC DRAGON PIN v0.10.63 — TEST

WHAT CHANGED IN v0.10.63
- Adds optimistic cloud revision/conflict protection to the evolving Supabase TEST sync Lego block.
- Each device now tracks the cloud revision its local data is based on.
- Upload is blocked if the cloud has advanced since that device's sync base.
- Server-side PATCH includes the expected revision, so a simultaneous device update cannot silently overwrite a newer revision.
- Check TEST Cloud compares the actual local state with the shared cloud payload; identical state can safely establish/re-establish the sync base.
- Cloud restore records the downloaded revision as the new local sync base only after verified replacement succeeds.
- Adds clear amber warning status for cloud/local divergence or blocked uploads.

TEST PLAN
1. On iPhone and iPad, sign in and press Check TEST Cloud. Both should establish revision 3 as their sync base if the data matches.
2. On iPad, Upload This Device to create revision 4.
3. On iPhone, DO NOT Check Cloud first; press Upload This Device. It must be blocked because iPhone is still based on revision 3.
4. On iPhone, press Check TEST Cloud. Because the payload is unchanged, it should safely recognise that local data matches revision 4 and update the sync base.
5. Upload from iPhone; it should then create revision 5 successfully.

WHAT CHANGED IN v0.10.62

- Complete App Data import now explains the pre-import safety-backup step BEFORE iPhone opens the native Share / Save sheet.
- The prompt tells the user why the Magic-Pin-SAFETY file is being created, what to do with it, and that cancelling leaves the device unchanged.

- Fixed stale dashboard Sunday status after replacing/overriding an older Sunday report.
- Historical replacement imports no longer mark that old date as the active Sunday workflow.
- Dashboard now self-heals an orphaned active Sunday pointer when the date is already complete, missing, or older than a newer completed Sunday.
- Existing current/incomplete Sunday workflows still resume normally.
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
- App badge: v0.10.63 TEST
- Service-worker cache: magic-pin-v0.10.63-test

Filename update v0.10.57: user-facing export/backup files use the short Magic-Pin-* naming convention for easier identification on iPhone.
