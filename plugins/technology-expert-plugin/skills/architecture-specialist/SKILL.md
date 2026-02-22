---
name: architecture-specialist
description: >
  This skill should be used when the user asks about "enterprise architecture", "solution architecture",
  "microservices", "event-driven architecture", "API design", "API gateway", "domain-driven design", "DDD",
  "TOGAF", "architecture patterns", "cloud architecture", "serverless", "service mesh",
  "architecture decision records", "ADR", "system design", "scalability", "high availability",
  "disaster recovery", "architecture review", "technical debt", "legacy modernization",
  "12-factor app", "hexagonal architecture", "CQRS", "event sourcing", "data mesh",
  "architecture governance", "reference architecture", "payments architecture",
  "PCI-DSS", "ISO 20022", "payment rails", "settlement", "real-time payments",
  "cloud native", "well-architected", "resilience patterns", "circuit breaker",
  or needs guidance on enterprise or solution architecture patterns and decisions.
  Use whenever the user needs architecture assessments, pattern recommendations, or technology design guidance.
version: 3.0.0
---

# Skill — Architecture Specialist

**Expert enterprise and solution architect with deep knowledge of modern architecture patterns, cloud-native design, API strategies, data architecture, payments infrastructure, and architecture governance.** This skill provides authoritative guidance that balances pragmatism with technical excellence, grounded in industry standards and proven patterns. It serves as the modular architecture knowledge base that other plugins reference for technical depth — consulting uses it for architecture assessments, communication for architecture narratives, finance for infrastructure cost analysis.

**Core Principles**: SPAR Framework, Pyramid Principle, SCQA Pattern, MECE Decomposition, Confidence Calibration, Source Attribution, Practical & Adaptable — these govern all outputs from this skill.

**Trigger keywords**: enterprise architecture, solution architecture, microservices, event-driven architecture, API design, API gateway, domain-driven design, DDD, TOGAF, architecture patterns, cloud architecture, serverless, service mesh, ADR, system design, scalability, high availability, disaster recovery, architecture review, technical debt, legacy modernization, 12-factor app, hexagonal architecture, CQRS, event sourcing, data mesh, architecture governance, reference architecture, payments architecture, PCI-DSS, ISO 20022, circuit breaker, resilience patterns.

## Section 1 — Enterprise Architecture Frameworks

### 1.1 TOGAF ADM (Architecture Development Method)

| Phase | Purpose | Key Deliverables |
|-------|---------|-----------------|
| **A: Architecture Vision** | Define scope, business drivers, stakeholders | Vision statement, principles |
| **B: Business Architecture** | Map processes, capabilities, value streams | Capability map, process flows |
| **C: Information Systems** | Design data and application architecture | Data flows, app portfolio |
| **D: Technology Architecture** | Define infrastructure, platforms, standards | Technology stack, deployment model |
| **E: Opportunities & Solutions** | Identify projects and transition states | Roadmap, building blocks |
| **F: Migration Planning** | Sequence implementation | Migration plan, dependencies |
| **G: Implementation Governance** | Monitor conformance during build | Compliance reviews |
| **H: Change Management** | Manage architecture evolution | Change process, lessons learned |

### 1.2 Architecture Domains (MECE)
- **Business Architecture**: Capabilities, value streams, processes, organizational structures
- **Information Architecture**: Data entities, flows, governance, master data management
- **Application Architecture**: Application portfolio, interactions, interfaces, lifecycle
- **Technology Architecture**: Infrastructure, cloud, middleware, security controls

### 1.3 Architecture Governance
- **Architecture Review Board (ARB)**: Monthly — approve/reject decisions, manage exceptions
- **Technology Steering Committee**: Quarterly — portfolio prioritization, investment alignment
- **Architecture Exception Process**: Lightweight for minor deviations, formal for significant departures
- **Technology Radar**: Semi-annual updates — Adopt/Trial/Assess/Hold quadrants

## Section 2 — Application Architecture Patterns

### 2.1 Pattern Comparison Matrix

| Aspect | Monolith | Modular Monolith | Microservices | Serverless |
|--------|----------|------------------|---------------|-----------|
| Team Size | <50 | 50-200 | 200+ | Any |
| Scaling | Full app | Full app | Per service | Per function |
| Tech Diversity | None | Limited | High | Platform dependent |
| Operational Complexity | Low | Medium | High | Very Low |
| Deployment Frequency | Low | Medium | High | Very High |
| Data Consistency | Strong | Eventual | Eventual | Eventual |

### 2.2 Microservices Architecture
**When to use**: Large organizations (200+ engineers), diverse scaling requirements, high-frequency deployment needs.

Key implementation considerations:
- **Service granularity**: Balance between too fine-grained (overhead) and too coarse-grained (lacks benefits)
- **Database per service**: Each service owns its data — no shared databases
- **API contracts**: Semantic versioning and backward compatibility
- **Service mesh**: Cross-cutting concerns (traffic management, security, observability)
- **Communication**: Synchronous (REST/gRPC) for queries, Asynchronous (events) for commands

### 2.3 Strangler Fig Pattern for Migration
Incrementally replace legacy system components:
1. Identify highest-value, lowest-risk feature to extract
2. Build new service with that functionality
3. Deploy alongside legacy system
4. Route traffic gradually (10% → 25% → 50% → 100%)
5. Monitor metrics and rollback if issues
6. Repeat for next feature

### 2.4 Integration Patterns

**Event-Driven Architecture**: Services communicate via event streams. Loose coupling, natural audit trail, horizontal scaling. Challenges: eventual consistency, event versioning, ordering guarantees.

**CQRS (Command Query Responsibility Segregation)**: Separate read and write models. Independent scaling of read/write paths. Often combined with Event Sourcing.

**Event Sourcing**: Store all state changes as immutable events. Complete audit trail, temporal queries, replay capability. Challenges: storage growth, snapshot management, event versioning.

**Saga Pattern**: Distributed transactions across services — Choreography (services emit/react to events, no central coordinator) vs. Orchestration (central coordinator manages workflow). Orchestration preferred for payments due to clear workflow visibility and easier failure handling.

## Section 3 — Data Architecture

### 3.1 Data Mesh Principles
1. **Domain Ownership**: Data owned by domain teams, not central team
2. **Data as Product**: SLAs, versioning, documentation, discoverability
3. **Self-Serve Data Platform**: Central platform enables self-service provisioning
4. **Federated Governance**: Decentralized decisions, interoperability standards

### 3.2 Data Lake / Warehouse / Lakehouse

| Architecture | Schema | Best For | Technologies |
|-------------|--------|----------|-------------|
| **Data Lake** | Schema-on-read | Raw data, ML, diverse sources | S3, ADLS, GCS |
| **Data Warehouse** | Schema-on-write | BI, reporting, analytics | Snowflake, BigQuery, Redshift |
| **Lakehouse** | Hybrid | Unified analytics + ML | Delta Lake, Iceberg, Hudi |

### 3.3 Polyglot Persistence — Database Selection

| Type | Best For | Examples |
|------|----------|---------|
| **Relational** | Transactional, complex queries | PostgreSQL, Oracle |
| **Document** | Flexible schema, JSON data | MongoDB, Firestore |
| **Key-Value** | Caching, session storage | Redis, Memcached |
| **Graph** | Relationships, recommendations | Neo4j, ArangoDB |
| **Time-Series** | Metrics, events, logs | InfluxDB, TimescaleDB |
| **Columnar** | Analytics, OLAP | Snowflake, ClickHouse |
| **Vector** | Semantic search, ML | Pinecone, Weaviate |

## Section 4 — Cloud Architecture

### 4.1 Well-Architected Framework (5 Pillars)
1. **Operational Excellence**: IaC, monitoring, automated deployments
2. **Security**: Least privilege, encryption, network segmentation, compliance
3. **Reliability**: Multi-AZ/region, auto-scaling, fault isolation, chaos engineering
4. **Performance Efficiency**: Right-sizing, caching, CDN, serverless
5. **Cost Optimization**: Reserved instances, spot, right-sizing, usage monitoring

### 4.2 Cloud-Native Design (12-Factor App)
1. Codebase in version control | 2. Explicit dependencies | 3. Config in environment | 4. Backing services as resources | 5. Separate build/release/run | 6. Stateless processes | 7. Port binding | 8. Horizontal concurrency | 9. Fast startup, graceful shutdown | 10. Dev/prod parity | 11. Logs to stdout | 12. Admin as one-off processes

### 4.3 Containerization & Orchestration
- **Docker**: Small base images, multi-stage builds, non-root user, health checks
- **Kubernetes**: Declarative config, self-healing, auto-scaling, rolling/canary deployments
- **Service Mesh** (Istio/Linkerd): Traffic management, mTLS, observability, policy enforcement

### 4.4 Multi-Cloud & Hybrid Strategies
- **Multi-Cloud**: Avoid vendor lock-in, best-of-breed, cost optimization. Challenge: operational complexity, skill requirements
- **Hybrid**: Leverage existing on-premises, compliance/data residency. Challenge: network latency, data consistency
- **Abstraction**: Kubernetes as portable platform, IaC across clouds, cloud-agnostic tools

## Section 5 — API Strategy

### 5.1 API Styles Comparison

| Style | Protocol | Best For | Trade-offs |
|-------|----------|----------|-----------|
| **REST** | HTTP/JSON | Public APIs, CRUD, broad compatibility | Simple, cacheable, but over/under-fetching |
| **GraphQL** | HTTP/JSON | Client-driven queries, mobile | Flexible, but complex caching and rate limiting |
| **gRPC** | HTTP/2 + Protobuf | Service-to-service, high performance | Fast, type-safe, but limited browser support |
| **AsyncAPI** | Various (Kafka, AMQP) | Event-driven documentation | Protocol-agnostic, but lower maturity |

### 5.2 API Gateway & Management
- Request routing, protocol translation, rate limiting, auth, versioning, analytics
- Versioning strategies: URL path (most common), query parameter, header, content negotiation
- Deprecation: Sunset header, 6-12 month notice, migration guide

### 5.3 API Security
- **OAuth 2.0**: User authentication (authorization code flow)
- **API Keys**: Machine-to-machine (header-based, scoped, rotated)
- **mTLS**: Service-to-service (strongest, certificate management complexity)
- **Rate Limiting**: Token bucket, sliding window, leaky bucket

## Section 6 — Architecture for Payments

### 6.1 High-Availability Patterns
- **Circuit Breaker**: Closed → Open (failures ≥ threshold) → Half-Open (test recovery). Prevents cascading failures
- **Bulkhead**: Isolate resources per function (thread pools, connection pools). One failure doesn't affect others
- **Retry with Exponential Backoff + Jitter**: 100ms → 400ms → 1600ms. Idempotency keys critical for financial operations
- **Timeout Management**: Service < client timeout. Queue rejection when capacity exceeded

### 6.2 Real-Time vs. Batch Settlement

| Aspect | Real-Time Processing | Batch Settlement |
|--------|---------------------|-----------------|
| **Timing** | Milliseconds | End-of-day |
| **Use Cases** | Card auth, debit, ACH same-day | Wire transfers, international, ACH batches |
| **Architecture** | Gateway → Auth → Processor → Ledger → Fraud | Queue → Batch → Reconciliation → Clearing → Settlement |

**Hybrid approach**: Real-time authorization + real-time ledger + batch settlement/reconciliation

### 6.3 PCI-DSS Architecture
- Network segmentation, DMZ for payment processing
- Tokenization (never store raw card numbers)
- TLS 1.2+ for all transmissions
- Audit trails for all access to payment data (1-year retention)
- Compliant pattern: Customer → API Gateway/WAF → Payment Service (DMZ) → Tokenization → External Processor → Internal Ledger (encrypted, audited)

### 6.4 ISO 20022 & Payment Rails

| Rail | Format | Settlement | Volume/Cost |
|------|--------|-----------|-------------|
| **ACH (US)** | Nacha | 1-2 days | High volume, low cost |
| **RTP/FedNow (US)** | ISO 20022 | Immediate, 24/7 | Higher cost per txn |
| **Card Networks** | Proprietary | Auth real-time, settlement T+1 | Very high volume |
| **SWIFT** | MT/ISO 20022 | Multi-hop, days | High value, expensive |

### 6.5 Disaster Recovery

| RTO / RPO | 15 min RPO | 1 hour RPO | 4 hour RPO |
|-----------|-----------|-----------|-----------|
| **15 min RTO** | Active-Active | — | — |
| **1 hour RTO** | Active-Active | Active-Passive | Warm standby |
| **4 hour RTO** | Active-Passive | Active-Passive | Pilot Light |

## Section 7 — Architecture Decision Records (ADRs)

### ADR Template
```markdown
# ADR-NNNN: [Decision Title]

## Status: [Proposed / Accepted / Deprecated / Superseded by ADR-XXXX]

## Context
[Business drivers, technical constraints, current limitations, why now]

## Decision
[Chosen solution, clearly stated]

## Rationale
[Why this over alternatives, trade-offs considered, expected benefits]

## Consequences
- Positive: [benefits]
- Negative: [costs, risks]
- Mitigations: [how to address negatives]

## Alternatives Considered
- Option A: [why rejected]
- Option B: [why rejected]
```

## Section 8 — Architecture Benchmarks

- Microservices maturity: Level 0 (Monolithic) → Level 4 (Platform Engineering with 50+ services)
- API maturity (Richardson): Level 0 (RPC) → Level 3 (HATEOAS)
- Cloud-native maturity: Beginner (<50% containerized) → Expert (95%+ containerized, continuous deployment)
- API response targets: Tier 1 user-facing <100ms p50, Tier 2 internal <200ms, Tier 3 batch <5s
- Architecture review cadence: Monthly for critical systems, quarterly for principles review, annual full assessment

## Output Patterns

### Architecture Assessment
```
SYSTEM: [Name]
SCOPE: [What's being assessed]

CURRENT STATE:
- Pattern: [Monolith/Microservices/etc.]
- Technology: [Stack summary]
- Maturity: [Level against maturity model]

ASSESSMENT (by Well-Architected pillar):
1. Operational Excellence: [score/assessment]
2. Security: [score/assessment]
3. Reliability: [score/assessment]
4. Performance: [score/assessment]
5. Cost: [score/assessment]

STRENGTHS: [Top 3]
GAPS: [Top 3 with severity]

TECHNICAL DEBT:
- [Debt item] — [Impact: High/Med/Low] — [Effort: High/Med/Low]

RECOMMENDATIONS:
1. [Action] — [Pattern/framework] — [Timeline]

ADR: [Architecture Decision Record for key decisions]

CONFIDENCE: [High/Medium/Low]
```

### Migration Roadmap
```
FROM: [Current state]
TO: [Target state]
PATTERN: [Strangler Fig / Replatform / Rebuild / etc.]

PHASES:
- Phase 1 (0-6mo): [Foundation — what to do, expected value]
- Phase 2 (6-12mo): [Platform — what to do, expected value]
- Phase 3 (12-24mo): [Modernization — what to do, expected value]

DEPENDENCIES: [Critical path items]
RISKS: [Top 3 with mitigations]
INVESTMENT: [Resource/cost estimate per phase]
```

## Quality Checks

- [ ] Does the architecture recommendation reference specific patterns with trade-offs?
- [ ] Are TOGAF ADM phases applied where relevant?
- [ ] Is the recommendation aligned with cloud-native and 12-factor principles?
- [ ] Are non-functional requirements addressed (scalability, availability, security, performance)?
- [ ] Is an ADR template provided for key decisions?
- [ ] Are migration patterns practical (Strangler Fig, 6Rs)?
- [ ] Does the output consider payments-specific requirements (PCI-DSS, settlement, reconciliation)?
- [ ] Are API recommendations aligned with REST/GraphQL/gRPC best practices?
- [ ] Is technical debt assessment included with business impact quantification?
- [ ] Are sources and frameworks properly attributed?

---

**Confidence Calibration**: High confidence for established architecture patterns (microservices, CQRS, event sourcing), TOGAF framework, Well-Architected pillars, and PCI-DSS requirements. Medium confidence for emerging patterns (data mesh implementation details, serverless at enterprise scale). Low confidence for specific vendor roadmaps — recommend web search for latest cloud provider announcements.

**Triggers**: Activate when user needs architecture assessments, pattern selection, migration planning, API design guidance, payments architecture review, or architecture decision support for CIO conversations.
