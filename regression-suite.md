# Regression Testing

Regression here is **targeted**, not full re-run: it focuses on the areas most likely to break when known defects are fixed, plus the core journey.

## Trigger
Run when a build claims to fix a reported defect, or before a release.

## Core journey (always re-run)
Register/log in → set role → search (Dushanbe → Khujand) → open trip → book → chat → cancel → review banner after completion.

## Defect-linked regression checks
| Fixed area | Re-check | Watch for |
|---|---|---|
| Field validation (BUG-035–056) | City fields on Home, "Where from/to", "Create request" | Over-correction blocking valid cities |
| Booking send (BUG-019) | Booking with a message on iOS | Keyboard/button layout regressions |
| Rating (BUG-020) | Profile of a no-review user | Placeholder vs. 5★ |
| Trip publish rule (BUG-027) | Publish with/without car data | Draft preserved + blocked-state reason |
| Trip state vs time (BUG-071/096/097) | Past-departure booking, completion sync | Driver/passenger state mismatch |
| Chat (BUG-022/065) | Message persistence; archived-chat send | Message loss, archive leaks |

## Smoke vs regression
Smoke confirms the build is testable at all; regression confirms a specific fix landed without breaking neighbours. Both are run at the start of a build round.
