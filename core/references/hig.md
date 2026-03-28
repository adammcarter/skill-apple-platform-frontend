# Apple HIG Notes

Use this reference when making layout, interaction, or visual design decisions for Apple-platform UI.

Primary source:
- Apple Human Interface Guidelines: https://developer.apple.com/design/human-interface-guidelines/

## Core Principles

- Hierarchy: make important content and actions visually obvious.
- Harmony: interfaces should feel aligned with Apple hardware and system experiences.
- Consistency: use platform conventions so the UI feels familiar across contexts and display sizes.

## Practical Application

- Prefer system patterns for navigation, search, toolbars, menus, sheets, inspectors, and settings.
- Avoid bespoke controls when system components already solve the interaction well.
- Use visual treatment to support comprehension, not to show off.
- Respect each platform's input model and density expectations.
- Make resizing, split-view changes, and text scaling part of the design, not an afterthought.

## Platform Biases

- macOS: keyboard-first, pointer-precise, denser information, richer menus, resizable windows.
- iOS/iPadOS: touch ergonomics, clear primary actions, strong safe-area discipline, predictable navigation.
- visionOS: comfort, depth discipline, stable placement, minimal visual overload.
- watchOS/tvOS: focus on glanceability and the dominant input mechanism.

## Decision Rule

When choosing between a custom pattern and a native one, prefer the native one unless the custom approach creates a clear product advantage without sacrificing accessibility, clarity, or platform familiarity.
