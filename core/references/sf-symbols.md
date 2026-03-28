# SF Symbols Notes

Use this reference when choosing icons or reviewing iconography in Apple-platform UI.

Primary source:
- SF Symbols overview: https://developer.apple.com/sf-symbols/

## Default Rule

Prefer SF Symbols for standard actions, objects, navigation affordances, status indicators, and utility controls. Reach for custom assets only when the product needs a distinct brand illustration or no suitable symbol exists.

## When SF Symbols Are The Right Choice

- Toolbar items, sidebar rows, menus, toggles, badges, status chips, inspector controls, and settings screens.
- Well-understood concepts like search, settings, close, add, remove, share, filter, sort, info, warning, download, upload, favorite, and navigation.
- Symbols that should visually harmonize with Apple typography and control chrome.

## When Custom Assets Are Justified

- Brand marks and product-specific illustrations.
- Domain-specific visuals where available SF Symbols are misleading.
- Cases where the UI needs a bespoke pictogram set with a clear product reason and consistent art direction.

## Rendering Guidance

- Match symbol weight and scale to the adjacent text and control prominence.
- Use monochrome for most utility controls unless color carries clear semantic value.
- Use hierarchical rendering to add subtle emphasis without looking noisy.
- Use palette or multicolor sparingly; they are easy to overuse and can weaken consistency in dense UI.
- Prefer consistency in rendering mode within the same control group or surface.

## Sizing Guidance

- Let symbols inherit from text size or control styling where possible.
- Avoid manually scaling symbols until they become optically heavy relative to labels.
- Check symbols at compact sizes on macOS toolbars and sidebars where visual density matters more.

## Usage Pitfalls

- Do not mix unrelated visual styles across symbols in the same region.
- Do not use custom icons for standard actions just to feel different.
- Do not pair a vague symbol with ambiguous copy and expect the combination to explain itself.
- Do not rely on color-only symbol changes for state communication.

## Review Questions

- Is this a standard concept that should use an SF Symbol?
- Does the symbol feel optically balanced with the surrounding text and chrome?
- Is rendering mode restrained and consistent?
- Does the symbol clarify meaning rather than merely decorate?
