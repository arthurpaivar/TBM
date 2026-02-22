---
name: powerpoint-specialist
description: >
  This skill should be used when the user asks about "presentation", "slide", "slides",
  "deck", "pitch", "powerpoint", "pptx", "slide structure", "executive presentation",
  "slide design", "board deck", "QBR", "quarterly review", "strategy deck",
  "presentation outline", "keynote", "slide content", "deck design",
  "JP Morgan presentation", "McKinsey slides", "consulting deck",
  or needs help structuring, designing, and creating presentation content.
  Also used internally by the create-improve-powerpoint command as the core
  presentation knowledge base. Use whenever the user mentions creating or improving
  a presentation or deck.
version: 2.0.0
---

# Skill — PowerPoint Specialist

**Expert in structuring, designing, and creating executive presentations following JP Morgan design standards and top-tier consulting methodologies (McKinsey, BCG, Bain).** This skill produces clear, understated, visually refined slide decks that communicate strategy, data, and recommendations with precision and authority. Every presentation follows the Pyramid Principle — leading with the answer, supporting with evidence, concluding with actionable insight. It serves as the core presentation knowledge base that the create-improve-powerpoint command orchestrates, and it can invoke skills from consulting-expert-plugin (problem-solving, benchmarking, deep search) and technology-expert-plugin (strategy, architecture) for content depth.

**Core Principles**: SPAR Framework, Pyramid Principle, SCQA Pattern, MECE Decomposition, Confidence Calibration, Source Attribution, Practical & Adaptable — these govern all outputs from this skill.

**Trigger keywords**: presentation, slide, slides, deck, pitch, powerpoint, pptx, slide structure, executive presentation, slide design, board deck, QBR, strategy deck, presentation outline, keynote, JP Morgan presentation, McKinsey slides, consulting deck.

## Section 1 — JP Morgan Design System

### 1.1 — Color Palette

The design philosophy is **understated authority** — colors support the message without competing for attention. Light, warm, institutional.

**Primary Palette:**

| Role | Color | Hex | Usage |
|------|-------|-----|-------|
| **JP Morgan Blue** (Primary) | Deep Navy | `002D72` | Titles, key headers, cover slide background, accent lines |
| **JP Morgan Warm** (Secondary) | Warm Brown | `6C3B2A` | Section headers, secondary accents, category labels |
| **Background Light** | Warm White | `F8F6F3` | Content slide backgrounds — never pure white |
| **Background Dark** | Deep Navy | `002D72` | Cover and conclusion slide backgrounds |
| **Text Primary** | Charcoal | `2D2D2D` | Body text, descriptions |
| **Text Secondary** | Medium Gray | `6B7280` | Footnotes, captions, supporting text |

**Accent Colors (use sparingly):**

| Role | Color | Hex | Usage |
|------|-------|-----|-------|
| **Positive/Success** | Muted Teal | `0D7377` | Upward trends, positive metrics, checkmarks |
| **Caution** | Warm Amber | `B8860B` | Warnings, attention items (never bright yellow) |
| **Negative/Risk** | Muted Burgundy | `8B2252` | Downward trends, risks (never bright red) |
| **Neutral** | Slate Blue | `4A6FA5` | Charts, data series, neutral information |

**Design Rules:**
- Never use bright, saturated colors — they feel aggressive and unprofessional
- Background should be warm white (`F8F6F3`) or very light gray — never stark white (`FFFFFF`)
- Maximum 3 colors visible on any single slide (excluding text colors)
- Charts use the JP Morgan Blue + Slate Blue + Muted Teal palette
- All colors should feel like they belong in a room with mahogany furniture

### 1.2 — Typography

| Element | Font | Size | Style |
|---------|------|------|-------|
| **Slide Title** | Georgia or Calibri | 36-40pt | Bold, JP Morgan Blue |
| **Section Header** | Calibri | 20-24pt | Bold, JP Morgan Warm |
| **Body Text** | Calibri Light | 14-16pt | Regular, Charcoal |
| **Data Labels** | Calibri | 12-14pt | Regular, Medium Gray |
| **Footnotes** | Calibri Light | 9-10pt | Italic, Medium Gray |
| **Cover Title** | Georgia | 40-44pt | Bold, White on navy |
| **Cover Subtitle** | Calibri Light | 18-20pt | Regular, Light gray on navy |

**Font Pairing:** Georgia (titles — serif for authority) + Calibri Light (body — clean, modern). If Georgia unavailable, use Calibri Bold for titles.

### 1.3 — Layout Grid

- **Margins**: 0.5" on all sides (sacred — never violate)
- **Content area**: 9" × 4.625" (within a 10" × 5.625" slide)
- **Title zone**: Top 0.8" of slide
- **Footer zone**: Bottom 0.4" (page number, date, confidentiality)
- **Whitespace**: Minimum 25% of each slide should be empty space — breathing room signals confidence
- **Alignment**: Left-align body text always. Center only titles and cover elements.

### 1.4 — Visual Motif

**Consistent across all slides:**
- Thin horizontal line (`002D72`, 0.5pt) below slide title — separates title from content
- Page number bottom-right (Calibri Light, 10pt, Medium Gray)
- No logos on content slides (logo only on cover and conclusion)
- No accent lines under elements (hallmark of AI-generated slides — avoid)
- Cards/boxes use subtle shadow (outer, blur: 4, offset: 1, opacity: 0.10) instead of borders

## Section 2 — Deck Size Framework

Every presentation should use the smallest format that communicates the message. More slides dilute impact. Each slide earns its place by delivering exactly one message.

### 2.1 — Small Deck (Cover + 3 Slides)

**Total: 4 slides.** The default. Use for most internal communications.

| Slide | Purpose | Content |
|-------|---------|---------|
| **Cover** | Set context | Title, subtitle, date, presenter |
| **Slide 1** | The So-What | Executive summary — recommendation or key finding (SCQA) |
| **Slide 2** | The Evidence | Supporting analysis — data, comparison, or issue tree |
| **Slide 3** | The Action | Next steps, timeline, decision required |

**When to use:** Status updates, single-topic briefings, approval requests, quick recommendations.

### 2.2 — Medium Deck (Cover + 4 Slides)

**Total: 5 slides.** When the evidence needs one more supporting slide.

| Slide | Purpose | Content |
|-------|---------|---------|
| **Cover** | Set context | Title, subtitle, date, presenter |
| **Slide 1** | The So-What | Executive summary (SCQA) |
| **Slide 2** | Evidence A | Primary supporting analysis |
| **Slide 3** | Evidence B | Secondary supporting analysis or comparison |
| **Slide 4** | The Action | Next steps, timeline, decision required |

**When to use:** Strategy updates, vendor comparisons, budget proposals, performance reviews.

### 2.3 — High Deck (Cover + 7 Slides)

**Total: 8 slides.** For comprehensive topics requiring multiple evidence layers.

| Slide | Purpose | Content |
|-------|---------|---------|
| **Cover** | Set context | Title, subtitle, date, presenter |
| **Slide 1** | Executive Summary | SCQA — the complete answer in one slide |
| **Slide 2** | Situation & Context | Current state, what's driving this |
| **Slide 3** | Problem / Opportunity | The complication — why action is needed |
| **Slide 4** | Analysis / Evidence | Core analytical finding (issue tree, benchmark, data) |
| **Slide 5** | Options / Comparison | Options evaluated, recommendation highlighted |
| **Slide 6** | Roadmap / Timeline | Implementation plan, milestones |
| **Slide 7** | Risks & Mitigation | Top risks with mitigation strategies |
| **Slide 8** | Decision & Next Steps | Specific ask, owners, timeline |

**When to use:** QBRs, transformation proposals, board-level briefings, investment cases.

### 2.4 — Ultra High Deck (Cover + N Slides)

**Total: Cover + as many as needed.** Only for complex, multi-topic sessions.

Structure: Cover → Executive Summary → Topic sections (each following its own Small/Medium structure) → Consolidated Next Steps → Appendix.

**When to use:** Annual planning, multi-workstream reviews, offsite agendas. Default to High or below — Ultra High requires justification.

### 2.5 — Deck Size Selection Logic

```
Is there ONE message to communicate?
├── YES → Small (Cover + 3)
│   └── Does the evidence need a second supporting view?
│       ├── NO → Small (Cover + 3)
│       └── YES → Medium (Cover + 4)
└── NO → Is there a natural Problem → Analysis → Solution → Action arc?
    ├── YES → High (Cover + 7)
    └── NO → Ultra High (Cover + N) — structure as modular sections
```

**Golden rule:** When in doubt, choose the smaller format. You can always add slides if asked — you can never un-bore an audience.

## Section 3 — Slide Architecture

### 3.1 — The One-Message Rule

Every slide communicates exactly ONE message. The slide title IS the message — not a label.

**Labels (weak):** "Q3 Performance" / "Cost Analysis" / "Risk Assessment"
**Messages (strong):** "Q3 volume up 23%, driven by new partnerships" / "Cloud migration saves $3.2M annually" / "Vendor delay is the critical risk — mitigation in place"

**Test:** Cover the slide body. Can the audience understand the key point from the title alone? If yes, the title works. If no, rewrite it.

### 3.2 — Slide Types

**Cover Slide:**
- Dark background (JP Morgan Blue `002D72`)
- White title text (Georgia, 40-44pt)
- Light subtitle (Calibri Light, 18-20pt, light gray)
- Date, presenter name, confidentiality notice
- No bullet points, no body text — clean and authoritative

**Executive Summary Slide (SCQA):**
- Warm white background
- Four clearly labeled sections: Situation, Complication, Question, Answer
- Answer section visually emphasized (slightly larger, bolder, or with subtle background card)
- Should be standalone — an executive who reads only this slide should understand everything

**Data / Evidence Slide:**
- ONE chart or data visualization per slide
- Title states the insight, not the topic
- Source citation in footnote
- Chart uses JP Morgan Blue palette — no rainbow charts

**Comparison / Options Slide:**
- Table or card layout
- Recommended option visually distinguished (subtle highlight, star marker)
- MECE criteria in rows, options in columns
- Consistent scoring throughout

**Timeline / Roadmap Slide:**
- Horizontal flow, left to right
- Phases with clear milestones
- Current state marker if showing progress
- Dependencies shown if critical

**Action / Decision Slide:**
- Clear recommendation statement
- Specific decision format ("Approve / Defer / Reject")
- Owner and deadline for each next step
- This slide should create urgency to act

### 3.3 — Narrative Structures

**Structure A — Pyramid (Default):**
```
Slide 1: Answer (recommendation/finding)
Slide 2: Reason 1 (strongest supporting argument)
Slide 3: Reason 2 (second strongest)
Slide 4: Next Steps (action)
```

**Structure B — SCQA (for executive audiences):**
```
Slide 1: Situation + Complication
Slide 2: Question + Answer
Slides 3-N: Evidence
Final Slide: Action
```

**Structure C — Problem → Solution → Impact (for transformation proposals):**
```
Slides 1-2: Problem (current state, what's broken, why it matters)
Slides 3-4: Solution (what we propose, how it works)
Slides 5-6: Impact (outcomes, timeline, investment)
Slide 7: Action (decision needed)
```

## Section 4 — Content Density Rules

### 4.1 — The Restraint Principle

Less content per slide = more impact per message. JP Morgan presentations should feel like they're communicating important things calmly — never shouting.

- **Maximum 4 bullet points per slide** (not 6 — that's too many for executive attention)
- **Maximum 8 words per bullet** (distill to the essential)
- **One visual element per slide** (chart, table, or diagram — never two)
- **Whitespace is content** — empty space signals confidence and authority
- **No animations, transitions, or decorative elements** — they diminish credibility

### 4.2 — Data Presentation

- **Headlines, not data dumps**: "Cost reduced 32% YoY" not a table of 12 months
- **Comparison over absolute**: "2x faster than industry average" is more powerful than "450ms latency"
- **Round numbers for strategy**: "$3.2M" not "$3,187,421" — precision isn't always accuracy
- **Source everything**: Small footnote with source and date — builds trust silently

## Section 5 — Cross-Plugin Orchestration

### When to Invoke Other Skills

The PowerPoint command orchestrates content depth by dispatching subagents:

| Content Need | Specialist to Invoke | What They Produce |
|-------------|---------------------|-------------------|
| Problem decomposition for a strategy deck | problem-solving-specialist (consulting) | SCQA framing, issue tree, options analysis |
| Industry benchmarks for a performance review | industry-benchmark-specialist (consulting) | Peer comparison data, gap analysis, sources |
| Research for a landscape or trend deck | deep-search-specialist (consulting) | Curated findings, source-attributed insights |
| Financial justification for a budget deck | business-case-specialist (consulting) | NPV/IRR analysis, scenario comparison |
| Technology strategy context | tech-strategy-advisory (technology) | Framework context, transformation patterns |
| Architecture assessment for a tech deck | architecture-specialist (technology) | Architecture patterns, trade-off analysis |
| Cost allocation for a budget deck | tech-bm-specialist (finance) | TBM taxonomy, cost transparency data |

### Orchestration Pattern

1. User provides context (theme, files, question)
2. Command determines deck type and narrative structure
3. For each content section needing depth → dispatch specialist subagent
4. Specialist returns structured analysis → transform into slide content
5. Apply JP Morgan design system → build actual .pptx file
6. Visual QA → refine → deliver

## Section 6 — Communication Protocol

### Opening (Cover + Executive Summary)
The first two things the audience sees must communicate the complete answer. The cover sets the stakes. The executive summary delivers the So-What. An executive who leaves after slide 2 should still understand the recommendation.

### Body (Evidence Slides)
Each slide supports the opening with one piece of evidence. Ordered by importance, not chronology. Every slide earns its place — if removing a slide doesn't weaken the argument, remove it.

### Conclusion (Action Slide)
End with clarity and urgency. What decision is needed? Who decides? By when? What happens next? The audience should leave knowing exactly what to do.

## Section 7 — Technical Integration

### Creating the Actual .pptx File

This skill provides the strategic and design knowledge. The actual file creation uses the **pptx Cowork skill** (at `/mnt/.skills/skills/pptx/`):

1. Read `pptx/SKILL.md` for the creation workflow
2. Read `pptx/pptxgenjs.md` for the JavaScript API
3. Apply the JP Morgan design system (Section 1) to the pptxgenjs code
4. Use `pptx/editing.md` if modifying an existing template

**Key technical mappings:**
- JP Morgan Blue → `fill: { color: "002D72" }` (no # prefix)
- Warm White background → `slide.background = { color: "F8F6F3" }`
- Georgia titles → `fontFace: "Georgia"`
- Subtle shadows → `shadow: { type: "outer", blur: 4, offset: 1, color: "000000", opacity: 0.10 }`
- Never reuse option objects between calls (PptxGenJS mutates them)

**QA process:**
- Convert to PDF then images for visual inspection
- Use a subagent with fresh eyes for visual QA
- Fix and re-verify until clean

## Output Patterns

### Slide-by-Slide Blueprint

```
═══════════════════════════════════════════════════════
PRESENTATION BLUEPRINT: [Title]
═══════════════════════════════════════════════════════

FORMAT: [Small/Medium/High/Ultra High] ([N] slides)
AUDIENCE: [CIO/Board/Working Team]
NARRATIVE: [Pyramid/SCQA/Problem-Solution-Impact]

───────────────────────────────────────────────────────

SLIDE 0 — COVER
Background: JP Morgan Blue (#002D72)
Title: [Compelling title — message, not label]
Subtitle: [Context — date, meeting type]
Presenter: [Name, role]

───────────────────────────────────────────────────────

SLIDE 1 — [TITLE AS MESSAGE]
Layout: [Type — executive summary / data / comparison / timeline / action]
Key Message: [The one thing the audience should remember]

Content:
• [Bullet 1]
• [Bullet 2]
• [Bullet 3]

Visual: [Chart type / table / diagram description]
Source: [Data source if applicable]

Speaker Notes: [30-45 seconds of talking points]

───────────────────────────────────────────────────────

[... continues for each slide]

───────────────────────────────────────────────────────
DESIGN NOTES
───────────────────────────────────────────────────────
Palette: JP Morgan Blue + Warm White + [accent if needed]
Typography: Georgia titles / Calibri Light body
Special elements: [Any charts, diagrams, or visuals needed]
═══════════════════════════════════════════════════════
```

### Quick Deck Outline

```
DECK OUTLINE: [Title] | [N] slides | [Audience]

Cover: [Title]
S1: [Message — slide type]
S2: [Message — slide type]
S3: [Message — slide type]
...

NARRATIVE ARC: [1-sentence description of the story]
```

## Quality Checks

- [ ] Does the deck use the smallest size that communicates the message?
- [ ] Does every slide title state a message (not a label)?
- [ ] Does the executive summary slide work standalone?
- [ ] Is the JP Morgan color palette applied consistently?
- [ ] Are there maximum 4 bullets per slide, 8 words per bullet?
- [ ] Is whitespace at least 25% of each slide?
- [ ] Does the conclusion slide create urgency to act?
- [ ] Would a McKinsey partner present this with confidence?
- [ ] Is the .pptx file visually clean (QA verified with images)?

---

**Confidence Calibration**: High confidence for deck structure, narrative design, and JP Morgan design standards. Medium confidence for domain-specific content — recommend invoking specialist subagents for technical depth. High confidence for pptxgenjs integration when following the technical skill guide.

**Triggers**: Activate when user requests presentation creation, slide design, deck structuring, or presentation improvement. Also activated internally by the create-improve-powerpoint command as the core presentation engine.
