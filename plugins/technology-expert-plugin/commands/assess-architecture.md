---
description: Assess an architecture design or pattern against best practices
allowed-tools: Read, WebSearch, WebFetch
argument-hint: "[architecture topic — e.g., 'microservices migration for payment processing', 'API gateway design']"
---

Assess architecture for $ARGUMENTS using the architecture-specialist skill.

## Layer 1 — Context & Intent

**What:** Define what architecture is being assessed and what the user needs.
**How:** Parse $ARGUMENTS to extract:
- What system, pattern, or design is being assessed?
- What architecture domain? (enterprise, solution, data, API, cloud, payments)
- Is this a current-state assessment, a proposed design review, or a pattern selection?
- What's the business context? (new build, migration, optimization, compliance)

If the topic also touches delivery practices, load `tech-delivery-specialist` for DevOps/SRE context. If it touches strategy, load `tech-strategy-advisory` for business alignment.
**Why:** Architecture assessments vary wildly in scope. Clarifying the domain and intent ensures the right frameworks are applied. An API design review uses different criteria than an enterprise architecture assessment.

## Layer 2 — Knowledge Loading

**What:** Load the architecture-specialist skill and extract relevant assessment frameworks.
**How:** Read the architecture-specialist SKILL.md. Extract the sections relevant to the domain:
- Section 1 (EA Frameworks) for enterprise-level assessments
- Section 2 (Application Patterns) for pattern selection and comparison
- Section 3 (Data Architecture) for data-related assessments
- Section 4 (Cloud Architecture) for cloud/infrastructure reviews
- Section 5 (API Strategy) for API design assessments
- Section 6 (Payments Architecture) for payments-specific requirements
- Section 7 (ADRs) for documenting the assessment decisions
- Section 8 (Benchmarks) for maturity and performance baselines
**Why:** The architecture-specialist contains deep knowledge across all architecture domains. Loading the right sections focuses the assessment and prevents irrelevant framework application.

## Layer 3 — Assessment Execution

**What:** Apply the relevant architecture frameworks to produce a structured assessment.
**How:** Follow the Architecture Assessment output pattern from the skill:
1. **Current State**: Document the current architecture pattern, technology stack, and maturity level
2. **Well-Architected Assessment**: Evaluate against the 5 pillars (Operational Excellence, Security, Reliability, Performance, Cost) — score each
3. **Pattern Fit**: Is the current/proposed pattern appropriate for the context? Reference the Pattern Comparison Matrix
4. **Strengths**: What's working well (top 3)
5. **Gaps**: What's missing or weak (top 3 with severity)
6. **Technical Debt**: Identify debt items with impact and effort ratings
7. **Payments-Specific**: Apply PCI-DSS, settlement, reconciliation requirements if relevant
8. **Trade-offs**: Document key trade-offs using CAP/PACELC if applicable

Use MECE decomposition throughout — the assessment should have no overlapping concerns and no blind spots.
**Why:** A structured assessment using recognized frameworks (Well-Architected, TOGAF) gives the output credibility. The CIO and architecture teams expect industry-standard evaluation criteria, not ad-hoc opinions.

## Layer 4 — Recommendations & ADR

**What:** Provide actionable recommendations and document key decisions.
**How:**
1. Prioritize recommendations by impact and effort (High-Impact/Low-Effort first)
2. Reference specific architecture patterns for each recommendation
3. Provide a Migration Roadmap if the assessment reveals a need for transformation
4. Draft an Architecture Decision Record (ADR) for the most significant decision
5. Include confidence calibration for each recommendation

If the assessment involves emerging patterns or technologies, use WebSearch to validate current industry adoption and best practices.
**Why:** An assessment without recommendations is just a report. The ADR ensures decisions are documented and traceable — critical for regulated environments where architecture decisions have audit implications.

**Output**: A structured architecture assessment following the Architecture Assessment output pattern — current state, Well-Architected scores, strengths, gaps, technical debt, recommendations with an ADR for key decisions, and a migration roadmap if transformation is needed. Confidence calibrated and sources attributed.
