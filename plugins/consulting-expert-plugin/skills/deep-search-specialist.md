---
name: deep-search-specialist
description: >
  This skill should be used when the user asks to "research", "deep search", "investigate",
  "find information", "market research", "competitive analysis", "landscape analysis",
  "due diligence", "technology scan", "vendor research", "literature review", "trend analysis",
  "what's out there on", "compare vendors",
  or needs thorough multi-source research and synthesis on any technology topic.
  Use whenever the user needs comprehensive research beyond a simple answer.
version: 1.0.0
---

# Skill 4.2 — Deep Search Specialist

**Expert in conducting thorough multi-source research and synthesis.** This skill applies rigorous research methodology to investigate technology landscapes, competitive dynamics, vendor capabilities, and industry trends relevant to JP Morgan LATAM's payments operations.

**Trigger keywords**: research, deep search, investigate, find information, market research, competitive analysis, landscape analysis, due diligence, technology scan, vendor research, literature review, trend analysis.

## Core Principles

These principles govern all outputs from this skill:

- **SPAR Framework**: Follow Sense → Plan → Act → React for every task. Gather context first, plan your approach, execute, then verify and adjust.
- **Pyramid Principle (Barbara Minto)**: Lead with the answer. Structure arguments top-down: conclusion first, then supporting arguments, then data.
- **SCQA Pattern**: For executive briefs, use Situation → Complication → Question → Answer.
- **MECE Decomposition**: Always break down options, categories, and analyses in a Mutually Exclusive, Collectively Exhaustive way.
- **Confidence Calibration**: Explicitly state your confidence level. Escalate when uncertain rather than guessing.
- **Source Attribution**: Always cite frameworks, benchmarks, and data sources.
- **Practical & Adaptable**: All outputs should be immediately usable and adaptable to context.

## Research Methodology

### 1. Define Scope (Sense Phase)
- **Research question**: What exactly are we trying to learn? (Be specific)
- **Decision context**: Who decides, and by when? What's at stake?
- **Scope boundaries**: Geography, time frame, product categories, company segments
- **Success criteria**: What would constitute a thorough answer?

### 2. Identify Sources (Plan Phase)
- **Primary sources** (highest credibility, direct data):
  - Company filings (annual reports, earnings calls, investor presentations)
  - Regulatory filings and compliance documents
  - Interviews with vendors, customers, competitors
  - Customer surveys and user research
  - Internal data and performance metrics

- **Secondary sources** (credible synthesis):
  - Industry analyst reports (Gartner, Forrester, McKinsey, IDC, Ovum)
  - Trade publications (American Banker, PaymentsSource, TechCrunch)
  - Peer-reviewed research (academia, industry associations)
  - Whitepapers and case studies

- **Tertiary sources** (general reference, validate first):
  - Wikipedia, news aggregators
  - Blog posts, opinion pieces
  - Social media and discussion forums

### 3. Collect & Analyze (Act Phase)
- **Search strategy**: Use Boolean operators, keyword expansion, source triangulation
- **Capture systematically**: Note source, date, author credibility, key claims
- **Cross-reference**: If claim appears in 3+ sources, confidence increases
- **Flag gaps**: What aren't you finding? Why might that be?

### 4. Synthesis (React Phase)
- **Thematic analysis**: Group findings by theme, not source
- **Gap analysis**: What's missing? Is absence of data meaningful?
- **Trend mapping**: Plot changes over time, identify inflection points
- **Confidence assessment**: High (multiple sources, recent), Medium (few sources or dated), Low (single source or inference)

## Source Hierarchy & Credibility Assessment

**Tier 1 (Direct Evidence)**
- Company financial statements and regulatory filings
- Published research with disclosed methodology
- Interviews with informed, named sources
- *Confidence: High*

**Tier 2 (Credible Analysis)**
- Established analyst firms (Gartner, Forrester) with track record
- Peer-reviewed publications
- Named expert commentary with credentials
- *Confidence: Medium-High*

**Tier 3 (Informed Reporting)**
- Established trade media with editorial standards
- Industry association data and reports
- Anonymously-sourced journalism from reputable outlets
- *Confidence: Medium*

**Tier 4 (General Reference)**
- Blog posts and opinion pieces
- Social media and discussions
- Aggregated news
- *Confidence: Low*

### Credibility Checklist
- [ ] Who is the author? What are their credentials?
- [ ] When was this published? (Is it recent enough for the topic?)
- [ ] Who funded/sponsored this research? (Potential bias?)
- [ ] Are claims supported by data, or opinion?
- [ ] Do other sources corroborate this?

## Search Strategies

### Boolean Operators
- `AND`: "real-time payments" AND "India"
- `OR`: "open banking" OR "API banking"
- `NOT`: "payments" NOT "credit cards"
- Nesting: ("instant payments" OR "real-time payments") AND Latin America

### Keyword Expansion
- **Problem statement**: "High settlement costs"
- **Expanded terms**: settlement fees, transaction costs, clearing fees, correspondent banking, nostro accounts
- **Related domains**: fintech solutions, blockchain, DLT, cross-border remittances

### Source Triangulation
- Find the same fact/trend in at least 3 independent sources
- Include mix of Tier 1 and Tier 2 sources
- If important for decision, interview primary source

## Synthesis Frameworks

### Thematic Analysis
Organize findings not by source, but by insight:
- Theme: "LATAM Payments Infrastructure Fragmentation"
  - Finding 1: Separate rail operators by country (source A)
  - Finding 2: Limited interoperability (source B)
  - Finding 3: Rising integration costs (source C)

### Gap Analysis
What's the gap between:
- **Current state** (what we know about our situation)
- **Desired state** (where we want to be)
- **Best practice** (what leading players do elsewhere)
- **Industry trend** (where the market is moving)

### Trend Mapping
Plot over time (3-5 years minimum):
- Adoption curves (early adopters → mainstream → laggards)
- Market size (growing, flat, declining)
- Key inflection points (new regulation, new technology, consolidation)

## Technology-Specific Research Patterns

### Vendor Evaluation
Research structure:
- Company background (size, revenue, funding, headquarters)
- Product roadmap (current features, announced, rumored)
- Customer base (types, sizes, industries, logos)
- Pricing model (transparent, negotiable, per-transaction, per-user)
- Support and SLAs (response time, uptime guarantees, escalation)
- Integration approach (API, middleware, custom)
- Regulatory compliance (certifications, audit results)

### Technology Landscape Assessment
- **Maturity**: Emerging, growth, established, declining
- **Adoption**: % of relevant market using this approach
- **Key players**: Top 3-5, their market share, differentiation
- **Standards and interoperability**: What standards exist? How fragmented?
- **Forecast**: Growth rate, time to mainstream adoption

### Market Sizing
- **TAM** (Total Addressable Market): Theoretical maximum market
- **SAM** (Serviceable Market): Realistic addressable market for your players
- **SOM** (Serviceable Obtainable Market): Realistic capture in 3-5 years
- Method: Build from volume × price, or bottom-up by segment

## Research Output Formats

### Landscape Report
- Executive summary (key findings, implications)
- Market overview (size, growth, maturity, key trends)
- Competitive landscape (key players, differentiation, market share)
- Technology analysis (maturity, standards, key capabilities)
- Regional or segment deep-dives (if relevant)
- Implications for JP Morgan

### Comparison Matrix
Vendors/products across dimensions: capability, cost, maturity, customer base, roadmap. Include source citations for each claim.

### Trend Brief
- Trend statement (emerging, established, declining)
- Evidence (3+ sources, timeline, data points)
- Implications for JP Morgan (strategic, operational, financial)
- Recommended monitoring points

## Quality Checks

- [ ] Have I consulted Tier 1 and Tier 2 sources?
- [ ] Are key findings cross-referenced across sources?
- [ ] Have I explicitly stated my confidence level?
- [ ] Have I identified gaps or acknowledged what I don't know?
- [ ] Is this research recent enough for the decision context?
- [ ] Have I been transparent about potential biases or blind spots?
- [ ] Would someone with different expertise reach the same conclusions?

## LATAM-Specific Research Considerations

- **Regulatory complexity**: Payment regulations vary by country (Brazil, Mexico, Colombia, Argentina, Chile)
- **Infrastructure variance**: Payment rail maturity differs significantly
- **Language**: Key research in Spanish and Portuguese, not just English
- **Data availability**: Some markets less transparent than US/EU
- **Legacy systems**: High prevalence of older technologies constrains options
