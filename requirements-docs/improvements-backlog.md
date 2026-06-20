# Improvements Backlog

Enhancement ideas surfaced during testing, kept **deliberately separate from defects**. A recurring discipline on this project: not everything that feels "missing" is a bug. In an MVP, an absent feature is only a defect if it contradicts defined behaviour; otherwise it is an enhancement. Filing these correctly keeps the defect list honest and shows product judgement.

## Trip & booking

- Dedicated settings for luggage allowance.
- Dedicated settings for pets.
- Child-seat availability and age category.
- Gender-based passenger restrictions (where compliant with product/legal requirements).
- Trip conditions as discrete checkboxes rather than free-text comment only.
- Editing a published trip (currently cancel-and-recreate only).
- Price filter in search.
- Centralised message to all passengers when a driver cancels a trip.

## Security (multi-device login)

- New-device login notification.
- List of active sessions.
- Remote sign-out of another device.
- Limit on the number of active devices.
- Password-change warning on suspicious login.

## Reviews

- Open the review form manually if the prompt banner was missed.
- Two-way reviews (driver → passenger as well as passenger → driver).
- Review history shown in the profile.
- Optional link between rating and trip cancellations, if the product wants it.

## Onboarding / unauthenticated UX

- Show "My Trips" and "Add trip" in a disabled state for guests, so the need to log in is obvious, **or**
- Let a guest walk the flow up to the final step, then prompt to register — preserving entered data and returning the user to the unfinished flow after login.

## Usability

- Pull-to-refresh on lists.
- "Show password" toggle on auth screens.
- Clearer countdown for the next allowed registration attempt.
- Active, intuitive date-picker fields (currently requires a back action to change a chosen date).
