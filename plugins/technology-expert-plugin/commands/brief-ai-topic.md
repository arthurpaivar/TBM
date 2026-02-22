---
description: Create an AI briefing for CIO-level conversations
allowed-tools: Read, WebSearch, WebFetch
argument-hint: "[AI topic — e.g., 'AI agents in payments operations', 'EU AI Act compliance', 'MCP adoption strategy']"
---

Create an AI briefing for $ARGUMENTS using the ai-specialist skill.

## Layer 1 — Context & Intent

**What:** Define the AI topic and the briefing purpose.
**How:** Parse $ARGUMENTS to extract:
- What AI domain? (agents, MCP, governance/regulation, use cases, ROI, strategy, operations)
- What's the briefing purpose? (inform the CIO, prepare for a meeting, evaluate an opportunity, assess risk)
- What level of depth? (overview for awareness, deep-dive for decision-making, comparison for vendor selection)
- What's the payments/financial services angle? (fraud, AML, operations, customer service, developer productivity)
**Why:** AI is broad. A briefing on "AI agents" for awareness is very different from one for "evaluating an AI agent vendor." Clarifying intent ensures the right depth and framing.

## Layer 2 — Knowledge Loading

**What:** Load the ai-specialist skill and extract relevant AI domain knowledge.
**How:** Read the ai-specialist SKILL.md. Extract based on the AI domain:
- For agents: Agent architecture patterns, capabilities, evaluation framework (Section 1)
- For MCP: Architecture, capabilities, adoption timeline, enterprise considerations (Section 2)
- For context/RAG/fine-tuning: Context window management, RAG, approach comparison (Section 3)
- For strategy: Use case prioritization, payments use cases, ROI framework, operating model (Section 4)
- For governance: SR 11-7, EU AI Act, NIST AI RMF, responsible AI principles (Section 5)
- For benchmarks: Industry data points, DORA AI findings (Section 6)

If the topic also requires strategic framing, cross-reference with `tech-strategy-advisory` for Three Horizons or business case structure.
**Why:** The ai-specialist skill contains the deep, curated AI knowledge. Loading specific sections prevents information overload and ensures the briefing is focused on what the CIO needs.

## Layer 3 — Briefing Construction

**What:** Build the AI briefing using the SCQA pattern for executive consumption.
**How:** Follow the AI Executive Briefing output pattern:

1. **Situation**: Current state of this AI area in the industry — adoption levels, key players, maturity
2. **Complication**: Why this matters now for a Payments CIO — regulatory pressure, competitive dynamics, opportunity cost
3. **Question**: The strategic question the CIO should be asking about this topic
4. **Answer**: Recommended position — lead with the answer (Pyramid Principle)

Then deepen with:
5. **Maturity Assessment**: Where the industry is, where we are (or assessment criteria), the gap
6. **Payments-Specific Use Cases**: 3-5 relevant use cases from Section 4.2, each with readiness level (Production/Emerging/Experimental)
7. **Governance Implications**: Which regulatory frameworks apply, what they require
8. **Recommendation**: Short-term (0-6mo), Medium-term (6-18mo), Long-term (18-36mo) actions

Use WebSearch to enrich with the latest AI developments — this field moves weekly, and the CIO may have seen recent headlines.
**Why:** CIO briefings must be structured, not streams of consciousness. The SCQA pattern is proven for executive consumption — it respects their time by leading with the answer and providing supporting detail in a predictable structure. Web search enrichment prevents the briefing from being stale.

## Layer 4 — Confidence & Currency

**What:** Validate the briefing's accuracy and add confidence calibration.
**How:**
1. Cross-reference claims against the ai-specialist benchmarks (Section 6)
2. Calibrate confidence for each major claim:
   - **High**: Well-established (agent patterns, regulatory frameworks, proven use cases)
   - **Medium**: Evolving (adoption timelines, market projections, emerging use cases)
   - **Low**: Speculative (2027+ predictions, unproven patterns)
3. Flag any areas where a web search couldn't confirm current data — note as "requires validation"
4. Attribute all sources (Gartner, McKinsey, DORA, regulatory bodies)
5. Suggest follow-up questions the CIO should ask vendors or teams
**Why:** AI is the domain with the highest hype-to-reality ratio. Confidence calibration protects the CIO from acting on inflated claims. Source attribution enables the CIO to dig deeper. Follow-up questions demonstrate advisory depth.

**Output**: A structured AI executive briefing following the SCQA pattern — situation, complication, question, answer — enriched with current data, payments-specific use cases, governance implications, a three-horizon recommendation, and confidence calibration. Ready for CIO conversations.
