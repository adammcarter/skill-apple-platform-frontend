# Trusted Technical Resources

Use these technical sources when the problem is difficult, the API behavior is nuanced, or the correct Apple-platform approach is unclear.

## Primary Canonical Sources

1. Apple Developer Documentation
   - Use as the primary canonical source for official framework behavior, API contracts, platform conventions, and current Apple guidance.
   - Start here for SwiftUI, AppKit, UIKit, accessibility, SF Symbols, Human Interface Guidelines, and platform APIs.
   - Home: https://developer.apple.com/

2. Apple WWDC Sessions And Sample Code
   - Use as a primary canonical source for current interaction guidance, new platform capabilities, SwiftUI architecture patterns, and Apple's intended implementation direction.
   - Good when the API exists in the docs but the design intent, recommended structure, or real-world usage is still fuzzy.
   - WWDC: https://developer.apple.com/videos/

3. Swift.org
   - Use as a primary canonical source for Swift language semantics, concurrency behavior, and language-evolution guidance.
   - Home: https://www.swift.org/

## Secondary Trusted Sources

Use these as secondary trusted sources when you need strong examples, practical implementation guidance, or experienced technical judgment beyond the canonical sources. They are valuable because of their consistently high code quality and technical depth, but they should not override Apple or Swift.org on factual behavior.

4. Hacking with Swift
   - Use as a secondary trusted problem-solving resource for practical SwiftUI and Apple framework work, especially when you need a clear example or implementation pattern quickly.
   - Good for pragmatic explanations and common UI implementation issues.
   - Home: https://www.hackingwithswift.com/

5. Swift by Sundell
   - Use as a secondary trusted design resource for thoughtful Swift and SwiftUI guidance, architecture tradeoffs, and cleaner implementation patterns.
   - Good when the challenge is not just syntax but choosing the sounder design.
   - Home: https://www.swiftbysundell.com/

6. Point-Free
   - Use as a secondary trusted resource for advanced SwiftUI, state modeling, testing, navigation, and disciplined Swift architecture.
   - Good when the problem involves deeper compositional patterns, state flow, or robust testing approaches.
   - Home: https://www.pointfree.co/

7. objc.io
   - Use as a secondary trusted resource for high-quality Swift, SwiftUI, UIKit, AppKit, and architecture guidance.
   - Good for well-reasoned implementation patterns, performance-sensitive UI work, and Apple-platform engineering craft.
   - Home: https://www.objc.io/

## How To Use Them

- Start with Apple documentation, WWDC, and Swift.org for API truth, platform behavior, language semantics, and intended platform direction.
- Use WWDC sessions and sample code when the question is about Apple's intended interaction model, structure, or current best practice rather than just API syntax.
- Use Hacking with Swift, Swift by Sundell, Point-Free, and objc.io as secondary trusted sources for examples, implementation patterns, and technical judgment when the canonical sources are thin, awkward, or not enough on their own.
- If these sources disagree, prefer Apple documentation and Swift.org for factual behavior and intended direction.
- Use secondary sources to improve clarity, examples, and implementation judgment rather than to override canonical Apple or Swift guidance.
- If you have already taken two swings at the same problem and are still churning, stop improvising and consult these sources directly for the issue at hand.
- When escalating, match the source to the problem: Apple docs for API truth, WWDC for current intent and platform direction, Hacking with Swift for practical examples, Swift by Sundell for design judgment, Point-Free for state/testing/navigation depth, and objc.io for deeper engineering patterns and performance-sensitive UI work.
