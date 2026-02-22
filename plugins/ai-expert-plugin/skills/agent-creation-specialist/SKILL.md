---
name: agent-creation-specialist
description: >
  This skill should be used when the user asks about "create an agent", "build an agent",
  "new agent", "agent design", "agent architecture", "how to build an agent",
  "AI agent development", "agent framework", "agent tools", "agent memory",
  "agent planning", "multi-agent", "agent orchestration", "agent deployment",
  "agentic workflow", "autonomous agent",
  or needs guidance on designing and building AI agents.
  Use whenever the user wants to create or design a new AI agent.
version: 1.0.0
---

# Skill — Agent Creation Specialist

**Expert guide for designing and building AI agents.** This skill provides comprehensive methodology for architecting, building, and deploying AI agents with tools, memory, planning capabilities, and multi-agent orchestration. Use when the user wants to create a new AI agent.

**Trigger keywords**: create an agent, build an agent, new agent, agent design, agent architecture, how to build an agent, AI agent development, agent framework, agent tools, agent memory, agent planning, multi-agent, agent orchestration.

## Core Principles

These principles govern all outputs from this skill:

- **SPAR Framework**: Follow Sense → Plan → Act → React for every task.
- **Pyramid Principle (Barbara Minto)**: Lead with the answer. Structure top-down.
- **SCQA Pattern**: For executive briefs, use Situation → Complication → Question → Answer.
- **MECE Decomposition**: Break down in a Mutually Exclusive, Collectively Exhaustive way.
- **Confidence Calibration**: Explicitly state confidence level.
- **Source Attribution**: Always cite sources.
- **Practical & Adaptable**: All outputs should be immediately usable.

## Agent Architecture Patterns

### Pattern 1: ReAct (Reason + Act)
Agent reasons about a task, takes an action, observes the result, and iterates.
- **Best for**: Tool-using agents, information retrieval, task execution
- **Flow**: Think → Act → Observe → Think → Act → ... → Answer
- **Pros**: Flexible, handles unexpected situations
- **Cons**: Can loop, harder to predict behavior

### Pattern 2: Plan-and-Execute
Agent creates a full plan upfront, then executes step by step.
- **Best for**: Complex multi-step workflows, project management
- **Flow**: Plan → Execute Step 1 → Execute Step 2 → ... → Verify
- **Pros**: Predictable, auditable, easier to debug
- **Cons**: Less flexible to surprises, planning overhead

### Pattern 3: Reflection
Agent critiques its own output and self-corrects.
- **Best for**: Writing, code generation, analysis quality
- **Flow**: Generate → Critique → Revise → Verify
- **Pros**: Higher quality output, catches errors
- **Cons**: Slower, more token usage

### Pattern 4: Multi-Agent Orchestration
Multiple specialized agents collaborate under an orchestrator.
- **Best for**: Complex systems, domain specialization, parallel tasks
- **Flow**: Orchestrator → Delegate to Agent A, B, C → Synthesize
- **Pros**: Specialization, parallel execution, separation of concerns
- **Cons**: Complexity, coordination overhead, error propagation

## Agent Design Methodology

### Phase 1: Define the Agent (Sense)
1. **Goal**: What is the agent trying to accomplish?
2. **Users**: Who will interact with the agent?
3. **Autonomy Level**: How much can it do without human approval?
4. **Domain**: What area of expertise does it need?
5. **Integration**: What systems does it need to connect to?

### Phase 2: Design the Architecture (Plan)
1. **Pattern Selection**: ReAct, Plan-and-Execute, Reflection, or Multi-Agent?
2. **Tool Design**: What tools does the agent need?
3. **Memory Design**: Short-term (context) vs. long-term (vector store)?
4. **Guardrails**: What constraints and safety measures?
5. **Context Window**: System prompt design (use context-window-specialist)

### Phase 3: Build (Act)
1. Set up the AI model and API integration
2. Implement tool definitions and handlers
3. Build memory systems (if needed)
4. Write the context window / system prompt
5. Implement the agent loop (ReAct, planning, etc.)
6. Add logging, monitoring, and error handling
7. Build the user interface (chat, API, or automation)

### Phase 4: Test and Deploy (React)
1. Unit test individual tools
2. Integration test agent workflows
3. Adversarial test for edge cases and failures
4. Performance test for latency and token usage
5. Deploy with monitoring and alerting
6. Iterate based on user feedback

## Agent Components

### Tools
- **Definition**: Functions the agent can call to interact with external systems
- **Design**: Clear name, description, input schema, output format
- **Best Practices**: Idempotent where possible, error handling, timeout management
- **Examples**: Database queries, API calls, file operations, web search

### Memory
- **Short-term**: Conversation context window (limited by token count)
- **Long-term**: Vector databases, knowledge graphs, file storage
- **Working Memory**: Scratchpad for intermediate reasoning
- **Episodic Memory**: Past conversation summaries for continuity

### Planning
- **Task Decomposition**: Breaking goals into subtasks
- **Prioritization**: Ordering tasks by dependency and importance
- **Progress Tracking**: Monitoring completion and adjusting plans
- **Replanning**: Adapting when obstacles are encountered

### Guardrails
- **Input Validation**: Check user inputs before processing
- **Output Filtering**: Verify agent outputs before delivery
- **Action Limits**: Cap the number of actions per turn
- **Human-in-the-Loop**: Require approval for high-stakes actions
- **Audit Trail**: Log all agent decisions and actions

## Agent Evaluation Framework

### Metrics
- **Task Completion Rate**: % of tasks successfully completed
- **Accuracy**: Correctness of agent outputs
- **Latency**: Time from request to response
- **Token Efficiency**: Tokens used per task
- **Error Rate**: Frequency and types of failures
- **User Satisfaction**: Qualitative feedback

### Testing Strategy
1. **Golden Set Testing**: Pre-defined inputs with expected outputs
2. **Adversarial Testing**: Edge cases, malicious inputs, confusion scenarios
3. **A/B Testing**: Compare agent versions on real traffic
4. **Regression Testing**: Ensure updates don't break existing behavior

## Output Patterns

### Agent Design Document
```
AGENT: [Name]
PURPOSE: [1-2 sentence description]
PATTERN: [ReAct / Plan-Execute / Reflection / Multi-Agent]

TOOLS:
- [Tool 1]: [Description, when used]
- [Tool 2]: [Description, when used]

MEMORY:
- Short-term: [Context window approach]
- Long-term: [Vector DB / Knowledge graph / None]

GUARDRAILS:
- [Guardrail 1]
- [Guardrail 2]

CONTEXT WINDOW: [Summary of system prompt design]

DEPLOYMENT: [Infrastructure and monitoring plan]
```

### Agent Blueprint
Visual architecture of agent components, data flow, and tool interactions.

## Quality Checks

- [ ] Is the agent's goal clearly defined?
- [ ] Is the architecture pattern appropriate for the use case?
- [ ] Are all necessary tools defined with clear schemas?
- [ ] Is the memory strategy appropriate (short vs. long-term)?
- [ ] Are guardrails comprehensive and tested?
- [ ] Is the context window optimized?
- [ ] Has the agent been tested with edge cases?
- [ ] Is there monitoring and logging in place?
- [ ] Is the deployment strategy defined?
