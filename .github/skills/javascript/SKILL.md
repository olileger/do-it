---
name: javascript
description: Design, fix, or review client-side JavaScript behavior with reliable, testable, high-performance, and secure flows.
---

# JavaScript

Apply these instructions whenever a task affects dynamic behavior, events, data, asynchronous calls, or interface state.

## Principles

- Follow the project's configuration, language level, and conventions.
- Favor short functions, explicit responsibilities, and easy-to-follow data flows.
- Use domain-oriented names and avoid ambiguous abbreviations.
- Prefer immutability when mutation makes state or effects difficult to reason about.
- Handle missing values and errors at boundaries rather than scattering defensive checks.
- Validate external data before using it.
- Represent asynchronous states explicitly and prevent stale responses from overwriting newer state.
- Cancel operations and remove listeners when their lifecycle ends.
- Use event delegation only when it genuinely simplifies handling dynamic elements.
- Keep behaviors keyboard-accessible and consistent with document semantics.

## Asynchrony and Errors

- Use `async` and `await` when they improve flow readability.
- Handle errors at the level that can interpret or present them meaningfully.
- Do not catch an error only to ignore it or return a false success.
- Distinguish expected errors, cancellations, and unexpected failures.
- Avoid sequential operations when independent, safe parallel execution is possible.
- Protect user actions against duplicate submissions and race conditions.

## Security

- Never insert an untrusted string as interpreted content.
- Use text and node-creation APIs for external content.
- Do not execute code constructed from strings.
- Never expose secrets in code delivered to the browser.
- Treat URLs, cross-context messages, parameters, and persisted data as untrusted.
- Use explicit comparisons and validation for sensitive decisions.

## Performance

- Measure before optimizing and target the genuinely expensive path.
- Avoid alternating reads and writes that trigger repeated recalculations.
- Limit work performed in high-frequency handlers.
- Load heavy features on demand when a concrete benefit is expected.
- Avoid retaining references that unnecessarily extend the lifetime of objects or nodes.

## Avoid

- Implicit global variables.
- Implicit type coercion in ambiguous conditions or comparisons.
- Arbitrary timeouts used to synchronize behavior.
- Unawaited promises without explicit handling.
- Duplicating derivable state.
- Generic abstractions without concrete use cases.
- Comments that repeat the code instead of explaining a constraint.

## Verification

- Test the happy path, invalid inputs, errors, cancellations, and repeated interactions.
- Verify effect ordering in asynchronous flows and race-condition scenarios.
- Check that no listeners, timers, or requests remain active after teardown.
- Run the available formatting, static analysis, targeted tests, and type checks.
