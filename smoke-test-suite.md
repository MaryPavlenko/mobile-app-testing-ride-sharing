# Smoke Test Suite

Run after **every** new build, on a clean device, before any deeper testing. If any step fails, the build is rejected for further checklist work and the blocker is reported immediately.

| # | Step | Expected result | Pass criteria |
|---|---|---|---|
| 1 | Install the fresh build | App installs and launches without crash | Launches to home |
| 2 | Log in with an existing account | Reaches the home screen | Authenticated, name in greeting |
| 3 | Search Dushanbe → Khujand | Results list (or an empty-catalogue state) | No spinner hang, no crash |
| 4 | Open "My Trips" | Requests / Active / Archive visible | Tabs load |
| 5 | Open a chat → send a message | Message sends and persists | Message visible after re-entry |
| 6 | Open Profile → log out → log back in | Clean logout and re-login | Session restored |
| 7 | Receive a test push | Push arrives; in-app behaviour correct when app is open | Notification handled |

## Notes
- Step 5 has a known related defect (BUG-022: message disappears on chat re-entry) — watch for regression.
- Step 7's behaviour while the app is open is itself defective on some builds (BUG-086); smoke confirms whether a fix landed.
- The suite is intentionally short (~7 steps) so it can be run on multiple devices quickly at the start of each test round.
