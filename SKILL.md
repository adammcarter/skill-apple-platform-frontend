---
name: apple-platform-frontend
description: Use this skill when the task is frontend work for Apple platforms, especially SwiftUI, AppKit, UIKit, visionOS, watchOS, or platform-specific interface design. It specializes in native interaction patterns, visual hierarchy, spacing, typography, motion, accessibility, previews, snapshots, and production-grade implementation details for Apple UI code.
---

# Apple Platform Frontend

This is the canonical Apple frontend skill package for Codex/OpenAI-style agents.

Always load:

- `./core/prompt.md`

Then load only the references that match the task:

If you are implementing or refactoring SwiftUI view structure, state handling, dependency flow, or view decomposition:

- `./core/references/swiftui-patterns.md`
- `./core/references/frontend-architecture.md`

If the task is about platform fit, native container choice, commands, navigation shape, or overall UI structure:

- `./core/references/decision-rules.md`
- `./core/references/hig.md`
- `./core/references/interaction-models.md`
- `./core/references/controls-and-commands.md`

If the task is about visual hierarchy, spacing, typography, color, materials, or visual polish:

- `./core/references/visual-design.md`
- `./core/references/testing-playbook.md`

If accessibility, focus, keyboard access, Dynamic Type, contrast, reduced motion, labels, or assistive technology behavior could change:

- `./core/references/accessibility.md`

If the task depends on lower-level SwiftUI implementation detail or style:

- `./core/references/swift-idioms-ui.md`

If previews or visual verification are part of the change:

- `./core/references/testing-playbook.md`

If the project uses `swift-snapshot-testing-macros`, or the user explicitly mentions that library:

- `./core/references/snapshot-testing-macros.md`

If the task is specifically about iconography or SF Symbol choice:

- `./core/references/sf-symbols.md`

If the task is specifically about motion, animation, or transitions:

- `./core/references/motion.md`

If AppKit or UIKit interop is required:

- `./core/references/appkit-uikit-interop.md`

If labels, empty-state copy, or CTA wording matter:

- `./core/references/microcopy-and-labeling.md`

If the task is specifically for macOS:

- `./core/references/platform-notes/macos.md`

If the task is specifically for iOS or iPadOS:

- `./core/references/platform-notes/ios-ipados.md`

If the task is specifically for visionOS:

- `./core/references/platform-notes/visionos.md`

If the task is specifically for watchOS or tvOS:

- `./core/references/platform-notes/watchos-tvos.md`

If performance, scrolling cost, or large collections are part of the problem:

- `./core/references/performance.md`

If you are reviewing or untangling suspicious UI code:

- `./core/references/anti-patterns.md`
- `./core/references/review-rubric.md`

If the user explicitly asks for concrete code examples:

- `./core/references/example-implementations.md`

If you are blocked or need authoritative follow-up resources for a tricky Apple-platform issue:

- `./core/references/trusted-resources.md`

Do not auto-load implementation docs, example recipes, platform notes, motion guidance, interop notes, performance notes, review docs, or trusted resources unless the task clearly needs them.

Additional OpenAI/Codex-specific behavior:

- Produce code, not just direction, unless the user explicitly asks for strategy only.
- Prefer hierarchy driven by structure, spacing, typography, and restrained emphasis over decorative chrome.
- If the target platform, input model, or verification expectations are unclear, resolve that before polishing.
- Prefer native controls, commands, tables, forms, search, focus behavior, and platform-specific interaction models over generic cross-platform UI patterns.
- When reviewing code, present findings first and prioritize regressions, accessibility failures, platform-fit misses, and state coverage gaps before style comments.
- Use file and line references when the environment supports them.
- Keep close-out summaries brief and verification-oriented so the developer can quickly check the change themselves.
