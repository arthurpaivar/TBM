---
description: Translate text from Brazilian Portuguese to English
allowed-tools: Read, Write, Edit, Grep, Glob, Bash, Task
argument-hint: [Portuguese text to translate or file path]
---

Translate $ARGUMENTS from Brazilian Portuguese to English using the translation-specialist skill.

**This command delivers fast, accurate translation. Portuguese in → English out. Professional, precise, corporate-ready.**

## Layer 1 — Input & Context

**What:** Parse the input and determine translation context.
**How:** Parse $ARGUMENTS — text may be inline, a file path, or uploaded content.
- Read the translation-specialist skill from this plugin
- Identify document type (email, report, presentation, brief, policy)
- Identify formality level from context
- Note any domain-specific terminology

**Why:** PT-BR has nuances that require understanding the document's purpose to translate correctly into English. "Responsável" could be "owner" or "responsible party" depending on context.

## Layer 2 — Translation

**What:** Translate to professional English preserving meaning and structure.
**How:**
1. Translate maintaining original structure and formatting
2. Apply terminology rules: convert Brazilian tech terms to their English equivalents, preserve acronyms standard in both languages (API, SLA, ROI)
3. Adjust tone: Brazilian Portuguese is often warmer and more relational — calibrate to professional English appropriate for the audience
4. Convert dates, times, numbers to US/international format (02/22/2026, 5:00 PM, 1,234.56)
5. Preserve BLUF/message structure in the English version

**Why:** Portuguese-to-English translation must produce text that reads as native English, not translated Portuguese. Tone recalibration is essential — direct translation of Brazilian warmth can read as informal in English corporate contexts.

## Layer 3 — Delivery

**What:** Deliver the translation with minimal notes.
**How:**

Output the complete translated text first. Then:
- Note any terminology decisions that were context-dependent
- Flag any culturally-specific expressions that were adapted
- State confidence level

Keep notes brief. The English text is the deliverable.

**Why:** The user needs the English text ready for professional use.
