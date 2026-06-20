# Checklist #3 — Authorization

Covers registration, log in, password recovery, logout and account deletion. Format: `action → expected result`. **⚠ Found:** notes link a check to the defect it surfaced.

Related requirements: REQ-AUTH-01 … REQ-AUTH-07.

## Registration

### Positive
- Open the app (unauthenticated) → go to Profile → a "Log in to account" button is shown.
- Tap "Log in to account" → the auth form is shown.
- Tap "Register" → the registration form is shown.
- Tap the × in the top-left of the form → the form closes → returns to Profile.
- Enter valid data in all fields and tap "Register" → user is registered; an alert asks to confirm the email, with an input for the code sent to the registered address.
  - ⚠ Found: date of birth cannot be typed from the keyboard — no `/` or `.` separators (BUG-028). Authorization itself also failing on the build at the time.
- Enter the valid confirmation code → code accepted; message "Email confirmed. Welcome, <user name>".

### Negative
- Enter an invalid confirmation code → field borders turn red; message "Invalid confirmation code".
- Leave all fields empty and tap "Register" → field borders turn red; "Required field" under each.
  - ⚠ Found: when the Name field is filled, the error reads "Enter email" (message logic, see BUG-089/#90 cluster).
- Fill all but one required field → that field's border turns red with "Required field".
- Password of 7 characters → "Password too short. Must be 8–16 characters."
- Password of 17 characters → "Password too long. Must be 8–16 characters."
- Invalid email → border red, "Invalid email format".
- Digits in the Name field → border red, "Invalid name format".
  - ⚠ Found: digits are accepted without any validation error (BUG-066).
- Wrong value in "Confirm password" → border red, "Passwords do not match".
- Tap "Register" with no internet (valid data) → alert: no internet; the form stays filled in.
- ⚠ Found: registration succeeds with a hidden space character in the password (BUG-057).

## Log in

### Positive
- Open the app (unauthenticated) → go to Profile → "Log in to account" is shown.
- Tap log in → the auth form is shown.
- Fill valid credentials → user is logged in.

### Negative
- Unregistered email → alert "No user is registered with this email".
- Email without `@` → border red, "Invalid email".
- Wrong password → alert "Incorrect email or password".
- Tap "Log in" with no internet (valid data) → alert: no internet.
- Tap "Log in" on a slow connection → a loading state is shown.

## Password recovery

> ⚠ Found: password recovery is **not implemented** in the build (BUG-067). The checks below define the expected behaviour for when it ships.

### Positive
- Auth form → tap "Forgot password?" → the recovery form opens.
- Enter a registered email → tap "Recover password" → "Recovery instructions sent to your email".
- Follow the email link → the change-password screen opens.
- Enter a valid new password + confirmation → tap "Save" → "Password changed successfully".
- Log in with the new password → success.

### Negative
- Unregistered email → "No user found with this email".
- Invalid email format → border red, "Invalid email format".
- Empty email → border red, "Required field".
- Mismatched new password / confirmation → "Passwords do not match".
- Password not meeting security rules → password-requirements message.
- Expired recovery link → "Link is invalid or has expired".
- "Recover password" with no internet → no-internet message.
- "Save" on a slow connection → loading state.

## Logout

### Positive
- Logged-in user opens Profile and scrolls to the bottom → "Log out" is shown.
- Tap "Log out" → user is logged out and returned to the auth/home screen.
- After logout, chat and My Trips are not accessible.
- Reopening the app keeps the user logged out.

### Negative
- "Log out" with no internet → logout completes correctly if the token is cleared locally; otherwise alert "No internet connection".
- Slow connection during logout → loading state.
- After logout, the system Back button does not restore the authenticated session.

## Account deletion

> ⚠ Found: account deletion is **not yet available** (BUG-082). Checks define expected behaviour.

### Positive
- Logged-in user opens Profile, scrolls to the bottom → "Delete account" is shown.
- Tap "Delete account" → a confirmation alert appears (ideally with a reason survey).
- Confirm deletion → account deleted, user logged out.
- After deletion, logging in with the old credentials is impossible.
- After deletion, re-registering with the same email works per business rules.

### Negative
- Cancel deletion → account stays active.
- "Delete account" with no internet → no-internet message.
- Server error during deletion → a correct error message.
- A repeated tap on delete does not trigger multiple deletions.
- After deletion, the user's protected data is removed from the app.
- Opening the app on an old session after deletion → user is redirected to the auth screen.
