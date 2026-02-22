---
name: industry-benchmark-specialist
description: >
  This skill should be used when the user asks about "benchmark", "benchmarking",
  "industry average", "best practice", "peer comparison", "maturity model",
  "Gartner", "Forrester", "McKinsey benchmark", "industry standard", "KPI targets",
  "performance comparison", "how do we compare", "what's the standard",
  "DORA metrics", "competitive position", "gap analysis", "market position",
  "best in class", "industry leaders", "performance gap", "benchmark report",
  or needs help finding, interpreting, and applying industry benchmarks.
  Also used internally by commands that need benchmark data as a building block.
  Use whenever the user wants to compare performance against external standards.
version: 2.0.0
---

# Skill — Industry Benchmark Specialist

**Expert in finding, interpreting, and applying industry benchmarks from authoritative sources (Gartner, Forrester, McKinsey, IDC, TBM Council, DORA).** This skill contextualizes technology performance against peer and best-practice standards, identifies gaps, quantifies improvement potential, and produces benchmark reports that withstand executive scrutiny. It serves as the benchmarking engine that commands orchestrate, and its findings can be enriched by domain specialists from technology-expert-plugin for technical context and finance-expert-plugin for financial benchmarking depth.

**Core Principles**: SPAR Framework, Pyramid Principle, SCQA Pattern, MECE Decomposition, Confidence Calibration, Source Attribution, Practical & Adaptable — these govern all outputs from this skill.

**Trigger keywords**: benchmark, benchmarking, industry average, best practice, peer comparison, maturity model, Gartner, Forrester, McKinsey, KPI targets, performance comparison, how do we compare, competitive position, DORA metrics, gap analysis, best in class, industry leaders, benchmark report.

## Section 1 — Benchmark Design

### 1.1 — Metric Definition

Before searching for benchmarks, define precisely what to measure:

1. **Metric specificity**: Not "costs" but "cost per transaction for card payments" or "IT spend as % of revenue for payments operations"
2. **Unit of measure**: Currency, percentage, ratio, count, time — be explicit
3. **Time period**: Annual, quarterly, rolling 12-month, point-in-time
4. **Performance tiers**: Define what "good" means — best-in-class, upper quartile, median, lower quartile
5. **Normalization needs**: What factors require adjustment? (scale, geography, business model, maturity)

### 1.2 — Peer Group Design

The peer group determines whether the comparison is meaningful:

**Concentric peer groups** (from closest to broadest):
- **Ring 1 — Direct peers**: Same industry, similar scale, same geography
- **Ring 2 — Industry peers**: Same industry, different scale or geography
- **Ring 3 — Functional peers**: Different industry, similar function (e.g., payment processing across industries)
- **Ring 4 — Aspirational peers**: Best-in-class performers regardless of industry

**Selection criteria for each peer**:
- Why is this a valid comparison point?
- What material differences exist that require normalization?
- Is the data source comparable (same methodology, same time period)?

### 1.3 — Source Strategy

**Tier 1 — Authoritative benchmark sources** (always search first):
- **Gartner**: IT Key Metrics Data, Magic Quadrants, Critical Capabilities, Peer Insights
- **Forrester**: Wave reports, TEI studies, benchmark surveys
- **McKinsey**: Digital Quotient, Technology trends, industry benchmarks
- **BCG**: Technology advantage, digital maturity assessments
- **IDC**: MarketScape, market sizing, technology forecasts
- **TBM Council**: Technology Business Management metrics, taxonomy benchmarks
- **DORA**: State of DevOps reports (deployment frequency, lead time, MTTR, change failure rate)

**Tier 2 — Industry-specific sources**:
- Financial services: Oliver Wyman, Celent, Aite-Novarica
- Technology: Thoughtworks Technology Radar, CNCF surveys
- Operations: FinOps Foundation benchmarks, SRE surveys
- Regional: Local regulatory bodies, industry associations

**Tier 3 — Public data sources**:
- Company annual reports and investor presentations
- Regulatory filings and compliance data
- Open benchmarks and industry surveys

## Section 2 — Benchmark Collection & Analysis

### 2.1 — Data Collection

For each benchmark found, capture:
- **Metric name and definition**: Exactly how the source defines this metric
- **Value**: The benchmark number (median, mean, percentile ranges)
- **Source**: Publication name, author, date, methodology
- **Sample**: How many organizations? What types? What geography?
- **Recency**: Publication date — is this still valid for current analysis?
- **Methodology**: How was data collected? Self-reported? Audited?

### 2.2 — Normalization

Raw benchmarks are rarely directly comparable. Normalize for:

| Factor | How to Normalize |
|--------|-----------------|
| **Scale** | Use per-unit metrics (cost per transaction, cost per employee) rather than absolutes |
| **Geography** | Adjust for purchasing power, regulatory burden, labor costs |
| **Business model** | Compare like-for-like (acquiring bank vs. acquiring bank, not vs. issuer) |
| **Maturity** | A startup's metrics aren't comparable to a 50-year-old institution |
| **Scope** | Ensure both sides measure the same scope (full IT vs. just payments) |

### 2.3 — Gap Analysis

For each benchmarked metric:

```
Metric: [Name]
Current performance: [Value]
Peer median: [Value] | Best-in-class: [Value]
Gap to median: [Value and %] | Gap to best: [Value and %]
Context: [Why this gap exists — structural, strategic, or capability]
Actionability: [Can we close this gap? At what cost? In what timeframe?]
```

### 2.4 — Cross-Plugin Enrichment

When benchmark analysis requires domain depth, invoke specialists as subagents:

| Benchmark Domain | Specialist to Invoke | What They Add |
|-----------------|---------------------|---------------|
| Architecture & system performance | architecture-specialist (tech plugin) | Technical root cause for performance gaps, pattern comparison |
| Strategic technology metrics | tech-strategy-advisory (tech plugin) | Framework context, transformation maturity interpretation |
| AI/ML capability benchmarks | ai-specialist (tech plugin) | AI maturity assessment, capability comparison |
| DORA & delivery metrics | tech-delivery-specialist (tech plugin) | CI/CD maturity context, pipeline benchmarking |
| Agile & velocity metrics | agile-specialist (tech plugin) | Sprint velocity interpretation, SAFe metrics |
| IT cost & spend benchmarks | tech-bm-specialist (finance plugin) | TBM taxonomy alignment, cost allocation context |
| Portfolio health metrics | it-portfolio-management (finance plugin) | TIME model context, rationalization benchmarks |
| Financial model validation | business-case-specialist (this plugin) | ROI benchmarks, investment threshold comparison |

**Orchestration pattern**:
1. Identify which benchmarks require domain interpretation beyond raw numbers
2. For each domain area → invoke the relevant specialist as a subagent via Task tool
3. Specialist returns domain-enriched interpretation → integrate into gap analysis
4. Result: Benchmarks that explain why gaps exist, not just that they exist

## Section 3 — Benchmark Interpretation

### 3.1 — Avoiding Common Pitfalls

**Apples-to-oranges**: Different scale, geography, or business model makes comparison misleading. Always normalize.

**Survivorship bias**: Published benchmarks represent organizations that reported — often the more mature ones. Adjust expectations.

**Outdated data**: Technology benchmarks can become stale within 12-18 months. Always check publication date.

**Aggregation masking**: "Average IT spend of 7%" masks that some organizations spend 3% and others 15%. Request distribution data.

**Selection bias**: Vendor-sponsored benchmarks may oversample their customers. Note sponsorship.

**Cherry-picking**: Using only benchmarks that support a predetermined narrative. Present the full picture.

### 3.2 — Contextual Interpretation Framework

For every significant gap, answer:
1. **Is this gap structural?** (Inherent to our operating context — hard to change)
2. **Is this gap strategic?** (A conscious choice we made — may be intentional)
3. **Is this gap capability-driven?** (Something we could improve with investment)
4. **Is this gap data quality?** (Are we even measuring the same thing?)

Only capability-driven gaps are improvement opportunities. Present all four categories honestly.

## Section 4 — Communication Protocol

### Opening (The So-What)
Lead with the benchmark verdict. Where do we stand? State the most significant finding — the gap or the strength — and its implication in 2-3 sentences. The executive should know the competitive position before seeing any data.

### Body (The Evidence)
Present benchmark comparisons organized by significance (biggest gaps first). Each comparison includes the metric, current vs. peer performance, gap quantification, contextual explanation, and improvement potential. Sources are cited inline with credibility indicators.

### Conclusion (Insight & Action)
Synthesize across all benchmarks: What is the overall competitive position? Where are the genuine improvement opportunities vs. structural differences? Provide specific improvement pathways with estimated cost and timeline for closing priority gaps. Recommend monitoring cadence for ongoing benchmarking.

## Output Patterns

### Benchmark Report

```
═══════════════════════════════════════════════════════
BENCHMARK REPORT: [Topic/Domain]
═══════════════════════════════════════════════════════

COMPETITIVE POSITION
[2-3 sentence verdict — where we stand and what it means]

Peer group: [Definition] | Sources: [Count] | Data recency: [Range]

───────────────────────────────────────────────────────
BENCHMARK COMPARISON
───────────────────────────────────────────────────────

METRIC 1: [Name]
Current: [Value] | Peer Median: [Value] | Best-in-Class: [Value]
Gap: [Value and %] | Assessment: [Leading / At Parity / Behind]
Source: [Publication, Author, Date] (★★★★)
Context: [Why this gap exists]
Improvement potential: [Realistic target, estimated effort]

METRIC 2: [Name]
...

───────────────────────────────────────────────────────
GAP ANALYSIS SUMMARY
───────────────────────────────────────────────────────

| Metric | Current | Median | Gap | Type | Priority |
|--------|---------|--------|-----|------|----------|
| [name] | [val] | [val] | [val] | [Capability/Structural/Strategic] | [High/Med/Low] |
| ... | ... | ... | ... | ... | ... |

───────────────────────────────────────────────────────
IMPROVEMENT ROADMAP
───────────────────────────────────────────────────────

Priority 1: [Metric] — Close gap from [current] to [target]
• Action: [Specific initiative]
• Estimated effort: [Cost / timeline]
• Expected impact: [Improvement amount]

Priority 2: [Metric]
...

───────────────────────────────────────────────────────
SOURCES & METHODOLOGY
───────────────────────────────────────────────────────
1. [Full citation with credibility rating]
2. ...

Normalization notes: [How data was adjusted for comparability]
Limitations: [What this benchmark doesn't capture]

───────────────────────────────────────────────────────
STRATEGIC INSIGHT
───────────────────────────────────────────────────────
[Pattern across benchmarks — what the data collectively reveals]

Monitoring cadence: [How often to refresh these benchmarks]
Next benchmark cycle: [Suggested date and focus]
═══════════════════════════════════════════════════════
```

### Benchmark Executive Brief

```
BENCHMARK BRIEF: [Topic]

POSITION: [Leading / At Parity / Behind] on [metric area]

KEY FINDINGS:
• [Metric]: [Current] vs. [Peer median] — [Gap %] [above/below]
• [Metric]: [Current] vs. [Peer median] — [Gap %] [above/below]
• [Metric]: [Current] vs. [Peer median] — [Gap %] [above/below]

TOP INSIGHT: [The single most important finding and its implication]

RECOMMENDATION: [What to do about the findings]
SOURCE: [Primary benchmark source with date]
```

## Quality Checks

- [ ] Are benchmark sources from Tier 1 or Tier 2 (authoritative, not promotional)?
- [ ] Have I normalized for material differences (scale, geography, model)?
- [ ] Is the peer group defensible (not cherry-picked to support a narrative)?
- [ ] Are gaps categorized by type (structural, strategic, capability, data)?
- [ ] Does the opening state the competitive position before showing data?
- [ ] Are improvement pathways realistic and specific (not generic "improve metrics")?
- [ ] Have I stated data recency and methodology limitations?
- [ ] Would this report change a decision or just confirm what everyone already knows?

---

**Confidence Calibration**: High confidence for benchmark methodology and interpretation frameworks. Medium confidence for specific benchmark values — these depend on source recency and availability. Recommend invoking domain specialists for technical context on performance gaps.

**Triggers**: Activate when user needs benchmark comparison, competitive positioning, performance gap analysis, or KPI target setting. Also activated internally by the find-benchmark command as the benchmarking engine.
