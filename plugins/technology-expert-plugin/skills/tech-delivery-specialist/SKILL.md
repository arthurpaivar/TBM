---
name: tech-delivery-specialist
description: >
  This skill should be used when the user asks about "SDLC", "software development lifecycle",
  "DevOps", "CI/CD", "continuous integration", "continuous delivery", "continuous deployment",
  "pipelines", "build automation", "release management", "infrastructure as code",
  "platform engineering", "SRE", "site reliability engineering", "observability",
  "monitoring", "incident management", "change management", "deployment strategies",
  "containerization", "Kubernetes", "cloud native", "testing strategy",
  "quality engineering", "developer experience", "DevEx", "inner loop", "outer loop",
  "GitOps", "IaC", "Terraform", "chaos engineering", "toil reduction",
  "error budgets", "SLIs", "SLOs", "SLAs", "post-mortem", "blameless postmortem",
  "CALMS", "DevOps maturity", "platform maturity", "engineering excellence",
  or needs frameworks for technology delivery, engineering excellence, and operational reliability.
  Use whenever the user needs guidance on delivery practices, DevOps maturity, or SRE principles.
version: 3.0.0
---

# Skill — Tech Delivery Specialist

**Expert in technology delivery with deep knowledge of modern SDLC practices, DevOps, CI/CD pipelines, platform engineering, SRE, and quality engineering for enterprise payments systems.** This skill provides authoritative guidance on engineering excellence practices grounded in industry best practices (DORA, Google SRE, CALMS). It serves as the modular delivery knowledge base that other plugins reference — consulting for delivery maturity assessments, communication for engineering narratives, finance for delivery cost optimization.

**Core Principles**: SPAR Framework, Pyramid Principle, SCQA Pattern, MECE Decomposition, Confidence Calibration, Source Attribution, Practical & Adaptable — these govern all outputs from this skill.

**Trigger keywords**: SDLC, software development lifecycle, DevOps, CI/CD, continuous integration, continuous delivery, pipelines, build automation, release management, infrastructure as code, platform engineering, SRE, site reliability engineering, observability, monitoring, incident management, deployment strategies, containerization, Kubernetes, cloud native, testing strategy, quality engineering, developer experience, DevEx, GitOps, IaC, Terraform, chaos engineering, error budgets, SLIs, SLOs, SLAs, CALMS, DevOps maturity, engineering excellence.

## Section 1 — Software Development Lifecycle (SDLC)

### 1.1 Modern SDLC Models
1. **Waterfall**: Sequential phases. Still relevant for regulatory-heavy, fixed-scope projects
2. **Iterative/Incremental**: Build in cycles, refine each iteration
3. **Agile (Scrum/Kanban)**: Short sprints, continuous feedback, adaptive planning
4. **DevOps/Continuous**: Integrated development and operations, automated everything
5. **Lean Software Development**: Eliminate waste, amplify learning, deliver fast

### 1.2 SDLC Phases (Modern Interpretation)
1. **Discovery & Design**: Requirements, architecture, threat modeling, API contracts
2. **Development**: Coding, unit testing, code review, local environment testing
3. **Build & Integration**: CI pipeline, automated builds, static analysis, dependency scanning
4. **Testing**: Automated test suites (unit, integration, E2E, performance, security)
5. **Deployment**: CD pipeline, environment promotion, canary/blue-green/rolling deployments
6. **Operations**: Monitoring, alerting, incident response, auto-scaling
7. **Feedback & Optimize**: Observability insights, user feedback, continuous improvement

### 1.3 Governance Gates for Regulated Environments
For payments and banking:
- **Architecture Review**: Before development begins
- **Security Review**: Threat model, SAST/DAST results, pen test findings
- **Change Advisory Board (CAB)**: Before production deployment
- **Post-Implementation Review**: After major releases

## Section 2 — DevOps Practices

### 2.1 DevOps Principles (CALMS)
- **Culture**: Collaboration between dev and ops, shared ownership, blameless postmortems
- **Automation**: Automate everything repeatable — builds, tests, deployments, infrastructure
- **Lean**: Reduce waste, small batch sizes, limit WIP
- **Measurement**: DORA metrics, flow metrics, business outcomes
- **Sharing**: Knowledge sharing, documentation, communities of practice

### 2.2 DevOps Toolchain

| Stage | Purpose | Example Tools |
|---|---|---|
| Plan | Work tracking | Jira, Azure DevOps, Rally |
| Code | Version control | Git, GitHub, GitLab, Bitbucket |
| Build | Compilation | Maven, Gradle, npm, Docker |
| Test | Automated testing | JUnit, Selenium, Cypress, k6 |
| Release | Artifact management | Nexus, Artifactory, ECR |
| Deploy | Deployment automation | Ansible, Terraform, ArgoCD, Spinnaker |
| Operate | Monitoring | Datadog, Splunk, Prometheus, Grafana |
| Monitor | Observability | Dynatrace, New Relic, Jaeger, OpenTelemetry |

### 2.3 DevOps Maturity Model

| Level | Characteristics | Indicators |
|---|---|---|
| **1 — Initial** | Manual processes, siloed teams | Deploy monthly+, no CI, manual testing |
| **2 — Managed** | Basic CI, some automation | Deploy biweekly, basic CI, some automated tests |
| **3 — Defined** | Full CI/CD, IaC, automated testing | Deploy weekly, automated tests, IaC for most infra |
| **4 — Measured** | Metrics-driven, SRE practices | Deploy daily, DORA tracked, SLOs defined |
| **5 — Optimized** | Continuous improvement, chaos engineering | Deploy on-demand, elite DORA, full self-service |

## Section 3 — CI/CD Pipeline Design

### 3.1 Continuous Integration (CI)
- Every commit triggers automated build and test
- Fast feedback: target <10 minutes for CI pipeline
- Branch strategy: trunk-based development preferred for high-performing teams
- Quality gates: code coverage thresholds, zero critical vulnerabilities, linting pass

### 3.2 Continuous Delivery (CD)
- Code always in deployable state
- Automated promotion: Dev → QA → Staging → Production
- Environment parity: all environments as similar as possible
- Feature flags for decoupling deployment from release

### 3.3 Deployment Strategies

| Strategy | Risk | Downtime | Rollback | Best For |
|----------|------|----------|----------|----------|
| **Rolling** | Low | Minimal | Moderate | Standard updates |
| **Blue-Green** | Low | Zero | Instant | Critical systems |
| **Canary** | Very Low | Zero | Instant | Data-driven validation |
| **Feature Flags** | Very Low | Zero | Instant | Decoupled deploy/release |
| **A/B Testing** | Low | Zero | Easy | User experience decisions |

### 3.4 Pipeline as Code
- Version-controlled definitions (Jenkinsfile, .github/workflows, azure-pipelines.yml)
- Shared pipeline libraries for consistency
- Pipeline templates for common patterns (microservice, library, infrastructure)

## Section 4 — Platform Engineering

### 4.1 Internal Developer Platform (IDP)
The evolution of DevOps — self-service platforms that abstract infrastructure complexity:
- **Golden Paths**: Opinionated, pre-built workflows for common tasks
- **Service Catalog**: Discoverable catalog of platform capabilities
- **Self-Service Provisioning**: Developers provision without tickets
- **Guardrails**: Security, compliance, and cost controls built in

### 4.2 Developer Experience (DevEx)
- **Inner Loop**: Code → build → test → debug (local). Target: <30 seconds
- **Outer Loop**: Push → CI → CD → production. Target: <15 minutes
- **Cognitive Load**: Reduce mental effort to understand, build, and operate
- **Developer Surveys**: SPACE framework (Satisfaction, Performance, Activity, Communication, Efficiency)

### 4.3 Platform Maturity Model
1. **Ad-hoc**: No platform, teams manage own infrastructure
2. **Standardized**: Shared CI/CD, common templates
3. **Self-Service**: Developer portal, automated provisioning, golden paths
4. **Product-Managed**: Platform as product with roadmap, SLOs
5. **Ecosystem**: Internal marketplace, composable services, measured productivity

## Section 5 — Site Reliability Engineering (SRE)

### 5.1 SRE Principles (Google SRE Book)
- **SLIs, SLOs, SLAs**: Service Level Indicators (metrics), Objectives (targets), Agreements (contracts)
- **Error Budgets**: Allowed failure rate. If budget consumed, halt feature work → focus reliability
- **Toil Reduction**: Automate repetitive tasks. Target: <50% SRE time on toil
- **Blameless Postmortems**: Systemic improvements, not individual blame
- **Release Engineering**: Automated, reproducible, self-service deployments

### 5.2 Observability Stack (Three Pillars + Emerging)
1. **Metrics**: Quantitative measurements — USE (Utilization, Saturation, Errors) and RED (Rate, Errors, Duration) methods
2. **Logs**: Structured event records for debugging and auditing
3. **Traces**: Distributed request tracing across services (OpenTelemetry standard)
4. **Events**: System events correlated with changes and incidents (emerging)
5. **Profiling**: Continuous profiling for performance optimization (emerging)

### 5.3 Incident Management

| Phase | Activities |
|-------|-----------|
| **Detection** | Automated alerting on SLI breaches |
| **Triage** | Severity classification (P1–P4), escalation |
| **Response** | Incident commander, communication channels, war room |
| **Resolution** | Root cause analysis, remediation |
| **Learning** | Blameless postmortem, tracked action items |

### 5.4 Incident Severity Framework

| Severity | Definition | Response Time | Communication |
|---|---|---|---|
| **P1 — Critical** | Service down, data loss, financial impact | Immediate (24/7) | Executive notification, war room |
| **P2 — Major** | Significant degradation, workaround available | <30 minutes | Team notification, status page |
| **P3 — Minor** | Limited impact, non-urgent | <4 hours (business hours) | Team notification |
| **P4 — Low** | Cosmetic, enhancement | Next sprint | Backlog item |

## Section 6 — Quality Engineering

### 6.1 Testing Pyramid
- **Unit Tests** (base): Fast, isolated, high volume. Target: 70–80% of tests
- **Integration Tests** (middle): Service interactions, API contracts. Target: 15–20%
- **E2E Tests** (top): Full user journey, slow, fewer. Target: 5–10%

### 6.2 Shift-Left Testing
- Security testing (SAST, SCA) in CI pipeline
- Performance testing in pre-production
- Chaos engineering in staging and production
- Contract testing for API compatibility

### 6.3 Quality Metrics
- Code coverage: target 80%+ for critical services
- Escaped defects (bugs found in production)
- Test execution time and flakiness rate
- Technical debt ratio (SonarQube or equivalent)

## Section 7 — Delivery Benchmarks

- CI pipeline execution: <10 min target
- Deployment lead time: <1 hour for elite performers
- Change failure rate: <5% for elite performers
- MTTR: <1 hour for elite performers
- Platform adoption rate: >80% of teams self-serving
- Developer inner loop: <30 seconds target
- Developer outer loop: <15 minutes target
- Code coverage: 80%+ for critical services
- Test flakiness: <2% target

## Output Patterns

### Delivery Maturity Assessment
```
ORGANIZATION/TEAM: [Name]
ASSESSMENT DATE: [Date]

DEVOPS MATURITY (CALMS):
- Culture: [Level 1-5] — [Evidence]
- Automation: [Level 1-5] — [Evidence]
- Lean: [Level 1-5] — [Evidence]
- Measurement: [Level 1-5] — [Evidence]
- Sharing: [Level 1-5] — [Evidence]
- Overall: [Level 1-5]

DORA METRICS:
- Deployment Frequency: [value] → [Elite/High/Medium/Low]
- Lead Time: [value] → [level]
- Change Failure Rate: [value] → [level]
- MTTR: [value] → [level]

PLATFORM MATURITY: [Level 1-5] — [Evidence]
DEVELOPER EXPERIENCE: Inner loop [time], Outer loop [time]
OBSERVABILITY: [Metrics/Logs/Traces coverage]

STRENGTHS: [Top 3]
GAPS: [Top 3 with impact]

IMPROVEMENT ROADMAP:
1. [Quick win — 0-3mo] — [Expected DORA improvement]
2. [Medium-term — 3-6mo] — [Expected improvement]
3. [Strategic — 6-12mo] — [Expected improvement]

CONFIDENCE: [High/Medium/Low]
```

### CI/CD Pipeline Design
```
PIPELINE: [Name]
TYPE: [Microservice / Library / Infrastructure]

STAGES:
1. [Stage] → [Tools] → [Quality Gate] → [Target Duration]
2. [Stage] → [Tools] → [Quality Gate] → [Target Duration]

DEPLOYMENT STRATEGY: [Blue-Green / Canary / Rolling]
ROLLBACK: [Mechanism]
MONITORING: [Post-deployment checks]

TOTAL PIPELINE DURATION TARGET: [Time]
```

## Quality Checks

- [ ] Does the delivery recommendation align with DORA performance levels?
- [ ] Are DevOps practices grounded in CALMS framework?
- [ ] Is the CI/CD design following pipeline-as-code best practices?
- [ ] Are SRE principles (SLIs/SLOs, error budgets, toil reduction) properly applied?
- [ ] Does the observability strategy cover all three pillars (metrics, logs, traces)?
- [ ] Is the platform engineering maturity realistically assessed?
- [ ] Are deployment strategies appropriate for the risk profile (regulated environment)?
- [ ] Are benchmarks attributed to sources (DORA report, Google SRE)?
- [ ] Is the guidance suitable for CIO-level conversations about engineering excellence?

---

**Confidence Calibration**: High confidence for DORA metrics, CALMS framework, testing pyramid, SRE principles — well-documented with industry consensus. Medium confidence for platform engineering maturity models — this field is evolving rapidly. Low confidence for specific tooling recommendations beyond 12 months — vendor landscape changes fast, recommend web search.

**Triggers**: Activate when user needs delivery maturity assessments, pipeline design, SRE guidance, DevOps transformation planning, platform engineering strategy, or engineering excellence narratives for CIO conversations.
