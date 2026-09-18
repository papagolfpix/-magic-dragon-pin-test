WHAT CHANGED IN v0.10.99 TEST
- Fixed saved delivery docket scrolling: long docket content now scrolls independently while the 2x2 action bar remains fixed at the viewport bottom.
- Restored explicit top navigation in Delivery Dockets with a compact Home button.
- Opening/collapsing a docket no longer scrolls the whole Delivery module header out of view.
- No Sunday, pricing, invoice, mapping, cloud, PDF or business-rule logic changed.

MAGIC DRAGON PIN v0.10.99 — TEST

PURPOSE
- Frozen Sunday-handoff candidate based directly on validated v0.10.97 TEST.
- No new business feature has been added.
- DEV/TEST Cloud Sync controls are hidden from the Pin handoff interface.
- Development-only whole-snapshot and harmless cross-device markers are removed automatically on first run.
- Normal Backup & Recovery remains available and is the supported Pin handoff/recovery path.

VALIDATED BEFORE THIS CANDIDATE
- Six real Sunday workbooks: 11 weekly blocks detected -> 7 unique branch/date reports.
- Duplicate report protection and multi-week separation passed.
- 13 Sep BM and Lamai linked to the immediately prior Sunday and fully reconciled.
- Suggested branch dockets generated from Sunday stock.
- Combined Suggested Delivery: 16 products / 107 units.
- Combined packing PDF matched the calculation.
- Suggested-docket Delivered date defaults to today, remains editable, and becomes the docket archive/sort date.
- Delivery record cloud sync passed in both directions in the DEV/TEST workspace.
- Cross-device conflict protection passed without silent overwrite.
- Whole-app snapshot upload/preview/restore passed; Rev 7 restored and verified with a pre-import safety backup.

IMPORTANT
The proven cloud work remains a DEV/TEST Lego block. It is intentionally hidden in this Pin release candidate until a separate production cloud workspace is deliberately commissioned. Do not repurpose the DEV workspace as Pin's production cloud.

MAGIC DRAGON PIN v0.10.97 — TEST

WHAT CHANGED IN v0.10.97
- Fixed TEST record-level cloud sync for Sunday suggested delivery dockets.
- Untouched auto-generated suggestions remain local-only and do not pollute cloud sync.
- As soon as a suggested docket is edited by Pin or marked Delivered, it becomes a normal cloud-linked docket and local changes are detected for upload.
- This preserves the clean suggestion workflow while allowing real saved/delivered dockets to sync correctly across devices.

WHAT CHANGED IN v0.10.96
- Mark Delivered now defaults the editable delivery-date prompt to today, not the draft/suggestion creation date.
- Confirming Delivered makes that chosen real delivery date the docket date used in the Delivery Dockets archive and chronological sorting.
- Sunday suggestion provenance remains preserved separately through sourceSundayDate and the suggested reference.
- Adds a narrow safe-undo exception for an accidental Delivered click made after an invoice had already been saved; genuine invoice-cycle deliveries and post-delivery edits remain locked.
- No Sunday parsing, product mapping, quantity calculation, invoice calculation or cloud-sync logic is otherwise changed.


WHAT CHANGED IN v0.10.95
- Hardens Sunday Excel preflight using the real six-file Sunday validation set supplied on 18 September 2026.
- Identical duplicate branch/date reports in the same upload batch are now detected by content: one copy is selected and redundant copies are safely left unchecked.
- If duplicate branch/date reports differ, none is preselected and the user must deliberately choose which copy to import.
- Selecting any copy for a branch/date automatically deselects the other copies for that same branch/date, preventing accidental duplicate selection.
- Multi-week detection, canonical mapping, delivery dockets, calculations and cloud-sync behavior are otherwise unchanged.

REAL SUNDAY VALIDATION TARGET
- Selecting all six supplied test workbooks should detect 11 weekly blocks.
- Those 11 blocks represent 7 unique branch/date reports: Lamai 23/08, 30/08, 06/09, 13/09 and BM Bangrak 30/08, 06/09, 13/09.
- Four redundant Lamai copies should be left unchecked automatically because their report contents are identical.


WHAT CHANGED IN v0.10.94
- Adds Settings > Branch product lists for deliberate shop-by-shop product assignment.
- Each shop shows every active canonical product, with products from its latest Sunday report identified clearly.
- “Tick all products on latest Sunday report” only adds unsaved ticks; it never removes assignments and still requires an explicit confirmed Save.
- Saved branch lists control future delivery-product choices only. Existing dockets, Sunday reports, stock history and invoices are unchanged.
- Canonical alias identities are now used when checking branch coverage, preventing an old duplicate product ID from creating a false outside-list warning.
- Adds compact assigned/latest/not-assigned counters and protects unsaved work when switching shops.


WHAT CHANGED IN v0.10.93
- Replaces the confusing all-history catalogue warning with a read-only comparison against the immediately previous Sunday for the same branch.
- “Missing since previous Sunday”, “New or returned this week”, and “On sheet but outside the current branch delivery list” are classified separately.
- A prior report counts only when it is 5–9 days earlier; otherwise the latest report is clearly marked as a continuity baseline.
- Adds a visible deterministic classification self-check under Settings > Catalogue integrity.
- This feature never deletes products, changes branch assignments, adjusts stock or alters an import automatically.
- Mapping, multi-week detection, delivery dockets and cloud sync are unchanged.


WHAT CHANGED IN v0.10.92
- Adds a compact mapping-integrity dashboard under Settings > Product mappings.
- Shows unique spreadsheet source names, resolved names, genuinely new/changed names and names saved for later.
- Confirms how many historical Sunday and weekly rows currently link to catalogue products.
- Saving an alias now updates past Sunday imports and their linked Excel weekly records in one operation, then reports the exact number of historical rows changed.
- Unresolved historical weekly rows are explicitly cleared instead of retaining a stale previous product link.
- Confirmed aliases continue to apply automatically to future imports, and resolved names disappear immediately from active review.
- The proven delivery sync and multi-week worksheet detector are unchanged.


WHAT CHANGED IN v0.10.91
- Strengthens detection of several weekly Sunday reports pasted into one worksheet.
- Each detected week is shown separately with its own shop, check date, product count and source-row range before import.
- Dates can now be read when embedded in labels, placed in adjacent cells, stored as ISO dates or stored as Excel date serials.
- A workbook/worksheet containing multiple weeks shows an explicit green separation notice.
- A block with an undetectable shop or check date is safely excluded instead of being silently filed under today's date or the wrong shop.
- Adds a visible deterministic detector self-check that must separate three test blocks and three dates correctly.
- Delivery dockets, delivery cloud sync, calculations and existing saved records are unchanged.


WHAT CHANGED IN v0.10.90
- Adds a harmless cross-device sync test inside Delivery Sync — TEST.
- The test adds only a visible TEST marker to one normal cloud-linked docket.
- It does not change stock, quantities, prices, delivery status, invoices or docket notes.
- The marker travels through the real record-level upload and pull path, so the receiving device can visibly confirm the transfer.
- A Clear button removes the marker locally; syncing again removes it from the cloud copy.


WHAT CHANGED IN v0.10.89
- Opening TEST Cloud Sync now performs a read-only delivery-record comparison automatically.
- Delivery Sync clearly reports Up to date, Cloud newer, Changes to upload, or Review needed.
- Local, cloud and safely-uploadable pending counts are refreshed from live delivery-record state.
- The automatic check never uploads, pulls or overwrites data; the existing buttons remain deliberate actions.
- The v0.10.88 docket UI checkpoint and all business logic are unchanged.


WHAT CHANGED IN v0.10.88
- Records > Delivery dockets now reuses the exact same compact docket-row component as the dedicated Delivery Dockets menu.
- Date/branch text, one-line layout, font size, border, spacing, status badges and chevron are now identical in both places.
- Other Records groups and all docket actions/business logic are unchanged.


WHAT CHANGED IN v0.10.87
- Fixed the first Records > Delivery dockets view so every row immediately shows Delivered or Not delivered.
- The Records list now uses the same saved deliveredAt status as the dedicated Delivery Dockets screen.
- New/updated-from-cloud information remains in the record description instead of replacing the delivery status badge.
- No docket actions, cloud-sync logic, fixed-footer behaviour or business data were changed.


WHAT CHANGED IN v0.10.86
- Delivery-docket actions now remain in a true iPhone-safe 2 × 2 footer fixed to the bottom of the viewport.
- The open docket uses the full available area above the footer and scrolls independently, including its final line.
- Each compact docket chevron now shows a green Delivered badge or pale orange-brown Not delivered badge.
- Button wording, colours, actions, docket data and v0.10.85 cloud-sync behaviour are unchanged.


WHAT CHANGED IN v0.10.85
- Fixed stale cross-device delivery pulls caused by the service worker caching Supabase GET responses.
- All cross-origin Supabase API/auth requests now bypass the service-worker cache and go directly to network.
- Delivery Sync cloud counts and Check / Pull from Cloud should now reflect the latest cloud rows on every device.

WHAT CHANGED IN v0.10.83
- Delivered-docket edit audit now automatically lists exactly what changed before Save.
- User only enters the reason WHY the correction was needed.
- Automatic change descriptions include quantity changes, product swaps, added/removed products, shop/date/note changes.
- The same automatic summary is stored in Edit history and syncs to other devices.

- Delivery docket archive now uses focused chevron behaviour.
- Initial view shows the full compact list of saved dockets.
- Opening one docket temporarily hides all other docket selectors.
- Collapsing the open docket restores the full selector list.
- This matches the proven focused Settings-chevron interaction pattern.

WHAT CHANGED IN v0.10.79
- Adds explicit Delivery Conflict Review with side-by-side local/cloud differences and deliberate resolution buttons.
- Delivered docket edits now require a short reason and save an audit trail with device, account, time and concise change details.
- Edit history travels with the docket through record-level cloud sync.
- No conflict is silently overwritten.
- iPad Sunday Workflow now keeps the branded Magic Dragon header visible instead of switching to a headerless fullscreen shell.
- Sunday Workflow content is isolated in its own scrollable viewport below the fixed tablet header while the bottom workflow navigation remains available.
- Opening Sunday Workflow now re-measures the shell after workflow mode starts, preventing stale header geometry.
- iPhone Sunday Workflow layout is intentionally unchanged.
- All v0.10.74 Delivery Sync separation/bulk-sync behaviour is preserved.

WHAT CHANGED IN v0.10.73
- Record-level delivery pull results now distinguish THIS pull from prior sync history.
- If nothing changed, message says all cloud dockets were already identical.
- New/updated cloud dockets are remembered and highlighted in Records.
- Delivery Records list now shows the docket ID so same-date/shop dockets can be distinguished.
- No record-sync architecture or business logic changed.

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


v0.10.73
- Fixes iPad/tablet Settings shell so the Magic Dragon header remains visible while Settings content scrolls.
- Tablet-only shell patch; proven iPhone header/keyboard behaviour is left unchanged.

- New Delivery now shows a clear “Docket history” escape button beside + New Delivery so accidental entry can return directly to the delivery history list without losing orientation.
