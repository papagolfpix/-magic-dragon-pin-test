MAGIC DRAGON PIN v0.10.47 — TEST

WHAT CHANGED IN v0.10.47
- Keeps the v0.10.46 stationary New Delivery control deck and Qty keyboard behaviour.
- Fixes the newly added delivery line appearing underneath / behind the controls.
- New Delivery now uses a strict column layout: fixed controls at the top, one flexible scrolling line-list zone underneath, fixed save actions at the bottom.
- Added line cards cannot occupy or paint back into the Branch / Date / Product / Variant / Qty / Add controls.
- No input reparenting, no forced refocus, and no change to the Qty keyboard viewport logic.

PASS CONDITION
1. Open New Delivery.
2. Tap Qty and enter a number; the stationary controls stay visible.
3. Tap Add.
4. The new line appears BELOW the Delivery note/control block, never underneath Branch/Date/Product controls.
5. Add several lines; only the line list scrolls. Top controls stay put.

VERSION / CACHE
- App badge: v0.10.47 TEST
- Service-worker cache: magic-pin-v0.10.47-test
