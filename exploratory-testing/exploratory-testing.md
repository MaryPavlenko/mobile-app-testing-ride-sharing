# Exploratory Testing

Session-based, time-boxed exploration used alongside the scripted checklists. Each **charter** states a mission, an area, and a time box; findings and any defects are logged after the session.

This is where a UX-research background pays off directly: structured curiosity about *how a real user breaks a flow* surfaced several of the higher-value defects (time-based trip states, multi-device login, archive/chat edge cases) that a pure happy-path script would miss.

| Charter | Mission | Outcome |
|---|---|---|
| [EXP-01](charter-01-guest-access.md) | Probe what an unauthenticated user can reach and do | Access-control gaps (BUG-017) |
| EXP-02 | Probe trip state vs. real time (past departure, auto-complete) | BUG-071, BUG-096, BUG-097 |
| EXP-03 | Probe multi-device login and session behaviour | Security weak spot confirmed (backlog) |
