# Test Strategy

## Objective

Validate the HamSafar MVP against reconstructed requirements, find and report defects with reproducible evidence, and make the limits of testability explicit given the access available.

## Scope

**In scope:** functional testing of the 10 product modules (auth/registration, home & search, trip creation, trip details & booking, my trips, chat, profile, push notifications, notifications feed, plus a cross-module smoke suite); negative testing of input fields; UI/usability observations; basic interrupt/network-condition checks.

**Out of scope (MVP):** performance/load testing, security penetration testing, payment flows (no in-app payment exists), localisation beyond Russian, and any behaviour listed as undefined in [open questions](../docs/open-questions.md).

## Approach

- **Checklist-based testing** per module (positive and negative paths) — see [`checklists/`](../checklists/).
- **Session-based exploratory testing** with time-boxed charters — see [`exploratory-testing/`](../exploratory-testing/).
- **Smoke** after every new build, **regression** around fixed defects.
- Test-design techniques applied to input fields: **equivalence partitioning**, **boundary value analysis** (e.g. password length 8–16, price cap at 1000, age ≥ 18), and **negative testing** (digits/special characters/non-existent cities in city fields).

## Environments

- **iOS:** beta builds delivered via **TestFlight**.
- **Android:** beta builds (sideloaded), with developer-options bug reports / logcat for logs.
- Multiple **real devices** across OS versions and form factors — see [`device-testing/`](../device-testing/).

## Access constraints (and how they shaped testing)

Most testers had **only the TestFlight build** — no admin panel, no API, and (for most) no database access. Consequences, made explicit rather than hidden:

- **"99+" notification counter** could not be exercised: no way to mass-generate notifications through the UI. Marked as a limited/theoretical check.
- **Server-side and data-integrity checks** were possible only where DB access (DBeaver/PostgreSQL) was available, and are noted as such on the relevant items.
- Where behaviour could not be confirmed, it was logged as an open question, not asserted.

Being precise about what *cannot* be tested under current access is part of a credible strategy.

## Risk-based focus

Highest attention went to the core revenue/trust path and known weak spots:

1. **Create trip → search → book → cancel** (the primary user journey).
2. **Input validation** on city, price, password, profile and date-of-birth fields (large defect cluster found here).
3. **Auth state & access control** (guest access to protected screens).
4. **Rating/reviews correctness** (known default-5-stars issue).
5. **Multi-device login** (flagged security weak spot).

## Entry / exit (per build)

- **Entry:** build installs and launches; smoke suite available; checklists assigned.
- **Exit:** smoke passes; assigned checklists executed; new defects reported with steps + environment + evidence; regression run on items tied to fixed defects.

## Defect workflow

Reported in Taiga as Issues; enhancement ideas routed to the [improvements backlog](../docs/improvements-backlog.md) instead of the defect list. Each report carries preconditions, steps, actual vs expected, environment, and (where useful) severity/priority — see the [bug-report template](../bug-reports/_TEMPLATE.md).
