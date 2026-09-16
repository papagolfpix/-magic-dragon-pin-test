MAGIC DRAGON PIN v0.10.37 — TEST

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


v0.10.37 TEST: iPhone New Delivery Qty keyboard fix. The top #delQty field is now explicitly excluded from edit-line positioning and all manual docket scroll correction while the keyboard is open. Safari owns focus/keyboard scrolling; Edit/Suggested Delivery Qty positioning remains unchanged.


v0.10.37 targeted iPhone correction:
- New Delivery Qty is fully exempt from keyboard-layout handling.
- No deliveryKeyboardOpen class, header collapse, select(), scroll, reparent, refocus or viewport correction is permitted for #delQty.
- Edit/Suggested Delivery line-item Qty keeps the existing scroll-list keyboard Lego block.
