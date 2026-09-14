MAGIC DRAGON PIN v0.10.13 — AUTOMATED TEST RUNNER v2

IMPORTANT
This build belongs in a SEPARATE TEST repository / GitHub Pages site.
Do NOT deploy it over Pin Production and do NOT use the normal DEV Pages site.

Recommended repository:
magic-dragon-pin-test

Recommended Pages URL:
https://papagolfpix.github.io/magic-dragon-pin-test/

VISUAL IDENTITY
The top-right version badge is intentionally:
- yellow background
- black text
- version number + TEST
This is a permanent safety convention for TEST builds so they cannot be confused with Production or DEV.

TEST RUNNER PURPOSE
Use this environment for automated and assisted regression tests.
When iOS/Safari actions cannot be fully automated, the runner should pause, explain the exact action required, and continue after the tester confirms it.

MAGIC DRAGON PIN v0.10.13 — AUTOMATED TEST RUNNER v1

THIS IS A TEST BUILD. DO NOT DEPLOY OVER PIN PRODUCTION.

PURPOSE
One-button regression test to reduce manual back-and-forth. It runs automatic checks, pauses for a few iPhone-native checkpoints, restores the starting database, and exports one JSON evidence file for upload to ChatGPT.

HOW TO USE
1. Install/deploy this ZIP only to a separate TEST URL/repository.
2. Open it on Pin's iPhone/device.
3. Tap Run Full App Test.
4. Tap Start Full Test.
5. The runner performs automatic checks.
6. When iOS/native behavior cannot be automated, a dark checkpoint bar explains exactly what to do. Perform the action, then tap Looks good / Problem / Skip.
7. At the end tap Export Test Evidence File.
8. Upload the resulting Magic-Dragon-Test-Evidence-*.json file to ChatGPT.

SAFETY
- Creates a pre-test database restore point.
- Temporary draft changes are not meant to survive.
- Restores the database automatically at the end.
- If a test is interrupted, the next launch detects the restore point and offers immediate recovery.

AUTOMATIC CHECKS INCLUDE
- Active catalogue / parent-family structure
- Product picker contains parent names only
- Variant picker population
- Show all stock vs Use shop list catalogue counts
- Draft Add Line behavior
- Save-action viewport geometry
- Customer-facing PDF branding rule
- Exactly two active Sunday suggested dockets
- Top-up/par-stock suggestion quantities against latest Sunday reports
- Combined Suggested Delivery presence and Save/Share PDF control
- JS/runtime errors collected during test

ASSISTED IPHONE CHECKPOINTS
- Native Product / Variant selector usability
- Qty keyboard / Safari viewport visibility
- Native Create/Share PDF sheet

EVIDENCE FILE
The JSON contains PASS/WARNING/FAIL results, active-screen text/HTML snapshots, element geometry, environment/viewport data, manual checkpoint answers, and runtime errors.

KNOWN EXPECTATION
This runner is intentionally able to FAIL current discrepancies. A red result is useful evidence, not a test-runner failure.
