# Checklist #9 — Profile

Covers the **guest** and **registered** profile, account actions, and the **reviews** flow. Format: `check → expected result`. **⚠ Found:** links a check to a defect.
Related requirements: REQ-PROF-01…06.

## Guest
**Display**
- The Profile screen opens with the title "Profile", a "Log in to account" block and its sub-text, menus appropriate to the access level, correct icons, non-truncated menu text, a correct bottom-nav block, and the "Profile" tab highlighted.

**Navigation**
- "Log in to account" opens the auth screen; each available menu item opens; Back returns to the previous screen.

**Access**
- Posting a trip is not available to a guest.
- A guest does not see: log out, delete account, personal data, completed-trip data, or search history. **⚠ Found: BUG-017** (privacy & security reachable by a guest).

**States**
- The screen renders correctly with no internet; load errors are shown correctly.

## Registered user
**Display**
- The Profile screen shows the title, the user icon/photo, the user name, access-appropriate menus, correct icons, non-truncated text, a correct bottom-nav block, and the highlighted "Profile" tab.

**Navigation**
- Each available menu item opens; the user stays logged in after an app restart.

**Functionality**
- "Log out" returns the user to guest mode; the user can post a trip.
- Privacy menu: current privacy settings shown; password change succeeds → user is redirected to login and cannot log in with the old password.
- Edit profile menu: current data shown; changes are saved.
- Account deletion: requires confirmation, deletes the account, clears user data, returns the app to guest state, and blocks login with the old credentials. **⚠ Found: BUG-082** (deletion not yet available).

**Negative**
- Network loss during login / logout / deletion; expired session; state conflict after relogin.

## Reviews
- After a completed trip a passenger can leave 1–5 stars + a comment.
- A "Leave a review" banner appears in the chat with the driver (can be dismissed twice; the third time it is gone for good).
- Reviews appear on the driver's public profile (author name + rating + comment + date).
- A new review overwrites the old one (1 passenger — 1 review per trip).

### Preconditions
- Trip completed; the passenger took part; a chat exists between passenger and driver.

### Review banner in chat
**Display**
- After completion the "Leave a review" banner is shown, **to the passenger only**, for a completed trip; banner text, the "Leave a review" button and the close button render correctly.

**Behaviour**
- First dismiss hides the banner; it reappears after 6 hours and is not shown before the timer expires.
- The 6-hour timer holds correctly across app restart, logout/login, network change, and background/foreground.
- Second dismiss hides it permanently — it does not return after restart, logout/login, screen refresh, or a long time.
- After submitting a review the banner disappears and does not return after logout/login.

**Review form**
- Tapping the banner opens the form; it opens correctly and can be closed without submitting.
- A rating 1–5 can be chosen (single value; re-tap updates it; the chosen value renders correctly).
- A comment can be entered or omitted (rating only); very long comments, special characters/emoji and line breaks are handled without breaking the layout.

**Submission logic**
- A review cannot be submitted without a rating (error shown); a valid review submits with a success message.
- Repeated taps on Submit do not create duplicates; a loading state is shown; network errors are shown and can be retried.
- One passenger → one review per trip; a re-submission overwrites the old review and the new rating/comment replaces the old (stale data not shown).
- A review cannot be left before completion, for someone else's trip, by the driver for themselves, or by a logged-out user.

**Profile display**
- Reviews appear on the driver's public profile showing author name, rating, comment and date, rendered correctly. **⚠ Found: BUG-020** (5-star rating shown for users with no reviews).

## Edit profile / Car (detailed field checks)
- Edit profile: avatar + "Change" control; "Name" (required, max-length, error on invalid). **⚠ Found: BUG-089.**
- Phone field: placeholder when empty; keyboard closes on tap-outside / confirm and does not cover "Save"; entered number not duplicated under the avatar; invalid phone shows an error. **⚠ Found: BUG-026.**
- Date of birth: calendar icon; cannot save age < 18 or today's date. **⚠ Found: BUG-088.**
- Email: placeholder when empty; format validated; cannot save invalid values (test, 12345, test@, test.com). **⚠ Found: BUG-090.** Open question: does changing the profile email change the login email? (**→ IMP-098**)
- "Save" pinned at the bottom, not covering fields; the updated value shows after saving.
- Car: "Make & model", "Colour", "Number" — required, max-length; "Colour" rejects digits-only. **⚠ Found: BUG-091.** Saved car data is used when a driver creates a trip.

## Notifications / Language & theme / Privacy / For passengers / For drivers
- **Notifications** screen: toggles "Messages", "Booking confirmation", "Trip reminders", "Promos & news" each with their description; on/off states are distinct; a toggle change persists across screen exit and app restart; save errors are handled.
- **Language & theme**: current language shown; theme options "Auto / Light / Dark" with the selected one highlighted; theme change applies and persists across restart (dark does not reset to light); all profile screens render correctly in the chosen theme.
- **Privacy & security**: "Public profile" toggle with description and persisted state; "Change password" block with field icons and "Update password"; empty fields, mismatched new/repeat, and a wrong current password each show the correct error. **⚠ Found: BUG-094** (shows "Invalid email or password" on a wrong current password); password rules enforced; success message on change.
- **For passengers / For drivers**: info banners and the numbered steps render in a consistent style, the screen scrolls, and long texts do not truncate or break the layout.
