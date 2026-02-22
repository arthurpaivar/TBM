# Finance Expert Plugin

Specialist in Technology Business Management (TBM) and IT Portfolio governance for payments technology. Serves as the **modular knowledge base (second brain)** for a Tech BM working directly with a Payments CIO — providing deep IT finance insights for CIO/CFO-level conversations.

Built on TBM Framework 2.0 and TBM Taxonomy v5.0.1 (July 2025), the global standards maintained by the TBM Council.

## Cross-Plugin Architecture

This plugin is designed as a **modular foundation** that other plugins reference:
- **Technology Plugin**: Uses finance skills for investment categories (R/G/T), cost context, and benchmark data
- **Consulting Plugin**: Uses finance skills for financial benchmarks, business case evaluation, and cost-benefit analysis
- **Communication Plugin**: Uses finance skills for cost narratives, financial presentations, and executive summaries

## Skills

- **Tech BM Specialist** (`tech-bm-specialist`): TBM Framework 2.0 (Foundations, Model, Outcomes, Value Drivers), TBM Taxonomy v5.0.1 (4 layers: Cost Pools, Resource Towers with Resource Domains, Solutions, Consumers), cost allocation models (direct, usage-based, weighted, even-split), showback/chargeback maturity, Run/Grow/Transform investment classification, investment typification, value realization, FinOps integration, AI cost management (GPU/TPU, model licensing, MLOps), GreenOps/sustainability, FAIR cybersecurity risk quantification, TBM Maturity Model (Crawl/Walk/Run + 4×4 Maturity Assessment 2.0), IT spend benchmarks

- **IT Portfolio Management** (`it-portfolio-management`): Application portfolio rationalization (TIME model), 6-dimension application health assessment (weighted composite scoring), application lifecycle management with governance gates, modernization patterns (6Rs with sequencing), portfolio analytics (capability heat maps, cost Pareto, age distribution, redundancy maps), IT investment governance (3-tier structure), demand management process, investment prioritization (WSJF, value-effort, scoring model), budget planning cycle, unit economics for payments, cost optimization levers

- **Excel for Finance** (`excel-for-finance`): Financial modeling standards (color coding, number formatting, formula discipline), TBM Excel templates (taxonomy mapping workbook, R/G/T tracker, unit cost dashboard), portfolio Excel templates (application portfolio assessment, business case financial model, demand pipeline tracker), Excel execution workflow bridging to the Cowork xlsx skill, data validation dropdowns for TBM/portfolio classifications

## Commands

| Command | Description | Skills Used |
|---------|-------------|-------------|
| `/evaluate-business-case` | Evaluate a business case proposal for technology investment | `tech-bm-specialist` + `it-portfolio-management` |
| `/consolidate-excel` | Consolidate and analyze financial data in Excel using TBM frameworks | `tech-bm-specialist` + `excel-for-finance` + `xlsx` |
| `/assess-portfolio` | Assess an IT application portfolio using TIME model and health scoring | `it-portfolio-management` + `excel-for-finance` (optional) |
| `/build-tbm-model` | Build a TBM cost model or taxonomy mapping in Excel | `tech-bm-specialist` + `excel-for-finance` + `xlsx` |

## Skill-to-Command Mapping

```
tech-bm-specialist      ← /evaluate-business-case, /consolidate-excel, /build-tbm-model
it-portfolio-management ← /evaluate-business-case, /assess-portfolio
excel-for-finance       ← /consolidate-excel, /assess-portfolio (optional), /build-tbm-model
```

Every skill is reachable via at least one dedicated command. The `excel-for-finance` skill always works alongside the Cowork `xlsx` skill for technical Excel execution.

## Usage Examples

```
/evaluate-business-case cloud migration business case for payments processing
/consolidate-excel Q4 IT cost data — map to TBM taxonomy and calculate unit costs
/assess-portfolio payments application portfolio — TIME model and health scoring
/build-tbm-model R/G/T investment tracker for 2026 budget planning
```

## Author
Arthur
