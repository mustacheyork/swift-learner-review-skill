# Typical beginner pitfalls, by Swift topic

Open the section for the assignment's topic and check each item on purpose. Report only what the stage allows (see `stages.md`). Each item: what to look for → the hint direction.

## Constants and variables（定数と変数）
- Everything declared with `var` → ask which values ever change after assignment
- A value re-declared instead of re-assigned (`let x = 1` then `let x = 2`) → scope and redeclaration
- One-letter or abbreviated names (`a`, `cnt`, `str1`) → "what is this value?" as the name
- String interpolation written as `"合計: " + String(total)` when `"\(total)"` was taught → interpolation exists for this

## Data types（データ型）
- `Int` used for prices or averages that need decimals → where does the fraction go?
- `Double` compared with `==` → floating point is approximate
- Mixing `Int` and `Double` without conversion → Swift does not convert silently; which one should the result be?
- `String` holding a number that is later used in arithmetic → the type should match the use

## Basic operators（演算子・基礎）
- Integer division surprise (`7 / 2 == 3`) → what type is each operand?
- `%` used on `Double` or expected to work like "percent" → remainder, not percent
- Operator precedence assumed left-to-right (`10 - 2 * 3`) → which operation runs first?
- Compound assignment avoided (`x = x + 1` everywhere) → `+=` exists; fine for beginners, mention once

## Advanced operators（演算子・応用）
- `&&` / `||` chains without parentheses → readability; group the intent
- `!` placed where it is hard to read (`!isNotReady`) → double negatives; rename
- Ternary nested two levels deep → an `if` would read better here
- `??` used on a non-optional → the compiler warns; what is actually optional?

## Conditions（条件分岐）
- `if` / `else if` chain that could be a `switch` on one value → switch reads as a table
- `switch` with a `default` that hides a missing case → is `default` really "anything else"?
- `==` against `true` (`if isOn == true`) → the Bool is already the condition
- Ranges written as `x >= 1 && x <= 10` when `1...10 ~= x` or `case 1...10` was taught → optional mention

## Loops（繰り返し処理）
- `for i in 0..<array.count` then `array[i]` → iterate the elements directly; `enumerated()` if the index is needed
- Loop variable named `i` for something that is not an index → name what each element is
- Off-by-one on `...` vs `..<` → count the iterations out loud
- `while` with a condition that never changes → where does the exit happen?
- Mutating the array being iterated → undefined behavior territory; collect first, change after

## Optionals（オプショナル）
- `!` force unwrap on user input or dictionary lookups → what happens when it is `nil`?
- `if let x = x` nesting three deep → `guard let` flattens; or combine with commas
- `Optional` returned where a default makes sense → `??`
- Comparing to `nil` then force-unwrapping on the next line → that is what `if let` does in one step
- Implicitly unwrapped optional (`String!`) in learner code → almost never what a beginner wants

## Tuples（タプル）
- Tuple used where a struct is clearly needed (passed around 4+ times) → mention only as "next step"
- Unlabeled tuple accessed with `.0` `.1` → label the elements
- Tuple returned when a single value would do → is the second value ever used?

## Arrays（配列）
- Index access without checking bounds (`items[3]`) → what if there are two items?
- `append` inside a loop that could be a `map` → fine for beginners; mention once at `app` stage
- `var` array that is never mutated → `let`
- Removing while iterating → see Loops

## Sets（セット）
- `Set` used but order expected → sets are unordered; sort when displaying
- Duplicates removed by hand with a loop → that is what a `Set` is for
- `Set` of a type that is not `Hashable` (a learner struct) → the compiler error is the hint

## Dictionaries（辞書）
- `dict[key]!` → the lookup is optional for a reason
- Iterating and assuming insertion order → unordered; sort keys when order matters
- `updateValue` vs subscript confusion → both work; subscript is the common form
- Key type `String` holding what is really an `Int` or an enum → the key should match the data

## Functions（関数）
- A function that does three things and is named for one → split, or name honestly
- Parameters passed in but never used → remove or use
- Return value computed then printed inside the function (and also returned) → one responsibility: return, let the caller print
- Argument labels that make the call site read oddly (`move(x: 3, y: 4)` vs `move(toX:y:)`) → read the call out loud
- Repeated code across two functions → extract the shared part

## Scope（スコープ）
- Variable declared at top level "so it's visible everywhere" → narrow it to where it is used
- Same name reused in nested scopes (shadowing) → legal but confusing; rename
- `var` outside a function mutated inside it → pass it in and return the result

## Structures（構造体）
- `struct` with all `var` properties that never change → `let`
- Mutating method without `mutating` → the compiler error is the hint
- A struct that is really just a tuple with a name (no methods, no invariants) → fine for now; mention only as next step
- Initializer written by hand that duplicates the memberwise init → Swift generates one
- Property named with the type repeated (`User.userName`) → `User.name`

## SwiftUI first apps（`app` stage）
- `@State` declared without `private` → convention; mention once
- State mutated from a child view through a copy instead of a `@Binding` → the change does not show
- A `body` longer than ~40 lines or with repeated blocks → extract a view or a computed property
- Modifiers in an order that changes the result (`.padding()` before/after `.background()`) → order is meaning
- Hard-coded strings and numbers repeated in several places → name them once
- `ForEach` over an array of non-`Identifiable` items with `id: \.self` on duplicates → the duplicate rows misbehave

## General (any topic)
- Leftover `print` used for debugging
- Commented-out code left in the submission
- Inconsistent indentation (Xcode's Ctrl+I fixes it)
- Japanese and English mixed inside one identifier
- A fix that makes the criteria pass but breaks the previous criterion
