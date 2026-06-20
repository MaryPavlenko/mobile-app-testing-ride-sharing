# BUG-082 — Account deletion is not yet available

| Field | Value |
|---|---|
| **ID** | BUG-082 (Taiga #82) |
| **Module** | Account deletion |
| **Severity** | Major |
| **Priority** | Medium |
| **Type** | Functional / Missing feature |
| **Platform** | Both |
| **Build** | v1.0.8 |
| **Related requirement** | REQ-AUTH-05 |
| **Status** | Open |

## Preconditions
- User is authenticated

## Steps to reproduce
1. Open Profile and scroll to the bottom → "Delete account"
2. Tap "Delete account" → a confirmation alert appears
3. Confirm deletion

## Actual result
Account deletion is not available — the flow cannot be completed.

## Expected result
Tapping "Delete account" → confirmation (ideally with a reason survey) → on confirm, the account is deleted and the user is logged out.

## Environment
- Platform: both (device not recorded in the original report)
- App build: v1.0.8
