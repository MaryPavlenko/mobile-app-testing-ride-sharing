# BUG-020 — Profile: users with no reviews display a 5-star rating

| Field | Value |
|---|---|
| **ID** | BUG-020 (Taiga #20) |
| **Module** | Profile / rating |
| **Severity** | Major |
| **Priority** | High |
| **Type** | Data / UI |
| **Platform** | Both (verified on all test devices) |
| **Build** | v1.0.8 |
| **Related requirement** | REQ-PROF-03 (no reviews → no 5-star rating) |
| **Status** | Open (confirmed by QA lead as a bug) |

## Preconditions
- A user account that has no reviews.

## Steps to reproduce
1. Open the profile of a user with no reviews.

## Actual result
The profile shows a rating of 5 stars even though the user has no reviews.

## Expected result
A user without reviews should not show 5 stars. Instead the app should show no rating or a placeholder such as "No reviews yet".

## Environment
- OS: iOS 26.4.2 (also reproduced on Android)
- App build: v1.0.8

## Evidence
- `../../screenshots/BUG-020-rating-5-no-reviews-1.png`
- `../../screenshots/BUG-020-rating-5-no-reviews-2.png`

## Notes
- A default 5★ inflates trust signals in a product where rating is the *only* reputation mechanism, so although the repro is trivial it directly undermines the core trust model — hence **High** priority. Confirmed as a defect by the QA lead.
