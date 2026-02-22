---
name: ai-specialist
description: >
  This skill should be used when the user asks about "AI", "artificial intelligence", "agents",
  "AI agents", "assistants", "MCP", "Model Context Protocol", "context windows",
  "LLM", "large language models", "GenAI", "generative AI",
  "prompt engineering", "RAG", "retrieval augmented generation", "fine-tuning",
  "AI governance", "responsible AI", "AI strategy", "enterprise AI", "copilots",
  "AI adoption", "AI use cases", "AI ROI", "MLOps", "AI platforms",
  "AI in payments", "AI in banking", "AI regulation", "SR 11-7", "EU AI Act",
  "NIST AI RMF", "model risk management", "AI operations", "agentic AI",
  "AI orchestration", "AI safety", "AI evaluation", "AI benchmarks",
  or needs guidance on AI technologies and their enterprise application in payments.
  Use whenever the user needs AI technology insights for CIO-level conversations.
version: 3.0.0
---

# Skill — AI Specialist

**Expert in enterprise AI with deep knowledge of modern AI architectures, agent patterns, the Model Context Protocol, and enterprise adoption strategies for regulated financial services.** This skill provides authoritative, forward-looking guidance on AI technologies, governance frameworks, and ROI models relevant to a Payments CIO. It serves as the modular AI knowledge base that other plugins (consulting, communication, finance) reference for AI-related insights.

**Core Principles**: SPAR Framework, Pyramid Principle, SCQA Pattern, MECE Decomposition, Confidence Calibration, Source Attribution, Practical & Adaptable — these govern all outputs from this skill.

**Trigger keywords**: AI, artificial intelligence, agents, AI agents, MCP, Model Context Protocol, LLM, GenAI, generative AI, RAG, fine-tuning, AI governance, responsible AI, AI strategy, enterprise AI, copilots, AI adoption, AI use cases, AI ROI, MLOps, AI in payments, SR 11-7, EU AI Act, NIST AI RMF, model risk management, agentic AI, AI orchestration, AI safety.

## Section 1 — AI Agent Landscape

### 1.1 Agent Architecture Patterns

Modern AI agents follow four core patterns:

1. **ReAct (Reason + Act)**: Agent reasons about a task, takes an action, observes the result, and iterates. Most common pattern for tool-using agents.
   - Best for: Information retrieval, task execution, customer support automation
   - Flow: Think → Act → Observe → Think → Act → ... → Answer

2. **Plan-and-Execute**: Agent creates a full plan upfront, then executes step by step. Better for complex, multi-step workflows.
   - Best for: Regulatory reporting, multi-system reconciliation, complex analysis
   - Flow: Plan → Execute Step 1 → Execute Step 2 → ... → Verify

3. **Reflection**: Agent critiques its own output and self-corrects. Improves quality for writing, code, and analysis tasks.
   - Best for: Document generation, code review, compliance checking
   - Flow: Generate → Critique → Revise → Verify

4. **Multi-Agent Orchestration**: Multiple specialized agents collaborate under an orchestrator. Best for complex systems requiring domain specialization.
   - Best for: End-to-end payment processing, fraud detection + remediation, cross-functional workflows
   - Flow: Orchestrator → Delegate to Agent A, B, C → Synthesize

### 1.2 Agent vs. Assistant vs. Copilot

| Archetype | Autonomy | Human Control | Use Case |
|-----------|----------|---------------|----------|
| **Copilot** | Low — augments in real-time | High — suggestions only | Autocomplete, side-panel Q&A, code completion |
| **Assistant** | Medium — follows instructions | Medium — responds to requests | Chat interfaces, document generation, search |
| **Agent** | High — autonomous goal pursuit | Low — minimal oversight | Multi-step workflows, autonomous operations |

### 1.3 Key Agent Capabilities
- **Tool Use**: Calling APIs, querying databases, reading files, executing code
- **Memory**: Short-term (context window), long-term (vector stores, knowledge graphs)
- **Planning**: Breaking complex goals into actionable steps
- **Reflection**: Self-evaluation and course correction
- **Multi-modal**: Processing text, images, audio, video, and structured data

### 1.4 Agent Evaluation Framework
When assessing AI agent maturity:
- **Accuracy**: Does the agent produce correct outputs? Measured by task success rate
- **Reliability**: Does it perform consistently? Measured by variance across runs
- **Safety**: Does it stay within boundaries? Measured by guardrail adherence
- **Efficiency**: Does it use resources well? Measured by token usage, API calls, latency
- **Autonomy Level**: How much human oversight is needed? Measured by intervention rate

## Section 2 — Model Context Protocol (MCP)

### 2.1 What is MCP?
MCP is an **open standard** introduced by Anthropic in November 2024 to standardize how AI systems integrate with external tools, systems, and data sources. It uses JSON-RPC 2.0 transport and borrows message-flow ideas from the Language Server Protocol (LSP).

**Before MCP**: N×M integration problem — every AI model needed custom connectors for every tool.
**After MCP**: Universal protocol — implement once, connect to the entire ecosystem.

### 2.2 MCP Architecture
- **MCP Host**: The AI application (e.g., Claude Desktop, IDE extension, custom agent)
- **MCP Client**: Protocol handler within the host that manages server connections
- **MCP Server**: Lightweight service exposing specific capabilities (tools, resources, prompts)
- **Transport**: stdio (local) or HTTP+SSE / Streamable HTTP (remote)

### 2.3 MCP Capabilities
Servers expose three types of capabilities:
1. **Tools**: Functions the AI can call (e.g., search database, create ticket, send email)
2. **Resources**: Data the AI can read (e.g., files, database records, API responses)
3. **Prompts**: Pre-built prompt templates for common tasks

### 2.4 Industry Adoption Timeline
- **Nov 2024**: Anthropic launches MCP as open standard
- **Mar 2025**: OpenAI adopted MCP across its products
- **Jul 2025**: AWS released key MCP integrations
- **Dec 2025**: Anthropic donated MCP to the Agentic AI Foundation (AAIF) under the Linux Foundation, co-founded with Block and OpenAI
- **2026**: Transition from experimentation to enterprise-wide production adoption
- MCP market projected to reach $1.8B, driven by regulated industries (finance, healthcare, manufacturing)

### 2.5 Enterprise MCP Considerations
- **Authentication & Identity**: Scoped, short-lived tokens via SSO (not blanket API keys)
- **RBAC**: Role-based access control for tool permissions
- **Audit Logging**: Full trace of agent actions for compliance
- **Data Governance**: Control what data agents can access and where it flows
- **Deployment**: Azure Container Apps, AWS Lambda, Kubernetes, or managed platforms

## Section 3 — Context Windows & Efficient AI

### 3.1 Context Window Management
- Context windows define how much information an AI model can process in a single interaction
- Current frontier models: 128K–1M+ tokens
- **Challenge**: As MCP scales, loading all tool definitions upfront consumes tokens rapidly
- **Solutions**: On-demand tool loading, data filtering before reaching the model, code execution for complex logic

### 3.2 RAG (Retrieval-Augmented Generation)
- Retrieve relevant documents/data from external sources at query time
- Combine with LLM generation for grounded, up-to-date responses
- Components: embedding model, vector database, retrieval pipeline, reranking
- Enterprise RAG: document chunking strategies, metadata filtering, hybrid search (semantic + keyword)

### 3.3 Fine-Tuning vs. RAG vs. Prompting

| Approach | When to Use | Cost | Freshness |
|---|---|---|---|
| Prompt Engineering | Most use cases, start here | Low | Real-time |
| RAG | Need grounding in specific documents/data | Medium | Near real-time |
| Fine-Tuning | Need consistent style, domain-specific behavior, or latency optimization | High | Static (retraining needed) |

**Decision rule for CIO conversations**: Start with prompting. Move to RAG when accuracy on proprietary data matters. Fine-tune only when you need consistent behavior at scale with optimized latency.

## Section 4 — Enterprise AI Strategy

### 4.1 AI Use Case Prioritization
Evaluate use cases across four dimensions:
1. **Business Impact**: Revenue, cost savings, risk reduction, experience improvement
2. **Feasibility**: Data availability, technical complexity, model maturity
3. **Scalability**: Can it be applied across the organization?
4. **Risk**: Regulatory, reputational, ethical, accuracy requirements

### 4.2 AI Use Cases in Payments & Financial Services

**High-Value, Production-Ready (2025–2026)**:
- Fraud detection and prevention (real-time transaction scoring)
- Anti-money laundering (AML) pattern detection and SAR narrative generation
- Customer service automation (intelligent triage, FAQ resolution, escalation)
- Document processing (invoice extraction, KYC document verification)
- Code generation and developer productivity (copilot-assisted development)
- Regulatory reporting automation (narrative generation, data validation)

**Emerging (2026–2027)**:
- Autonomous payment operations agents (exception handling, reconciliation)
- Real-time credit decisioning with explainable AI
- Personalized product recommendations at scale
- AI-powered treasury and liquidity management
- Predictive maintenance for payment rails and infrastructure

**Experimental (2027+)**:
- Multi-agent orchestration for end-to-end payment lifecycle
- AI-native payment products (adaptive pricing, dynamic routing)
- Autonomous compliance monitoring and remediation

### 4.3 AI ROI Framework
Measuring AI value across five dimensions:
1. **Efficiency Gains**: FTE equivalent savings, cost per transaction reduction
2. **Quality Improvements**: Defect rate reduction, false positive rate improvement
3. **Revenue Impact**: Revenue uplift, NPS improvement, conversion rate
4. **Risk Reduction**: Fraud losses avoided, regulatory findings reduction
5. **Innovation Velocity**: Time-to-market reduction, experiment throughput

### 4.4 AI Operating Model
How to organize AI capabilities in the enterprise:
- **Centralized CoE**: Single AI team serving the enterprise. Best for: early stages, governance consistency
- **Federated Model**: AI capabilities embedded in business units with central standards. Best for: scaled organizations, domain-specific needs
- **Hub-and-Spoke**: Central platform team + distributed AI engineers. Best for: balancing governance with speed
- **Key Roles**: AI/ML Engineers, Data Engineers, MLOps Engineers, AI Product Managers, AI Ethics/Governance Officers, Prompt Engineers

## Section 5 — AI Governance for Regulated Industries

### 5.1 Model Risk Management (SR 11-7 / OCC 2011-12)
The Federal Reserve's SR 11-7 guidance establishes the standard for model risk management in banking:
- **Model Development**: Documentation of methodology, assumptions, limitations
- **Model Validation**: Independent validation before production deployment
- **Model Monitoring**: Ongoing performance monitoring, drift detection, revalidation triggers
- **Model Inventory**: Centralized registry of all models with risk tiering
- **Board Oversight**: Senior management accountability for model risk

### 5.2 EU AI Act (Effective August 2025)
Risk-based regulatory framework for AI in the European Union:
- **Unacceptable Risk**: Banned (social scoring, manipulative AI, real-time biometric surveillance)
- **High Risk**: Strict requirements (credit scoring, fraud detection, hiring). Requires conformity assessment, documentation, human oversight, transparency
- **Limited Risk**: Transparency obligations (chatbots must disclose AI nature)
- **Minimal Risk**: No specific requirements (spam filters, AI-assisted search)

**Impact on Payments**: Credit decisioning, fraud detection, and AML systems classified as HIGH RISK — requiring documentation, testing, monitoring, and human oversight mechanisms.

### 5.3 NIST AI Risk Management Framework (AI RMF 1.0)
Four core functions:
1. **Govern**: Establish AI risk governance structure, policies, and accountability
2. **Map**: Identify AI risks in context (intended use, stakeholders, potential harms)
3. **Measure**: Assess and analyze AI risks using quantitative and qualitative methods
4. **Manage**: Prioritize and act on AI risks, monitor effectiveness of controls

### 5.4 Responsible AI Principles
- **Fairness**: Bias testing across protected classes, disparate impact analysis
- **Transparency**: Explainability requirements for high-stakes decisions
- **Privacy**: Data minimization, consent management, anonymization
- **Security**: Adversarial robustness, prompt injection defense, data poisoning prevention
- **Accountability**: Clear ownership, audit trails, incident response procedures
- **Human Oversight**: Human-in-the-loop for high-risk decisions, override mechanisms

## Section 6 — AI Benchmarks & Industry Data

### Key Benchmarks
- Enterprise AI adoption maturity (Gartner, McKinsey Digital)
- Typical AI project success rates: 50–60% reach production (McKinsey 2024)
- Financial services AI spend: 13–15% of IT budget allocated to AI/ML (Gartner 2025)
- AI team composition ratios: 1 ML engineer : 2 data engineers : 0.5 MLOps (industry average)
- Fraud detection AI: 30–50% reduction in false positives (industry benchmark)
- AML/KYC automation: 40–60% reduction in manual review time
- 2025 DORA AI findings: +7.5% documentation quality, +3.4% code quality, BUT -7.2% delivery stability

### AI Hallucination Mitigation Strategies
- Grounding via RAG with authoritative sources
- Guardrails and output validation
- Confidence scoring and abstention policies
- Human-in-the-loop review for high-stakes outputs
- Chain-of-thought verification

## Output Patterns

### AI Executive Briefing
```
TOPIC: [AI topic]
AUDIENCE: CIO / Executive Leadership

SITUATION: [Current state of this AI area in the industry]
COMPLICATION: [Why this matters now for payments]
QUESTION: [Strategic question the CIO should be asking]
ANSWER: [Recommended position and next steps]

MATURITY ASSESSMENT:
- Industry: [Where the industry is]
- Our organization: [Where we are — or assessment criteria]
- Gap: [What needs to close]

USE CASES (Payments-Specific):
1. [Use case] — [Impact] — [Readiness: Production/Emerging/Experimental]
2. [Use case] — [Impact] — [Readiness]

GOVERNANCE IMPLICATIONS:
- [Regulatory framework] — [What it means for us]

RECOMMENDATION:
- Short-term (0-6mo): [Action]
- Medium-term (6-18mo): [Action]
- Long-term (18-36mo): [Action]

CONFIDENCE: [High/Medium/Low] — [Rationale]
```

### AI Use Case Assessment
```
USE CASE: [Name]
DOMAIN: [Fraud/AML/Operations/Customer/Developer/etc.]

BUSINESS IMPACT: [High/Medium/Low] — [Quantified where possible]
FEASIBILITY: [High/Medium/Low] — [Data readiness, model maturity, integration complexity]
SCALABILITY: [High/Medium/Low] — [Cross-org applicability]
RISK: [High/Medium/Low] — [Regulatory, reputational, accuracy]

ARCHITECTURE: [Agent pattern, model choice, integration approach]
GOVERNANCE: [SR 11-7 tier, EU AI Act classification, required controls]
ROI ESTIMATE: [5 dimensions from ROI framework]

RECOMMENDATION: [Proceed/Pilot/Defer] — [Rationale]
```

### AI Governance Assessment
```
ORGANIZATION: [Name]
SCOPE: [AI systems under review]

REGULATORY POSTURE:
- SR 11-7 compliance: [Status]
- EU AI Act readiness: [Status]
- NIST AI RMF alignment: [Status]

MODEL INVENTORY: [Number of models, risk tiers]
VALIDATION COVERAGE: [% of models independently validated]
MONITORING: [Drift detection, performance monitoring status]

GAPS:
1. [Gap] — [Impact] — [Priority]

RECOMMENDATIONS:
1. [Action] — [Timeline] — [Owner]

CONFIDENCE: [High/Medium/Low]
```

## Quality Checks

- [ ] Is the AI guidance grounded in current industry developments and regulatory requirements?
- [ ] Does the output reference specific frameworks (SR 11-7, EU AI Act, NIST AI RMF)?
- [ ] Are AI use cases relevant to payments and financial services context?
- [ ] Is the ROI framework quantifiable with specific metrics?
- [ ] Are governance recommendations appropriate for a regulated environment?
- [ ] Does the output distinguish between proven, emerging, and experimental AI capabilities?
- [ ] Are sources and frameworks properly attributed?
- [ ] Is the content suitable for CIO-level conversations?

---

**Confidence Calibration**: High confidence for established AI patterns (agents, RAG, governance frameworks). Medium confidence for adoption timelines and market projections — these shift rapidly. Low confidence for 2027+ experimental predictions — recommend web search for latest data.

**Triggers**: Activate when user needs AI technology insights, governance guidance, agent architecture patterns, MCP information, or AI strategy for CIO-level conversations in financial services.
