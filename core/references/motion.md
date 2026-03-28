# Apple Motion Notes

Use this reference when designing or implementing animations and transitions for Apple-platform UI.

## Core Rule

Motion should explain interface behavior. It should help the user perceive change, continuity, hierarchy, and focus.

## Good Uses Of Motion

- Showing that one element expanded from or collapsed back into another.
- Explaining insertion, removal, reordering, filtering, or navigation.
- Reinforcing direct manipulation so the interface feels responsive to touch, pointer, keyboard, crown, or gaze.
- Guiding attention toward a changed region without overwhelming the rest of the screen.

## Weak Uses Of Motion

- Animation that exists only to make the UI feel flashy.
- Large transitions on common repeated actions that slow the workflow down.
- Unrelated movement across multiple layers that makes state changes harder to parse.
- Motion that competes with content readability or induces discomfort.

## Implementation Guidance

- Prefer a small number of consistent transition patterns across the product.
- Match animation style to the event: subtle for local state, clearer for navigation or structural change.
- Use interruption-friendly animations for interactive controls.
- Keep animation timing short enough to preserve momentum.
- Respect Reduce Motion and keep the fallback communicative, not inert.

## Review Questions

- Does the motion explain what changed?
- Does it improve orientation or focus?
- Would removing it make the interface harder to understand?
- Is it comfortable and appropriately restrained for the platform?
