# Snapshot Testing Macros

Use this reference when a codebase uses `swift-snapshot-testing-macros` for visual verification.

Primary sources:
- Repository: https://github.com/adammcarter/swift-snapshot-testing-macros
- Introduction discussion: https://github.com/pointfreeco/swift-snapshot-testing/discussions/974

## What This Skill Should Do

- Recognize when the project uses `swift-snapshot-testing-macros`.
- Prefer updating or adding snapshots when a UI change materially affects visual output or state coverage.
- Treat the library as the source of truth for exact syntax, macro options, traits, and workflow details.

## When To Reach For It

Use the library when a change affects:
- layout or hierarchy
- empty/loading/error states
- light and dark appearance
- selection, hover, focus, disabled, or editing states
- toolbars, sidebars, inspectors, sheets, and other Apple-specific surfaces

## Expectations

- Add snapshots for the most meaningful UI states, not every possible permutation.
- Keep snapshot coverage aligned with previews and other visual verification paths.
- Review visual diffs deliberately rather than treating snapshot updates as automatic churn.
- Use snapshots for visual correctness, not as a substitute for logic tests or broad end-to-end interaction coverage.
- Defer implementation specifics to the library documentation inside `swift-snapshot-testing-macros`.
