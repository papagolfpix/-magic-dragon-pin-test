MAGIC DRAGON PIN v0.10.70 — TEST

WHAT CHANGED IN v0.10.70
- Adds the first record-level Supabase sync Lego block for individual delivery dockets.
- Delivery records sync independently; this test does NOT replace the whole app database.
- Per-record revision protection blocks stale overwrites.
- Pulling delivery records safely adds new dockets or updates only records whose local base has not diverged.
- Local unsynced edits / true two-sided changes are left untouched and reported as conflicts.
- Existing whole-snapshot TEST Cloud sync remains available as the proven safety/reference path.
- Requires the one-time Magic-Pin-TEST-Delivery-Record-Setup-v1.sql migration in the DEV/TEST Supabase project.

TEST TARGET
1. Run the supplied SQL once in Magic Dragon Pin DEV Supabase.
2. On iPhone create a harmless test delivery docket in the normal New Delivery screen.
3. Settings > TEST Cloud Sync > Delivery Record Sync — TEST: select it and Upload selected docket.
4. On iPad sign in, Pull delivery records. The docket should appear without a whole-app restore.
5. Edit that same docket on iPad, then upload the selected docket again.
6. On iPhone Pull delivery records and verify the edited docket arrives.
