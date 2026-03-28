# AppKit And UIKit Interop

Use this reference when SwiftUI alone is not the right tool for the required UI behavior.

## When Interop Is Justified

- The app already has substantial UIKit or AppKit infrastructure worth preserving.
- A specific control, text system, collection behavior, drag/drop flow, or rendering path is materially better in the platform framework.
- The requirement depends on APIs that are missing, immature, or awkward in SwiftUI.

## Interop Rules

- Wrap the smallest possible surface area.
- Keep ownership clear: the wrapper should adapt platform behavior to SwiftUI, not become a second app architecture.
- Keep platform-specific code close to the wrapper rather than leaking it across the whole feature.
- Prefer a narrow coordinator with explicit responsibilities over a catch-all object.

## Design Guidance

- Preserve native platform behavior instead of flattening it into cross-platform compromise.
- Do not force AppKit or UIKit control density onto the wrong platform.
- Keep accessibility semantics intact when bridging custom platform views into SwiftUI.

## Code Structure

- Isolate representable wrappers behind focused names.
- Expose a SwiftUI-friendly API rather than mirroring every underlying platform knob.
- Push configuration that affects visuals or interaction to the wrapper boundary, not scattered call sites.
- Keep delegates, data sources, and callbacks disciplined; do not let them become alternate state stores.

## Warning Signs

- A representable that exists only because the author was more comfortable in UIKit or AppKit.
- Large bidirectional state sync with unclear ownership.
- Wrapper code that recreates behavior SwiftUI already provides adequately.
- Platform code copied into many call sites instead of centralized behind one wrapper.
