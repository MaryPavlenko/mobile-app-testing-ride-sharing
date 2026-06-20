# BUG-041 — Tapping the date field on Home opens an empty calendar

| Field | Value |
|---|---|
| **ID** | BUG-041 (Taiga #41) |
| **Module** | Home & Search |
| **Severity** | Major |
| **Priority** | High |
| **Type** | Functional |
| **Platform** | Android |
| **Build** | v1.0.8 |
| **Related requirement** | REQ-HOME-02 |
| **Status** | Open |

## Preconditions
- Launch the app
- On the Home tab

## Steps to reproduce
1. Tap the date field

## Actual result
An empty calendar opens.

## Expected result
A calendar opens that allows selecting a trip date.

## Environment
- Device: POCO M3 Pro 5G, Android 13, MIUI 14.0.6
- App build: v1.0.8

## Evidence
- `../../screenshots/BUG-041-home-empty-calendar.png`
