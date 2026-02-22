# Technology Expert Plugin

Specialist in Enterprise AI, Agile Delivery, Architecture, Engineering Excellence, and Technology Strategy for payments technology. Serves as the **modular knowledge base (second brain)** for a Tech BM working directly with a Payments CIO — providing deep tech insights for CIO-level conversations.

## Cross-Plugin Architecture

This plugin is designed as a **modular foundation** that other plugins reference:
- **Consulting Plugin**: Uses technology skills for tech advisory in problem solving, benchmarks, and deep research
- **Communication Plugin**: Uses technology skills for PowerPoint content, executive narratives, and tech explanations
- **Finance Plugin**: Uses technology skills for IT portfolio concepts, cost analysis, and TBM-related technology insights

## Skills

- **AI Specialist** (`ai-specialist`): Enterprise AI — agents (ReAct, Plan-Execute, Reflection, Multi-Agent), MCP protocol and adoption, GenAI, RAG, context windows, AI governance (SR 11-7, EU AI Act, NIST AI RMF), AI ROI frameworks, payments AI use cases, responsible AI principles
- **Agile Specialist** (`agile-specialist`): SAFe 6.0 competencies, DORA metrics (5 metrics with Elite/High/Medium/Low thresholds), team topologies (Skelton & Pais), Scrum, Kanban, flow metrics, WSJF, OKRs, lean portfolio management, 2025 DORA AI findings
- **Architecture Specialist** (`architecture-specialist`): Enterprise architecture (TOGAF ADM, Zachman), application patterns (monolith → microservices → serverless), integration patterns (event-driven, CQRS, event sourcing, saga), data architecture (data mesh, lakehouse, polyglot persistence), cloud architecture (Well-Architected, 12-factor, containers/K8s), API strategy (REST, GraphQL, gRPC, AsyncAPI), payments architecture (PCI-DSS, ISO 20022, payment rails, settlement, resilience patterns), ADRs
- **Tech Delivery Specialist** (`tech-delivery-specialist`): SDLC models, DevOps practices (CALMS framework), CI/CD pipeline design, deployment strategies (rolling, blue-green, canary, feature flags), platform engineering (IDP, golden paths, DevEx), SRE (SLIs/SLOs, error budgets, observability, incident management), quality engineering (testing pyramid, shift-left)
- **Tech Strategy Advisory** (`tech-strategy-advisory`): McKinsey frameworks (3Ds, Six Building Blocks, Three Horizons), BCG Platinion (transformation phases, GAMMA, Technology Advantage), Accenture (Total Enterprise Reinvention), TOM design (6 components), product operating model, capability mapping, value stream mapping, technology radar, build vs buy vs partner, business case structure, technology governance, investment categories (Run/Grow/Transform)

## Commands

| Command | Description | Skills Used |
|---------|-------------|-------------|
| `/explain-tech-concept` | Explain a technology concept clearly for CIO-level understanding | Routes to appropriate skill by topic |
| `/assess-architecture` | Assess an architecture design or pattern against best practices | `architecture-specialist` |
| `/review-delivery` | Review delivery maturity and engineering excellence posture | `tech-delivery-specialist` + `agile-specialist` |
| `/advise-strategy` | Provide technology strategy advisory using consulting frameworks | `tech-strategy-advisory` |
| `/brief-ai-topic` | Create an AI briefing for CIO-level conversations | `ai-specialist` |
| `/list-tech-references` | Find and compile technology references for a topic | Routes to appropriate skill by topic |

## Skill-to-Command Mapping

```
ai-specialist         ← /brief-ai-topic, /explain-tech-concept, /list-tech-references
agile-specialist      ← /review-delivery, /explain-tech-concept, /list-tech-references
architecture-specialist ← /assess-architecture, /explain-tech-concept, /list-tech-references
tech-delivery-specialist ← /review-delivery, /explain-tech-concept, /list-tech-references
tech-strategy-advisory  ← /advise-strategy, /explain-tech-concept, /list-tech-references
```

Every skill is reachable via at least one dedicated command and also via the routing commands (`/explain-tech-concept`, `/list-tech-references`).

## Usage Examples

```
/explain-tech-concept event sourcing for payment ledgers
/assess-architecture microservices migration for our payment processing platform
/review-delivery DevOps maturity assessment for the payments engineering organization
/advise-strategy build vs buy decision for real-time fraud detection
/brief-ai-topic AI agents for autonomous payment operations
/list-tech-references data mesh implementation in financial services
```

## Author
Arthur
