---
description: Structured problem decomposition and recommendation using consulting frameworks
allowed-tools: Read, Write, Edit, Grep, Glob, Bash, WebSearch, WebFetch, Task
argument-hint: [problem or question — e.g., "Why are our deployment lead times increasing?"]
---

Solve $ARGUMENTS using the problem-solving-specialist skill from consulting-expert-plugin. This command orchestrates a full McKinsey/BCG-grade problem-solving workflow, invoking domain specialists as subagents for technical depth.

## CRITICAL: Subagent Orchestration

This command uses the Task tool to spawn specialist subagents at specific stages. Each subagent receives a focused brief and returns domain-specific analysis that feeds the synthesis. Do not skip the subagent steps — they are what elevate this from surface-level analysis to consulting-grade depth.

## Layer 1 — Context & Intent

**What:** Understand the problem from whatever input the user provides — a phrase, a paragraph, an image, a document, or a conversation context.
**How:** Parse $ARGUMENTS to extract:
- The surface-level problem as stated
- The implied deeper question (what is the user really trying to solve?)
- The decision context (who decides, what's at stake, what constraints exist)
- Available data or evidence already provided

If the input is ambiguous, ask one clarifying question — but bias toward action. A well-framed hypothesis is more useful than a perfectly scoped question.
**Why:** The quality of the entire analysis depends on solving the right problem. Misframing here cascades through every subsequent layer.

## Layer 2 — Knowledge Loading

**What:** Load the problem-solving-specialist skill and internalize its methodology.
**How:** Read the problem-solving-specialist SKILL.md from consulting-expert-plugin. Extract:
- From **Section 1**: The framing protocol and SCQA pattern
- From **Section 2**: Issue tree construction methodology and MECE validation
- From **Section 3**: Hypothesis-driven analysis and cross-plugin orchestration patterns
- From **Section 6**: Communication protocol (Opening / Body / Conclusion)
- From **Section 7**: The cross-plugin orchestration table — which specialists to invoke for which domains

Also note which domain specialists might be needed based on the problem domain identified in Layer 1.
**Why:** The skill contains the accumulated consulting methodology. Loading it before analysis ensures every step follows proven frameworks rather than ad hoc reasoning.

## Layer 3 — Problem Framing

**What:** Frame the problem using SCQA and define the issue tree root.
**How:** Apply the Framing Protocol from the skill:
1. Write the SCQA: Situation (factual context), Complication (what changed/what's wrong), Question (the precise question to answer), Answer (initial hypothesis)
2. Define success criteria: What would a good answer look like?
3. Quantify cost of inaction: What happens if nothing changes?
4. Identify the issue tree type: Diagnostic (why is this happening?) or Solution (what should we do?)

Present the framing to yourself before proceeding — if the question isn't sharp, sharpen it.
**Why:** SCQA forces precision. The hypothesis in the Answer position gives the analysis direction — every subsequent step either confirms or redirects it. Without a clear frame, analysis becomes unfocused exploration.

## Layer 4 — Issue Tree & Specialist Dispatch

**What:** Build the MECE issue tree and dispatch specialist subagents to analyze priority branches.
**How:**
1. **Build the tree**: Decompose the question into 2-4 MECE branches at Level 1. Break each branch into 2-3 sub-branches at Level 2.
2. **MECE validation**: For each level — are branches mutually exclusive? Collectively exhaustive? Balanced?
3. **Prioritize branches**: Mark each as Investigate (high impact + likely), Monitor (moderate), or Park (low priority)
4. **Dispatch subagents**: For each "Investigate" branch that requires domain expertise, spawn a subagent via the Task tool:

   - **Technology branches** → Task a subagent to: "Read the [relevant specialist] SKILL.md from technology-expert-plugin and analyze: [specific branch question]. Return a structured assessment with evidence, confidence level, and implications."
     - Architecture questions → architecture-specialist
     - Strategy questions → tech-strategy-advisory
     - AI/ML questions → ai-specialist
     - Delivery/DevOps questions → tech-delivery-specialist or agile-specialist

   - **Financial branches** → Task a subagent to: "Read the [relevant specialist] SKILL.md from finance-expert-plugin and analyze: [specific branch question]. Return a structured assessment with cost data, benchmarks, and financial implications."
     - Cost questions → tech-bm-specialist
     - Portfolio questions → it-portfolio-management

   - **Research branches** → Task a subagent to: "Read the deep-search-specialist SKILL.md from consulting-expert-plugin and research: [specific question]. Return key findings with sources, credibility ratings, and implications."

   - **Benchmark branches** → Task a subagent to: "Read the industry-benchmark-specialist SKILL.md from consulting-expert-plugin and find benchmarks for: [specific metric]. Return benchmark data with sources, peer comparison, and gap analysis."

5. **Collect results**: Gather all subagent outputs. Map findings back to the issue tree branches.

**Why:** This is where the magic happens. Instead of shallow analysis across every branch, specialist subagents provide genuine depth on priority branches. The issue tree ensures MECE coverage while subagents ensure depth. This combination is what separates consulting-grade analysis from surface-level problem-solving.

## Layer 5 — Hypothesis Testing & Root Cause

**What:** Test the initial hypothesis against the evidence collected, identify root causes, and refine the analysis.
**How:**
1. **Evidence mapping**: For each priority branch, compile the evidence from subagent outputs and direct analysis
2. **Hypothesis verdict**: For each branch — Confirmed (evidence supports), Rejected (evidence contradicts), or Inconclusive (insufficient data, state confidence)
3. **Root cause identification**: Using the confirmed branches, apply root cause analysis:
   - 5 Whys for specific failure chains
   - Fishbone for multi-domain causes (People, Process, Technology, Environment)
   - Pareto for quantifying relative impact of multiple causes
4. **Synthesis check**: Does the root cause explain the full problem, or are there contributing factors? Build the So-What Tree: Data → Insight → Implication → Action

**Why:** Hypothesis testing prevents confirmation bias — every branch gets an honest verdict. Root cause analysis prevents treating symptoms instead of causes. The So-What Tree connects evidence to actionable recommendations.

## Layer 6 — Options & Recommendation

**What:** Develop options, evaluate them, and build the recommendation.
**How:**
1. **Design 3-4 options**: Based on the root cause analysis:
   - Option A: Minimum viable (fast, cheap, addresses symptoms)
   - Option B: Balanced (recommended — addresses root cause with acceptable risk)
   - Option C: Comprehensive (maximum investment, maximum long-term value)
   - Option D: Transformational (only if the problem warrants fundamental redesign)

2. **Evaluate each option** against: Impact, Feasibility, Cost, Timeline, Risk, Dependencies

3. **Build the Recommendation Pyramid**:
   - Recommendation (1 sentence)
   - Key reasons (3-4, each supported by evidence from the analysis)
   - Risk mitigation for the recommended option
   - Next steps with owners and timelines

4. **If financial quantification is needed** → spawn a business-case subagent: "Read the business-case-specialist SKILL.md from consulting-expert-plugin and build a financial comparison of these options: [Option details]. Return NPV, IRR, payback for each."

**Why:** Options give the decision-maker agency — even when one option is clearly best, presenting alternatives shows rigor and builds trust. The Recommendation Pyramid ensures the conclusion follows logically from the analysis with no gaps.

## Layer 7 — Quality Review & Evaluation

**What:** Verify the analysis is complete, defensible, and executive-ready.
**How:** Spawn an evaluation subagent via the Task tool:
- "You are a critical reviewer. Evaluate this problem-solving analysis for: (1) Is the problem framing sharp and specific? (2) Is the issue tree genuinely MECE? (3) Are hypotheses tested with evidence, not assumption? (4) Does the recommendation follow logically from the analysis? (5) Are there logical gaps or unsupported claims? (6) Would a McKinsey partner present this with confidence? Return specific feedback with suggested improvements."

Apply the feedback. Fix any gaps identified. If critical issues are found, loop back to the relevant layer.

Run the Quality Checks from the skill:
- [ ] Real problem framed, not surface symptom?
- [ ] Issue tree MECE at every level?
- [ ] Hypotheses tested with evidence?
- [ ] Recommendation follows logically?
- [ ] So-What clear for a busy executive?
- [ ] Options genuinely distinct, no straw men?
- [ ] Impact quantified where possible?
- [ ] Strategic insight in conclusion?
- [ ] Next steps specific with owners and timelines?

**Why:** Self-evaluation catches gaps before the user sees them. The external reviewer subagent provides a fresh perspective — it's easy to be blind to your own logical gaps. This QA layer is what ensures consistent quality across every use.

## Layer 8 — Executive Delivery

**What:** Deliver the problem-solving summary using the communication protocol.
**How:** Structure the output as:

**Opening (The So-What)**: 2-3 sentences — the recommendation and its impact. The decision-maker should understand the conclusion immediately. No preamble.

**Body (The Evidence)**: The structured analysis:
- Problem framing (SCQA — concise)
- Issue tree with priority branches highlighted
- Root cause with confidence level
- Options comparison table
- Each section earns its place by directly supporting the recommendation

**Conclusion (Insight & Action)**:
- Strategic insight — what this means beyond the immediate problem
- Specific recommendations with next steps, owners, timelines
- What to monitor and when to reassess

Use the Executive Problem-Solving Summary output pattern from the skill. The output should be executive-ready — someone could present this in a leadership meeting as-is.

If the user wants to deep-dive into any branch, they can ask — the analysis supports drill-down on demand.

**Why:** The communication protocol ensures the output is immediately useful. Opening with the answer respects the reader's time. Ending with strategic insight elevates the analysis from tactical to advisory.

**Output**: An executive problem-solving summary following the skill's output pattern — recommendation, problem framing, issue tree, root cause, options evaluation, strategic insight, and specific next steps. Designed for executive consumption with drill-down available on request.
