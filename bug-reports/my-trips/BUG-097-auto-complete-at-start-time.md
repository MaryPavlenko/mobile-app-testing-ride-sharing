# BUG-097 — Trip auto-completes for the driver at the trip start time

| Field | Value |
|---|---|
| **ID** | BUG-097 (Taiga #97) |
| **Module** | My Trips |
| **Severity** | Major |
| **Priority** | High |
| **Type** | Functional |
| **Platform** | Both |
| **Build** | v1.0.8 |
| **Related requirement** | REQ-MYTRIPS-01 |
| **Status** | Open |

## Preconditions
- Driver and passenger accounts exist
- The trip start time is set close to the current time

## Steps to reproduce
1. Sign in as the driver and create a trip (Dushanbe — Khujand, today, 23:39, 80 TJS)
2. Confirm it appears in My Trips → Active
3. Sign in as the passenger, find and request the trip
4. Sign in as the driver and confirm the request
5. Wait until (or a few minutes past) the start time
6. Reopen the driver account / refresh My Trips and check the trip status

## Actual result
The trip auto-completes for the driver at the start time, rather than at the actual end of the trip.

## Expected result
A trip should not be considered complete merely because its start time has been reached.

## Environment
- App build: v1.0.8 (device not recorded in the original report)
