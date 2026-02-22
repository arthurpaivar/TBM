---
description: Provide technology strategy advisory using consulting frameworks
allowed-tools: Read, WebSearch, WebFetch
argument-hint: "[strategy topic — e.g., 'cloud migration strategy for payments', 'build vs buy for fraud detection']"
---

Provide technology strategy advisory for $ARGUMENTS using the tech-strategy-advisory skill.

## Layer 1 — Context & Intent

**What:** Define the strategic question, decision, or transformation challenge being addressed.
**How:** Parse $ARGUMENTS to extract:
- What's the strategic question? (technology direction, investment decision, transformation roadmap, operating model design)
- What's the business context? (competitive pressure, regulatory change, cost optimization, growth enablement)
- Who's the audience? (CIO, executive committee, board, technology leadership)
- What consulting-grade deliverable is needed? (strategy brief, options analysis, business case, TOM canvas, roadmap)

If the topic also requires deep technical knowledge (architecture patterns, delivery practices, AI capabilities), identify which specialist skills to cross-reference.
**Why:** Strategy advisory is the highest-stakes output this plugin produces. The CIO uses it for investment decisions and executive conversations. Getting the intent right prevents misaligned recommendations that could lead to poor decisions.

## Layer 2 — Knowledge Loading

**What:** Load the tech-strategy-advisory skill and extract the relevant consulting frameworks.
**How:** Read the tech-strategy-advisory SKILL.md. Extract based on the strategic question type:
- For transformation: McKinsey 3Ds, BCG Transformation phases, Accenture Reinvention (Sections 1-3)
- For strategic planning: Three Horizons, capability mapping, value stream mapping (Section 4)
- For investment decisions: Build vs. Buy vs. Partner, business case structure (Section 4.6-4.7)
- For operating model: TOM design, product operating model (Section 4.1-4.2)
- For governance: Governance framework, investment categories (Section 5)
- For benchmarks: Industry data points (Section 6)

If the strategy requires technical depth, also load the relevant specialist skill (architecture-specialist for modernization strategies, ai-specialist for AI strategy, etc.).
**Why:** Top-tier consulting firms don't improvise — they apply proven frameworks. Loading the right framework ensures the advisory is rigorous, structured, and credible at the CIO level.

## Layer 3 — Strategic Analysis

**What:** Apply the consulting framework to produce structured strategic analysis.
**How:** Use the SCQA pattern (Situation → Complication → Question → Answer) as the backbone:

1. **Situation**: Current state, market context, competitive positioning. Use industry benchmarks from Section 6
2. **Complication**: Why the current approach is insufficient. What's changed or what's at risk
3. **Question**: The strategic question the CIO needs to answer
4. **Answer**: The recommended direction — lead with the answer (Pyramid Principle)

Then deepen with:
5. **Options Analysis**: 3-4 options with pros/cons/costs/risks (MECE)
6. **Recommendation**: Selected option with clear rationale
7. **Implementation Roadmap**: Quick wins (0-3mo), Scale (3-12mo), Transform (12-36mo)
8. **Investment**: Run/Grow/Transform allocation with industry benchmarks
9. **Governance**: Which decision bodies approve what, and when

If the strategy involves emerging technologies or rapidly changing markets, use WebSearch to enrich with current data points.
**Why:** The SCQA + Options Analysis structure is the consulting industry standard. CIOs who've worked with McKinsey, BCG, or Accenture expect this structure. Delivering it builds credibility and makes the advisory immediately usable in executive conversations.

## Layer 4 — Delivery & Confidence

**What:** Finalize the strategic advisory with confidence calibration and source attribution.
**How:**
1. Apply quality checks from the tech-strategy-advisory skill
2. Calibrate confidence for each recommendation (High/Medium/Low with rationale)
3. Attribute all benchmarks and frameworks to their sources (Gartner, McKinsey, BCG, etc.)
4. Note any assumptions that could change the recommendation
5. Suggest follow-up actions or decisions that need to be made

Structure the final output using the Technology Strategy Advisory output pattern from the skill.
**Why:** Strategy advisory without confidence calibration is dangerous — the CIO needs to know which recommendations are well-grounded and which carry uncertainty. Source attribution adds credibility and allows the CIO to dig deeper on specific data points.

**Output**: A consulting-grade technology strategy advisory following the SCQA structure with options analysis, recommendation, implementation roadmap, investment allocation, and governance guidance. Structured using the Pyramid Principle with confidence calibration and source attribution. Ready for CIO-level conversations.
