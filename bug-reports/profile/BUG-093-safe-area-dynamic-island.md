# BUG-093 — Profile: UI ignores safe area on iPhone 14 Pro in landscape (Dynamic Island overlap)

| Field | Value |
|---|---|
| **ID** | BUG-093 (Taiga #93) |
| **Module** | Profile / nested screens |
| **Severity** | Minor |
| **Priority** | Medium |
| **Type** | UI |
| **Platform** | iOS (device-specific) |
| **Build** | v1.0.8 |
| **Related requirement** | — (general UI quality) |
| **Status** | Open |

## Preconditions
- HamSafar open on an iPhone 14 Pro.
- App in landscape orientation, user in the Profile section.

## Steps to reproduce
1. Rotate the device to landscape.
2. Open Profile nested screens (Edit profile, Car, Notifications, Privacy, For passengers, For drivers, Support, Suggest an idea, Terms, Privacy policy).
3. Check the layout of elements near the left system area.

## Actual result
In landscape on iPhone 14 Pro, left-side UI elements sit too close to the system area; part of the UI falls into the unsafe area near the Dynamic Island / notch and can be partially overlapped. Reproduces across several Profile sub-screens — the interface does not respect the device safe area in landscape.

## Expected result
The UI respects the iPhone 14 Pro safe area in landscape; no element (back button, headers, input fields) enters the Dynamic Island / cutout region.

## Environment
- Device: iPhone 14 Pro
- App build: v1.0.8

## Evidence
- `../../screenshots/BUG-093-dynamic-island-safe-area.png`

## Notes
- Device- and orientation-specific. Lower severity (cosmetic, narrow device set) but worth a Medium priority because it affects a flagship device class and multiple screens at once.
