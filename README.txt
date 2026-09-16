MAGIC DRAGON PIN v0.10.52 — TEST

WHAT CHANGED IN v0.10.52
- Added a catalogue-vs-Sunday-report discrepancy check to the Excel preflight screen.
- Each detected weekly block is compared with the active product list expected for that branch.
- If active products are missing, shop rows are unmapped/new, or mapped products are unexpected for that branch, the app shows a clear amber REVIEW warning before import.
- The warning lists counts and the first affected product names, but does not block import because legitimate catalogue/report differences can occur.
- A fully aligned report shows a compact green catalogue-check confirmation.

PRESERVED
- v0.10.47 delivery fixed-top / scrolling-middle / fixed-bottom Lego block is unchanged.
- Multi-week Sunday worksheet detection is unchanged.
- Duplicate-week keep/replace protection from v0.10.48-v0.10.50 is unchanged.
- Safe Sunday-report deletion protection from v0.10.51 is unchanged.

TEST
1. Open Sunday Reports > Import Reports.
2. Choose a known Sunday Excel workbook.
3. Review the detected weekly block(s).
4. Confirm each block now shows either Catalogue check aligned or an amber Catalogue check — review before import warning.
5. If a warning appears, verify the counts/product names make sense; import remains available.

BUILD
- App badge: v0.10.52 TEST
- Service-worker cache: magic-pin-v0.10.52-test
