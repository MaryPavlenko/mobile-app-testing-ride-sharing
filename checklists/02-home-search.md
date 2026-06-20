# Checklist #4 — Home & Search

Format: `check → expected result`. **⚠ Found:** links a check to the defect it surfaced.
Related requirements: REQ-HOME-01, REQ-HOME-02, REQ-HOME-04.

## Header
- Guest → greeting "Hello!" with no name.
- Authenticated → "Hello, NAME!".
- Notification bell shown in the top-right corner.
- Tapping the bell → opens the notifications feed.
- Bell shows no counter when there are no notifications.
- Bell shows a badge counter when there are unread notifications.
- Subtitle under the greeting: "Intercity routes without calls or long negotiations".

## Search card ("From", "To", "When")
See checklist [#5 — Trip & request creation](03-trip-and-request-creation.md) for the full field-level checks (the same From/To/date controls are used here).

## Footer (bottom navigation, left → right)
- "Home" (house icon) — highlighted when on this screen.
- "My Trips" (car icon).
- "+" (central).
- "Chat" (chat icon).
- "Profile" (person icon).
- Tapping an icon navigates to the matching section.
