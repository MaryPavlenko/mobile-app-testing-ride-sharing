# Checklist #10 — Push Notifications

Format: `check → expected result`. **⚠ Found:** links a check to a defect.
Related requirements: REQ-NOTIF-01. Triggers: messages and bookings.

## System permissions
- First launch → the system notification-permission prompt appears. **⚠ Found: BUG-034** (no prompt on iOS first launch).
- Grant permission → pushes arrive. Deny → no pushes.
- Disable permission in system settings and restart → no pushes; re-enable → pushes arrive.
- Pushes land in the notification centre. Settings persist between sessions and across other devices of the same account.

## Toggle "Messages"
- On → a new message produces a notification; Off → it does not.
- The push contains the sender name and message text.
- Tapping the push → opens the right chat; the push appears in the notification centre.

## Toggle "Booking confirmation"
- On → a request status change produces a push; Off → it does not.
- The push contains correct booking data; tapping it opens the right booking; it appears in the notification centre.

## Toggle "Trip reminders"
- On → a departure/meeting reminder push arrives; Off → it does not.
- The push contains correct time and trip details; tapping it opens the right trip.

## Toggle "Promos & news"
- Off by default → no promo pushes; On → promo/route pushes arrive; Off again → they stop.

## Notification centre
- Several pushes of different categories display correctly without overwriting each other.
- Tapping any notification opens the right screen.
- With permission revoked in system settings → pushes do not appear in the centre.

## Sync across sessions / devices (same account)
- Change a toggle → close and reopen the app → setting kept.
- Change a toggle → log out and back in → setting kept.
- Change settings on device A → device B with the same account matches (all off on A → all off on B; on A → on on B).

> ⚠ Access limit: see BUG-023 / BUG-025 / BUG-086 for in-app delivery and tap-through defects found while exercising this checklist.
