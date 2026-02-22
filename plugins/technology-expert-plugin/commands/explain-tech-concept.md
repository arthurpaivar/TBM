---
description: Explain a technology concept clearly for CIO-level understanding
allowed-tools: Read, WebSearch, WebFetch
argument-hint: "[concept to explain — e.g., 'event sourcing', 'MCP protocol', 'data mesh']"
---

Explain $ARGUMENTS for CIO-level understanding using the appropriate technology-expert-plugin specialist skill.

## Layer 1 — Context & Intent

**What:** Identify what concept needs explaining and which specialist skill contains the relevant knowledge.
**How:** Parse $ARGUMENTS to extract the technology concept. Route to the correct skill:
- AI, agents, MCP, LLM, GenAI → `ai-specialist`
- Architecture, patterns, APIs, cloud, data → `architecture-specialist`
- DevOps, CI/CD, SRE, platform, testing → `tech-delivery-specialist`
- Agile, DORA, SAFe, team topologies → `agile-specialist`
- Strategy, TOM, capability mapping, consulting frameworks → `tech-strategy-advisory`

If the concept spans multiple skills, identify the primary skill and note cross-references.
**Why:** Routing to the right skill ensures depth. A shallow explanation from the wrong skill is worse than no explanation at all.

## Layer 2 — Knowledge Loading

**What:** Load the identified specialist skill and extract the relevant domain knowledge.
**How:** Read the SKILL.md for the identified specialist. Locate the specific section that covers this concept. Extract:
- Definition and core mechanics
- Key frameworks or patterns
- Payments/financial services relevance
- Industry benchmarks or data points
**Why:** The specialist skills contain the deep domain knowledge accumulated by trial and error. Loading the right section provides authoritative, consistent explanations.

## Layer 3 — Concept Structuring

**What:** Structure the explanation for CIO-level consumption using the Pyramid Principle.
**How:** Build the explanation top-down:
1. **Key Insight First**: One sentence capturing why this concept matters for a Payments CIO
2. **Definition**: What it is in clear, non-jargon language
3. **How It Works**: Mechanics explained with practical analogy
4. **Why It Matters**: Business relevance for payments technology
5. **Current State**: Where the industry is with this concept (adoption, maturity)
6. **What To Do About It**: Practical next steps or questions to ask

Use analogies from the payments/financial services world where possible. Avoid acronym soup — spell out and explain every abbreviation on first use.
**Why:** CIO-level explanations need to be strategic, not tactical. Leading with the insight and structuring top-down respects executive attention and provides the "so what" before the "what."

## Layer 4 — Enrichment & Validation

**What:** Enrich with current data and validate accuracy.
**How:** If the concept is rapidly evolving (AI, cloud services, emerging patterns), use WebSearch to find the latest industry data, adoption statistics, or vendor announcements. Cross-reference against the specialist skill's benchmarks section. Add confidence calibration — note what's well-established vs. what's evolving.
**Why:** Technology concepts evolve rapidly. The specialist skills provide foundational knowledge, but enrichment with current data prevents stale explanations — especially important when the CIO may have seen recent news.

**Output**: A clear, CIO-ready explanation of the technology concept structured with the Pyramid Principle — key insight first, then definition, mechanics, business relevance, current state, and recommended actions. Includes confidence calibration and source attribution.
