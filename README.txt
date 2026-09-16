MAGIC DRAGON PIN v0.10.50 — TEST

WHAT CHANGED IN v0.10.50
- Refined the duplicate Sunday-report completion flow only.
- After Keep Existing, Replace Existing, or a successful new import, the selected file(s), detected-week cards, conflict selectors, result cards, and import action state are cleared.
- A single clear completion message remains at the top of the import area.
- Keep Existing now reports: “Nothing was imported … kept exactly as-is.”
- Import and Clear Selection buttons are disabled until a new Excel file is chosen, preventing accidental repeat actions.
- Existing multi-week detection, duplicate protection, Sunday data logic, and the locked v0.10.47 Delivery form Lego block are unchanged.

TEST
1. Choose a workbook containing already imported weeks.
2. Leave all detected conflicts on Keep Existing and tap the black action button.
3. Confirm the selection/conflict area clears and only the “Nothing was imported” message remains.
4. Repeat, choose Replace for one week, and run it.
5. Confirm the selection/conflict area clears and only the replacement-complete message remains.
6. Choose a new workbook and confirm the import controls become active again.

VERSION / CACHE
- App badge: v0.10.50 TEST
- Service-worker cache: magic-pin-v0.10.50-test
