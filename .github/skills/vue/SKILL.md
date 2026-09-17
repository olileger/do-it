---
name: vue
description: Build, fix, or review simple and maintainable Vue 3 single-page interfaces using native framework patterns.
---

# Vue

Apply these instructions whenever a task affects Vue components, reactivity, routing, component communication, or application state.

## Default Approach

- Use Vue 3 and Single-File Components.
- Prefer the Composition API with `<script setup>` for new components.
- Keep templates declarative and move non-trivial behavior into the script section.
- Keep component styles scoped when they are not intentionally global.
- Split components by coherent user-interface responsibility, not by arbitrary size.
- Prefer built-in Vue capabilities before adding a dependency.

## Components and Reactivity

- Define props and emitted events explicitly and keep their contracts typed.
- Treat props as read-only and communicate changes through events or shared state.
- Use `ref` for individual reactive values and `reactive` for cohesive objects.
- Use `computed` for derived state; do not duplicate values that can be derived.
- Use watchers only for side effects. Do not use a watcher when a computed value is sufficient.
- Keep template expressions simple and free of side effects.
- Provide stable keys based on domain identity when rendering lists.
- Use template refs only when declarative rendering cannot express the requirement.

## State and Data

- Keep state local to a component until multiple independent areas genuinely need it.
- Move reusable stateful behavior into a composable with a clear, focused API.
- Add a state-management library only when shared state complexity justifies it.
- Represent loading, empty, success, error, and stale states explicitly.
- Clean up subscriptions, timers, and external listeners when their owning scope is disposed.

## Routing

- Add a router only when the demo has multiple navigable views.
- Keep route definitions focused and use lazy loading when it provides a meaningful benefit.
- Validate route parameters before using them.
- Preserve browser navigation semantics and provide a useful not-found view.

## Avoid

- Mixing the Options API and Composition API within a new component without a concrete reason.
- Mutating props or relying on implicit parent-child coupling.
- Large components that own unrelated behavior.
- Watchers used to synchronize duplicated state.
- Global state for values used by only one component subtree.
- Installing a component or utility library for a single trivial feature.

## Verification

- Test component behavior through user-visible output and interactions.
- Verify prop, event, slot, and routing contracts.
- Check conditional rendering, list updates, asynchronous states, and component teardown.
- Run the repository's available type checks, component tests, and production build.
