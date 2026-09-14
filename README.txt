MAGIC DRAGON PIN v0.10.14 — TEST SUNDAY TOP-UP CANDIDATE v1

DEPLOY TO:
  TEST repository only: magic-dragon-pin-test

DO NOT DEPLOY THIS TO PIN PRODUCTION YET.

CHANGES
- Sunday suggested deliveries now use:
    max(0, target stock - current Sunday closing stock)
- Targets:
    Bangrak: 1g 30 / 5g 3 / Pre-Roll 15 / Hash 10 / Gummy 15
    Lamai:   1g 6 / 5g 0 / Pre-Roll 6 / Hash 0 / Gummy 0
- Exactly two latest Sunday suggestions remain active: Bangrak + Lamai.
- Older untouched generated suggestions are removed.
- Older user-edited generated suggestions are retained as superseded history.
- A current branch suggestion can remain with zero lines if no top-up is needed.
- TEST manual prompts now minimise while you perform the requested iPhone action.

EXPECTED AFTER RUNNING FULL TEST
The previous failures:
  1. Exactly two active Sunday suggestions
  2. Top-up target calculation
should now pass.

Still intentionally separate:
  - Combined Suggested Delivery Save/Share PDF
  - Delivery Save viewport warning
