# Apple Platform Frontend 🍎

Build Apple UI that feels native instead of merely functional.

This skill helps agents implement SwiftUI, AppKit, UIKit, and other Apple-platform interfaces with better platform fit, clearer hierarchy, stronger accessibility, and cleaner verification.

## What it can do

- Turn a rough SwiftUI screen into something that feels at home on macOS, iOS, iPadOS, visionOS, watchOS, or tvOS.
- Pick the right container, navigation model, commands, forms, tables, toolbars, and interaction patterns for the platform.
- Improve layout, spacing, typography, motion, accessibility, previews, and snapshot coverage without adding random visual noise.

## Solves problems like

- A screen works, but it does not feel like a real Mac, iPad, iPhone, visionOS, watchOS, or tvOS experience.
- A feature needs the right container, navigation shape, controls, commands, or interaction model.
- A UI needs polish around spacing, typography, motion, previews, snapshots, or accessibility.

## Good when you want to

- Use it to work out what kind of screen, container, or navigation model you should build before you go too far.
- Use it to explain why a layout feels off, why a control choice feels wrong, or why a screen feels too web-like.
- Use it to refactor a large SwiftUI surface into smaller pieces while keeping previews, snapshots, accessibility, and state flow in good shape.

## Example prompts

- `Use $apple-platform-frontend to explain why this iPad screen feels too web-like and suggest a more native structure.`
- `Use $apple-platform-frontend to build a native-feeling macOS settings screen with the right sidebar, toolbar, and form layout.`
- `Use $apple-platform-frontend to refactor this SwiftUI view into smaller pieces without losing behavior or preview coverage.`
- `Use $apple-platform-frontend to review this screen for hierarchy, spacing, accessibility, and platform-fit regressions.`
- `Use $apple-platform-frontend to improve the motion and transition polish in this onboarding flow without overdoing it.`

## Skill Judge

This skill scored `120/120` using the separate `skill-judge` skill.

<https://github.com/softaworks/agent-toolkit/blob/main/skills/skill-judge/SKILL.md>

## Install

With skills.sh:

```bash
npx skills add adammcarter/skill-apple-platform-frontend
```

For a local Codex install:

```bash
ln -s ~/repos/skill-apple-platform-frontend ~/.codex/skills/apple-platform-frontend
```
