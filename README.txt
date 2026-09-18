WHAT CHANGED IN v0.10.123 TEST
- Fixes a real correction-lifecycle bug found during v0.10.122 regression testing.
- If a linked delivered docket was edited, the week now reconciles, and the verified invoice difference is exactly ฿0, acknowledging the review now closes the correction automatically.
- Existing acknowledged zero-difference legacy corrections self-heal on load/recheck; no second acknowledgement is required.
- A zero-difference correction does not create a replacement invoice revision and does not create a next-Sunday adjustment.
- The resolved live signature is recorded so the invoice no longer remains falsely marked UPDATE REQUIRED.
- Paid invoices remain protected and all existing money values are left unchanged.

WHAT CHANGED IN v0.10.122 TEST
- A completed correction clears its old Resume conflict resolution shortcut when returning to the dashboard.
- The shortcut also disappears on the dashboard while a correction remains in progress; the dashboard keeps its own action.
- This interface change does not edit saved invoices, dockets, quantities, or amounts.

WHAT CHANGED IN v0.10.121 TEST
- A saved choice to carry a correction forward no longer hides an unreconciled invoice week.
- The dashboard says the correction is waiting for reconciliation, and offers a direct Review correction button.
- No existing invoice, correction, docket or amount is changed by this update.

WHAT CHANGED IN v0.10.120 TEST
- A Sunday top-up derived from a report never counts as a delivery into that same report, even if its saved date is earlier.
- Existing dockets and completed invoices are not edited; any misdated delivered top-up remains visibly flagged for review.
- Future marking of generated top-ups requires an actual delivery date after their source Sunday report.
- TEST-copy exclusions and original docket snapshot handling from v0.10.119 remain.
