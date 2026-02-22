---
description: Translate text from English to Brazilian Portuguese
allowed-tools: Read, Write, Edit, Grep, Glob, Bash, Task
argument-hint: [English text to translate or file path]
---

Translate $ARGUMENTS from English to Brazilian Portuguese using the translation-specialist skill.

**This command delivers fast, accurate translation. English in → Portuguese out. Professional, natural, culturally adapted.**

## Layer 1 — Input & Context

**What:** Parse the input and determine translation context.
**How:** Parse $ARGUMENTS — text may be inline, a file path, or uploaded content.
- Read the translation-specialist skill from this plugin
- Identify document type (email, report, presentation, brief, policy)
- Identify formality level from context (C-level formal, technical precise, team conversational)
- Note any domain-specific terminology (payments, technology, finance)

**Why:** Translation quality depends on understanding the document's purpose and audience. A board email requires different Portuguese than a team Slack message.

## Layer 2 — Translation

**What:** Translate applying cultural adaptation and terminology management.
**How:**
1. Translate maintaining the original structure and formatting
2. Apply terminology rules: preserve English tech terms standard in Brazil (deploy, sprint, pipeline), translate business terms (budget → orçamento, timeline → cronograma)
3. Apply cultural adaptation: use "você" (not formal "Vossa Excelência"), add proper articles, convert to active voice where natural in PT-BR
4. Convert dates, times, numbers to Brazilian format (22/02/2026, 17h00, 1.234,56)
5. Preserve BLUF/message structure — don't let translation flatten the hierarchy

**Why:** Professional translation is more than word substitution. Cultural adaptation ensures the Portuguese reads as native, not as translated English.

## Layer 3 — Delivery

**What:** Deliver the translation with minimal notes.
**How:**

Output the complete translated text first. Then:
- Note any terminology decisions that were context-dependent
- Flag any sections where human review is recommended (ambiguity, idioms)
- State confidence level

Keep notes brief. The translation is the deliverable.

**Why:** The user needs the Portuguese text, not a translation methodology lesson.
