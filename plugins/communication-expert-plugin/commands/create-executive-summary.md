---
description: Create a concise executive summary from content or topic
allowed-tools: Read, Write, Edit, Grep, Glob, Bash, WebSearch, WebFetch, Task
argument-hint: [content, document, or topic to summarize]
---

Create an executive summary for $ARGUMENTS using the text-improver-specialist and e-mail-generator skills for structure and tone.

**This command produces a 1-page executive summary following the SCQA pattern. Content in → structured executive brief out.**

## Layer 1 — Input & Extraction

**What:** Parse the input and extract the key messages.
**How:** Parse $ARGUMENTS — may be inline text, a file path, uploaded document, or a topic requiring research.
- Read the text-improver-specialist skill from this plugin (for structuring and refining)
- Read the e-mail-generator skill from this plugin (for executive tone and BLUF patterns)
- If input is a document: extract key messages, decisions, data points, and action items
- If input is a topic: use WebSearch to gather current information, then synthesize

Identify:
- The core recommendation or finding (the So-What)
- The 3-5 supporting evidence points
- The required decision or action
- The audience (default: executive)

**Why:** An executive summary is not a shorter version of the document — it's the distilled answer. Finding the So-What before writing ensures the summary leads with it.

## Layer 2 — Structure & Write

**What:** Write the executive summary following SCQA.
**How:**

Apply the SCQA pattern:
1. **Situation** (2-3 sentences): Current state, what's established
2. **Complication** (2-3 sentences): What changed, why action is needed
3. **Question** (implied or explicit): What must be decided
4. **Answer** (the bulk): Recommendation with supporting evidence

Apply text-improver-specialist principles:
- Active voice, no hedging, data-driven
- Maximum 1 page
- BLUF in the opening sentence
- Specific next steps with owners and deadlines

Apply executive tone from e-mail-generator:
- Concise, strategic, risk-aware
- Decision format clear
- No filler, no redundancy

**Why:** SCQA creates a narrative arc that executives recognize and trust. It answers "why now?" (complication) before "what to do?" (answer).

## Layer 3 — Delivery

**What:** Deliver the executive summary.
**How:**

Output the executive summary — clean, formatted, ready to use.
- Note the SCQA structure applied
- Flag any areas where additional data or human judgment would strengthen the summary
- If source material was provided, note what was prioritized and what was omitted

The summary is the deliverable. Keep meta-commentary minimal.

**Why:** An executive's time is the scarcest resource. The summary should respect that with precision and brevity.
