# Checklist #11 — Notifications Feed

The home-screen bell shows the unread counter. Format: `check → expected result`.
Related requirements: REQ-NOTIF-02, REQ-NOTIF-03.

## Counter display
- Logged-in user → home screen shows the bell icon.
- Has unread → a counter is shown on the bell; no unread → no counter / 0.

## Counter updates
- Reading one notification decrements the counter by 1; reading all clears it / shows 0.
- A new notification increments it.
- The counter keeps its correct value after app close/reopen and after logout/login.

## Opening notifications
- Tapping the bell opens the notifications feed; the user's notifications are listed.
- Opening an unread notification marks it read; returning home updates the counter.

## Boundary checks
- 1 unread → bell shows "1".
- Many unread → counter renders correctly.
- Unstable network → counter renders without display errors.
- After app restart → counter shows the correct unread count.

## Counter UI
- The counter is positioned correctly over/next to the bell.
- Single-digit and double-digit (10+) values render fully without truncation.
- More than 99 unread → shows "99+", with the "+" not wrapping to a new line. **⚠ Not testable** without admin/DB/API to mass-generate notifications — see [open question #15](../docs/open-questions.md) and the [test strategy](../test-design/test-strategy.md).
- Counter is readable in light and dark themes, and at increased system font scale.

## Cross-device sync
- Same account on two devices → a new notification shows the same counter on both.
- Reading a notification on device A updates the counter on device B; reading all on A clears/zeroes it on B.

## Bulk receipt
- Two notifications received in quick succession → counter increments by 2; the feed shows them in the correct order. **⚠ Partially blocked:** bulk generation needs back-end access (see "99+" above).
