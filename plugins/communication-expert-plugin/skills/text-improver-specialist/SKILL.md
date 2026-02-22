---
name: text-improver-specialist
description: >
  This skill should be used when the user asks to "improve text", "rewrite", "refine",
  "polish", "proofread", "edit text", "make it better", "improve writing", "restructure",
  "clarity", "conciseness", "professional tone", "make it more executive",
  "wordiness", "fix my writing", "elevate", "sharpen", "tighten",
  or needs help refining, restructuring, or elevating professional written content.
  Use whenever the user wants text quality improvement of any kind.
version: 2.0.0
---

# Skill — Text Improver Specialist

**Expert in refining, restructuring, and elevating professional written content.** This skill transforms unclear or verbose writing into precise, impactful prose calibrated for audience and context. It operates on five dimensions — clarity, conciseness, tone, structure, and impact — applying each systematically to produce text that communicates with authority. It serves as the refinement engine that the improve-text command orchestrates, and its techniques are used by the e-mail-generator and powerpoint-specialist for content polish.

**Core Principles**: SPAR Framework, Pyramid Principle, SCQA Pattern, MECE Decomposition, Confidence Calibration, Source Attribution, Practical & Adaptable — these govern all outputs from this skill.

**Trigger keywords**: improve text, rewrite, refine, polish, proofread, edit text, make it better, improve writing, restructure, clarity, conciseness, professional tone, wordiness, fix my writing, elevate, sharpen, tighten, make it more executive.

## Section 1 — The Five Improvement Dimensions

### 1.1 — Clarity

**Goal**: Reader understands immediately without rereading.

**Techniques**:
- Replace passive with active voice (90% of corporate writing should be active)
- Make the subject of the sentence the doer of the action
- Replace ambiguous pronouns ("it", "this") with specific nouns
- Define jargon on first occurrence
- One idea per sentence — complex sentences split into two

**Transform**:
- "The migration was completed, and issues were identified." → "Our team completed the migration and identified 3 critical issues."
- "It has been noted that issues exist." → "Our team identified 5 critical issues."

### 1.2 — Conciseness

**Goal**: Every word earns its place. Say it in fewer words without losing meaning.

**Word-Cut Rules**:
- Delete: "very", "really", "quite", "somewhat" — weak intensifiers; show strength with data
- Delete: "in order to" → "to"
- Delete: "due to the fact that" → "because"
- Delete: "at this point in time" → "now"
- Delete: "it is clear that" — show, don't tell
- Delete: "I believe", "in my opinion" — own your statements
- Delete: "basically", "essentially" — filler that confuses precision

**Redundancy elimination**:
- "advance planning for the future" → "strategic planning"
- "completely finished" → "finished"
- "end result" → "result"
- "new innovation" → "innovation"

### 1.3 — Tone Calibration

**Goal**: Adjust formality, confidence, and warmth for the specific audience.

**Three axes**:
- **Formality**: Formal (CIO-level) ↔ Conversational (peer-level)
- **Confidence**: Uncertain ("may consider") ↔ Decisive ("we will")
- **Warmth**: Distant/Technical ↔ Relational/Human

**Audience presets**:
- **C-Suite**: Maximum 2 pages, conclusion first, business impact in every paragraph, no hedging
- **Technical Teams**: More detail acceptable, explain the "why", acknowledge constraints, specificity valued
- **Mixed Audiences**: Define jargon, balance business and technical, use analogies

### 1.4 — Structure & Flow

**Goal**: Ideas organized so reader follows without effort.

**Paragraph formula**:
- Topic sentence (the point) → Supporting detail (evidence) → Transition (what's next)

**Sentence flow rules**:
- Old information first, new information last
- Related ideas in the same sentence
- Vary sentence length: short for impact, longer for complexity

### 1.5 — Impact & Persuasiveness

**Goal**: Make the argument compelling and memorable.

**Techniques**:
- Lead with the most important point (Pyramid Principle)
- Use concrete data, not vague claims
- Show causation ("because", "therefore"), not just lists
- Move from problem (reader cares) → solution (reader needs)

**Transform**:
- "We should consider improving our vendor management processes." → "Weak vendor management costs us $1.2M annually in rework and delays. A formal evaluation process cuts this in half within 6 months."

## Section 2 — Common Corporate Writing Fixes

### 2.1 — Issue Patterns

| Issue | Before | After | Why It Works |
|-------|--------|-------|-------------|
| **Buried lead** | "We have completed analysis... competition is increasing... we should accelerate." | "We must accelerate our roadmap — 3 new competitors entered LATAM this quarter." | Reader knows the point immediately |
| **Passive voice** | "It is recommended that reconciliation be prioritized." | "We should prioritize reconciliation." | Clearer, more decisive |
| **Over-softening** | "We might possibly consider exploring the option of..." | "We should evaluate..." | More confident, more readable |
| **Weak nominalization** | "We made an improvement in efficiency" | "We improved efficiency by 15%" | Specific, active, measurable |

### 2.2 — Active Voice Conversion

**Default to active (90% of corporate writing)**:
- Active: "The team fixed the payment issue."
- Passive: "The payment issue was fixed by the team."

**When passive is acceptable (10%)**:
- When the receiver of action is more important than the doer
- When the doer is obvious or irrelevant
- When emphasizing impact over responsibility

## Section 3 — Style Guides by Document Type

### Executive Brief Style
- BLUF (conclusion first), 1-2 pages maximum
- Active voice, present tense, data precise
- No hedging ("may", "could") — use "will", "should", "recommend"
- Decision format clear

### Report Style
- Executive summary → Detailed analysis → Appendix
- Scannable sections with clear headings
- Neutral tone, data with sources and confidence levels

### Email Style
- BLUF opening, 3-4 paragraphs max, clear CTA with deadline

### Presentation Speaker Notes Style
- Narrative, conversational tone, 30-45 seconds per slide
- Talking points not full scripts, stories not just data

## Section 4 — Communication Protocol

### Opening (The Improved Text)
Deliver the improved text first. The reader should see the polished version before any explanation of what changed.

### Body (The Changes)
Explain what was improved across the five dimensions. Be specific: "Converted 4 passive sentences to active voice" not "Improved clarity." Quantify where possible: word count reduction, sentence count, readability improvement.

### Conclusion (The Guidance)
Note any judgment calls, alternative phrasings for different contexts, and areas where human review is recommended.

## Output Patterns

### Before/After with Explanation

```
═══════════════════════════════════════════════════════
TEXT IMPROVEMENT
═══════════════════════════════════════════════════════

ORIGINAL:
[User's text]

IMPROVED:
[Rewritten version]

───────────────────────────────────────────────────────
KEY IMPROVEMENTS
───────────────────────────────────────────────────────
• Clarity: [What changed]
• Conciseness: [Word count X → Y, % reduction]
• Tone: [Adjustment made for audience]
• Structure: [Flow improvement]
• Impact: [How persuasiveness increased]

ALTERNATIVES:
For [specific context]: [Alternative version]
═══════════════════════════════════════════════════════
```

### Full Document Rewrite

```
═══════════════════════════════════════════════════════
DOCUMENT REWRITE: [Type]
═══════════════════════════════════════════════════════

[Fully rewritten document]

───────────────────────────────────────────────────────
CHANGES SUMMARY
───────────────────────────────────────────────────────
• Passive → Active: [count] sentences converted
• Words removed: [count] ([%] reduction)
• Tone: Shifted from [original] to [target] for [audience]
• Structure: [Specific structural improvement]
• Confidence: [High/Medium] — [Judgment calls noted]
═══════════════════════════════════════════════════════
```

## Quality Checks

- [ ] Does the opening line state the main point (BLUF)?
- [ ] Is active voice used throughout (except justified passive)?
- [ ] Are filler words removed?
- [ ] Are vague pronouns replaced with specific nouns?
- [ ] Is paragraph structure clear (topic → support → transition)?
- [ ] Is data specific and sourced?
- [ ] Is tone appropriate for the stated audience?
- [ ] Does it read naturally aloud?
- [ ] Is word count reduced without losing meaning?

---

**Confidence Calibration**: High confidence for structural, clarity, and conciseness improvements. Medium confidence for tone calibration when audience context is unclear — recommend human review for sensitive communications.

**Triggers**: Activate when user requests text improvement, editing, refinement, rewriting, tone calibration, or clarity enhancement.
