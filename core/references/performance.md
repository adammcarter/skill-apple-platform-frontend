# Frontend Performance Notes

Use this reference when implementing or reviewing Apple-platform UI for responsiveness.

## Core Goal

Maintain a UI that feels immediate under realistic data, image, and interaction load.

## Practical Rules

- Avoid invalidating large view trees for small local state changes.
- Localize expensive effects, image decoding, and rendering work.
- Prefer lazy containers for long or heavy collections when they materially reduce work.
- Be careful with layered materials, blurs, shadows, and masks in dense or animated regions.
- Keep animations interruptible and short enough that frequent interaction still feels direct.

## SwiftUI Considerations

- Keep derived view state cheap and explicit.
- Avoid piling multiple geometry-driven effects onto scrolling content without a clear payoff.
- Profile before introducing complexity intended to “optimize” prematurely.

## Image And Asset Handling

- Size images appropriately for display context.
- Avoid rendering full-resolution assets where thumbnails or prepared variants suffice.
- Check how imagery behaves in lists, inspectors, zoomable canvases, and transitions.

## Review Questions

- Does this screen still feel responsive with realistic content size?
- Are expensive visuals concentrated in the highest-value areas?
- Will animation and scrolling remain comfortable on lower-end hardware?
