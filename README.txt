MAGIC DRAGON PIN — v0.10.132 TEST

Targeted historical repair test.

Repairs the missing 13 Sep 2026 historical invoice/completed Sunday entry only when both surviving 13 Sep branch reports are present and their saved totals exactly reconstruct THB 9,156.5.

The repair is intentionally guarded and one-time. It does not change the current 20 Sep invoice, payment status, reports, deliveries, or live calculations.

Expected after first load:
- Records / Invoices contains MD-20260913 for THB 9,156.5.
- 13 Sep appears as a historical paid week rather than adding to current due.
- Current due remains THB 9,658.
- Current 20 Sep invoice/payment state is unchanged.
