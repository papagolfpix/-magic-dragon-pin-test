MAGIC DRAGON PIN v0.10.18 — TEST UI STATE RESTORE v1

DEPLOY TO TEST ONLY: magic-dragon-pin-test
DO NOT deploy to Production yet.

Fix:
The automated run could restore the database but leave the Delivery UI in keyboard-compressed state.

Now the runner also:
- blurs focused inputs;
- removes keyboard/test state classes;
- returns to a clean New Delivery screen;
- waits for visualViewport recovery;
- verifies Branch, Date, Product, Variant, Qty, Add and Save all have visible geometry;
- adds an Automatic UI state cleanup PASS/FAIL;
- captures a post-test-clean-ui snapshot.

A run is complete only when both data and UI state are restored.
