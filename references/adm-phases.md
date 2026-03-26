# ADM Phases — Artifact & Decision Checklist

## Table of Contents
1. [Preliminary Phase](#preliminary)
2. [Phase A: Architecture Vision](#phase-a)
3. [Phase B: Business Architecture](#phase-b)
4. [Phase C: Information Systems Architecture](#phase-c)
5. [Phase D: Technology Architecture](#phase-d)
6. [Phase E: Opportunities & Solutions](#phase-e)
7. [Phase F: Migration Planning](#phase-f)
8. [Phase G: Implementation Governance](#phase-g)
9. [Phase H: Architecture Change Management](#phase-h)
10. [Requirements Management](#requirements-management)
11. [ADM Iteration Patterns](#iteration-patterns)

---

## Preliminary Phase {#preliminary}

**Purpose:** Establish the architecture capability, define the operating model,
tailor TOGAF, and confirm organizational commitment.

### Key Decisions
- Scope of enterprise covered by the architecture practice
- Architecture framework tailoring decisions (TOGAF adaptation, integration with
  other frameworks: ITIL, COBIT, SAFe, etc.)
- Architecture principles: sponsorship, approval process, authority hierarchy
- Architecture Repository structure and tooling selection
- Architecture governance framework: board composition, escalation paths,
  compliance process

### Core Artifacts
| Artifact | Type | Purpose |
|---|---|---|
| Architecture Principles | Catalog | Govern all subsequent ADM cycles |
| Organizational Model for EA | Document | Defines roles, responsibilities, budget |
| Tailored Architecture Framework | Document | Adapted TOGAF for the enterprise |
| Architecture Repository (initial) | Repository | Baseline structure for all assets |
| Request for Architecture Work | Document | Triggers Phase A |

### Decision Gates
- [ ] Architecture principles approved by sponsoring executive
- [ ] Architecture Board chartered and empowered
- [ ] Repository structure defined and populated with any existing assets
- [ ] Governance framework ratified
- [ ] Scope and partitioning decisions documented

---

## Phase A: Architecture Vision {#phase-a}

**Purpose:** Define the scope, constraints, and high-level target for a specific
ADM cycle. Secure stakeholder buy-in before committing to detailed architecture work.

### Key Decisions
- Architecture cycle scope: which domains, business units, time horizon
- Stakeholder identification and concern mapping
- High-level Target Architecture direction (vision, not detail)
- Constraints: budget, time, regulatory, political
- Architecture principles applicability to this cycle

### Core Artifacts
| Artifact | Type | Purpose |
|---|---|---|
| Architecture Vision | Document | High-level statement of Target state |
| Statement of Architecture Work | Document | Formal scope and plan for the cycle |
| Stakeholder Map | Matrix | Concerns, influence, engagement strategy |
| Value Chain / Business Capability Map | Diagram | Scoping boundary visualization |
| Architecture Definition Document (stub) | Document | Initiated here, completed B–D |

### Decision Gates
- [ ] Sponsoring executive sign-off on Statement of Architecture Work
- [ ] Stakeholder concerns documented and traceable to requirements
- [ ] Scope boundaries explicit — what is in and out of this cycle
- [ ] Architecture Vision reviewed by Architecture Board
- [ ] Known constraints and risks logged

---

## Phase B: Business Architecture {#phase-b}

**Purpose:** Develop the Baseline and Target Business Architecture. Identify gaps
that drive downstream IS and Technology architecture decisions.

### Key Decisions
- Business capability target state and sequencing priorities
- Value stream ownership and handoff redesign
- Organizational model changes required
- Business process scope: which processes are in scope for redesign vs. stabilize
- Business requirements that constrain IS and Technology architecture

### Core Artifacts
| Artifact | Type | Purpose |
|---|---|---|
| Business Capability Map | Catalog/Diagram | Baseline and Target capability inventory |
| Value Stream Map | Diagram | End-to-end flow with capability linkage |
| Organization/Actor Catalog | Catalog | Roles, actors, organizational units |
| Business Interaction Matrix | Matrix | Actor-to-function interaction patterns |
| Business Footprint Diagram | Diagram | Org units × capabilities × locations |
| Business Use Case Diagram | Diagram | Actor-triggered business processes |
| Process Flow Diagrams | Diagram | Detailed in-scope process flows |
| Gap Analysis | Document | Baseline → Target delta with impact rating |

### Decision Gates
- [ ] Business capability gaps prioritized and ranked by strategic impact
- [ ] Organizational model changes identified and flagged for HR/change management
- [ ] Business requirements formally captured in Architecture Requirements Specification
- [ ] Traceability from Architecture Vision to Business Architecture established
- [ ] Stakeholder review completed; concerns addressed or logged as risks

---

## Phase C: Information Systems Architecture {#phase-c}

**Purpose:** Develop Baseline and Target Data and Application architectures.
Typically run as two sub-phases (Data first, then Application, or concurrently).

### Data Architecture

#### Key Decisions
- Canonical data model scope and ownership
- Master data management strategy
- Data sovereignty, residency, and classification policy
- Data lifecycle: retention, archival, purge
- API vs. event vs. batch data exchange patterns

#### Core Artifacts
| Artifact | Type | Purpose |
|---|---|---|
| Data Entity / Data Component Catalog | Catalog | Authoritative data entity inventory |
| Data Entity / Business Function Matrix | Matrix | Ownership and stewardship mapping |
| Logical Data Diagram | Diagram | Entity relationships, canonical model |
| Data Dissemination Diagram | Diagram | Data flows across application/org boundaries |
| Data Security Classification | Catalog | Sensitivity levels, handling rules |
| Data Migration Plan (stub) | Document | Initiated here, detailed in E/F |

### Application Architecture

#### Key Decisions
- Application portfolio rationalization: retain, retire, replace, re-platform
- Integration style: point-to-point vs. ESB vs. API gateway vs. event mesh
- SaaS adoption boundaries — what stays on-prem vs. cloud-native
- Application capability gap: build vs. buy vs. partner
- Application interaction and dependency risk

#### Core Artifacts
| Artifact | Type | Purpose |
|---|---|---|
| Application Portfolio Catalog | Catalog | Full inventory with lifecycle status |
| Application / Organization Matrix | Matrix | App ownership by business unit |
| Application Interaction Diagram | Diagram | Integration topology, data flows |
| Application Communication Diagram | Diagram | Protocol-level interaction patterns |
| App / Function Matrix | Matrix | Business function to application coverage |
| Gap Analysis | Document | Portfolio gaps, redundancies, and risks |

### Decision Gates
- [ ] Data ownership and stewardship assigned for all critical entities
- [ ] Application rationalization decisions approved by domain owners
- [ ] Integration patterns selected and rationale documented
- [ ] Data and Application gaps mapped to Business Architecture gaps (traceability)
- [ ] Security and compliance requirements captured in Architecture Requirements Spec

---

## Phase D: Technology Architecture {#phase-d}

**Purpose:** Define the Baseline and Target Technology Architecture that supports
the IS and Business architectures. Map logical services to physical building blocks.

### Key Decisions
- Platform strategy: public cloud, private cloud, hybrid, multi-cloud
- Technology standards: approved platforms, languages, protocols, versions
- Infrastructure patterns: containerization, serverless, managed services
- Network topology and security zone design
- Technology lifecycle: which platforms are sunset vs. strategic
- SBB selection rationale against TRM service categories

### Core Artifacts
| Artifact | Type | Purpose |
|---|---|---|
| Technology Standards Catalog | Catalog | Approved/preferred/prohibited technologies |
| Technology Portfolio Catalog | Catalog | Current infrastructure inventory with status |
| Technology / Application Matrix | Matrix | App-to-platform dependency mapping |
| Environments and Locations Diagram | Diagram | Physical / logical deployment topology |
| Platform Decomposition Diagram | Diagram | Platform layers mapped to TRM categories |
| Network Computing / Hardware Diagram | Diagram | Infrastructure topology |
| Communications Engineering Diagram | Diagram | Network connectivity and protocols |
| Gap Analysis | Document | Baseline → Target with risk and cost flags |

### Decision Gates
- [ ] Technology standards ratified by Architecture Board
- [ ] Cloud/platform strategy aligned with enterprise risk and security policy
- [ ] SBB selections traceable to ABBs from Content Framework
- [ ] Technology gaps mapped to IS and Business gaps (end-to-end traceability)
- [ ] Technology lifecycle risks flagged with mitigation options

---

## Phase E: Opportunities & Solutions {#phase-e}

**Purpose:** Generate the initial Architecture Roadmap. Identify work packages,
transition architectures, and delivery vehicle options.

### Key Decisions
- Work package definition: scope, dependencies, sequencing constraints
- Transition Architecture states: how many, what each one achieves
- Delivery vehicle: programme, project, agile release train, product increment
- Build vs. buy vs. reuse decisions for identified building blocks
- Quick wins vs. foundational investments: sequencing philosophy

### Core Artifacts
| Artifact | Type | Purpose |
|---|---|---|
| Architecture Roadmap (initial) | Document | Work package sequence with dependencies |
| Transition Architecture(s) | Document | Intermediate stable states |
| Implementation Factor Catalog | Catalog | Risks, issues, assumptions affecting delivery |
| Consolidated Gap / Solution / Dependency Matrix | Matrix | Gaps × solutions × sequencing |
| Project Context Diagram | Diagram | Work package context and boundaries |
| Benefits Diagram | Diagram | Capability outcomes × business value |

### Decision Gates
- [ ] Work packages defined with clear scope and entry/exit criteria
- [ ] Transition Architectures validated as architecturally coherent (not just milestones)
- [ ] Dependencies between work packages documented and risk-rated
- [ ] Build/buy/reuse decisions documented with rationale
- [ ] Roadmap reviewed by Architecture Board and programme leadership

---

## Phase F: Migration Planning {#phase-f}

**Purpose:** Finalize the Architecture Roadmap and create an implementable
Migration Plan in coordination with portfolio/programme management.

### Key Decisions
- Project priority ranking: value, risk, dependency, resource availability
- Funding and resource allocation across transition states
- Portfolio/programme management integration: how architecture work packages
  map to delivery constructs
- Architecture compliance checkpoints embedded in delivery lifecycle

### Core Artifacts
| Artifact | Type | Purpose |
|---|---|---|
| Architecture Roadmap (finalized) | Document | Baselined delivery sequence |
| Migration Plan | Document | Transition timeline, resources, dependencies |
| Capability Assessment | Document | Delivery capability vs. plan requirements |
| Architecture Contract (programme-level) | Document | Obligations between architecture and delivery |

### Decision Gates
- [ ] Migration Plan approved by programme/portfolio governance
- [ ] Architecture compliance checkpoints defined for each work package
- [ ] Funding confirmed for first transition state
- [ ] Architecture Board sign-off on finalized roadmap

---

## Phase G: Implementation Governance {#phase-g}

**Purpose:** Ensure architecture compliance throughout delivery. This is the
architecture practice's primary touchpoint with project execution.

### Key Decisions
- Compliance review frequency and depth by project risk level
- Dispensation criteria: when is non-compliance acceptable, and at what cost
- Architecture change requests: impact assessment process
- Lessons learned: what feeds back to the Architecture Repository

### Core Artifacts
| Artifact | Type | Purpose |
|---|---|---|
| Architecture Contract (project-level) | Document | Project-specific compliance obligations |
| Compliance Assessment | Document | Project adherence to Target Architecture |
| Dispensation Request / Decision | Document | Documented exception with rationale |
| Change Request | Document | Triggers Phase H if architecture impact confirmed |
| Implementation and Migration Plan (updates) | Document | Reflects as-built deviations |

### Decision Gates
- [ ] Architecture contracts in place before project execution begins
- [ ] Compliance review schedule agreed with project/programme management
- [ ] Dispensation process operational and understood by delivery teams
- [ ] Architecture Repository updated with as-built artifacts post-delivery

---

## Phase H: Architecture Change Management {#phase-h}

**Purpose:** Manage changes to the architecture in a controlled manner. Determine
whether a change requires a new ADM cycle or can be handled as a maintenance update.

### Key Decisions
- Change classification: maintenance update vs. significant change triggering new cycle
- Driver: technology change, business change, regulatory, or lessons learned
- Impact scope: which domains, which roadmap work packages are affected
- Architecture governance response: board notification vs. full review

### Core Artifacts
| Artifact | Type | Purpose |
|---|---|---|
| Architecture Change Request | Document | Formal trigger for H phase assessment |
| Change Impact Assessment | Document | Scope, cost, risk of the proposed change |
| Updated Architecture Roadmap | Document | If change affects sequencing |
| Updated Architecture Definition Document | Document | Reflects approved changes |

### Decision Gates
- [ ] Change classified and routed correctly (maintenance vs. new cycle)
- [ ] Impact assessment reviewed by Architecture Board
- [ ] Affected work packages and contracts updated
- [ ] Change communicated to impacted stakeholders

---

## Requirements Management {#requirements-management}

**Purpose:** Continuous process running across all phases. Captures, maintains,
and manages architecture requirements throughout the ADM cycle.

### Key Principles
- Requirements are distinct from concerns — a concern becomes a requirement when
  it is scoped, owned, and traceable
- All requirements must be traceable to a stakeholder concern and an architecture
  deliverable
- Requirements changes must trigger impact assessment across open ADM phases

### Core Artifacts
| Artifact | Type | Purpose |
|---|---|---|
| Architecture Requirements Specification | Document | Formally scoped, owned requirements |
| Requirements Impact Assessment | Document | Effect of a requirement change across phases |

---

## ADM Iteration Patterns {#iteration-patterns}

### Architecture Development Iteration
Full or partial ADM cycle focused on developing architecture for a new capability
or domain. Most common pattern for greenfield or major transformation programs.

### Transition Planning Iteration
Phases E–F iterated to refine work packages and transition states as delivery
realities emerge. Triggered when roadmap needs resequencing.

### Architecture Governance Iteration
Phases G–H operating continuously alongside delivery. The "steady state" of a
mature architecture practice.

### Capability-Based Iteration
ADM scoped around a specific business capability rather than a domain or
technology. Useful in agile enterprises where capability ownership is clearer
than domain boundaries.

### Agile ADM Adaptation
- Phase A → Architecture Vision becomes a sprint-0 equivalent
- Phases B–D run concurrently for narrow-scope features
- Phase E work packages map to epics or features
- Phases G–H operate as architecture review ceremonies within the delivery cadence
- Architecture Board → Architecture Guild or Chapter model in scaled agile contexts
