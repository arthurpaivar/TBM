---
description: Assess an IT application portfolio using TIME model and health scoring
allowed-tools: Read, Write, Edit, Grep, Glob, Bash, WebSearch, WebFetch, Task
argument-hint: "[portfolio scope — e.g., 'payments application portfolio', 'CIB technology portfolio assessment']"
---

Assess the IT portfolio for $ARGUMENTS using the it-portfolio-management skill.

## Layer 1 — Context & Intent

**What:** Define what portfolio is being assessed and what the user needs.
**How:** Parse $ARGUMENTS to extract:
- What's the portfolio scope? (full organization, business unit, product line, technology stack)
- Is there existing data? (application list, cost data, health scores, or starting from scratch?)
- What assessment type? (full rationalization, health check, modernization planning, cost analysis)
- What decision is this supporting? (budget planning, modernization investment, tech debt reduction, M&A due diligence)
**Why:** Portfolio assessments vary from quick triage (which apps to retire?) to comprehensive governance reviews (full TIME + health + cost analysis). Matching the depth to the need prevents wasted effort.

## Layer 2 — Knowledge Loading

**What:** Load the portfolio management skill and extract the assessment frameworks.
**How:** Read the it-portfolio-management SKILL.md. Extract based on assessment type:
- For rationalization: TIME Model (Section 1.1), Modernization Patterns 6Rs (Section 1.4)
- For health assessment: 6-Dimension Health Assessment (Section 1.2), Composite scoring formula
- For lifecycle: Application Lifecycle Management (Section 1.3), governance gates
- For analytics: Portfolio Analytics views (Section 1.5), benchmarks (Section 1.6)
- For investment: Investment Governance (Section 2), Budget Planning (Section 3)

If the assessment needs an Excel deliverable, also load excel-for-finance Section 3.1 (Application Portfolio Assessment template).
**Why:** The it-portfolio-management skill contains deep, structured frameworks for every type of portfolio assessment. Loading the right sections ensures the assessment applies the correct methodology.

## Layer 3 — Assessment Execution

**What:** Produce a structured portfolio assessment using the appropriate frameworks.
**How:** Follow the Portfolio Assessment output pattern, building:

1. **Portfolio Inventory**: List applications with key attributes (name, capability, stack, age, cost)
2. **Health Scoring**: Score each application across 6 dimensions (Business Value 25%, Technical Health 20%, Operational Stability 20%, Cost Efficiency 15%, Compliance & Risk 10%, User Satisfaction 10%)
3. **TIME Classification**: Classify each application (Tolerate/Invest/Migrate/Eliminate) based on health scores, strategic value, and platform fit
4. **Portfolio Analytics**: Generate key views — TIME distribution, cost Pareto, age distribution, capability heat map, redundancy map
5. **Risk Assessment**: Identify high-risk applications (low health + high criticality)
6. **Modernization Roadmap**: For Migrate/Eliminate apps, recommend 6Rs pattern and sequencing

If the user provides an application list or Excel file, work with the actual data. If starting from scratch, provide the assessment framework and template.
**Why:** The comprehensive assessment (health + TIME + analytics + risk) gives the CIO a complete picture. The 6-dimension health scoring is weighted to prioritize business value and technical health — the dimensions most relevant for investment decisions.

## Layer 4 — Recommendations & Output

**What:** Deliver portfolio recommendations with quantified impact.
**How:**
1. Quantify the opportunity: estimated savings from retirement, modernization benefits, risk reduction
2. Prioritize recommendations: Retire first (quick cost wins) → Rehost (volume) → Replatform → Refactor (strategic)
3. Compare against benchmarks: ~30% retirement candidates (Gartner), portfolio age distribution norms
4. Build a phased roadmap: Wave 1 (0-6mo quick wins) → Wave 2 (6-12mo optimization) → Wave 3 (12-24mo transformation)
5. Include confidence calibration for estimates

If an Excel deliverable is requested, build the Application Portfolio Assessment workbook from excel-for-finance Section 3.1 — with inventory sheet, health scorecard, dashboard, and TIME analysis.
**Why:** The quantified recommendations transform the assessment from a report into an investment case. The phased roadmap provides a clear execution path. Benchmarks ground the recommendations in industry reality.

**Output**: A structured portfolio assessment with TIME classification, 6-dimension health scores, portfolio analytics views, risk assessment, modernization roadmap, and quantified recommendations. Optionally delivered as a professional Excel workbook.
