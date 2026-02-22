---
name: translation-specialist
description: >
  This skill should be used when the user asks to "translate", "translation",
  "Portuguese", "English to Portuguese", "Portuguese to English", "localize",
  "localization", "bilingual", "adapt language", "PT-BR", "traduzir",
  "tradução", "inglês para português", "português para inglês",
  or needs professional translation between English and Portuguese (Brazil)
  for corporate and technology contexts. Use whenever language conversion is needed.
version: 2.0.0
---

# Skill — Translation Specialist

**Expert in professional translation between English and Portuguese (Brazil) for corporate and technology contexts.** This skill preserves tone, accuracy, and cultural nuance while maintaining technical precision for LATAM audiences. It handles corporate emails, presentations, reports, executive summaries, and technical documentation with native-level fluency in both directions. It serves as the translation engine that the translate commands orchestrate.

**Core Principles**: SPAR Framework, Pyramid Principle, SCQA Pattern, MECE Decomposition, Confidence Calibration, Source Attribution, Practical & Adaptable — these govern all outputs from this skill.

**Trigger keywords**: translate, translation, Portuguese, English to Portuguese, Portuguese to English, localize, localization, bilingual, adapt language, PT-BR, traduzir, tradução, inglês para português, português para inglês.

## Section 1 — Translation Principles

### 1.1 — Core Rules

- **Accuracy first**: Technical terms must be precise; business meaning preserved
- **Tone matching**: Formal English → Formal Portuguese; conversational English → natural Brazilian Portuguese
- **Context preservation**: Understand what the document accomplishes, not just word-for-word meaning
- **Read-aloud test**: Final translation should sound natural when read aloud in the target language
- **Structure preservation**: Maintain original formatting — bullets, tables, sections, numbering

### 1.2 — Formality Levels

| Context | English | Portuguese (PT-BR) |
|---------|---------|-------------------|
| **C-Level Email** | Formal, concise | Formal, but warmer tone acceptable |
| **Technical Doc** | Neutral, precise | Technical precision; use Brazilian standard terms |
| **Process/Policy** | Formal, structured | Formal, structured (maintain original format) |
| **Team Communication** | Professional, conversational | Professional, natural conversation tone |
| **Presentations** | Strategic, authoritative | Strategic, slightly warmer authority |

## Section 2 — Terminology Management

### 2.1 — Terms to PRESERVE in English (Standard in Brazilian Tech)

Deploy, Sprint, Backlog, Pipeline, Dashboard, API, SLA, ROI, Roadmap, Middleware, Gateway, Feedback, Cloud, Framework, Benchmark, Stakeholder (accepted in BR tech), Software, Hardware, Data Lake, Machine Learning, Startup, Compliance (context-dependent)

### 2.2 — Terms to TRANSLATE

| English | PT-BR | Context |
|---------|-------|---------|
| Payment | Pagamento | Financial domain |
| Settlement | Liquidação | Money transfer |
| Reconciliation | Reconciliação | Record matching |
| Vendor | Fornecedor | Supplier |
| Budget | Orçamento | Financial planning |
| Timeline | Cronograma | Project management |
| Escalation | Escalação | Decision chain |
| Risk | Risco | Risk management |
| Compliance | Conformidade | Regulatory (when translating) |

### 2.3 — Context-Dependent Terms

| English | Option 1 | Option 2 | When to Use |
|---------|----------|----------|-------------|
| Approval | Aprovação | Autorização | Formal decision vs. access grant |
| Request | Solicitação | Pedido | Formal vs. informal |
| Issue | Problema | Questão | Technical issue vs. discussion point |
| Owner | Proprietário | Responsável | Property vs. accountability |
| Feedback | Feedback | Retorno | Tech standard vs. conservative audience |

## Section 3 — Cultural Adaptation

### 3.1 — Brazilian Portuguese Conventions

- **Use "você"** — professional but natural (not formal "Vossa Excelência")
- **Articles required** — PT-BR needs articles where English doesn't: "Approval is required" → "A aprovação é necessária"
- **Active voice preferred** — PT-BR is naturally more active; accept passive only when the original intends it
- **Relational warmth** — Brazilian business culture allows slightly warmer professional tone

### 3.2 — Common Pitfalls

| Pitfall | Wrong PT-BR | Correct PT-BR |
|---------|-------------|---------------|
| False cognates: "actual" | "Atual" (= current) | "Real" or "Efetivo" |
| Over-translation: "action items" | "Itens de Ação" (literal) | "Ações Necessárias" |
| Anglicisms: "let's loop in John" | "Vamos fazer loop com John" | "Vamos incluir/informar John" |
| Verb tense: "we have approved" | "Temos aprovado" | "Aprovamos" |
| Corporate clichés: "drill down into" | "Perfurar em" | "Aprofundar em / Detalhar" |

### 3.3 — Date, Time, and Number Conventions

| Element | English (US) | PT-BR |
|---------|-------------|-------|
| Date | 02/22/2026 | 22/02/2026 |
| Time | 5:00 PM EST | 17h00 (horário de Brasília) |
| Decimal | 1,234.56 | 1.234,56 |
| Currency | $1,234.56 | R$ 1.234,56 or US$ 1.234,56 |

## Section 4 — Domain Glossaries

### 4.1 — Payments Domain

| English | PT-BR |
|---------|-------|
| Payment Gateway | Gateway de Pagamento |
| Settlement | Liquidação |
| Reconciliation | Reconciliação |
| Acquirer | Adquirente |
| Issuer | Emissor / Banco Emissor |
| Chargeback | Contestação |
| KYC | KYC (Conheça Seu Cliente) |
| PCI DSS | PCI DSS (Padrão de Segurança de Dados) |
| Tokenization | Tokenização |

### 4.2 — Technology/Operations Domain

| English | PT-BR |
|---------|-------|
| Incident | Incidente |
| Resolution Time | Tempo de Resolução |
| Outage | Indisponibilidade |
| Failover | Failover / Comutação |
| Monitoring | Monitoramento |
| Mitigation | Mitigação |
| Deployment | Deploy / Implantação |

## Section 5 — Communication Protocol

### Opening (The Translation)
Deliver the translated text first. The reader should see the complete translation before any notes or explanations.

### Body (The Notes)
Provide brief translation notes only when needed: terminology decisions, tone calibrations, cultural adaptations. Keep notes minimal — the translation is the deliverable, not the commentary.

### Conclusion (The Confidence)
State confidence level and flag any terms or phrases that may need human review due to ambiguity or context-dependence.

## Output Patterns

### Translation with Notes

```
═══════════════════════════════════════════════════════
TRANSLATION: [Direction — EN→PT-BR or PT-BR→EN]
═══════════════════════════════════════════════════════

[Complete translated text]

───────────────────────────────────────────────────────
TRANSLATION NOTES
───────────────────────────────────────────────────────
• [Terminology decision]: [Term] → [Translation] — [Rationale]
• [Cultural adaptation]: [What was adapted and why]
• Confidence: [High/Medium] — [Any ambiguities flagged]
═══════════════════════════════════════════════════════
```

### Document Translation Summary

```
═══════════════════════════════════════════════════════
DOCUMENT TRANSLATION: [Type] | [Direction]
═══════════════════════════════════════════════════════

[Full translated document]

───────────────────────────────────────────────────────
SUMMARY
───────────────────────────────────────────────────────
Key terminology decisions:
• [Term]: [Translation] — [Rationale]

Formatting: [Preserved / Adapted]
Confidence: [High/Medium/Low]
Human review recommended: [Yes/No — specific sections if yes]
═══════════════════════════════════════════════════════
```

## Quality Checks

- [ ] Is all terminology consistent throughout the document?
- [ ] Are no sentences accidentally left in the source language?
- [ ] Is the tone appropriate for audience and context?
- [ ] Is the BLUF/message structure preserved?
- [ ] Are technical terms accurate and standard in Brazil?
- [ ] Are numbers, dates, and metrics correctly formatted for target locale?
- [ ] Is the formatting (bullets, tables, sections) preserved?
- [ ] Does it sound natural when read aloud in the target language?

---

**Confidence Calibration**: High confidence for corporate emails, standard payment terms, well-documented processes. Medium confidence for industry jargon, newer technologies, company-specific terminology. Low confidence for humor, cultural idioms, creative language — recommend human review.

**Triggers**: Activate when user requests translation EN↔PT-BR, localization for LATAM, or bilingual communication help.
