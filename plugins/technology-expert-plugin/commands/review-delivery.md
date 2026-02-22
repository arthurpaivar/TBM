---
description: Review delivery maturity and engineering excellence posture
allowed-tools: Read, WebSearch, WebFetch
argument-hint: "[delivery topic — e.g., 'DevOps maturity for payments team', 'CI/CD pipeline optimization']"
---

Review delivery maturity for $ARGUMENTS using the tech-delivery-specialist and agile-specialist skills.

## Layer 1 — Context & Intent

**What:** Define what delivery aspect is being reviewed and the scope of assessment.
**How:** Parse $ARGUMENTS to extract:
- What's being reviewed? (team, organization, pipeline, practice, tool)
- What delivery domain? (DevOps maturity, CI/CD, SRE, platform engineering, agile practices, DORA metrics)
- Is this a maturity assessment, a specific problem diagnosis, or an improvement plan?
- What's the current pain? (slow deployments, high failure rates, poor observability, team friction)
**Why:** Delivery reviews span two skills — tech-delivery-specialist for DevOps/SRE/CI-CD and agile-specialist for DORA metrics/SAFe/team topologies. Identifying the scope ensures both skills are loaded appropriately.

## Layer 2 — Knowledge Loading

**What:** Load both delivery-related specialist skills and extract the assessment frameworks.
**How:** Read both SKILL.md files:
- From **tech-delivery-specialist**: DevOps maturity model (Section 2.3), CI/CD pipeline design (Section 3), Platform maturity model (Section 4.3), SRE principles (Section 5), Quality engineering (Section 6), Benchmarks (Section 7)
- From **agile-specialist**: DORA metrics and performance levels (Section 2), Team topologies (Section 3), SAFe competencies (Section 1), Flow metrics and OKRs (Section 5)
**Why:** Delivery excellence lives at the intersection of DevOps practices and agile delivery. Loading both skills gives a complete picture — DORA metrics from agile-specialist provide the measurement framework, while tech-delivery-specialist provides the practices and maturity models.

## Layer 3 — Assessment Execution

**What:** Produce a comprehensive delivery maturity assessment.
**How:** Follow the Delivery Maturity Assessment output pattern, evaluating across:

1. **DORA Metrics** (from agile-specialist Section 2.2):
   - Deployment Frequency → classify as Elite/High/Medium/Low
   - Lead Time for Changes → classify
   - Change Failure Rate → classify
   - MTTR → classify
   - Trend direction (improving/stable/declining)

2. **DevOps Maturity** (from tech-delivery-specialist Section 2.3):
   - Score each CALMS dimension (Culture, Automation, Lean, Measurement, Sharing) on 1-5
   - Classify overall level (Initial → Optimized)

3. **Platform Engineering** (from tech-delivery-specialist Section 4):
   - Platform maturity level (Ad-hoc → Ecosystem)
   - Developer experience: inner loop and outer loop times
   - Self-service adoption rate

4. **Agile & Team Structure** (from agile-specialist Sections 1, 3):
   - SAFe competency scores if applicable
   - Team topology assessment (stream-aligned %, interaction modes)
   - Cognitive load assessment

5. **Observability & Reliability** (from tech-delivery-specialist Section 5):
   - Three pillars coverage (metrics, logs, traces)
   - SLI/SLO/SLA maturity
   - Incident management effectiveness

**Why:** A delivery review that only looks at one dimension gives a partial picture. The five-dimension assessment (DORA + DevOps + Platform + Agile + SRE) is MECE — it covers every aspect of delivery excellence without overlap.

## Layer 4 — Improvement Roadmap

**What:** Produce actionable improvement recommendations with expected DORA impact.
**How:**
1. Identify the top 3 strengths (celebrate what's working)
2. Identify the top 3 gaps (with business impact quantification where possible)
3. Build an improvement roadmap in three horizons:
   - **Quick wins (0-3 months)**: High-impact, low-effort improvements
   - **Medium-term (3-6 months)**: Structural improvements
   - **Strategic (6-12 months)**: Transformational changes
4. For each recommendation, state the expected DORA metric improvement
5. Reference specific benchmarks from both skills (DORA performance levels, platform maturity targets, DevEx targets)

If the review involves specific technologies or tools, use WebSearch to validate current best practices and alternatives.
**Why:** The roadmap is what makes a delivery review actionable. Without it, the assessment is just a diagnosis. The three-horizon structure with expected DORA impact gives the CIO a clear investment case for engineering excellence improvements.

**Output**: A structured delivery maturity assessment following the output patterns from both skills — DORA metrics, DevOps maturity scores (CALMS), platform maturity, agile assessment, observability coverage, strengths, gaps, and a three-horizon improvement roadmap with expected DORA impact. CIO-ready narrative with benchmarks and confidence calibration.
