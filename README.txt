MAGIC DRAGON PIN v0.10.46 — TEST

WHAT CHANGED IN v0.10.46
- Based on the v0.10.42 keyboard approach because that was the closest on the real iPhone.
- Fixes the intermittent second movement: while New Delivery Qty stays focused, the app now remembers the strongest Safari visual-viewport pan seen during that keyboard session and will not follow a later transient offset back upward.
- The visible keyboard height is likewise held at the smallest stable viewport height until Qty loses focus.
- No input reparenting and no forced refocus.
- On blur, all temporary viewport values are cleared so the normal screen returns cleanly.
- Runtime Qty visibility self-test retained.

PASS CONDITION
Tap New Delivery Qty -> numeric keyboard opens -> the Qty input remains visible continuously -> type a number and see it in the Qty field -> dismiss keyboard -> normal delivery screen returns.

VERSION / CACHE
- App badge: v0.10.46 TEST
- Service-worker cache: magic-pin-v0.10.46-test
