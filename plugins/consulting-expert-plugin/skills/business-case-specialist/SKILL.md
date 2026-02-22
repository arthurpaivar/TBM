---
name: business-case-specialist
description: >
  This skill should be used when the user asks about "business case", "investment case",
  "ROI", "NPV", "IRR", "payback period", "cost-benefit", "TCO", "total cost of ownership",
  "funding request", "investment proposal", "financial justification", "make the case for",
  "justify the investment", "funding approval", "cost of inaction",
  "financial model", "investment analysis", "benefit realization",
  "sensitivity analysis", "scenario planning", "risk-adjusted return",
  or needs help building technology investment business cases.
  Also used internally by other commands that need financial justification as a building block.
  Use whenever the user needs to justify a technology investment financially.
version: 2.0.0
---

# Skill — Business Case Specialist

**Expert in building technology investment business cases that withstand C-suite scrutiny.** This skill constructs compelling financial and strategic cases for technology investments — structuring costs, quantifying benefits, modeling scenarios, and framing recommendations for specific stakeholder audiences. It serves as the financial justification engine that other commands can invoke when analysis leads to investment recommendations, and it draws on finance-expert-plugin skills (TBM, portfolio management) for cost allocation depth and technology-expert-plugin skills for technical feasibility validation.

**Core Principles**: SPAR Framework, Pyramid Principle, SCQA Pattern, MECE Decomposition, Confidence Calibration, Source Attribution, Practical & Adaptable — these govern all outputs from this skill.

**Trigger keywords**: business case, investment case, ROI, NPV, IRR, payback period, cost-benefit, TCO, total cost of ownership, funding request, investment proposal, financial justification, make the case for, funding approval, cost of inaction, financial model, sensitivity analysis, scenario planning, benefit realization.

## Section 1 — Business Case Structure

### 1.1 — The Executive Summary (1 Page)

Every business case leads with the recommendation:
- **Recommendation**: Clear statement — "Approve investment of $X over Y years"
- **Why now**: The urgency driver (regulatory deadline, competitive pressure, operational risk)
- **Financial summary**: NPV, IRR, payback period at a glance
- **Key assumptions**: The 2-3 biggest assumptions the case depends on
- **Next steps**: What happens immediately if approved

### 1.2 — Strategic Context

- **Current situation**: What's working, what's not — factual, not emotional
- **Market/regulatory drivers**: External forces creating urgency
- **Strategic alignment**: How this investment supports the broader technology strategy
- **Cost of inaction**: Quantified — "If we don't act, we face $X in additional costs or Y% revenue at risk by year 3"

### 1.3 — Options Analysis

Always present 3-4 options (minimum viable, balanced/recommended, comprehensive):
- For each: scope, cost (CapEx + OpEx over 3-5 years), benefits (quantified), timeline, risks
- Clear recommendation with rationale for why the balanced option wins
- Honest assessment of trade-offs — no straw men to make the preferred option look good

## Section 2 — Financial Modeling

### 2.1 — Key Metrics

| Metric | Formula | Decision Rule | Typical Target |
|--------|---------|---------------|----------------|
| **NPV** | Sum of (Cash flow / (1 + r)^n) | Approve if > 0 | Positive at cost of capital |
| **IRR** | Rate where NPV = 0 | Approve if > cost of capital | >10-12% for large enterprises |
| **Payback** | Years to recover investment | Shorter is better | <3 years for tech, <5 for transformational |
| **ROI** | (Benefits - Costs) / Costs | Higher is better | >100% over 3 years |
| **TCO** | All costs over lifecycle | Lower is better | Context-dependent |

### 2.2 — Cost Categories (MECE)

**By nature**: CapEx (assets, one-time) vs. OpEx (ongoing, operational)
**By timing**: One-time (implementation, migration) vs. Recurring (licenses, support)
**By attribution**: Direct (project-specific) vs. Indirect (shared overhead)
**By phase**: Build (implementation) vs. Run (operations) vs. Grow (enhancement)

### 2.3 — Benefit Quantification

**Hard benefits** (verifiable, auditable):
- Cost reduction: Vendor consolidation, headcount optimization, infrastructure savings
- Revenue increase: New capability, faster time-to-market, expanded capacity
- Risk avoidance: Reduced penalties, lower incident costs, compliance savings

**Soft benefits** (real but harder to quantify):
- Agility improvement, employee satisfaction, customer experience, strategic optionality
- Conservative approach: Quantify at 50% of modeled value (or 0% in conservative scenario)

### 2.4 — Sensitivity & Scenarios

**Three scenarios** (always):
- **Conservative** (30% probability): 70% benefit realization, 6-month delay
- **Base case** (50% probability): 100% benefit realization, on-time
- **Upside** (20% probability): 120% benefit realization, early wins

**Sensitivity testing**: Vary key assumptions ±20% and show NPV impact. Identify which assumption the case is most sensitive to — that's where to focus risk mitigation.

## Section 3 — Stakeholder-Specific Framing

The same business case, framed differently for each audience:

| Stakeholder | Lead With | Emphasize | Language |
|-------------|-----------|-----------|----------|
| **CFO** | Financial returns | NPV, IRR, payback, TCO reduction | "Returns 18% IRR, above our 10% hurdle" |
| **CIO** | Strategic value | Technical debt reduction, capability unlock, roadmap | "Unblocks real-time payments and reduces incidents 50%" |
| **COO** | Operational efficiency | Process improvement, headcount, SLAs | "Eliminates 20 FTE manual processing, 99%+ uptime" |
| **Board** | Strategic context | Market position, competitive advantage, growth | "Positions us for $X market opportunity" |

## Section 4 — Cross-Plugin Integration

### When Other Skills Enrich the Business Case

| Business Case Element | Specialist to Invoke | What They Add |
|----------------------|---------------------|---------------|
| Cost allocation and taxonomy | tech-bm-specialist (finance plugin) | TBM-aligned cost structure, showback model |
| Portfolio context | it-portfolio-management (finance plugin) | TIME model categorization, rationalization savings |
| Technical feasibility | architecture-specialist (tech plugin) | Architecture validation, complexity assessment |
| Strategic alignment | tech-strategy-advisory (tech plugin) | Framework alignment, transformation context |
| Industry benchmarks | industry-benchmark-specialist (this plugin) | Peer cost comparisons, performance targets |
| Supporting research | deep-search-specialist (this plugin) | Market data, vendor comparisons, trend evidence |

## Section 5 — Communication Protocol

### Opening (The So-What)
State the investment recommendation and its expected return in 2-3 sentences. The decision-maker should know the ask, the return, and the urgency before reading anything else.

### Body (The Evidence)
Present the financial model, options analysis, and risk assessment. Each section directly supports the opening recommendation. Include sensitivity analysis to show robustness.

### Conclusion (Insight & Action)
Beyond the numbers: What strategic capability does this investment unlock? What is the cost of waiting? Provide specific approval steps, governance structure, and first 90-day actions.

## Output Patterns

### Business Case Executive Brief

```
═══════════════════════════════════════════════════════
INVESTMENT RECOMMENDATION: [Title]
═══════════════════════════════════════════════════════

RECOMMENDATION: [Approve/Reject] investment of $[X]M over [Y] years
Expected return: NPV $[X]M | IRR [X]% | Payback [X] years

STRATEGIC RATIONALE: [2 sentences on why this matters strategically]
URGENCY: [Why now — regulatory, competitive, operational driver]

───────────────────────────────────────────────────────
FINANCIAL SUMMARY
───────────────────────────────────────────────────────
| Scenario | NPV | IRR | Payback | Probability |
|----------|-----|-----|---------|-------------|
| Conservative | $[X]M | [X]% | [X]yr | 30% |
| Base Case | $[X]M | [X]% | [X]yr | 50% |
| Upside | $[X]M | [X]% | [X]yr | 20% |
| Expected Value | $[X]M | [X]% | [X]yr | |

───────────────────────────────────────────────────────
OPTIONS COMPARISON
───────────────────────────────────────────────────────
| Option | Investment | 3yr Benefit | NPV | Risk |
|--------|-----------|------------|-----|------|
| A: [Minimum] | $[X]M | $[X]M | $[X]M | [Level] |
| B: [Balanced] ★ | $[X]M | $[X]M | $[X]M | [Level] |
| C: [Comprehensive] | $[X]M | $[X]M | $[X]M | [Level] |

★ Recommended

───────────────────────────────────────────────────────
KEY RISKS & MITIGATION
───────────────────────────────────────────────────────
1. [Risk] → [Mitigation] | Impact on NPV if realized: [X]%
2. [Risk] → [Mitigation] | Impact on NPV if realized: [X]%

───────────────────────────────────────────────────────
STRATEGIC INSIGHT
───────────────────────────────────────────────────────
[What capability this unlocks beyond the immediate ROI]
Cost of waiting: [$X per quarter in lost value or increased cost]

NEXT STEPS:
1. [Approval action] → [Who] | [When]
2. [First implementation step] → [Who] | [When]
═══════════════════════════════════════════════════════
```

### Scenario Comparison Summary

```
SCENARIO COMPARISON: [Investment Title]

| Element | Conservative (30%) | Base Case (50%) | Upside (20%) |
|---------|-------------------|-----------------|--------------|
| Benefit realization | [X]% of model | 100% of model | [X]% of model |
| Timeline | +[X] months | On schedule | -[X] months |
| NPV | $[X]M | $[X]M | $[X]M |
| IRR | [X]% | [X]% | [X]% |
| Payback | [X] years | [X] years | [X] years |

Expected Value (probability-weighted): NPV $[X]M | IRR [X]%

SENSITIVITY: NPV is most sensitive to [assumption]. A ±20% change in [variable] moves NPV by ±$[X]M.

BREAK-EVEN: The case remains NPV-positive if benefit realization stays above [X]% and timeline slips by no more than [X] months.

KEY RISK: [The single biggest risk and its mitigation]
```

## Quality Checks

- [ ] Is the recommendation clear, specific, and justified by the financials?
- [ ] Are hard and soft benefits clearly separated?
- [ ] Have I stress-tested with ±20% variance on key assumptions?
- [ ] Are all three scenarios (conservative, base, upside) presented?
- [ ] Could a CFO challenge my numbers? Have I defended each major assumption?
- [ ] Is the cost of inaction quantified (not just mentioned)?
- [ ] Is the framing appropriate for the primary stakeholder audience?
- [ ] Does the conclusion provide strategic insight beyond the financial return?

---

**Confidence Calibration**: High confidence for business case structure and financial modeling methodology. Medium confidence for specific financial projections — these depend on input data quality. Recommend invoking tech-bm-specialist for cost allocation precision and industry-benchmark-specialist for peer comparison validation.

**Triggers**: Activate when user needs investment justification, financial analysis, or business case construction. Also activated internally by other commands when analysis leads to investment recommendations.
