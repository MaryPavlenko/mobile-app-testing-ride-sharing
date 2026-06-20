# BUG-018 — System status-bar icons become unreadable after entering a menu

| Field | Value |
|---|---|
| **ID** | BUG-018 (Taiga #18) |
| **Module** | Profile |
| **Severity** | Minor |
| **Priority** | Medium |
| **Type** | UI |
| **Platform** | iOS |
| **Build** | v1.0.8 |
| **Related requirement** | — |
| **Status** | Open |

## Preconditions
- The app is open

## Steps to reproduce
1. Open the app
2. Go to the Profile tab
3. Open any menu

## Actual result
Status-bar icons (time, battery, signal) turn white and become poorly readable / unreadable on a light background.

## Expected result
Status-bar icon colour contrasts correctly with the background and stays readable on every screen.

## Environment
- OS: iOS 26.4.2
- App build: v1.0.6
