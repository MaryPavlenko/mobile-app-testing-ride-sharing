# BUG-060 — App does not warn the user that there is no internet while in use

| Field | Value |
|---|---|
| **ID** | BUG-060 (Taiga #60) |
| **Module** | Cross-cutting |
| **Severity** | Major |
| **Priority** | Medium |
| **Type** | Network |
| **Platform** | iOS |
| **Build** | v1.0.8 |
| **Related requirement** | — |
| **Status** | Open |

## Preconditions
- None

## Steps to reproduce
1. Launch the app
2. Go to "My Trips"
3. Disable internet on the device
4. Go to "Home"
5. Run a trip search

## Actual result
Search returns trips even with internet disabled.

## Expected result
An alert: "No internet connection".

## Environment
- OS: iOS 16.7.16
- App build: v1.0.8

## Notes
Likely stale/cached data being served while offline — worth a data-freshness check once DB access is available.
