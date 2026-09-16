MAGIC DRAGON PIN v0.10.40 — TEST

PURPOSE
Fix the New Delivery Qty/iPhone keyboard regression shown in the 16 Sep screenshots.

ROOT CAUSE
v0.10.39 moved the fixed Magic Dragon hero by visualViewport.offsetTop when Safari panned the visual viewport, but the fixed contentViewport was still anchored only to --content-top. When offsetTop became about 94px, the Product / Variant / Qty row moved upward underneath the hero. The old self-test then compared against the wrong visible interval and could report misleading geometry.

FIX
- Hero and contentViewport now use the same visualViewport.offsetTop origin.
- contentViewport top = offsetTop + content-top.
- contentViewport height = visualViewport.height - content-top - bottom margin.
- Open Menu is shifted by the same offset while Qty owns focus.
- Runtime Qty self-test now evaluates the true visible interval: offsetTop .. offsetTop + height.
- Self-test measures the active Qty input and also requires it to pass element hit-testing, so a field hidden behind another layer cannot falsely pass.
- No input reparenting/refocus workaround was reintroduced.

EXPECTED IPHONE BEHAVIOUR
Tap Qty -> numeric keyboard opens -> Product / Variant / Qty row remains visible below the branded header -> no large upward jump -> Qty remains tappable and visible.

RELEASE CHECKS
- App badge: v0.10.40 TEST
- Service-worker cache: magic-pin-v0.10.40-test
- Service-worker registration cache-buster: v=1040
- Inline JavaScript syntax checked with Node.
