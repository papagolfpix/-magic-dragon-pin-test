MAGIC DRAGON PIN v0.10.43 — TEST

WHAT CHANGED
- New Delivery Qty is now passive on iPhone: tapping Qty does not ask the app to move, collapse, resize, reparent, refocus or offset anything.
- Removed the v0.10.42 Qty-focus collapse mode and visualViewport shell shifting.
- Removed repeated visualViewport-driven Qty shell corrections.
- Safari is allowed to open/close the numeric keyboard naturally.
- The existing runtime diagnostic remains observation-only: it can report if Qty is genuinely hidden, but it does not move the UI.
- Edit-existing-delivery Qty keyboard handling is unchanged.

PASS CONDITION
Tap New Delivery Qty -> numeric keyboard opens -> the same Qty box remains visible -> type a number and see it in that box -> close keyboard -> layout remains normal.

RELEASE CHECKS
- App badge: v0.10.43 TEST
- Service-worker cache: magic-pin-v0.10.43-test
- Service-worker registration cache-buster: v=1043
- JavaScript syntax checked with Node.
- ZIP integrity checked.
