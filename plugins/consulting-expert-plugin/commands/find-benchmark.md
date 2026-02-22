---
description: Find and analyze industry benchmarks with sources and gap analysis
allowed-tools: Read, Write, Edit, Grep, Glob, Bash, WebSearch, WebFetch, Task
argument-hint: [area or KPI to benchmark — e.g., "DORA metrics for enterprise payments"]
---

Research and apply industry benchmarks for $ARGUMENTS using the industry-benchmark-specialist skill from consulting-expert-plugin. This command orchestrates a multi-source benchmark research workflow, invoking specialists for domain context and producing an executive-grade benchmark report with authoritative sources.

## Layer 1 — Context & Intent

**What:** Understand what the user wants to benchmark and why.
**How:** Parse $ARGUMENTS to extract:
- The specific metric(s) or area to benchmark (be precise — "cost per transaction" not just "costs")
- The comparison context — what are we comparing against? (peers, industry, best-in-class)
- The decision context — what will this benchmark inform? (investment case, improvement initiative, executive reporting)
- Current performance data if provided (or note that we'll need it)

If the user provides a broad topic, narrow it: identify the 3-5 most relevant metrics to benchmark for that topic.
**Why:** Benchmarks are only useful if they measure the right thing. A vague scope leads to generic comparisons that don't inform decisions.

## Layer 2 — Knowledge Loading

**What:** Load the benchmark methodology and identify supporting specialists.
**How:** Read the industry-benchmark-specialist SKILL.md from consulting-expert-plugin. Extract:
- From **Section 1**: Metric definition protocol and peer group design
- From **Section 2**: Benchmark source strategy (Tier 1-3 sources) and normalization methodology
- From **Section 3**: Interpretation framework and common pitfalls
- From **Section 4**: Communication protocol (Opening / Body / Conclusion)

Based on the topic identified in Layer 1, note which cross-plugin specialists might add domain context:
- Technology metrics → architecture-specialist, tech-delivery-specialist, or agile-specialist
- Financial metrics → tech-bm-specialist
- Portfolio metrics → it-portfolio-management
**Why:** The skill's source hierarchy and normalization methodology ensure we find credible benchmarks and compare them fairly. Domain specialists add interpretation depth that generic benchmarks lack.

## Layer 3 — Benchmark Scoping & Search Design

**What:** Define precise metrics, design the peer group, and plan the search strategy.
**How:**
1. **Metric definition**: For each metric to benchmark:
   - Name, precise definition, unit of measure
   - Time period and performance tiers (best-in-class, upper quartile, median, lower quartile)
   - Normalization needs (what factors require adjustment)

2. **Peer group design**: Define concentric rings:
   - Ring 1: Direct peers (same industry, scale, geography)
   - Ring 2: Industry peers (broader)
   - Ring 3: Functional peers (same function, different industry)
   - Ring 4: Aspirational (best-in-class regardless)

3. **Source strategy**: Plan which sources to search:
   - Tier 1: Gartner IT Key Metrics, Forrester benchmarks, McKinsey reports, DORA State of DevOps
   - Tier 2: Industry associations (TBM Council, FinOps Foundation, SWIFT), analyst reports
   - Tier 3: Public company data, regulatory data, open benchmarks

**Why:** Precision in scoping prevents wasted search effort. Peer group design ensures the comparison is defensible — the most common challenge to any benchmark is "but we're different."

## Layer 4 — Multi-Source Research

**What:** Execute the benchmark search across multiple sources simultaneously.
**How:** Spawn parallel subagent searches via the Task tool:

1. **Analyst research subagent**: "Search for industry benchmarks from Gartner, Forrester, McKinsey, IDC for: [specific metrics]. Find the most recent published data. Return: metric name, benchmark values (by tier), source, date, methodology, sample size."

2. **Open benchmark subagent**: "Search for publicly available benchmark data for: [specific metrics]. Look in DORA reports, TBM Council publications, FinOps Foundation, industry association reports, company annual reports. Return: metric name, values, source, date, methodology."

3. **Domain context subagent** (when the topic requires technical depth): "Read the [relevant specialist] SKILL.md from [technology/finance]-expert-plugin and provide context for interpreting [these metrics]. What drives these numbers? What are the common causes of over/under performance? Return structured interpretation guidance."

4. **Competitive intelligence subagent** (when comparing against specific companies): "Search for publicly available performance data for [named companies/competitors] on [these metrics]. Return: company, metric, value, source, date."

Collect all subagent outputs. Cross-reference findings — if the same metric appears in multiple sources, note the range and which source is most authoritative.
**Why:** Parallel multi-source search produces richer results than sequential searching. Subagents focused on specific source tiers maintain quality while covering breadth. Domain context subagents add the interpretation layer that raw numbers lack.

## Layer 5 — Analysis & Comparison

**What:** Normalize data, analyze gaps, and develop improvement pathways.
**How:**
1. **Data consolidation**: Combine all subagent findings into a unified benchmark dataset. For each metric:
   - Best available benchmark value (with confidence: high if multiple Tier 1 sources agree, medium if single source or Tier 2)
   - Source attribution with date and methodology
   - Range across sources if values differ

2. **Normalization**: Apply adjustments for:
   - Scale differences (use per-unit metrics)
   - Geographic factors (purchasing power, regulatory burden)
   - Business model differences (like-for-like comparison)
   - Maturity stage (greenfield vs. legacy)
   - Document every adjustment transparently

3. **Gap analysis**: For each metric:
   - Current vs. peer median vs. best-in-class
   - Gap quantification (absolute and percentage)
   - Gap type classification: Structural (inherent), Strategic (intentional), Capability (improvable), Data quality (measurement issue)
   - Improvement potential and estimated effort

4. **Pattern identification**: Across all metrics — where are we strong? Where are we behind? What story does the collection of benchmarks tell?

**Why:** Raw benchmarks mislead without normalization. Gap classification prevents false urgency — not every gap is an improvement opportunity. Pattern identification elevates individual comparisons into strategic insight.

## Layer 6 — Quality Review

**What:** Verify the analysis is rigorous and defensible before delivery.
**How:** Run the Quality Checks:
- [ ] Are sources from Tier 1 or Tier 2 (authoritative)?
- [ ] Have I normalized for material differences?
- [ ] Is the peer group defensible (not cherry-picked)?
- [ ] Are gaps categorized by type?
- [ ] Have I stated data recency and limitations?
- [ ] Would this change a decision (not just confirm what's known)?

If any check fails, address it before proceeding.

For high-stakes benchmarks, spawn an evaluation subagent: "Review this benchmark analysis for: (1) Are comparisons fair and normalized? (2) Are sources authoritative and recent? (3) Could someone challenge the peer group? (4) Are improvement recommendations realistic? Return specific feedback."
**Why:** Benchmark data gets scrutinized heavily in executive settings. One poorly sourced number can undermine the entire analysis. The QA gate ensures every claim is defensible.

## Layer 7 — Executive Delivery

**What:** Deliver the benchmark report using the communication protocol.
**How:** Structure the output as:

**Opening (The So-What)**: 2-3 sentences — the competitive position verdict and its most significant implication. The reader should know where they stand before seeing any data tables.

**Body (The Evidence)**: The benchmark analysis:
- Metric-by-metric comparison with gap analysis
- Sources cited inline with credibility ratings (★ system)
- Normalization notes where relevant
- Organized by significance (biggest gaps first, not alphabetically)

**Conclusion (Insight & Action)**:
- Strategic pattern across benchmarks — what the data collectively reveals
- Specific improvement roadmap for priority gaps (action, effort, expected impact)
- Monitoring cadence and next benchmark cycle recommendation

Use the Benchmark Report output pattern from the skill. The report should be presentation-ready — someone could include these tables and charts in a board deck.

**Why:** Executives don't read benchmark data — they read benchmark verdicts. The opening delivers the verdict. The body provides the evidence. The conclusion provides the path forward. This structure respects their time and enables action.

**Output**: An executive benchmark report following the skill's output pattern — competitive position verdict, metric-by-metric comparison with authoritative sources, gap analysis with type classification, improvement roadmap, and monitoring recommendations. All sources cited with credibility ratings.
