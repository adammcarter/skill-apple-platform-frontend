# Decision Rules

Use this reference for the hard judgment calls in Apple-platform UI work.

## SwiftUI Or Interop

- Prefer SwiftUI by default for new UI.
- Use AppKit or UIKit interop only when the requirement is materially better served there or the codebase already depends on it heavily.
- Wrap the smallest necessary platform surface.

## Custom UI Or Native UI

- Prefer native containers, controls, and patterns first.
- Create custom UI only when the product benefit is real and the result still respects platform expectations, accessibility, and input behavior.

## Protocols Or Concrete Types

- Prefer concrete types in view code.
- Introduce protocols only when they create a real UI seam for substitution, previews, testing, or shared behavior.
- Avoid abstraction that makes state ownership harder to follow.

## Previews Or Snapshots

- Use previews for fast iteration and state exploration.
- Use snapshots when visual output needs durable regression protection.
- Update both when the project relies on both and the change materially affects visual behavior.

## Add A New Primitive Or Stay Local

- Keep implementation local until repetition or shared behavior clearly emerges.
- Extract a reusable primitive when the same UI pattern appears enough times that inconsistency or repeated work becomes a cost.
