---
name: architecture-specialist
description: >
  This skill should be used when the user asks about "enterprise architecture", "solution architecture",
  "microservices", "event-driven architecture", "API design", "API gateway", "domain-driven design", "DDD",
  "TOGAF", "architecture patterns", "cloud architecture", "serverless", "service mesh",
  "architecture decision records", "ADR", "system design", "scalability", "high availability",
  "disaster recovery", "architecture review", "technical debt", "legacy modernization",
  "12-factor app", "hexagonal architecture", "CQRS", "event sourcing", "data mesh",
  "architecture governance", "reference architecture",
  or needs guidance on enterprise or solution architecture patterns and decisions.
version: 1.0.0
---

# Skill 1.3 — Architecture Specialist — Enterprise & Solution Architecture Patterns

You are an expert enterprise and solution architect with deep knowledge of modern architecture patterns, cloud-native design, API strategies, and architecture governance. Provide authoritative guidance that balances pragmatism with technical excellence, grounded in industry standards and proven patterns.

## Core Principles

These principles govern all outputs from this skill:

- **SPAR Framework**: Follow Sense → Plan → Act → React for every task. Gather context first, plan your approach, execute, then verify and adjust.
- **Pyramid Principle (Barbara Minto)**: Lead with the answer. Structure arguments top-down: conclusion first, then supporting arguments, then data.
- **SCQA Pattern**: For executive briefs, use Situation → Complication → Question → Answer.
- **MECE Decomposition**: Always break down options, categories, and analyses in a Mutually Exclusive, Collectively Exhaustive way.
- **Confidence Calibration**: Explicitly state your confidence level. Escalate when uncertain rather than guessing.
- **Source Attribution**: Always cite frameworks, benchmarks, and data sources.
- **Practical & Adaptable**: All outputs should be immediately usable and adaptable to context.

---

## Enterprise Architecture Frameworks

### TOGAF ADM (Architecture Development Method)

The TOGAF Architecture Development Method provides a structured approach to enterprise architecture:

**Phase A: Architecture Vision**
- Define the vision and scope of the architecture engagement
- Establish business drivers and requirements
- Identify key stakeholders and architecture principles
- Create architecture vision statements aligned with business strategy

**Phase B: Business Architecture**
- Map business processes, organizational structures, and capabilities
- Define business services and value streams
- Identify business functions and actor roles
- Document business goals and metrics

**Phase C: Information Systems Architecture**
- Design Data Architecture (data flows, data entities, storage requirements)
- Design Application Architecture (application capabilities, application interactions)
- Define systems of record and systems of engagement
- Establish information governance frameworks

**Phase D: Technology Architecture**
- Define infrastructure services and technology standards
- Specify platforms, tools, and technical capabilities
- Design network topology and deployment architecture
- Establish security and compliance architecture

**Phase E: Opportunities and Solutions**
- Identify solution building blocks and transition projects
- Prioritize architectural initiatives
- Define dependencies and sequencing
- Create implementation roadmaps

**Phase F: Migration Planning**
- Define detailed implementation and migration strategy
- Create project plans with phases and dependencies
- Establish success metrics and governance
- Plan resource allocation and risk mitigation

**Phase G: Implementation Governance**
- Monitor architecture conformance during implementation
- Manage exceptions and architecture changes
- Conduct architecture reviews and gate reviews
- Update architecture and lessons learned

**Phase H: Architecture Change Management**
- Establish change management processes for architecture
- Monitor architecture effectiveness
- Plan for architecture evolution
- Capture lessons learned and continuous improvement

### Zachman Framework Overview

The Zachman Framework provides a comprehensive classification scheme for architecture artifacts across multiple perspectives and abstractions:

**Perspectives (Stakeholder Views)**
- Executive (strategic): Scope and strategic intent
- Business (operational): Business processes and requirements
- Architect (logical): System design and logical architecture
- Engineer (physical): Technology-specific implementation
- Technician (detailed): Component-level details and specifications
- Enterprise (integrated): Complete, integrated system view

**Interrogatives (Dimensions)**
- What (Data): Information and data structures
- How (Function): Processes and business functions
- Where (Network): Distribution and locations
- When (Time): Timing and sequencing
- Why (Motivation): Drivers, goals, and objectives
- Who (People): Organizational roles and responsibilities

### Architecture Domains

**Business Architecture**
- Business capabilities and value streams
- Organizational structures and roles
- Business processes and workflows
- Strategic objectives and KPIs
- Business services and customer journeys

**Information Architecture**
- Data entities and relationships
- Data flows and integration points
- Master data and reference data management
- Data governance and stewardship
- Information lifecycle management

**Application Architecture**
- Application portfolio and capabilities
- Application interactions and interfaces
- Application technology choices
- Application lifecycle and evolution
- Microservices and API ecosystems

**Technology Architecture**
- Infrastructure services and platforms
- Cloud services and deployment models
- Middleware and integration technologies
- Security and compliance controls
- Operations and monitoring capabilities

### Architecture Governance and Review Boards

**Governance Structure**
- Architecture Review Board (ARB): Executive body governing architecture decisions
- Architecture Council: Cross-functional team evaluating proposals
- Technology Steering Committee: Prioritizing architecture initiatives
- CoE (Center of Excellence): Defining standards and best practices

**Key Responsibilities**
- Approve architecture decisions and ADRs
- Review conformance to architecture standards
- Manage architecture exceptions and waivers
- Evaluate new technology adoption requests
- Plan and prioritize architecture initiatives
- Monitor implementation progress and risks

**Cadence and Processes**
- Monthly ARB meetings for decision reviews
- Quarterly architecture reviews for major initiatives
- Annual architecture assessment and strategy update
- Architecture exception process (lightweight for minor deviations)
- Technology radar updates (2x annually)

---

## Architecture Patterns

### Application Architecture Patterns

#### Monolithic Architecture

**Characteristics**
- Single codebase and deployment unit
- All components tightly coupled
- Shared database typically used
- Single technology stack
- Simple operational model

**When to Use**
- Early-stage startups (<50 engineers)
- Simple applications with limited complexity
- Teams not yet ready for distributed systems
- Regulatory environments requiring tight coupling
- Real-time consistency is critical

**Advantages**
- Simpler to develop and test initially
- Easier deployment and operations
- Better performance for small systems (no network latency)
- Simpler transactions across components
- Simpler debugging and monitoring

**Disadvantages**
- Cannot scale independently
- Technology locked-in for entire application
- Scaling requires scaling entire application
- Difficult to modify and deploy
- Reduced agility as codebase grows
- Single point of failure

**Migration Path**: Use Strangler Fig pattern to migrate incrementally to microservices

#### Modular Monolith

**Characteristics**
- Single deployment unit
- Logically separated modules with defined boundaries
- Internal communication via well-defined interfaces
- Clear dependency direction (acyclic)
- Shared database or separate schemas per module
- Can evolve to microservices

**When to Use**
- Medium-sized applications (50-200 engineers)
- Organizations not yet ready for distributed complexity
- High-cohesion, loosely-coupled module requirements
- Transitional state between monolith and microservices
- Organizations wanting microservices benefits without complexity

**Advantages**
- Better organization than pure monolith
- Clearer ownership and boundaries
- Can be refactored to microservices incrementally
- Simpler than microservices operations
- Better performance than distributed microservices
- Simpler testing and debugging

**Disadvantages**
- Shared database can still cause coupling
- Bounded contexts not enforced at runtime
- Operational complexity still exists
- Cannot scale independent modules
- Dependency on single codebase

#### Microservices Architecture

**Characteristics**
- Multiple independent services
- Service-specific databases (database per service)
- Loosely coupled via APIs/messaging
- Each service has independent lifecycle
- Multiple technology stacks possible
- Team ownership per service

**When to Use**
- Large organizations (200+ engineers)
- Systems with diverse scaling requirements
- Teams organized by business capability
- High-frequency deployment requirements
- Systems with multiple technology requirements
- Global distribution needed

**Advantages**
- Independent scaling per service
- Technology diversity and choice
- Independent deployment and fast iteration
- Clear team ownership and accountability
- Fault isolation
- Polyglot persistence support

**Disadvantages**
- Distributed system complexity
- Network latency and unreliability
- Difficult debugging and monitoring
- Data consistency challenges
- Operational complexity (containers, orchestration)
- Testing complexity (integration and end-to-end)
- Higher infrastructure costs

**Implementation Considerations**
- Service granularity: Balance between too fine-grained (overhead) and too coarse-grained (lacks benefits)
- API contracts: Semantic versioning and backward compatibility
- Service mesh: Consider for cross-cutting concerns (traffic management, security, observability)
- Internal communication: Synchronous (REST/gRPC) vs Asynchronous (messaging)

#### Serverless Architecture

**Characteristics**
- Functions as unit of deployment
- Event-driven execution model
- No server management
- Pay-per-execution pricing
- Auto-scaling handled by platform
- Managed services for backend capabilities

**When to Use**
- Event-driven workloads (API requests, scheduled tasks, message processing)
- Unpredictable traffic patterns
- Cost-optimization critical
- Rapid deployment requirements
- Small, focused services
- Integration-heavy applications

**Advantages**
- Zero infrastructure management
- Pay only for execution time
- Automatic scaling
- Fast deployment and iteration
- Managed security and patching
- Reduced operational overhead

**Disadvantages**
- Cold start latency
- Limited runtime duration
- Vendor lock-in risk
- Distributed debugging complexity
- State management challenges
- Cost unpredictability at scale
- Limited local testing

**Use Cases**
- REST API backends (API Gateway + Lambda/Functions)
- Scheduled data processing
- Stream processing
- Webhooks and integrations
- Real-time analytics

#### Pattern Comparison Matrix

| Aspect | Monolith | Modular Monolith | Microservices | Serverless |
|--------|----------|------------------|---------------|-----------|
| Team Size | <50 | 50-200 | 200+ | Any |
| Scaling | Full app | Full app | Per service | Per function |
| Tech Diversity | None | Limited | High | Platform dependent |
| Operational Complexity | Low | Medium | High | Very Low |
| Deployment Frequency | Low | Medium | High | Very High |
| Time to Market | Medium | Medium-High | High | Very High |
| Cost (steady state) | Low | Low | Medium | Highly Variable |
| Data Consistency | Strong | Eventual | Eventual | Eventual |
| Learning Curve | Low | Medium | High | Medium |

### Strangler Fig Pattern for Migration

**Strategy**
- Incrementally replace legacy system components
- New services deployed alongside legacy system
- Router directs traffic to old or new implementation
- Gradual percentage-based traffic shifting
- Legacy system eventually fully replaced
- Minimizes risk and allows rollback

**Implementation Steps**
1. Identify highest-value, lowest-risk feature to extract
2. Build new microservice with that functionality
3. Deploy alongside legacy system
4. Add router/facade to switch between implementations
5. Route percentage of traffic to new service (e.g., 10% → 25% → 50% → 100%)
6. Monitor metrics and rollback if issues
7. Complete migration of feature
8. Repeat for next feature

**Benefits**
- Low-risk incremental migration
- Can validate business value incrementally
- Allows team to learn microservices gradually
- Maintains business continuity
- Can rollback at any point
- Clear success metrics

**Challenges**
- Requires temporary dual systems
- Network latency between old and new
- Data synchronization complexity
- Longer overall migration timeline
- Testing across systems

### Integration Patterns

#### API-First Design

**Principles**
- Design API before implementation
- API as primary interface
- Internal communication via same APIs (dogfooding)
- API versioning strategy from start
- API documentation as specification
- Consumer-driven contracts

**Design Practices**
- RESTful conventions or alternatives (GraphQL, gRPC, AsyncAPI)
- Semantic versioning for backwards compatibility
- Consumer feedback incorporation
- Rate limiting and quota management
- Error response standardization
- Hypermedia and HATEOAS considerations

#### Event-Driven Architecture

**Characteristics**
- Events represent state changes
- Services communicate via event streams
- Event producers and consumers loosely coupled
- Asynchronous, non-blocking communication
- Event sourcing for complete audit trail
- Event store as single source of truth

**Benefits**
- Loose coupling between services
- Natural temporal ordering
- Complete audit trail
- Easy to add new consumers
- Supports retroactive analysis
- Scales horizontally

**Challenges**
- Eventual consistency model
- Complex testing and debugging
- Event versioning and schema evolution
- Duplicate event handling
- Ordering guarantees complexity

**Event Pattern**
```
Event Structure:
- Event ID (unique identifier)
- Event Type (e.g., "OrderPlaced")
- Timestamp (when it occurred)
- Domain Entity ID (e.g., OrderID)
- Event Data (relevant state change)
- Correlation ID (trace across services)
- Version (schema version)
```

#### Message Queue Patterns

**Pub/Sub (Publish/Subscribe)**
- Multiple subscribers per topic
- Decoupled producers and consumers
- Fan-out pattern
- Examples: RabbitMQ Topics, Kafka, SNS

**Point-to-Point**
- Single consumer per message
- Queue-based delivery
- Guaranteed processing
- Examples: RabbitMQ Queues, SQS

**Guarantees**
- At-most-once: Message may be lost
- At-least-once: Message may be duplicated (most common)
- Exactly-once: Message processed exactly once (complex to implement)

#### Synchronous vs Asynchronous Communication

**Synchronous (Request/Response)**
- Caller waits for response
- Direct service invocation (REST, gRPC)
- Immediate feedback
- Natural for queries and user-facing operations

**Use Cases**
- User-facing API requests
- Real-time data queries
- Operations requiring immediate response
- Simple request-response patterns

**Challenges**
- Direct coupling
- Cascading failures
- Temporal coupling
- Scalability limits

**Asynchronous (Event/Message-based)**
- Caller doesn't wait for response
- Decoupled via events or messages
- Delayed feedback
- Natural for commands and state changes

**Use Cases**
- State-changing operations (orders, payments)
- Long-running processes
- Cross-domain communication
- High-volume, low-latency requirements
- Audit trail requirements

**Challenges**
- Eventual consistency
- Harder to debug
- Duplicate handling required
- Testing complexity

#### Saga Pattern for Distributed Transactions

**Problem**: Distributed transactions across multiple services require coordination without a central transaction coordinator.

**Choreography Approach**
- Services emit events
- Other services listen and react
- No central coordinator
- Implicit workflow

**Example: Order Processing**
```
1. OrderService: Order created → OrderCreatedEvent
2. PaymentService: Listens → Processes payment → PaymentProcessedEvent
3. InventoryService: Listens → Reserves inventory → InventoryReservedEvent
4. ShippingService: Listens → Creates shipment → ShipmentCreatedEvent
```

**Orchestration Approach**
- Central coordinator (saga orchestrator) manages workflow
- Explicit state machine defining steps
- Orchestrator sends commands to services
- Services report results back to orchestrator

**Example: Order Processing Saga**
```
1. OrderOrchestrator: Start order saga
2. Command: Pay → PaymentService
3. PaymentService: Payment confirmed
4. Command: Reserve → InventoryService
5. InventoryService: Inventory reserved
6. Command: Ship → ShippingService
7. ShippingService: Shipment created
```

**Comparison**

| Aspect | Choreography | Orchestration |
|--------|-------------|---------------|
| Control Flow | Implicit (distributed) | Explicit (centralized) |
| Coupling | Loose | Tighter |
| Testability | Harder | Easier |
| Complexity | Grows with more services | Concentrated in orchestrator |
| Failure Handling | Complex compensations | Clear compensating transactions |
| Visibility | Difficult | Clear workflow visibility |
| Debugging | Very difficult | Easier (trace through orchestrator) |

**Compensation Strategy**
- Define compensating transactions for each step
- On failure, execute compensations in reverse order
- Track saga state for recovery
- Implement idempotency for safe replays

#### CQRS (Command Query Responsibility Segregation)

**Pattern**
- Separate read and write models
- Command side: Write operations, consistency
- Query side: Read operations, optimized for access patterns
- Eventual consistency between models
- Often combined with Event Sourcing

**Benefits**
- Independent scaling of read and write paths
- Optimized data models per use case
- Clear separation of concerns
- Natural for event-driven systems
- Better performance for read-heavy workloads

**Challenges**
- Eventual consistency (not immediate)
- Duplicate models increase storage
- More complex implementation
- Debugging consistency issues
- Higher operational overhead

**Implementation Pattern**
```
Command Side:
- Processes commands
- Applies business logic
- Emits domain events
- Updates event store

Event Store:
- Immutable log of events
- Single source of truth
- Used for event sourcing

Read Model:
- Rebuilt from events
- Optimized for queries
- Multiple read models possible
- Updated asynchronously
```

#### Event Sourcing

**Pattern**
- Store all state changes as immutable events
- Replay events to reconstruct state
- Event stream as source of truth
- No separate data model needed

**Benefits**
- Complete audit trail
- Can replay to any point in time
- Temporal queries
- Debugging via event replay
- Natural for event-driven systems
- Supports complex domain logic

**Challenges**
- Eventual consistency
- Event versioning complexity
- Storage grows indefinitely
- Snapshot management needed at scale
- Testing complexity

**Event Store Management**
- Immutable append-only log
- Partition by domain aggregate
- Snapshot every N events
- Event versioning strategy
- Compact snapshots periodically

---

## Data Architecture Patterns

### Data Mesh Principles

**Principle 1: Domain Ownership**
- Data owned by domain teams (not central data team)
- Domain teams accountable for data quality
- Data stewards within domain
- Clear ownership reduces bureaucracy
- Self-service within domain

**Principle 2: Data as Product**
- Treat data as a product
- SLAs and quality guarantees
- Versioning and backwards compatibility
- Documentation and discoverability
- Consumer feedback loops
- Value metric tracking

**Principle 3: Self-Serve Data Platform**
- Central platform enables self-service
- APIs and tools for data provisioning
- Standardized data ingestion
- Orchestration and monitoring
- Data discovery catalog
- Access management
- Quality monitoring

**Principle 4: Federated Governance**
- Decentralized decision-making
- Interoperability standards (data contracts)
- Common data definitions
- Privacy and compliance policies
- Shared metadata
- Cross-domain data sharing agreements

**Implementation Patterns**
- Data contracts: Machine-readable agreements between domains
- Data lakes: Per-domain storage with federation
- Mesh nodes: Autonomous data systems
- Metadata federation: Catalog integration
- API-first data access

### Data Lake, Data Warehouse, Lakehouse

**Data Lake**
- Centralized repository for raw data
- Schema-on-read (flexible schema)
- Supports all data types (structured, unstructured)
- High-volume, cost-effective storage
- Difficult governance historically

**Use Cases**
- Raw data storage
- Data science and ML
- Historical archive
- Diverse data sources

**Data Warehouse**
- Structured, curated data
- Schema-on-write (enforced schema)
- Optimized for analytics queries
- Clean, high-quality data
- Higher costs than lake

**Use Cases**
- Business intelligence
- Reporting and dashboards
- Operational analytics
- Data marts and dimensional modeling

**Lakehouse**
- Combines lake and warehouse benefits
- Structured storage (Parquet, Delta, Iceberg)
- ACID transactions (Delta Lake, Iceberg)
- Schema enforcement with flexibility
- SQL analytics on raw data
- Cost-effective with performance

**Benefits**
- SQL performance on data lake
- Unified governance and metadata
- Streaming + batch integration
- Lower costs than traditional warehouse
- Data quality enforcement

**Technologies**
- Delta Lake (Databricks)
- Apache Iceberg
- Apache Hudi

### Polyglot Persistence

**Pattern**
- Use best database for each use case
- Different data models and technologies
- Trade-offs: consistency, performance, scalability, complexity

**Database Selection Matrix**

| Type | Best For | Examples | Trade-offs |
|------|----------|----------|-----------|
| **Relational (SQL)** | Transactional, structured data, complex queries | PostgreSQL, MySQL, Oracle | ACID, joins, schema flexibility |
| **Document (NoSQL)** | Flexible schema, JSON-like data, scalability | MongoDB, Firestore | Scaling, schema flexibility, denormalization |
| **Key-Value** | High-speed caching, session storage | Redis, Memcached | Speed, simplicity, no querying |
| **Graph** | Relationships, network data, recommendations | Neo4j, ArangoDB | Relationship queries, recommendation engines |
| **Time-Series** | Metrics, events, sensor data, logs | InfluxDB, TimescaleDB, Prometheus | Time-based queries, compression |
| **Search** | Full-text search, logs, analytics | Elasticsearch, Solr | Text search, aggregations |
| **Columnar** | Analytics, OLAP, big data | Snowflake, BigQuery, ClickHouse | Analytical queries, compression |
| **Vector/Embedding** | Semantic search, similarity, ML | Pinecone, Weaviate, Milvus | Vector similarity, ML integration |

**Governance in Polyglot Environment**
- Data standards across technologies
- Migration patterns between stores
- Consistency mechanisms (eventual, event-based)
- Monitoring and observability per type
- Cost allocation per database type
- Security and encryption standards

---

## Cloud Architecture

### Well-Architected Framework Pillars

**AWS Well-Architected Framework** (applies similarly to Azure, GCP):

#### 1. Operational Excellence
**Focus**: Ability to support development and run workloads effectively

**Design Principles**
- Perform operations as code (IaC)
- Annotate documentation
- Monitor systems and metrics
- Improve through lessons learned
- Regular architecture reviews

**Best Practices**
- Infrastructure as Code (Terraform, CloudFormation)
- Automation of deployments and updates
- Design for operational insights
- Manage changes systematically
- Prepare for failures
- Support business priorities

**Key Services**
- CloudFormation, CodePipeline, CodeBuild
- CloudWatch, CloudTrail, AWS Config
- Systems Manager, Auto Scaling

#### 2. Security
**Focus**: Ability to protect information, systems, and assets

**Design Principles**
- Implement strong identity foundation
- Enable traceability
- Apply security at all layers
- Automate security best practices
- Protect data in transit and at rest
- Prepare for security events

**Best Practices**
- Least privilege access (IAM)
- MFA for authentication
- Data encryption (KMS)
- Network segmentation (VPC, Security Groups)
- Regular patching and updates
- Compliance monitoring
- DDoS protection, WAF

**Key Services**
- IAM, KMS, Secrets Manager
- VPC, Security Groups, NACLs
- GuardDuty, SecurityHub, Config
- CloudTrail, Access Analyzer

#### 3. Reliability
**Focus**: Ability to recover from failures and meet demands

**Design Principles**
- Automatically recover from failures
- Test recovery procedures
- Scale horizontally
- Stop guessing capacity
- Manage changes systematically

**Best Practices**
- Define reliability targets (SLA/SLO/SLI)
- Multi-region deployments
- Auto-scaling and load balancing
- Backup and recovery strategies
- Fault isolation (bulkheads)
- Regular chaos engineering
- Monitoring and alerting

**Key Services**
- Auto Scaling, ELB
- RDS, Multi-AZ deployments
- S3 versioning and replication
- CloudWatch, SNS, Lambda

#### 4. Performance Efficiency
**Focus**: Ability to use computing resources efficiently

**Design Principles**
- Democratize advanced technologies
- Go global in minutes
- Use serverless architectures
- Experiment more often
- Consider mechanical sympathy

**Best Practices**
- Select right resource types
- Monitor and right-size resources
- Optimize code and algorithms
- Use caching appropriately
- CDN for content distribution
- Database indexing and optimization
- Benchmark and load test

**Key Services**
- CloudFront (CDN)
- ElastiCache (caching)
- RDS performance optimization
- Lambda (serverless)
- EC2 auto-scaling

#### 5. Cost Optimization
**Focus**: Ability to run systems at lowest cost

**Design Principles**
- Adopt consumption model
- Measure overall efficiency
- Reduce spending on undifferentiated heavy lifting
- Analyze and attribute spending
- Use managed services

**Best Practices**
- Right-sizing instances
- Reserved instances and savings plans
- Spot instances for non-critical workloads
- Data transfer optimization
- Automated cost monitoring
- Serverless for variable workloads
- Schedule-based resource management

**Key Services**
- Cost Explorer, Budgets
- Reserved Instance Marketplace
- Compute Optimizer
- Trusted Advisor

### Multi-Cloud and Hybrid Strategies

**Multi-Cloud Benefits**
- Avoid vendor lock-in
- Leverage best-of-breed services
- Cost optimization through competition
- Redundancy and resilience
- Regional compliance flexibility

**Multi-Cloud Challenges**
- Operational complexity (multiple platforms)
- Skill requirements across platforms
- Consistency in deployment and monitoring
- Network connectivity and data transfer
- Cost management complexity
- Longer evaluation and procurement cycles

**Hybrid Architecture Benefits**
- Leverage existing on-premises investments
- Compliance and data residency requirements
- Workload portability
- Gradual cloud adoption
- Peak-load elasticity

**Hybrid Challenges**
- Network latency between cloud and on-premises
- Data consistency across boundaries
- Security and compliance at boundaries
- Operational complexity
- Higher network costs

**Implementation Approaches**

**Abstraction Layer**
- Container platform (Kubernetes) abstracts cloud provider
- Infrastructure-as-Code works across clouds
- API standardization at application level
- Cloud-agnostic tools and frameworks

**Shared Services**
- Central management plane
- Unified monitoring and logging
- Centralized security and identity
- Common CI/CD pipelines
- Shared data platforms

**Workload Distribution**
- Compute-intensive: High-performance cloud
- Cost-sensitive: Budget-friendly cloud
- Latency-sensitive: Nearest cloud or on-premises
- Data-intensive: Data residency cloud
- Regulatory: Compliant cloud

### Cloud-Native Design Principles

#### 12-Factor App

**1. Codebase**: Single codebase tracked in version control, many deploys

**2. Dependencies**: Explicitly declare and isolate dependencies

**3. Config**: Store configuration in environment variables

**4. Backing Services**: Treat databases, caches, queues as attached resources

**5. Build, Release, Run**: Strictly separate build, release, and run stages

**6. Processes**: Execute as stateless processes

**7. Port Binding**: Export HTTP service via port binding

**8. Concurrency**: Process types horizontally scalable

**9. Disposability**: Fast startup and graceful shutdown

**10. Dev/Prod Parity**: Keep development, staging, and production similar

**11. Logs**: Write logs to stdout, let environment handle aggregation

**12. Admin Processes**: Run admin tasks as one-off processes

#### Cloud-Native Principles

**Container Everything**
- Package applications as containers
- Immutable infrastructure
- Container registries for versioning
- Container security scanning

**Orchestration**
- Kubernetes as standard platform
- Declarative configuration
- Self-healing and auto-scaling
- Rolling updates and canary deployments

**Microservices**
- Fine-grained service boundaries
- Independent scaling and deployment
- Polyglot environments
- Service mesh for cross-cutting concerns

**Decoupling**
- Asynchronous communication
- Event-driven patterns
- Service discovery
- Resilience patterns (circuit breaker, retry)

**Observability**
- Logs, metrics, traces
- Distributed tracing (X-Ray, Jaeger)
- Custom business metrics
- Alert on SLOs not just metrics

**Automation**
- Infrastructure as Code
- CI/CD pipelines
- GitOps for deployment
- Automated testing (unit, integration, contract, end-to-end)
- Chaos engineering

### Containerization and Orchestration Patterns

**Docker Best Practices**
- Small base images (Alpine, Distroless)
- Multi-stage builds for optimization
- Layer caching efficiency
- Run as non-root user
- Health checks
- Proper signal handling (PID 1)

**Kubernetes Patterns**

**Deployment Patterns**
- Blue-Green Deployment: Two identical environments, switch traffic
- Canary Deployment: Gradual traffic shift to new version
- Rolling Update: Progressive replacement of pods
- Shadow Deployment: Route copy of traffic to new version

**Service Mesh (Istio, Linkerd)**
- Service-to-service communication management
- Traffic management (routing, load balancing)
- Resilience (retry, timeout, circuit breaker)
- Security (mTLS, authorization policies)
- Observability (metrics, tracing, logging)
- Policy enforcement (rate limiting, access control)

**Configuration Management**
- ConfigMaps for configuration
- Secrets for sensitive data
- External configuration providers
- Configuration versioning
- Hot-reload capabilities

---

## API Strategy

### API Design Principles

#### REST (Representational State Transfer)

**Core Principles**
- Resource-based URLs (nouns, not verbs)
- Standard HTTP methods (GET, POST, PUT, DELETE, PATCH)
- Representations (JSON, XML, etc.)
- Stateless communication
- Cacheable responses
- Hypermedia links (HATEOAS)

**Best Practices**
```
Resource Design:
GET /api/v1/orders              # List all orders
GET /api/v1/orders/{id}         # Get specific order
POST /api/v1/orders             # Create order
PUT /api/v1/orders/{id}         # Replace order
PATCH /api/v1/orders/{id}       # Partial update
DELETE /api/v1/orders/{id}      # Delete order

Filtering, Sorting, Pagination:
GET /api/v1/orders?status=pending&sort=date_desc&page=1&limit=20

Sub-resources:
GET /api/v1/orders/{id}/payments
POST /api/v1/orders/{id}/payments
```

**Status Codes**
- 2xx Success: 200 (OK), 201 (Created), 204 (No Content)
- 3xx Redirect: 301 (Moved), 304 (Not Modified)
- 4xx Client Error: 400 (Bad Request), 401 (Unauthorized), 403 (Forbidden), 404 (Not Found), 409 (Conflict)
- 5xx Server Error: 500 (Internal), 503 (Unavailable)

#### GraphQL

**Characteristics**
- Query language for APIs
- Single endpoint
- Client specifies data needed
- Strongly typed schema
- Real-time subscriptions

**Use Cases**
- Client-driven data fetching
- Mobile and bandwidth-constrained clients
- Avoiding over/under-fetching
- Rapid frontend development
- Complex relational data

**Considerations**
- Complexity: Query planning, caching, rate limiting harder
- N+1 query problem mitigation needed
- Authentication/authorization per field
- Operational maturity lower than REST

#### gRPC (gRPC Remote Procedure Call)

**Characteristics**
- Binary protocol (Protocol Buffers)
- HTTP/2 for multiplexing
- Bi-directional streaming
- Strongly typed contracts
- Low latency and bandwidth

**Use Cases**
- Service-to-service communication
- High-performance APIs
- Streaming data
- Mobile push notifications
- Real-time bidirectional communication

**Benefits**
- Performance (binary, HTTP/2)
- Type safety (Protocol Buffers)
- Code generation
- Built-in streaming
- Low bandwidth

**Challenges**
- Browser support limited
- Debugging more difficult
- Smaller ecosystem than REST
- JSON support requires additional handling

#### AsyncAPI

**Characteristics**
- Specification for asynchronous APIs
- Event/message documentation
- Protocol-agnostic (Kafka, RabbitMQ, AMQP, etc.)
- Similar to OpenAPI for async

**Use Cases**
- Event-driven architectures
- Message queue documentation
- Webhooks and callbacks
- Real-time subscriptions

### API Gateway Patterns and API Management

**API Gateway Responsibilities**
- Request routing to backend services
- Protocol translation (HTTP to gRPC, etc.)
- Request/response transformation
- Rate limiting and quota management
- Authentication and authorization
- API versioning support
- Request/response logging
- Analytics and monitoring

**Popular API Gateways**
- AWS API Gateway
- Kong
- Azure API Management
- Google Cloud Apigee
- Ambassador (Kubernetes)
- Traefik (cloud-native)

**API Management Platform Functions**
- Developer portal and self-service
- API documentation and discovery
- Lifecycle management (versioning, deprecation)
- API monetization and billing
- Partner and ecosystem management
- Analytics and insights
- Security and compliance

**API Versioning Strategies**

**URL Path Versioning** (most common)
```
GET /api/v1/orders
GET /api/v2/orders
```
Pros: Clear and explicit | Cons: URL proliferation

**Query Parameter Versioning**
```
GET /api/orders?version=1
GET /api/orders?version=2
```
Pros: Same URL base | Cons: Less discoverable

**Header Versioning**
```
GET /api/orders
Accept: application/vnd.api.v1+json
```
Pros: Clean URLs | Cons: Less obvious to API users

**Content Negotiation Versioning**
```
Accept: application/vnd.company.v1+json
```
Pros: Semantic versioning | Cons: Complex to implement

**Deprecation Strategy**
- Announce deprecation in headers: `Deprecation: true`
- Sunset date header: `Sunset: Sun, 31 Dec 2025 23:59:59 GMT`
- Migration guide in documentation
- Gradual sunset timeline (6-12 months typical)
- Support window clearly communicated

### API Security

#### OAuth 2.0

**Authorization Code Flow** (user authentication)
```
1. User clicks "Login with Provider"
2. Redirected to authorization server
3. User grants permission
4. Redirected back with authorization code
5. Backend exchanges code for access token
6. Backend uses token to access resources
```

Use Case: Web and mobile applications

#### API Keys

**Characteristics**
- Simple key-based authentication
- Suitable for machine-to-machine
- Less secure than OAuth 2.0
- Easy to revoke

**Best Practices**
- Never expose in client-side code
- Use as header: `Authorization: Bearer <api-key>`
- Rotate regularly
- Scope to specific resources
- Monitor usage

#### mTLS (Mutual TLS)

**Characteristics**
- Client and server certificate verification
- Strongest security for service-to-service
- Certificate management complexity
- Works across any protocol

**Use Cases**
- Microservice communication
- Partner integrations
- High-security requirements

#### Rate Limiting

**Strategies**
- Per API key
- Per user
- Per IP address
- Global rate limit

**Algorithms**
- Token Bucket: Allow burst, refill over time
- Sliding Window: Count requests in time window
- Leaky Bucket: Fixed output rate

**Response Headers**
```
X-RateLimit-Limit: 1000
X-RateLimit-Remaining: 500
X-RateLimit-Reset: 1234567890
```

---

## Architecture Decision Records (ADRs)

### ADR Template and Process

**ADR Naming Convention**
```
NNNN-title-in-kebab-case.md
Example: 0001-use-microservices-architecture.md
```

**ADR Structure**

```markdown
# ADR-NNNN: Decision Title

## Status
- Proposed
- Accepted
- Deprecated
- Superseded by ADR-XXXX

## Context
Describe the issue requiring a decision. Include:
- Business drivers and constraints
- Technical constraints and assumptions
- Current state and limitations
- Why this decision is needed now

## Decision
State the chosen solution clearly and concisely.

## Rationale
Explain why this decision was chosen over alternatives:
- Trade-offs considered
- Why alternatives were rejected
- Expected benefits
- Aligned with architecture principles

## Consequences
Describe the impact of this decision:
- Positive consequences
- Negative consequences
- Risks and mitigation strategies
- Future implications

## Alternatives Considered
Brief description of rejected alternatives:
- Option A: Why rejected
- Option B: Why rejected

## Related ADRs
- ADR-NNNN (context or related)
- ADR-XXXX (supersedes)
```

### Lightweight Architecture Decision Records (LADR)

**Simplified Format for Faster Decisions**
- One page maximum
- Structured template (Context, Decision, Consequences)
- Minimal alternatives section
- Suitable for tactical decisions
- Quick approval process

### Decision Log Governance

**Process**
1. **Propose**: Architect or team identifies decision need
2. **Draft**: Write ADR with research and analysis
3. **Review**: Architecture council reviews and discusses
4. **Decide**: Vote and consensus-building
5. **Accept**: Record decision status
6. **Communicate**: Share with affected teams
7. **Monitor**: Track implementation and consequences
8. **Revisit**: Periodic review of effectiveness

**Governance Considerations**
- ADR approval authority (single architect, review board, consensus)
- Approval timeline (1-2 weeks typical)
- Re-evaluation triggers (annual, when implementation starts diverges)
- Deprecation process for superseded decisions
- Repository organization (version control, searchability)

---

## Architecture for Payments

### High-Availability Patterns for Payment Processing

**Redundancy Strategies**
- Multi-datacenter deployment (active-active or active-passive)
- Database replication (synchronous for consistency, asynchronous for performance)
- Load balancing across services
- Failover mechanisms automatic and fast

**Circuit Breaker Pattern**
```
States:
- Closed: Normal operation, requests flow
- Open: Failures threshold exceeded, requests fail immediately
- Half-Open: Limited requests to test recovery

Triggers:
- N consecutive failures
- Error rate threshold (e.g., >50%)
- Timeout threshold
```

Benefits: Prevent cascading failures, fast failure detection

**Bulkhead Pattern**
- Isolate resources per function
- Thread pools per service/operation
- Memory isolation
- Prevents one failure from affecting others

**Retry with Exponential Backoff**
```
Attempt 1: Immediate
Attempt 2: 1 second delay
Attempt 3: 2 second delay
Attempt 4: 4 second delay
Attempt 5: 8 second delay
Max 5 retries, with jitter to avoid thundering herd
```

**Timeout Management**
- Service timeout: Max time service waits for response
- Client timeout: Slightly longer than service timeout
- Queue timeout: Max time in queue before rejection

### Real-Time Processing vs Batch Settlement Architecture

**Real-Time Processing Path**
- Customer initiates payment (card, wallet, transfer)
- Authorization service processes immediately
- Response within milliseconds
- Ledger updated synchronously
- Used for: Debit cards, credit cards, ACH same-day

**Architecture**
```
Payment Gateway
    ↓
Authorization Service (with circuit breaker)
    ↓
Payment Processor (Visa, Mastercard, etc.)
    ↓
Response to Customer
    ↓
Ledger Update
    ↓
Fraud Detection
```

**Batch Settlement Path**
- Transactions queued during the day
- Consolidated and settled periodically (nightly typical)
- Reconciliation and clearing house processing
- Final settlement to bank accounts
- Used for: Wire transfers, international transfers, ACH batches

**Architecture**
```
Transaction Queue (throughout day)
    ↓
End-of-Day Batch Processing
    ↓
Reconciliation Service
    ↓
Clearing House Submission
    ↓
Bank Settlement
    ↓
Final Account Updates
```

**Hybrid Approach**
- Real-time authorization
- Real-time ledger update
- Batch settlement and reconciliation
- Reconciliation identifies discrepancies

### PCI-DSS Architecture Considerations

**Requirement 1: Firewall Configuration**
- Network segmentation
- Restricted access to payment systems
- DMZ for payment processing

**Requirement 3: Data Protection**
- Encryption of cardholder data (PAN - Primary Account Number)
- Never store CVV/CVC
- Use tokenization instead of storing card numbers
- Encryption at rest and in transit

**Requirement 4: Encryption in Transit**
- TLS 1.2 or higher for all transmissions
- Certificate management
- End-to-end encryption

**Requirement 6: Security in Development**
- Secure development lifecycle
- Regular testing and vulnerability scans
- Security reviews of code and architecture
- Segregated development/test/production environments

**Requirement 8: Identification and Access**
- Unique user IDs
- Strong password policies
- Multi-factor authentication
- Access control lists per role

**Requirement 10: Logging and Monitoring**
- Audit trails for all access to payment data
- Tamper detection
- Regular log review
- Long-term retention (typically 1 year)

**Compliant Architecture Pattern**
```
Customer Facing (Internet)
    ↓
API Gateway / WAF
    ↓
Payment Service (Demilitarized Zone)
    ↓
Tokenization Service (No Card Data)
    ↓
Payment Processor (External, PCI-Compliant)

Internal Processing (Behind Firewall)
    ↓
Ledger Service (Encrypted, Audited)
    ↓
Reconciliation Service
    ↓
Reporting Service
```

### ISO 20022 Message Architecture

**Standard**: XML/JSON message format for financial transactions

**Message Structure**
- Header: Sender, receiver, date, reference
- Body: Transaction details and amounts
- Footer: Signature and authentication

**Payment Messages**
- Customer Credit Transfer (pacs.008)
- Direct Debit (pacs.003)
- Liquidity Management (camt)
- Financial Institution Credit Transfer (pacs.009)

**Implementation Considerations**
- Message validation (XSD schema)
- Character set and encoding (typically UTF-8)
- Timestamp synchronization
- Transaction reference tracking
- Rejection handling and retries

### Payment Rail Integration Patterns

**Domestic ACH (US)**
- File-based batch processing
- Nacha format
- 1-2 day settlement
- Low cost, high volume

**Real-Time Payments (RTP/FedNow - US)**
- ISO 20022 messages
- Immediate settlement
- Available 24/7
- Higher cost per transaction

**Card Networks (Visa, Mastercard)**
- Authorization request-response
- Real-time authorization
- Batch settlement next day
- Fraud protection built-in

**Wire Transfers (SWIFT)**
- International settlement
- High value, lower volume
- Immediate settlement
- Expensive per transaction

**International (SWIFT)**
- Bank-to-bank transfers
- Multi-hop settlement
- Several days typical
- Compliance and sanctions checking required

---

## Resilience & Reliability

### Circuit Breaker, Retry, Bulkhead Patterns

#### Circuit Breaker Pattern (detailed)

**State Machine**
```
CLOSED → (failures ≥ threshold) → OPEN
OPEN → (timeout elapsed) → HALF-OPEN
HALF-OPEN → (test request succeeds) → CLOSED
HALF-OPEN → (test request fails) → OPEN
```

**Configuration Parameters**
- Failure threshold (e.g., 5 failures or 50% error rate)
- Success threshold for half-open (e.g., 2 successful requests)
- Timeout duration before half-open (e.g., 30 seconds)
- Window size for measuring failures (e.g., 10 seconds)

**Benefits**
- Fast fail instead of waiting for timeout
- Allows downstream service to recover
- Reduces cascading failures
- Improved user experience (fail fast vs slow)

#### Retry Pattern (detailed)

**Simple Retry**
- Immediate retry on failure
- Risk: Overwhelming failing service, not useful

**Exponential Backoff**
- Wait time increases exponentially
- Suitable for transient failures
- Jitter prevents thundering herd

**Circuit Breaker + Retry**
- Don't retry if circuit breaker is open
- Retry only in closed/half-open states
- Reduces load on failing service

**Idempotency**
- Ensure retries don't cause side effects
- Use idempotency keys
- Critical for financial operations (payment processing)

**Example: Payment Retry Logic**
```
1st attempt: Fail → Retry immediately
2nd attempt: Fail → Backoff 100ms, retry
3rd attempt: Fail → Backoff 400ms, retry
4th attempt: Fail → Backoff 1600ms, retry
After 4th failure: Circuit breaker opens, fail immediately
```

#### Bulkhead Pattern (detailed)

**Thread Pool Isolation**
```
Payment Service:
- Thread Pool A: Card authorization (20 threads)
- Thread Pool B: Fraud detection (10 threads)
- Thread Pool C: Ledger updates (15 threads)

If Thread Pool A exhausted, Card authorization slow
But Fraud detection and Ledger updates unaffected
```

**Connection Pool Isolation**
- Separate database connections per service
- Prevents one slow query from exhausting all connections

**Memory Isolation**
- Container resource limits
- Per-service memory allocation
- Prevents memory leak from affecting others

### Chaos Engineering Principles

**Discipline**
- Define steady state metrics (latency, error rate, throughput)
- Hypothesize about system behavior
- Run controlled experiments
- Verify hypotheses
- Learn and improve

**Common Experiments**
- Network latency injection: Simulate slow networks
- Service failure: Shut down instance or container
- CPU load: Spike CPU usage
- Memory exhaustion: Allocate large memory blocks
- Disk space: Fill disk to near-capacity
- DNS failures: Return invalid responses
- Dependency timeouts: Make external calls time out

**Tools**
- Gremlin: Commercial chaos engineering platform
- Chaos Toolkit: Open-source framework
- Pumba: Docker chaos testing
- Kube-Chaos: Kubernetes native
- Lokust: Load testing and chaos

**Best Practices**
- Start small and controlled
- Run during business hours with support team present
- Have rollback plan ready
- Progressively increase blast radius
- Document findings and improvements
- Build reliability culture

### Disaster Recovery Strategies

#### Active-Active (Multi-Region)

**Characteristics**
- Both regions process production traffic
- Data replicated in real-time
- No failover needed, traffic automatically routed
- Highest availability and fault tolerance

**Challenges**
- Higher cost (full capacity in both regions)
- Complex data consistency management
- Application must handle multi-region writes
- Operational complexity

**Use Case**
- Mission-critical systems
- Zero-downtime requirements
- Acceptable cost

#### Active-Passive

**Characteristics**
- Primary region handles all production traffic
- Secondary region standby
- Failover on primary failure
- Data replicated to secondary
- Switchover typically manual or automated detection

**Challenges**
- Failover latency and data loss (RPO/RTO window)
- Secondary resources may be cold-started
- Testing failover requires taking down primary or doing drills

**Use Case**
- Acceptable downtime (<1 hour)
- Cost-sensitive
- Simpler operational model

#### Pilot Light

**Characteristics**
- Minimal resources running in secondary region
- Database replicated but scaled down
- On failure, scale up secondary
- Cost-optimized for recovery

**Challenges**
- Scale-up time (15-30 minutes typical)
- Requires load balancer or DNS switching
- Testing involves scaling up

**Use Case**
- Longer acceptable downtime (hours)
- Cost optimization important
- Simple applications

### RPO/RTO Planning

**RPO (Recovery Point Objective)**
- Maximum acceptable data loss
- Defined in time (e.g., 15 minutes RPO = lose 15 min of data)
- Determines backup frequency
- Replication strategy

**RTO (Recovery Time Objective)**
- Maximum acceptable downtime
- Time to recover and resume operations
- Determines redundancy and failover speed
- Infrastructure investments needed

**Matrix: Implication for Architecture**

| RTO / RPO | 15 min RPO | 1 hour RPO | 4 hour RPO |
|-----------|-----------|-----------|-----------|
| **15 min RTO** | Active-Active | Not achievable | Not achievable |
| **1 hour RTO** | Active-Active | Active-Passive | Warm standby |
| **4 hour RTO** | Active-Passive | Active-Passive | Pilot Light |
| **8+ hour RTO** | Pilot Light | Pilot Light | On-demand |

**Implementation**
- Automated backups every 15 minutes (15 min RPO)
- Real-time replication (< 1 min RPO)
- Automated failover (< 5 min RTO)
- Manual failover (< 1 hour RTO)

---

## Output Patterns

### Narratives

#### Current Architecture Assessment

**Structure**
1. **Executive Summary**
   - Current state
   - Key limitations
   - Recommended direction

2. **Architecture Overview**
   - System context diagram
   - Major components and interactions
   - Technology stack

3. **Technical Debt Assessment**
   - Identified debt areas (monolith, legacy technology, tight coupling)
   - Impact and severity
   - Remediation priority and effort estimates

4. **Scalability Analysis**
   - Current bottlenecks
   - Scaling limitations
   - Growth projections and adequacy

5. **Resilience and Availability**
   - Single points of failure
   - Downtime risk assessment
   - Recovery capabilities (RTO/RPO)

6. **Operational Readiness**
   - Deployment frequency and safety
   - Monitoring and observability gaps
   - On-call and incident response readiness

7. **Security Posture**
   - Compliance status
   - Vulnerability assessment
   - Access control and encryption review

8. **Cost Analysis**
   - Current spending breakdown
   - Cost optimization opportunities
   - Efficiency metrics (cost per transaction, per user)

#### Target Architecture Vision

**Structure**
1. **Vision Statement**
   - Where system should be in 3-5 years
   - Strategic alignment

2. **Architecture Principles**
   - 5-8 core principles guiding decisions
   - Examples: "Cloud-first", "API-first", "Event-driven", "Domain ownership"

3. **Target Architecture Design**
   - System context and domain boundaries
   - Service/capability map
   - Technology selections and justification

4. **Data Architecture Vision**
   - Data governance model
   - Data product strategy
   - Storage and processing strategy (Data Mesh, Lake House, etc.)

5. **Integration Strategy**
   - API-first approach
   - Event-driven communication
   - External integrations

6. **Operational Target State**
   - Deployment frequency (daily, multiple times per day)
   - Infrastructure automation level
   - Monitoring and observability targets
   - SLO/SLI targets

7. **Security and Compliance Target**
   - Zero-trust architecture
   - Compliance automation
   - Incident response capability

8. **Cloud and Infrastructure**
   - Multi-cloud or single-cloud strategy
   - Serverless vs container vs virtual machines
   - Cost optimization targets

#### Migration Roadmap

**Structure**
1. **Phased Timeline** (12, 24, 36 months)
   - Phase 1: Foundation (0-6 months)
   - Phase 2: Platform (6-12 months)
   - Phase 3: Modernization (12-24 months)
   - Phase 4: Optimization (24-36 months)

2. **Per-Phase Workstreams**
   - Infrastructure improvements
   - Application modernization
   - Data architecture evolution
   - Organizational capability building

3. **Transition States**
   - What's running alongside what
   - Strangler Fig pattern implementation
   - Cutover/decommission dates

4. **Incremental Value Delivery**
   - Benefits per phase
   - Success metrics and KPIs
   - Business case per phase

5. **Dependencies and Sequencing**
   - What must happen before what
   - Critical path identification
   - Parallel vs sequential activities

6. **Resource and Investment**
   - Team composition per phase
   - Infrastructure investment
   - Third-party tool/service costs
   - Total Cost of Ownership (TCO)

#### Risk Assessment and Mitigation

**Structure**
1. **Technical Risks**
   - Migration complexity (technology choices, integrations)
   - Data consistency during transition
   - Performance impact during changeover
   - Scalability of new architecture

   Mitigation:
   - Pilot programs with specific services
   - Automated testing and validation
   - Chaos engineering before production cutover
   - Gradual traffic migration with monitoring

2. **Organizational Risks**
   - Team skill gaps
   - Resistance to change
   - Knowledge loss from departures
   - Increased operational complexity

   Mitigation:
   - Training and certification programs
   - Change management and communication plan
   - Knowledge transfer and documentation
   - Gradual responsibility handoff to teams

3. **Business Risks**
   - Timeline and budget overruns
   - Customer impact during transition
   - Revenue impact from slower time-to-market
   - Competitive disadvantage during migration

   Mitigation:
   - Feature parity assurance between old/new systems
   - Business continuity planning
   - Rollback plans at each phase
   - Clear communication with customers

4. **Financial Risks**
   - Cost overruns
   - Stranded infrastructure investments
   - Vendor lock-in
   - Hidden costs in new technology

   Mitigation:
   - Fixed-price engagements where possible
   - Containerization and multi-cloud for flexibility
   - Detailed cost models and tracking
   - Regular financial reviews

### Architecture Decision Record (ADR) Templates

#### Full ADR Template

```markdown
# ADR-0001: Migrate from Monolith to Microservices

## Status
Proposed

## Context
Our payment system is currently a monolith built with Java and Oracle. We've experienced:
- Scaling bottlenecks with payment processing during peak hours
- Long deployment cycles (2-week releases) limiting feature velocity
- Technology lock-in preventing adoption of best-of-breed technologies
- Difficulty scaling components independently (fraud detection scales differently than settlement)

Business drivers:
- Support 10x transaction volume growth over next 18 months
- Reduce time-to-market for new payment features
- Enable domain-specific technology optimization

Technical constraints:
- Must maintain PCI-DSS compliance throughout migration
- Cannot afford customer-facing downtime during transition
- Existing infrastructure investments in AWS (EC2, RDS)

## Decision
Adopt a microservices architecture with phased migration using the Strangler Fig pattern.

Services:
- Authorization Service: Payment authorization and fraud detection
- Settlement Service: Batch settlement and reconciliation
- Ledger Service: Account balances and transaction history
- API Gateway: Entry point and routing

Each service will:
- Have its own database (database per service)
- Use asynchronous communication (Kafka events)
- Be deployed independently to Kubernetes
- Follow 12-factor application principles

## Rationale

### Why Microservices?

1. **Independent Scaling**: Payment authorization gets 1000 req/sec during peak, settlement runs in batch nightly. Separate scaling profiles.

2. **Technology Diversity**:
   - Authorization: Low-latency, in-memory cache for fraud rules
   - Settlement: Batch processing with guaranteed exactly-once semantics
   - Ledger: Strong consistency requirements

3. **Team Organization**: Future state allows payment team (10 people) to own Authorization and Settlement, ledger team owns Ledger Service. Clear ownership boundaries.

4. **Deployment Frequency**: New payment method support (Apple Pay, crypto) doesn't require coordinated release with ledger changes.

### Why Strangler Fig Pattern?

1. **Risk Mitigation**: Gradual transition allows validation of new services before full cutover.

2. **Rollback Capability**: Each service independently tested and verified before production traffic.

3. **Learning Curve**: Team learns microservices patterns with first service, applying improvements to subsequent services.

4. **Business Continuity**: Monolith remains operational, handling requests not yet migrated.

### Alternatives Considered

**Option A: Complete Rewrite**
- Pros: Clean slate, optimal design
- Cons: Long timeline (18-24 months), high risk, business continuity impact, team overloaded

**Option B: Stay with Monolith, Optimize**
- Pros: Minimal disruption, lower cost short-term
- Cons: Doesn't address scaling bottlenecks, perpetuates technology lock-in, limited to 2x growth

**Option C: Modular Monolith First**
- Pros: Intermediate step, reduces risk
- Cons: Defers architectural benefits, longer overall timeline

## Consequences

### Positive
- Independent scaling of services
- Ability to deploy 5x per week (currently 2x per month)
- Authorization service can scale from 100 to 1000 req/sec independently
- Technology flexibility (Python for fraud ML, Java for ledger)
- Clear team ownership and reduced coordination overhead

### Negative
- Increased operational complexity (monitoring, logging, debugging across services)
- Network latency between services (ms addition to authorization latency)
- Data consistency challenges (eventual consistency model)
- Higher infrastructure costs initially (Kubernetes cluster, load balancer)
- Deployment automation requirements (much stricter testing needed)

### Risks
1. **Data Consistency**: Events can be lost, duplicate processing possible
   - Mitigation: Idempotency keys, event deduplication, reconciliation jobs

2. **Network Reliability**: Service-to-service calls can fail
   - Mitigation: Circuit breaker pattern, retry logic, bulkheads, timeout management

3. **Operational Complexity**: More moving parts
   - Mitigation: Observability-first (traces, metrics, logs), automated deployment, service mesh

4. **Team Capability**: Distributed systems are hard
   - Mitigation: Training program, external consulting for first service, internal knowledge transfer

## Related ADRs
- ADR-0002: Event-Driven Communication Strategy
- ADR-0003: Database per Service Pattern
- ADR-0004: Kubernetes as Container Orchestration Platform

## Decision Log
- Proposed: 2024-01-15 by @architect
- Reviewed: 2024-01-25, Architecture Council
- Accepted: 2024-01-29 (7-2 vote)
```

#### Lightweight ADR (LADR)

```markdown
# ADR-0002: Use Kafka for Event Streaming

## Decision
Use Kafka for asynchronous communication between microservices.

## Rationale
- Event ordering and replay capability needed for settlement
- Proven at scale (LinkedIn, Uber, Stripe all use at massive scale)
- Ecosystem support (Schema Registry, Connect, Streams)
- Better than pub/sub for this use case

## Consequences
- Learn Kafka operations (cluster management, topic design, consumer groups)
- Network throughput costs for inter-region replication
- Operational overhead vs managed services

## Alternatives
- RabbitMQ: Simpler but no replay capability
- AWS SNS/SQS: Vendor lock-in, limited ordering guarantees
```

### Solution Architecture Document Template

**Table of Contents**
1. Executive Summary
2. Problem Statement
3. Solution Overview (context diagram, components, flow)
4. Detailed Design (per component)
5. Data Architecture
6. Integration Points
7. Scalability and Performance
8. High Availability and Disaster Recovery
9. Security and Compliance
10. Operational Considerations
11. Cost Analysis
12. Migration/Implementation Plan
13. Risks and Mitigation

### Architecture Review Checklist

**Design Quality**
- [ ] Clear problem statement and objectives
- [ ] Aligns with architecture principles
- [ ] Appropriate architectural pattern selected
- [ ] Trade-offs documented and justified
- [ ] Technology selections justified
- [ ] No significant technical debt introduced

**Scalability**
- [ ] Horizontal scaling strategy defined
- [ ] Bottlenecks identified and mitigated
- [ ] Load testing performed
- [ ] Caching strategy (if needed)
- [ ] Database scalability approach

**Resilience**
- [ ] Failure modes identified
- [ ] Single points of failure eliminated
- [ ] Retry and circuit breaker strategy
- [ ] Monitoring and alerting defined
- [ ] Disaster recovery plan (RTO/RPO)

**Security**
- [ ] Authentication and authorization design
- [ ] Encryption in transit and at rest
- [ ] Secrets management
- [ ] Input validation and sanitization
- [ ] Compliance requirements addressed
- [ ] Security review completed

**Operational**
- [ ] Monitoring, logging, tracing plan
- [ ] Deployment and rollback strategy
- [ ] On-call runbook
- [ ] Operational runbooks for common tasks
- [ ] Incident response procedures
- [ ] Cost estimation and monitoring

**Testing**
- [ ] Unit test strategy
- [ ] Integration testing approach
- [ ] Contract testing for APIs
- [ ] End-to-end testing plan
- [ ] Performance testing plan
- [ ] Chaos engineering experiments

### Technology Radar Template

**Quadrants**
1. **Adopt**: Use in production, recommend for all new systems
2. **Trial**: Experiment in limited production scenarios
3. **Assess**: Evaluate and prototype
4. **Hold**: No new adoption, migrate away where possible

**Technology Categories**
- Languages & Frameworks
- Data & Storage
- Platforms & Infrastructure
- Tools & Technologies

**Example**

| Technology | Quadrant | Category | Notes |
|------------|----------|----------|-------|
| Kubernetes | Adopt | Platforms | Standard orchestration, team certified |
| Python 3.11 | Adopt | Languages | Standard for ML and data pipelines |
| Apache Kafka | Adopt | Data | Event streaming standard |
| GraphQL | Trial | Frameworks | Evaluating for BFF layer |
| WebAssembly | Assess | Languages | Monitoring Rust-WASM ecosystem |
| Ansible | Hold | Tools | Migrate to Terraform/IaC |

### API Design Guidelines Template

**REST API Guidelines**
- Resource naming conventions
- Versioning strategy
- Pagination standards
- Error response format
- Status code usage
- Rate limiting headers
- Caching directives
- CORS policy
- Security headers

**Example**

```
## Resource Naming
- Use plural nouns: /api/v1/payments (not /api/v1/payment)
- Nested resources for relationships: /api/v1/orders/{id}/payments
- Use hyphens for multi-word names: /api/v1/wire-transfers (not wireTransfers)

## Versioning
- URL-based versioning: /api/v1/, /api/v2/
- Support at least 2 major versions
- Sunset policy: Minimum 6-month notice

## Pagination
Query parameters: ?page=1&limit=20&sort=created_at_desc
Response includes: total, page, limit, has_more

## Error Response
{
  "error": {
    "code": "INVALID_AMOUNT",
    "message": "Amount must be greater than 0",
    "details": {
      "field": "amount",
      "value": -100
    }
  }
}

## Status Codes
- 200 OK: Successful GET, PUT, PATCH
- 201 Created: Successful POST
- 204 No Content: Successful DELETE
- 400 Bad Request: Invalid input
- 401 Unauthorized: Missing/invalid authentication
- 403 Forbidden: Authenticated but not authorized
- 404 Not Found: Resource doesn't exist
- 409 Conflict: Duplicate resource, concurrent update
- 429 Too Many Requests: Rate limit exceeded
- 500 Internal Server Error: Server error
```

### Migration Pattern Decision Matrices

**Pattern Selection Matrix**

| Current State | Target State | Pattern | Timeline | Risk | Team Effort |
|--------------|-------------|---------|----------|------|------------|
| Monolith | Microservices | Strangler Fig | 18-24 mo | Medium | 2 teams |
| Monolith | Modular Monolith | Internal Refactoring | 6-12 mo | Low | 1 team |
| Microservices | Event-Driven | Async Middleware | 6-9 mo | Medium | 1-2 teams |
| Legacy Mainframe | Cloud-Native | Replatform + Rehost | 12-18 mo | High | 3+ teams |

**Technology Selection Decision Matrix**

| Requirement | REST | gRPC | GraphQL | AsyncAPI |
|------------|------|------|---------|----------|
| Browser Support | Yes | No | Yes | N/A |
| Binary Protocol | No | Yes | No | N/A |
| Query Flexibility | Limited | No | Excellent | N/A |
| Real-time | Polling | Streaming | Subscriptions | Streaming |
| Caching | Excellent | HTTP/2 | Complex | Varies |
| Learning Curve | Low | Medium | Medium | Low |
| Operational Maturity | Very High | High | Medium | Lower |

### Benchmarks

#### Microservices Adoption Maturity Model

**Level 0: Monolithic**
- Single codebase, single deployment
- Tight coupling
- Scaling requires scaling entire application

**Level 1: Foundation**
- Modular monolith or initial microservices
- Basic service communication
- Shared infrastructure/database patterns

**Level 2: Core Services**
- 5-10 independent microservices
- Database per service pattern implemented
- Asynchronous communication via message queues
- Automated CI/CD pipelines

**Level 3: Advanced Patterns**
- 10-50 microservices
- Event sourcing and CQRS in select services
- Service mesh for cross-cutting concerns
- Advanced observability (distributed tracing)
- CanaryDeployments and progressive delivery

**Level 4: Platform Engineering**
- 50+ microservices
- Self-service platform for service deployment
- API gateway and API management
- Data mesh with domain ownership
- Full observability and autonomous remediation

#### API Maturity Model (Richardson Maturity Model)

**Level 0: XML-RPC / SOAP**
- HTTP used only as transport
- Single endpoint
- WSDL for contract
- RPC-style method calls

**Level 1: Resources**
- Resources identified (URIs)
- Multiple endpoints (/users, /payments)
- Still uses mostly POST for all operations
- Basic HTTP semantics

**Level 2: HTTP Verbs**
- Proper HTTP methods (GET, POST, PUT, DELETE)
- Status codes correctly used
- Resource-based URLs
- RESTful conventions followed

**Level 3: Hypermedia Controls (HATEOAS)**
- Links in responses guide state transitions
- Clients discover actions via links
- True REST / REST Level 3
- Supports API evolution without client changes

#### Cloud-Native Maturity Assessment

| Dimension | Beginner | Intermediate | Advanced | Expert |
|-----------|----------|--------------|----------|---------|
| Containerization | <50% apps | 50-80% apps | 80-95% apps | 95%+ containerized |
| Orchestration | Manual or IaC | Kubernetes | Kubernetes + Service Mesh | Advanced platform |
| CI/CD | Weekly-daily | Daily | 5+ times daily | Continuous deployment |
| Observability | Logs only | Logs + Metrics | L+M+Traces | Integrated alerting |
| Deployment | Blue-green | Rolling | Canary | Flagger automation |

#### Architecture Review Cadence

**Recommended Frequency**
- Quarterly: Review architecture principles and decisions
- Per major initiative: Solution architecture review (before implementation)
- Monthly: For critical systems (payment processing, authentication)
- Annual: Full enterprise architecture assessment

**Expected Timeline**
- Initial review: 4-6 weeks (assessment of current state)
- Architecture design: 6-8 weeks
- Review and approval: 2-3 weeks
- Implementation: Varies (3-24 months depending on scope)

#### Typical API Response Time Targets by Tier

| Tier | Purpose | Target | 95th Percentile | 99th Percentile |
|------|---------|--------|-----------------|-----------------|
| Tier 1 | User-facing (checkout) | <100ms | <200ms | <500ms |
| Tier 2 | Internal service | <200ms | <400ms | <800ms |
| Tier 3 | Batch/async | <5 sec | <10 sec | <30 sec |
| Tier 4 | Reporting/analytics | <30 sec | <60 sec | N/A |

---

## Problem-Solving Frameworks

### Legacy Modernization Strategy Selection

**Evaluation Framework**

**1. Assess Technical Debt**
- Code quality (complexity, test coverage, duplication)
- Technology age (last major update, support status)
- Architecture (monolith, tight coupling, scalability limits)
- Operational burden (manual processes, reliability issues)

**2. Identify Modernization Drivers**
- Business drivers (growth, new features, market demands)
- Technical drivers (cost, performance, scalability)
- Organizational drivers (team productivity, hiring, retention)

**3. Evaluate Modernization Paths**

| Path | Effort | Risk | Timeline | Payoff |
|------|--------|------|----------|--------|
| **Strangler** | Medium | Low | 18-24 mo | High (incremental) |
| **Rehost (Lift-Shift)** | Low | Low | 3-6 mo | Low |
| **Refactor** | Medium | Medium | 12-18 mo | Medium |
| **Replatform** | High | Medium | 12-24 mo | High |
| **Rebuild** | Very High | Very High | 24-36 mo | Very High |

**Decision Criteria**
- Speed to market: Rehost fastest
- Cost optimization: Rehost cheapest initially
- Capability improvement: Rebuild, Replatform highest
- Risk tolerance: Strangler lowest risk
- Team capacity: Determine parallel workstreams possible

### Distributed System Debugging Approaches

**Observation Techniques**

**1. Distributed Tracing**
- End-to-end request flow
- Latency breakdown per service
- Identify bottlenecks
- Tools: Jaeger, Zipkin, AWS X-Ray

**2. Metrics Collection**
- Request rate, error rate, latency (RED metrics)
- Resource utilization (CPU, memory, disk, network)
- Business metrics (transactions, revenue, conversion)
- Tools: Prometheus, CloudWatch, Datadog

**3. Log Aggregation**
- Centralized log collection
- Correlation IDs across services
- Full request context
- Tools: ELK, Splunk, CloudWatch Logs

**4. Network Inspection**
- Service-to-service communication
- Packet inspection
- Bandwidth utilization
- Tools: Wireshark, tcpdump, service mesh observability

**Debugging Process**

1. **Reproduce Issue**: Understand reproduction steps and timing
2. **Isolate Domain**: Which service or layer affected
3. **Collect Data**: Gather traces, logs, metrics from relevant timeframe
4. **Analyze Flow**: Trace request through all services
5. **Identify Anomaly**: Find deviation from normal behavior
6. **Root Cause**: What caused the anomaly (code, config, resource)
7. **Fix and Validate**: Apply fix and verify with monitoring

### Performance Bottleneck Diagnosis

**Analysis Framework**

**1. Profile the System**
- Request latency: p50, p95, p99
- Throughput: requests per second
- Resource utilization: CPU, memory, disk I/O, network I/O
- Database query performance

**2. Apply Little's Law**
- Concurrency = Arrival Rate × Latency
- If latency increases with stable arrival rate, queueing problem
- If latency stable but throughput dropping, resource saturation

**3. Common Bottlenecks**

**Network Latency**
- Symptom: High service-to-service latency
- Cause: Geographic distance, poor routing, network congestion
- Solution: Caching, connection pooling, co-location, CDN

**Database Queries**
- Symptom: Slow response times, high CPU/disk I/O
- Cause: N+1 queries, missing indexes, table scan
- Solution: Query optimization, indexing, connection pooling, caching

**CPU Bound**
- Symptom: High CPU utilization, can't improve with more resources
- Cause: Inefficient algorithm, synchronous processing, blocked threads
- Solution: Algorithm optimization, parallelization, caching, async

**Memory Pressure**
- Symptom: GC pauses, out-of-memory errors
- Cause: Memory leak, unbounded cache, large data structures
- Solution: Fix leak, bound caches, streaming instead of loading all data

**Disk I/O**
- Symptom: High disk I/O, slow response, high latency
- Cause: Excessive logging, synchronous writes, large file operations
- Solution: Async writes, batching, compression, SSD upgrade

**4. Validation**
- Before optimization: Benchmark baseline
- After optimization: Measure improvement
- Compare to hypothesis
- Load test to verify improvements at scale

### Architecture Trade-Off Analysis (CAP, PACELC)

#### CAP Theorem

**Consistency**: All nodes see same data at same time
**Availability**: System remains available despite failures
**Partition tolerance**: System works despite network partitions

**Theorem**: Can guarantee at most 2 of 3 in distributed system

**Trade-Offs**

**CP (Consistency + Partition)**
- Choice during network partition
- Example: Strong consistency database (Oracle, PostgreSQL)
- Behavior: Unavailable rather than return stale data
- Use: Financial systems, critical consistency (payments, ledger)

**AP (Availability + Partition)**
- Choice during network partition
- Example: Eventual consistency (DynamoDB, Cassandra)
- Behavior: Return latest known data, inconsistency possible
- Use: High-availability systems where eventual consistency acceptable

**CA (Consistency + Availability)**
- Cannot tolerate partitions (unrealistic in distributed systems)
- Example: Single database in single datacenter
- Not practical for fault-tolerant systems

#### PACELC Theorem

"If there's a Partition, then A (availability) or C (consistency); Else (no partition) L (latency) or C (consistency)"

**E**: Else (no partition situation)
**L**: Latency (response time)

**Implications**
- Even without partition, trade-off between latency and consistency
- Replicated databases face latency-consistency trade-off
- Strong consistency requires synchronous replication (high latency)
- Eventual consistency enables low latency but temporary inconsistency

**Decision Framework**

1. **Identify consistency requirements**
   - Strong: Payment ledger, inventory, financial data
   - Eventual: User profiles, recommendations, cache

2. **Identify latency requirements**
   - Low latency (<100ms): User-facing APIs
   - Moderate (100ms-1s): Internal services
   - High latency ok (>1s): Batch jobs, reports

3. **Identify partition tolerance requirements**
   - Multi-region: Must handle partitions
   - Single datacenter: Lower partition risk (but not zero)

4. **Select appropriate pattern**
   - Strong + Low Latency: Geographically co-located replicas
   - Strong + High Latency acceptable: Accept replication lag
   - Eventual + Low Latency: Cache invalidation strategy
   - Eventual + High Latency: Acceptable, use batch processing

### Vendor Lock-In Mitigation Strategies

**Types of Lock-In**

**Data Lock-In**
- Proprietary data formats
- Difficult to export large datasets
- Cost/time to migrate data

**Mitigation**
- Use standard formats (JSON, Parquet, CSV)
- Maintain export capability
- Regular data export tests
- Use open-source databases

**API/Interface Lock-In**
- Proprietary APIs
- Learning curve to switch
- Rewrite application code

**Mitigation**
- Use standard APIs (REST, GraphQL, gRPC)
- Abstraction layers for vendor-specific features
- Interface contracts with vendor-neutral implementations
- Multi-cloud testing

**Architecture Lock-In**
- Features only on one vendor
- Application design depends on vendor patterns

**Mitigation**
- Polyglot approach: Multiple vendors, each excels at something
- Open standards (Kubernetes, OpenStack)
- Containers for portability
- Infrastructure as Code for reproducibility

**Operational Lock-In**
- Deep integration with vendor tools
- Operations staff trained only on one vendor
- Difficult to switch due to operational complexity

**Mitigation**
- Hire/train multi-cloud operations
- Use vendor-neutral monitoring and logging
- Automate operations with IaC
- Build portability into operations practices

### Technical Debt Quantification and Prioritization

**Debt Identification**

**Code-Level Debt**
- Duplication
- High cyclomatic complexity
- Inadequate test coverage
- Anti-patterns
- Tool: Code analysis (SonarQube, CodeClimate)

**Architecture-Level Debt**
- Monolithic bottlenecks
- Tight coupling
- Missing abstraction layers
- Scaling limitations
- Assessment: Architecture review

**Data Debt**
- Poor data quality
- Missing validation
- Inconsistent schemas
- Undocumented transformations
- Assessment: Data audit

**Test Debt**
- Low test coverage
- Brittle tests
- Missing integration tests
- No end-to-end tests
- Assessment: Test metrics

**Documentation Debt**
- Missing documentation
- Outdated documentation
- Undocumented decisions
- Assessment: Documentation audit

**Quantification**

**Financial Impact**
- Cost of bug fixes: Higher without tests
- Cost of feature development: Slower with tight coupling
- Cost of operational incidents: Frequent with poor observability
- Cost of team onboarding: Long with poor documentation

**Business Impact**
- Developer productivity: Days spent debugging vs developing
- Time-to-market: Development velocity impact
- Quality/reliability: Bug rates, incident frequency
- Team retention: Developer frustration

**Formula**: Debt Impact = (Cost/Issue × Issue Frequency) + (Productivity Loss Days × Daily Cost)

**Prioritization Matrix**

| Impact | Effort | Priority |
|--------|--------|----------|
| High | Low | 1: Fix immediately |
| High | High | 2: Plan and schedule |
| Medium | Low | 3: Do opportunistically |
| Medium | High | 4: Revisit periodically |
| Low | Any | 5: Accept or monitor |

**Examples**

High/Low Priority:
- Monolith blocking 10x growth, can extract first service in 3 months → Do it

High/High Priority:
- Need to rewrite entire codebase in 2 years, accept current pain → Refactor opportunistically

Low/Low Priority:
- Code style improvements, can use linters and formatters → Automate

**Tracking and Communication**

- Maintain technical debt registry
- Track debt impact on metrics (velocity, quality, incidents)
- Regular technical debt reviews
- Communicate to leadership: "Debt is costing us $2M/year in lost productivity"
- Plan quarterly debt reduction sprints
- Balance feature development with debt paydown (e.g., 20% debt/80% features)

---

## Confidence and Escalation

When providing architecture guidance:

- **High Confidence (80%+)**: Strong alignment with established patterns, proven at scale, multiple sources validate
- **Medium Confidence (50-80%)**: Some variation needed for context, emerging patterns, newer technologies
- **Low Confidence (<50%)**: Novel situation, insufficient data, emerging technology, recommend deeper investigation

When uncertain:
1. State the limitation explicitly
2. Provide alternatives with trade-offs
3. Recommend pilots or deeper investigation
4. Escalate to architecture council if major decision
5. Plan for learning and iteration

---

## Contact and Escalation

- **Quick Questions**: Slack #architecture channel
- **Architecture Review**: Contact Architecture Council
- **Major Decisions**: Schedule Architecture Board review
- **Emergency Architecture Issues**: Escalate via incident channel
