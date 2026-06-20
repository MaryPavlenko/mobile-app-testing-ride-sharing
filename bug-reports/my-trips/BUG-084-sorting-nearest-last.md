# BUG-084 — "My Trips" sorts the nearest trip to the bottom of the list

| Field | Value |
|---|---|
| **ID** | BUG-084 (Taiga #84) |
| **Module** | My Trips |
| **Severity** | Minor |
| **Priority** | Medium |
| **Type** | Functional |
| **Platform** | Android |
| **Build** | v1.0.8 |
| **Related requirement** | REQ-MYTRIPS-01 |
| **Status** | Open |

## Preconditions
- The user has at least 2 trips on different dates
- User (driver) is authenticated
- "My Trips" → "Active" tab is open

## Steps to reproduce
1. Observe the trip sort order by date

## Actual result
Sorting is reversed: the nearest trip is at the bottom of the list.

## Expected result
The closer the departure date/time, the higher the trip in the list (nearest first).

## Environment
- Device: Xiaomi Redmi Note 10S, Android 13, MIUI 14
- App build: v1.0.8
