# Checklist #6 — Trip Details & Booking

One account can act as both **driver** and **passenger**, so this module is tested from both sides. Format: `check → expected result`. **⚠ Found:** links a check to a defect.
Related requirements: REQ-BOOK-01…05, REQ-CHAT-01.

## 1. Trip details — Driver view
- The trip details card/screen opens from the list.
- Trip data shown: origin, destination, date, departure time, arrival time, price (UZS / TJS), free seats, car data, seat count.
- Long city/address names do not break the layout; missing data is handled gracefully.
- Details match the data in the trip list.

## 1.1 Trip details — Passenger view
- Details open from the list and show: origin, destination, date, departure/arrival time, price (UZS / TJS), free seats, **driver avatar, name, rating, link to driver profile**, car data (if absent, the trip should never have been published — see REQ-TRIP-01).
- Phone number / call option is **not** shown on the trip card (only in chat).
- Long names and missing data do not break the layout; details match the list.

## 2. Public driver profile (future trips)
- The public driver profile opens from the trip card and shows future trips only (`departureDate > now`), sorted ascending by date; past trips are not shown; trips from another marketplace are not shown.
- Profile shows: avatar, driver name, rating, reviews, completed-trip count, registration date, phone/email verification status, an "About" block with trip rules, and a "Report user" link.

## 3. Booking — Passenger side
- Search results can be sorted by departure date.
- The booking button is available from trip details and only to authenticated users.
- A passenger can send a booking request; the correct status is shown afterwards.
- A chat between driver and passenger is available after booking/confirmation.
- A passenger can cancel a previously sent but **not-yet-confirmed** request. **⚠ Found: Taiga #31** (see open question OQ-7).
- Re-sending a request to the same trip is unavailable when there are no free seats; request sending is idempotent against available seats.
- Booking is blocked when there are no free seats (button disabled); a completed/cancelled trip cannot be booked. **⚠ Found: BUG-071** (already-departed trip is bookable).
- A passenger can cancel a previously **confirmed** trip → status becomes "Cancelled", the driver gets a push, the seat returns to available, the record is kept in My Trips → Archive. **⚠ Found: BUG-061** (passenger cannot cancel).
- Open question: does cancellation affect the passenger's rating programmatically, or only reviews? (OQ-9)

## 4. Request confirmation — Driver side
- The driver sees the incoming request (pending status if applicable) and can confirm or reject it; status updates accordingly on both sides.
- On confirmation the available-seat count decreases; the chat is available; the last free seat is handled correctly for extra requests.
- The driver can cancel a confirmed booking and can cancel the whole trip. **⚠ Found: BUG-058** (driver cannot cancel a trip).

## 5. Access & roles
- A user sees only driver-specific actions as a driver, and passenger-specific actions as a passenger.
- A driver cannot book their own trip (if disallowed); a passenger cannot confirm a request without the driver role on that trip.
- Switching role context updates the UI and actions correctly.
- An unauthenticated user has no access to search or trip details. **→ IMP-016** (guest-flow handling).

## 6. Cross-screen behaviour
- List → details navigation works without delays > 2s; a loader (not a white screen) is shown on slow loads.
- Details → booking does not lose data; driver profile → future trips works.
- Data stays consistent after a refresh; backgrounding/foregrounding does not change the data; system Back does not break the screen state.
- Build 1.0.8 (Android): Manrope font across the app.

## 7. Boundary & negative scenarios
- Trip with date exactly `now` (boundary).
- Very large number of future trips in a driver profile; zero future trips.
- All trips are within a single time zone (UTC+5).
- No server connection on open/booking. **⚠ Found: BUG-059, BUG-060.**
- Low network speed; expired session; OS battery-saver throttling.
- Screen rotation does not change the data or navigate away.
- Deliberate duplicate request from one passenger.
- Re-login on another device preserves all data and does not log out the previous device (security weak spot — see REQ-AUTH-06).
