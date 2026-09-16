MAGIC DRAGON PIN v0.10.38 — TEST

Purpose of this build:
- Fix the underlying iPhone Safari visual-viewport shell movement revealed by the v0.10.37 screenshot.
- Do not redesign, scroll, reparent, refocus or manually move the New Delivery Qty input.
- Reuse the existing fixed Magic Dragon shell, but anchor that shell to visualViewport.offsetTop while New Delivery Qty has focus.

Root cause now addressed:
- iOS Safari can pan the visual viewport when the numeric keyboard opens.
- The app header/content shell was position:fixed against the layout viewport, so the whole shell could end up above the visible viewport.
- The screenshot showing the top of the Magic Dragon banner cut off proves this is a shell/viewport problem, not a Qty-field-only problem.

New reusable Lego block:
- iPhone visual-viewport shell anchor: when a fixed mobile form is active and Safari pans the visual viewport, anchor the fixed shell to visualViewport.offsetTop and size the content area to visualViewport.height.
- This moves the shell, never the focused input.
- Existing Edit/Suggested Delivery line-item keyboard behavior remains unchanged.

Automatic regression test:
- Open index.html with ?mdselftest=qtyviewport.
- The app simulates a 92px visual-viewport pan and a 461px visible keyboard viewport.
- The test is PASS only if the branded header, content top and New Delivery Qty field all remain inside the synthetic visible viewport.
- Release packaging should not proceed if this self-test reports FAIL.

Manual iPhone checkpoint:
1. Open New Delivery.
2. Tap Qty.
3. Leave the numeric keyboard open.
4. The Magic Dragon header must remain fully visible.
5. Product / Variant / Qty / Add must remain visible below it.
6. Closing the keyboard must restore the normal shell without a jump.
