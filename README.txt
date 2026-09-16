MAGIC DRAGON PIN v0.10.39 — TEST

Purpose of this build:
- Correct the Qty viewport self-test false FAIL exposed by the iPhone screenshot from 16 Sep 2026.
- Do not change the proven Qty focus, keyboard, shell positioning, reparenting, scrolling or refocus behaviour.
- Preserve the v0.10.38 visual-viewport shell fix unchanged.

Root cause corrected in the test:
- getBoundingClientRect() returns viewport-client coordinates.
- visualViewport.offsetTop is a layout-viewport offset.
- The v0.10.38 runtime assertion compared those two different coordinate spaces, so Safari visual pan could be counted twice and produce a false FAIL even when Qty was visible.

Correct invariant:
- DOMRect visible range is client 0..visualViewport.height.
- Safe Qty top is max(0, branded-header bottom).
- Safe Qty bottom is visualViewport.height minus the existing 12px keyboard margin.
- visualViewport.offsetTop is retained only as diagnostic data; it is not added to DOMRect positions.

Diagnostic banner:
- PASS remains silent.
- FAIL now reports visible client range, visualViewport offsetTop, calculated safe range, header range and Qty range.
- This makes any future regression numerically diagnosable from one screenshot.

Deterministic regression test:
- Open index.html with ?mdselftest=qtyviewport.
- It simulates the shell shift from a 92px Safari visual pan and checks against a 461px client-visible height.
- The deterministic test calls the same invariant function used by the on-device runtime test, so the two checks cannot silently drift apart.

Manual iPhone checkpoint:
1. Open New Delivery.
2. Tap Qty and leave the numeric keyboard open.
3. Product / Variant / Qty / Add must remain visible.
4. No red self-test banner should appear when Qty is inside the safe client area.
5. Closing the keyboard must restore the normal shell without a jump.
