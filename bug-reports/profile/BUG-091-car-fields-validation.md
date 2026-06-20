# BUG-091 — Profile / Car: no validation on "Make & model", "Colour", "Number"

| Field | Value |
|---|---|
| **ID** | BUG-091 (Taiga #91) |
| **Module** | Profile |
| **Severity** | Major |
| **Priority** | Medium |
| **Type** | Validation |
| **Platform** | iOS |
| **Build** | v1.0.8 |
| **Related requirement** | REQ-TRIP-01 |
| **Status** | Open |

## Preconditions
- HamSafar is open
- User is authenticated
- "Car" screen open
- Make & model, Colour and Number are empty

## Steps to reproduce
1. Leave "Make & model", "Colour" and "Number" empty and tap "Save car"
2. Enter a numeric value in "Colour" (e.g. 12345) and tap "Save car"

## Actual result
Car data saves with empty values and with an invalid numeric "Colour"; no validation errors appear; "Save car" stays enabled.

## Expected result
Required and format validation runs on the car fields.

## Environment
- App build: v1.0.8 (iPhone 14 Pro, iOS — same session as related profile reports)

## Evidence
- `../../screenshots/BUG-091-vehicle-fields-no-validation.png`

## Notes
Relevant to REQ-TRIP-01: car data gates trip publishing, so weak car-field validation undermines that rule (see BUG-027).
