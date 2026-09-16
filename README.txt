MAGIC DRAGON PIN v0.10.49 — TEST

WHAT CHANGED IN v0.10.49
- Added explicit duplicate Sunday-week protection to the Excel import preflight.
- Existing branch/date reports are highlighted before import.
- Default action is KEEP EXISTING; replacement must be explicitly selected.
- Selecting the same branch/date more than once in one import batch is blocked before any data changes.
- Replacing a report removes the old linked Excel week and archived source file, then stores the new source and report.
- Multi-week-in-one-sheet detection is preserved unchanged.
- v0.10.47 Delivery form Lego block is preserved unchanged.

TEST
1. Choose a Sunday workbook containing a week already imported.
2. Confirm it is marked Already imported before pressing Import.
3. Leave Keep existing selected and import: existing data must remain untouched.
4. Repeat and choose Replace existing: the new report should replace the old one once, with no duplicate week left behind.
5. Select two files containing the same branch/date: import must stop and ask you to uncheck one copy.

VERSION / CACHE
- App badge: v0.10.49 TEST
- Service-worker cache: magic-pin-v0.10.49-test


v0.10.49 duplicate-import UX refinement:
- Existing-report conflict box now spans the full available width on mobile.
- Keep Existing gives an immediate visible no-change confirmation.
- Replace Existing gives a clear success confirmation and clears the processed file so the same conflict screen is not immediately redisplayed.
- Delivery docket v0.10.47 Lego block unchanged.
