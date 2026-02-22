---
description: Build a TBM cost model or taxonomy mapping in Excel
allowed-tools: Read, Write, Edit, Grep, Glob, Bash, WebSearch, WebFetch, Task
argument-hint: "[TBM model type — e.g., 'taxonomy mapping for payments IT', 'R/G/T investment tracker', 'unit cost dashboard']"
---

Build a TBM model for $ARGUMENTS using the tech-bm-specialist and excel-for-finance skills, with the xlsx skill for Excel execution.

## Layer 1 — Context & Intent

**What:** Define what TBM model needs to be built and its purpose.
**How:** Parse $ARGUMENTS to extract:
- What model type? (taxonomy mapping, R/G/T tracker, unit cost dashboard, cost allocation model, budget template, FinOps dashboard)
- What's the scope? (full organization, business unit, specific cost pool, specific tower)
- Is there existing data to incorporate? (GL data, cost reports, or building a blank template?)
- Who's the audience? (CIO for strategy, Finance for cost transparency, VP for operations)
**Why:** TBM models serve different stakeholder views (Finance, IT, Business — see tech-bm-specialist Section 1.6). The model type and audience determine which template to use and what level of detail to build.

## Layer 2 — Knowledge Loading

**What:** Load TBM methodology, Excel template design, and technical execution guidance.
**How:** Read three resources:
- From **tech-bm-specialist**: TBM Taxonomy v5.0.1 structure (Section 2), Cost Allocation Models (Section 3), Investment Management (Section 4), Connected Standards (Section 5), Maturity Model (Section 6)
- From **excel-for-finance**: Select the relevant template from Section 2 (TBM templates):
  - 2.1 TBM Taxonomy Mapping Workbook (for full taxonomy models)
  - 2.2 R/G/T Tracker (for investment classification)
  - 2.3 Unit Cost Dashboard (for cost per transaction analysis)
  - Also reference Section 1 (Financial Modeling Standards) and Section 4 (Execution Workflow)
- **Also load the xlsx skill** for Python/openpyxl execution

**Why:** TBM models are knowledge-heavy — getting the taxonomy layers right, the allocation methods correct, and the output professional requires all three knowledge sources working together.

## Layer 3 — Model Construction

**What:** Build the TBM model following the template specification.
**How:** Execute the model construction in stages:

1. **Set up workbook structure** (from excel-for-finance Section 1.4):
   - Cover/Summary → Assumptions → Data/Input → Analysis → Dashboard → Reference

2. **Build the taxonomy layers** (from tech-bm-specialist Section 2):
   - Cost Pools sheet: GL account mapping to 9 cost pool categories
   - Tower Mapping sheet: Cost pool allocation to Resource Domains and Towers
   - Solutions sheet: Tower costs mapped to business-facing services
   - Consumers sheet: Solution costs allocated to business units/products

3. **Apply allocation logic** (from tech-bm-specialist Section 3):
   - Set up allocation methods per tower (Direct, Usage-Based, Weighted, Even-Split)
   - Include allocation keys and formulas
   - Target: >70% direct + usage-based allocation

4. **Build classification** (from tech-bm-specialist Section 4):
   - R/G/T classification per initiative with dropdown validation
   - Investment typification (strategic alignment, value type, horizon)

5. **Create dashboards** (from excel-for-finance templates):
   - Cost waterfall: Cost Pools → Towers → Solutions → Consumers
   - R/G/T pie chart with trend and benchmark comparison
   - Unit cost tracking with sparklines
   - Conditional formatting for benchmarks and variances

6. **Apply standards** (from excel-for-finance Section 1):
   - Color coding (blue inputs, black formulas, green cross-references)
   - Number formatting ($#,##0 currency, 0.0% percentages)
   - Data validation dropdowns for all classification fields
   - Cell comments for assumption documentation

**Why:** The staged approach ensures each taxonomy layer builds correctly on the previous one. The allocation logic is the hardest part — if Cost Pool → Tower mapping is wrong, everything downstream is wrong.

## Layer 4 — Validation & Delivery

**What:** Validate the model and deliver as a professional Excel workbook.
**How:**
1. **Formula validation**: Check zero errors (#REF!, #DIV/0!, #VALUE!, #N/A)
2. **Allocation validation**: Total allocated = Total input (no cost leakage, no double-counting)
3. **Benchmark validation**: Compare R/G/T split, IT spend ratios against industry benchmarks
4. **Visual validation**: Charts render correctly, conditional formatting is accurate
5. **Documentation**: All assumptions documented, dropdown values complete, reference sheet populated

Save to outputs folder with computer:// link. Provide a brief summary of the model structure and key metrics.
**Why:** Financial models must be defensible. Zero formula errors, balanced allocations, and documented assumptions are non-negotiable for any model that will be used in CIO/CFO discussions. The benchmarks provide context for whether the model's outputs are reasonable.

**Output**: A professional TBM Excel workbook following Taxonomy v5.0.1 structure — with cost pool mapping, tower allocation, solutions and consumer mapping, R/G/T classification, unit cost calculations, dashboards with charts and conditional formatting, and benchmarks. Color-coded, formula-validated, fully documented.
