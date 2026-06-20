# BUG-059 — Search is not blocked when there is no internet connection

| Field | Value |
|---|---|
| **ID** | BUG-059 (Taiga #59) |
| **Module** | Home & Search |
| **Severity** | Major |
| **Priority** | High |
| **Type** | Network |
| **Platform** | iOS |
| **Build** | v1.0.8 |
| **Related requirement** | REQ-HOME-03 |
| **Status** | Open |

## Preconditions
- The device has no internet

## Steps to reproduce
1. Launch the app
2. Choose an origin and a destination
3. Tap "Search"

## Actual result
The "Search" button turns into a loader; after ~50 seconds the search result is empty.

## Expected result
An alert: "No internet access".

## Environment
- OS: iOS 16.7.16
- App build: v1.0.8
