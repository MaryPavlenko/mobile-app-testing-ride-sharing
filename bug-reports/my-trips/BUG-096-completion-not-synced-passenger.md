# BUG-096 — Trip completes for the driver but not for the passenger

| Field | Value |
|---|---|
| **ID** | BUG-096 (Taiga #96) |
| **Module** | My Trips |
| **Severity** | Major |
| **Priority** | High |
| **Type** | Functional / Data |
| **Platform** | Both |
| **Build** | v1.0.8 |
| **Related requirement** | REQ-MYTRIPS-01 |
| **Status** | Open |

## Preconditions
- Two accounts exist: driver and passenger
- The driver has a created trip
- The passenger can find and book it

## Steps to reproduce
1. Sign in as the driver and create a trip (Dushanbe — Khujand, today, 23:39, 80 TJS)
2. Confirm the trip appears in My Trips → Active
3. Sign in as the passenger, find and request the trip
4. Sign in as the driver and confirm the passenger's booking
5. Sign in as the passenger and confirm the trip has started in the trip chat
6. Sign in as the driver a few minutes after start time and open My Trips → History

## Actual result
The trip is marked completed for the driver but remains active/not completed for the passenger — the two sides are out of sync.

## Expected result
Trip completion is reflected consistently for both driver and passenger.

## Environment
- App build: v1.0.8 (device not recorded in the original report)
