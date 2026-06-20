# BUG-094 — Profile / Privacy: incorrect error message on wrong current password

| Field | Value |
|---|---|
| **ID** | BUG-094 (Taiga #94) |
| **Module** | Profile |
| **Severity** | Minor |
| **Priority** | Medium |
| **Type** | UI / Copy |
| **Platform** | Both |
| **Build** | v1.0.8 |
| **Related requirement** | — |
| **Status** | Open |

## Preconditions
- HamSafar is open
- User is authenticated
- "Privacy and security" screen open

## Steps to reproduce
1. In "Change password" tap "Current password" and enter a wrong current password
2. Enter a valid new password in "New password"
3. Repeat it in "Repeat new password"
4. Tap "Update password"

## Actual result
The password is not updated and the message "Invalid email or password" is shown — but no email is entered on the change-password screen, so the message does not match the action.

## Expected result
On a wrong current password, a message that matches the change-password error is shown, pointing to the correct field.

## Environment
- App build: v1.0.8 (iPhone 14 Pro, iOS — same session as related profile reports)
