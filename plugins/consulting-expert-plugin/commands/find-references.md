---
description: Deep multi-source research with curated references across all content types
allowed-tools: Read, Write, Edit, Grep, Glob, Bash, WebSearch, WebFetch, Task
argument-hint: [topic to research — e.g., "event-driven architecture for payments"]
---

Conduct comprehensive multi-source, multi-modal research on $ARGUMENTS using the deep-search-specialist skill from consulting-expert-plugin. This command orchestrates parallel search streams, curates content across formats (articles, videos, tools, communities), and delivers a research report that is more insightful and better organized than what search engines provide.

## Layer 1 — Context & Intent

**What:** Understand what the user wants to learn and how they'll use it.
**How:** Parse $ARGUMENTS to extract:
- The core research topic — restate in precise terms
- The depth needed — executive overview, technical deep-dive, or comprehensive landscape
- The content types desired — written only, or also video, tools, communities, visual resources
- The decision context — what will this research inform? (learning, decision, presentation, strategy)

Accept input in any form: a phrase, a question, an image, a document excerpt. Transform it into a precise research question.

Default assumption: The user wants comprehensive, multi-modal research unless they specify otherwise.
**Why:** A well-scoped research question prevents two failure modes: too broad (drowning in noise) and too narrow (missing important adjacent findings).

## Layer 2 — Knowledge Loading

**What:** Load the deep search methodology and design the search strategy.
**How:** Read the deep-search-specialist SKILL.md from consulting-expert-plugin. Extract:
- From **Section 1**: Research design methodology — scope definition and search strategy design
- From **Section 2**: Parallel search streams and source evaluation criteria (★ credibility system)
- From **Section 3**: Synthesis methodology — thematic organization and content curation taxonomy
- From **Section 4**: Cross-plugin enrichment — which domain specialists can add depth
- From **Section 5**: Communication protocol (Opening / Body / Conclusion)

Design the keyword architecture:
- Primary terms (core topic, most common formulations)
- Synonym expansion (alternative names, acronyms)
- Qualifier terms (year, industry, "case study", "best practices")
- Exclusion terms (filter out noise)
**Why:** The skill's multi-tier source hierarchy and credibility evaluation system ensures the research is rigorous. Planning the keyword architecture before searching prevents scattered, unfocused results.

## Layer 3 — Parallel Search Execution

**What:** Execute research across multiple streams simultaneously using subagents.
**How:** Spawn 4-5 parallel subagents via the Task tool:

1. **Web research subagent**: "Conduct a comprehensive web search for: [topic with keyword variations]. Find the most authoritative and recent articles, reports, and analysis. For each finding, capture: title, author/organization, date, URL, 1-line summary, and credibility assessment (★ to ★★★★★). Return the top 10-15 results sorted by credibility."

2. **Analyst & expert content subagent**: "Search specifically for Gartner, Forrester, McKinsey, BCG, IDC publications and expert practitioner content on: [topic]. Also search for conference talks, whitepapers, and academic papers. For each finding, capture: title, author/organization, type (report/whitepaper/talk), date, URL, 1-line summary, credibility rating. Return the top 8-10 results."

3. **Video & multimedia subagent**: "Search YouTube, conference recording sites, and webinar platforms for high-quality video content on: [topic]. Prioritize: conference talks from recognized experts, technical deep-dives, product demos, tutorials. For each finding, capture: title, speaker/channel, duration, date, URL, what you'll learn. Return the top 5-8 results."

4. **Community & tools subagent**: "Search GitHub, Stack Overflow, Reddit, HackerNews, and specialized forums for: [topic]. Find: reference implementations, open-source tools, active discussions, community resources, newsletters. For each finding, capture: title, platform, type (repo/discussion/tool/newsletter), activity level, URL, why it's useful. Return the top 5-8 results."

5. **Domain specialist subagent** (when the topic intersects with a specific domain): "Read the [relevant specialist] SKILL.md from [technology/finance]-expert-plugin. Provide domain context for [topic]: key frameworks, common patterns, decision criteria, and what to look for in the research. Return structured domain context that enriches the search findings."

**Why:** Parallel subagents are the core differentiator. Each stream is specialized — a video search specialist finds better videos than a generic search. A community specialist finds GitHub repos and discussions that web search misses. This breadth across content types is what makes this better than Google or Perplexity.

## Layer 4 — Curation & Synthesis

**What:** Evaluate all findings, organize by theme, and curate into the content taxonomy.
**How:**
1. **Consolidate**: Merge all subagent outputs into a single pool of findings
2. **Deduplicate**: Remove duplicates (same content found by multiple streams)
3. **Evaluate credibility**: Apply the ★ system to every source:
   - ★★★★★ Peer-reviewed, official standards, audited data
   - ★★★★ Major analyst firms, established expert practitioners
   - ★★★ Respected trade publications, detailed case studies
   - ★★ Credible blogs, community evidence, vendor whitepapers
   - ★ Anonymous, unverified, promotional — include only if uniquely valuable

4. **Thematic synthesis**: Group findings by insight (not by source):
   - What are the 3-5 major themes that emerged across sources?
   - For each theme: key insight, supporting sources, contrarian views, practical implication
   - Do themes tell a coherent story? What's the narrative?

5. **Content curation**: Sort into the taxonomy from the skill:
   - **Must-Read**: The 3-5 definitive sources — "if you read nothing else, read these"
   - **Deep Dives**: Technical papers, detailed case studies, long-form analysis by sub-topic
   - **Watch / Listen**: Video talks, podcast episodes, webinars — with timestamp highlights
   - **Tools & Resources**: Frameworks, templates, GitHub repos, calculators, playgrounds
   - **Community & Discussion**: Forums, Slack/Discord communities, newsletters
   - **Visual Resources**: Infographics, architecture diagrams, comparison charts

6. **Gap identification**: What couldn't we find? Where do sources disagree? What's emerging?

**Why:** Curation is the value. Raw search results are noise — curated, evaluated, and organized findings are insight. The thematic synthesis reveals patterns that individual sources don't show. The content taxonomy serves different learning styles and depth needs.

## Layer 5 — Quality Review & Enrichment

**What:** Verify research quality and enrich where gaps exist.
**How:**
Run the Quality Checks:
- [ ] Have I searched across all source tiers (not just web)?
- [ ] Have I included multi-modal content (videos, tools, communities)?
- [ ] Are sources evaluated with credibility ratings?
- [ ] Are findings organized by theme, not by source?
- [ ] Have I identified gaps, contested areas, and emerging signals?
- [ ] Would this enable better decisions than a Google search alone?
- [ ] Are follow-up recommendations specific?

If gaps are critical, spawn additional targeted subagents to fill them.

For high-stakes research, spawn an evaluation subagent: "Review this research report for: (1) Are the top themes accurately identified? (2) Are source credibility ratings defensible? (3) Are there obvious gaps in content types or source tiers? (4) Is the synthesis insight-driven or just a list? Return specific feedback."

Apply feedback and fix any gaps.
**Why:** Research quality compounds — one missing high-credibility source can leave a critical gap, while including one low-credibility source without noting its limitations can mislead. The QA gate ensures the output is trustworthy.

## Layer 6 — Executive Delivery

**What:** Deliver the deep search report using the communication protocol.
**How:** Structure the output as:

**Opening (The So-What)**: 2-3 sentences — the research synthesis. What is the most important finding? What should the reader take away? State this before showing any sources. The reader should understand the landscape from the opening alone.

**Body (The Evidence)**: The research findings:
- Key themes with source-attributed insights
- Curated resources organized by content type (Must-Read, Watch/Listen, Tools, Community, Visual)
- Each source with: title, author/org, credibility rating (★), year, URL, and why it matters
- Gap identification and contested areas

**Conclusion (Insight & Follow-Up)**:
- The meta-insight — what patterns emerged across all the research
- What's surprising or counterintuitive
- Specific follow-up actions: deeper research areas, experts to engage, decisions enabled
- Monitoring suggestions — what to watch as this topic evolves

Use the Deep Search Report output pattern from the skill. The report should feel like receiving a briefing from a research analyst — organized, evaluated, and immediately useful.

**Why:** The communication protocol ensures the report is actionable, not just comprehensive. Opening with the synthesis respects the reader's time. Curating by content type serves different needs (quick read vs. deep-dive vs. visual). Closing with follow-up turns research into a launchpad for action.

**Output**: A comprehensive deep search report following the skill's output pattern — research insight synthesis, thematic findings with source attributions, curated resources across all content types (articles, videos, tools, communities, visuals), gap identification, and strategic follow-up recommendations. Every source cited with credibility rating, author, date, and URL.
