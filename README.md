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
- ✅ Consistent, expert-level guidance on demand
- ✅ No compliance or data security issues
- ✅ Methodologies are generic, applications are specific
- ✅ Your VDI Claude becomes a specialized advisor for technology leadership

## Repository Structure

```
TBM/
├── README.md
├── plugins/
│   ├── technology-expert-plugin/          [4 skills - 800 lines]
│   │   ├── README.md
│   │   ├── plugin.json
│   │   └── skills/
│   │       ├── ai-specialist.md
│   │       ├── agile-specialist.md
│   │       ├── tech-delivery-specialist.md
│   │       └── tech-strategy-advisory.md
│   │
│   ├── consulting-expert-plugin/          [4 skills - 875 lines]
│   │   ├── README.md
│   │   ├── plugin.json
│   │   └── skills/
│   │       ├── problem-solving-specialist.md
│   │       ├── deep-search-specialist.md
│   │       ├── industry-benchmark-specialist.md
│   │       └── business-case-specialist.md
│   │
│   ├── communication-expert-plugin/       [4 skills - 1,073 lines]
│   │   ├── README.md
│   │   ├── plugin.json
│   │   └── skills/
│   │       ├── e-mail-generator.md
│   │       ├── translation-specialist.md
│   │       ├── powerpoint-specialist.md
│   │       └── text-improver-specialist.md
│   │
│   └── finance-expert-plugin/             [2 skills - 377 lines]
│       ├── README.md
│       ├── plugin.json
│       └── skills/
│           ├── tech-bm-specialist.md
│           └── it-portfolio-management.md
│
└── skills/
    ├── public/     (Anthropic built-in skills - docx, pdf, pptx, xlsx, etc.)
    ├── private/    (Reserved for future use)
    └── examples/   (Reference examples)
```

**Total:** 4 plugins | 14 skills | ~3,125 lines of expertise

## Plugin Suite Overview

### 1. Technology Expert Plugin (v2.1.0)
**Expert in:** AI/MCP, Agile, Tech Delivery, Strategy

| Skill | Focus Areas |
|-------|-------------|
| **AI Specialist** | MCP architecture, agent patterns (ReAct, Plan-Execute), RAG vs fine-tuning, enterprise AI governance |
| **Agile Specialist** | SAFe 6.0, DORA metrics (Elite/High/Medium/Low tiers), PI planning, WSJF prioritization |
| **Tech Delivery Specialist** | SDLC, DevOps (CALMS), CI/CD pipelines, SRE principles (SLIs/SLOs/SLAs), testing pyramid |
| **Tech Strategy Advisory** | McKinsey 3Ds, BCG Digital Transformation, Accenture frameworks, TOM design, capability mapping |

### 2. Consulting Expert Plugin (v1.0.0)
**Expert in:** Structured problem-solving, research, benchmarking, business cases

| Skill | Focus Areas |
|-------|-------------|
| **Problem-Solving Specialist** | MECE decomposition, hypothesis-driven analysis, root cause (5 Whys, Fishbone), decision matrices |
| **Deep Search Specialist** | Multi-source research, vendor evaluation, landscape analysis, trend synthesis |
| **Industry Benchmark Specialist** | Gartner/Forrester/McKinsey benchmarks, peer comparison, maturity models, KPI targets |
| **Business Case Specialist** | NPV, IRR, TCO, cost-benefit analysis, investment proposals, stakeholder-specific framing |

### 3. Communication Expert Plugin (v1.0.0)
**Expert in:** Professional communication, translation, presentations, writing

| Skill | Focus Areas |
|-------|-------------|
| **E-mail Generator** | BLUF methodology, status updates, escalations, approvals, follow-ups, stakeholder communications |
| **Translation Specialist** | EN↔PT-BR professional translation, tech terminology, cultural adaptation for LATAM |
| **PowerPoint Specialist** | SCQA pattern, Pyramid Principle, presentation frameworks, storytelling for leadership, deck templates |
| **Text Improver Specialist** | Clarity, conciseness, tone calibration, structure, audience-aware rewriting |

### 4. Finance Expert Plugin (v1.0.0)
**Expert in:** Technology Business Management, IT Portfolio governance

| Skill | Focus Areas |
|-------|-------------|
| **Tech BM Specialist** | TBM Framework 2.0, Taxonomy v5.0.1, cost transparency, showback/chargeback, Run/Grow/Transform, FinOps |
| **IT Portfolio Management** | Application portfolio (TIME model), investment governance, ITFM, demand management, 6Rs modernization |

## Core Principles (All Skills)

Every skill follows these governing principles:

- **SPAR Framework**: Sense → Plan → Act → React
- **Pyramid Principle**: Lead with the answer, structure top-down (Barbara Minto)
- **SCQA Pattern**: Situation → Complication → Question → Answer
- **MECE Decomposition**: Mutually Exclusive, Collectively Exhaustive
- **Confidence Calibration**: Explicit confidence levels, escalate when uncertain
- **Source Attribution**: Always cite frameworks and data sources
- **Practical & Adaptable**: Immediately usable, context-aware outputs

## Design Philosophy

### Why Skills Inside Plugins?

Plugins represent **distinct expert personas** (Technology Expert, Consulting Expert, etc.):
- Skills are **tightly coupled** to their domain
- Each plugin IS an expert with bundled capabilities
- Simpler mental model: "Load Technology Expert" = get all tech skills
- Easier versioning: Version the whole expert persona as a unit

This is a **"Second Brain of Experts"** approach, not a skill marketplace.

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

| Plugin | Version | Commit | Date | Changes |
|--------|---------|--------|------|---------|
| Technology Expert | v2.1.0 | 53cec1d | 2026-02-16 | Initial deployment: 4 skills |
| Consulting Expert | v1.0.0 | 72b011d | 2026-02-17 | Initial deployment: 4 skills |
| Communication Expert | v1.0.0 | 944a4b1 | 2026-02-17 | Initial deployment: 4 skills |
| Finance Expert | v1.0.0 | c8e568c | 2026-02-17 | Initial deployment: 2 skills |

## How to Use

### Inside VDI Claude:
1. Reference plugins as expert knowledge sources
2. Ask domain-specific questions triggering relevant skills
3. Apply generic frameworks to your actual JP Morgan context
4. Generate consulting-grade outputs for real work

### Example Interactions:
- "Using MECE decomposition, analyze our payment failure rate" → Problem-Solving Specialist
- "Build a business case for cloud migration with NPV/IRR" → Business Case Specialist
- "Draft an escalation email to the CIO about vendor delays" → E-mail Generator
- "What's our Run/Grow/Transform split?" → Tech BM Specialist
- "Translate this executive summary to Portuguese" → Translation Specialist

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
**Total Expertise:** 4 plugins, 14 skills, ~3,125 lines of consulting-grade frameworks
