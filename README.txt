MAGIC DRAGON PIN v0.10.26 — TEST

Purpose of this build:
- Add an always-visible two-state IN STOCK / OUT OF STOCK control to every active product variant in Product catalogue.
- Fix the iPhone New Delivery Qty-field keyboard regression so the quantity control remains visible above the numeric keyboard.

Stock-status behaviour:
- Every active catalogue variant shows a clear IN STOCK / OUT OF STOCK segmented switch.
- Marking OUT OF STOCK persists on the master product and removes that SKU from current automatic suggested top-ups.
- Switching back to IN STOCK reactivates the SKU for future top-up calculations.
- Archive/Restore remains a separate catalogue lifecycle control.

Keyboard behaviour:
- New Delivery Qty now scrolls the actual active app section rather than the wrong page/document container.
- Repositions repeatedly through the iOS visualViewport keyboard animation so the Qty field cannot be pushed above the visible screen.
- Existing Edit/Suggested Delivery quantity keyboard handling is preserved.

Preserved from v0.10.25:
- Validated target-stock replenishment safeguards and review-before-top-up flow.
- Cali Mousse product-specific target override.
- Compact Combined Suggested Delivery UI.
- Single-file iOS PDF share/print flow and alternating PDF row shading.

TEST BUILD — verify catalogue stock-status toggling and New Delivery Qty visibility on iPhone before production promotion.
