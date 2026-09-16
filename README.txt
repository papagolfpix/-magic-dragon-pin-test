MAGIC DRAGON PIN v0.10.42 — TEST

WHAT CHANGED IN v0.10.42
- Qty keyboard focus mode: when the New Delivery Qty box is tapped, non-essential delivery chrome collapses so the Product / Variant / Qty / Add row remains visibly on-screen above the iPhone numeric keyboard.
- Does not reparent, refocus, or replace the Qty input.
- Restores the normal delivery screen when the keyboard closes.
- The on-device self-test now also verifies the focus-mode chrome is collapsed and the picker row remains visible.

PURPOSE
Fix the New Delivery Qty/iPhone keyboard regression shown in the 16 Sep screenshots.

ROOT CAUSE
v0.10.40 fixed the on-screen Qty/keyboard positioning, but its runtime self-test mixed two different iPhone Safari coordinate spaces. visualViewport.offsetTop is a layout-viewport offset while the fixed shell rectangles returned by getBoundingClientRect() are visual-viewport coordinates during the keyboard state. That mismatch produced the red false-failure banner even though Qty was inside the safe visible area.

FIX
- Hero and contentViewport now use the same visualViewport.offsetTop origin.
- contentViewport top = offsetTop + content-top.
- contentViewport height = visualViewport.height - content-top - bottom margin.
- Open Menu is shifted by the same offset while Qty owns focus.
- Runtime Qty self-test now evaluates rect geometry in visual-viewport coordinates: 0 .. visualViewport.height.
- visualViewport.offsetTop is retained only for diagnostics and is never mixed into getBoundingClientRect() comparisons.
- The active Qty input must be inside the safe region below the hero/content top and must pass element hit-testing.
- The exact v0.10.40 screenshot geometry (offset 94, safe 140–441, Qty 307–341) now evaluates PASS instead of false FAIL.
- No input reparenting/refocus workaround was reintroduced.

EXPECTED IPHONE BEHAVIOUR
Tap Qty -> numeric keyboard opens -> Product / Variant / Qty row remains visible below the branded header -> no large upward jump -> Qty remains tappable and visible.

RELEASE CHECKS
- App badge: v0.10.42 TEST
- Service-worker cache: magic-pin-v0.10.42-test
- Service-worker registration cache-buster: v=1041
- Inline JavaScript syntax checked with Node.
