# Apple UI Anti-Patterns

Use this reference to catch weak Apple-platform frontend decisions early.

## Platform Fit

- Importing generic web or Dribbble aesthetics without adapting them to Apple conventions.
- Using oversized card-heavy layouts on macOS where denser, clearer structure would work better.
- Porting the exact same UI across macOS, iOS, and visionOS without respecting each platform's interaction model.

## Components

- Replacing standard Apple controls with custom controls that are harder to use and less accessible.
- Hiding important actions behind ambiguous icon-only buttons when text or system patterns would be clearer.
- Creating complex navigation patterns where a native split view, tab view, sheet, or inspector would be simpler.

## Layout

- Using fixed frames to paper over poor hierarchy or layout structure.
- Letting text truncate or overlap under Dynamic Type, localization growth, or window resizing.
- Treating empty states as decorative filler instead of actionable orientation.

## Motion

- Adding animation that looks expensive but does not communicate reason, continuity, or hierarchy.
- Using long transitions on frequent actions that should feel immediate.
- Animating multiple layers at once in a way that makes the change harder to parse.

## Iconography

- Using custom icons for standard concepts that SF Symbols already expresses better.
- Mixing rendering styles, weights, or visual languages within one toolbar or control group.
- Relying on color-only icon changes to communicate meaning or state.

## Accessibility

- Encoding state with color alone.
- Treating VoiceOver, keyboard access, or reduced motion as cleanup instead of design constraints.
- Shipping custom controls without explicit accessibility labels, values, and actions.

## Code Structure

- A single view that owns too much state, layout, and business logic.
- Modifier stacks and workaround properties that visually force a result while obscuring the real layout or state problem.
- Redundant view state or styling properties that cancel each other out or make the screen harder to reason about.
- Interop wrappers that exist only because the implementer defaulted to UIKit or AppKit out of habit.
- Preview coverage that ignores the states most likely to regress.

## Bad SwiftUI Examples

Unnecessary modifier pile-up:

```swift
Text(title)
    .font(.headline)
    .padding(.horizontal, 16)
    .padding(.horizontal, 12)
    .frame(maxWidth: .infinity)
    .frame(width: 240)
    .background(Color.blue)
    .background(Color.clear)
    .cornerRadius(12)
    .clipShape(RoundedRectangle(cornerRadius: 12))
```

Why it is weak:
- modifiers are compensating for each other instead of expressing one clear layout intent
- repeated padding and conflicting frames make the final result harder to reason about
- stacked background and shape modifiers suggest the structure wants simplifying rather than more polish

Bad nesting and overloaded body:

```swift
struct DashboardView: View {
    @State private var isLoading = false
    @State private var showEmpty = false
    @State private var showError = false
    @State private var selectedItem: Item?

    var body: some View {
        VStack {
            HStack {
                VStack {
                    if isLoading {
                        ProgressView()
                    } else {
                        if showError {
                            Text("Something went wrong")
                        } else {
                            if showEmpty {
                                Text("No Items")
                            } else {
                                ScrollView {
                                    VStack {
                                        ForEach(items) { item in
                                            HStack {
                                                Text(item.title)
                                                Spacer()
                                                if selectedItem?.id == item.id {
                                                    Image(systemName: "checkmark")
                                                }
                                            }
                                            .padding()
                                            .background(selectedItem?.id == item.id ? Color.blue.opacity(0.2) : Color.clear)
                                            .onTapGesture {
                                                selectedItem = item
                                            }
                                        }
                                    }
                                }
                            }
                        }
                    }
                }
            }
        }
    }
}
```

Why it is weak:
- nested conditionals and containers bury the actual screen structure
- state, selection rules, empty/error/loading logic, and row rendering all live in one body
- this wants explicit state modeling and extracted subviews rather than more indentation
