MAGIC DRAGON PIN v0.10.19 — TEST iOS KEYBOARD DISMISS CLEANUP v1

DEPLOY TO TEST ONLY: magic-dragon-pin-test
DO NOT deploy to Production yet.

Focus: wait for iOS visualViewport to recover after blur before validating final UI cleanup.
The runner now samples viewport height for up to about 2 seconds, rebuilds New Delivery, allows final layout settle, then validates all controls.
