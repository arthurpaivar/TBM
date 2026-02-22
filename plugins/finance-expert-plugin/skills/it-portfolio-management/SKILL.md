---
name: it-portfolio-management
description: >
  This skill should be used when the user asks about "IT portfolio", "application portfolio",
  "portfolio management", "app rationalization", "application lifecycle", "modernization roadmap",
  "tech debt assessment", "application health", "buy vs build", "sunset an app",
  "migration strategy", "IT investment", "portfolio optimization", "demand management",
  "project portfolio", "program portfolio", "investment governance", "IT budget",
  "capacity planning", "resource allocation", "IT financial management", "ITFM",
  "TIME model", "application scoring", "portfolio analytics", "6Rs",
  "investment prioritization", "WSJF", "value vs effort", "portfolio dashboard",
  "application lifecycle management", "decommission", "retire application",
  or needs frameworks for managing technology portfolios and investments.
  Use whenever the user needs portfolio governance, app rationalization, or investment prioritization guidance.
version: 3.0.0
---

# Skill — IT Portfolio Management

**Expert in IT portfolio management with deep knowledge spanning application portfolio rationalization, IT investment governance, demand management, financial management (ITFM), and portfolio analytics for enterprise payments technology.** This skill provides authoritative guidance connecting technology portfolios to business value using TBM-aligned financial frameworks. It serves as the modular portfolio knowledge base that other plugins reference — consulting for portfolio benchmarks, technology for modernization patterns (6Rs), communication for portfolio narratives.

**Core Principles**: SPAR Framework, Pyramid Principle, SCQA Pattern, MECE Decomposition, Confidence Calibration, Source Attribution, Practical & Adaptable — these govern all outputs from this skill.

**Trigger keywords**: IT portfolio, application portfolio, portfolio management, app rationalization, application lifecycle, modernization roadmap, tech debt assessment, application health, buy vs build, sunset, migration strategy, IT investment, portfolio optimization, demand management, investment governance, capacity planning, ITFM, TIME model, application scoring, portfolio analytics, 6Rs, WSJF, investment prioritization, decommission.

## Section 1 — Application Portfolio Management

### 1.1 TIME Model (Portfolio Rationalization)
Classify applications into four categories (MECE):

| Category | Action | Investment | Criteria |
|----------|--------|-----------|----------|
| **Tolerate** | Maintain as-is, minimal spend | Run only | Low strategic value, stable, acceptable risk |
| **Invest** | Enhance, scale, modernize | Grow | High strategic value, needs capability improvement |
| **Migrate** | Move to modern platform | Transform | Good capability, wrong platform (legacy infra, outdated stack) |
| **Eliminate** | Decommission, consolidate, replace | Negative (cost recovery) | Redundant, obsolete, replaced by other solutions |

**Assessment criteria per application**:
- Application Name, Business Capability Mapped, TIME Category, Rationale
- Estimated Migration/Retirement Effort (T-shirt: S/M/L/XL)
- Risk Level (High/Medium/Low), Dependencies (upstream/downstream)
- Annual Run Cost, Business Criticality Score (1-5)

### 1.2 Application Health Assessment (6 Dimensions)
Score each application 1-5 across:

1. **Business Value** (weight: 25%): Revenue impact, strategic alignment, user adoption, business criticality
2. **Technical Health** (weight: 20%): Code quality, tech debt level, scalability, security posture, architecture fitness
3. **Operational Stability** (weight: 20%): Incident frequency, MTTR, SLA compliance, monitoring maturity
4. **Cost Efficiency** (weight: 15%): TCO, cost per transaction, licensing overhead, infrastructure utilization
5. **Compliance & Risk** (weight: 10%): Regulatory compliance, data classification, DR/BCP readiness, vendor risk
6. **User Satisfaction** (weight: 10%): End-user feedback, adoption rate, support ticket volume, NPS

**Composite Health Score** = Weighted average → classify as: Healthy (4-5), Stable (3-3.9), At Risk (2-2.9), Critical (1-1.9)

### 1.3 Application Lifecycle Management
Phases with governance gates:

| Phase | Activities | Gate |
|-------|-----------|------|
| **Ideation** | Business case, demand intake | Investment committee approval |
| **Design** | Architecture, security, data design | Architecture Review Board |
| **Build** | Development, testing, integration | Security & compliance review |
| **Deploy** | Production deployment, monitoring setup | Change Advisory Board |
| **Operate** | Run, monitor, optimize, support | Quarterly health review |
| **Optimize** | Performance tuning, cost reduction | Annual portfolio review |
| **Retire** | Data migration, user transition, decommission | Retirement checklist sign-off |

### 1.4 Modernization Patterns (6Rs)

| Pattern | Change Level | Time | Cost | Best When |
|---------|-------------|------|------|-----------|
| **Rehost** (Lift-and-shift) | Minimal | Fast | Low | Quick wins, data center exits |
| **Replatform** | Minor optimization | Medium | Medium | Database migration, managed services |
| **Refactor** | Re-architect | Long | High | Core differentiator, cloud-native target |
| **Repurchase** | Replace with SaaS | Medium | Medium | Commodity capability, mature SaaS market |
| **Retain** | No change | None | Minimal | Not worth migrating yet |
| **Retire** | Decommission | Short | Negative | Redundant, functionality absorbed elsewhere |

**Sequencing guidance**: Start with Retire (quick cost wins) → Rehost (volume migration) → Replatform (optimization) → Refactor (strategic investment).

### 1.5 Portfolio Analytics
Key portfolio-level views:

- **Business Capability Heat Map**: Applications mapped to capabilities, colored by health score
- **Technology Stack Distribution**: Languages, frameworks, databases — identify concentration risk
- **Age Distribution**: Application age histogram — flag aging assets (>10 years = high risk)
- **Cost Distribution**: Pareto chart (80/20 rule — typically 20% of apps consume 80% of budget)
- **Redundancy Map**: Overlapping applications serving the same capability
- **TIME Distribution**: % of portfolio in each TIME category — track quarterly
- **Risk Exposure**: Applications with combined low health + high business criticality

### 1.6 Portfolio Benchmarks
- ~30% of enterprise apps are candidates for retirement (Gartner)
- Average large enterprise portfolio: 300-1000+ applications
- Technical debt typically represents 20-40% of application value
- Modernization timeline: 12-24 months for significant portfolio transformation
- Cloud migration: 3-5 year programs for full portfolio, 6-12 months per wave
- Annual rationalization target: 5-10% of portfolio retired or consolidated

## Section 2 — IT Investment Governance

### 2.1 Investment Portfolio Structure (3 Tiers)
1. **Strategic Investments** (>$5M): Transformational programs aligned to business strategy. CIO/CFO approval, quarterly reviews
2. **Tactical Investments** ($500K–$5M): Department-level projects enhancing capabilities. VP approval, monthly tracking
3. **Operational Investments** (<$500K): BAU maintenance, break-fix, compliance. Director approval, sprint-level tracking

### 2.2 Demand Management Process
Structured pipeline from idea to funded initiative:

1. **Intake**: Standardized demand request (business need, strategic alignment, estimated effort, expected value)
2. **Assessment**: Technical feasibility, capacity check, dependency analysis, architecture fit
3. **Prioritization**: Score using WSJF, value-vs-effort matrix, or strategic alignment model
4. **Approval**: Investment committee at threshold-appropriate level
5. **Allocation**: Capacity assigned to approved demand (people, infrastructure, budget)
6. **Tracking**: Progress against milestones, benefits realization, budget consumption

### 2.3 Investment Prioritization Methods

| Method | Formula/Approach | Best For |
|--------|-----------------|----------|
| **WSJF** | Cost of Delay / Job Duration | Agile teams, SAFe organizations |
| **Value vs. Effort** | 2×2 matrix (High Value/Low Effort = do first) | Quick triage, portfolio workshops |
| **Scoring Model** | Weighted criteria (strategic fit, ROI, risk, capacity) | Investment committees, formal governance |
| **MoSCoW** | Must/Should/Could/Won't | Requirements prioritization within projects |

### 2.4 Investment Decision Framework
Evaluate proposals across five dimensions:

1. **Strategic Fit** (30%): Alignment to business strategy, OKRs, technology roadmap
2. **Financial Merit** (25%): NPV, IRR, payback period, TCO over 3–5 years
3. **Risk Profile** (20%): Technical, delivery, adoption, regulatory, vendor risks
4. **Capacity Impact** (15%): Required skills, team availability, infrastructure needs
5. **Dependencies** (10%): Cross-portfolio dependencies, integration requirements

### 2.5 Run / Grow / Transform Classification
Aligned with TBM Framework 2.0 (reference tech-bm-specialist Section 4.1):
- **Run**: Maintaining current services (target: <55% best-in-class)
- **Grow**: Enhancing existing capabilities (target: 20–30%)
- **Transform**: New capabilities and innovation (target: 15–25%)
- Track allocation quarterly, report trends to leadership

## Section 3 — IT Financial Management (ITFM)

### 3.1 Budget Planning Cycle
Annual planning integrated with portfolio management:

| Phase | Timing | Activities |
|-------|--------|-----------|
| **Strategic Planning** | Q2–Q3 | Align technology investments with business strategy |
| **Demand Collection** | Q3 | Gather project demand from business units |
| **Capacity Planning** | Q3–Q4 | Match demand to capacity (people, infrastructure, budget) |
| **Budget Formulation** | Q4 | Bottom-up budget with top-down targets |
| **Approval** | Q4/Q1 | Investment committee and CFO/CIO approval |
| **Execution & Tracking** | Ongoing | Monthly actuals vs. plan, quarterly reforecast |

### 3.2 Unit Economics for Payments
Key unit cost metrics:

| Metric | Formula | Benchmark Direction |
|--------|---------|-------------------|
| **Cost per Transaction** | Total tech cost / transaction volume (by rail) | ↓ Lower is better |
| **Cost per User** | Total tech cost / active users | ↓ Lower is better |
| **Cost per Service** | Total allocated cost / service consumption | ↓ Lower is better |
| **Infra Unit Cost** | Compute cost / vCPU-hour; Storage cost / TB | ↓ Lower is better |
| **Delivery Cost** | Development cost / story point or feature | ↓ Lower is better |

### 3.3 Budget Variance Analysis
Standard variance categories (MECE):
- **Volume variance**: More/less transactions or users than planned
- **Rate variance**: Unit cost changes (rate increases, efficiency gains)
- **Mix variance**: Shift between cost categories (cloud adoption increasing)
- **Timing variance**: Spend shifted between quarters
- **New demand**: Unplanned initiatives added after budget approval

## Section 4 — IT Cost Breakdown & Prioritization

### 4.1 Cost Breakdown Structure (CBS)
Hierarchical decomposition of IT costs:

```
Total IT Spend
├── By Nature (Cost Pool): Labor / Software / Hardware / Cloud / Facilities / Telecom
├── By Function (Tower): Compute / Storage / Network / Application / Data / Security / Delivery
├── By Purpose (R/G/T): Run / Grow / Transform
├── By Consumer (BU): Business Unit A / B / C
└── By Initiative: Program 1 / Project 2 / BAU
```

### 4.2 Cost Optimization Levers
Structured by impact and effort:

**Quick Wins (0–3 months):**
- License rationalization (unused software, shelfware)
- Cloud rightsizing (oversized instances)
- Vendor contract renegotiation (volume discounts)

**Medium-Term (3–12 months):**
- Application retirement (eliminate TIME category)
- Cloud commitment optimization (RIs, savings plans)
- Labor model optimization (onshore/offshore mix)

**Strategic (12+ months):**
- Platform consolidation (reduce technology sprawl)
- Automation (reduce manual operational costs)
- Architecture modernization (reduce run costs structurally)

## Output Patterns

### Portfolio Assessment
```
PORTFOLIO: [Organization/Business Unit]
ASSESSMENT DATE: [Date]
TOTAL APPLICATIONS: [N]

TIME DISTRIBUTION:
- Tolerate: [N] ([%]) — Annual Run Cost: [$X]
- Invest: [N] ([%]) — Annual Run Cost: [$X]
- Migrate: [N] ([%]) — Annual Run Cost: [$X]
- Eliminate: [N] ([%]) — Annual Run Cost: [$X]

HEALTH DISTRIBUTION:
- Healthy (4-5): [N] ([%])
- Stable (3-3.9): [N] ([%])
- At Risk (2-2.9): [N] ([%])
- Critical (1-1.9): [N] ([%])

PORTFOLIO METRICS:
- Total annual run cost: [$X]
- Average application age: [X] years
- Tech debt estimate: [$X] ([%] of portfolio value)
- Redundancy: [N] capabilities with overlapping apps

TOP RISKS:
1. [Risk] — [Impact] — [Mitigation]

RECOMMENDATIONS:
1. Retire: [N] applications → [$X] annual savings
2. Modernize: [N] applications → [Expected benefit]
3. Invest: [N] applications → [Strategic capability gained]

CONFIDENCE: [High/Medium/Low]
```

### Investment Governance Report
```
PERIOD: [Quarter/Year]
PORTFOLIO: [Organization]

DEMAND PIPELINE:
- New requests: [N] — Total estimated value: [$X]
- Approved: [N] — Funded: [$X]
- Deferred: [N] — Reason: [capacity/strategic fit/budget]

ACTIVE INVESTMENTS:
- Total: [N] initiatives — [$X] total spend
- Run: [$X] ([%]) | Grow: [$X] ([%]) | Transform: [$X] ([%])

STATUS:
- On Track: [N] ([%])
- At Risk: [N] ([%]) — [Top issues]
- Behind: [N] ([%]) — [Recovery actions]

VALUE REALIZATION:
- Benefits planned: [$X]
- Benefits realized: [$X] ([%])
- At-risk benefits: [$X]

BUDGET PERFORMANCE:
- Plan: [$X] | Actual: [$X] | Variance: [$X] ([%])
- Forecast: [$X]

RECOMMENDATIONS:
1. [Portfolio rebalancing action]
2. [At-risk initiative intervention]
```

## Quality Checks

- [ ] Is the TIME model applied correctly with clear criteria per category?
- [ ] Does the application health assessment use all 6 dimensions with weights?
- [ ] Are modernization patterns (6Rs) applied with appropriate sequencing?
- [ ] Is the investment governance structure aligned with organizational thresholds?
- [ ] Are prioritization methods appropriate for the context (WSJF, scoring, value-effort)?
- [ ] Is the budget planning cycle realistic and integrated with demand management?
- [ ] Are unit economics calculated with proper denominators?
- [ ] Are benchmarks attributed to sources (Gartner, TBM Council)?
- [ ] Is the output suitable for CIO-level portfolio governance conversations?

---

**Confidence Calibration**: High confidence for TIME model, 6Rs patterns, investment governance structures, budget planning cycles — well-established frameworks. Medium confidence for specific benchmarks and portfolio analytics — vary significantly by organization size and context. Low confidence for cost-per-transaction benchmarks — highly dependent on payment rail and volume, recommend organization-specific data.

**Triggers**: Activate when user needs portfolio rationalization, application assessment, investment prioritization, demand management, modernization roadmaps, or portfolio governance reports for CIO conversations.
