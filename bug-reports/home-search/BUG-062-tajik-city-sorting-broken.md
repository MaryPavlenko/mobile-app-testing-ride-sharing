# BUG-062 — City-list filtering is broken when typing a Tajik city name

| Field | Value |
|---|---|
| **ID** | BUG-062 (Taiga #62) |
| **Module** | Home & Search |
| **Severity** | Major |
| **Priority** | Medium |
| **Type** | Functional |
| **Platform** | Android |
| **Build** | v1.0.8 |
| **Related requirement** | REQ-HOME-02 |
| **Status** | Open |

## Preconditions
- User is NOT authenticated
- App is open

## Steps to reproduce
1. Tap the "From" field on Home
2. Start typing a city name, e.g. "Rudaki"

## Actual result
Type-ahead filtering does not work; the list is not narrowed as characters are entered.

## Expected result
The city is matched as the user types, filtering out non-matching entries until only the matching option remains.

## Environment
- Device: Xiaomi Redmi Note 10S, Android 13, MIUI 14
- App build: v1.0.8

## Evidence
- `../../screenshots/BUG-062-city-filter-not-working-1.png`
- `../../screenshots/BUG-062-city-filter-not-working-2.png`

## Notes
Reproduces in trip search and in trip/request creation for both From/To. Affects many Tajik cities (Khatlon and Sughd regions).
