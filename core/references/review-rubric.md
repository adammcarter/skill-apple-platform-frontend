# Review Rubric

Use this reference when reviewing Apple-platform frontend code.

## Review Output Shape

- Findings first.
- Lead with regressions in platform fit, interaction clarity, accessibility, missing state coverage, or obviously risky performance choices.
- If no issues stand out, say which axes were checked so the review still feels deliberate.

## Immediate Failure Signals

- Cross-platform UI transplanted onto Apple platforms without adapting navigation, density, or controls.
- Primary actions hidden, ambiguous, or competing with secondary decoration.
- Meaning expressed through color alone or accessibility semantics left implicit.
- Loading, empty, error, or destructive states missing from a changed surface.
- Expensive visual effects added to dense, scrolling, or frequently animating regions without clear payoff.

## Order Of Evaluation

1. Platform fit
2. Visual hierarchy and interaction quality
3. Accessibility
4. State coverage
5. Code structure
6. Performance
7. Verification coverage

## Platform Fit

- Does the UI use native navigation, windowing, toolbars, menus, and sheet behavior?
- Does the density and interaction model fit the target platform?
- Are custom controls justified or merely decorative reinventions?

## Visual Hierarchy And Interaction Quality

- Is there one clear focal point or primary action per surface?
- Are spacing, typography, and emphasis doing most of the hierarchy work instead of stacked decoration?
- Would the screen still read clearly if color and materials were toned down?
- Are primary and secondary actions obvious?
- Do hover, focus, pressed, selected, and disabled states read clearly?
- Does motion explain change and preserve orientation?

## Accessibility

- Are semantics, labels, values, and actions exposed clearly?
- Does the screen work with larger text, contrast needs, keyboard access, and assistive technologies?
- Is meaning communicated through more than color?

## State Coverage

- Are loading, empty, error, and partial-content states implemented?
- Are destructive or irreversible actions signposted appropriately?
- Are transitions between states understandable?

## Code Structure

- Is state ownership clear?
- Are views decomposed along meaningful boundaries?
- Is interop used only where justified?

## Performance

- Will the screen remain responsive with realistic content sizes?
- Are images, expensive effects, and animations used responsibly?
- Is rendering work localized, or does small state change invalidate too much?

## Verification

- Are previews, snapshot tests, or equivalent visual checks present for meaningful states?
- Is there enough coverage to catch visual regressions in the changed area?

## Escalate When

- The issue is systemic across the whole surface rather than a local tweak.
- The UI now looks more polished but less native, less accessible, or harder to scan.
- Missing verification means a likely visual regression would go unnoticed.
