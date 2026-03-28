# Example Recipe: Previews And Snapshots

Use this when the task explicitly needs examples of preview coverage or snapshot-friendly state matrices.

## Standalone Preview State Example

```swift
enum PreviewCardState: Equatable {
    case loading
    case empty
    case loaded(String)
    case failed(String)
}

struct PreviewCardView: View {
    let state: PreviewCardState

    var body: some View {
        switch state {
        case .loading:
            ProgressView("Loading")
                .frame(width: 320, height: 160)

        case .empty:
            ContentUnavailableView(
                "No Selection",
                systemImage: "sidebar.right",
                description: Text("Choose an item to inspect its details.")
            )
            .frame(width: 320, height: 160)

        case .loaded(let title):
            VStack(alignment: .leading, spacing: 8) {
                Text(title)
                    .font(.headline)
                Text("Metadata is available and ready to inspect.")
                    .foregroundStyle(.secondary)
            }
            .frame(maxWidth: .infinity, maxHeight: .infinity, alignment: .topLeading)
            .padding()
            .frame(width: 320, height: 160)

        case .failed(let message):
            ContentUnavailableView(
                "Couldn’t Load Details",
                systemImage: "exclamationmark.triangle",
                description: Text(message)
            )
            .frame(width: 320, height: 160)
        }
    }
}
```

## Multi-State Preview Coverage

```swift
#Preview("States") {
    Group {
        PreviewCardView(state: .loading)
        PreviewCardView(state: .empty)
        PreviewCardView(state: .loaded("Project Alpha"))
        PreviewCardView(state: .failed("The metadata file could not be read."))
    }
    .padding()
}
```

## Snapshot-Friendly State Matrix

```swift
// This snapshot example assumes the project already uses `swift-snapshot-testing-macros`.
@Suite
@SnapshotSuite
struct PreviewCardSnapshots {
    @SnapshotTest(configurationValues: [
        PreviewCardState.loading,
        .empty,
        .loaded("Project Alpha"),
        .failed("The metadata file could not be read."),
    ])
    func content(state: PreviewCardState) -> some View {
        PreviewCardView(state: state)
            .padding()
    }
}
```

Why it works:
- keeps the recipe standalone instead of depending on another example file
- covers loading, empty, loaded, and failed states
- only uses the snapshot macros when that specific library is already part of the project
