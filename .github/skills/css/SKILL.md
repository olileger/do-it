---
name: css
description: Design, fix, or review CSS for a responsive, accessible, consistent, and maintainable web interface.
---

# CSS

Apply these instructions whenever a task affects layout, theming, visual states, viewport adaptation, or animation.

## Principles

- Prioritize the existing design system, variables, scales, and conventions.
- Use the cascade, inheritance, and specificity predictably.
- Prefer short, stable selectors tied to component responsibilities rather than document position.
- Design components for their available space rather than for an arbitrary list of devices.
- Use units and functions suited to fluid typography, spacing, and dimensions.
- Preserve readability when zoomed, when text is enlarged, and in narrow viewports.
- Define visible states for hover, focus, activation, selection, disabled controls, and errors.
- Verify contrast for text, informative icons, meaningful borders, and focus indicators.
- Respect reduced-motion preferences and avoid making motion essential to understanding.
- Limit global styles to genuinely shared foundations.

## Architecture and Maintenance

- Reuse existing tokens before adding a literal value.
- Keep styles close to their area of responsibility, following the project's organization.
- Avoid duplication; extract a shared rule only when it represents a stable concept.
- Briefly document non-obvious cascade or compatibility exceptions.
- Remove styles only when their lack of use has been demonstrated.

## Performance

- Avoid unnecessarily complex selectors and expensive layout changes during interactions.
- Prefer animating properties that do not trigger layout recalculation.
- Reserve `will-change` for measured and temporary cases.
- Size media to minimize layout shifts during loading.

## Avoid

- Using `!important` as a routine specificity fix.
- Fixed dimensions that truncate content or prevent enlargement.
- Removing a focus indicator without an equivalent or better replacement.
- Relying on color alone to convey information.
- Repeated magic values unrelated to the visual system.
- Adding responsive breakpoints without observing the actual content.

## Verification

- Check narrow, intermediate, and wide viewport sizes.
- Verify zoom, enlarged text, and long or translated content.
- Test interactive states and supported user preferences.
- Look for overflow, layout shifts, and undersized click or touch targets.
- Run the available formatting, analysis, and visual regression tools.
