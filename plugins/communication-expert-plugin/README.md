# Communication Expert Plugin

Your AI-powered coworker for professional communication in technology leadership at JP Morgan LATAM. Four specialist skills and six commands covering presentations, emails, translation, text improvement, and executive summaries — all following the Pyramid Principle and JP Morgan design standards.

## Skills

| Skill | Focus Areas |
|-------|-------------|
| **PowerPoint Specialist** | JP Morgan design system (navy #002D72, warm brown #6C3B2A, warm white #F8F6F3), 4 deck sizes (Small/Medium/High/Ultra High), slide architecture (Pyramid/SCQA/Problem-Solution-Impact), cross-plugin orchestration |
| **E-mail Generator** | BLUF methodology, 6 email types, tone calibration by audience, LATAM cultural sensitivity, subject line patterns |
| **Text Improver Specialist** | 5-dimension improvement (clarity, conciseness, tone, structure, impact), audience-aware rewriting, before/after analysis |
| **Translation Specialist** | EN↔PT-BR professional translation, terminology management, cultural adaptation, domain glossaries (payments, technology) |

## Commands

| Command | What It Does | Key Feature |
|---------|-------------|-------------|
| **create-improve-powerpoint** | Creates or improves a .pptx presentation | **Flagship** — orchestrates specialist subagents for content depth, builds actual .pptx with JP Morgan design, visual QA |
| **create-improve-email** | Creates or improves a professional email | Fast BLUF-structured email with tone calibration |
| **improve-text** | Refines and elevates any professional text | 5-dimension systematic improvement |
| **translate-en-pt** | Translates English to Brazilian Portuguese | Cultural adaptation + terminology management |
| **translate-pt-en** | Translates Brazilian Portuguese to English | Tone recalibration for English corporate context |
| **create-executive-summary** | Creates 1-page executive summary | SCQA pattern with decision format |

## Cross-Plugin Architecture

The PowerPoint command orchestrates specialists from other plugins for content depth:

```
create-improve-powerpoint (this plugin)
├── powerpoint-specialist (this plugin) — design system & narrative
├── problem-solving-specialist (consulting plugin) — SCQA framing, issue trees
├── industry-benchmark-specialist (consulting plugin) — sourced benchmarks
├── deep-search-specialist (consulting plugin) — multi-source research
├── business-case-specialist (consulting plugin) — financial justification
├── tech-strategy-advisory (technology plugin) — strategy context
└── architecture-specialist (technology plugin) — technical assessment
```

The Executive Summary command orchestrates internal skills (no external subagents):

```
create-executive-summary (this plugin)
├── text-improver-specialist (this plugin) — structure, clarity, conciseness
└── e-mail-generator (this plugin) — executive tone, BLUF pattern, CTA format
```

## Communication Protocol

All outputs follow: **Opening** (the So-What — answer first) → **Body** (evidence and structure) → **Conclusion** (guidance and next steps).

## How to Use

Each command activates with its slash command:

- `/create-improve-powerpoint Q4 strategy review for the board` → Full .pptx deck
- `/create-improve-email escalation about vendor delay to CIO` → Ready-to-send email
- `/improve-text [paste text]` → Polished version with change summary
- `/translate-en-pt [paste English text]` → Brazilian Portuguese translation
- `/translate-pt-en [paste Portuguese text]` → English translation
- `/create-executive-summary [document or topic]` → 1-page executive brief

## Setup

No configuration needed. Install the plugin and all skills and commands are available automatically.
