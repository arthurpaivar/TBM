---
description: Refine and elevate professional writing
allowed-tools: Read, Write, Edit, Grep, Glob, Bash, Task
argument-hint: [text to improve or file path]
---

Improve and refine the provided text in $ARGUMENTS using the text-improver-specialist skill.

**This command is about fast, high-quality text transformation. Input text → improved text. Clean and immediate.**

## Layer 1 — Assessment

**What:** Understand the text and what needs improvement.
**How:** Parse $ARGUMENTS — the text may be provided inline, as a file path, or as uploaded content.
- Read the text-improver-specialist skill from this plugin
- Assess the text across all five dimensions: clarity, conciseness, tone, structure, impact
- Identify the document type (email, brief, report, speaker notes, slide content) for style calibration
- Identify the likely audience if not specified (default: executive)

**Why:** The five dimensions provide a systematic improvement framework. Identifying document type ensures the right style guide is applied.

## Layer 2 — Improvement

**What:** Apply the five improvement dimensions.
**How:**
1. **Clarity**: Convert passive to active, replace vague pronouns, define jargon
2. **Conciseness**: Remove filler words, eliminate redundancy, tighten sentences
3. **Tone**: Calibrate for audience — formal for C-suite, detailed for technical teams
4. **Structure**: Apply topic → support → transition paragraph flow; lead with BLUF
5. **Impact**: Lead with the most important point, use data over vague claims, show causation

Deliver the improved text first, then summarize changes.

**Why:** Systematic application of all five dimensions ensures nothing is missed. Delivering the improved text before the explanation respects the user's time.

## Layer 3 — Delivery

**What:** Present the improved text with change summary.
**How:**

Output the improved text, then provide:
- Key improvements (what changed across the five dimensions)
- Word count reduction (original → improved, % reduction)
- Any alternative phrasings for different contexts

Keep the summary concise — the improved text is the deliverable.

**Why:** The user wants better text, not a writing workshop. Show the result, explain briefly, move on.
