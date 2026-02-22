# TBM - Technology Business Manager Repository

**Your JP Morgan Second Brain** - A comprehensive knowledge repository of consulting-grade frameworks, methodologies, and best practices for technology leadership.

## Purpose

This repository contains **generic, non-proprietary expert knowledge** that acts as a framework library for high-quality work outputs. Think of it as having McKinsey, BCG, and Gartner methodologies on-demand.

### Architecture Philosophy

**Outside VDI (This Repository):**
- Generic frameworks and best practices (zero proprietary/classified data)
- Version-controlled expert knowledge plugins
- Safe to store publicly on GitHub

**Inside VDI (Your Claude Instance):**
- References these plugins as expert knowledge
- You bring actual JP Morgan context + these frameworks = consulting-grade outputs
- Speeds up work and improves quality without data security concerns

**The Value Proposition:**
- Consistent, expert-level guidance on demand
- No compliance or data security issues
- Methodologies are generic, applications are specific
- Your VDI Claude becomes a specialized advisor for technology leadership

## Repository Structure

```
TBM/
├── README.md
├── plugins/
│   ├── technology-expert-plugin/              [5 skills + 6 commands]
│   │   ├── .claude-plugin/
│   │   │   └── plugin.json
│   │   ├── README.md
│   │   ├── commands/
│   │   │   ├── advise-strategy.md
│   │   │   ├── assess-architecture.md
│   │   │   ├── brief-ai-topic.md
│   │   │   ├── explain-tech-concept.md
│   │   │   ├── list-tech-references.md
│   │   │   └── review-delivery.md
│   │   └── skills/
│   │       ├── ai-specialist/SKILL.md
│   │       ├── agile-specialist/SKILL.md
│   │       ├── architecture-specialist/SKILL.md
│   │       ├── tech-delivery-specialist/SKILL.md
│   │       └── tech-strategy-advisory/SKILL.md
│   │
│   ├── consulting-expert-plugin/              [4 skills + 3 commands]
│   │   ├── .claude-plugin/
│   │   │   └── plugin.json
│   │   ├── README.md
│   │   ├── commands/
│   │   │   ├── find-benchmark.md
│   │   │   ├── find-references.md
│   │   │   └── problem-solve.md
│   │   └── skills/
│   │       ├── problem-solving-specialist/SKILL.md
│   │       ├── deep-search-specialist/SKILL.md
│   │       ├── industry-benchmark-specialist/SKILL.md
│   │       └── business-case-specialist/SKILL.md
│   │
│   ├── communication-expert-plugin/           [4 skills + 6 commands]
│   │   ├── .claude-plugin/
│   │   │   └── plugin.json
│   │   ├── README.md
│   │   ├── commands/
│   │   │   ├── create-executive-summary.md
│   │   │   ├── create-improve-email.md
│   │   │   ├── create-improve-powerpoint.md
│   │   │   ├── improve-text.md
│   │   │   ├── translate-en-pt.md
│   │   │   └── translate-pt-en.md
│   │   └── skills/
│   │       ├── e-mail-generator/SKILL.md
│   │       ├── translation-specialist/SKILL.md
│   │       ├── powerpoint-specialist/SKILL.md
│   │       └── text-improver-specialist/SKILL.md
│   │
│   ├── finance-expert-plugin/                 [3 skills + 4 commands]
│   │   ├── .claude-plugin/
│   │   │   └── plugin.json
│   │   ├── README.md
│   │   ├── commands/
│   │   │   ├── assess-portfolio.md
│   │   │   ├── build-tbm-model.md
│   │   │   ├── consolidate-excel.md
│   │   │   └── evaluate-business-case.md
│   │   └── skills/
│   │       ├── excel-for-finance/SKILL.md
│   │       ├── tech-bm-specialist/SKILL.md
│   │       └── it-portfolio-management/SKILL.md
│   │
│   ├── ai-expert-plugin/                      [8 skills + 7 commands]
│   │   ├── .claude-plugin/
│   │   │   └── plugin.json
│   │   ├── README.md
│   │   ├── commands/
│   │   │   ├── create-commands.md
│   │   │   ├── create-context-window.md
│   │   │   ├── create-plugin.md
│   │   │   ├── create-skill.md
│   │   │   ├── update-commands.md
│   │   │   ├── update-plugin.md
│   │   │   └── update-skill.md
│   │   └── skills/
│   │       ├── agent-creation-specialist/SKILL.md
│   │       ├── command-creation-specialist/SKILL.md
│   │       ├── command-specialist/SKILL.md
│   │       ├── context-window-specialist/SKILL.md
│   │       ├── plugin-creation-specialist/SKILL.md
│   │       ├── plugin-specialist/SKILL.md
│   │       ├── skill-creation-specialist/SKILL.md
│   │       └── skill-specialist/SKILL.md
│   │
│   └── github-expert-plugin/                  [1 skill + 3 commands]
│       ├── .claude-plugin/
│       │   └── plugin.json
│       ├── README.md
│       ├── commands/
│       │   ├── create-github-element.md
│       │   ├── update-github-element.md
│       │   └── remove-github-element.md
│       └── skills/
│           └── github-repository-specialist/SKILL.md
│
└── skills/
    ├── public/     (Anthropic built-in skills - docx, pdf, pptx, xlsx, etc.)
    ├── private/    (Reserved for future use)
    └── examples/   (Reference examples)
```

**Total:** 6 plugins | 25 skills | 29 commands

## Plugin Suite Overview

### 1. Technology Expert Plugin (v4.0.0)
**Expert in:** AI/MCP, Agile, Architecture, Tech Delivery, Strategy

| Skill | Focus Areas |
|-------|-------------|
| **AI Specialist** | MCP architecture, agent patterns (ReAct, Plan-Execute), RAG vs fine-tuning, enterprise AI governance |
| **Agile Specialist** | SAFe 6.0, DORA metrics (Elite/High/Medium/Low tiers), PI planning, WSJF prioritization |
| **Architecture Specialist** | Enterprise/solution architecture, DDD, microservices, event-driven, TOGAF, ADRs, cloud-native patterns |
| **Tech Delivery Specialist** | SDLC, DevOps (CALMS), CI/CD pipelines, SRE principles (SLIs/SLOs/SLAs), testing pyramid |
| **Tech Strategy Advisory** | McKinsey 3Ds, BCG Digital Transformation, Accenture frameworks, TOM design, capability mapping |

| Command | What It Does |
|---------|-------------|
| `/advise-strategy` | Provide technology strategy advisory using consulting frameworks |
| `/assess-architecture` | Assess an architecture design or pattern against best practices |
| `/brief-ai-topic` | Create an AI briefing for CIO-level conversations |
| `/explain-tech-concept` | Explain a technology concept clearly and thoroughly |
| `/list-tech-references` | List technology references and resources for a topic |
| `/review-delivery` | Review delivery maturity and engineering excellence posture |

### 2. Consulting Expert Plugin (v2.0.0)
**Expert in:** Structured problem-solving, research, benchmarking, business cases

| Skill | Focus Areas |
|-------|-------------|
| **Problem-Solving Specialist** | MECE decomposition, hypothesis-driven analysis, root cause (5 Whys, Fishbone), decision matrices |
| **Deep Search Specialist** | Multi-source research, vendor evaluation, landscape analysis, trend synthesis |
| **Industry Benchmark Specialist** | Gartner/Forrester/McKinsey benchmarks, peer comparison, maturity models, KPI targets |
| **Business Case Specialist** | NPV, IRR, TCO, cost-benefit analysis, investment proposals, stakeholder-specific framing |

| Command | What It Does |
|---------|-------------|
| `/find-references` | Deep research and find references on any topic |
| `/find-benchmark` | Find and apply industry benchmarks for a topic or KPI |
| `/problem-solve` | Structured problem decomposition and analysis |

### 3. Communication Expert Plugin (v2.0.0)
**Expert in:** Professional communication, translation, presentations, writing

| Skill | Focus Areas |
|-------|-------------|
| **E-mail Generator** | BLUF methodology, 6 email types, tone calibration by audience, LATAM cultural sensitivity |
| **Translation Specialist** | EN↔PT-BR professional translation, terminology management, cultural adaptation, domain glossaries |
| **PowerPoint Specialist** | JP Morgan design system, 4 deck sizes, Pyramid/SCQA narrative, cross-plugin orchestration, PptxGenJS |
| **Text Improver Specialist** | 5-dimension improvement (clarity, conciseness, tone, structure, impact), audience-aware rewriting |

| Command | What It Does |
|---------|-------------|
| `/create-improve-email` | Create or improve a professional corporate email |
| `/create-executive-summary` | Create a concise executive summary from content or topic |
| `/create-improve-powerpoint` | Create or improve a PowerPoint presentation |
| `/improve-text` | Refine and elevate professional writing |
| `/translate-en-pt` | Translate text from English to Brazilian Portuguese |
| `/translate-pt-en` | Translate text from Brazilian Portuguese to English |

### 4. Finance Expert Plugin (v4.0.0)
**Expert in:** Technology Business Management, IT Portfolio governance, Financial Modeling

| Skill | Focus Areas |
|-------|-------------|
| **Tech BM Specialist** | TBM Framework 2.0, Taxonomy v5.0.1, cost transparency, showback/chargeback, Run/Grow/Transform, FinOps |
| **IT Portfolio Management** | Application portfolio (TIME model), investment governance, ITFM, demand management, 6Rs modernization |
| **Excel for Finance** | Financial modeling in Excel, TBM cost models, budget templates, portfolio dashboards |

| Command | What It Does |
|---------|-------------|
| `/assess-portfolio` | Assess an IT application portfolio using TIME model and health scoring |
| `/build-tbm-model` | Build a TBM cost model or taxonomy mapping in Excel |
| `/consolidate-excel` | Consolidate and analyze financial data in Excel using TBM frameworks |
| `/evaluate-business-case` | Evaluate a business case proposal for technology investment |

### 5. AI Expert Plugin (v2.0.0)
**Expert in:** AI plugins, skills, commands, agents, and context windows for the Claude/Cowork ecosystem

| Skill | Focus Areas |
|-------|-------------|
| **Plugin Specialist** | Existing plugin structure, capabilities, and usage |
| **Skill Specialist** | Existing skill triggers, patterns, and best practices |
| **Command Specialist** | Existing command design, execution, and patterns |
| **Plugin Creation Specialist** | Guide for creating new plugins from scratch |
| **Skill Creation Specialist** | Guide for creating new skills from scratch |
| **Command Creation Specialist** | Guide for creating new commands from scratch |
| **Context Window Specialist** | Designing context windows for AI agents |
| **Agent Creation Specialist** | Building AI agents with tools, memory, and planning |

| Command | What It Does |
|---------|-------------|
| `/create-plugin` | Create a new plugin from scratch |
| `/update-plugin` | Update an existing plugin |
| `/create-skill` | Create a new skill from scratch |
| `/update-skill` | Update an existing skill |
| `/create-commands` | Create new commands for a plugin |
| `/update-commands` | Update existing commands in a plugin |
| `/create-context-window` | Create a context window for an AI agent |

### 6. GitHub Expert Plugin (v2.0.0)
**Expert in:** GitHub repository management for the Tech BM Second Brain

| Skill | Focus Areas |
|-------|-------------|
| **GitHub Repository Specialist** | Repository structure, plugin/skill/command sync, vault architecture, version control |

| Command | What It Does |
|---------|-------------|
| `/create-github-element` | Create a new plugin, skill, or command in the GitHub Tech BM Second Brain |
| `/update-github-element` | Update a plugin, skill, or command in the GitHub Tech BM Second Brain |
| `/remove-github-element` | Remove a plugin, skill, or command from the GitHub Tech BM Second Brain |

## Core Principles (All Skills)

Every skill follows these governing principles:

- **SPAR Framework**: Sense → Plan → Act → React
- **Pyramid Principle**: Lead with the answer, structure top-down (Barbara Minto)
- **SCQA Pattern**: Situation → Complication → Question → Answer
- **MECE Decomposition**: Mutually Exclusive, Collectively Exhaustive
- **Confidence Calibration**: Explicit confidence levels, escalate when uncertain
- **Source Attribution**: Always cite frameworks and data sources
- **Practical & Adaptable**: Immediately usable, context-aware outputs

## Commands Reference (All Plugins)

Commands are slash-triggered shortcuts that invoke specialist skills with structured workflows. Every command follows SPAR methodology and produces structured deliverables.

| Plugin | Command | Description |
|--------|---------|-------------|
| Technology | `/advise-strategy` | Provide technology strategy advisory using consulting frameworks |
| Technology | `/assess-architecture` | Assess an architecture design or pattern against best practices |
| Technology | `/brief-ai-topic` | Create an AI briefing for CIO-level conversations |
| Technology | `/explain-tech-concept` | Explain a technology concept clearly and thoroughly |
| Technology | `/list-tech-references` | List technology references and resources for a topic |
| Technology | `/review-delivery` | Review delivery maturity and engineering excellence posture |
| Consulting | `/find-references` | Deep multi-source research with curated references |
| Consulting | `/find-benchmark` | Find and analyze industry benchmarks with sources and gap analysis |
| Consulting | `/problem-solve` | Structured problem decomposition and recommendation |
| Communication | `/create-improve-email` | Create or improve a professional corporate email |
| Communication | `/create-executive-summary` | Create a concise executive summary from content or topic |
| Communication | `/create-improve-powerpoint` | Create or improve a PowerPoint presentation |
| Communication | `/improve-text` | Refine and elevate professional writing |
| Communication | `/translate-en-pt` | Translate text from English to Brazilian Portuguese |
| Communication | `/translate-pt-en` | Translate text from Brazilian Portuguese to English |
| Finance | `/assess-portfolio` | Assess an IT application portfolio using TIME model |
| Finance | `/build-tbm-model` | Build a TBM cost model or taxonomy mapping in Excel |
| Finance | `/consolidate-excel` | Consolidate and analyze financial data in Excel |
| Finance | `/evaluate-business-case` | Evaluate a business case proposal for technology investment |
| AI | `/create-plugin` | Create a new plugin from scratch |
| AI | `/update-plugin` | Update an existing plugin |
| AI | `/create-skill` | Create a new skill from scratch |
| AI | `/update-skill` | Update an existing skill |
| AI | `/create-commands` | Create new commands for a plugin |
| AI | `/update-commands` | Update existing commands in a plugin |
| AI | `/create-context-window` | Create a context window for an AI agent |
| GitHub | `/create-github-element` | Create a new plugin, skill, or command in GitHub |
| GitHub | `/update-github-element` | Update a plugin, skill, or command in GitHub |
| GitHub | `/remove-github-element` | Remove a plugin, skill, or command from GitHub |

## Design Philosophy

### Why Skills Inside Plugins?

Plugins represent **distinct expert personas** (Technology Expert, Consulting Expert, etc.):
- Skills are **tightly coupled** to their domain
- Each plugin IS an expert with bundled capabilities
- Simpler mental model: "Load Technology Expert" = get all tech skills
- Easier versioning: Version the whole expert persona as a unit

This is a **"Second Brain of Experts"** approach, not a skill marketplace.

### Why Commands?

Commands provide **quick-trigger workflows** for common tasks:
- Each command invokes the relevant specialist skill automatically
- Structured output format ensures consistent, deliverable results
- SPAR methodology baked into every command execution
- No need to remember which skill does what — just use the command

## Workflow

### Development Process
1. **Draft** - Create/update plugins in Claude/Cowork sessions
2. **Review** - Validate content quality and framework accuracy
3. **Deploy** - Use GitHub Expert Plugin commands to push to GitHub
4. **Version** - Git maintains full history for rollbacks

### Deployment Commands

Claude handles all git operations via the GitHub Expert Plugin:
- `/create-github-element` — Add new plugins, skills, or commands
- `/update-github-element` — Sync changes from Claude/Cowork to GitHub
- `/remove-github-element` — Remove elements with double confirmation

Each command automatically updates this README and syncs the Obsidian vault after execution.

## Version History

| Plugin | Version | Date | Changes |
|--------|---------|------|---------|
| Technology Expert | v2.1.0 | 2026-02-16 | Initial deployment: 5 skills |
| Consulting Expert | v1.0.0 | 2026-02-17 | Initial deployment: 4 skills |
| Communication Expert | v1.0.0 | 2026-02-17 | Initial deployment: 4 skills |
| Finance Expert | v1.0.0 | 2026-02-17 | Initial deployment: 2 skills |
| Technology Expert | v2.1.0 | 2026-02-22 | Updated commands: explain-tech-concept, list-tech-references |
| Communication Expert | v1.0.0 | 2026-02-22 | Updated commands: 6 commands (email, summary, pptx, text, translate EN/PT) |
| Consulting Expert | v1.0.0 | 2026-02-22 | Updated commands: find-references, find-benchmark, problem-solve |
| Finance Expert | v1.0.0 | 2026-02-22 | Updated commands: consolidate-excel, evaluate-business-case |
| AI Expert | v1.1.0 | 2026-02-22 | New plugin: 8 skills, 7 commands |
| GitHub Expert | v1.0.0 | 2026-02-22 | New plugin: 1 skill, 3 commands |
| Consulting Expert | v2.0.0 | 2026-02-22 | Massive update: all skills + commands rewritten with layered What/How/Why, cross-plugin orchestration |
| Communication Expert | v2.0.0 | 2026-02-22 | Massive update: PowerPoint as flagship (JP Morgan design), all skills + commands rewritten |
| GitHub Expert | v2.0.0 | 2026-02-22 | Format alignment: skill + commands rewritten with layered What/How/Why framework |
| Technology Expert | v4.0.0 | 2026-02-22 | Massive update: 5 skills updated, 4 new commands (advise-strategy, assess-architecture, brief-ai-topic, review-delivery) |
| Finance Expert | v4.0.0 | 2026-02-22 | Massive update: 1 new skill (excel-for-finance), 2 new commands (assess-portfolio, build-tbm-model), all content updated |
| AI Expert | v2.0.0 | 2026-02-22 | Massive update: all 8 skills + 7 commands rewritten with v2.0.0 format standardization |

## How to Use

### Outside VDI Claude:
1. Reference plugins as expert knowledge sources
2. Ask domain-specific questions triggering relevant skills
3. Use slash commands for structured workflows
4. Apply generic frameworks to your actual JP Morgan context
5. Generate consulting-grade outputs for real work

### Example Interactions:
- `/problem-solve payment failure rate` → Structured MECE decomposition of the issue
- `/find-references LATAM real-time payments` → Deep research and synthesis
- `/create-improve-email escalation to CIO about vendor delays` → Professional email with BLUF
- `/consolidate-excel Q4 cost report` → TBM Framework cost analysis
- `/translate-en-pt executive summary` → Professional EN→PT-BR translation
- `/explain-tech-concept event-driven architecture` → Clear technology explanation
- `/create-plugin new-domain-expert` → Scaffold a new plugin from scratch
- `/update-github-element skill agile-specialist in technology-expert-plugin` → Sync to GitHub

## Contributing

**Author:** Arthur (JP Morgan LATAM Payments Technology)

**Maintenance:**
- Updates happen in Claude/Cowork sessions
- Deployments via GitHub Expert Plugin commands
- All changes version-controlled in GitHub
- Obsidian vault synced automatically after each deployment

## License

Private repository - All rights reserved

---

**Last Updated:** 2026-02-22
**Repository:** https://github.com/arthurpaivar/TBM
**Total Expertise:** 6 plugins, 25 skills, 29 commands
