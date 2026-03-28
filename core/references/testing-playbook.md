# Testing Playbook

Use this reference when validating Apple-platform frontend work.

## Core Goal

Verify that the UI is correct, native-feeling, accessible, and stable across the states most likely to regress.

## Preferred Validation Order

1. Previews or fast local visual feedback
2. Snapshot coverage for meaningful visual states
3. Accessibility checks
4. Focused UI tests for high-value flows when the codebase has them
5. Manual interaction checks for platform-specific behavior
6. Relevant existing unit or feature tests when the codebase has them

## What To Cover

- loading, empty, error, selected, focused, hovered, disabled, and populated states
- light and dark appearance when relevant
- platform-specific surfaces like sidebars, inspectors, sheets, toolbars, and menus
- text growth, window resizing, and layout stress points when applicable

## Snapshot Expectations

- After changing UI code, run the most relevant existing snapshot or unit tests before declaring the work done when the environment supports it.
- Add or update snapshots when the change materially affects visual output.
- Prefer a small set of high-signal states over exhaustive low-value permutations.
- Review snapshot diffs deliberately instead of treating them as automatic churn.
- Treat a failing snapshot as a prompt to investigate whether the code regressed, the snapshot baseline is stale, or the test itself is no longer a valid reference.
- Do not re-record snapshots reflexively just to make the suite green.

## Unit And Feature Test Expectations

- Run the most directly related existing tests after changing UI behavior, view state handling, or supporting logic.
- Prefer targeted test runs over broad suites when that is enough to validate the change efficiently.
- If tests are flaky, stale, or obviously misaligned with the intended UI, note that clearly instead of treating the failure as authoritative truth.
- If no relevant tests exist, say that explicitly and rely on previews, snapshots, and manual verification instead.

## UI Test Expectations

- Use UI tests for high-value user journeys, navigation flows, system integration edges, and regressions that are hard to prove with lower-level tests alone.
- Keep UI tests focused and sparse; do not try to encode every UI state through expensive end-to-end automation.
- Prefer UI tests for workflows where the interaction itself is the behavior under test.
- If a logic or state test would prove the behavior more cheaply, prefer that lower layer.

## Accessibility Expectations

- Ensure semantics, labels, values, and actions remain clear.
- Check reduced motion implications for animated changes.
- Verify keyboard access and focus behavior where the platform expects it.
