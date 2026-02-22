---
description: Find and compile technology references for a topic
allowed-tools: Read, WebSearch, WebFetch
argument-hint: "[topic to research — e.g., 'event-driven architecture for payments', 'AI governance frameworks']"
---

Find and compile technology references for $ARGUMENTS using the appropriate technology-expert-plugin specialist skill.

## Layer 1 — Context & Intent

**What:** Define what topic needs references and what type of references the user needs.
**How:** Parse $ARGUMENTS to extract:
- What technology topic needs references?
- What type of references? (official documentation, analyst reports, frameworks, books, tools, case studies)
- What depth? (quick reference list, annotated bibliography, curated reading list)
- What's the purpose? (self-study, preparing a presentation, building a business case, vendor evaluation)

Route to the correct specialist skill for domain knowledge:
- AI topics → `ai-specialist`
- Architecture topics → `architecture-specialist`
- DevOps/delivery topics → `tech-delivery-specialist`
- Agile topics → `agile-specialist`
- Strategy topics → `tech-strategy-advisory`
**Why:** References are most useful when categorized by the domain specialist. The skill's knowledge of key frameworks, benchmarks, and sources ensures we find authoritative references, not random blog posts.

## Layer 2 — Knowledge Extraction

**What:** Extract the relevant frameworks, sources, and benchmarks from the specialist skill.
**How:** Read the identified specialist skill. Extract:
- Named frameworks and their sources (e.g., TOGAF → The Open Group, SAFe → Scaled Agile)
- Benchmark sources (e.g., DORA Report, Gartner, McKinsey Digital)
- Industry standards (e.g., PCI-DSS, ISO 20022, SR 11-7)
- Key practitioners and thought leaders
- Recommended books and publications from the domain

These form the "known" reference base — authoritative sources the skill already vouches for.
**Why:** The specialist skills have curated the most relevant frameworks and sources through expert design. Starting from these ensures the reference list has a strong authoritative foundation before web search adds recency.

## Layer 3 — Web Enrichment

**What:** Search for current, high-quality references to complement the skill's knowledge base.
**How:** Use WebSearch to find:
1. **Official documentation**: Product docs, specification documents, standards bodies
2. **Analyst reports**: Gartner Magic Quadrant, Forrester Wave, McKinsey/BCG publications
3. **Industry reports**: DORA State of DevOps, ThoughtWorks Technology Radar, Stack Overflow Survey
4. **Case studies**: Real-world implementations, especially in financial services/payments
5. **Books and courses**: Definitive books, recommended certifications
6. **Tools and platforms**: Open-source projects, commercial tools, evaluation resources

For each reference found, assess:
- **Credibility**: Source authority (official > analyst > practitioner > blog)
- **Recency**: Publication date (prefer last 2 years for technology topics)
- **Relevance**: Direct applicability to the topic (High/Medium/Low)
**Why:** Web search adds currency to the skill's foundational knowledge. Technology references age quickly — a 2023 report on AI agents is already outdated. The credibility/recency/relevance assessment prevents low-quality sources from diluting the list.

## Layer 4 — Compilation & Delivery

**What:** Organize references into a structured, actionable reference list.
**How:** Categorize using MECE decomposition:
1. **Official Documentation & Standards**: Specs, standards bodies, official guides
2. **Industry Reports & Analyst Research**: Gartner, Forrester, McKinsey, DORA
3. **Frameworks & Methodologies**: Named frameworks with source references
4. **Books & Deep Reading**: Definitive books for the domain
5. **Tools & Platforms**: Relevant tools, open-source projects, platforms
6. **Case Studies & Examples**: Real-world implementations

For each reference include:
- Title and source
- Brief description (1-2 sentences)
- Relevance rating (High/Medium/Low)
- Recency (publication date or "evergreen")

Prioritize by relevance and authority. Cap at 15-20 references unless the user requests more — quality over quantity.
**Why:** A structured reference list is immediately useful. The MECE categories ensure coverage without overlap. Relevance ratings help the user prioritize their reading. Capping the list prevents information overload.

**Output**: A curated, categorized reference list organized by type (official docs, analyst reports, frameworks, books, tools, case studies) with brief descriptions, relevance ratings, and recency indicators. Quality over quantity — 15-20 authoritative references.
