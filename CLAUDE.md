# CLAUDE.md — AI Assistant Guide for AI-na-Maksa

## Repository Overview

This is the **GitHub profile portfolio repository** for Maksym Bystrov (`AI-na-Maksa`), a No-Code & AI specialist. It serves two purposes:

1. **Profile README** — `README.md` displays as the GitHub profile page
2. **Demo notebooks** — Jupyter notebooks showcasing AI/automation projects, designed to run in Google Colab

**Repository type:** Documentation + Jupyter notebooks (Python)
**No web app, build system, or test suite exists.**

---

## Repository Structure

```
AI-na-Maksa/
├── README.md                        # Bilingual (UA/EN) portfolio profile page
├── google_ai_content_maker.ipynb    # Google AI content pipeline notebook (UA/PL, Colab)
└── CLAUDE.md                        # This file — AI assistant guide
```

---

## README.md Conventions

### Language

The README is **bilingual UA/EN** — every user-facing section contains both:
- **Ukrainian** (`🇺🇦`) — primary language
- **English** (`🇬🇧`) — secondary language

> **Note:** Jupyter notebooks use **UA/PL** (Ukrainian + Polish), not UA/EN. Keep these language pairs separate — do not mix them.

When adding or editing README content, always provide both Ukrainian and English versions. Use the existing side-by-side table pattern for prose sections:

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

## Jupyter Notebook Conventions

### Language

Notebooks are **bilingual UA/PL** — Ukrainian (`🇺🇦`) primary, Polish (`🇵🇱`) secondary. This is intentional and targets a UA+PL audience. Do not use English (`🇬🇧`) in notebooks.

Bilingual table pattern (same structure as README, different flag):

```markdown
| 🇺🇦 | 🇵🇱 |
| --- | --- |
| Текст українською | Tekst po polsku |
```

### Colab Badge

Every notebook must include an "Open In Colab" badge in the first cell, pointing to the `main` branch:

```markdown
[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/AI-na-Maksa/AI-na-Maksa/blob/main/<notebook-filename>.ipynb)
```

> During development on a feature branch, the badge may temporarily point to that branch. Update to `main` before or after merging.

### Notebook Structure Pattern

Each notebook follows this cell order:

1. **Title cell (markdown)** — `# 🤖 Notebook Title`, Colab badge, bilingual description table, author line
2. **Stack/tools table (markdown)** — overview of all tools/APIs used
3. **Dependencies cell (code)** — `!pip install <packages> -q`
4. **Setup/config section (markdown + code)** — API key loading instructions and code
5. **Feature sections** — one section per capability, each with a markdown explanation cell followed by code cell(s)
6. **Author bio cell (markdown)** — bilingual, with GitHub/LinkedIn/Telegram links

### Dependencies

Dependencies are installed inline via `!pip install` in the first code cell. Current notebooks use:

| Notebook | Package(s) |
|----------|-----------|
| `google_ai_content_maker.ipynb` | `google-generativeai` |

Do not add `requirements.txt` or `pyproject.toml` — notebooks are self-contained.

### API Keys

API keys are loaded at runtime; never hard-coded. The standard pattern:

```python
try:
    from google.colab import userdata
    API_KEY = userdata.get('KEY_NAME')
except Exception:
    API_KEY = os.environ.get('KEY_NAME', '')

if not API_KEY:
    raise ValueError("KEY_NAME not set.")
```

### Runtime Output Files

Files generated during notebook execution (e.g. `content_output.csv`) are created at runtime in the Colab environment and are **not committed** to the repository.

---

## Development Workflow

### Making Changes

Since there is no build system, the workflow is straightforward:

1. Edit `README.md` or a `.ipynb` notebook directly
2. Review changes visually (Markdown preview / Jupyter preview)
3. Commit with a descriptive message
4. Push to the appropriate branch

### Commit Message Style

Based on the existing git history, commits follow plain descriptive messages:

- `Initial commit: Created README.md with title "..."`
- `Polished bilingual README`
- `Add Google AI Content Maker notebook (Gemini, Veo, NotebookLM) — UA/PL`

Prefer descriptive messages that explain *what changed*, e.g.:
- `Add new project to portfolio: <project-name>`
- `Update contact information`
- `Add <tool> to stack section`
- `Add <topic> notebook — UA/PL`

### Branch Strategy

- **`main`** — default branch with production content
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

1. **README has nothing to run** — do not attempt to execute, test, or build `README.md`
2. **Notebooks run in Google Colab** — do not run notebooks locally unless explicitly asked; they depend on Colab Secrets for API keys
3. **Always bilingual** — README additions need UA + EN; notebook additions need UA + PL
4. **Never mix language pairs** — README is UA/EN, notebooks are UA/PL; do not cross them
5. **Preserve emoji convention** — emojis are intentional and part of the style
6. **HTML sparingly** — only for centering/alignment in README; pure Markdown in notebooks
7. **Do not add project tooling** — no `package.json`, `requirements.txt`, `Makefile`, CI config, etc.
8. **Keep it personal** — content reflects Maksym's actual skills and projects; do not invent or fabricate portfolio items
9. **Badge URLs must be valid** — verify shields.io and Colab badge URLs before adding them
10. **Never hard-code API keys** — always use Colab Secrets / environment variable pattern
