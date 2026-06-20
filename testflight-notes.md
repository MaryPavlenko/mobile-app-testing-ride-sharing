# TestFlight — Setup, Builds & Logs

## Access model
- iOS beta builds were distributed through **TestFlight**; testers were invited by email and joined via the TestFlight app.
- No new Apple ID is required to join a TestFlight beta — an existing Apple ID with two-factor authentication and an accepted invite is enough. (Several onboarding hiccups on the team came from Apple ID / email mismatches; documented so the next tester avoids them.)
- Most testers had **only** the TestFlight build — no admin panel, API or database — which is reflected in the [test strategy](../test-design/test-strategy.md) and in which checks were marked "not testable under current access".

## Build tracking
- Multiple builds were tested in sequence (v1.0.6, v1.0.8 on iOS). Several defects (e.g. BUG-019) were confirmed across more than one build, which raised their priority.
- A separate tracking checklist recorded **who installed which build/version on which device**, so coverage gaps were visible at a glance.

## What "done per build" meant
- Smoke suite green → assigned checklists executed → new defects filed with steps + environment + evidence → regression on items tied to fixed defects.
