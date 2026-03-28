# Example Recipe: AppKit Interop

Use this when the task explicitly needs a lightweight AppKit bridge from SwiftUI.

## Lightweight AppKit Interop

```swift
struct VisualEffectView: NSViewRepresentable {
    var material: NSVisualEffectView.Material = .sidebar
    var blendingMode: NSVisualEffectView.BlendingMode = .withinWindow

    func makeNSView(context: Context) -> NSVisualEffectView {
        let view = NSVisualEffectView()
        view.state = .active
        return view
    }

    func updateNSView(_ view: NSVisualEffectView, context: Context) {
        view.material = material
        view.blendingMode = blendingMode
    }
}
```

Why it works:
- keeps the interop surface narrow and obvious
- uses SwiftUI for the surrounding structure and AppKit only for the missing capability
- avoids wrapping more framework behavior than the task requires
