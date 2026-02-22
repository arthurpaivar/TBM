---
name: problem-solving-specialist
description: >
  This skill should be used when the user asks about "problem solving", "root cause",
  "issue tree", "hypothesis", "structured thinking", "5 whys", "fishbone", "Ishikawa",
  "MECE", "decomposition", "problem framing", "decision matrix", "trade-off analysis",
  "options analysis", "why is this happening", "how do we fix", "breakdown",
  "structured analysis", "consulting framework", "McKinsey problem solving",
  "so what tree", "recommendation", "root cause analysis", "diagnostic",
  or needs structured problem-solving using top-tier consulting frameworks.
  Also used internally by commands that need problem decomposition as a building block.
  Use whenever the user faces a complex problem that needs rigorous decomposition and recommendation.
version: 2.0.0
---

# Skill — Problem-Solving Specialist

**Expert in structured problem solving using top-tier consulting methodologies (McKinsey, BCG, Bain).** This skill applies rigorous, hypothesis-driven problem-solving to decompose complex challenges, identify root causes, evaluate options, and build defensible recommendations. It serves as the core analytical engine that commands orchestrate — and its methodology can be combined with domain specialists from technology-expert-plugin (architecture, strategy, AI, agile, delivery) and finance-expert-plugin (TBM, portfolio, financial modeling) for domain-specific depth.

**Core Principles**: SPAR Framework, Pyramid Principle, SCQA Pattern, MECE Decomposition, Confidence Calibration, Source Attribution, Practical & Adaptable — these govern all outputs from this skill.

**Trigger keywords**: problem solving, root cause, issue tree, hypothesis, structured thinking, 5 whys, fishbone, Ishikawa, MECE, decomposition, problem framing, decision matrix, trade-off analysis, options analysis, so what tree, recommendation, root cause analysis, diagnostic, McKinsey problem solving, structured analysis.

## Section 1 — Problem Framing

The most common failure in problem solving is solving the wrong problem well. Framing determines everything that follows.

### 1.1 — The Framing Protocol

Before any decomposition, answer these five questions:

1. **What is the real question?** Strip away symptoms. A CIO saying "our costs are too high" might really mean "we can't justify our spend to the CFO." These are different problems with different solutions.
2. **Who is the decision-maker?** The person who will act on the recommendation. Frame everything for their context, authority, and constraints.
3. **What would a good answer look like?** Define success criteria before starting. "A recommendation the CIO can present to the board with confidence" is specific. "Solve the problem" is not.
4. **What constraints exist?** Time, budget, political, regulatory, organizational. Constraints shape which branches of the issue tree are actionable.
5. **What is the cost of inaction?** Quantify what happens if nothing changes. This anchors urgency and frames the scale of investment warranted.

### 1.2 — SCQA for Problem Statements

Structure the problem statement as:

- **Situation**: The established context everyone agrees on (factual, neutral)
- **Complication**: What changed, what's wrong, what's at risk (creates tension)
- **Question**: The precise question we need to answer (derived from the complication)
- **Answer**: The hypothesis or recommendation (stated upfront, then proven)

Example:
- **S**: We process 2M transactions daily across 4 payment rails
- **C**: Failed transaction rate increased from 0.3% to 1.2% in Q3, costing $4.8M in lost revenue
- **Q**: What is causing the increase and what should we do about it?
- **A**: Network-side latency on the card rail is responsible for 70% of failures; migrating to the new gateway will restore rates within 6 weeks

### 1.3 — Reframing Techniques

When the initial problem feels too broad or too narrow:

- **Zoom out**: "Why does this matter?" → reveals the strategic context
- **Zoom in**: "What specifically?" → reveals the operational detail
- **Flip**: "What would the opposite look like?" → reveals hidden assumptions
- **Stakeholder lens**: "How would the CFO / CTO / customer frame this?" → reveals framing bias

## Section 2 — Issue Tree Construction

The issue tree is the backbone of the analysis. Every branch must be MECE — Mutually Exclusive (no overlap) and Collectively Exhaustive (no gaps).

### 2.1 — Building Top-Down

Start with the core question at the root. Break into 2-4 branches at each level. Each branch answers a distinct sub-question.

**Two types of issue trees:**

**Diagnostic Tree** (Why is this happening?):
```
Why is transaction failure rate increasing?
├── System-side causes
│   ├── Application bugs (new releases, regression)
│   ├── Infrastructure capacity (CPU, memory, storage)
│   └── Configuration errors (routing rules, thresholds)
├── Network-side causes
│   ├── Latency spikes (ISP, cloud provider, CDN)
│   ├── Packet loss (network congestion, hardware failure)
│   └── DNS resolution failures
├── Endpoint causes
│   ├── Invalid requests (malformed data, expired credentials)
│   ├── Merchant-side errors (timeout, retry storms)
│   └── Customer-side issues (insufficient funds, fraud blocks)
└── Integration causes
    ├── Third-party service outages
    ├── API version mismatches
    └── Data format incompatibilities
```

**Solution Tree** (What should we do?):
```
How do we reduce transaction failure rate to <0.5%?
├── Quick wins (0-4 weeks)
│   ├── Fix known bugs in latest release
│   ├── Increase timeout thresholds
│   └── Add retry logic for transient failures
├── Medium-term fixes (1-3 months)
│   ├── Migrate to new payment gateway
│   ├── Implement circuit breakers
│   └── Add real-time monitoring and alerting
└── Strategic improvements (3-12 months)
    ├── Redesign payment orchestration layer
    ├── Multi-provider redundancy
    └── ML-based anomaly detection
```

### 2.2 — MECE Validation

For each level of the tree, verify:
- **Mutually Exclusive**: Can an item belong to more than one branch? If yes, redefine boundaries.
- **Collectively Exhaustive**: Is there anything that doesn't fit any branch? If yes, add a branch or expand scope.
- **Balanced**: Are branches roughly comparable in size and importance? Lopsided trees indicate poor decomposition.

### 2.3 — Prioritization

Not all branches deserve equal investigation. Prioritize using:
- **Impact**: Which branches, if true, would most change the recommendation?
- **Likelihood**: Based on available evidence, which branches are most probable?
- **Testability**: Which branches can be quickly validated or eliminated?

Mark branches as: **Investigate** (high priority), **Monitor** (keep visible), or **Park** (low priority, revisit if needed).

## Section 3 — Hypothesis-Driven Analysis

Move from decomposition to testing. Every branch becomes a hypothesis to prove or disprove.

### 3.1 — Hypothesis Formation

For each priority branch, state:
- **Hypothesis**: "We believe [cause/solution] because [initial evidence]"
- **Key question**: "What would we need to see to confirm or reject this?"
- **Minimum viable analysis**: "What is the fastest way to test this?"

### 3.2 — Evidence Collection

For each hypothesis, gather evidence systematically:
- **Quantitative**: Data, metrics, benchmarks, financial analysis
- **Qualitative**: Expert interviews, case studies, analogies
- **External**: Industry research, analyst reports, competitor intelligence

**Cross-plugin orchestration**: When a hypothesis requires domain-specific depth:
- Technology questions → invoke technology-expert-plugin skills (architecture-specialist for system design, tech-strategy-advisory for strategic context, ai-specialist for AI-related topics, agile-specialist for delivery methodology, tech-delivery-specialist for CI/CD and DevOps)
- Financial questions → invoke finance-expert-plugin skills (tech-bm-specialist for cost analysis, it-portfolio-management for portfolio decisions, excel-for-finance for financial modeling)

### 3.3 — Synthesis

After testing hypotheses, synthesize:
- **Confirmed**: Evidence supports the hypothesis → include in recommendation
- **Rejected**: Evidence contradicts → document why and move on
- **Inconclusive**: Not enough data → state explicitly with confidence level

## Section 4 — Root Cause Analysis Methods

When the issue tree points to a branch but the root cause isn't yet clear:

### 4.1 — 5 Whys (Drill to Root)

Ask "why" iteratively until the actionable root cause emerges. Stop when the next "why" leads to something outside your control or scope.

### 4.2 — Fishbone / Ishikawa

Organize causes by category: **People** (skills, staffing, accountability), **Process** (workflow, handoffs, approvals), **Technology** (tools, infrastructure, data), **Environment** (market, regulation, organizational culture). Useful when causes span multiple domains.

### 4.3 — Pareto Analysis

Identify the 20% of causes driving 80% of impact. Quantify each cause's contribution. Focus recommendation on the vital few.

### 4.4 — Change Analysis

When the problem is a deviation from a previous norm: What changed? When? Who initiated it? What else changed simultaneously? Useful for regression-type problems.

## Section 5 — Options Development & Evaluation

### 5.1 — Option Design

Always present 3-4 options (never 1, rarely 2, avoid 5+):
- **Option A — Minimum viable**: Lowest cost, fastest, addresses core issue only
- **Option B — Balanced (typically recommended)**: Best risk-adjusted return, addresses root cause
- **Option C — Comprehensive**: Highest investment, maximum long-term value
- **Option D — Transformational** (when warranted): Fundamental redesign, highest ambition

### 5.2 — Evaluation Framework

For each option, assess:

| Dimension | What to Evaluate |
|-----------|-----------------|
| **Impact** | How much does this solve the problem? (% of gap closed) |
| **Feasibility** | Can we execute this with current capabilities? |
| **Cost** | Total investment required (CapEx + OpEx over 3 years) |
| **Timeline** | Time to first value, time to full value |
| **Risk** | What could go wrong? How severe? How likely? |
| **Dependencies** | What must be true for this to work? |

### 5.3 — Weighted Decision Matrix

When the choice is close, apply weights:
1. Define criteria with the decision-maker
2. Assign weights (must sum to 100%)
3. Score each option (1-5) against each criterion
4. Calculate weighted scores
5. Discuss: Does the winner feel right? If not, the weights may be wrong.

## Section 6 — Synthesis & Recommendation

### 6.1 — So-What Tree

Build layers of insight from data to action:
```
DATA → INSIGHT → IMPLICATION → ACTION
"Card rail failures 4x above baseline" → "Gateway provider SLA breach" → "Current vendor unreliable for scale" → "Begin gateway migration, parallel-run for 8 weeks"
```

### 6.2 — Recommendation Pyramid

Structure the recommendation top-down:
1. **Recommendation** (1 sentence): What to do
2. **Key reasons** (3-4): Why this is the right choice
3. **Supporting evidence**: Data, analysis, benchmarks that prove each reason
4. **Risk mitigation**: How we address the biggest concerns
5. **Next steps**: Immediate actions with owners and timelines

### 6.3 — Communication Protocol

All problem-solving outputs follow this structure:

**Opening (The So-What)**: Lead with the answer. State the recommendation and its impact in 2-3 sentences. The decision-maker should understand the conclusion before reading any analysis. No preamble, no throat-clearing — straight to the point.

**Body (The Evidence)**: Present the structured analysis that supports the opening. Issue tree, hypothesis testing results, root cause findings, options evaluation. Organized top-down, not chronologically. Each section earns its place by directly supporting the recommendation.

**Conclusion (Insight & Action)**: Go beyond the analysis. Provide strategic insight — what does this mean for the broader context? Actionable recommendations with specific next steps, owners, and timelines. End with what to monitor and when to reassess. This section should leave the reader feeling equipped to act.

## Section 7 — Cross-Plugin Orchestration

This skill is designed to work in concert with domain specialists. When the problem-solve command orchestrates a full analysis:

### When to Invoke Other Skills

| Signal in the Problem | Specialist to Invoke | What to Extract |
|----------------------|---------------------|----------------|
| Architecture or system design questions | architecture-specialist (tech plugin) | Patterns, trade-offs, technical feasibility |
| Strategic technology decisions | tech-strategy-advisory (tech plugin) | Frameworks, market context, transformation patterns |
| AI/ML components | ai-specialist (tech plugin) | AI capabilities, implementation patterns |
| Delivery methodology questions | agile-specialist or tech-delivery-specialist (tech plugin) | Process maturity, DORA metrics, CI/CD patterns |
| Cost or investment analysis | tech-bm-specialist (finance plugin) | TBM taxonomy, cost allocation, benchmarks |
| Portfolio decisions | it-portfolio-management (finance plugin) | TIME model, rationalization, prioritization |
| Financial modeling | business-case-specialist (this plugin) | NPV, IRR, TCO, sensitivity analysis |
| External evidence needed | deep-search-specialist (this plugin) | Multi-source research, source hierarchy |
| Performance benchmarks | industry-benchmark-specialist (this plugin) | Peer comparison, KPI targets, maturity models |

### Orchestration Pattern

1. Frame the problem → identify which branches need domain-specific depth
2. For each branch requiring expertise → invoke the relevant specialist as a subagent via Task tool
3. Collect specialist outputs → synthesize into the unified recommendation
4. Use specialist outputs as evidence in the So-What Tree

## Output Patterns

### Executive Problem-Solving Summary

```
═══════════════════════════════════════════════════════
PROBLEM-SOLVING SUMMARY
═══════════════════════════════════════════════════════

RECOMMENDATION
[1-2 sentence recommendation with quantified impact]

───────────────────────────────────────────────────────
PROBLEM FRAMING
───────────────────────────────────────────────────────
Situation: [Factual context]
Complication: [What changed / what's at risk]
Question: [The precise question answered]

───────────────────────────────────────────────────────
ISSUE TREE & ROOT CAUSE
───────────────────────────────────────────────────────
[Visual tree with priority branches marked]

Root Cause: [Primary cause with evidence]
Contributing Factors: [Secondary causes]
Confidence: [High/Medium/Low with rationale]

───────────────────────────────────────────────────────
OPTIONS EVALUATED
───────────────────────────────────────────────────────
| Option | Impact | Cost | Timeline | Risk | Score |
|--------|--------|------|----------|------|-------|
| A: [name] | [assessment] | [est.] | [est.] | [level] | [x/5] |
| B: [name] ★ | [assessment] | [est.] | [est.] | [level] | [x/5] |
| C: [name] | [assessment] | [est.] | [est.] | [level] | [x/5] |

★ Recommended

───────────────────────────────────────────────────────
STRATEGIC INSIGHT
───────────────────────────────────────────────────────
[What this means beyond the immediate problem — broader implications, patterns, opportunities]

───────────────────────────────────────────────────────
NEXT STEPS
───────────────────────────────────────────────────────
1. [Immediate action] → Owner: [who] | By: [when]
2. [Follow-up action] → Owner: [who] | By: [when]
3. [Monitor] → Metric: [what] | Trigger: [threshold]

═══════════════════════════════════════════════════════
```

### Decision Brief (1-Page)

```
DECISION BRIEF: [Title]

RECOMMENDATION: [Clear action statement]

SITUATION: [2-3 sentences of context]
COMPLICATION: [What creates urgency]
KEY FINDING: [Root cause or critical insight]

OPTIONS:
A. [Minimum] — [1-line summary, cost, timeline]
B. [Balanced] — [1-line summary, cost, timeline] ★ RECOMMENDED
C. [Comprehensive] — [1-line summary, cost, timeline]

WHY OPTION B:
• [Reason 1 with evidence]
• [Reason 2 with evidence]
• [Reason 3 with evidence]

RISKS & MITIGATION:
• [Top risk] → [Mitigation]

NEXT STEPS: [Immediate actions with owners]
```

## Quality Checks

- [ ] Have I framed the real problem, not the surface symptom?
- [ ] Is the issue tree genuinely MECE at every level?
- [ ] Are hypotheses tested with evidence, not assumption?
- [ ] Does the recommendation follow logically from the analysis (no leaps)?
- [ ] Is the So-What clear — could a busy executive act on the Opening alone?
- [ ] Are options genuinely distinct and fairly evaluated (no straw men)?
- [ ] Have I quantified impact where possible (not just directional)?
- [ ] Does the conclusion provide strategic insight beyond the immediate problem?
- [ ] Are next steps specific with owners and timelines?

---

**Confidence Calibration**: High confidence for structured problem decomposition and MECE validation. Medium confidence for root cause identification in domains requiring specialist knowledge — recommend invoking domain-specific specialists via subagents. Low confidence for financial quantification without finance-expert-plugin support.

**Triggers**: Activate when user faces a complex problem needing decomposition, root cause analysis, options evaluation, or structured recommendation. Also activated internally by the problem-solve command as the core analytical engine.
