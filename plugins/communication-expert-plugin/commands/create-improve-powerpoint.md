---
description: Create or improve a PowerPoint presentation
allowed-tools: Read, Write, Edit, Grep, Glob, Bash, WebSearch, WebFetch, Task
argument-hint: [presentation topic, context, files, or existing .pptx to improve]
---

Create or improve a presentation for $ARGUMENTS using the powerpoint-specialist skill as the core design engine, orchestrating specialist subagents for content depth, and delivering a production-ready .pptx file.

**This is the flagship command of the communication-expert-plugin. Every presentation must meet JP Morgan design standards and follow the Pyramid Principle. Quality over speed — always.**

## Layer 1 — Context & Intent

**What:** Understand what kind of presentation is needed and from what inputs.
**How:** Parse $ARGUMENTS to extract:
- **Input type**: Theme only? Theme + files? Existing .pptx to improve? Images + context?
- **Audience**: CIO, board, working team, external? (Default: executive if unclear)
- **Purpose**: Strategy, status update, recommendation, training, pitch?
- **Constraints**: Time slot, page count preference, specific requirements?
- If improving an existing .pptx: Read it using the pptx Cowork skill to understand current state

Determine the operating mode:
- **CREATE mode**: No existing deck → build from scratch
- **IMPROVE mode**: Existing .pptx provided → assess and enhance

**Why:** The presentation's success depends on understanding the audience and purpose before designing a single slide. A board deck is fundamentally different from a team status update — the same content requires different structure, density, and tone.

## Layer 2 — Knowledge Loading

**What:** Load all required skills for this presentation.
**How:** Read the following skill files:
1. **powerpoint-specialist** from this plugin — JP Morgan design system, deck sizes, slide architecture, narrative structures
2. **pptx SKILL.md** from `/mnt/.skills/skills/pptx/SKILL.md` — the Cowork pptx creation workflow
3. **pptxgenjs.md** from `/mnt/.skills/skills/pptx/pptxgenjs.md` — JavaScript API for building .pptx files

If improving an existing file, also read:
4. **editing.md** from `/mnt/.skills/skills/pptx/editing.md` — for modifying templates

**Why:** The powerpoint-specialist provides design standards and narrative structure. The pptx technical skill provides the actual file creation machinery. Both are required — design without execution or execution without design both produce poor results.

## Layer 3 — Content Strategy & Specialist Dispatch

**What:** Determine the narrative structure, deck size, and whether specialist subagents are needed for content depth.
**How:**

**Step 1 — Deck Size Selection** (from powerpoint-specialist Section 2):
- One message → Small (Cover + 3)
- One message + second evidence view → Medium (Cover + 4)
- Problem → Analysis → Solution → Action arc → High (Cover + 7)
- Multi-topic → Ultra High (Cover + N)
- **Default to the smallest format that communicates the message.**

**Step 2 — Narrative Structure Selection**:
- Recommendation/finding → Pyramid (answer first, then reasons)
- Executive audience → SCQA (situation, complication, question, answer)
- Transformation proposal → Problem → Solution → Impact

**Step 3 — Content Depth Assessment**:
For each content section, decide if specialist depth is needed. If YES, dispatch subagents using the Task tool:

| Content Need | Subagent Instruction |
|-------------|---------------------|
| Problem decomposition for strategy deck | "Read the problem-solving-specialist skill at [path]. Apply SCQA framing and MECE issue tree to: [topic]. Return: executive summary with situation, complication, question, answer, and top 3 recommendations with evidence." |
| Industry benchmarks for performance deck | "Read the industry-benchmark-specialist skill at [path]. Find benchmarks for: [topic]. Return: benchmark comparison table, gap analysis, and sources with credibility ratings." |
| Research for landscape/trend deck | "Read the deep-search-specialist skill at [path]. Research: [topic]. Return: top 5 findings organized by theme, with sources, credibility ratings, and 1-sentence implications." |
| Financial justification for budget deck | "Read the business-case-specialist skill at [path]. Build a financial case for: [topic]. Return: NPV, payback period, 3-scenario comparison, and executive summary." |

Each subagent receives the specific specialist skill path and returns structured content ready for slide integration.

**Why:** The power of this command is that it doesn't just make slides — it generates the analytical content that belongs on them. A strategy deck without MECE analysis is just opinions on slides. A benchmark deck without sourced data is decoration. The specialist dispatch transforms input themes into substantive, defensible content.

## Layer 4 — Slide-by-Slide Blueprint

**What:** Design the complete slide blueprint before writing any code.
**How:** Build a Presentation Blueprint (from powerpoint-specialist Output Patterns):

For each slide, define:
- **Slide number and title** (message, not label — "Cloud migration saves $3.2M annually" not "Cost Analysis")
- **Layout type**: Cover, executive summary (SCQA), data/evidence, comparison, timeline, action
- **Key message**: The one thing the audience should remember from this slide
- **Content**: Bullets (max 4, max 8 words each), data points, or visual description
- **Visual element**: Chart type, table structure, or diagram (ONE per slide)
- **Source**: Data attribution if applicable
- **Speaker notes**: 30-45 seconds of talking points

Apply JP Morgan Design System throughout:
- Colors: JP Morgan Blue `002D72`, Warm Brown `6C3B2A`, Background `F8F6F3`
- Typography: Georgia for titles, Calibri Light for body
- Content density: Max 4 bullets, 25% whitespace minimum, no decorative elements

**Why:** A blueprint catches structural problems before they become code problems. It's much easier to restructure a text outline than to rebuild JavaScript. The blueprint also serves as a contract — the user can review the plan before execution.

## Layer 5 — Build the .pptx File

**What:** Generate the actual PowerPoint file using PptxGenJS.
**How:** Follow the pptx Cowork skill workflow:

1. **Write the generation script** using PptxGenJS API:
   - Import pptxgenjs: `const pptxgen = require("pptxgenjs")`
   - Create presentation: `const pres = new pptxgen()`
   - Set slide dimensions: `pres.defineLayout({ name: "custom", width: 10, height: 5.625 })`
   - For each slide in the blueprint:
     - Create slide with warm white background: `slide.background = { color: "F8F6F3" }`
     - Add title in Georgia, JP Morgan Blue
     - Add thin separator line below title (0.5pt, `002D72`)
     - Add content elements (text, shapes, tables, charts)
     - Add page number bottom-right (Calibri Light, 10pt, gray)
   - Cover slide: Navy background (`002D72`), white Georgia title
   - **CRITICAL**: Never reuse option objects between API calls — PptxGenJS mutates them. Create fresh objects for each call.

2. **Generate the file**: `pres.writeFile({ fileName: "presentation.pptx" })`

3. **Convert to images for QA**: Follow the pptx skill's conversion workflow to generate slide thumbnails

**Why:** The .pptx file is the final deliverable. PptxGenJS provides programmatic control over every element — fonts, colors, positioning — ensuring the JP Morgan design system is applied precisely, not approximately.

## Layer 6 — Visual Quality Assurance

**What:** Verify the generated presentation meets JP Morgan design standards.
**How:**

1. Convert the .pptx to images (PDF → PNG) following the pptx skill QA workflow
2. Spawn a QA subagent using the Task tool with fresh context:
   - "You are a senior visual QA reviewer for JP Morgan presentations. Review these slide images against these standards: [JP Morgan Design System from powerpoint-specialist Section 1]. Check: color consistency (navy #002D72, warm white #F8F6F3), typography (Georgia titles, Calibri body), layout (0.5\" margins, 25% whitespace), content density (max 4 bullets per slide), one visual per slide, titles state messages not labels. Report issues with severity (Critical/Medium/Minor) and specific fixes needed."

3. Fix any Critical or Medium issues found
4. Re-generate and re-verify if fixes were needed

**Why:** AI-generated presentations often have subtle visual problems — misaligned elements, wrong font sizes, inconsistent spacing. A QA pass with fresh eyes catches what the builder's context misses. JP Morgan standards demand perfection — "good enough" is not acceptable.

## Layer 7 — Delivery

**What:** Deliver the final .pptx file with a concise summary.
**How:**

1. Copy the final .pptx to the outputs folder
2. Present with a brief summary following the Communication Protocol:

**Opening (So-What)**: What was created and the core narrative
- "[Deck size] presentation on [topic] for [audience]. Core message: [the answer/recommendation]."

**Body (Structure)**: Quick slide-by-slide summary
- "Cover → [Slide 1 message] → [Slide 2 message] → ... → [Action slide message]"

**Conclusion (Guidance)**: Practical notes
- Design system applied, speaker notes included, any areas for personalization

3. Provide the file link for download

**Why:** The delivery should be as polished as the presentation itself. A clean summary helps the user understand what was built and how to use it. The file is the star — not the explanation.

## CRITICAL CONSTRAINTS

**Subagent orchestration**: When dispatching specialist subagents via the Task tool, each subagent MUST receive:
1. The full path to the specialist skill file to read
2. A specific, well-scoped task description
3. Clear output format expectations
Subagents are independent — they don't share context. Give them everything they need.

**Design non-negotiables**:
- JP Morgan color palette — no bright, saturated colors ever
- Georgia titles + Calibri Light body — no substitutions
- Warm white background (`F8F6F3`) — never pure white
- Maximum 4 bullets per slide, 8 words per bullet
- One visual element per slide
- 25% whitespace minimum
- No animations, transitions, or decorative elements
- Slide titles state messages, not labels

**Quality gate**: No presentation ships without visual QA. If QA finds Critical issues, fix and re-verify.

**Deck size discipline**: Always prefer the smallest format. A 3-slide deck that communicates clearly beats an 8-slide deck that dilutes the message. When in doubt, fewer slides.
