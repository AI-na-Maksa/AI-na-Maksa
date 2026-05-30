# CLAUDE.md — AI Assistant Guide for AI-na-Maksa

## Repository Overview

This is a **GitHub profile portfolio repository** for Maksym Bystrov (`AI-na-Maksa`), a No-Code & AI specialist. The repository's sole purpose is to display a professional portfolio README on the GitHub profile page.

**Repository type:** Documentation/Markdown only
**Primary artifact:** `README.md` — a bilingual (Ukrainian/English) profile page
**No source code, dependencies, tests, or build systems exist.**

---

## Repository Structure

```
AI-na-Maksa/
├── README.md        # Bilingual portfolio profile page (the only content file)
└── CLAUDE.md        # This file — AI assistant guide
```

---

## README.md Conventions

### Language

The README is **bilingual** — every user-facing section contains both:
- **Ukrainian** (`🇺🇦`) — primary language
- **English** (`🇬🇧`) — secondary language

When adding or editing content, always provide both language versions. Use the existing side-by-side table pattern for prose sections:

```markdown
| 🇺🇦 | 🇬🇧 |
| --- | --- |
| Ukrainian text | English text |
```

### Structure & Sections

| Section | Purpose |
|---------|---------|
| `<h1>` header | Name and branding with emoji |
| Tagline `<p>` | Bilingual one-liner summary |
| `👋 Про мене / About me` | Personal intro in table format |
| `⚙️ Стек & інструменти / Stack & Tools` | Tool categories as bullet lists |
| `🚀 Портфоліо / Portfolio` | Project table with Ukrainian/English descriptions |
| `📫 Контакти / Contact` | Contact links |
| Badge footer `<p align="center">` | Profile view counter + role/focus shields.io badges |

### Formatting Rules

- Section headers use emoji prefix: `## 👋 Section name`
- Tables use pipe-separated Markdown syntax
- HTML is used only for alignment (`<h1 align="center">`, `<p align="center">`)
- Bold (`**text**`) used for tool/technology names
- Bullet lists use `·` (middle dot) as separator for same-category items
- Horizontal rule `---` separates the header block from the body

### Badges (shields.io)

Badges are rendered via shields.io. URL-encode spaces as `&nbsp;` in badge labels:
```
https://img.shields.io/badge/Label-Value-color
```

Profile view counter uses komarev.com:
```
https://komarev.com/ghpvc/?username=AI-na-Maksa&style=flat
```

---

## Development Workflow

### Making Changes

Since there is no build system, the workflow is straightforward:

1. Edit `README.md` directly
2. Review changes visually (Markdown preview)
3. Commit with a descriptive message
4. Push to the appropriate branch

### Commit Message Style

Based on the existing git history, commits follow plain descriptive messages:
- `Initial commit: Created README.md with title "..."`
- `Polished bilingual README`
- `Update README.md`

Prefer descriptive messages that explain *what changed*, e.g.:
- `Add new project to portfolio: <project-name>`
- `Update contact information`
- `Add Python to stack section`

### Branch Strategy

- **`master`** — main branch with production content
- Feature/AI branches follow the pattern: `claude/<descriptor>-<session-id>`

---

## Contact & Profile Information

| Field | Value |
|-------|-------|
| Name | Maksym Bystrov |
| GitHub username | `AI-na-Maksa` |
| Email | ai.na.maksa@gmail.com |
| LinkedIn | linkedin.com/in/maksym-bystrov-2421a4118 |
| Telegram | @ai_na_maksa |

---

## Key Constraints for AI Assistants

1. **No code execution** — there is nothing to run, test, or build
2. **Always bilingual** — every new content addition needs Ukrainian + English
3. **Preserve emoji convention** — emojis are intentional and part of the style
4. **HTML sparingly** — only for centering/alignment, prefer Markdown elsewhere
5. **Do not add dependencies** — this repo intentionally has no package managers or tooling
6. **Keep it personal** — content reflects Maksym's actual skills and projects; do not invent or fabricate portfolio items
7. **Badge URLs must be valid** — test shields.io URLs before adding new badges

---

## Coding Guidelines (Karpathy)

Behavioral guidelines to reduce common LLM coding mistakes. Merge with project-specific instructions as needed.

**Tradeoff:** These guidelines bias toward caution over speed. For trivial tasks, use judgment.

### 1. Think Before Coding

**Don't assume. Don't hide confusion. Surface tradeoffs.**

Before implementing:
- State your assumptions explicitly. If uncertain, ask.
- If multiple interpretations exist, present them — don't pick silently.
- If a simpler approach exists, say so. Push back when warranted.
- If something is unclear, stop. Name what's confusing. Ask.

### 2. Simplicity First

**Minimum code that solves the problem. Nothing speculative.**

- No features beyond what was asked.
- No abstractions for single-use code.
- No "flexibility" or "configurability" that wasn't requested.
- No error handling for impossible scenarios.
- If you write 200 lines and it could be 50, rewrite it.

Ask yourself: "Would a senior engineer say this is overcomplicated?" If yes, simplify.

### 3. Surgical Changes

**Touch only what you must. Clean up only your own mess.**

When editing existing code:
- Don't "improve" adjacent code, comments, or formatting.
- Don't refactor things that aren't broken.
- Match existing style, even if you'd do it differently.
- If you notice unrelated dead code, mention it — don't delete it.

When your changes create orphans:
- Remove imports/variables/functions that YOUR changes made unused.
- Don't remove pre-existing dead code unless asked.

The test: Every changed line should trace directly to the user's request.

### 4. Goal-Driven Execution

**Define success criteria. Loop until verified.**

Transform tasks into verifiable goals:
- "Add validation" → "Write tests for invalid inputs, then make them pass"
- "Fix the bug" → "Write a test that reproduces it, then make it pass"
- "Refactor X" → "Ensure tests pass before and after"

For multi-step tasks, state a brief plan:
```
1. [Step] → verify: [check]
2. [Step] → verify: [check]
3. [Step] → verify: [check]
```

Strong success criteria let you loop independently. Weak criteria ("make it work") require constant clarification.

**These guidelines are working if:** fewer unnecessary changes in diffs, fewer rewrites due to overcomplication, and clarifying questions come before implementation rather than after mistakes.

> Source: [multica-ai/andrej-karpathy-skills](https://github.com/multica-ai/andrej-karpathy-skills) — MIT License
