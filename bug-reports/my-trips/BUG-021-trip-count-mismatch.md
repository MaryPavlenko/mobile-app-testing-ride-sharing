# BUG-021 — Trip count in the profile header does not match user statistics

| Field | Value |
|---|---|
| **ID** | BUG-021 (Taiga #21) |
| **Module** | My Trips |
| **Severity** | Minor |
| **Priority** | Medium |
| **Type** | Data |
| **Platform** | iOS |
| **Build** | v1.0.8 |
| **Related requirement** | REQ-MYTRIPS-02 |
| **Status** | Open |

## Preconditions
- The user has at least 1 trip

## Steps to reproduce
1. Open the user profile
2. Check the trip count in the profile header
3. Compare it with the user statistics block

## Actual result
The header shows 0 trips while statistics show 1 trip.

## Expected result
The trip count is identical across all profile sections.

## Environment
- OS: iOS 26.4.2
- App build: v1.0.8
