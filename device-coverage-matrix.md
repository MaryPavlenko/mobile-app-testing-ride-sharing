# Device Coverage Matrix

Real-device coverage across the two platforms. A distributed team meant a genuinely varied device pool — useful for catching device- and OEM-specific issues (e.g. MIUI behaviour, Dynamic Island safe-area, gralloc rendering).

## iOS (via TestFlight)

| Device | iOS | Notes |
|---|---|---|
| iPhone 14 Pro | latest | Surfaced safe-area / Dynamic Island issue in landscape (BUG-093) |
| iPhone (older, iOS 16.x) | 16.7.x | Chat re-entry message loss (BUG-022) |
| iPhone (current, iOS 26.x) | 26.4.2 | Booking send-button hidden (BUG-019), rating-5 (BUG-020) |

## Android (beta builds)

| Device | Android / shell | Notes |
|---|---|---|
| Google Pixel 7 | Android 17 Beta | Trip without car data (BUG-027), minor driver (BUG-079) |
| Xiaomi Redmi Note 10S | Android 13, MIUI 14 | Past-departure booking (BUG-071); MIUI-specific log capture |
| Xiaomi Pad 6 | Android 14 | My Trips date/validation issues (BUG-013/14/15) |

## Log capture
- **Android:** developer-options bug report (`*#*#284#*#*` on MIUI) / `logcat` via Android Studio over USB debugging.
- **iOS:** TestFlight feedback + screen recordings.
- **Network conditions:** tested with/without VPN and on slow connections to validate offline and loading states.
