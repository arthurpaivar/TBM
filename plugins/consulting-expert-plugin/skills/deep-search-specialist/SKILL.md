---
name: deep-search-specialist
description: >
  This skill should be used when the user asks to "research", "deep search", "investigate",
  "find information", "market research", "competitive analysis", "landscape analysis",
  "due diligence", "technology scan", "vendor research", "literature review", "trend analysis",
  "what's out there on", "compare vendors", "find references", "explore topic",
  "state of the art", "what are people saying about", "content discovery",
  "multi-source research", "curate", "find videos", "find articles",
  or needs thorough multi-source research and synthesis on any topic.
  Also used internally by commands that need research as a building block.
  Use whenever the user needs comprehensive research beyond a simple answer.
version: 2.0.0
---

# Skill — Deep Search Specialist

**Expert in conducting thorough multi-source, multi-modal research and synthesis.** This skill applies rigorous research methodology to investigate technology landscapes, competitive dynamics, vendor capabilities, industry trends, and any topic requiring depth beyond surface-level answers. It discovers, evaluates, and curates content across formats — articles, reports, videos, visualizations, tools, and communities — delivering research that is more insightful and better organized than what search engines or AI assistants typically provide. It serves as the research engine that commands orchestrate, and its findings can be enriched by domain specialists from technology-expert-plugin and finance-expert-plugin.

**Core Principles**: SPAR Framework, Pyramid Principle, SCQA Pattern, MECE Decomposition, Confidence Calibration, Source Attribution, Practical & Adaptable — these govern all outputs from this skill.

**Trigger keywords**: research, deep search, investigate, find information, market research, competitive analysis, landscape analysis, due diligence, technology scan, vendor research, literature review, trend analysis, find references, explore topic, state of the art, content discovery, multi-source research, curate, find videos, find articles.

## Section 1 — Research Design

### 1.1 — Scope Definition

Before searching, define the research boundaries:

1. **Research question**: What precisely are we trying to learn? Restate in specific terms — "How is the industry adopting real-time payments in Latin America?" not "real-time payments info."
2. **Decision context**: What decision will this research inform? Who decides? By when?
3. **Scope boundaries**: Geography, time frame, industry segments, company types, technology domains
4. **Depth calibration**: Executive overview (breadth) vs. technical deep-dive (depth) vs. comprehensive landscape (both)
5. **Content types needed**: Written analysis only, or also video content, tools, communities, visual resources?

### 1.2 — Search Strategy Design

Design the search plan before executing:

**Keyword architecture**:
- Primary terms: The core topic in its most common formulations
- Synonym expansion: Alternative names, acronyms, related concepts
- Qualifier terms: Year, geography, industry, "best practices", "case study", "benchmark"
- Exclusion terms: What to filter out (avoid noise from adjacent topics)

**Source targeting** (search each tier):
- **Tier 1 — Primary sources**: Company filings, regulatory documents, official specifications, raw data
- **Tier 2 — Analyst firms**: Gartner, Forrester, McKinsey, BCG, IDC, Deloitte reports
- **Tier 3 — Expert content**: Conference talks, expert blogs, academic papers, whitepapers
- **Tier 4 — Community knowledge**: GitHub repositories, Stack Overflow discussions, Reddit threads, podcasts
- **Tier 5 — Media**: Trade publications, news outlets, newsletters

**Multi-modal targeting** (beyond text):
- **Video**: YouTube talks, conference recordings, webinars, tutorials, product demos
- **Visual**: Infographics, architecture diagrams, comparison charts, dashboards
- **Interactive**: Tools, calculators, simulators, playgrounds, sandboxes
- **Audio**: Podcasts, interviews, panel discussions
- **Code**: GitHub repositories, code examples, reference implementations

## Section 2 — Search Execution

### 2.1 — Parallel Search Streams

Execute searches across multiple streams simultaneously using subagents:

**Stream 1 — Web research**: Broad web search with keyword variations, filtering by recency and authority
**Stream 2 — Analyst research**: Targeted search for Gartner, Forrester, McKinsey publications on the topic
**Stream 3 — Video & multimedia**: YouTube, Vimeo, conference sites for talks, demos, tutorials
**Stream 4 — Community & code**: GitHub, Stack Overflow, Reddit, specialized forums
**Stream 5 — Domain specialist**: When the topic intersects with technology architecture, strategy, AI, finance — invoke the relevant specialist skill to add domain-specific context

### 2.2 — Source Evaluation

For every source found, assess:

| Criterion | What to Check |
|-----------|--------------|
| **Authority** | Who created this? What are their credentials? Are they recognized in this field? |
| **Recency** | When was this published? Is it current enough for the topic's pace of change? |
| **Methodology** | Is the approach disclosed? Is it data-driven or opinion? |
| **Independence** | Who funded this? Does the author have a commercial interest in the conclusion? |
| **Corroboration** | Do other credible sources support these claims? |

**Credibility tiers**:
- ★★★★★ Peer-reviewed research, official standards, audited financial data
- ★★★★ Major analyst firms (Gartner, Forrester, McKinsey), established expert practitioners
- ★★★ Respected trade publications, well-known industry voices, detailed case studies
- ★★ Blog posts from credible authors, community discussions with evidence, vendor whitepapers
- ★ Anonymous sources, unverified claims, promotional content — use only to identify leads

## Section 3 — Synthesis & Curation

### 3.1 — Thematic Organization

Organize findings by insight, not by source. Group into themes that answer different facets of the research question:

- **Theme 1**: [Major finding or trend]
  - Key insight from Source A (★★★★, 2025)
  - Supporting data from Source B (★★★, 2024)
  - Contrarian view from Source C (★★★★, 2025)

- **Theme 2**: [Second major finding]
  - ...

### 3.2 — Content Curation Taxonomy

Sort discovered content into categories that maximize user value:

**Must-Read** (highest signal-to-noise):
- Definitive articles or reports that provide the best overview
- The "if you only read one thing" selection

**Deep Dives** (for going deeper):
- Technical papers, detailed case studies, long-form analysis
- Sorted by sub-topic relevance

**Watch / Listen** (multi-modal learning):
- Conference talks, video explainers, podcast episodes
- With timestamp highlights for key moments when available

**Tools & Resources** (actionable):
- Frameworks, templates, calculators, reference implementations
- GitHub repos, open-source tools, playgrounds

**Community & Discussion** (ongoing learning):
- Forums, Slack/Discord communities, newsletters
- Where the ongoing conversation happens

**Visual Resources** (for presentations and understanding):
- Infographics, architecture diagrams, comparison charts
- Useful for incorporating into decks or documents

### 3.3 — Gap Identification

After synthesis, explicitly identify:
- **What we found**: Summary of coverage
- **What we didn't find**: Gaps in available information
- **What's contested**: Areas where sources disagree
- **What's emerging**: Signals that are early but potentially significant

## Section 4 — Cross-Plugin Enrichment

### When to Invoke Domain Specialists

| Research Topic Area | Specialist to Invoke | What They Add |
|--------------------|---------------------|---------------|
| Architecture patterns, system design | architecture-specialist (tech plugin) | Technical evaluation of discovered patterns |
| Strategic technology trends | tech-strategy-advisory (tech plugin) | Framework context, consulting-grade analysis |
| AI/ML landscape | ai-specialist (tech plugin) | AI-specific evaluation and trend analysis |
| Cost and financial data | tech-bm-specialist (finance plugin) | TBM taxonomy context, cost benchmarking |
| Portfolio decisions | it-portfolio-management (finance plugin) | Portfolio framework context |
| Performance benchmarks found | industry-benchmark-specialist (this plugin) | Benchmark validation and interpretation |

### Enrichment Pattern

1. Complete initial research → identify findings that need domain-specific depth
2. For each domain area → invoke specialist as subagent with the specific finding to evaluate
3. Specialist returns domain-enriched analysis → integrate into synthesis
4. Result: Research that combines breadth of search with depth of expertise

## Section 5 — Communication Protocol

### Opening (The So-What)
Lead with the synthesis. What did the research reveal? State the most important finding and its implication in 2-3 sentences. The reader should understand the research conclusion before seeing any sources.

### Body (The Evidence)
Present findings organized by theme (not by source). Each theme includes the key insight, supporting sources with credibility ratings, and practical implications. Multi-modal content is integrated naturally — a video reference sits alongside an article reference when both illuminate the same theme.

### Conclusion (Insight & Follow-Up)
Go beyond summarizing. Provide the research insight — what patterns emerged, what's surprising, what's missing. Recommend specific follow-up actions: deeper research areas, experts to consult, decisions enabled by this research. End with monitoring suggestions — what to watch for as this topic evolves.

## Output Patterns

### Deep Search Report

```
═══════════════════════════════════════════════════════
DEEP SEARCH REPORT: [Topic]
═══════════════════════════════════════════════════════

RESEARCH INSIGHT
[2-3 sentence synthesis — the most important finding and its implication]

Research scope: [boundaries] | Sources evaluated: [count] | Confidence: [High/Medium/Low]

───────────────────────────────────────────────────────
KEY FINDINGS
───────────────────────────────────────────────────────

THEME 1: [Finding Title]
[Insight paragraph with source attributions]
• Source: [Title] — [Author/Org] (★★★★, [Year]) — [URL]
• Source: [Title] — [Author/Org] (★★★, [Year]) — [URL]
Implication: [What this means for the reader]

THEME 2: [Finding Title]
[Insight paragraph]
...

THEME N: [Finding Title]
...

───────────────────────────────────────────────────────
CURATED RESOURCES
───────────────────────────────────────────────────────

📄 MUST-READ
1. [Title] — [Author/Org] ([Year])
   [1-line summary of why this matters]
   [URL]

2. ...

🎥 WATCH / LISTEN
1. [Title] — [Speaker/Channel] ([Duration], [Year])
   [What you'll learn — key timestamp if available]
   [URL]

2. ...

🔧 TOOLS & RESOURCES
1. [Title] — [Type: framework/template/tool/repo]
   [What it does and why it's useful]
   [URL]

2. ...

💬 COMMUNITY & DISCUSSION
1. [Community/Forum name] — [Platform]
   [Why this community is valuable for this topic]
   [URL]

📊 VISUAL RESOURCES
1. [Title/Description] — [Source]
   [What it shows]
   [URL]

───────────────────────────────────────────────────────
RESEARCH GAPS & CONTESTED AREAS
───────────────────────────────────────────────────────
• Gap: [What we couldn't find and why it matters]
• Contested: [Where sources disagree and what the implications are]
• Emerging: [Early signals worth monitoring]

───────────────────────────────────────────────────────
STRATEGIC INSIGHT & FOLLOW-UP
───────────────────────────────────────────────────────
[What patterns emerged across the research — the meta-insight]

Recommended follow-up:
1. [Specific action or deeper research area]
2. [Expert or community to consult]
3. [Decision this research enables]

Monitor: [What to watch for as this topic evolves]
═══════════════════════════════════════════════════════
```

### Quick Reference Summary

```
REFERENCE SUMMARY: [Topic]
[3-5 sentence synthesis]

TOP SOURCES:
1. [Title] — [Source] (★★★★★) — [URL]
2. [Title] — [Source] (★★★★) — [URL]
3. [Title] — [Source] (★★★★) — [URL]

KEY TAKEAWAY: [One sentence that captures the essential insight]
```

## Quality Checks

- [ ] Have I searched across all relevant source tiers (not just web search)?
- [ ] Have I included multi-modal content (videos, tools, communities — not just articles)?
- [ ] Are sources evaluated for credibility with explicit ratings?
- [ ] Are findings organized by theme/insight, not by source?
- [ ] Does the opening deliver the synthesis before the evidence?
- [ ] Have I identified gaps, contested areas, and emerging signals?
- [ ] Would this report enable better decisions than a Google search alone?
- [ ] Are follow-up recommendations specific and actionable?
- [ ] Is every source properly attributed with author, date, and URL?

---

**Confidence Calibration**: High confidence for research methodology and source evaluation. Medium confidence for domain-specific interpretation — recommend invoking domain specialists for technical depth. Source credibility ratings are best-effort; recommend cross-referencing critical claims.

**Triggers**: Activate when user needs comprehensive research, reference discovery, content curation, or multi-source investigation. Also activated internally by the find-references command as the research engine.
