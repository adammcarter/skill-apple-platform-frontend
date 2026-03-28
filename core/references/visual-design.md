# Visual Design

Use this reference when the task is about visual hierarchy, spacing, typography, color, materials, or polish for Apple-platform UI.

## Core Bias

- Let structure, spacing, and typography do most of the work before reaching for color, materials, borders, or shadows.
- Prefer one obvious primary action or focal point per surface.
- Use ornamentation to reinforce hierarchy, not to create hierarchy from scratch.
- Keep macOS dense but scannable, and keep iPhone/iPad surfaces roomy enough for touch and glanceability.

## Hierarchy

- Establish hierarchy first with grouping, alignment, whitespace, and heading scale.
- Keep supporting metadata quieter than primary content with secondary styling, not smaller hit targets.
- If every card, row, or button is equally loud, the screen has no hierarchy.
- When a surface needs outlines, fills, shadows, badges, and accent color all at once, the structure is probably doing too little.

## Spacing And Type

- Prefer a small number of spacing steps that repeat consistently within a screen.
- Let text wrap and grow; avoid fixed-height containers around live content.
- Prefer fewer text styles with clear roles over many near-identical weights and sizes.
- On macOS, tighten density carefully for scanability; on iOS and iPadOS, leave more room around touch targets and grouped content.

## Color, Materials, And Chrome

- Use accent color sparingly for primary action, selection, or meaningful status.
- Prefer a restrained palette with one dominant accent and a small number of semantic colors.
- Use materials, vibrancy, blurs, and shadows only where they explain layering, depth, or focus.
- Keep SF Symbols weight, scale, and rendering mode aligned with the surrounding text and control chrome.

## Polish Checks

- The first pass should still read clearly in grayscale and with reduced emphasis.
- Hovered, focused, pressed, selected, and disabled states should remain legible without dramatic decoration.
- Empty and loading states should feel intentional rather than like missing content holes.
- If the screen only starts to feel "designed" after adding decoration, revisit layout and hierarchy first.

## Warning Signs

- Every container turned into a card.
- Multiple accent colors competing on the same surface.
- Borders, fills, shadows, and materials stacked on one region.
- Typography styles changing too often without semantic reason.
- Polishing work that makes scanning harder instead of easier.
