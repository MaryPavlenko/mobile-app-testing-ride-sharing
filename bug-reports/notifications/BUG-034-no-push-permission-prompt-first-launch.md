# BUG-034 — No system push-permission prompt on first launch

| Field | Value |
|---|---|
| **ID** | BUG-034 (Taiga #34) |
| **Module** | Notifications |
| **Severity** | Major |
| **Priority** | High |
| **Type** | Functional |
| **Platform** | iOS |
| **Build** | v1.0.8 |
| **Related requirement** | REQ-NOTIF-01 |
| **Status** | Open |

## Preconditions
- HamSafar installed via TestFlight on iPhone 17, iOS 26.4.2
- App is launched for the first time after install

## Steps to reproduce
1. Install HamSafar via TestFlight
2. Launch the app for the first time
3. Check whether the iOS push-permission prompt appears

## Actual result
The system push-permission prompt is not shown, and push notifications also cannot be configured in device settings.

## Expected result
On first launch the iOS system prompt to allow push notifications is displayed.

## Environment
- Device: iPhone 17
- OS: iOS 26.4.2
- App build: TestFlight v.1.0 (2)
- UI language: Russian

## Evidence
- `../../screenshots/BUG-032-free-seats-incorrect.png`

## Notes
Without the first-launch prompt, no push permission is ever granted, which blocks the entire push feature on iOS — hence High priority.
