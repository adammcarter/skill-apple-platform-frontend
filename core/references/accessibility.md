# Apple Accessibility Notes

Use this reference when implementing or reviewing Apple-platform frontend code.

Primary source:
- Apple HIG Accessibility: https://developer.apple.com/design/human-interface-guidelines/accessibility

## Non-Negotiables

- Do not communicate meaning with color alone.
- Maintain sufficient contrast in both light and dark appearances.
- Support assistive technologies through semantic labels, values, roles, and actions.
- Provide alternatives to gesture-only interactions.
- Avoid unnecessary timed dismissal and hard-to-control motion.

## Concrete Apple Guidance To Apply

- Support larger text sizes and avoid fragile fixed-size text layouts.
- Prefer Dynamic Type or equivalent scalable typography behavior where the platform expects it.
- Make controls comfortably tappable or clickable and leave enough spacing between them.
- Ensure keyboard navigation works for core flows where supported.
- Pair audio-only feedback with visual or haptic feedback where appropriate.
- Use simple gestures for common actions and provide visible alternatives for complex interactions.

## Platform Details

- macOS minimum control sizing can be smaller than iOS, but cramped controls still hurt usability; optimize for comfort, not just minimums.
- iOS and watchOS should generally feel comfortable at touch-friendly sizes.
- visionOS should minimize motion intensity, reduce discomfort, and avoid content that feels stuck to the user.

## Review Questions

- Can a VoiceOver user understand and operate this screen?
- Does the UI still work with larger text or increased contrast?
- Are hover, focus, selected, and disabled states visible without relying on color alone?
- Can the user complete the core task without specialized gestures?
