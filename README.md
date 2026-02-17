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
│   ├── technology-expert-plugin/              [5 skills + 3 commands]
│   │   ├── .claude-plugin/
│   │   │   └── plugin.json
│   │   ├── README.md
│   │   ├── commands/
│   │   │   ├── tech-assess.md
│   │   │   ├── architecture-review.md
│   │   │   └── agile-metrics.md
│   │   └── skills/
│   │       ├── ai-specialist/SKILL.md
│   │       ├── agile-specialist/SKILL.md
│   │       ├── architecture-specialist/SKILL.md
│   │       ├── tech-delivery-specialist/SKILL.md
│   │       └── tech-strategy-advisory/SKILL.md
│   │
│   ├── consulting-expert-plugin/              [4 skills + 4 commands]
│   │   ├── .claude-plugin/
│   │   │   └── plugin.json
│   │   ├── README.md
│   │   ├── commands/
│   │   │   ├── research.md
│   │   │   ├── business-case.md
│   │   │   ├── benchmark.md
│   │   │   └── problem-solve.md
│   │   └── skills/
│   │       ├── problem-solving-specialist/SKILL.md
│   │       ├── deep-search-specialist/SKILL.md
│   │       ├── industry-benchmark-specialist/SKILL.md
│   │       └── business-case-specialist/SKILL.md
│   │
│   ├── communication-expert-plugin/           [4 skills + 4 commands]
│   │   ├── .claude-plugin/
│   │   │   └── plugin.json
│   │   ├── README.md
│   │   ├── commands/
│   │   │   ├── draft-email.md
│   │   │   ├── translate.md
│   │   │   ├── improve-text.md
│   │   │   └── presentation.md
│   │   └── skills/
│   │       ├── e-mail-generator/SKILL.md
│   │       ├── translation-specialist/SKILL.md
│   │       ├── powerpoint-specialist/SKILL.md
│   │       └── text-improver-specialist/SKILL.md
│   │
│   └── finance-expert-plugin/                 [2 skills + 2 commands]
│       ├── .claude-plugin/
│       │   └── plugin.json
│       ├── README.md
│       ├── commands/
│       │   ├── cost-analysis.md
│       │   └── portfolio-review.md
│       └── skills/
│           ├── tech-bm-specialist/SKILL.md
│           └── it-portfolio-management/SKILL.md
│
└── skills/
    ├── public/     (Anthropic built-in skills - docx, pdf, pptx, xlsx, etc.)
    ├── private/    (Reserved for future use)
    └── examples/   (Reference examples)
```

**Total:** 4 plugins | 15 skills | 13 commands

## Plugin Suite Overview

### 1. Technology Expert Plugin (v2.1.0)
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
| `/tech-assess` | Comprehensive technology assessment using SPAR framework with specialist skill selection |
| `/architecture-review` | Architecture review using enterprise patterns, ADRs, and best practices |
| `/agile-metrics` | Analyze DORA and agile delivery metrics with industry benchmarking |

### 2. Consulting Expert Plugin (v1.0.0)
**Expert in:** Structured problem-solving, research, benchmarking, business cases

| Skill | Focus Areas |
|-------|-------------|
| **Problem-Solving Specialist** | MECE decomposition, hypothesis-driven analysis, root cause (5 Whys, Fishbone), decision matrices |
| **Deep Search Specialist** | Multi-source research, vendor evaluation, landscape analysis, trend synthesis |
| **Industry Benchmark Specialist** | Gartner/Forrester/McKinsey benchmarks, peer comparison, maturity models, KPI targets |
| **Business Case Specialist** | NPV, IRR, TCO, cost-benefit analysis, investment proposals, stakeholder-specific framing |

| Command | What It Does |
|---------|-------------|
| `/research` | Deep multi-source research and synthesis on any topic |
| `/business-case` | Build a technology investment business case with ROI/NPV/IRR |
| `/benchmark` | Find and apply industry benchmarks from Gartner, Forrester, McKinsey |
| `/problem-solve` | Structured problem decomposition using MECE, SCQA, and root cause analysis |

### 3. Communication Expert Plugin (v1.0.0)
**Expert in:** Professional communication, translation, presentations, writing

| Skill | Focus Areas |
|-------|-------------|
| **E-mail Generator** | BLUF methodology, status updates, escalations, approvals, follow-ups, stakeholder communications |
| **Translation Specialist** | EN↔PT-BR professional translation, tech terminology, cultural adaptation for LATAM |
| **PowerPoint Specialist** | SCQA pattern, Pyramid Principle, presentation frameworks, storytelling for leadership, deck templates |
| **Text Improver Specialist** | Clarity, conciseness, tone calibration, structure, audience-aware rewriting |

| Command | What It Does |
|---------|-------------|
| `/draft-email` | Draft a professional corporate email with pyramid principle and cultural sensitivity |
| `/translate` | Professional EN↔PT-BR translation with terminology accuracy |
| `/improve-text` | Refine and elevate professional writing for clarity, tone, and structure |
| `/presentation` | Structure a presentation using pyramid principle and SCQA framework |

### 4. Finance Expert Plugin (v1.0.0)
**Expert in:** Technology Business Management, IT Portfolio governance

| Skill | Focus Areas |
|-------|-------------|
| **Tech BM Specialist** | TBM Framework 2.0, Taxonomy v5.0.1, cost transparency, showback/chargeback, Run/Grow/Transform, FinOps |
| **IT Portfolio Management** | Application portfolio (TIME model), investment governance, ITFM, demand management, 6Rs modernization |

| Command | What It Does |
|---------|-------------|
| `/cost-analysis` | Analyze IT costs using TBM Framework 2.0 and FinOps principles |
| `/portfolio-review` | Review and optimize IT application portfolio with rationalization frameworks |

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
| Technology | `/tech-assess` | Run a technology assessment or review |
| Technology | `/architecture-review` | Review architecture decisions and patterns |
| Technology | `/agile-metrics` | Analyze agile and DORA delivery metrics |
| Consulting | `/research` | Deep research and analysis on any topic |
| Consulting | `/business-case` | Build a technology investment business case |
| Consulting | `/benchmark` | Find and apply industry benchmarks |
| Consulting | `/problem-solve` | Structured problem decomposition and analysis |
| Communication | `/draft-email` | Draft a professional corporate email |
| Communication | `/translate` | Professional EN↔PT-BR translation |
| Communication | `/improve-text` | Refine and elevate professional writing |
| Communication | `/presentation` | Structure a presentation or slide deck |
| Finance | `/cost-analysis` | Analyze IT costs using TBM frameworks |
| Finance | `/portfolio-review` | Review and optimize IT application portfolio |

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
1. **Draft** - Create/update plugins in Obsidian (private drafting environment)
2. **Review** - Validate content quality and framework accuracy
3. **Deploy** - Use Claude to commit and push to GitHub
4. **Version** - Git maintains full history for rollbacks

### Deployment Commands
```bash
# Claude handles all git operations
User: "Claude, deploy [plugin/skill name] - [what changed]"

Claude automatically:
1. Copies files to /home/claude/TBM/plugins/
2. Commits with semantic message
3. Pushes to GitHub
4. Returns commit hash
```

## Version History

| Plugin | Version | Date | Changes |
|--------|---------|------|---------|
| Technology Expert | v2.1.0 | 2026-02-16 | Initial deployment: 5 skills |
| Consulting Expert | v1.0.0 | 2026-02-17 | Initial deployment: 4 skills |
| Communication Expert | v1.0.0 | 2026-02-17 | Initial deployment: 4 skills |
| Finance Expert | v1.0.0 | 2026-02-17 | Initial deployment: 2 skills |

## How to Use

### Outside VDI Claude:
1. Reference plugins as expert knowledge sources
2. Ask domain-specific questions triggering relevant skills
3. Use slash commands for structured workflows
4. Apply generic frameworks to your actual JP Morgan context
5. Generate consulting-grade outputs for real work

### Example Interactions:
- `/problem-solve payment failure rate` → Structured MECE decomposition of the issue
- `/business-case cloud migration` → Full business case with NPV/IRR analysis
- `/draft-email escalation to CIO about vendor delays` → Professional email with BLUF methodology
- `/cost-analysis Run/Grow/Transform split` → TBM Framework cost analysis
- `/translate executive summary to Portuguese` → Professional EN→PT-BR translation
- `/architecture-review microservices migration` → Enterprise architecture assessment with ADRs
- `/agile-metrics Q4 sprint delivery` → DORA metrics analysis with industry benchmarks

## Contributing

**Author:** Arthur (JP Morgan LATAM Payments Technology)

**Maintenance:**
- Updates happen in Obsidian drafting environment
- Deployments via Claude automation
- All changes version-controlled in GitHub

## License

Private repository - All rights reserved

---

**Last Updated:** 2026-02-17
**Repository:** https://github.com/arthurpaivar/TBM
**Total Expertise:** 4 plugins, 15 skills, 13 commands
