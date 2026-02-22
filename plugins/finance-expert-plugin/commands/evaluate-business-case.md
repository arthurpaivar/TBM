---
description: Evaluate a business case proposal for technology investment
allowed-tools: Read, Write, Edit, Grep, Glob, Bash, WebSearch, WebFetch, Task
argument-hint: "[business case document or investment proposal — e.g., 'cloud migration business case', 'fraud detection platform investment']"
---

Evaluate the business case in $ARGUMENTS using the tech-bm-specialist and it-portfolio-management skills.

## Layer 1 — Context & Intent

**What:** Define what business case is being evaluated and what the user needs.
**How:** Parse $ARGUMENTS to extract:
- What investment is being proposed? (new platform, modernization, vendor purchase, etc.)
- Is there a document attached, or does the user want a framework for evaluation?
- What's the investment tier? (Strategic >$5M, Tactical $500K-$5M, Operational <$500K)
- What decision is needed? (Go/No-Go, compare alternatives, strengthen the case)
**Why:** Business case evaluations range from quick assessments to deep financial analyses. Clarifying the scope prevents over- or under-engineering the response.

## Layer 2 — Knowledge Loading

**What:** Load both financial skills to cover investment governance and TBM alignment.
**How:** Read both SKILL.md files:
- From **tech-bm-specialist**: Business Case Framework (Section 4.3), Investment Typification (Section 4.2), R/G/T classification (Section 4.1), Value Realization (Section 4.4), IT Spend Benchmarks (Section 6.3)
- From **it-portfolio-management**: Investment Decision Framework (Section 2.4), Prioritization Methods (Section 2.3), Demand Management (Section 2.2), Unit Economics (Section 3.2)
**Why:** A strong business case evaluation needs both the TBM financial lens (is the cost structure sound?) and the portfolio lens (does this fit our investment strategy?). Loading both skills ensures comprehensive assessment.

## Layer 3 — Evaluation Execution

**What:** Produce a structured business case evaluation across all dimensions.
**How:** Evaluate the proposal using the Investment Decision Framework (5 dimensions):

1. **Strategic Fit** (30%): Does it align with business strategy, OKRs, technology roadmap? What R/G/T category? What horizon (H1/H2/H3)?
2. **Financial Merit** (25%): Validate NPV, IRR, payback period, TCO. Check assumptions against benchmarks. Stress-test with sensitivity analysis
3. **Risk Profile** (20%): Assess technical, delivery, adoption, regulatory, vendor risks. Each rated High/Medium/Low with mitigation
4. **Capacity Impact** (15%): What skills, teams, and infrastructure are needed? Is capacity available?
5. **Dependencies** (10%): Cross-portfolio dependencies, integration requirements, timing constraints

Score each dimension 1-5 and calculate weighted composite score.
**Why:** The 5-dimension framework is MECE — it covers strategic, financial, risk, operational, and dependency aspects without overlap. The weighted scoring makes the evaluation defensible in investment committee discussions.

## Layer 4 — Recommendation & Output

**What:** Deliver a scored assessment with clear Go/No-Go recommendation.
**How:**
1. Calculate composite score (weighted average of 5 dimensions)
2. Classify: Strong (>4.0) = Go, Moderate (3.0-4.0) = Go with conditions, Weak (<3.0) = No-Go or rework
3. Compare against industry benchmarks (IT spend, R/G/T ratios, TCO benchmarks)
4. Provide specific improvement recommendations if the case is weak
5. Include confidence calibration for each dimension

If the user wants an Excel-based evaluation, reference the excel-for-finance skill's Business Case Financial Model template (Section 3.2).
**Why:** The Go/No-Go framing is what investment committees need. The scored assessment provides a defensible methodology, and the improvement recommendations make a No-Go constructive rather than just a rejection.

**Output**: Business Case Evaluation with scored assessment (5 dimensions), financial validation (NPV/IRR/payback), R/G/T classification, benchmark comparison, risk analysis, and Go/No-Go recommendation with confidence calibration.
