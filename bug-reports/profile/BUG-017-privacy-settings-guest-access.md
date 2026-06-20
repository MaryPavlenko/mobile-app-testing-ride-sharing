# BUG-017 — Profile privacy settings are reachable by an unauthenticated user

| Field | Value |
|---|---|
| **ID** | BUG-017 (Taiga #17) |
| **Module** | Profile |
| **Severity** | Major |
| **Priority** | High |
| **Type** | Functional / Access control |
| **Platform** | iOS |
| **Build** | v1.0.8 |
| **Related requirement** | REQ-PROF-01 |
| **Status** | Open |

## Preconditions
- User is not authenticated

## Steps to reproduce
1. Open the app
2. Do not log in
3. Go to the Profile tab
4. Open "Privacy and security"

## Actual result
An unauthenticated user can access the privacy settings.

## Expected result
"Privacy and security" must be available only to authenticated users; a guest must not reach it.

## Environment
- OS: iOS 26.4.2
- App build: v1.0.6
