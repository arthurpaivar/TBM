---
description: Design and write a 6-layer context window for an AI agent (L0-L5), within 40K character budget
allowed-tools: Read, Write, Edit, Grep, Glob, Bash, WebSearch, WebFetch, Task
argument-hint: [agent purpose, domain, and target users — e.g., "technology strategy advisor for IT leaders"]
---

Design and create a context window for $ARGUMENTS using the context-window-specialist skill.

## CRITICAL: 40,000 Character Maximum

The total context window must not exceed **40,000 characters**. Every sentence must earn its place. Plan the token budget before writing.

## CRITICAL: 6-Layer Architecture Required

Every context window must follow the standard 6-layer architecture:
- **L0 Metadata** → L1 Identity → L2 Memory → L3 Execution → L4 Communication Protocol → **L5 Quality Protocol**

No layers may be skipped. No layers may be merged. Each layer covers a distinct, non-overlapping aspect of agent behavior.

## Layer 1 — Context & Intent

**What:** Define what agent we're building a context window for and what it needs to accomplish.
**How:** Parse $ARGUMENTS to extract:
- What domain does this agent operate in?
- Who are the target users?
- What is the agent's primary function?
- What tools or systems will it have access to?
- What autonomy level is expected (fully autonomous, semi-autonomous, always-ask)?

Clarify ambiguity with the user before proceeding. An agent context window with unclear purpose produces inconsistent behavior.
**Why:** The agent's domain, users, and autonomy level determine everything — from how much knowledge to embed (L2) to how strict the guardrails need to be (L5). Getting this wrong means rewriting the entire context window.

## Layer 2 — Knowledge Loading

**What:** Load the context-window-specialist skill and internalize its 6-layer architecture.
**How:** Read the context-window-specialist SKILL.md from this plugin. Extract and structure:
- The 6-Layer Architecture (Section 1) — understand what each layer contains and why the order matters
- The Layer-by-Layer Design Guide (Section 2) — the detailed guidance for writing each layer
- Token Budget Management (Section 3) — the 40K constraint and allocation strategy
- Writing Best Practices (Section 4) — XML structure, clarity, defensive design
- Validation Standards (Section 5) — the quality checks to run before delivery

Separate what you need for design (Sections 1, 3) vs. writing (Sections 2, 4) vs. validation (Section 5).
**Why:** The skill contains the complete methodology for the 6-layer architecture. Loading it properly means you follow proven patterns for each layer.

## Layer 3 — Agent Requirements Discovery

**What:** Deeply understand the agent's requirements before designing the context window.
**How:** Research the agent's domain. For each layer, identify what content is needed:

**For L0 (Metadata):** Agent name, version, domain label, target users
**For L1 (Identity):** Role definition, expertise areas, core principles, persona traits, scope boundaries
**For L2 (Memory):** What domain knowledge does this agent need? What frameworks? What reference data? How much can be embedded vs. searched dynamically?
**For L3 (Execution):** What tools will the agent use? What are the 3-5 most common workflows? What decision logic is needed?
**For L4 (Communication):** What output formats do target users expect? What tone? What structure rules?
**For L5 (Quality):** What are the hard constraints (NEVER do)? What validation rules? What failure modes need error handling?

If the domain requires specialized knowledge, use WebSearch to research before writing L2.
**Why:** A context window is only as good as the requirements behind it. Thin requirements produce a thin agent. This layer ensures you have substance for every layer before writing.

## Layer 4 — Architecture Design & Token Budget

**What:** Plan the 6-layer structure and allocate the 40,000 character budget.
**How:** Following the context-window-specialist's architecture (Section 1) and token budget guidance (Section 3):

1. Determine the budget allocation per layer based on this agent's needs:
   - Default: L0 ~5% | L1 ~15% | L2 ~30% | L3 ~25% | L4 ~10% | L5 ~15%
   - Adjust: Knowledge-heavy agents shift budget to L2. Tool-heavy agents shift to L3. High-risk agents shift to L5.

2. For each layer, outline the key content sections:
   - L0: What metadata fields?
   - L1: What expertise areas? What principles?
   - L2: What knowledge topics (MECE)? Embedded vs. dynamic?
   - L3: What tools? What workflows? What decision rules?
   - L4: What output formats? What tone rules?
   - L5: What hard constraints? What validation rules? What escalation paths?

3. Validate the design: Are the layers MECE? Does the budget add up to ≤40,000 characters?

Present the Context Window Design Brief (from the skill's output patterns) as your design artifact.
**Why:** Designing before writing prevents budget overruns and structural gaps. Once you start writing L2 without a budget, you'll inevitably overshoot and have to cut L5 — the worst layer to shortchange.

## Layer 5 — Content Build

**What:** Write the complete context window following the 6-layer architecture.
**How:** Follow the layer-by-layer design guide from the context-window-specialist (Section 2). Write in order L0 → L5, using XML tags for structure:

1. **L0 — Metadata**: Agent name, version, domain, target users, token allocation, critical constraints summary. Keep minimal (~5%).
2. **L1 — Identity**: Role definition (one sentence), expertise areas, core principles (actionable, not aspirational), persona traits, scope boundaries. ~15%.
3. **L2 — Memory**: Domain knowledge organized in MECE topics, frameworks with enough detail to apply (not just names), reference data, knowledge boundaries. The largest layer ~30%.
4. **L3 — Execution**: Tools with when-to-use guidance, top 3-5 workflows at strategic level, decision logic (act vs. ask), integration points. ~25%.
5. **L4 — Communication Protocol**: 2-4 output format templates, tone calibration rules, structure patterns, interaction guidance. ~10%.
6. **L5 — Quality Protocol**: Hard constraints (NEVER), soft constraints, binary validation rules, error handling for top failure modes, escalation paths, confidence calibration. ~15%.

After writing, count total characters. If over 40,000, apply the cutting priority from the skill: never cut L0 metadata, L1 role, or L5 hard constraints. Trim L2 depth and L4 examples first.
**Why:** The build order follows the architecture — each layer builds on the previous. L1 sets the persona that L2-L5 operate under. L2 provides the knowledge that L3 workflows draw from. L4 formats what L3 produces. L5 governs everything.

## Layer 6 — Quality Validation & Delivery

**What:** Verify the context window meets all standards and deliver it.
**How:** Run the full validation from the context-window-specialist (Section 5):

**Architectural Checks:**
- All 6 layers present (L0-L5)?
- Each layer MECE with the others?
- Total character count ≤ 40,000?
- Token budget allocation appropriate?

**Layer Quality:**
- L0: Metadata complete (name, version, domain, users, allocation)?
- L1: Role definition clear in one sentence? Scope boundaries explicit?
- L2: Knowledge MECE and actionable? Frameworks have enough detail to apply?
- L3: Every tool has when-to-use? Workflows strategic, not tactical?
- L4: 2-4 output templates? Tone calibration specified?
- L5: Hard constraints use NEVER? Validation rules binary? Escalation defined?

**Consistency:**
- L1 principles align with L5 validation rules?
- L3 tools have L5 error handling?
- L4 formats align with L2 knowledge structure?
- No contradictions between layers?

**Character Count Report:**
Include the character count per layer in the delivery confirmation.

Write the context window to the outputs folder. Present the delivery confirmation with layer breakdown.

**Output**: A complete context window document following the 6-layer architecture (L0-L5), within 40,000 characters, delivered with character count breakdown per layer.
