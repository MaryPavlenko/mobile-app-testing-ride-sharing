# Mobile App Testing [HamSafar]
[![Platform](https://img.shields.io/badge/platform-iOS%20%7C%20Android-informational)]()
[![Artifacts](https://img.shields.io/badge/artifacts-checklists%20%7C%20test%20cases%20%7C%20bug%20reports-orange)]()
[![Tools](https://img.shields.io/badge/tools-TestFlight%20%7C%20Taiga-lightgrey)]()
[![Defects](https://img.shields.io/badge/defects%20reported-74-red)]()

## Overview

End-to-end manual testing of HamSafar, a ride-sharing (carpooling) mobile app for Uzbekistan and Tajikistan, tested in beta on iOS (TestFlight) and Android.

The artifacts connect into one testing workflow:

```
Derived requirements → Checklists & test cases → Bug reports → Evidence → Traceability
```
## About the app

HamSafar is a ride-sharing / carpooling app (similar to BlaBlaCar) for intercity trips in Uzbekistan and Tajikistan. A driver publishes a trip between two cities; a passenger searches for it and books a seat.

* Two roles in one account: driver and passenger.
* No in-app payment. The driver sets the price, shown on the trip card, and payment is by personal agreement. There is no payment step, commission, or service fee anywhere in the flow.
* Cities belong to Uzbekistan and Tajikistan. Interface language is Russian, with no language switch in the MVP.
* Communication is through an in-app chat with a call button. There is no VoIP and no number masking.
* Rating is based only on post-trip reviews, prompted by a banner in the chat after a completed trip.

A full reconstruction of the app logic is in [requirements-docs/app-overview.md](requirements-docs/app-overview.md).

## My role

Manual QA on a distributed team, testing iOS builds through TestFlight and Android beta builds, with the project tracked in Taiga. I reconstructed the requirements, wrote the checklists and test cases, ran exploratory sessions, and reported defects.

Most testers had access only to the TestFlight build, with no admin panel, API, or database. This shaped what could be tested and is documented in the [test strategy](test-design/test-strategy.md).

## What's Inside

* [requirements-docs/](https://github.com/MaryPavlenko/mobile-app-testing-hamsafar/tree/main/requirements-docs) — reconstructed app logic, requirements derived from team communication, open questions, and the improvements backlog.
* [test-design/](https://github.com/MaryPavlenko/mobile-app-testing-hamsafar/tree/main/test-design) — test strategy (scope, approach, environments, access constraints) and the traceability matrix.
* [checklists/](https://github.com/MaryPavlenko/mobile-app-testing-hamsafar/tree/main/checklists) — 10 module checklists with positive and negative scenarios.
* [test-cases/](https://github.com/MaryPavlenko/mobile-app-testing-hamsafar/tree/main/test-cases) — detailed test cases for critical paths, including boundary and negative cases.
* [bug-reports/](https://github.com/MaryPavlenko/mobile-app-testing-hamsafar/tree/main/bug-reports) — defect reports organized by module, with a triaged index and a report template.
* [exploratory-testing/](https://github.com/MaryPavlenko/mobile-app-testing-hamsafar/tree/main/exploratory-testing) — session-based testing charters and findings.
* [smoke-testing/](https://github.com/MaryPavlenko/mobile-app-testing-hamsafar/tree/main/smoke-test-suite.md) — smoke suite run after each build.
* [regression-testing/](https://github.com/MaryPavlenko/mobile-app-testing-hamsafar/tree/main/regression-suite.md) — targeted regression suite tied to fixed defects.
* [push-notifications/](https://github.com/MaryPavlenko/mobile-app-testing-hamsafar/tree/main/push-notifications) — push notification test notes and access limitations.
* [device-testing/](https://github.com/MaryPavlenko/mobile-app-testing-hamsafar/tree/main/device-coverage-matrix.md) — real-device coverage matrix for iOS and Android.
* [testflight/](https://github.com/MaryPavlenko/mobile-app-testing-hamsafar/tree/main/testflight-notes.md) — TestFlight setup, build tracking, and log capture.
* [screenshots/](https://github.com/MaryPavlenko/mobile-app-testing-hamsafar/tree/main/screenshots) — screenshots and the [bug-to-screenshot map](https://github.com/MaryPavlenko/mobile-app-testing-hamsafar/blob/main/screenshots/evidence.md).

## Tools

TestFlight, Taiga, Android developer tools (bug report / logcat), DBeaver / PostgreSQL for database checks, VPN and slow-network conditions. Techniques: checklist-based testing, session-based exploratory testing, equivalence partitioning, boundary value analysis, negative testing, smoke and regression.

## Author

Created by [Mary Pavlenko](https://www.linkedin.com/in/mary-pavlenko/) to document end-to-end mobile testing of a real app, from requirement reconstruction to defect reporting.
