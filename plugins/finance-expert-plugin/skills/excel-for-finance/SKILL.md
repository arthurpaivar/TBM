---
name: excel-for-finance
description: >
  This skill should be used when the user asks to "create Excel", "build spreadsheet",
  "financial model in Excel", "TBM Excel", "cost model spreadsheet", "budget template",
  "portfolio dashboard Excel", "investment tracker", "cost allocation Excel",
  "consolidate costs in Excel", "Excel template", "financial dashboard",
  "pivot table", "cost breakdown Excel", "unit cost spreadsheet",
  "R/G/T Excel", "run grow transform spreadsheet", "FinOps dashboard",
  "application portfolio Excel", "TIME model Excel", "health scorecard Excel",
  "business case Excel", "NPV IRR Excel", "TCO spreadsheet",
  or needs to create, analyze, or consolidate Excel-based financial outputs
  using TBM frameworks and IT finance methodologies.
  Use whenever the user needs Excel deliverables for IT financial management.
version: 3.0.0
---

# Skill — Excel for Finance

**Expert in designing and building Excel-based financial models, dashboards, and templates for Technology Business Management and IT portfolio governance.** This skill bridges the gap between TBM/portfolio knowledge (from sibling skills) and Excel execution (from the Cowork xlsx skill). It defines the data structures, formulas, layouts, and validation rules for finance-specific Excel deliverables. It serves as the modular Excel knowledge base that commands use to produce professional financial spreadsheets.

**Core Principles**: SPAR Framework, Pyramid Principle, MECE Decomposition, Financial Modeling Best Practices (color coding, formula discipline, assumption separation), Practical & Adaptable — these govern all outputs from this skill.

**Trigger keywords**: create Excel, build spreadsheet, financial model, TBM Excel, cost model, budget template, portfolio dashboard, investment tracker, cost allocation, consolidate costs, Excel template, financial dashboard, pivot table, cost breakdown, unit cost spreadsheet, R/G/T Excel, FinOps dashboard, application portfolio Excel, TIME model, health scorecard, business case Excel, NPV IRR, TCO spreadsheet.

## Section 1 — Excel Financial Modeling Standards

### 1.1 Color Coding Convention (Industry Standard)

| Color | Usage | Examples |
|-------|-------|---------|
| **Blue text** (RGB: 0,0,255) | Hardcoded inputs and assumptions | Growth rates, unit costs, headcount |
| **Black text** (RGB: 0,0,0) | All formulas and calculations | SUM, NPV, derived metrics |
| **Green text** (RGB: 0,128,0) | Cross-sheet references | Links pulling from other worksheets |
| **Red text** (RGB: 255,0,0) | External data links | References to other workbooks |
| **Yellow background** (RGB: 255,255,0) | Key assumptions needing attention | Cells requiring user input |

### 1.2 Number Formatting Standards

| Data Type | Format | Example |
|-----------|--------|---------|
| Currency | $#,##0 with unit in header | "Revenue ($K)" |
| Percentages | 0.0% (one decimal) | 65.3% |
| Years | Text strings | "2025" not "2,025" |
| Negative numbers | Parentheses | ($1,234) not -$1,234 |
| Zeros | Dash format | "-" not "0" |
| Multiples | 0.0x | 2.5x |

### 1.3 Formula Discipline
- **Separate assumptions**: All inputs in dedicated assumption cells, never hardcoded in formulas
- **Cell references**: Use =B5*(1+$B$6) not =B5*1.05
- **Consistent formulas**: Same formula pattern across all projection periods
- **Error prevention**: IFERROR wrappers on division operations, range validation
- **Documentation**: Comment cells with source attribution ("Source: Gartner IT Spending 2025")

### 1.4 Workbook Structure Standards
For TBM/finance workbooks, follow this sheet ordering:

1. **Cover/Summary**: Executive dashboard with key metrics and navigation
2. **Assumptions**: All input parameters in one place (blue text, yellow background)
3. **Data/Input**: Raw data import sheets
4. **Analysis**: Calculation and analysis sheets
5. **Output/Dashboard**: Formatted output views for stakeholders
6. **Reference**: Lookup tables, taxonomy mappings, benchmarks

## Section 2 — TBM Excel Templates

### 2.1 TBM Taxonomy Mapping Workbook
Sheet structure:

**Sheet 1: Cost Pools (Layer 1)**
| Column | Content |
|--------|---------|
| A | GL Account Code |
| B | GL Account Name |
| C | Cost Pool Category (dropdown: Internal Labor, External Labor, Hardware, Software, Cloud Services, Facilities, Telecom, Other) |
| D | Monthly Amount (Jan–Dec) |
| E | Annual Total (SUM formula) |
| F | % of Total (formula) |

**Sheet 2: Tower Mapping (Layer 2)**
| Column | Content |
|--------|---------|
| A | Cost Pool Source |
| B | Resource Domain (dropdown: Infrastructure, Application & Platform, Data, Security & Risk, Management) |
| C | Tower (dropdown: contextual based on Domain) |
| D | Allocation Method (dropdown: Direct, Usage-Based, Weighted, Even-Split) |
| E | Allocation Key (e.g., "transaction volume", "headcount") |
| F | Allocated Amount |

**Sheet 3: Solutions Mapping (Layer 3)**
**Sheet 4: Consumer Mapping (Layer 4)**
**Sheet 5: Summary Dashboard** — Waterfall chart from Cost Pools → Towers → Solutions → Consumers

### 2.2 Run/Grow/Transform Tracker
Sheet structure:

**Sheet 1: Investment Classification**
| Column | Content |
|--------|---------|
| A | Initiative ID |
| B | Initiative Name |
| C | Sponsor |
| D | Classification (dropdown: Run/Grow/Transform) |
| E | Investment Type (dropdown: Cost Reduction, Revenue Growth, Risk Mitigation, Experience, Compliance) |
| F | Annual Budget |
| G | YTD Spend |
| H | Variance (formula) |
| I | Status (dropdown: On Track, At Risk, Behind) |

**Sheet 2: R/G/T Dashboard**
- Pie chart: R/G/T allocation (current period)
- Trend line: R/G/T allocation over last 4 quarters
- Benchmark comparison: Actual vs. target vs. industry average
- Conditional formatting: Red if Run >65%, Green if Transform >15%

### 2.3 Unit Cost Dashboard
Track cost per transaction by payment rail:

| Column | Content |
|--------|---------|
| A | Payment Rail (ACH, Wire, Card, RTP/FedNow) |
| B | Total Tech Cost Allocated |
| C | Transaction Volume |
| D | Cost per Transaction (B/C formula) |
| E | Prior Period Cost/Txn |
| F | Change % (formula) |
| G | Benchmark (industry average) |
| H | Variance to Benchmark |

Sparkline charts for 12-month trend per rail.

## Section 3 — Portfolio Excel Templates

### 3.1 Application Portfolio Assessment
Sheet structure:

**Sheet 1: Application Inventory**
| Column | Content |
|--------|---------|
| A | App ID |
| B | Application Name |
| C | Business Capability |
| D | Technology Stack |
| E | Age (years) |
| F–K | Health Scores (6 dimensions, 1-5) |
| L | Composite Health Score (weighted formula) |
| M | TIME Classification (formula based on scores + dropdown override) |
| N | Annual Run Cost |
| O | Business Criticality (1-5) |
| P | Recommended Action |

**Sheet 2: Portfolio Dashboard**
- Bubble chart: Business Value (X) vs. Technical Health (Y), sized by Annual Cost
- Stacked bar: TIME distribution
- Heat map: Business Capability × Health Score
- Pareto: Top 20 apps by cost (80/20 analysis)

**Sheet 3: Health Scorecard**
- Radar chart per application (6 dimensions)
- Conditional formatting: Red (<2), Yellow (2-3), Green (>3)

### 3.2 Business Case Financial Model
Sheet structure:

**Sheet 1: Assumptions**
- All input parameters with blue text, yellow background
- Growth rates, discount rate (WACC), inflation, headcount costs
- Scenario toggles (Base/Optimistic/Pessimistic)

**Sheet 2: Cost Model (5-Year)**
| Row Categories | Year 1 | Year 2 | Year 3 | Year 4 | Year 5 |
|---------------|--------|--------|--------|--------|--------|
| Development costs | | | | | |
| Infrastructure costs | | | | | |
| License/subscription | | | | | |
| Operations & support | | | | | |
| **Total Cost** | | | | | |

**Sheet 3: Benefits Model (5-Year)**
| Row Categories | Year 1 | Year 2 | Year 3 | Year 4 | Year 5 |
|---------------|--------|--------|--------|--------|--------|
| Cost avoidance | | | | | |
| Revenue uplift | | | | | |
| Efficiency gains (FTE) | | | | | |
| Risk reduction (quantified) | | | | | |
| **Total Benefits** | | | | | |

**Sheet 4: Financial Summary**
- NPV = NPV(discount_rate, cash_flows) — formula referencing assumption cell
- IRR = IRR(cash_flows)
- Payback Period = calculated iteratively
- ROI = (Total Benefits - Total Costs) / Total Costs
- Sensitivity table: NPV at different discount rates and benefit scenarios

### 3.3 Demand Pipeline Tracker
Sheet structure:
- Demand intake form (structured input)
- Scoring matrix (WSJF or value-effort)
- Pipeline waterfall (Submitted → Assessed → Approved → Funded → In Progress → Complete)
- Capacity allocation view (team/quarter)

## Section 4 — Excel Execution Workflow

### 4.1 How This Skill Connects to the xlsx Skill
This skill defines **what to build** (data structures, formulas, layouts). The Cowork `xlsx` skill defines **how to build it** (openpyxl code, formatting commands, chart creation). When a command needs an Excel deliverable:

1. **This skill** provides: Template structure, column definitions, formula logic, validation rules, chart specifications
2. **The xlsx skill** provides: Python/openpyxl execution, formatting best practices, LibreOffice recalculation, error prevention

### 4.2 Execution Checklist
Before generating any Excel file:
- [ ] Load the xlsx skill (SKILL.md) for technical execution guidance
- [ ] Define sheet structure from this skill's templates
- [ ] Identify all formulas and validate logic
- [ ] Set up data validation (dropdowns) for classification fields
- [ ] Apply color coding standards (Section 1.1)
- [ ] Apply number formatting standards (Section 1.2)
- [ ] Add conditional formatting for visual indicators
- [ ] Create charts/dashboards on dedicated output sheets
- [ ] Add cell comments for assumptions documentation
- [ ] Validate zero formula errors before delivery

### 4.3 Data Validation Dropdowns
Standard dropdown values for TBM/portfolio Excel files:

| Field | Dropdown Values |
|-------|----------------|
| Cost Pool | Internal Labor, External Labor, Hardware, Software, Cloud Services, Facilities, Telecom, Other |
| Resource Domain | Infrastructure, Application & Platform, Data, Security & Risk, Management |
| R/G/T Classification | Run, Grow, Transform |
| TIME Category | Tolerate, Invest, Migrate, Eliminate |
| Status | On Track, At Risk, Behind, Complete |
| Risk Level | High, Medium, Low |
| Priority | Critical, High, Medium, Low |
| Allocation Method | Direct, Usage-Based, Weighted, Even-Split |

## Output Patterns

### Excel Template Specification
```
TEMPLATE: [Name]
PURPOSE: [What it solves]
AUDIENCE: [Who uses it]

SHEETS:
1. [Sheet Name] — [Purpose] — [Key columns/rows]
2. [Sheet Name] — [Purpose] — [Key columns/rows]

KEY FORMULAS:
- [Cell/Range]: [Formula logic] — [What it calculates]

CHARTS:
- [Chart type]: [Data source] — [What it shows]

VALIDATION:
- [Field]: [Dropdown values or validation rule]

CONDITIONAL FORMATTING:
- [Rule]: [When/What color]

ASSUMPTIONS SECTION:
- [Parameter]: [Default value] — [Source]
```

### Excel Consolidation Output
```
INPUT: [Source file(s) or data description]
TBM FRAMEWORK APPLIED: [Which taxonomy layers, which classification]

CONSOLIDATION LOGIC:
1. [Step] — [What data, what transformation]
2. [Step] — [Aggregation level, grouping]

OUTPUT SHEETS:
1. [Sheet] — [Content summary]

KEY METRICS CALCULATED:
- [Metric]: [Formula] — [Value]

ANOMALIES/TRENDS:
1. [Finding] — [Implication]

RECOMMENDATIONS:
1. [Action] — [Expected impact]
```

## Quality Checks

- [ ] Does the Excel file follow color coding standards (blue inputs, black formulas)?
- [ ] Are all assumptions separated in dedicated cells (never hardcoded in formulas)?
- [ ] Are number formats consistent (currency with headers, percentages with 1 decimal)?
- [ ] Are data validation dropdowns applied for all classification fields?
- [ ] Does the workbook have zero formula errors (#REF!, #DIV/0!, #VALUE!, #N/A)?
- [ ] Is conditional formatting applied for visual indicators (health scores, status, variances)?
- [ ] Do charts/dashboards use dedicated output sheets (not mixed with data)?
- [ ] Are TBM taxonomy terms used correctly in column headers and categories?
- [ ] Is the workbook structure logical (Cover → Assumptions → Data → Analysis → Dashboard → Reference)?

---

**Confidence Calibration**: High confidence for financial modeling standards (color coding, formula discipline, number formatting) — these are industry conventions. High confidence for TBM template structures — aligned with Taxonomy v5.0.1. Medium confidence for specific chart/visualization recommendations — depend on data density and audience preference.

**Triggers**: Activate when user needs Excel-based financial deliverables — TBM models, portfolio dashboards, business cases, cost allocation workbooks, investment trackers, or any spreadsheet that combines IT finance data with TBM/portfolio frameworks. Always load alongside the xlsx skill for technical execution.
