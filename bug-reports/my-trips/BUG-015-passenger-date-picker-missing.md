# BUG-015 — My Trips (Passenger): date picker does not open

| Field | Value |
|---|---|
| **ID** | BUG-015 (Taiga #15) |
| **Module** | My Trips |
| **Severity** | Major |
| **Priority** | High |
| **Type** | Functional |
| **Platform** | Android |
| **Build** | v1.0.8 |
| **Related requirement** | REQ-HOME-02 |
| **Status** | Open |

## Preconditions
- HamSafar is open
- "My Trips" tab open, "I'm a passenger" role

## Steps to reproduce
1. Enter Dushanbe in "From"
2. Enter Khujand in "To"
3. Tap the date field

## Actual result
The calendar in the date picker does not open; the only available value is the previously set "Tomorrow".

## Expected result
A calendar opens for date selection.

## Environment
- Device: Xiaomi Pad 6
- OS: Android 14 (UKQ1.240624.001)
