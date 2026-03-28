# Interaction Models

Use this reference when the quality of the UI depends on input behavior: keyboard, focus, pointer, hover, gestures, drag and drop, remote input, or spatial interaction.

## Core Rule

Design for the real interaction model of the platform instead of assuming every screen is finger-first mobile UI.

## Keyboard And Focus

- On macOS and iPad where keyboard use is plausible, make primary flows navigable without touch or pointer dependency.
- Focus order should feel intentional, stable, and unsurprising.
- Keyboard shortcuts should accelerate common actions, not duplicate obscure ones only engineers remember.
- Visible focus treatment matters; do not rely on invisible focus state.
- If editing flows depend on a focused field or selection, make that state explicit in the UI.

## Pointer, Hover, And Selection

- macOS and iPad pointer experiences should reward precision with hover feedback, richer selection affordances, and contextual actions where appropriate.
- Hover should clarify what is interactive; it should not be the only way to discover it.
- Selection should remain legible when the window deactivates, when multiple panes are visible, or when focus moves elsewhere.
- Do not apply oversized touch-first spacing everywhere on macOS if it destroys scanability.

## Gestures

- Prefer gestures that feel standard for the platform and content type.
- Pair gesture-driven actions with visible affordances or an alternate route.
- Do not stack multiple hidden gestures onto the same element unless the payoff is genuinely strong.
- Reduce gesture cleverness when clarity would improve with a visible control.

## Drag And Drop

- Use drag and drop when the task genuinely benefits from direct manipulation: reordering, assigning, importing, arranging, or cross-pane movement.
- Drop targets should be obvious, stable, and match the user's likely mental model.
- Provide feedback for valid, invalid, active, and completed drop states.
- If drag and drop is optional rather than primary, the non-drag path should still feel first class.

## Motion And Continuity

- Motion should support the interaction model by clarifying source, destination, hierarchy, and state change.
- Avoid theatrical transitions that fight precise work or make target acquisition harder.
- Respect reduced motion preferences and avoid depending on motion alone to explain state.

## Platform-Specific Notes

- tvOS should optimize for focus movement, spatial grouping, and remote-driven discoverability.
- visionOS should avoid disorienting motion, awkward reach assumptions, and interfaces that feel pinned to the user's face.
- watchOS interactions should stay lightweight, immediate, and glanceable.

## Review Questions

- Could a keyboard-heavy or pointer-heavy user complete the main flow efficiently where the platform supports that?
- Are drag, hover, focus, and selection states concrete and readable?
- Are gestures additive and helpful, rather than the only path through the UI?
- Does the interaction model match the device, or does it feel like a port from another Apple platform?
