# Example Recipe: Controls And State

Use this when the task explicitly needs examples of native toolbar actions, SF Symbol discipline, or small state-driven visual changes.

## Toolbar Action With SF Symbol Discipline

```swift
struct CompareToolbar: ToolbarContent {
    let toggleInspector: () -> Void

    var body: some ToolbarContent {
        ToolbarItem(placement: .primaryAction) {
            Button("Inspector", systemImage: "sidebar.right", action: toggleInspector)
                .help("Show or hide the inspector")
        }
    }
}
```

## State Transition That Explains Change

```swift
struct SelectionBadge: View {
    let isSelected: Bool

    var body: some View {
        ZStack {
            if isSelected {
                Label("Selected", systemImage: "checkmark.circle.fill")
                    .font(.caption.weight(.semibold))
                    .padding(.horizontal, 10)
                    .padding(.vertical, 6)
                    .background(.regularMaterial, in: Capsule())
                    .transition(.scale.combined(with: .opacity))
            }
        }
        .animation(.spring(response: 0.25, dampingFraction: 0.85), value: isSelected)
    }
}
```

Why it works:
- uses native toolbar patterns and clear labels
- keeps iconography aligned with system meaning
- uses animation to explain state change rather than decorate it
