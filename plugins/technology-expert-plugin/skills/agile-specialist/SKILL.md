---
name: agile-specialist
description: >
  This skill should be used when the user asks about "agile", "scrum", "sprint",
  "backlog", "user stories", "velocity", "SAFe", "SAFe 6.0", "PI planning", "retrospective",
  "kanban", "agile metrics", "story points", "definition of done", "agile transformation",
  "DORA metrics", "deployment frequency", "lead time", "change failure rate", "MTTR",
  "flow metrics", "WSJF", "agile release train", "ART", "value stream",
  "team topologies", "product teams", "agile at scale", "lean portfolio management",
  "OKRs", "agile governance", "delivery metrics", "predictability",
  or needs help structuring agile delivery or assessing delivery performance.
  Use whenever the user needs agile frameworks, delivery metrics, or team effectiveness guidance.
version: 3.0.0
---

# Skill — Agile Specialist

**Expert agile practitioner with deep knowledge of SAFe 6.0, DORA metrics, Scrum, Kanban, team topologies, and modern delivery practices for enterprise payments technology.** This skill provides authoritative guidance with adaptable templates, frameworks, and delivery narratives for CIO-level conversations about engineering effectiveness and agile maturity. It serves as the modular agile knowledge base that other plugins (consulting for benchmarks, communication for delivery narratives, finance for capacity planning) reference.

**Core Principles**: SPAR Framework, Pyramid Principle, SCQA Pattern, MECE Decomposition, Confidence Calibration, Source Attribution, Practical & Adaptable — these govern all outputs from this skill.

**Trigger keywords**: agile, scrum, sprint, backlog, user stories, velocity, SAFe, SAFe 6.0, PI planning, retrospective, kanban, DORA metrics, deployment frequency, lead time, change failure rate, MTTR, flow metrics, WSJF, agile release train, ART, value stream, team topologies, delivery metrics, predictability, OKRs, agile governance.

## Section 1 — SAFe 6.0 — Scaled Agile Framework

### 1.1 Competency-Based Model
SAFe 6.0 places **seven core competencies** at the center of the model, shifting from practices/roles to capability building:

1. **Team and Technical Agility**: High-performing agile teams with strong engineering practices
2. **Agile Product Delivery**: Customer-centric design, DevOps, continuous delivery
3. **Enterprise Solution Delivery**: Coordinating large-scale, multi-ART solutions
4. **Lean Portfolio Management**: Strategy, funding, and governance
5. **Organizational Agility**: Lean-thinking culture across the enterprise
6. **Continuous Learning Culture**: Innovation, learning cycles, commitment to improvement
7. **Lean-Agile Leadership**: Leaders who model and champion Lean-Agile mindset

### 1.2 SAFe Measurement: Outcomes, Flow, Competency
SAFe 6.0's **Measure and Grow** approach evaluates business agility through three domains:

- **Outcomes**: Are solutions meeting business and customer needs? Measured via KPIs, OKRs, NPS, employee engagement
- **Flow**: Is value being delivered efficiently? Measured via flow metrics (velocity, throughput, cycle time, load, distribution, predictability)
- **Competency**: How mature are teams in SAFe practices? Measured via competency assessments

### 1.3 Key SAFe Constructs
- **PI Planning**: Quarterly planning cadence. Structure PI objectives linking team-level features to strategic themes. Target predictability >80%
- **ART (Agile Release Train)**: Long-lived team-of-teams aligned to a single value stream. Map capabilities to value streams
- **Program Board**: Visualize cross-team dependencies and milestones
- **WSJF** (Weighted Shortest Job First): Prioritization = Cost of Delay / Job Duration
- **Innovation & Planning (IP) Iteration**: Dedicated time for innovation, enablers, and planning

### 1.4 SAFe & AI (6.0 Evolution)
SAFe 6.0 acknowledges integrating AI into agile practices:
- AI for backlog refinement, story generation, and test automation
- Predictive analytics for delivery forecasting
- AI-augmented retrospectives and pattern recognition
- **2025 DORA AI Paradox**: AI improves individual task quality but may reduce team-level delivery stability without proper adoption governance

## Section 2 — DORA Metrics — DevOps Research & Assessment

### 2.1 The Five DORA Metrics
1. **Deployment Frequency**: How often code reaches production
2. **Lead Time for Changes**: Commit to production
3. **Change Failure Rate**: % of deployments causing incidents
4. **Mean Time to Restore (MTTR)**: Incident recovery speed
5. **Reliability** (5th metric, added 2024): Operational performance against targets

### 2.2 DORA Performance Levels

| Metric | Elite | High | Medium | Low |
|---|---|---|---|---|
| Deploy Frequency | On-demand (multiple/day) | Weekly–Monthly | Monthly–Biannual | <1 per 6 months |
| Lead Time | <1 hour | 1 day–1 week | 1–6 months | >6 months |
| Change Failure Rate | <5% | 5–10% | 10–15% | >15% |
| MTTR | <1 hour | <1 day | 1 day–1 week | >1 week |

### 2.3 2025 DORA Report Key Findings
- **+7.5%** improvement in documentation quality with AI assistance
- **+3.4%** better code quality with AI tools
- **+3.1%** faster code reviews with AI support
- **+1.8%** reduction in code complexity
- **BUT: -7.2%** reduction in delivery stability, **-1.5%** reduction in throughput
- **Key insight**: Organizations need seven critical capabilities before AI tools deliver full value at team level

### 2.4 Combining DORA + Flow Metrics
Use DORA alongside SAFe Flow Metrics for full-picture delivery health:
- DORA measures engineering effectiveness (build → deploy)
- Flow metrics measure value delivery (idea → customer)
- Together they quantify DevOps transformation impact against business results

## Section 3 — Team Topologies

### 3.1 Four Fundamental Team Types (Skelton & Pais)
1. **Stream-Aligned Teams**: Primary team type. Aligned to a single value stream. Responsible for end-to-end delivery. Target: 80%+ of teams
2. **Platform Teams**: Provide self-service internal platforms that reduce cognitive load for stream-aligned teams
3. **Enabling Teams**: Help stream-aligned teams overcome obstacles, adopt new practices, and learn new technologies. Temporary engagement model
4. **Complicated-Subsystem Teams**: Own complex components requiring deep specialist knowledge (e.g., payment routing engines, cryptographic modules)

### 3.2 Three Interaction Modes
1. **Collaboration**: Two teams working closely together for discovery (time-boxed)
2. **X-as-a-Service**: One team provides a service consumed by others (clear API contract)
3. **Facilitating**: One team helps another learn or adopt a new capability

### 3.3 Team Sizing and Structure
- **Two-pizza rule**: 5–9 people per team
- **Cognitive load management**: Limit the complexity each team must handle
- **Conway's Law**: Team structure shapes system architecture. Design teams to produce the architecture you want
- **Inverse Conway Maneuver**: Restructure teams to drive desired architecture changes

## Section 4 — Scrum & Kanban Essentials

### 4.1 Sprint Planning
Structure sprint goals linking to business outcomes. Emphasize:
- Regulatory/compliance stories that cannot slip
- Settlement cycle dependencies and release windows
- Cross-team dependencies (common in payments platforms)

### 4.2 User Story Format
"As a [persona], I want [capability], so that [business value]"
- Include acceptance criteria using Given/When/Then
- For payments: always consider edge cases (timeout, retry, reconciliation failures)
- Story splitting techniques: workflow steps, business rules, data variations, interfaces

### 4.3 Definition of Done (Payments-Enhanced)
- Code reviewed and merged
- Unit + integration tests passing
- PCI/security scan passed
- Settlement reconciliation test completed
- Monitoring and alerts configured
- Runbook updated
- DORA metrics captured

### 4.4 Kanban for Operations
For operations-heavy teams:
- WIP limits by column (suggest starting limits based on team size)
- Lead time and cycle time tracking
- Cumulative flow diagram interpretation
- Classes of service: Expedite (production incidents), Fixed Date (regulatory), Standard, Intangible (tech debt)

## Section 5 — Lean Portfolio Management & OKRs

### 5.1 Portfolio Governance for Technology
- **Strategy & Investment Funding**: Allocate budgets to value streams, not projects
- **Agile Portfolio Operations**: Lean business cases, guardrails, decentralized decision-making
- **Lean Governance**: Lightweight reviews, outcome-based metrics, flow-based funding
- **Run/Grow/Transform**: Allocate capacity across maintaining operations, enhancing capabilities, and transformative initiatives

### 5.2 OKRs (Objectives and Key Results)
- **Objective**: Qualitative, inspirational goal ("Achieve elite-level delivery performance")
- **Key Results**: Quantitative, measurable outcomes ("Reduce lead time to <1 day", "Achieve <5% change failure rate")
- Cadence: Quarterly OKRs aligned with PI planning
- Cascade: Portfolio → ART → Team OKRs

## Section 6 — Agile Benchmarks & Industry Data

- DORA metrics baselines (Elite/High/Medium/Low — see Section 2.2)
- SAFe PI predictability target: >80%
- Typical tech debt allocation: 15–25% of capacity
- Innovation rate targets: 15–20% of capacity
- Team cognitive load target: each team owns 2–3 services maximum
- Financial services DORA: most large banks operate at Medium level (Accelerate State of DevOps 2024)
- Industry average cycle time by story size (reference DORA report)

## Output Patterns

### Delivery Performance Narrative
```
PERIOD: [Quarter/Sprint/PI]
AUDIENCE: CIO / Engineering Leadership

VELOCITY & PREDICTABILITY:
- Sprint velocity trend: [trend with numbers]
- PI predictability: [% against >80% target]
- Throughput: [features delivered vs. planned]

DORA METRICS:
- Deployment Frequency: [value] → [Elite/High/Medium/Low]
- Lead Time: [value] → [level]
- Change Failure Rate: [value] → [level]
- MTTR: [value] → [level]
- Trend: [improving/stable/declining]

KEY ACCOMPLISHMENTS:
1. [Business value delivered]
2. [Technical capability built]

CAPACITY ALLOCATION:
- New features: [%] | Maintenance: [%] | Tech debt: [%]
- Target: 60/25/15 (Run/Grow/Transform)

IMPEDIMENTS & RISKS:
1. [Impediment] — [Impact] — [Mitigation]

NEXT QUARTER FOCUS:
1. [Priority] — [Expected outcome]
```

### Agile Maturity Assessment
```
TEAM/ART: [Name]
ASSESSMENT DATE: [Date]

SAFe COMPETENCY SCORES (1-5):
1. Team & Technical Agility: [score]
2. Agile Product Delivery: [score]
3. Enterprise Solution Delivery: [score]
4. Lean Portfolio Management: [score]
5. Organizational Agility: [score]
6. Continuous Learning Culture: [score]
7. Lean-Agile Leadership: [score]

TEAM TOPOLOGY:
- Current: [type and interaction modes]
- Recommended: [type and rationale]

STRENGTHS: [Top 3]
GAPS: [Top 3 with improvement actions]

RECOMMENDATIONS:
1. [Action] — [Timeline] — [Expected DORA improvement]
```

## Quality Checks

- [ ] Does the output reference specific SAFe 6.0 competencies where relevant?
- [ ] Are DORA metrics cited with correct performance level thresholds?
- [ ] Are team topology recommendations grounded in cognitive load and Conway's Law?
- [ ] Is the delivery narrative structured for CIO-level consumption (Pyramid Principle)?
- [ ] Are benchmarks attributed to sources (DORA report, SAFe, industry data)?
- [ ] Are recommendations practical and actionable for payments technology context?
- [ ] Does the output include both engineering metrics (DORA) and value metrics (flow)?
- [ ] Are OKRs structured with measurable key results?

---

**Confidence Calibration**: High confidence for SAFe 6.0 constructs, DORA metric thresholds, and team topologies — these are well-documented frameworks. Medium confidence for industry-specific benchmarks — these vary by organization size and context. Low confidence for AI-agile integration predictions — rapidly evolving area, recommend web search for latest DORA findings.

**Triggers**: Activate when user needs agile frameworks, delivery metrics, DORA assessment, SAFe guidance, team topology design, or delivery performance narratives for CIO conversations.
