WHAT CHANGED IN v0.10.130 TEST

- Fixes the Financial > Review Sunday Report dead end.
- A spreadsheet-total mismatch is now resolved inside the Sunday Workflow; it no longer opens the iPhone file picker.
- The mismatch card shows Resolve mismatch and Open saved report.
- Resolve mismatch explicitly lets the user acknowledge the spreadsheet formula problem and use the calculation from all imported product lines.
- The acknowledgement is tied to the exact mismatch signature. If report data changes later, the red flag automatically returns.
- The original spreadsheet totals remain preserved for audit.
- Generic Review Sunday Report actions now open the saved Sunday Reports area rather than the file picker.
- Preserves v0.10.129 fixes: Saturday/Sunday cycle grouping, spreadsheet financial-integrity detection, and targeted cleanup of the stale Lamai 23-Aug test adjustment.

TEST FIRST. Do not deploy to Pin production until this flow is verified.
