---
name: e-mail-generator
description: >
  This skill should be used when the user asks to "draft email", "write email", "reply email",
  "follow-up email", "escalation email", "status update email", "stakeholder communication",
  "executive summary email", "meeting summary email", "compose email", "email template",
  "professional email", "corporate email", "email tone", "email structure",
  or needs help crafting professional corporate emails for technology leadership contexts.
  Use this skill even when the user casually mentions needing to send or compose an email.
version: 2.0.0
---

# Skill — E-mail Generator

**Expert in crafting professional corporate emails for technology leadership contexts.** This skill produces clear, action-oriented emails calibrated to audience, with proper tone, structure, and cultural sensitivity for LATAM environments. Every email follows the BLUF principle — Bottom Line Up Front — so the reader knows the purpose within 10 seconds. It serves as the email knowledge base that the create-improve-email command orchestrates, and it can invoke text-improver-specialist for refinement and translation-specialist for bilingual delivery.

**Core Principles**: SPAR Framework, Pyramid Principle, SCQA Pattern, MECE Decomposition, Confidence Calibration, Source Attribution, Practical & Adaptable — these govern all outputs from this skill.

**Trigger keywords**: draft email, write email, reply email, follow-up email, escalation email, status update email, stakeholder communication, executive summary email, meeting summary email, compose email, email template, professional email, corporate email, email tone, email structure.

## Section 1 — Email Types & Subject Line Patterns

### 1.1 — Primary Email Types

| Type | When to Use | Subject Pattern |
|------|------------|-----------------|
| **Status Update** | Project progress, delivery milestones, blockers | `[Status Update] Project X – Milestone Y Achieved` |
| **Action Required** | Budget approval, vendor selection, resource requests | `[ACTION REQUIRED] Budget Approval Needed – $X by DATE` |
| **FYI** | Awareness only, no response needed | `[FYI] Q4 Technology Roadmap – No Action Required` |
| **Escalation** | Risks, budget overages, timeline slippages | `[ESCALATED] Vendor Delay – $X Impact, Mitigation Required` |
| **Follow-up** | Action items, decision confirmations, next steps | `[Follow-up] Decision on X – Confirmation Required by DATE` |
| **Meeting Summary** | Decisions, action items, owners, deadlines | `[Meeting Summary] Topic – Key Decisions & Actions` |

### 1.2 — Subject Line Rules

- Subject line must indicate the email type AND the core content
- Include the metric or deadline when relevant — it creates urgency
- Never use vague subjects like "Update" or "Quick question"
- Maximum 60 characters for mobile readability

## Section 2 — Email Structure Framework

### 2.1 — BLUF Opening (Bottom Line Up Front)

The first sentence states the decision, recommendation, or key message. Context comes second.

**Pattern**: `[What you need to know/do] + [by when] + [why it matters]`

**Strong BLUF examples**:
- "We recommend proceeding with Vendor A for the payment gateway migration. Approval needed by Friday."
- "Q3 delivery is on track — 78% complete with no blockers."
- "Budget overrun of $200K identified. Mitigation plan attached; decision required by Wednesday."

**Weak openings to avoid**:
- "I wanted to follow up on our discussion from last week..."
- "Hope you're doing well. I'm reaching out because..."
- "As discussed in the meeting, there are several items..."

### 2.2 — Body Structure

Maximum 4 paragraphs. Each paragraph earns its place:

1. **Context/Situation** (1-2 sentences): What triggered this email
2. **Key Message** (clear, singular): The recommendation or finding
3. **Supporting Details** (bulleted if >2 items): Evidence or options
4. **Next Steps** (specific owners & deadlines): Who does what by when

### 2.3 — Call-to-Action (CTA)

Every email that requires action must end with an explicit CTA:

- `Please confirm by [DATE]`
- `Decision needed: [Option A / Option B / Option C]`
- `Approval required by [DATE] — respond to this email`

Never close with: "Let me know if you have questions" — it's passive and creates no urgency.

## Section 3 — Tone Calibration

### 3.1 — Audience-Specific Tone

| Audience | Tone | Opening Style | Closing Style |
|----------|------|--------------|---------------|
| **CIO/C-Suite** | Concise, strategic, risk-aware | Impact first | Decision request + deadline |
| **CFO/Finance** | Data-driven, ROI-focused | Lead with business case | Budget impact summary |
| **Global Leads** | Formal, inclusive | Acknowledge geographies | Clear escalation paths |
| **Technical Teams** | Direct, detailed, context-rich | Problem statement | Technical next steps |
| **Vendors/External** | Professional, courteous | Formal greeting | Contract/process reminder |

### 3.2 — LATAM Cultural Considerations

- **Relational warmth**: LATAM culture favors slightly more personal, relational tone. A brief human touch without sacrificing professionalism
- **Language**: Default to English for C-level; offer Portuguese option for distributed teams
- **Time zones**: Always reference time zone explicitly: "Approval needed by Friday 5 PM São Paulo time"
- **Formality gradient**: Use "Sr./Sra." for initial contact; shift to first names after established relationship

## Section 4 — Email Patterns

### 4.1 — BLUF Pattern (Default)

```
Subject: [TYPE] Specific topic – Key metric or deadline

[BLUF: Decision/recommendation/status in one sentence]

Context: [1-2 sentences of situation]
Recommendation: [Clear recommendation]
Timeline: [Decision deadline]

Next Steps:
• [Owner]: [Action] by [Date]
• [Owner]: [Action] by [Date]

[Professional sign-off]
```

### 4.2 — Escalation Pattern

```
Subject: [ESCALATED] Risk/Issue – Immediate Attention Needed

[BLUF: What's at risk and what's needed]

Situation: [What happened]
Impact: [Business/timeline/budget impact — be specific with numbers]
Mitigation: [What we're doing + what we need from you]
Timeline: [Critical dates]
Decision: [What requires escalation approval]

[Sign-off with urgency]
```

### 4.3 — Meeting Summary Pattern

```
Subject: [Meeting Summary] Topic – Key Decisions & Actions

Meeting: [Name] | Date: [Date] | Attendees: [Names]

Key Decisions:
1. [Decision] — Owner: [Name]
2. [Decision] — Owner: [Name]

Action Items:
• [Action] — [Owner] — Due: [Date]
• [Action] — [Owner] — Due: [Date]

Next Meeting: [Date/Time] — Agenda: [Topic]
```

### 4.4 — Before/After Improvement Pattern

```
ORIGINAL:
[User's draft]

IMPROVED:
[Refactored email]

KEY IMPROVEMENTS:
• [What changed and why]
• [Tone/structure/clarity fixes]
```

## Section 5 — Thread Management & Etiquette

- **New Thread**: Use when topic is unrelated to previous conversation
- **Reply vs Forward**: Reply when continuing; forward when adding stakeholders
- **CC Etiquette**: CC = needs awareness; maximum 4 people without strong reason
- **BCC**: Rare — only for archiving per organizational policy
- **Reply-All**: Only when all recipients need the response

## Section 6 — Communication Protocol

### Opening (The Email)
The email itself IS the output. BLUF structure delivers the message. The reader should understand purpose, required action, and deadline within 10 seconds of opening.

### Body (The Guidance)
When generating an email, provide brief guidance notes: personalization points, tone adjustments, language options. Keep guidance minimal — the email is the star, not the notes.

### Conclusion (The Checklist)
End with a quick mental checklist: subject line clear, BLUF in first sentence, body ≤ 4 paragraphs, CTA with deadline, tone calibrated, recipients intentional.

## Output Patterns

### Email with Guidance Notes

```
═══════════════════════════════════════════════════════
EMAIL: [Type]
═══════════════════════════════════════════════════════

Subject: [Subject line]

[Full email text — ready to send]

───────────────────────────────────────────────────────
NOTES
───────────────────────────────────────────────────────
• Tone: [Calibration notes]
• Personalization: [What to adjust for your specific context]
• Language: [English/Portuguese option if relevant]
═══════════════════════════════════════════════════════
```

### Email Improvement Report

```
═══════════════════════════════════════════════════════
EMAIL IMPROVEMENT
═══════════════════════════════════════════════════════

ORIGINAL:
[User's draft]

IMPROVED:
[Refactored email]

───────────────────────────────────────────────────────
KEY IMPROVEMENTS
───────────────────────────────────────────────────────
• [Clarity fix]
• [Structure fix]
• [Tone calibration]
• [Word count: X → Y]
═══════════════════════════════════════════════════════
```

## Quality Checks

- [ ] Does the subject line indicate type AND content?
- [ ] Does the first sentence deliver the BLUF?
- [ ] Is the body ≤ 4 paragraphs?
- [ ] Is there an explicit CTA with deadline?
- [ ] Is the tone calibrated for the specific audience?
- [ ] Are recipients intentional (no unnecessary CC)?
- [ ] Would this email get the desired response on first read?

---

**Confidence Calibration**: High confidence for standard corporate email structures and tone calibration. Medium confidence for sensitive personnel communications or politically complex escalations — recommend human review for these cases.

**Triggers**: Activate when user requests email drafting, reply help, tone calibration, or professional email improvement.
