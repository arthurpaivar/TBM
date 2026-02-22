---
description: Create or improve a professional corporate email
allowed-tools: Read, Write, Edit, Grep, Glob, Bash, Task
argument-hint: [email purpose, context, or draft to improve]
---

Create or improve a professional corporate email about $ARGUMENTS using the e-mail-generator skill.

**This command is about smooth, fast delivery. Input → polished email. No unnecessary steps.**

## Layer 1 — Context & Mode

**What:** Understand what's needed and determine operating mode.
**How:** Parse $ARGUMENTS:
- **CREATE mode**: User provides purpose, audience, and key points → generate email from scratch
- **IMPROVE mode**: User provides an existing draft → assess and refine it
- **Audience**: CIO, CFO, technical team, vendor, mixed? (Default: professional peer if unclear)
- **Type**: Status update, escalation, approval request, follow-up, FYI, meeting summary?
- **Language**: English or Portuguese? (Default: English unless specified)

**Why:** The mode determines the workflow. Creating from scratch requires structure design; improving requires diagnosis first.

## Layer 2 — Knowledge Loading & Execution

**What:** Load the email skill and produce the email.
**How:** Read the e-mail-generator skill from this plugin. Then:

**For CREATE mode:**
1. Select the appropriate email pattern (BLUF, Escalation, Meeting Summary, FYI)
2. Write the subject line following the type conventions
3. Write the BLUF opening — key message in the first sentence
4. Write the body — max 4 paragraphs with clear structure
5. Write the CTA — explicit action, deadline, decision format
6. Calibrate tone for the audience

**For IMPROVE mode:**
1. Assess the draft across: BLUF presence, structure, tone, conciseness, CTA clarity
2. Rewrite applying the e-mail-generator patterns
3. Provide before/after with key improvements noted

If the user needs the email in Portuguese, invoke the translation-specialist skill to translate the final output with proper cultural adaptation.

**Why:** The email skill contains all the patterns and rules. The command's job is to apply them efficiently and deliver.

## Layer 3 — Delivery

**What:** Present the ready-to-send email.
**How:**

For CREATE: Deliver the email with brief guidance notes (tone calibration, personalization suggestions).
For IMPROVE: Deliver before/after with key improvements summarized.

Keep the output clean — the email is the deliverable, not the explanation.

**Why:** The user needs a ready-to-send email, not a writing lesson. Guidance notes should be minimal and practical.
