# Traceability Matrix

Links requirements → checklists → defects, so coverage is visible and every defect traces back to a requirement (or to an explicit open question / improvement).

| Requirement | Checklist | Defects | Coverage |
|---|---|---|---|
| REQ-AUTH-02/03 (registration + email confirm) | #3 Authorization | BUG-028, 057, 066, 089/090 | ✅ |
| REQ-AUTH-07 (password recovery) | #3 Authorization | BUG-067 (missing) | ✅ (gap) |
| REQ-HOME-01 (greeting + name) | #4 Home & search | — | ✅ |
| REQ-HOME-02/04 (city + required-field validation) | #4, #5 | BUG-035–056, 062 | ✅ |
| REQ-HOME-03 (unauth search must prompt login) | #4; EXP-01 | improvement (guest flow) | ✅ |
| REQ-TRIP-01 (no car data → no publish) | #5 Trip creation | BUG-027 | ✅ |
| REQ-TRIP-03 (published trip not editable) | #5, #7 | BUG-014 | ✅ |
| REQ-TRIP-04 (origin ≠ destination) | #5 | BUG-076 | ✅ |
| REQ-BOOK-03 (passenger cancels, push to other party) | #6, #7 | BUG-058, 061 | ✅ |
| REQ-BOOK-04 (no booking after departure) | #6; EXP-02 | BUG-071 | ✅ |
| REQ-MYTRIPS-02 (counts match) | #7, #9 | BUG-021 | ✅ |
| REQ-CHAT-01 (chat + call button after booking) | #8 | BUG-022, 065, 077 | ✅ |
| REQ-PROF-01 (privacy auth-only) | #9; EXP-01 | BUG-017 | ✅ |
| REQ-PROF-03 (no-review rating) | #9 | BUG-020 | ✅ |
| REQ-PROF-06 (age ≥ 18, field validation) | #9 | BUG-079, 088, 089, 090, 091 | ✅ |
| REQ-NOTIF-01 (cancel → push) | #10, #11 | BUG-023, 025, 034, 086 | ✅ |
| REQ-NOTIF-03 ("99+") | #10 | not testable (open #15) | ⚠ blocked by access |
