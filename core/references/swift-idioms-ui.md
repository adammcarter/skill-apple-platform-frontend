# Swift Idioms For UI

Use this reference for Swift language choices that improve Apple frontend code.

## Standard Library First

- Prefer standard library collection types, enums, optionals, and result modeling before inventing custom helper types.
- Reach for language features that make UI state more legible rather than more abstract.

## Value Semantics

- Prefer structs for views, lightweight presentation state, and other value-like UI models.
- Keep mutation localized and understandable.
- Avoid reference-heavy UI models unless shared mutable identity is genuinely needed.

## Enums For UI State

- Prefer enums for mutually exclusive UI states such as loading, loaded, failed, empty, editing, or selection mode.
- Use associated values when they clarify state-specific data.
- Avoid scattered booleans that create invalid combinations.

## Protocol-Oriented Design

- Use protocols when they create a real UI seam for substitution, testing, or cross-surface reuse.
- Avoid protocols that erase helpful concrete behavior or make previews awkward.
- Prefer concrete generics or concrete types when the UI benefits from clarity.

## API Shape

- Favor initializers and modifiers that read clearly at the call site.
- Name things around UI meaning: selection badge, inspector section, toolbar action, loading state.
- Prefer small focused helpers over broad utility grab-bags.

## Anti-Patterns

- Type erasure used only to hide straightforward concrete composition.
- Protocols introduced for one implementation with no meaningful UI seam.
- Helper extensions that make state flow harder to search or reason about.
- Clever abstractions that reduce readability in view code.
