---
name: html
description: Design, fix, or review the HTML structure of a web interface with robust semantics and native accessibility.
---

# HTML

Apply these instructions whenever a task affects document structure, rendered content, forms, navigation, or interface accessibility.

## Principles

- Use the native element that matches the intended meaning and behavior before using a generic element.
- Maintain a logical heading hierarchy; never choose a heading level for its appearance.
- Identify the document language and any language changes within the content.
- Associate every form field with an explicit, understandable label.
- Use native validation, input, and autocomplete attributes when they match the requirement.
- Give buttons and links their actual roles: a button triggers an action, while a link navigates to a resource.
- Provide useful alternative text for informative images and an empty alternative for decorative images.
- Structure tables with a caption, headers, and explicit associations when needed.
- Keep reading and tab order consistent with the visual order.
- Add ARIA attributes only when no suitable native semantics exist.

## Interactions and Dynamic Content

- Preserve focus during dynamic updates and move it only when a context change requires it.
- Announce important feedback without unnecessarily interrupting the user.
- Make form errors identifiable, understandable, and associated with the affected fields.
- Ensure hidden areas are not still exposed to assistive technologies.
- For a dialog, manage its accessible name, initial focus, focus containment, and focus restoration when it closes.

## Avoid

- Interaction handlers on non-interactive elements without full keyboard support.
- Positive `tabindex` values.
- Redundant, invalid, or behaviorally contradictory ARIA attributes.
- Duplicate identifiers.
- Invalid structures or nested interactive elements.
- Essential content injected solely through an inaccessible or non-indexable mechanism without justification.

## Verification

- Validate the document structure and check for markup errors.
- Navigate the interface using the keyboard only.
- Verify the exposed name, role, state, and value of every control.
- Check form journeys, including errors and confirmation.
- Run the repository's available accessibility tests, without treating their success as sufficient on its own.
