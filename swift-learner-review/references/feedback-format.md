# Feedback format

## The 4-section template

```markdown
## 📝 コードレビュー

### ✅ 達成条件の確認
- 条件1: ✅ / ⚠️ / ❌ — 根拠（行・挙動）
- 条件2: …

### 🌟 良かった点
- `識別子` や該当行を挙げて、何が良くてなぜ大事かを 1〜2 文で

### 💡 改善のヒント
- 気づいてほしい考え方 ＋ それに向かう問いかけ
- コードを出すなら Before / After で

### 📚 次のステップ
- 次に学ぶと今回の学びがつながるもの、または次の課題への一言
```

In English, keep the same four headings: Criteria / What works / Hints / Next step.

## Rules
- **Criteria first.** The learner needs to know "did I pass" before anything else.
- **Praise is evidence-based.** Name the line. "Good naming" is not feedback; "`totalPrice` says exactly what the value is, so the `if` on line 12 reads like a sentence" is.
- **One idea per hint.** Three sharp hints beat ten vague ones. Cap at 3 for beginners, 5 for later stages.
- **Never a wall of text.** A beginner reads about 15 lines before they stop. Short sections, blank lines, bullets.
- **End on what to do next**, not on a problem.

## Before / After

When you suggest a rewrite, show both, with the learner's own code first:

````markdown
**Before（あなたのコード）**
```swift
if isOn {
    Text("ライトON").foregroundStyle(.black)
} else {
    Text("ライトOFF").foregroundStyle(.white)
}
```

**After（三項演算子で共通部分をまとめる）**
```swift
Text(isOn ? "ライトON" : "ライトOFF")
    .foregroundStyle(isOn ? .black : .white)
```
````

- The After must change **one idea** only, so the learner can see the cause of the improvement.
- Label the After with the concept name, so it becomes something they can search for.
- A Before/After is allowed only for a *part* of the code. Never for the whole assignment.

## Short version (for chat)

```
拝見しました！ 条件分岐の切り分けがとても丁寧で、意図が読み取れるコードでした👍
フィードバックはこちらにまとめています → <link>  次は「繰り返し処理」です。
```
