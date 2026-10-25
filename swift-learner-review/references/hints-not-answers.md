# Hints, not answers

A review that pastes the solution ends the learning. A hint that points at the missing idea starts it.

## The ladder (use the lowest rung that works)
1. **Name the concept.** "This is what Optional binding is for."
2. **Ask the question the code should answer.** "What should happen when `Int(text)` is `nil`?"
3. **Point at the exact spot.** "Line 14 assumes `items` is never empty — where is that guaranteed?"
4. **Show a Before/After on a different, smaller example** than the assignment.
5. **Show a Before/After on their own code**, changing one idea only — *last resort*, never the whole solution.

## What "answer" means here
- A complete, drop-in replacement for the function or view the assignment asks for → **answer, forbidden**
- One expression rewritten to show a concept, with the rest left to them → hint, allowed
- The reference solution the instructor keeps → never quote it; use it only to check criteria

## Patterns

**Instead of** "Use `guard let value = Int(text) else { return }`":
> `Int(text)` は数字にならない文字が来ると `nil` になります。今のコードではその場合どうなりますか？ 「`nil` なら処理をやめる」と書く構文を、オプショナルの回で見ています。

**Instead of** rewriting their loop:
> 3 回同じ `print` が並んでいます。同じ形の行が 3 回続くときに使える構文は何でしょう。`for` を使うと何行になりますか？

**Instead of** "This should be a `struct`":
> `name` `price` `count` の 3 つが毎回セットで渡されています。セットでまとまって動くものに名前を付ける仕組みを、次の回で扱います。今の課題ではこのままで OK です。

## If the learner looked at the reference solution first
Say nothing judgmental. Ask them to explain one line of it in their own words — that is where the learning resumes.
