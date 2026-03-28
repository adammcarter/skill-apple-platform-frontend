# Example Recipe: Visual Polish

Use this when the task explicitly needs a concrete example of hierarchy, spacing, typography, and restrained chrome.

```swift
struct SummaryPanel: View {
    let title: String
    let subtitle: String
    let status: String
    let metrics: [Metric]

    var body: some View {
        VStack(alignment: .leading, spacing: 16) {
            HStack(alignment: .firstTextBaseline, spacing: 12) {
                VStack(alignment: .leading, spacing: 4) {
                    Text(title)
                        .font(.title3.weight(.semibold))

                    Text(subtitle)
                        .font(.subheadline)
                        .foregroundStyle(.secondary)
                }

                Spacer(minLength: 0)

                Text(status)
                    .font(.caption.weight(.semibold))
                    .foregroundStyle(.secondary)
                    .padding(.horizontal, 10)
                    .padding(.vertical, 6)
                    .background(.quaternary, in: Capsule())
            }

            Divider()

            HStack(spacing: 20) {
                ForEach(metrics) { metric in
                    VStack(alignment: .leading, spacing: 2) {
                        Text(metric.value)
                            .font(.headline)
                        Text(metric.label)
                            .font(.caption)
                            .foregroundStyle(.secondary)
                    }
                }
            }
        }
        .padding(20)
        .background(.regularMaterial, in: RoundedRectangle(cornerRadius: 18, style: .continuous))
    }
}

struct Metric: Identifiable {
    let id = UUID()
    let label: String
    let value: String
}
```

Why it works:
- hierarchy comes from grouping, spacing, and type before decoration
- there is one clear focal path: title and subtitle first, status second, metrics third
- chrome is used once for the surface and once for the status, rather than stacked on every subview
- secondary information stays quiet without becoming hard to scan
