MAGIC DRAGON PIN v0.10.28 — TEST

Purpose of this build:
- Regression-only fix for New Delivery Qty keyboard opening + visibility on iPhone Safari.
- Preserve the working IN STOCK / OUT OF STOCK catalogue toggle and all v0.10.26 business/PDF logic unchanged.

Blueprint / Lego-block rule applied:
- The New Delivery Product / Variant / Qty / Add controls are mounted directly under document.body on the Qty pointer-down gesture, BEFORE focus occurs; the same Qty input is then focused synchronously so iOS opens the numeric keyboard.
- This is the same viewport-root principle used for proven iPhone fixed-action components: do not rely on position:fixed inside overflow/clipping/containment contexts.
- Never reparent an already-focused iOS input: doing so drops focus and can prevent the keyboard from opening. visualViewport resize/scroll events then keep the pre-mounted dock inside the visible area while iOS animates the keyboard.
- The underlying delivery section is prevented from drifting upward; the picker is restored to its original DOM position after the keyboard closes.

Preserved from v0.10.26:
- Always-visible IN STOCK / OUT OF STOCK catalogue toggle.
- Target-stock replenishment safeguards and out-of-stock review flow.
- Compact Combined Suggested Delivery UI.
- Single-file iOS PDF share/print flow and alternating PDF row shading.

TEST BUILD — verify tapping New Delivery Qty opens the numeric keyboard immediately, Qty remains visible, and the layout returns cleanly when the keyboard closes.
