# SwiftUI Patterns

Use this reference for implementation decisions in SwiftUI codebases.

Primary source:
- SwiftUI overview: https://developer.apple.com/xcode/swiftui/

## Default Bias

Use SwiftUI for new Apple-platform UI unless the codebase is firmly built around UIKit or AppKit, or the requirement depends on lower-level APIs SwiftUI cannot reasonably satisfy.

## Composition Rules

- Keep views small and composable, but do not split them so aggressively that layout logic becomes unreadable.
- Extract subviews around real semantic boundaries: toolbar region, empty state, inspector section, form row, status badge, or reusable card.
- Prefer many small focused view files over one giant screen file when the split improves scanability.
- Reusable subviews should be extracted eagerly enough that duplication and oversized bodies do not accumulate.
- A helper view can stay private in the same file when it is tightly coupled to one parent view and has no broader reuse value.
- Prefer the smallest set of modifiers and state needed to express the intended UI clearly.
- Prefer a custom view modifier when the same styling or presentation treatment repeats across multiple views or files.
- Prefer value-driven view composition over imperative mutation.
- Avoid opaque “style helper” layers unless they clearly reduce duplication.

## State Ownership

- Keep ephemeral UI state local to the view when possible.
- Push shared app state upward to a clear owner rather than threading bindings through many unrelated layers.
- Separate derived presentation state from long-lived domain state when that keeps the view easier to reason about.
- Avoid one oversized observable object driving an entire screen when local state would suffice.

## Dependency Injection

- Prefer environment-based injection for view models and other UI-facing dependencies in SwiftUI.
- Avoid turning every SwiftUI view initializer into a dependency plumbing surface.
- Keep initializer injection for focused child-view data and clearly local configuration, not app-wide dependency wiring.

## Containers And Navigation

- Prefer native containers: `NavigationStack`, `NavigationSplitView`, `TabView`, lists, forms, inspectors, sheets, and popovers.
- Use a split view on macOS or iPadOS when the task naturally benefits from persistent navigation context.
- Use sheets for focused temporary tasks, not as a default navigation substitute.
- Prefer toolbars and menus for secondary actions over crowding the main content region.

## Layout

- Start with stacks, grids, lists, forms, and system spacing before reaching for custom layout code.
- Use a custom `Layout` only when the interface has a recurring geometry problem that standard containers handle poorly.
- Avoid hard-coded sizes unless the design truly depends on them.
- Remove redundant or compensating modifiers when they are cancelling each other out or masking a simpler structural fix.
- Test for large text, localization growth, and window resizing early.

## Visual States

- Make loading, empty, error, partial, selected, hovered, focused, and disabled states concrete.
- Design empty states with action and orientation, not just decoration.
- Keep placeholder content visually related to the eventual content to reduce jarring transitions.

## Previews

- Add previews for meaningful permutations: populated, empty, loading, error, selected, hovered, and dark/light appearance where relevant.
- Prefer stable preview fixtures over ad hoc inline mock state when a component will evolve.
- If previews are absent but the project supports snapshot testing, use snapshots to cover the same state space.

## Anti-Patterns

- Massive views with layout, state orchestration, and business logic all mixed together.
- Giant single files full of nested layout sections that should be separate views.
- Reimplementing system containers without a concrete product reason.
- Fixed frames used to “solve” layout issues caused by missing hierarchy.
- Overusing preference keys, geometry readers, or custom alignment hacks when simpler structure would work.
