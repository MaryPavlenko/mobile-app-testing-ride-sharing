# Push Notifications — Test Notes

## What was verifiable through the UI
- First-launch system permission prompt for push (expected; **missing** → BUG-034).
- Receiving a single notification.
- In-app notification counter: display, increment, reset after viewing.
- Tap-through from a push to the relevant message/notification (**broken** → BUG-025).
- Push to the other party on trip/request cancellation (REQ-NOTIF-01).

## Defects found
| ID | Issue |
|---|---|
| BUG-023 | In-app notifications not displayed |
| BUG-025 | Opening a push does not navigate to the message/notification |
| BUG-034 | No system push-permission prompt on first launch |
| BUG-086 | Push not shown while the app is in use |
| BUG-100 | No permission prompt on the first chat attachment |

## Access limitation (stated explicitly)
- The **"99+" high-volume counter** (REQ-NOTIF-03) could **not** be exercised: mass-generating notifications needed admin/DB/API access that most testers did not have. This was logged as a limited/theoretical check rather than asserted — see [open questions #15](../docs/open-questions.md) and the [test strategy](../test-design/test-strategy.md).
