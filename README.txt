MAGIC DRAGON PIN v0.10.27 — TEST

Purpose of this build:
- Regression-only fix for New Delivery Qty visibility on iPhone Safari.
- Preserve the working IN STOCK / OUT OF STOCK catalogue toggle and all v0.10.26 business/PDF logic unchanged.

Blueprint / Lego-block rule applied:
- The New Delivery Product / Variant / Qty / Add controls are temporarily mounted directly under document.body while the numeric keyboard is open.
- This is the same viewport-root principle used for proven iPhone fixed-action components: do not rely on position:fixed inside overflow/clipping/containment contexts.
- visualViewport resize/scroll events keep the dock inside the visible area while iOS animates the keyboard.
- The underlying delivery section is prevented from drifting upward; the picker is restored to its original DOM position after the keyboard closes.

Preserved from v0.10.26:
- Always-visible IN STOCK / OUT OF STOCK catalogue toggle.
- Target-stock replenishment safeguards and out-of-stock review flow.
- Compact Combined Suggested Delivery UI.
- Single-file iOS PDF share/print flow and alternating PDF row shading.

TEST BUILD — verify New Delivery Qty remains visible when the iPhone numeric keyboard opens and returns cleanly when it closes.
