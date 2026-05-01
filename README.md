# 1 Hour Guide — Content Repository

Tutorial content for **[1hour.guide](https://1hour.guide)**.

> Learn anything in 1 hour. Hands-on tutorials, no fluff.

This is a **content-only** repository. The site framework lives separately at [tutorial-kit](../tutorial-kit/).

## Structure

```
1hour-guide-content/
├─ tutorials/                  # All tutorials
│  └─ <slug>/
│     ├─ meta.yaml             # Shared metadata (category, difficulty, etc.)
│     ├─ en.mdx                # English version
│     └─ zh.mdx                # Chinese version
├─ categories.yaml             # Category definitions (multilingual)
├─ site.yaml                   # Site-wide metadata
├─ i18n/                       # UI string translations
│  ├─ en.yaml
│  └─ zh.yaml
└─ README.md
```

## Tutorial Schema

### `meta.yaml`

```yaml
slug: python-basics
category: code              # one of: code, ai, design, business, web, mind
difficulty: beginner        # beginner, intermediate, advanced
duration: 60                # minutes (target: 60)
tags: [python, cli]
date: 2026-05-01
published: true
cover: /images/tutorials/python-basics.svg
author: zoe

translations:
  en: { status: published }   # published | draft | missing
  zh: { status: published }
```

### `<lang>.mdx`

```mdx
---
title: "1 Hour to Python Basics"
description: "Go from zero to..."
---

By the end of this hour...

## 🎯 What You'll Build

...

<TimeBlock start="0" end="10" title="Setup" />

<Checkpoint>
Question text
<Answer>Answer text</Answer>
</Checkpoint>

<NextStep slug="ai-chatbot" />
```

## Custom MDX Components

| Component | Usage |
|-----------|-------|
| `<TimeBlock start={0} end={10} title="..." />` | Time allocation marker |
| `<Checkpoint>...</Checkpoint>` | Self-test block |
| `<Answer>...</Answer>` | Collapsible answer (inside Checkpoint) |
| `<NextStep slug="..." />` | Recommend next tutorial |

## Writing Style

1. **Time-boxed**: every tutorial fits in 60 minutes
2. **Outcome-first**: lead with what you'll build
3. **Hands-on**: code first, theory second
4. **Checkpoints**: verify progress at each section
5. **Concise**: target 500–1500 words per tutorial

## Adding a New Tutorial

1. Create folder: `tutorials/<slug>/`
2. Add `meta.yaml` with required fields
3. Write `en.mdx` (English first; Chinese can come later)
4. Mark `translations.zh.status: draft` if no Chinese version yet
5. Submit a PR

## Translation Workflow

1. English is the **source of truth**
2. Chinese translations follow when possible
3. Use `translations.<lang>.status: missing` if not yet translated
4. Tutorials with `status: missing` show a fallback notice on the localized page

## License

CC BY-SA 4.0 — feel free to share and adapt with attribution.
