# Example Recipe: Empty States And Actions

Use this when the task explicitly needs a concrete example of a clear empty state or explicit UI state modeling.

## Empty State With Clear Action

```swift
struct LibraryEmptyState: View {
    let importAction: () -> Void

    var body: some View {
        ContentUnavailableView {
            Label("No Images Yet", systemImage: "photo.on.rectangle.angled")
        } description: {
            Text("Import a pair of images to start comparing changes.")
        } actions: {
            Button("Import Images", action: importAction)
                .buttonStyle(.borderedProminent)
        }
        .padding(24)
    }
}
```

## Explicit UI State

```swift
enum InspectorContentState: Equatable {
    case loading
    case empty
    case loaded(InspectorContent)
    case failed(String)
}

struct InspectorContentView: View {
    let state: InspectorContentState
    let retry: () -> Void

    var body: some View {
        switch state {
        case .loading:
            ProgressView("Loading")
                .frame(maxWidth: .infinity, maxHeight: .infinity)

        case .empty:
            ContentUnavailableView(
                "Nothing Selected",
                systemImage: "sidebar.right",
                description: Text("Choose an item to inspect its details.")
            )

        case let .loaded(content):
            InspectorDetailView(content: content)

        case let .failed(message):
            ContentUnavailableView {
                Label("Couldn’t Load Details", systemImage: "exclamationmark.triangle")
            } description: {
                Text(message)
            } actions: {
                Button("Try Again", action: retry)
            }
        }
    }
}
```

Why it works:
- uses native empty-state patterns instead of decorative filler
- keeps the next action obvious
- makes loading, empty, loaded, and failed states explicit
