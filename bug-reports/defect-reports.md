# Defect Reports

~80 defects found across the HamSafar MVP, reported in Taiga with reproducible steps, environment and evidence. IDs preserve the original Taiga issue numbers.

Each report follows the [`_TEMPLATE.md`](_TEMPLATE.md) format. **Every item below has its own file** in the relevant module folder (`BUG-NNN-*.md` for defects, `IMP-NNN-*.md` for improvements), translated from the original Taiga reports. The table is the triaged index.

## How severity vs priority is used here

- **Severity** = technical impact on the product (Blocker › Critical › Major › Minor › Trivial).
- **Priority** = how soon it should be fixed (High › Medium › Low).
  A trivial-severity bug on the first onboarding screen can still be high priority; a major-severity bug on an edge path can be low priority. They are rated independently.

## Index

Legend: 🐞 Bug · 💡 Improvement (routed to [backlog](../requirements-docs/improvements-backlog.md), not a defect)

### Authorization & Registration

| ID | Title | Type | Severity | Priority | Platform |
|---|---|---|---|---|---|
| #24 | "Log in" header does not switch to "Register" when toggling to registration | 🐞 | Minor | Low | iOS |
| #28 | No separators on the keyboard for manual date-of-birth entry | 🐞 | Minor | Medium | Android |
| #29 | Hard birth-year limits (1940–2010) with no user feedback | 🐞 | Minor | Low | Both |
| #30 | Keyboard does not appear when tapping the Email field during registration | 🐞 | Major | High | iOS |
| #57 | Registration succeeds with a hidden special character (space) in the password | 🐞 | Major | Medium | Both |
| #66 | "Name" field accepts digits with no "invalid name format" validation | 🐞 | Minor | Medium | Both |
| #67 | No password-recovery functionality | 🐞 | Major | High | Both |
| #80 | No explicit countdown to the next allowed registration attempt | 🐞 | Minor | Low | Both |
| #81 | No "show password" toggle | 💡 | — | — | Both |
| #82 | Account deletion not yet available | 🐞 | Major | Medium | Both |

### Home & Search

| ID | Title | Type | Severity | Priority | Platform |
|---|---|---|---|---|---|
| #35 | No validation on required "From"/"To" fields (Home + create-request, both roles) | 🐞 | Major | High | Both |
| #36–#40 | Home "From"/"To": digits, special chars and non-existent cities raise no error | 🐞 | Minor | Medium | Both |
| #41 | Tapping the date field on Home opens an empty calendar | 🐞 | Major | High | Both |
| #42–#49 | "Where from?"/"Where to?" screens: invalid input not flagged; empty "To" keeps Continue clickable | 🐞 | Major | Medium | Both |
| #50–#56 | "Create request" screen: invalid From/To input not flagged; date not selectable | 🐞 | Major | Medium | Both |
| #59 | Search not blocked when there is no internet connection | 🐞 | Major | High | Both |
| #60 | App does not warn the user that there is no internet | 🐞 | Major | Medium | Both |
| #62 | City-list sorting broken when typing a Tajik city name | 🐞 | Major | Medium | Both |

### Trip Creation (Driver)

| ID | Title | Type | Severity | Priority | Platform |
|---|---|---|---|---|---|
| #27 | App allows creating a trip without car data (violates publish rule) | 🐞 | Major | High | Both |
| #76 | App allows a trip with identical origin and destination | 🐞 | Major | Medium | Both |
| #79 | App allows a minor (under-18) driver to create a trip | 🐞 | Critical | High | Both |
| #99 | Add currency selection when the driver sets the trip price | 💡 | — | — | Both |

### Trip Details & Booking

| ID | Title | Type | Severity | Priority | Platform |
|---|---|---|---|---|---|
| #19 | "Send request" button hidden after focusing the message field — booking cannot be completed | 🐞 | Critical | High | iOS |
| #32 | Incorrect number of free seats shown on the trip card | 🐞 | Major | High | Both |
| #71 | Booking allowed on a trip whose departure time has already passed | 🐞 | Major | High | Both |

### My Trips

| ID | Title | Type | Severity | Priority | Platform |
|---|---|---|---|---|---|
| #13 | Driver: can proceed to destination without filling "From" | 🐞 | Major | High | Android |
| #14 | Driver: chosen date cannot be changed (date field inactive) | 🐞 | Minor | Medium | Android |
| #15 | Passenger: date picker does not open | 🐞 | Major | High | Android |
| #21 | Trip count in profile header does not match user statistics | 🐞 | Minor | Medium | iOS |
| #58 | Driver cannot cancel a trip | 🐞 | Critical | High | Both |
| #61 | Passenger cannot cancel their trip request | 🐞 | Critical | High | Both |
| #83 | Cannot re-book a previously confirmed-then-driver-cancelled booking | 🐞 | Major | Medium | Both |
| #84 | "My Trips" sorts the nearest trip to the bottom of the list | 🐞 | Minor | Medium | Both |
| #96 | Trip completes for the driver but not for the passenger | 🐞 | Major | High | Both |
| #97 | Trip auto-completes for the driver at the trip start time | 🐞 | Major | High | Both |

### Chat

| ID | Title | Type | Severity | Priority | Platform |
|---|---|---|---|---|---|
| #22 | Chat message disappears on re-entering the chat via the "Questions?" button | 🐞 | Major | Medium | iOS |
| #64 | Left-swipe on a chat shows "Delete chat?" (unexpected) | 🐞 | Minor | Low | Both |
| #65 | A message can be sent from a chat that is in the archive | 🐞 | Major | Medium | Both |
| #68 | Archive in/out logic for chats is inconsistent | 🐞 | Minor | Medium | Both |
| #77 | Files sent in chat cannot be opened/viewed | 🐞 | Major | Medium | Both |
| #100 | No permission prompt on the first chat attachment | 🐞 | Minor | Low | iOS |

### Profile

| ID | Title | Type | Severity | Priority | Platform |
|---|---|---|---|---|---|
| #17 | Profile privacy settings reachable by an unauthenticated user | 🐞 | Major | High | iOS |
| #18 | Status-bar icons become unreadable after entering a menu | 🐞 | Minor | Medium | iOS |
| #20 | Users with no reviews show a 5-star rating | 🐞 | Major | High | Both |
| #26 | Edit profile: keyboard does not close after phone entry, covers "Save" | 🐞 | Major | High | Both |
| #88 | Edit profile: no date-of-birth validation; can save age under 18 | 🐞 | Major | High | Both |
| #89 | Edit profile: no "Name" validation; empty or over-long value can be saved | 🐞 | Minor | Medium | Both |
| #90 | Edit profile: no email validation; invalid value can be saved | 🐞 | Major | Medium | Both |
| #91 | Car details: no validation on make/model, colour, plate | 🐞 | Major | Medium | Both |
| #92 | Auth/logout: no error message when offline | 🐞 | Minor | Medium | Both |
| #93 | Nested screens: UI ignores safe area on iPhone 14 Pro landscape (Dynamic Island overlap) | 🐞 | Minor | Medium | iOS |
| #94 | Privacy: incorrect error message on wrong current password | 🐞 | Minor | Medium | Both |
| #95 | "Suggest an idea": incorrect error message when submitting an empty field | 🐞 | Minor | Low | Both |

### Notifications & Push

| ID | Title | Type | Severity | Priority | Platform |
|---|---|---|---|---|---|
| #23 | In-app notifications are not displayed | 🐞 | Major | High | Both |
| #25 | Opening a push does not navigate to the message/notification | 🐞 | Major | Medium | Both |
| #34 | No system push-permission prompt on first launch | 🐞 | Major | High | Both |
| #86 | Push notifications not shown while using the app | 🐞 | Major | Medium | Both |

### Cross-cutting (platform / rendering)

| ID | Title | Type | Severity | Priority | Platform |
|---|---|---|---|---|---|
| #69 | Back-stack loss when pressing the system Back button | 🐞 | Major | Medium | Android |
| #70 | Rendering glitches from accumulating gralloc4 errors; unstable FPS | 🐞 | Major | Medium | Android |
| #85 | No pull-to-refresh anywhere in the app | 💡 | — | — | Both |

### Improvements (not defects)

| ID | Title |
|---|---|
| #16 | Limit functionality / guide unauthenticated users through the flow |
| #63 | Quick toggles for extra trip attributes at creation |
| #74 | Gender-based filtering for safety |
| #75, #87, #98 | Misc. enhancement suggestions (trip / registration / profile) |
| #101 | Verify a valid driving licence |
| #102 | Validate car documents and appearance |

## Counts

| | Count |
|---|---|
| Total items filed | 85 (one file each) |
| Defects (🐞) | 74 |
| Improvements (💡) | 11 |
| Critical severity | #19, #58, #61, #79 (plus high-priority booking/data blockers) |
| Largest cluster | input validation on city fields (#35–#56) |
