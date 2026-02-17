---
name: business-case-specialist
description: >
  This skill should be used when the user asks about "business case", "investment case",
  "ROI", "NPV", "IRR", "payback period", "cost-benefit", "TCO", "total cost of ownership",
  "funding request", "investment proposal", "financial justification", "make the case for",
  "justify the investment", "funding approval",
  or needs help building technology investment business cases.
  Use whenever the user needs to justify a technology investment financially.
version: 1.0.0
---

# Skill 4.4 — Business Case Specialist

**Expert in building technology investment business cases.** This skill builds compelling financial and strategic cases for technology investments, justifies funding requests, and structures financial models that can withstand CFO scrutiny while remaining strategically grounded.

**Trigger keywords**: business case, investment case, ROI, NPV, IRR, payback period, cost-benefit, TCO, total cost of ownership, funding request, investment proposal, financial justification, make the case for, funding approval.

## Core Principles

These principles govern all outputs from this skill:

- **SPAR Framework**: Follow Sense → Plan → Act → React for every task. Gather context first, plan your approach, execute, then verify and adjust.
- **Pyramid Principle (Barbara Minto)**: Lead with the answer. Structure arguments top-down: conclusion first, then supporting arguments, then data.
- **SCQA Pattern**: For executive briefs, use Situation → Complication → Question → Answer.
- **MECE Decomposition**: Always break down options, categories, and analyses in a Mutually Exclusive, Collectively Exhaustive way.
- **Confidence Calibration**: Explicitly state your confidence level. Escalate when uncertain rather than guessing.
- **Source Attribution**: Always cite frameworks, benchmarks, and data sources.
- **Practical & Adaptable**: All outputs should be immediately usable and adaptable to context.

## Business Case Structure

### Executive Summary (1 page)
- **Recommendation**: Clear statement: "Approve investment of $X million over Y years"
- **Why now**: Urgency and business driver (regulatory, competitive, operational)
- **Financial summary**: NPV, IRR, payback period, key risks
- **Key assumptions**: 2-3 biggest assumptions underlying the case
- **Next steps**: If approved, what happens immediately?

### Strategic Context (0.5 page)
- **Current situation**: Where we stand, what's working, what's not
- **Market/regulatory drivers**: Why this matters now
- **Strategic alignment**: How this supports JPM's strategy
- **Competitive context**: What are competitors doing?

### Current State Assessment (1-2 pages)
- **Pain points**: What's driving the need?
- **Cost of doing nothing**: Explicitly quantify: "If we don't act, we'll lose $X in revenue or incur $X in additional costs by year 3"
- **Operational impact**: Customer impact, employee productivity, risk exposure
- **Financial impact**: Annual run-rate cost/loss

### Options Analysis (1-2 pages)
**Option A: Status Quo / Minimal Investment**
- Pros: Minimal upfront cost
- Cons: Doesn't solve root problem, increases future cost
- 3-year cost: $X
- Risks: High; competitive disadvantage, regulatory exposure

**Option B: Recommended Approach (Balanced)**
- Pros: Best risk-adjusted return, achievable timeline
- Cons: Requires organizational change, execution risk
- 3-year investment: $X, 3-year benefit: $Y
- NPV @ 10% discount: $Z
- Risks: Moderate; mitigation plan included

**Option C: Comprehensive Approach (Premium)**
- Pros: Fastest path, maximum long-term value, lowest operational risk
- Cons: Highest upfront cost and complexity
- 3-year investment: $X, 3-year benefit: $Y
- NPV @ 10% discount: $Z
- Risks: Lower, but requires larger upfront commitment

## Financial Modeling Framework

### Key Financial Metrics

**Net Present Value (NPV)**
- Formula: Sum of (Annual cash flow / (1 + discount rate)^year)
- Discount rate guidance: 10% for mature businesses, 15% for higher-risk initiatives
- Decision rule: Approve if NPV > 0; compare across options
- Example: $1M investment year 1, $500K benefit years 2-4 @ 10% discount rate = NPV of ~$270K

**Internal Rate of Return (IRR)**
- Definition: The discount rate at which NPV = 0
- Interpretation: "This investment returns 18% annually"
- Compare to: Cost of capital (usually 10-12% for large banks)
- Decision rule: Approve if IRR exceeds cost of capital; higher IRR = more attractive

**Payback Period**
- Definition: Years to recover initial investment
- Target: <3 years for most technology investments, <5 years for transformational ones
- Limitation: Doesn't account for cash flows after payback; use with NPV/IRR
- Use case: Quick gut-check; communicates to non-financial stakeholders

**Total Cost of Ownership (TCO) over 3-5 years**
- Includes all costs: hardware, software, implementation, training, ongoing support
- Annualized TCO: Total TCO / number of years
- Compare to: Annual benefits (cost avoidance, revenue uplift)
- Example: TCO $10M over 3 years = $3.3M annually; if delivering $5M annual benefit, ROI = 52%

### Cost Categories

**CapEx (Capital Expenditure) — Asset purchases**
- Infrastructure (servers, network, storage)
- Software licenses (multi-year)
- One-time implementation costs
- Asset depreciation: typically 3-5 years for technology

**OpEx (Operating Expense) — Ongoing costs**
- Software subscriptions (annual or monthly)
- Hosting/cloud fees
- Support and maintenance contracts (typically 15-20% of license cost annually)
- Staffing (headcount or contractors)
- Ongoing training and change management

**Direct vs. Indirect Costs**
- Direct: Costs directly attributable (e.g., software license for this project)
- Indirect: Shared costs (e.g., portion of IT operations team)
- Allocation method: Transparent, defensible, consistent

**One-time vs. Recurring**
- One-time: Implementation, migration, training
- Recurring: Support, licenses, hosting
- Separate in financial model for clarity

## Benefit Quantification

### Hard Benefits (Easy to quantify and verify)
- **Cost reduction**: Vendor consolidation saves $2M/year (verify with procurement)
- **Revenue increase**: Faster payment clearing attracts $50M in new merchant volume @ 5% margin
- **Headcount reduction**: Automation eliminates 20 FTE roles @ $150K loaded cost
- **Asset sale**: Retiring 500 legacy servers generates $3M in hardware revenue

**Quantification rigor**:
- Unit economics method: Volume × unit impact
- Benchmark method: Industry best-practice savings
- Pilot method: Test on small segment, extrapolate
- Always stress-test: What if we only achieve 60% of modeled benefit?

### Soft Benefits (Real but harder to quantify; use conservative estimates)
- **Risk reduction**: "Reduces regulatory audit findings by estimated 40%" → estimate annual audit cost savings
- **Speed/agility**: "Faster deployment" → estimate time-to-market value or revenue impact
- **Customer experience**: "Improves NPS by 10 points" → estimate customer lifetime value impact
- **Employee engagement**: "Reduces manual work, improves job satisfaction" → estimate attrition reduction value
- **Strategic optionality**: "Enables future product lines" → estimate as % of potential revenue

**Conservative approach**: Quantify soft benefits at 50% of model (or 0% in conservative scenario)

## Sensitivity Analysis & Scenario Planning

### Sensitivity Analysis
Test how NPV changes with variations in key assumptions:
```
BASE CASE NPV: $500K @ 10% discount rate

If deployment timeline slips 6 months:
- NPV = $350K (30% reduction due to delayed benefits)

If benefit realization is only 80% of model:
- NPV = $200K (60% reduction)

If discount rate is 15% (not 10%):
- NPV = $300K (40% reduction)

If annual savings only reach 80% and timeline slips 6 months:
- NPV = $100K (80% reduction; business case still positive)
```

### Scenario Planning
Present three scenarios:

| Scenario | Probability | NPV | IRR | Payback | Key Assumption |
|----------|-------------|-----|-----|---------|-----------------|
| **Conservative** | 30% | $150K | 8% | 4.2 years | 70% benefit realization, 6-month delay |
| **Base Case** | 50% | $500K | 15% | 2.8 years | 100% benefit realization, on-time delivery |
| **Upside** | 20% | $900K | 22% | 2.1 years | 120% benefit realization, early wins captured |
| **Expected Value** | | $455K | 14.2% | 3.0 years | Probability-weighted average |

## Risk Assessment & Mitigation

### Risk Categories
| Risk | Impact | Probability | Mitigation |
|------|--------|-------------|-----------|
| Execution delay | 6 months | Medium (40%) | Experienced vendor, fixed-price contract, weekly governance |
| Benefit realization shortfall | 20% reduction | Medium (35%) | Pilot program, clear success metrics, incentive alignment |
| Vendor viability | Total loss | Low (10%) | Escrow, source code access, support from established vendor |
| Regulatory change | Investment becomes unnecessary | Low (15%) | Flexible architecture, modular approach, phased implementation |

### Contingency Approach
- Add 10-15% schedule contingency (embedded in timeline)
- Create benefit realization reserve: Assume 80-90% success in base case
- Reserve budget for risk items (typically 5-10% of total CapEx)

## Common Technology Business Cases

### Cloud Migration
```
INVESTMENT: $15M year 1 (implementation), $5M/year ongoing (lower than current $12M/year on-prem)
BENEFITS:
- Data center exit: $3M/year OpEx reduction
- License optimization: $2M/year (move to consumption-based)
- Headcount reduction: 12 FTE @ $150K = $1.8M/year
- Improved uptime/disaster recovery: $500K/year risk reduction value
- Total annual benefit: $7.3M

FINANCIALS:
- Year 1: -$15M investment + $3.7M benefit = -$11.3M
- Years 2-5: $7.3M annual benefit
- Payback period: 1.9 years
- 5-year NPV @ 10%: $18.2M
- IRR: 32%
```

### Platform Modernization
```
INVESTMENT: $8M over 2 years (refactor legacy monolith to microservices)
BENEFITS:
- Faster feature delivery: 8 weeks → 2 weeks per feature (estimate $1M/year value in competitive advantage)
- Reduced production incidents: 50% reduction in failures (estimate $500K/year risk value)
- Improved customer experience: Enable real-time payments (attract $100M in volume @ 2% margin = $2M annual)
- Better scalability: Support 5x growth without infrastructure overhaul (enable future growth)
- Headcount reduction: 5 FTE freed for innovation (estimate $750K/year)
- Total quantified benefit: $4.25M/year

FINANCIALS:
- 2-year investment: $8M
- Annual benefit year 3+: $4.25M
- Payback period: 2.4 years (assumes half benefit in year 2)
- 5-year NPV @ 10%: $8.4M
- IRR: 18%
```

### Vendor Consolidation
```
INVESTMENT: $3M (data migration, integration, training)
BENEFITS:
- License savings: Reduce from 4 vendors to 1; negotiate 30% discount on consolidated volume = $2M/year
- Reduced integration overhead: 2 FTE saved = $300K/year
- Improved vendor relationship: Faster support, better roadmap alignment = $200K/year (estimated)
- Total annual benefit: $2.5M/year

FINANCIALS:
- One-time investment: $3M year 1
- Annual benefit year 2+: $2.5M
- Payback period: 1.4 years (conservatively assume 50% benefit in year 1)
- 3-year NPV @ 10%: $4.8M
- IRR: 45%
```

## Stakeholder-Specific Framing

**For the CFO**: Lead with financial returns
- "This investment delivers 32% IRR with 1.9-year payback, well above our 10% cost of capital hurdle rate"
- Show TCO reduction: "Reduces annual OpEx from $12M to $5M over 3 years"
- Include conservative and upside scenarios

**For the CIO**: Lead with strategic value
- "Modernizes our payment platform, reducing technical debt and enabling real-time payments capabilities"
- Show roadmap impact: "Unblocks ability to launch X, Y, Z in 2026"
- Include risk mitigation: "Reduces security exposure and operational incidents"

**For the COO**: Lead with operational efficiency
- "Eliminates 20 FTE of manual processing, improves transaction success rate from 96% to 99%"
- Show customer impact: "Reduces payment settlement time from 2 days to real-time"
- Include resilience: "Disaster recovery improves from 8-hour RPO to 1-hour"

**For the Board**: Lead with strategic context
- "Closes competitive gap vs. peers and enables next-generation payment capabilities"
- Show market opportunity: "Positions LATAM for $X market expansion"
- Include track record: "Vendor has successfully deployed at JPM in North America; benefits realized exceeded targets"

## Output Patterns

### 1-Page Executive Brief
- Recommendation and investment amount
- Strategic rationale (2 sentences)
- Financial summary: NPV, IRR, payback, conservative/base/upside scenarios
- Key risks and mitigation
- Approval checklist and decision date

### Full Business Case Document (8-12 pages)
1. Executive summary
2. Strategic context and current state
3. Problem statement and cost of inaction
4. Options analysis (3-4 options)
5. Recommended approach detail
6. Financial model and projections
7. Risk assessment and mitigation
8. Implementation roadmap and governance
9. Appendix: Detailed assumptions, benchmark data, vendor responses

### Financial Model (Excel/Spreadsheet)
- Assumptions tab (centralized, easy to adjust)
- Year-by-year detail: CapEx, OpEx, benefits, net cash flow
- NPV/IRR calculation (automated)
- Scenario tabs (conservative, base, upside)
- Sensitivity analysis (data table or charts)

## Quality Checks

- [ ] Is my recommendation clear and justified by the financials?
- [ ] Have I stress-tested the model against ±20% variance in key assumptions?
- [ ] Are hard vs. soft benefits clearly separated?
- [ ] Have I identified and mitigated the top 3-4 risks?
- [ ] Would a CFO challenge my numbers? Have I defended each major assumption?
- [ ] Is the payback period realistic for this investment type?
- [ ] Have I compared this business case to benchmarks for similar investments?
- [ ] Is the implementation roadmap actually achievable in the stated timeline?
