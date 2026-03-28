# Controls And Commands

Use this reference when shaping concrete UI surfaces such as forms, lists, tables, toolbars, menus, search, inspectors, and commands.

## Core Rule

Prefer standard Apple controls and command surfaces before inventing a custom composite. The UI should feel like it belongs on the platform even before the styling lands.

## Forms And Data Entry

- Use `Form` or clear form-like grouping when the task is structured data entry, settings, or inspection.
- Prefer explicit labels, help text, and inline validation over placeholder-only explanation.
- Keep destructive actions visually separated from primary save or continue actions.
- Model draft, saving, success, validation failure, and conflict states explicitly.
- Avoid hiding critical validation behind disabled buttons with no explanation.

## Lists, Tables, And Collections

- Use `List` for browseable collections, navigation, and standard row affordances.
- Use `Table` on macOS or iPadOS when users need dense comparison, sorting, or multi-column scanning.
- Design rows so selection, hover, drag state, context actions, and empty states are all obvious.
- Prefer built-in swipe, context menu, and selection behavior over reimplementing row actions from scratch.
- If the task is detail-oriented, pair a list or table with detail or inspector context rather than overloading a single row.

## Toolbars, Menus, And Commands

- Put frequent secondary actions in toolbars only when they genuinely support the current surface.
- Use menus or context menus for less-frequent or structurally grouped actions.
- On macOS and iPad with keyboard support, make command discoverability part of the design rather than an afterthought.
- Keep toolbar items purposeful; a crowded toolbar is usually a sign the information architecture is off.
- Prefer command groups that mirror product concepts, not internal implementation seams.

## Search, Filtering, And Sorting

- Use native search presentation where possible.
- Make filtering and sorting visible when they materially affect what the user is looking at.
- Preserve user orientation when search narrows results; do not make the whole screen jump without explanation.
- Empty search results should explain what happened and suggest a useful next step.

## Sheets, Popovers, Inspectors, And Alerts

- Use sheets for focused temporary tasks with a clear finish.
- Use popovers for lightweight contextual work, not for full flows pretending to be lightweight.
- Use inspectors for supporting detail that should stay available without replacing the main content.
- Alerts should be short, concrete, and tied to an actual decision.
- Confirmation dialogs should protect destructive actions, not ordinary navigation.

## Review Questions

- Is each action living in the right surface: primary content, toolbar, menu, context menu, command, inspector, or sheet?
- Would a Mac user and an iPad power user find the information density and command placement sensible?
- Does the form or collection still make sense in loading, empty, error, selected, and editing states?
- Did we reach for a custom control where the standard Apple one would have been clearer?
