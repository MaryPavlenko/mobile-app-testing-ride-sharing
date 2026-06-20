# IMP-087 — Registration enhancements

| Field | Value |
|---|---|
| **ID** | IMP-087 (Taiga #87) |
| **Module** | Registration |
| **Type** | Improvement (not a defect) |
| **Platform** | Android |
| **Status** | Proposed → [improvements backlog](../../requirements-docs/improvements-backlog.md) |

## Summary
Small registration UX improvements.

## Rationale
Reduce confusion and friction during sign-up.

## Proposed behaviour
- State the confirmation-code validity period in the email that contains the code.
- Fix input focus after the code email: focus stays on "Repeat password", so users type the code into the password field by mistake.
- Optionally deliver the code via push and let the app read it (with OS permission) to autofill.

> Filed as an enhancement, not a defect: it does not contradict any defined MVP behaviour. Kept separate to keep the defect list honest.
