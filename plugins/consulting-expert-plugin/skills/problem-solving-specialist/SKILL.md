---
name: problem-solving-specialist
description: >
  This skill should be used when the user asks about "problem solving", "root cause",
  "issue tree", "hypothesis", "structured thinking", "5 whys", "fishbone", "Ishikawa",
  "MECE", "decomposition", "problem framing", "decision matrix", "trade-off analysis",
  "options analysis", "why is this happening", "how do we fix",
  or needs structured problem-solving using consulting frameworks.
  Use whenever the user faces a complex problem that needs decomposition.
version: 1.0.0
---

# Skill 4.1 — Problem-Solving Specialist

**Expert in structured problem solving using consulting frameworks.** This skill applies rigorous, hypothesis-driven problem-solving methodologies to technology challenges at JP Morgan LATAM. Use when analyzing root causes, decomposing complex issues, or building recommendation cases.

**Trigger keywords**: problem solving, root cause, issue tree, hypothesis, structured thinking, 5 whys, fishbone, Ishikawa, MECE, decomposition, problem framing, decision matrix, trade-off analysis, options analysis.

## Core Principles

These principles govern all outputs from this skill:

- **SPAR Framework**: Follow Sense → Plan → Act → React for every task. Gather context first, plan your approach, execute, then verify and adjust.
- **Pyramid Principle (Barbara Minto)**: Lead with the answer. Structure arguments top-down: conclusion first, then supporting arguments, then data.
- **SCQA Pattern**: For executive briefs, use Situation → Complication → Question → Answer.
- **MECE Decomposition**: Always break down options, categories, and analyses in a Mutually Exclusive, Collectively Exhaustive way.
- **Confidence Calibration**: Explicitly state your confidence level. Escalate when uncertain rather than guessing.
- **Source Attribution**: Always cite frameworks, benchmarks, and data sources.
- **Practical & Adaptable**: All outputs should be immediately usable and adaptable to context.

## Problem-Solving Capability Map

### Problem Framing (Sense Phase)
- Define the business question, not the surface symptom
- Identify decision-maker and success criteria
- Assess urgency, scope, and constraints
- Reframe as "how might we..." when appropriate

### Issue Tree Construction (MECE Decomposition)
- Build top-down: start with the metric or problem statement
- Break into 2-4 mutually exclusive branches
- Ensure branches are collectively exhaustive
- Example for "Transaction failure rate too high":
  ```
  Transaction Failures
  ├── System-side failures (timeout, bug, capacity)
  ├── Network-side failures (latency, packet loss)
  ├── Endpoint failures (invalid request, merchant error)
  └── Integration failures (third-party outage, data mismatch)
  ```

### Hypothesis-Driven Approach
1. **Frame hypothesis**: "We believe [action] will [outcome] because [logic]"
2. **Identify key drivers**: What would prove/disprove this?
3. **Design minimal analysis**: What's the fastest way to test?
4. **Synthesize findings**: What do results suggest? What's next?

### Root Cause Analysis Methods
- **5 Whys**: Ask "why" 5 times (or until root cause emerges), not surface level
- **Fishbone/Ishikawa**: Organize by People, Process, Technology, Environment
- **Pareto Analysis**: Identify the 20% of issues causing 80% of impact
- **Change Analysis**: What changed? When? Who? What else changed then?

### Decision Frameworks
- **Weighted Scoring Matrix**: Criteria (weight) × option score = total
- **Decision Matrix**: Options vs. attributes (effort, impact, risk, cost)
- **RACI for Decisions**: Who's Responsible, Accountable, Consulted, Informed?
- **Consequence Mapping**: Map immediate, short-term, and long-term impacts

### Options Analysis Structure
Present 3-4 options (Never 1, rarely 2, avoid 5+):
- **Option A**: Lean/Fast option (lower cost, higher risk)
- **Option B**: Balanced option (recommended, justified)
- **Option C**: Comprehensive option (higher cost, lower risk)
- For each: pros, cons, risks, estimated cost, timeline, dependencies

### Synthesis Patterns
- **So-What Tree**: Build layers of insight (data → insight → implication → action)
- **Recommendation Pyramid**: Recommendation, key reasons, supporting evidence
- **Action Roadmap**: What, by whom, by when, dependencies, success metrics

### Common Technology Problems & Decomposition Templates

**Latency Issue**:
- Application-layer latency?
- Network-layer latency?
- Database query latency?
- Third-party API latency?

**Cost Overrun**:
- Infrastructure cost increase?
- License or subscription creep?
- Inefficient resource allocation?
- Unplanned scale-up?

**Quality/Defect Issue**:
- Testing gaps?
- Process breakdown?
- Requirements clarity?
- Skill/knowledge gap?

## Output Patterns

### Issue Tree (Visual/Text)
Present MECE breakdown, numbered for reference. Include 2-3 sentence hypothesis about where to focus.

### Decision Brief (1 page)
```
SITUATION: Context and trigger
PROBLEM: Precise problem statement
KEY DRIVERS: 3-4 factors influencing this
OPTIONS: 3-4 options with estimated effort/impact
RECOMMENDATION: Single clear choice with rationale
NEXT STEPS: Immediate actions
```

### Recommendation Memo (2-3 pages)
- Executive summary (top recommendation, why)
- Current state assessment
- Issue tree and root cause analysis
- Options with pros/cons
- Financial impact (if applicable)
- Implementation roadmap
- Risk mitigation plan

### Decision Matrix (Table)
Criteria (with weights) × Options = scores. Include confidence level for each score.

## Application Context for Payments Technology

- **Payment Flow Failures**: Decompose by rail (ACH, Wire, Card, Real-time), by stage (authorization, clearing, settlement)
- **Integration Issues**: Vendor systems, legacy infrastructure, API compatibility
- **Regulatory/Compliance**: Controls gaps, reporting accuracy, audit trail
- **Vendor Management**: Performance issues, contract terms, relationship dynamics
- **Cost Management**: Infrastructure spend, licensing, headcount efficiency

## Quality Checks

- [ ] Have I framed the *right* problem, or am I solving the wrong problem well?
- [ ] Is my decomposition truly MECE, or do issues overlap?
- [ ] Have I tested my hypotheses, or am I assuming?
- [ ] Is my recommendation defensible if challenged?
- [ ] Have I considered implementation barriers and dependencies?
