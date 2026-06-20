# App Overview — Reconstructed Logic

There was no specification for HamSafar. This document is the consolidated understanding of the app, reconstructed from team communication and hands-on exploration, and used as the working baseline for all checklists, test cases and defects. Items marked **(needs clarification)** were open product questions at the time of testing; the full list is in [open-questions.md](open-questions.md).

The app is an MVP: some behaviour is defined, some is intentionally not yet built and was routed to the [improvements backlog](improvements-backlog.md).

## 1. General

- **Stage:** MVP.
- **Markets:** Uzbekistan and Tajikistan. Cities in the app must belong to these countries.
- **Language:** Russian only; no language switch in the MVP.
- **Currency:** the driver sets the trip price, and it is shown on the trip card. Exact currency handling **(needs clarification)** — whether the driver picks the currency manually, whether it is derived from the route country, and whether UZS and TJS are both supported.

## 2. Payment & fees

In-app payment does **not** exist. The passenger does not pay inside the app, the driver is not paid through the app, and there is no commission or service fee. Payment is by personal agreement.

**To verify:** no mandatory payment step; no payment screen during booking; no fee/surcharge; no misleading copy implying the app processes money.

## 3. Trip price

The driver enters the price; it appears on the trip card and in trip details. The app does not compute or influence price. There is no price filter yet, and its absence is not a bug in the MVP.

**Needs clarification:** whether a trip can be created without a price; min/max price bounds (testing surfaced that values above 1000 are silently capped at 1000); whether 0 is allowed; whether decimals are allowed; how currency is determined.

## 4. Trip creation & publishing (Driver)

- If the driver's profile has **no car data**, the trip must **not** publish. Correct behaviour: the trip does not disappear and does not publish — it stays in a blocked/unpublishable state, and the user can see why publishing is blocked.
- A **published trip cannot be edited**. To change date/time/details, the driver cancels it and creates a new one.

**To verify:** driver without car data cannot publish; the draft is not lost and is shown as blocked with a visible reason; published trips are not editable but can be cancelled.

## 5. Trip card

Should contain everything a passenger needs to decide:

- **Driver:** avatar, name, rating, tap-through to the public driver profile.
- **Trip:** car, trip conditions, price, number of free seats, pickup point, destination.

Some fields are filled in the profile, some at trip creation.

## 6. Luggage, pets, child seats, restrictions

None of these have dedicated settings yet. There are no separate required fields for luggage, pets, child seats, age category, or gender restrictions, and no system-level block on booking with luggage/pet. Such details, if needed, can only go in the free-text trip comment. All of these are enhancement candidates (see backlog).

## 7. Booking & cancellation

- A passenger can cancel a **confirmed** trip; on cancellation, a **push goes to the other party**.
- **My Trips** contains: requests, active trips, archive.
- A driver can cancel a published trip.
- **Needs clarification:** whether a passenger can cancel an *unconfirmed* request, and whether the driver is notified if so.

**To verify:** passenger can cancel a confirmed trip; the other party receives a push; cancelled items appear correctly in My Trips; active vs archive are separated correctly.

## 8. Chat, calls, phone number

There is an in-app chat. There is no VoIP call feature and no number masking; the phone number is not shown on the trip card. A call button lives inside the chat.

**Needs clarification:** whether the chat is created automatically on booking; at which stage the chat and the call button appear.

## 9. Rating & reviews

- Rating depends only on reviews. Cancelling a trip does not affect rating programmatically. A complaints/report feature exists.
- **Known bug:** a default rating of **5 stars shown for users with no reviews** is incorrect.
- A review can be left after a **completed** trip. After completion, a banner *"Leave a review"* appears in the chat with the driver → tapping opens a 1–5 star + comment form.
- **Banner behaviour:** first dismiss (×) hides it; it reappears after **6 hours**; a second dismiss hides it permanently; submitting a review removes it permanently.

## 10. Multi-device login

A user can log in on a second device; the first device is **not** logged out, data is fully carried over, and (currently) no new-login notification is sent and no security check applies. This is expected current behaviour but a **security weak spot** — candidates for the backlog: new-device login alerts, active-session list, remote sign-out, device limit, password-change warning on suspicious login.

## 11. Home screen & auth state

If the user is **not** logged in, the home screen shows a plain greeting. If logged in, the user's name is added to the greeting.

## 12. Time zones

Uzbekistan and Tajikistan are both UTC+5, so there is no time-zone difference between routes within these two countries; trip times should display identically. If countries with different offsets are added later, local-time logic will be needed.

## 13. Notifications

A push must be sent to the other party on trip/request cancellation. The "99+" counter behaviour could not be fully verified because mass-generating notifications required admin/DB/API access not available to most testers. Via UI it was possible to verify: receiving a single notification, the counter display, tapping through, counter reset after viewing, and push on cancellation.
