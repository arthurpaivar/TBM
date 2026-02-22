---
description: Consolidate and analyze financial data in Excel using TBM frameworks
allowed-tools: Read, Write, Edit, Grep, Glob, Bash, WebSearch, WebFetch, Task
argument-hint: "[Excel file or cost data — e.g., 'Q4 IT cost data', 'consolidate cloud spending by tower']"
---

Consolidate and analyze the data in $ARGUMENTS using the tech-bm-specialist and excel-for-finance skills, with the xlsx skill for Excel execution.

## Layer 1 — Context & Intent

**What:** Define what data needs consolidating and what TBM framework to apply.
**How:** Parse $ARGUMENTS to extract:
- What data is provided? (Excel file, CSV, cost data description, or starting from scratch?)
- What consolidation is needed? (cost pool mapping, tower allocation, R/G/T classification, unit cost calculation)
- What output format? (new Excel workbook, updated existing file, dashboard view)
- What TBM taxonomy layer is the focus? (Cost Pools, Towers, Solutions, Consumers, or full waterfall)
**Why:** Consolidation can range from simple data aggregation to full TBM taxonomy mapping. Understanding the scope determines which templates from excel-for-finance to apply and how much TBM methodology to load.

## Layer 2 — Knowledge Loading

**What:** Load TBM methodology AND Excel execution guidance.
**How:** Read three resources:
- From **tech-bm-specialist**: TBM Taxonomy v5.0.1 layers (Section 2), Cost Allocation Models (Section 3), R/G/T Model (Section 4.1), IT Spend Benchmarks (Section 6.3)
- From **excel-for-finance**: Relevant template structure (Section 2 for TBM templates, Section 3 for portfolio templates), Financial Modeling Standards (Section 1), Execution Workflow (Section 4)
- **Also load the xlsx skill** (from Cowork core skills) for Python/openpyxl execution guidance

The excel-for-finance skill defines WHAT to build. The xlsx skill defines HOW to build it.
**Why:** Excel consolidation requires three knowledge layers: TBM methodology (what categories and allocations), financial template design (what structure and formulas), and Excel technical execution (how to create the file). Missing any one produces suboptimal output.

## Layer 3 — Data Analysis & Consolidation

**What:** Analyze the source data and apply TBM framework consolidation.
**How:**
1. **Read the source data**: If Excel file provided, read with pandas. Identify columns, data types, volume
2. **Map to TBM taxonomy**: Classify each cost line into the appropriate Cost Pool (Layer 1). Use data validation dropdowns from excel-for-finance Section 4.3
3. **Allocate to Towers**: Apply allocation method (Direct, Usage-Based, Weighted, Even-Split) per the tech-bm-specialist Section 3.1
4. **Classify R/G/T**: Tag each initiative/cost line as Run, Grow, or Transform
5. **Calculate unit costs**: Cost per transaction, per user, per service — using formulas from excel-for-finance Section 2.3
6. **Identify anomalies**: Outliers, missing allocations, unusual trends, benchmark deviations

Follow the Excel Financial Modeling Standards (color coding, formula discipline, number formatting) from excel-for-finance Section 1.
**Why:** The step-by-step approach ensures no data is lost in consolidation. Each step builds on the previous — you can't allocate to towers without first classifying cost pools. The TBM framework provides the logic; the Excel template provides the structure.

## Layer 4 — Output & Dashboard

**What:** Produce the consolidated Excel workbook with dashboards and recommendations.
**How:**
1. Build the workbook following excel-for-finance structure (Cover → Assumptions → Data → Analysis → Dashboard → Reference)
2. Create summary dashboard with: total spend composition, R/G/T allocation chart, unit cost trends, top cost categories
3. Apply conditional formatting for visual indicators (variances, benchmarks)
4. Add data validation dropdowns for interactive classification
5. Include benchmark comparison sheet (actual vs. Gartner/TBM Council benchmarks)
6. Document all assumptions in comments and dedicated assumptions sheet
7. Validate zero formula errors before delivery

Save to outputs folder and provide computer:// link.
**Why:** The dashboard transforms raw data into decision-grade information. The structured workbook allows stakeholders to explore the data while the summary provides the key insights. Zero formula errors is non-negotiable for financial deliverables.

**Output**: A professional Excel workbook consolidating the source data using TBM Taxonomy v5.0.1 — with cost pool mapping, tower allocation, R/G/T classification, unit cost calculations, benchmark comparisons, and a summary dashboard. Color-coded, formula-validated, ready for CIO/CFO review.
