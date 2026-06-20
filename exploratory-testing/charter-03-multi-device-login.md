# Charter EXP-03 — Multi-device login & session behaviour

| Field | Value |
|---|---|
| **Mission** | Understand how sessions behave across devices for one account, and probe the security exposure. |
| **Areas** | Authentication, active sessions, data sync |
| **Time box** | 45 minutes |
| **Build** | v1.0.8 (two devices signed into the same account; cross-checked against the database where access was available) |
| **Technique** | Session-based exploratory testing; a "second device" persona |

## Why this charter
The team confirmed that multi-device login keeps the previous device logged in, carries all data over, and (currently) applies no security checks — see [app overview §10](../docs/app-overview.md). Confirmed-but-risky behaviour like this is exactly where exploratory testing earns its place: the job is to map the blast radius, not just to re-state the rule.

## Notes from the session
- Logging in on device #2 does **not** log device #1 out; both stay authenticated. (REQ-AUTH-06)
- Profile, trips, requests, chats and history all sync to device #2.
- No new-device login notification is sent; no active-session list is visible; no device limit was observed.
- Re-login on another device preserves data and does not force a logout — internally consistent, but a clear security weak spot.

## Outcome
- **No functional defect** — the behaviour matches the current (intended) MVP design, so this is filed as a security finding, not a bug. Honest classification matters: calling expected behaviour a "bug" would mislead the team.
- Raised backlog items: new-device login alert, active-session list, remote sign-out, device limit, and a password-change warning on suspicious login — see the [improvements backlog](../docs/improvements-backlog.md).
