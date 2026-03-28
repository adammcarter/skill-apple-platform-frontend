# Frontend Architecture

Use this reference for Apple UI architecture decisions, not for generic app architecture doctrine.

## Core Goal

Choose structure that keeps UI state, interaction, and platform behavior easy to understand and cheap to change.

## State Ownership

- Keep transient state local when it only affects one view or one interaction.
- Elevate state only when multiple surfaces genuinely need to coordinate.
- Keep domain state and presentation state distinct when that improves clarity.
- Use explicit UI state models for loading, error, empty, selection, and editing flows.

## View Models And Presentation Models

- Use a view model when it simplifies the UI boundary, not because every screen needs one.
- Avoid ceremony-heavy MVVM where the view model becomes a pass-through for trivial state.
- Prefer direct, readable state flow over architecture that looks “clean” but hides behavior.
- A small presentation model can be useful when formatting, derived display state, or async orchestration would otherwise overwhelm the view.

## View Decomposition

- Prefer small focused views and small files when that keeps UI structure easy to scan and change.
- Extract reusable subviews around meaningful UI responsibilities rather than leaving one giant body to do everything.
- It is fine for a supporting subview to stay private in the same file when it is only used by that parent view and the file still scans cleanly.
- Move a private helper view into its own file when it becomes reused, grows substantial logic, or deserves standalone previews/tests.
- Prefer custom view modifiers for repeated styling patterns that span multiple views or multiple files.
- Do not keep everything in one file out of habit when the screen has clearly become too large to read comfortably.

## Protocols And Boundaries

- Use protocols where the UI needs substitution, clear seams, or test doubles.
- Do not introduce protocol layers for concrete views and simple models just to appear abstract.
- If a protocol makes a SwiftUI feature harder to compose or preview, it is probably the wrong abstraction.

## Dependency Injection

- Keep dependency injection lightweight in UI code.
- For SwiftUI-facing code, prefer environment-based injection for view models and other UI-facing dependencies.
- Prefer initializer injection below the UI boundary, and avoid stuffing view initializers with app-level dependency wiring.
- Prefer simple initializer injection or environment-based dependencies over indirection-heavy containers.
- Optimize for previewability and readability.

## Async UI

- Treat async operations as part of the UI design.
- Model loading, retry, success, failure, and cancellation visibly.
- Keep task ownership clear so the screen reacts predictably to lifecycle changes.

## Modularization

- Extract a feature or component when it improves ownership and reuse.
- A top-level `Views/` folder can contain subfolders when a feature grows beyond a flat list of view files.
- Group subfolders by meaningful UI areas such as `Screens/`, `Components/`, `Sections/`, `Rows/`, or platform-specific surfaces when that improves navigation.
- Do not split code into modules so aggressively that common UI changes become expensive.
- Shared UI primitives should emerge from repeated need, not speculation.
