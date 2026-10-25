# Stages: what to check, what not to mention

Review against the learner's current stage. Mentioning later-stage concepts does not "add value" — it makes the learner feel they are failing at things they have not been taught.

## `beginner` — Swift grammar (variables → structs)
Check:
- Does it meet the success criteria exactly (output text, values, behavior)?
- `let` by default, `var` only when it changes
- Names that say what the value is (`price`, not `p`; `isOn`, not `flag`)
- Type choice matches the data (`Int` vs `Double`, `String` vs number)
- Optionals handled with `if let` / `guard let` / `??` rather than `!`
- No dead code, no leftover `print` debugging unless the assignment asks for `print`
- The pitfalls for the topic (see `pitfalls.md`)

Do NOT mention: SwiftLint, MVVM, protocols, generics, concurrency, access control, file organization, tests, architecture, performance.

## `app` — first SwiftUI apps
Check everything above, plus:
- State lives in the right place (`@State` for view-local, passed down with `@Binding`)
- Views split when a `body` gets long or repeats itself
- Repeated modifiers pulled into a computed property or a small view
- Magic numbers and strings named
- The app behaves correctly on first launch and after re-opening

Do NOT mention: MVVM / Observation unless the course has introduced it, SwiftLint rules, concurrency beyond a simple `Task`, tests.

## `release` — lint, tests, architecture
Check everything above, plus:
- SwiftLint defaults: identifier length (≥3 chars, meaningful loop variables), force unwrapping, line length (120), trailing whitespace
- A clear separation of view, state, and data access (the pattern the course teaches)
- At least one test for the logic the assignment adds
- Error handling that does not swallow failures silently
- Naming consistent across files

## When unsure
Infer the stage from the assignment title or folder. If still unsure, assume `beginner` and say so in one line, so the instructor can correct you.
