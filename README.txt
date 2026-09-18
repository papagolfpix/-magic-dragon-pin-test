MAGIC DRAGON PIN v0.10.90 — TEST


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
