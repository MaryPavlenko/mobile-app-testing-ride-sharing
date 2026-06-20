# BUG-076 — A trip can be created with identical origin and destination

| Field | Value |
|---|---|
| **ID** | BUG-076 (Taiga #76) |
| **Module** | Trip creation |
| **Severity** | Major |
| **Priority** | Medium |
| **Type** | Validation / Business rule |
| **Platform** | Android |
| **Build** | v1.0.8 |
| **Related requirement** | REQ-TRIP-04 |
| **Status** | Open |

## Preconditions
- User is authenticated
- Create-trip form filled for any valid date with identical (matching) origin and destination

## Steps to reproduce
1. Tap "Publish trip"

## Actual result
The trip is published and bookable; the app even computes a travel time of 03h 45m.

## Expected result
The app blocks a trip whose origin and destination match and shows "Origin and destination cannot be the same" — the app is for intercity trips.

## Environment
- Device: Xiaomi Redmi Note 10S, Android 13, MIUI 14
- App build: v1.0.8

## Evidence
- `../../screenshots/BUG-076-same-origin-destination-trip.png`
- `../../screenshots/BUG-076-same-origin-destination-request.png`
