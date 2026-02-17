---
command: presentation-generator
trigger: "create presentation", "build deck", "generate preso", "make slides"
plugin: communication-expert-plugin
version: 1.0.0
description: >
  Orchestrates multiple expert skills to generate consulting-grade presentation first drafts.
  Dynamically selects relevant expertise based on topic, structures content using consulting
  frameworks, iterates with sequential thinking, and produces PowerPoint deliverable.
---

# Command: Presentation Generator

**Intelligent presentation creation** that assembles the right expert team, structures compelling narratives, and produces executive-ready first drafts.

## Trigger Phrases

Use this command when the user says:
- "Create a presentation on [topic]"
- "Build a deck about [subject]"
- "Generate a preso for [audience] on [theme]"
- "Make slides for [meeting/event]"
- "Help me present [concept/strategy]"

## Input Required from User

Before starting the workflow, gather:

1. **Topic/Theme** - What is the presentation about?
2. **Audience** - Who will see this? (CIO, Board, Technical Team, etc.)
3. **Key Information** - Any specific data, decisions, or context to include
4. **Meeting Context** - QBR? Budget approval? Strategy review? (optional)
5. **Time Constraint** - Presentation length (optional, default: 15-20 slides)

## Workflow: 6-Step Orchestration

### STEP 1: Theme Evaluation & Skill Selection
**Owner:** Communication Expert Plugin → PowerPoint Specialist

**Actions:**
1. Analyze the topic to identify domain(s):
   - Technology/Technical? → Technology Expert Plugin
   - Strategy/Problem-Solving? → Consulting Expert Plugin
   - Financial/Investment? → Finance Expert Plugin
   - Cross-functional? → Multiple plugins

2. Determine presentation type:
   - QBR → Status update structure
   - Budget Proposal → Business case structure
   - Strategy Review → SCQA narrative
   - Technical Deep-Dive → Problem → Solution → Impact

3. Identify audience calibration needs:
   - C-Suite → Strategic, concise, risk-focused
   - Board → Governance, compliance, shareholder value
   - Technical Team → Detailed, execution-focused

**Output:** Skill selection map + presentation framework

**Example:**
```
Topic: "Cloud Migration Strategy for Payments Platform"
Domains: Technology (primary), Finance (secondary), Consulting (structure)
Type: Strategy Review
Audience: CIO + CFO
Framework: SCQA Pattern

Selected Skills:
- Technology Expert: Architecture Specialist (cloud patterns)
- Technology Expert: Tech Strategy Advisory (transformation roadmap)
- Consulting Expert: Business Case Specialist (financial justification)
- Consulting Expert: Problem-Solving Specialist (MECE structure)
- Finance Expert: TBM Specialist (cost modeling)
- Communication Expert: PowerPoint Specialist (deck structure)
```

---

### STEP 2: Content Generation (Multi-Skill Synthesis)
**Owner:** Dynamically selected expert skills (from Step 1)

**Actions:**
1. **Call relevant domain experts** to generate content components:
   
   **For Technology topics:**
   - Architecture Specialist → Technical patterns, design principles
   - Tech Strategy Advisory → Strategic frameworks (McKinsey 3Ds, etc.)
   - AI Specialist → AI/automation components (if relevant)
   - Agile Specialist → Delivery approach, metrics (if relevant)
   
   **For Consulting/Analysis:**
   - Problem-Solving Specialist → Issue trees, MECE decomposition
   - Business Case Specialist → NPV, IRR, ROI calculations
   - Industry Benchmark Specialist → Peer comparisons, maturity models
   - Deep Search Specialist → Market research, vendor landscape (if needed)
   
   **For Financial/Investment:**
   - TBM Specialist → Cost transparency, Run/Grow/Transform
   - IT Portfolio Management → Application rationalization, 6Rs

2. **Synthesize insights** into presentation components:
   - Current State (Situation)
   - Challenge/Gap (Complication)
   - Strategic Question (Question)
   - Recommendation (Answer)
   - Supporting Evidence (Data, benchmarks, examples)
   - Implementation Roadmap
   - Financial Impact
   - Risk & Mitigation

**Output:** Raw content organized by presentation section

---

### STEP 3: Narrative Structuring
**Owner:** Consulting Expert Plugin → Problem-Solving Specialist

**Actions:**
1. Apply **Pyramid Principle** (Barbara Minto):
   - Lead with the answer (recommendation upfront)
   - Structure supporting arguments MECE
   - Layer data under each argument

2. Apply **SCQA Pattern**:
   - Situation: Current state context
   - Complication: Problem/opportunity
   - Question: What should we do?
   - Answer: Our recommendation

3. Build **logical flow**:
   - Executive Summary (standalone)
   - Problem/Context (why we're here)
   - Analysis/Options (what we evaluated)
   - Recommendation (what we propose)
   - Impact (what we achieve)
   - Next Steps (how we proceed)

4. Apply **6x6 Rule** for slide density:
   - Max 6 bullets per slide
   - Max 6 words per bullet
   - Exception: Tables and detailed data

**Output:** Structured narrative outline with slide sequence

**Example Outline:**
```
Slide 1: Title
Slide 2: Executive Summary (SCQA)
Slide 3-4: Current State & Challenge
Slide 5-6: Strategic Options Analysis
Slide 7-8: Recommended Approach
Slide 9-10: Financial Case (NPV, Timeline)
Slide 11-12: Implementation Roadmap
Slide 13: Risk & Mitigation
Slide 14: Decision & Next Steps
Slide 15+: Appendix
```

---

### STEP 4: Iterative Refinement with Sequential Thinking
**Owner:** Sequential Thinking MCP (MCP_DOCKER:sequentialthinking)

**Actions:**
1. **Evaluate narrative quality:**
   - Is the story arc compelling? (Problem → Solution → Impact)
   - Are arguments MECE and mutually reinforcing?
   - Is data supporting or overwhelming the message?
   - Does it pass the "elevator test"? (Can you explain slide 2 in 60 seconds?)

2. **Iterate on weak points:**
   - Unclear recommendation → Sharpen language
   - Weak business case → Add comparative data
   - Missing risks → Surface and mitigate
   - Dense slides → Simplify or split

3. **Optimize for audience:**
   - CIO → Add technical credibility markers
   - CFO → Strengthen financial justification
   - Board → Simplify, focus on governance and ROI
   - Technical Team → Add implementation detail

4. **Use Sequential Thinking to:**
   - Think through: "What questions will the audience ask?"
   - Validate: "Does this recommendation hold up under scrutiny?"
   - Refine: "Can we make this clearer/stronger/more compelling?"

**Output:** Refined narrative with optimizations applied

---

### STEP 5: Slide-by-Slide Content Development
**Owner:** Communication Expert Plugin → PowerPoint Specialist

**Actions:**
1. **For each slide, generate:**
   - Slide Title (states the insight, not just the topic)
   - Content (bullets, data, visuals)
   - Speaker Notes (30-45 seconds of talking points)
   - Visual Recommendation (chart type, layout)

2. **Apply presentation best practices:**
   - Title Slide: Compelling statement + context
   - Data Slides: One chart per slide, insight in title
   - Comparison Slides: MECE comparison matrix
   - Recommendation Slide: Clear CTA with next steps
   - Appendix: Supporting detail, organized by topic

3. **Ensure consistency:**
   - Terminology aligned across slides
   - Visual hierarchy maintained
   - Tone appropriate for audience
   - Formatting clean (whitespace, fonts, colors)

**Output:** Complete slide content specification

**Example Slide:**
```
SLIDE 7: Recommended Approach

Title: "Phased Cloud Migration Delivers $2.5M Annual Savings with Minimal Risk"

Content:
• Phase 1 (Q2-Q3): Non-critical workloads → Proven approach, build capability
• Phase 2 (Q4-Q1): Payment processing → Leverage Phase 1 learnings
• Phase 3 (Q2): Legacy decommission → Complete modernization

Investment: $8M over 18 months
Return: $2.5M annual savings, 2.4-year payback
Risk: Moderate, mitigated by phased approach

Speaker Notes:
"We're proposing a three-phase approach that balances speed with risk management. 
Phase 1 builds our team's cloud capability on non-critical systems. Phase 2 tackles 
our core payment processing with confidence. Phase 3 completes the transformation 
by retiring legacy infrastructure. This delivers $2.5M in annual savings with a 
proven, low-risk execution model."

Visual: Horizontal timeline with three phases, showing milestones and benefits
```

---

### STEP 6: PowerPoint Generation
**Owner:** PowerPoint MCP (Anthropic built-in skill: pptx)

**Actions:**
1. **Read SKILL.md for PowerPoint best practices:**
   ```
   Call: view tool on /mnt/skills/public/pptx/SKILL.md
   ```

2. **Generate .pptx file** with:
   - All slides from Step 5 content
   - Professional formatting (JP Morgan style if template available)
   - Charts and visuals where specified
   - Speaker notes included
   - Appendix slides clearly marked

3. **File naming convention:**
   ```
   [Topic]_[Audience]_[Date]_v1.pptx
   Example: CloudMigration_CIO_2026-02-17_v1.pptx
   ```

4. **Deliver to user:**
   ```
   Call: present_files with the generated .pptx filepath
   ```

**Output:** Downloadable PowerPoint first draft

---

## Quality Checks (Before Final Delivery)

**Content Quality:**
- [ ] Recommendation clear in Executive Summary (Slide 2)
- [ ] Story arc evident (Problem → Solution → Impact)
- [ ] Data supports arguments (no orphan charts)
- [ ] Financial case compelling (NPV, payback, ROI)
- [ ] Risks identified and mitigated

**Structural Quality:**
- [ ] SCQA pattern applied
- [ ] Pyramid Principle structure (answer first)
- [ ] MECE decomposition evident
- [ ] Slide count appropriate for time (1 min/slide + intro)
- [ ] Appendix organized and labeled

**Audience Fit:**
- [ ] Tone calibrated (CIO/CFO/Board/Team)
- [ ] Technical depth appropriate
- [ ] Business impact front-loaded
- [ ] Next steps actionable

**Technical Quality:**
- [ ] 6x6 rule followed (max 6 bullets, 6 words each)
- [ ] Slide titles state insights (not topics)
- [ ] Visual hierarchy clear
- [ ] No typos or formatting errors
- [ ] Speaker notes complete

---

## Example Execution

**User Request:**
"Create a presentation for the CIO on our AI agent strategy for payments automation"

**Step 1: Theme Evaluation**
```
Topic: AI agent strategy for payments
Domains: Technology (AI), Consulting (Strategy), Finance (ROI)
Audience: CIO
Type: Strategic initiative proposal
Framework: Problem → Solution → Impact

Skills Selected:
- AI Specialist (agent patterns, MCP)
- Tech Strategy Advisory (transformation roadmap)
- Business Case Specialist (ROI modeling)
- Problem-Solving Specialist (structure)
- PowerPoint Specialist (deck creation)
```

**Step 2-3: Content Generation & Structuring**
```
Outline:
1. Executive Summary
2. Current State: Manual payment processes → high cost, errors
3. AI Agent Opportunity: Automation potential
4. Recommended Approach: MCP-based agent architecture
5. Technical Architecture: Agent patterns (ReAct, Plan-Execute)
6. Business Case: $1.2M annual savings, 18-month payback
7. Implementation Roadmap: Phased rollout
8. Risks & Mitigation
9. Next Steps
```

**Step 4: Sequential Thinking Iteration**
```
Thought 1: Is the business case strong enough for CIO approval?
→ Add benchmark: "Industry leaders report 40% cost reduction"

Thought 2: Will CIO ask about vendor lock-in?
→ Add slide: "Open architecture prevents vendor lock-in"

Thought 3: Is technical credibility established?
→ Add: "Built on MCP standard, proven at [comparable org]"
```

**Step 5-6: Slide Creation & PowerPoint Generation**
```
Generate 14-slide deck with:
- SCQA structure
- Agent architecture diagrams
- Financial projections
- Phased roadmap
- Speaker notes for each slide

Output: AI_Agent_Strategy_CIO_2026-02-17_v1.pptx
```

---

## Command Success Criteria

This command succeeds when:
✅ Presentation addresses user's topic comprehensively
✅ Multiple plugin skills synthesized seamlessly
✅ Consulting frameworks (SCQA, Pyramid, MECE) applied
✅ Audience-appropriate tone and depth
✅ Downloadable .pptx file delivered
✅ User can present with minimal edits

---

## Version History

| Version | Date | Changes |
|---------|------|---------|
| 1.0.0 | 2026-02-17 | Initial command creation - Multi-plugin orchestration with MCP integration |

---

## Notes for Future Enhancement

**Potential improvements:**
- Add translation step (auto-generate PT-BR version using Translation Specialist)
- Integrate image search for slide visuals
- Add voice-over generation using text-to-speech
- Create accompanying executive brief email using E-mail Generator
- Auto-schedule presentation review using calendar integration

**Integration opportunities:**
- Google Slides export option
- Direct upload to SharePoint/OneDrive
- Auto-email to stakeholders with speaker notes
- Version control with previous presentations
