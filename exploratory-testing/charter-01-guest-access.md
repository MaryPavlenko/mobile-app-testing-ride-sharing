# Charter EXP-01 — Guest (unauthenticated) access boundaries

| Field | Value |
|---|---|
| **Mission** | Find places where an unauthenticated user can reach functionality or data that should require login. |
| **Areas** | Profile, privacy & security, search, booking entry points |
| **Time box** | 45 minutes |
| **Build** | v1.0.6 / v1.0.8 (iOS) |
| **Technique** | Session-based exploratory testing; "follow the unauthenticated user" persona |

## Why this charter
Access control is rarely fully specified in an MVP, and the home screen already behaves differently for guests vs. logged-in users (REQ-HOME-01). That difference is a strong hint that other screens may not consistently gate on auth state.

## Notes from the session
- From a guest session, Profile is reachable (expected: it hosts the log-in entry point).
- **Privacy & security settings are reachable and editable without logging in** — they should be authenticated-only. → reported as **BUG-017**.
- Attempting to search while unauthenticated should make the app "complain" and prompt login (REQ-HOME-03); observed a spinning/loading state in places instead — candidate UX issue, raised as an improvement (guest-flow handling, backlog).

## Outcome
- 1 access-control defect (BUG-017).
- 1 improvement candidate (guest onboarding flow).
- Follow-up: a scripted negative checklist for "guest reaches protected screen" was added to the Profile checklist.
