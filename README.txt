MAGIC DRAGON PIN v0.10.35 — TEST

Purpose of this build:
- Regression-only repair for New Delivery Qty on iPhone Safari.
- Restore the previously proven shared keyboard-safe input Lego block instead of using DOM reparenting or a new keyboard dock.

Blueprint / Lego-block rule applied:
- New Delivery Qty stays in its normal DOM position and is a standard keyboardSafeInput.
- The existing shared mobileKeyboardSafeFocus / visualViewport logic moves the real app scroll owner, not the input itself.
- No pointerdown preventDefault, no synthetic refocus, and no reparenting of the Qty field. These can suppress the iOS numeric keyboard.
- Keep the field at 16px to avoid iPhone focus zoom.

Preserved unchanged from the immediately prior test build:
- IN STOCK / OUT OF STOCK catalogue toggle.
- Target-stock replenishment safeguards and review flow.
- Combined Suggested Delivery UI and PDF/share behavior.

TEST CHECK:
Tap New Delivery Qty. The numeric keyboard must open normally, the Qty field must remain visible above it, and the layout must restore after the keyboard closes.


v0.10.35 TEST: New Delivery keyboard handling rolled back wholesale to the previously proven delivery keyboard subsystem. All v0.10.34 HUD/shell-freeze experiments were removed; no keyboard-specific reparenting or shell-geometry override remains.
