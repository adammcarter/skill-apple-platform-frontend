# Example Recipe: macOS Layout

Use this when the task explicitly needs a concrete macOS example with sidebar, detail content, toolbar actions, and an inspector.

## macOS Sidebar And Inspector Layout

```swift
struct WorkspaceView: View {
    @State private var selection: UUID?
    @State private var inspectorPresented = true

    var body: some View {
        NavigationSplitView {
            ProjectSidebar(selection: $selection)
        } detail: {
            CanvasDetailView(selection: selection)
                .toolbar {
                    Button("Inspector", systemImage: "sidebar.right") {
                        inspectorPresented.toggle()
                    }
                }
                .inspector(isPresented: $inspectorPresented) {
                    InspectorPanel(selection: selection)
                        .inspectorColumnWidth(min: 260, ideal: 320)
                }
        }
    }
}
```

Why it works:
- uses native macOS split-view and inspector structure
- keeps secondary detail UI out of the main content column
- matches platform expectations for resizable, information-dense layouts
