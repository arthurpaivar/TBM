---
name: context-window-specialist
description: >
  This skill should be used when the user asks about "context window", "system prompt",
  "agent prompt", "AI context", "prompt design", "agent instructions",
  "context optimization", "token management", "prompt engineering for agents",
  "agent persona", "agent behavior design", "system message",
  "how to create a context window", "agent configuration", "agent context",
  "design a context window", "agent layers", "context architecture",
  or needs guidance on designing context windows and system prompts for AI agents.
  Use whenever the user wants to create or optimize an AI agent's context window.
version: 2.0.0
---

# Skill — Context Window Specialist

**Expert in designing context windows and system prompts for AI agents.** This skill provides the complete methodology for crafting context windows that shape agent behavior through a structured 6-layer architecture. It covers identity design, knowledge structuring, execution capabilities, communication protocols, and quality guardrails — all within a 40,000 character budget.

**Core Principles**: SPAR Framework, Pyramid Principle, SCQA Pattern, MECE Decomposition, Confidence Calibration, Source Attribution, Practical & Adaptable — these govern all outputs from this skill.

**Trigger keywords**: context window, system prompt, agent prompt, AI context, prompt design, agent instructions, context optimization, token management, agent persona, agent behavior design, system message, how to create a context window, agent configuration, agent context, design a context window, agent layers, context architecture.

## Section 1 — The 6-Layer Context Window Architecture

Every context window follows a layered architecture. Each layer covers a distinct, non-overlapping aspect of agent behavior. Together they form a complete, MECE specification of what the agent is, knows, does, says, and controls.

### Layer Overview

| Layer | Name | Purpose | Key Question |
|-------|------|---------|-------------|
| **L0** | Metadata | Agent identity card — name, version, domain, constraints | What IS this agent? |
| **L1** | Identity | Persona, role, core principles, expertise boundaries | WHO is this agent? |
| **L2** | Memory | Domain knowledge, frameworks, reference material, key facts | WHAT does this agent know? |
| **L3** | Execution | Tools, capabilities, workflows, processes, decision logic | HOW does this agent act? |
| **L4** | Communication Protocol | Output formats, tone, structure, interaction patterns | HOW does this agent communicate? |
| **L5** | Quality Protocol | Guardrails, constraints, validation, error handling, escalation | HOW does this agent ensure quality? |

### Why This Order Matters

The layers build on each other:
- **L0 (Metadata)** anchors the agent's identity card — the model reads this first to understand scope
- **L1 (Identity)** sets the persona and principles — every subsequent layer is filtered through this identity
- **L2 (Memory)** loads the knowledge — the agent needs to know things before it can act on them
- **L3 (Execution)** defines the capabilities — now the agent knows who it is, what it knows, and what it can do
- **L4 (Communication Protocol)** shapes how it delivers — the agent has all the substance, now it needs the form
- **L5 (Quality Protocol)** governs everything — the final layer ensures all other layers produce quality output

### Hard Constraint: 40,000 Characters Maximum

The total context window must not exceed **40,000 characters**. This forces disciplined writing — every sentence must earn its place. Token budget allocation guidance is in Section 3.

## Section 2 — Layer-by-Layer Design Guide

### Layer 0 — Metadata

**Purpose**: The agent's identity card. Quick-reference information that establishes scope and constraints at a glance.

**Must contain:**
- Agent name and version
- Domain / specialty
- Target users
- Token budget allocation (how the 40K characters are distributed)
- Creation date and author
- Key constraints summary (the 2-3 most critical rules)

**Format**: Use XML tags for clean parsing:
```xml
<metadata>
  <agent_name>[Name]</agent_name>
  <version>[X.Y.Z]</version>
  <domain>[What this agent specializes in]</domain>
  <target_users>[Who uses this agent]</target_users>
  <max_characters>40000</max_characters>
  <created>[Date]</created>
  <author>[Author]</author>
  <critical_constraints>
    - [Constraint 1 — the most critical rule]
    - [Constraint 2]
  </critical_constraints>
</metadata>
```

**Best practice**: Keep L0 short — it's a header, not a narrative. The detail lives in subsequent layers.

### Layer 1 — Identity

**Purpose**: Define WHO the agent is — its persona, role, expertise, and the principles that govern its behavior.

**Must contain:**
- **Role definition**: One clear sentence stating who the agent is and what it does
- **Expertise areas**: What domains the agent is a specialist in (be specific)
- **Core principles**: The behavioral principles that govern all outputs (e.g., SPAR, Pyramid Principle, MECE)
- **Persona traits**: Tone characteristics, professional posture, how the agent "feels" to interact with
- **Scope boundaries**: What's IN scope (the agent helps with) and OUT of scope (the agent redirects or declines)

**Design guidance:**
- The role definition should pass the "job title test" — if you described this agent as a person, would the title feel natural?
- Core principles should be actionable, not aspirational. "Lead with the answer" is actionable. "Be excellent" is not.
- Scope boundaries prevent the agent from drifting into domains where it lacks expertise

**Format**:
```xml
<identity>
  <role>[One sentence: You are [Name], an expert in [domain]. Your role is to [primary function] for [target users].]</role>

  <expertise>
    - [Domain area 1]: [specific capabilities]
    - [Domain area 2]: [specific capabilities]
  </expertise>

  <core_principles>
    - [Principle 1]: [What it means in practice]
    - [Principle 2]: [What it means in practice]
  </core_principles>

  <persona>
    [Tone, style, communication characteristics]
  </persona>

  <scope>
    <in_scope>[What this agent handles]</in_scope>
    <out_of_scope>[What this agent redirects or declines]</out_of_scope>
  </scope>
</identity>
```

### Layer 2 — Memory

**Purpose**: Define WHAT the agent knows — the domain knowledge, frameworks, reference material, and key facts it draws from.

**Must contain:**
- **Domain knowledge**: The core expertise areas, organized by topic
- **Frameworks and methodologies**: Named frameworks the agent applies (with enough detail to use them, not just names)
- **Key facts and reference data**: Numbers, standards, benchmarks the agent should know
- **Plugins**: Which plugins this agent has access to and what domain each covers
- **Skills**: Which specialist skills are available, their trigger keywords, and what knowledge they provide
- **Commands**: Which slash commands exist, what each does, and when to use them
- **Knowledge boundaries**: Where the agent's knowledge is strong vs. where it should search or escalate

**Design guidance:**
- This is typically the largest layer (~30% of budget) because knowledge IS the agent's value
- Organize knowledge in MECE sections — each section covers a distinct topic
- Include enough detail that the agent can apply frameworks, not just name them
- For knowledge that changes frequently, instruct the agent to search rather than rely on embedded facts
- Use pyramid principle within each knowledge section — most important information first

**Format**:
```xml
<memory>
  <domain_knowledge>
    <topic name="[Topic 1]">
      [Structured knowledge content — frameworks, key concepts, decision criteria]
    </topic>
    <topic name="[Topic 2]">
      [Structured knowledge content]
    </topic>
  </domain_knowledge>

  <frameworks>
    <framework name="[Framework Name]">
      [How to apply it — steps, criteria, when to use]
    </framework>
  </frameworks>

  <plugins>
    <plugin name="[Plugin Name]">[Domain it covers, key capabilities]</plugin>
  </plugins>

  <skills>
    <skill name="[Skill Name]">[What knowledge it provides, trigger keywords]</skill>
  </skills>

  <commands>
    <command name="/[command-name]">[What it does, when to use it]</command>
  </commands>

  <reference_data>
    [Key numbers, standards, benchmarks]
  </reference_data>

  <knowledge_boundaries>
    <strong>[Topics with high confidence]</strong>
    <moderate>[Topics where search may be needed]</moderate>
    <redirect>[Topics outside this agent's domain]</redirect>
  </knowledge_boundaries>
</memory>
```

### Layer 3 — Execution

**Purpose**: Define HOW the agent acts — its tools, capabilities, workflows, and decision logic.

**Must contain:**
- **Available tools**: What tools the agent can use, with guidance on when and how
- **Sources**: Where the agent retrieves information — APIs, databases, web search, MCP servers, knowledge bases
- **Commands**: How the agent invokes slash commands as part of its workflows, including when to delegate to specific commands
- **Workflows**: Common task patterns the agent follows (step-by-step for key scenarios)
- **Decision logic**: How the agent chooses between approaches, when to act vs. ask
- **Integration points**: How the agent connects to external systems, data sources, or other agents

**Design guidance:**
- For each tool, specify WHEN to use it (not just WHAT it does) — this prevents tool misuse
- Workflows should cover the 3-5 most common tasks the agent handles
- Decision logic should address the key judgment calls — when to act autonomously vs. when to ask the user
- Keep workflows at the strategic level (what to think about) not tactical (exact keystrokes)

**Format**:
```xml
<execution>
  <tools>
    <tool name="[Tool Name]">
      <purpose>[What it does]</purpose>
      <when_to_use>[Conditions that trigger this tool]</when_to_use>
      <how_to_use>[Key usage guidance]</how_to_use>
    </tool>
  </tools>

  <sources>
    <source name="[Source Name]">
      <type>[API / Database / Web Search / MCP Server / Knowledge Base]</type>
      <when_to_use>[When to query this source]</when_to_use>
    </source>
  </sources>

  <commands>
    <command name="/[command-name]">
      <purpose>[What it does]</purpose>
      <when_to_invoke>[When to delegate to this command]</when_to_invoke>
    </command>
  </commands>

  <workflows>
    <workflow name="[Common Task Name]">
      [Step-by-step process for this task type]
    </workflow>
  </workflows>

  <decision_logic>
    <rule>[Condition] → [Action]</rule>
    <rule>When uncertain about [topic] → [Behavior: ask user / search / escalate]</rule>
  </decision_logic>
</execution>
```

### Layer 4 — Communication Protocol

**Purpose**: Define HOW the agent communicates — output formats, tone calibration, structure patterns, and interaction style.

**Must contain:**
- **Output formats**: Standard formats for different response types (analysis, recommendation, summary, etc.)
- **Tone calibration**: How formal/casual, how detailed/concise, based on context
- **Structure patterns**: How to organize responses (pyramid principle, headers, bullet rules)
- **Interaction patterns**: When to ask clarifying questions, how to handle multi-turn conversations

**Design guidance:**
- Define 2-4 output format templates for the most common response types
- Tone should adapt to context — specify the rules for calibration (e.g., "match the user's formality level")
- Be explicit about what the agent should NOT do in communication (e.g., "never use bullet points for reports" or "never use emojis unless the user does")
- Include guidance on response length — when to be brief vs. comprehensive

**Format**:
```xml
<communication_protocol>
  <output_formats>
    <format name="[Format Name — e.g., Analysis]">
      [Template structure — sections, required elements, length guidance]
    </format>
    <format name="[Format Name — e.g., Recommendation]">
      [Template structure]
    </format>
  </output_formats>

  <tone>
    <default>[Default tone and formality level]</default>
    <calibration>[Rules for adapting tone based on context]</calibration>
  </tone>

  <structure_rules>
    - [Rule 1: e.g., Lead with the answer]
    - [Rule 2: e.g., Use headers for responses over X lines]
  </structure_rules>

  <interaction_patterns>
    <clarification>[When and how to ask clarifying questions]</clarification>
    <multi_turn>[How to handle follow-up conversations]</multi_turn>
  </interaction_patterns>
</communication_protocol>
```

### Layer 5 — Quality Protocol

**Purpose**: Define HOW the agent ensures quality — guardrails, constraints, validation rules, error handling, and escalation paths.

**Must contain:**
- **Hard constraints**: Things the agent must NEVER do (non-negotiable rules)
- **Soft constraints**: Things the agent should avoid unless explicitly asked
- **Validation rules**: Checks the agent runs before delivering output
- **Error handling**: What to do when things go wrong (missing data, ambiguous request, tool failure)
- **Escalation paths**: When and how to escalate to the user or another system
- **Confidence calibration**: How to communicate certainty levels

**Design guidance:**
- Hard constraints are the most critical — they prevent harmful or incorrect behavior
- Validation rules should be binary (pass/fail) and actionable
- Error handling should cover the 3-5 most likely failure modes
- Escalation paths should be clear about WHAT triggers escalation and WHO to escalate to
- Confidence calibration should specify how the agent communicates uncertainty (e.g., "state confidence as high/medium/low")

**Format**:
```xml
<quality_protocol>
  <hard_constraints>
    - NEVER [prohibited action 1]
    - NEVER [prohibited action 2]
  </hard_constraints>

  <soft_constraints>
    - Avoid [behavior] unless explicitly requested
    - Prefer [approach A] over [approach B]
  </soft_constraints>

  <validation_rules>
    Before delivering any output:
    - [ ] [Check 1]
    - [ ] [Check 2]
    - [ ] [Check 3]
  </validation_rules>

  <error_handling>
    <scenario name="[Failure Mode]">
      <response>[What to do]</response>
    </scenario>
  </error_handling>

  <escalation>
    <trigger>[Condition that triggers escalation]</trigger>
    <action>[How to escalate — ask user, flag uncertainty, redirect]</action>
  </escalation>

  <confidence_calibration>
    [How to communicate certainty: high/medium/low with definitions]
  </confidence_calibration>
</quality_protocol>
```

## Section 3 — Token Budget Management

### The 40,000 Character Constraint

Every context window must fit within **40,000 characters**. This is a hard constraint — exceeding it causes truncation or failure.

### Recommended Allocation

| Layer | % of Budget | ~Characters | Priority |
|-------|-------------|-------------|----------|
| L0 — Metadata | ~5% | ~2,000 | Fixed — keep minimal |
| L1 — Identity | ~15% | ~6,000 | High — sets everything |
| L2 — Memory | ~30% | ~12,000 | Highest — the agent's value |
| L3 — Execution | ~25% | ~10,000 | High — defines capabilities |
| L4 — Communication | ~10% | ~4,000 | Medium — templates are concise |
| L5 — Quality | ~15% | ~6,000 | High — prevents failures |

### Budget Optimization Techniques

- **Prioritize by frequency**: Content used in every interaction gets more budget. Rare-case handling gets less.
- **Concise but complete**: Remove redundant phrasing but never remove meaning. "Always verify before responding" not "It is important that you always make sure to verify your work before you respond to the user."
- **Dynamic loading over static embedding**: For large knowledge bases, instruct the agent to search rather than embedding everything in L2.
- **Templates over prose**: Output format templates in L4 are more token-efficient than narrative descriptions of how to respond.
- **Test and trim**: After writing, test with representative queries. If a section isn't influencing behavior, it's wasting tokens.

### What to Cut When Over Budget

Priority order (cut last → cut first):
1. **Never cut**: L0 metadata, L1 role definition, L5 hard constraints
2. **Trim carefully**: L2 domain knowledge (reduce depth, not breadth), L3 workflows (keep top 3, cut edge cases)
3. **Cut first**: L4 detailed format examples (keep 2, cut extras), L2 reference data (instruct to search instead), L3 rare-case workflows

## Section 4 — Writing Best Practices

### XML Structure

Use XML tags for all layers. This provides:
- Clear section boundaries the model can parse efficiently
- Consistent structure across different context windows
- Easy maintenance — sections can be updated independently

**Nesting**: Use one level of nesting within layers (e.g., `<tools><tool name="...">`) but avoid deep nesting (3+ levels) — it wastes characters and confuses parsing.

### Clarity Principles

- **Be explicit over implicit**: "Respond in 3-5 sentences" not "Be concise"
- **Use examples for ambiguous cases**: Show what good output looks like
- **Define what "good" means**: For each output type, specify what success looks like
- **Positive over negative framing**: "Do X" is clearer than "Don't not do X" — but hard constraints should use NEVER for emphasis

### Defensive Design

- **Anticipate edge cases**: What happens when the user asks something outside scope? When data is missing? When tools fail?
- **Define escalation early**: Don't wait for Layer 5 to mention escalation if it's critical — reference it in L3 decision logic too
- **Test with adversarial queries**: Questions designed to confuse the agent reveal gaps in the context window

### Consistency Across Layers

- Principles in L1 should be reflected in validation rules in L5
- Tools in L3 should have corresponding error handling in L5
- Output formats in L4 should align with knowledge structure in L2
- If L1 says "lead with the answer", L4 output templates must follow pyramid principle

## Section 5 — Validation Standards

### Architectural Checks
- [ ] Are all 6 layers present (L0-L5)?
- [ ] Is each layer MECE with the others (no overlap, no gaps)?
- [ ] Does the total character count stay within 40,000?
- [ ] Is the token budget allocation appropriate for this agent's domain?

### Layer Quality Checks
- [ ] L0: Does metadata include agent name, version, domain, target users, and token allocation?
- [ ] L1: Is the role definition clear in one sentence? Are scope boundaries explicit?
- [ ] L2: Is domain knowledge organized in MECE sections? Is it actionable (not just names)?
- [ ] L3: Does every tool have when-to-use guidance? Are workflows strategic, not tactical?
- [ ] L4: Are 2-4 output format templates defined? Is tone calibration specified?
- [ ] L5: Are hard constraints using NEVER? Are validation rules binary? Is escalation defined?

### Consistency Checks
- [ ] Do L1 principles align with L5 validation rules?
- [ ] Do L3 tools have corresponding L5 error handling?
- [ ] Do L4 output formats align with L2 knowledge structure?
- [ ] Are there no contradictions between layers?

### Effectiveness Checks
- [ ] Would this context window produce expert-level output on first use?
- [ ] Could the agent handle the 5 most common user requests correctly?
- [ ] Does the agent know when to escalate vs. when to act?
- [ ] Is the communication style appropriate for the target users?

## Section 6 — Output Patterns

### Context Window Design Brief (use during planning)
```
CONTEXT WINDOW DESIGN: [Agent Name]

DOMAIN: [What this agent specializes in]
TARGET USERS: [Who uses this agent]
PRIMARY FUNCTION: [What the agent does in one sentence]

LAYER BUDGET:
L0 Metadata:      ~[X]% (~[N] chars)
L1 Identity:      ~[X]% (~[N] chars)
L2 Memory:        ~[X]% (~[N] chars)
L3 Execution:     ~[X]% (~[N] chars)
L4 Communication: ~[X]% (~[N] chars)
L5 Quality:       ~[X]% (~[N] chars)
TOTAL:            ≤40,000 chars

KEY DESIGN DECISIONS:
- Knowledge approach: [Embedded vs. dynamic search vs. hybrid]
- Autonomy level: [When agent acts vs. asks]
- Output style: [Formal/casual, brief/detailed]
```

### Context Window Delivery Confirmation
```
CONTEXT WINDOW CREATED: [Agent Name] v[Version]

CHARACTER COUNT: [actual] / 40,000
LAYER BREAKDOWN:
- L0 Metadata:      [count] chars ([%])
- L1 Identity:      [count] chars ([%])
- L2 Memory:        [count] chars ([%])
- L3 Execution:     [count] chars ([%])
- L4 Communication: [count] chars ([%])
- L5 Quality:       [count] chars ([%])

VALIDATION: All checks passed
DELIVERY: [File location]
```

---

**Confidence Calibration**: High confidence for context windows in well-defined domains with clear user needs. Medium confidence for multi-domain agents or agents requiring complex tool orchestration — recommend starting with a focused scope and expanding.

**Triggers**: Activate when user requests context window creation, system prompt design, agent configuration, or prompt engineering for AI agents.
