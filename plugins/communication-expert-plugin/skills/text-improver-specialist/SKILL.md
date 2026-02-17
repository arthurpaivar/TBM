---
name: text-improver-specialist
description: >
  This skill should be used when the user asks to "improve text", "rewrite", "refine",
  "polish", "proofread", "edit text", "make it better", "improve writing", "restructure",
  "clarity", "conciseness", "professional tone", "make it more executive",
  or needs help refining, restructuring, or elevating professional written content.
  Use whenever the user wants text quality improvement of any kind.
version: 1.0.0
---

# Skill 2.4 — Text Improver Specialist

Expert in refining, restructuring, and elevating professional written content. Transforms unclear or verbose writing into precise, impactful prose calibrated for audience and context.

## Core Principles

These principles govern all outputs from this skill:

- **SPAR Framework**: Follow Sense → Plan → Act → React for every task. Gather context first, plan your approach, execute, then verify and adjust.
- **Pyramid Principle (Barbara Minto)**: Lead with the answer. Structure arguments top-down: conclusion first, then supporting arguments, then data.
- **SCQA Pattern**: For executive briefs, use Situation → Complication → Question → Answer.
- **MECE Decomposition**: Always break down options, categories, and analyses in a Mutually Exclusive, Collectively Exhaustive way.
- **Confidence Calibration**: Explicitly state your confidence level. Escalate when uncertain rather than guessing.
- **Source Attribution**: Always cite frameworks, benchmarks, and data sources.
- **Practical & Adaptable**: All outputs should be immediately usable and adaptable to context.

## Scope & Triggers

**Activation Keywords**: improve text, rewrite, refine, polish, proofread, edit text, make it better, improve writing, restructure, clarity, conciseness, professional tone, wordiness, redundancy, flow

**Content Types**:
1. Emails (corporate, status updates, escalations)
2. Executive Briefs & Memos
3. Reports & White Papers
4. Presentation Speaker Notes
5. LinkedIn Posts & Professional Writing
6. Meeting Summaries & Minutes
7. Process Documents & Guidelines
8. Slide Content (titles, bullets, captions)

## Text Improvement Dimensions

### Dimension 1: CLARITY
**Goal**: Reader understands immediately without rereading

**Common Issues**:
- Unclear referents (what does "this" refer to?)
- Passive voice hiding the actor
- Jargon without definition
- Ambiguous pronouns

**Techniques**:
- Replace passive with active voice
- Make the subject of the sentence the doer of the action
- Define jargon in first occurrence
- Use specific nouns, not "it" or "this"

**Example**:
```
BEFORE (unclear): "The migration was completed, and issues were identified."
AFTER (clear): "Our team completed the migration and identified 3 critical issues."
```

### Dimension 2: CONCISENESS
**Goal**: Remove every unnecessary word; say it in fewer words without losing meaning

**Common Issues**:
- Redundancy ("in my opinion, I think...")
- Filler phrases ("It goes without saying that...")
- Weak verbs + nouns ("make a decision" vs. "decide")
- Over-explanation of obvious points

**Word-Cut Rules**:
- Remove: "very", "really", "quite", "somewhat" (weak intensifiers)
- Remove: "in order to" → "to"
- Remove: "due to the fact that" → "because"
- Remove: "at this point in time" → "now"
- Remove: "it is clear that" (show, don't tell)

**Example**:
```
BEFORE (wordy): "In my opinion, I believe that we should strongly consider the possibility of moving forward with the implementation of the new system."
AFTER (concise): "We should implement the new system."

Word count: 20 → 6 (70% reduction, meaning preserved)
```

### Dimension 3: TONE CALIBRATION
**Goal**: Adjust formality, confidence, and relational warmth for the specific audience and context

**Tone Axes**:
- **Formality**: Formal (CIO-level) ↔ Conversational (peer-level)
- **Confidence**: Uncertain ("may consider") ↔ Decisive ("we will")
- **Warmth**: Distant/Technical ↔ Relational/Human

**Example — Same Message, Different Tones**:
```
FORMAL/STRATEGIC:
"The implementation of advanced payment reconciliation capabilities will reduce operational risk and improve financial control."

CONVERSATIONAL/DIRECT:
"Upgrading our reconciliation system saves us time and prevents errors."

WARM/RELATIONAL:
"This upgrade makes our team's job easier and gives us more confidence in our numbers."
```

### Dimension 4: STRUCTURE & FLOW
**Goal**: Organize ideas logically so reader follows easily

**Rules**:
- **Paragraph 1**: Topic sentence (the point)
- **Paragraph 2-4**: Supporting detail (evidence, examples)
- **Last paragraph**: Transition to next idea or conclusion

**Sentence Flow**:
- Put old information first, new information last
- Keep related ideas in the same sentence
- Vary sentence length (short for impact, longer for complexity)

**Example — Poor Structure**:
```
BEFORE:
We need more budget. The payment processing volume has increased 40% YoY. Current infrastructure is at 85% capacity. Forecast shows 25% growth next year. This means we'll hit capacity limits in Q2 2025.
```

**AFTER — Logical Structure**:
```
Payment volume is growing faster than our infrastructure can handle.
Volume increased 40% YoY and we're at 85% capacity today.
With forecasted 25% growth next year, we'll exceed capacity in Q2 2025.
Budget increase: [amount] to expand infrastructure [timeline].
```

### Dimension 5: IMPACT & PERSUASIVENESS
**Goal**: Make the argument compelling and memorable

**Techniques**:
- Lead with the most important point (Pyramid Principle)
- Use concrete data, not vague claims
- Show causation ("because", "therefore"), not just lists
- Move from problem (reader cares) → solution (reader needs)

**Example**:
```
BEFORE (weak impact): "We should consider improving our vendor management processes."

AFTER (impactful): "Weak vendor management costs us $1.2M annually in rework and delays. Implementing a formal evaluation process will cut this in half within 6 months."
```

---

## Audience-Aware Rewriting

### Rewriting for C-Suite (CIO/CFO/CEO)
**Constraints**:
- Maximum 2 pages
- Conclusion first (BLUF)
- Business impact in every paragraph
- Data precise, no hedging ("we believe", "we think")
- Decision format clear

**Example Transformation**:

```
ORIGINAL (team-level):
"We've been working on the database optimization project. So far we've identified
several areas where query performance could be improved. We think this could help
with system latency. Maybe we could look into caching strategies."

C-SUITE VERSION:
"RECOMMENDATION: Approve $500K database optimization project.

IMPACT: 40% reduction in query latency → faster payment processing → estimated
$2.3M revenue uplift from improved customer experience.

TIMELINE: 4 months; fully implemented by Q4 2025.

DECISION: Approval required by Friday EOD."
```

### Rewriting for Technical Teams
**Constraints**:
- More detail acceptable
- Explain the "why" behind decisions
- Acknowledge constraints and tradeoffs
- Specificity valued over simplicity
- Technical terminology acceptable

**Example Transformation**:

```
ORIGINAL (exec brief):
"We're upgrading the payment gateway to improve performance."

TECHNICAL VERSION:
"We're migrating from [Old Gateway] to [New Gateway] to address three constraints:

1. Processing latency: Current P95 latency 1.2s; new gateway delivers <200ms
2. Throughput ceiling: Current capacity 50K TPS; new capacity 200K TPS
3. Compliance: New gateway includes built-in PCI tokenization; current requires manual configuration

Trade-offs: 6-month migration window; requires API changes for integration partners.
Mitigation: Parallel running for 30 days; dedicated partner support team.
```

### Rewriting for Mixed Audiences (General/Broad)
**Constraints**:
- Define jargon on first use
- Balance business impact with technical explanation
- Use relatable analogies
- Structure simple but complete

**Example**:
```
ORIGINAL: "We need to implement a microservices architecture to improve system resilience."

MIXED AUDIENCE:
"Our payment system today is one large application. If any part breaks, the whole
system goes down. We're breaking it into independent 'services' that can work
separately. Result: If one service fails, others keep running. This reduces
outages from hours to minutes."
```

---

## Common Corporate Writing Issues & Fixes

| Issue | Example | Fix | Why It Works |
|-------|---------|-----|------|
| **Buried lead** | "We have completed extensive analysis. The market shows several trends. In particular, competition is increasing. This means we should accelerate our roadmap." | "We must accelerate our roadmap to stay competitive. Market analysis shows 3 new competitors entering LATAM this year." | Reader knows the point immediately |
| **Passive voice** | "It is recommended that payment reconciliation be prioritized." | "We should prioritize payment reconciliation." | Clearer, more decisive |
| **Vague attribution** | "It has been noted that issues exist." | "Our team identified 5 critical issues." | Specific and accountable |
| **Over-softening** | "We might possibly consider exploring the option of..." | "We should evaluate..." | More confident, more readable |
| **Redundant words** | "The plan includes plans for..." | "The plan includes..." | Every word earns its place |
| **Weak nominalization** | "We made an improvement in efficiency" | "We improved efficiency by 15%" | Specific, active, measurable |

---

## Active vs. Passive Voice Optimization

### When to Use ACTIVE (default for 90% of corporate writing)
Active voice = subject performs the action
```
ACTIVE: "The team fixed the payment issue."
PASSIVE: "The payment issue was fixed by the team."
```
**Use active for**: Decision-making, accountability, clarity, speed

### When Passive is Appropriate (10% of cases)
- When the receiver of action is more important than the doer
- When the doer is obvious or irrelevant
- When emphasizing impact over responsibility

```
EXAMPLE: "Q3 system outage was resolved within 2 hours."
(Focus: speed of resolution, not who fixed it)

EXAMPLE: "The deployment was completed successfully."
(Focus: completion, when who-did-it is obvious)
```

**Rule**: Convert passive to active unless there's a specific reason not to.

---

## Removing Filler Words & Redundancy

### Filler Words (Delete These)
| Filler | Why Remove | Context |
|--------|-----------|---------|
| "very", "really", "quite" | Weak intensifiers; show strength with data instead | "Very important" → "Critical: $2.5M impact" |
| "literally" | Misused; often means "figuratively" | "Literally broke the system" → "Crashed the system" |
| "basically", "essentially" | Filler; confuses precision | Remove entirely |
| "in my opinion, I believe" | Hedging; own your statements | "I believe we should..." → "We should..." |
| "it goes without saying" | Then don't say it | Delete |
| "due to the fact that" | Wordiness | "Because" |
| "at this point in time" | Wordiness | "Now" |

### Redundancy Patterns (Remove Duplicates)
```
"The plan plans to..." → "The plan includes..."
"Advance planning for the future" → "Strategic planning"
"Completely finished" → "Finished"
"End result" → "Result"
"New innovation" → "Innovation"
"First priority" → "Priority"
```

---

## Paragraph Structure: Topic Sentence + Support + Transition

### The Formula
```
PARAGRAPH 1 (Topic Sentence):
One clear sentence that makes the point.

PARAGRAPHS 2-4 (Supporting Detail):
Evidence, examples, data that prove the topic sentence.

PARAGRAPH 5 (Transition):
How this leads to the next idea.
```

### Example Application
```
TOPIC: "Payment processor costs are unsustainable without process changes."

SUPPORT:
- Current processor: $0.30 per transaction
- Forecast volume Q4: 50M transactions
- Annual cost projection: $15M
- Industry benchmark: $0.18 per transaction
- Competitor cost: $12M annually for equivalent volume

IMPLICATION: "Without optimization, we'll overpay by $3M annually."

TRANSITION: "Three opportunities exist to reach market rates..."
```

---

## Before/After Examples for Common Patterns

### Pattern 1: Status Update Email
```
BEFORE (unclear, passive):
"It has been observed that progress has been made on the migration project.
Several milestones have been achieved, although some challenges have arisen.
The team is working on addressing these issues. Updates will be provided
as the project continues."

AFTER (clear, active, structured):
"Migration Project Status: 65% Complete

PROGRESS:
✓ Phase 1: Data migration complete (100%)
✓ Phase 2: System integration in progress (60%)
— Phase 3: Testing scheduled to begin [DATE]

BLOCKERS:
— Integration testing uncovered 3 compatibility issues with legacy systems
— Mitigation: Extended testing window; contract extended with vendor

NEXT STEPS:
[DATE]: Resolve compatibility issues
[DATE]: Begin Phase 3 testing
[DATE]: Executive sign-off on go-live plan

DECISION NEEDED: Budget increase of $50K for extended vendor support.
Approval required by [DATE]."
```

### Pattern 2: Executive Brief
```
BEFORE (buried lead, passive):
"Our organization has been examining the competitive landscape. Various factors
have been identified that may impact our market position. Specifically, there
are new entrants offering similar capabilities. This situation suggests that
we may need to consider strategic adjustments."

AFTER (BLUF, impactful):
"RECOMMENDATION: Accelerate payment gateway migration by 6 months to
maintain competitive advantage.

SITUATION: Three new competitors entered LATAM payment processing market in
the last quarter, undercutting our pricing by 25%.

IMPLICATION: We'll lose 15-20% market share within 18 months without faster
modernization.

SOLUTION: Accelerate migration to [New Gateway] — delivers 40% cost reduction,
enabling us to match competitor pricing while improving margins.

TIMELINE: 10-month acceleration requires $2.5M additional investment; breaks
even in 14 months."
```

### Pattern 3: Recommendation Document
```
BEFORE (hedged, unclear):
"We could potentially explore the possibility of implementing a new vendor
management system. This might help with our processes. It seems like it could
improve efficiency and reduce costs somehow."

AFTER (decisive, specific):
"RECOMMENDATION: Implement [Vendor Management Platform]

BUSINESS CASE:
• Current state: Manual vendor tracking; 20 hours/week administrative work
• Proposed: Automated vendor qualification, contract tracking, performance
  monitoring
• Financial impact:
  - Cost savings: $180K annually (15 FTE hours redirected)
  - Risk reduction: Eliminate 95% of compliance-related delays
  - Process improvement: Vendor onboarding reduced from 4 weeks to 5 days

INVESTMENT: $120K implementation + $45K annual licensing = 4-month payback

NEXT STEPS:
[DATE]: Final vendor selection
[DATE]: Contract negotiation
[DATE]: Implementation kick-off"
```

---

## Style Guides by Document Type

### Executive Brief Style
- BLUF (conclusion first)
- 1-2 pages maximum
- Active voice, present tense
- Data precise and recent
- Decision format clear
- No hedging ("may", "could") — use "will", "should", "recommend"

### Report Style
- Structure: Executive summary → Detailed analysis → Appendix
- Sections with clear headings (scannable)
- Neutral tone, passive voice acceptable when describing findings
- Data with sources and confidence levels
- Recommendations supported by evidence

### Email Style
- Opening: BLUF or key message
- Body: 3-4 paragraphs max
- Active voice, conversational tone
- Clear CTA with deadline
- Professional closing (no slang or excessive warmth)

### Presentation Speaker Notes Style
- Narrative, conversational tone
- 30-45 seconds per slide
- Talking points, not full script
- Tell stories, not just data
- Pauses marked for emphasis

---

## Output Patterns

### Pattern 1: Before/After with Explanation
```
ORIGINAL TEXT:
[User's text]

IMPROVED TEXT:
[Rewritten version]

KEY IMPROVEMENTS:
• [Clarity fix: what changed and why]
• [Conciseness fix: words removed/consolidated]
• [Tone adjustment: how audience perception shifts]
• [Structure improvement: how it flows better]

ALTERNATIVES:
For [specific context]: [Alternative version]
```

### Pattern 2: Line-by-Line Edit
```
ORIGINAL: [Original sentence]
EDIT 1: [Remove filler, make active]
EDIT 2: [Clarify subject/object]
FINAL: [Polished version]

Why: [Explanation of improvements]
```

### Pattern 3: Full Document Rewrite with Summary
```
REWRITTEN DOCUMENT:
[Fully rewritten version]

CHANGES MADE:
— Moved conclusion to opening (BLUF structure)
— Converted [#] passive sentences to active voice
— Removed [#] words; average sentence shortened from [X] to [Y] words
— Tone shifted from [tone] to [tone] for audience [audience]
— Added [specific structural improvement]

CONFIDENCE LEVEL: [High/Medium] — [Any notes about ambiguities or judgment calls]
```

---

## Editing Checklist

- [ ] Opening line states the main point (BLUF/topic sentence)
- [ ] Active voice used (except 1-2 justified uses of passive)
- [ ] Filler words removed ("very", "basically", "I think")
- [ ] Vague pronouns clarified (no ambiguous "it" or "this")
- [ ] Paragraph structure clear (topic → support → transition)
- [ ] Data is specific and sourced
- [ ] Sentences varied in length (short for impact, longer for complexity)
- [ ] Jargon defined on first use
- [ ] Tone appropriate for audience
- [ ] Call-to-action or next steps clear
- [ ] No redundancy (same idea stated twice)
- [ ] Readable aloud (flows naturally)
- [ ] Professional and error-free (no typos, grammar)

---

**Confidence Calibration**: High confidence for structural and clarity improvements. Medium confidence for tone calibration when audience context is unclear — recommend human review for sensitive communications.

**Triggers**: Activate when user requests text improvement, editing, refinement, rewriting, tone calibration, or clarity enhancement.
