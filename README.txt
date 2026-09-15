MAGIC DRAGON PIN v0.10.24 — TEST
UI-only cleanup: Combined Suggested Delivery now uses compact docket spacing and bottom-right dark Create / Share PDF action.

Suggested-docket workflow refinement:
- moves Review before top-up to the top of each suggested docket, immediately below the docket header;
- uncertain / possible out-of-stock items are therefore resolved before the confirmed delivery lines are reviewed;
- Out of stock still removes the item from suggested top-ups and marks the master SKU;
- Keep top-up still moves the item into the confirmed top-up lines for that Sunday;
- retains all v0.10.21 replenishment safeguards and the Cali Mousse target override;
- service-worker cache key bumped for a clear iPhone refresh.

TEST BUILD — verify review actions and line movement before production promotion.
Changes in v0.10.24 TEST:
- Fixed Combined Suggested Delivery PDF generation to produce a standards-valid single PDF for iOS Preview/Print.
- Native Share now sends exactly one PDF file (no title/text payload).
- PDF button resets before the iOS share/print sheet opens, preventing a stuck Preparing state.
