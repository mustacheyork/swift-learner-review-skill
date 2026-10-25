# Swift Learner Review — Agent Skill for teaching-grade code review

**An agent skill that turns Claude Code / Codex / Cursor into a patient Swift mentor.**
It reviews a beginner's Swift / SwiftUI code the way an experienced instructor would: check the goal, praise what is right, give hints instead of answers, and speak to the learner as an adult.

Built from 11 years of writing *iPhoneアプリ開発集中講座* (an annually revised Swift textbook) and running the online school [CodeCandy](https://code-candy.com/), where every submission has been reviewed with this method since 2015 — by humans first, by AI since 2025.

---

**Claude Code / Codex / Cursor を「根気強い Swift の先輩」にする agent skill です。**
初学者の Swift / SwiftUI コードを、経験ある講師と同じ順番でレビューします。達成条件の確認、良い点の具体的な称賛、答えではなくヒント、そして大人の学習者への敬意ある言葉づかい。

11 年続けて改訂している書籍『iPhoneアプリ開発集中講座』と、オンラインスクール CodeCandy での添削経験（2015 年から人が、2025 年からは AI が同じ方法で）をまとめたものです。

## What it does / できること

- **Goal first** — reads the assignment's success criteria and checks each one before anything else
- **Praise with evidence** — names the exact line that was done well and why it matters
- **Hints, not answers** — points at the idea the learner is missing; never pastes the solution
- **Before / After** — when suggesting a rewrite, shows the learner's own code next to the improved one
- **Stage-aware** — does not mention SwiftLint, architecture, or concurrency to someone on day 3
- **Adult tone** — no "let's try hard!", no classroom voice; peer-to-peer language (default: Japanese)
- **Topic pitfalls** — a reference of what beginners typically get wrong per Swift topic, from constants to structs

## Install / インストール

```bash
npx skills add https://github.com/mustacheyork/swift-learner-review-skill --skill swift-learner-review
```

Claude Code plugin:

```
/plugin marketplace add mustacheyork/swift-learner-review-skill
/plugin install swift-learner-review@swift-learner-review-skill
```

`npx skills add` installs into the **current project** by default. Add `-g` to make it available in every project:

```bash
npx skills add https://github.com/mustacheyork/swift-learner-review-skill --skill swift-learner-review -g
```

> 💡 If you run the command from inside an agent (for example `! npx skills add …` in Claude Code), it installs non-interactively into that project. Run it in your own terminal, or add `-g`, for a global install. Restart the agent session afterwards so the skill is loaded.

Or copy `swift-learner-review/` into `~/.claude/skills/` (Claude Code) or your agent's skills folder.

## Use / 使い方

Give the agent the learner's code (a file, a folder, a PR, or pasted text) and, if you have one, the assignment text. Then:

```
/swift-learner-review  review this submission for the "Optionals" assignment
```

```
このコードを「定数と変数」課題として レビューして
```

The agent returns a review in four sections — ✅ criteria / 🌟 good points / 💡 hints / 📚 next step — plus a two-line summary you can paste into Slack or a comment.

### Options you can state in the prompt
- **language**: `in English` / `日本語で`（default: Japanese）
- **stage**: `beginner` (grammar), `app` (first SwiftUI apps), `release` (lint, tests, architecture)
- **strictness**: `gentle` / `normal` / `strict`
- **assignment**: paste the success criteria, or say "no assignment" for a free review

## Who it is for / 想定ユーザー

- Instructors and mentors who review many beginner submissions
- Self-learners who want a review that teaches rather than fixes
- Teams onboarding junior iOS engineers

## Structure

```
swift-learner-review/
├── SKILL.md                      # the procedure the agent follows
└── references/
    ├── feedback-format.md        # the 4-section template and Before/After rule
    ├── tone.md                   # adult-learner wording (JA/EN)
    ├── stages.md                 # what to check at each learning stage, what NOT to mention
    ├── hints-not-answers.md      # how to hint without giving the solution
    └── pitfalls.md               # typical beginner mistakes per Swift topic
```

## Author

Kanako Kobayashi — iOS engineer, co-author of *iPhoneアプリ開発集中講座* (2016–2026), founder of TickleCode LLC and CodeCandy.
Blog: https://blog.code-candy.com/

## License

MIT
