# BUG-070 — Rendering glitches from accumulating gralloc4 errors; unstable FPS

| Field | Value |
|---|---|
| **ID** | BUG-070 (Taiga #70) |
| **Module** | Cross-cutting |
| **Severity** | Major |
| **Priority** | Medium |
| **Type** | Performance / Rendering |
| **Platform** | Android |
| **Build** | v1.0.8 |
| **Related requirement** | — |
| **Status** | Open |

## Preconditions
- User is authenticated and using a VPN

## Steps to reproduce
1. Use the app actively, creating at least 4 upcoming trips

## Actual result
Smeared blobs appear instead of characters on screen; logs spam "gralloc4: Empty SMPTE 2094-40 data"; FPS drops to 2.14 / 4.32 / 6.34 / 7.18 fps.

## Expected result
Stable GUI; no thousands of repeated rendering-error lines in the logs.

## Environment
- Device: Xiaomi Redmi Note 10S, Android 13, MIUI 14
- App build: v1.0.8

## Evidence
- `../../screenshots/BUG-070-render-glitch-gralloc4.jpg`

## Notes
Found via prolonged-use exploratory testing; attach a logcat excerpt as evidence.
