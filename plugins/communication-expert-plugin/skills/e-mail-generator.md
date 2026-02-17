---
name: e-mail-generator
description: >
  This skill should be used when the user asks to "draft email", "write email", "reply email",
  "follow-up email", "escalation email", "status update email", "stakeholder communication",
  "executive summary email", "meeting summary email",
  or needs help crafting professional corporate emails for technology leadership contexts.
  Use this skill even when the user casually mentions needing to send or compose an email.
version: 1.0.0
---

# Skill 2.1 — E-mail Generator

Expert in crafting professional corporate emails for technology leadership contexts. Produces clear, action-oriented emails calibrated to audience, with proper tone, structure, and cultural sensitivity for LATAM environments.

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

**Activation Keywords**: email, e-mail, draft email, write email, reply email, follow-up, escalation email, status update email, stakeholder communication, executive summary email

**Primary Email Types**:
1. Status Updates (project progress, delivery milestones, blockers)
2. Escalations (risks, budget overages, timeline slippages)
3. Approval Requests (vendor selection, budget allocation, resource requests)
4. Follow-ups (action items, decision confirmations, next steps)
5. Stakeholder Communications (alignment updates, strategic directions)
6. Meeting Summaries (decisions, action items, owners, deadlines)

## Email Structure Framework

### Subject Line Patterns
- **Status**: `[Status Update] Project X — Milestone Y Achieved`
- **Action Required**: `[ACTION REQUIRED] Budget Approval Needed — Amount & Timeline`
- **FYI**: `[FYI] Q4 Technology Roadmap — Strategic Alignment`
- **Escalation**: `[ESCALATED] Risk: Vendor Delay — Impact & Mitigation`

### BLUF Opening (Bottom Line Up Front)
Begin with the decision, recommendation, or key message in the first sentence. Follow with context.

Example: *"We recommend proceeding with Vendor A for our payment gateway migration. Decision required by Friday EOD."*

### Body Structure (3-5 paragraphs max)
1. **Context/Situation** (1-2 sentences): What triggered this email?
2. **Key Message/Recommendation** (clear and single): What do you need?
3. **Supporting Details** (bulleted if >2 items): Why this is the answer
4. **Action/Next Steps** (specific owners & deadlines): Who does what by when?

### Call-to-Action (CTA)
- Explicit: `Please confirm by [DATE]` or `Decision needed: [OPTIONS]`
- Avoid ambiguous closings like "Let me know if you have questions"
- Always include deadline and decision format

## Tone Calibration by Audience

| Audience | Tone | Opening | Closing |
|----------|------|---------|---------|
| CIO/C-Suite | Concise, strategic, risk-focused | Start with impact | Decision request + deadline |
| CFO/Finance | Data-driven, ROI-focused, fiscal | Lead with business case | Budget impact summary |
| Global Leads | Formal, inclusive, aligned | Acknowledge geographies | Escalation paths clear |
| Technical Teams | Direct, detailed, context-rich | Problem statement | Technical next steps |
| Vendors/External | Professional, courteous, clear | Formal greeting | Contract/process reminder |

## LATAM-Specific Considerations

- **Tone**: LATAM culture favors slightly more personal, relational tone vs. Anglo-Saxon brevity. Add brief human touch without sacrificing professionalism.
- **Bilingual Context**: Default to English for C-level, offer Portuguese option for distributed teams. Flag language explicitly: "This email is in [English|Portuguese]. Preference for [other language]?"
- **Time Zones**: Reference time zone explicitly when setting deadlines: "Approval needed by Friday 5 PM São Paulo time"
- **Formality**: Use "Sr./Sra." for initial contact; shift to first names after established relationship

## Common Corporate Patterns

### BLUF Pattern
```
[DECISION REQUIRED] [Brief statement of what's needed]

Context: [1-2 sentences of situation]
Recommendation: [Clear recommendation]
Timeline: [Decision deadline]
```

### Action-Required Flag Pattern
```
Subject: [ACTION REQUIRED] [Specific action] — Deadline [DATE]

Body:
We need [specific action] by [DATE] to [business impact].

What we need from you: [List, max 3 items]
Timeline: [Milestones/deadline]
Owner: [Person responsible for follow-up]
```

### FYI Pattern (Information Only)
```
Subject: [FYI] [Topic] — No action required

Body:
Sharing for awareness: [Key information]

Context: [Why this matters]
Impact: [How this affects their work, if relevant]
Questions: [Contact if clarification needed]
```

### Escalation Pattern
```
Subject: [ESCALATED] [Risk/Issue] — Immediate Attention Needed

Situation: [What happened]
Impact: [Business/timeline/budget impact]
Mitigation: [What we're doing; what we need from you]
Timeline: [Critical dates]
Decision: [What requires escalation approval]
```

## Thread Management

- **New Thread**: Use when topic is unrelated to previous conversation
- **Reply vs Forward**: Reply when continuing conversation; forward when bringing new stakeholders in
- **CC/BCC Etiquette**:
  - CC = needs awareness, may need to respond
  - BCC = rare, only for archiving; avoid unless explicit organizational policy
  - Don't CC more than 4 people without strong reason

## Output Patterns

### Pattern 1: Email Template with Guidance
```
[Subject line recommendation]

[Opening sentence — BLUF]

[Body: context, key message, supporting points]

[Call-to-action with deadline]

[Sign-off]

---
NOTES FOR USER:
- [Personalization points]
- [Tone adjustments based on relationship]
- [Language options if relevant]
```

### Pattern 2: Before/After Comparison
```
ORIGINAL (unclear):
[User's draft]

IMPROVED:
[Refactored email]

WHY THIS WORKS:
- [Clarity improvement]
- [Structure improvement]
- [Tone calibration]
```

## Examples by Context

### Status Update Email (Technical Team)
**When**: Weekly/monthly progress check
**Structure**: Milestones → Blockers → Next Week → Escalations (if any)

### Escalation Email (CIO)
**When**: Risk/delay/budget overrun surfaces
**Structure**: Impact first → Mitigation plan → Decision needed → Timeline

### Approval Request (CFO)
**When**: Budget, vendor, or resource decision
**Structure**: Business case → Financials → Risk → ROI → Decision format

## Checklist Before Sending

- [ ] Subject line clearly indicates action/type (STATUS/ACTION/FYI/ESCALATION)
- [ ] BLUF in first sentence — reader knows purpose in 10 seconds
- [ ] Body ≤ 4 paragraphs or equivalent white space
- [ ] Clear CTA with deadline and decision format
- [ ] Recipient list correct (CC/BCC intentional)
- [ ] Tone appropriate for audience
- [ ] Language consistent (English/Portuguese, not mixed)
- [ ] Formal greeting/sign-off appropriate
- [ ] No typos, professional formatting

---

**Confidence Calibration**: This skill provides high-confidence email structures for standard corporate contexts. Custom escalations or sensitive personnel communications may require human judgment refinement.

**Triggers**: Activate when user requests email drafting, reply help, or tone calibration for professional communication.
