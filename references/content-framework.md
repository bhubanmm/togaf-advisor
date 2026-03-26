# Architecture Content Framework — Artifact Catalog

## Table of Contents
1. [Content Metamodel Overview](#metamodel)
2. [Building Blocks](#building-blocks)
3. [Artifact Catalog by Type](#artifact-catalog)
   - [Catalogs](#catalogs)
   - [Matrices](#matrices)
   - [Diagrams](#diagrams)
4. [Artifact-to-Phase Mapping](#phase-mapping)
5. [Deliverable Structures](#deliverables)
6. [Enterprise Continuum & Solutions Continuum](#continuum)

---

## Content Metamodel Overview {#metamodel}

The TOGAF Content Metamodel defines the core entities and their relationships
across all architecture domains. Understanding the metamodel is prerequisite to
populating artifacts correctly.

### Core Entity Classes

| Class | Examples | Domain |
|---|---|---|
| **Motivation** | Driver, Goal, Objective, Principle, Requirement, Constraint, Assumption | Cross-domain |
| **Actor / Role** | Organization Unit, Actor, Role | Business |
| **Business** | Function, Service, Process, Event, Contract, Product | Business |
| **Information** | Data Entity, Logical Data Component, Physical Data Component | Data |
| **Application** | Logical App Component, Physical App Component | Application |
| **Technology** | Logical Tech Component, Physical Tech Component, Node, Network | Technology |
| **Implementation** | Work Package, Deliverable, Implementation Factor | Cross-domain |

### Key Metamodel Relationships
- **Driver → Goal → Objective → Requirement**: motivation traceability chain
- **Business Function → Application Component**: function-to-support mapping
- **Logical Component → Physical Component**: ABB → SBB realization
- **Work Package → Building Block**: delivery traceability

---

## Building Blocks {#building-blocks}

### Architecture Building Blocks (ABBs)
- Technology-agnostic, capability-oriented
- Defined in terms of required behavior and interfaces
- Live in the Architecture Continuum (Foundation → Common Systems → Industry)
- Sourced from TRM service categories, III-RM integration patterns, or custom
  industry models

### Solution Building Blocks (SBBs)
- Product- or vendor-specific realizations of ABBs
- Can be commercial products, open source components, or custom-built
- Sourced from the Solutions Continuum
- Selection rationale must document: ABB covered, constraints addressed,
  gaps or partial coverage

### Building Block Assessment Criteria
| Criterion | Questions to Answer |
|---|---|
| Fit | Does the SBB fully realize the ABB's required capability? |
| Interoperability | Does it conform to required interfaces and standards? |
| Reuse | Is it already present in the Solutions Continuum? |
| Lifecycle | Is it on the strategic or sunset technology list? |
| Risk | Vendor lock-in, support continuity, security posture |
| Cost | TCO vs. build or alternative SBB |

---

## Artifact Catalog by Type {#artifact-catalog}

### Catalogs {#catalogs}

Catalogs are structured inventories. They are the primary artifacts for
establishing Baseline Architecture facts.

| Artifact | Domain | Key Columns / Attributes |
|---|---|---|
| Principles Catalog | Cross | ID, Statement, Rationale, Implications |
| Business Capability Catalog | Business | ID, Name, Description, Owner, Maturity Level |
| Value Stream Catalog | Business | ID, Name, Triggering Event, Outcome, Stakeholder |
| Organization / Actor Catalog | Business | ID, Name, Type, Responsibilities, Location |
| Driver / Goal / Objective Catalog | Motivation | ID, Type, Description, Owner, KPI |
| Role Catalog | Business | ID, Name, Type (internal/external), Responsibilities |
| Business Service / Function Catalog | Business | ID, Name, Type, Owner, Supporting App |
| Location Catalog | Cross | ID, Name, Type, Geography, Jurisdiction |
| Process / Event / Control / Product Catalog | Business | ID, Name, Type, Owner, Related Function |
| Data Entity / Data Component Catalog | Data | ID, Name, Type, Owner, Classification, Master System |
| Application Portfolio Catalog | Application | ID, Name, Owner, Status, Lifecycle Stage, Platform |
| Interface Catalog | Application | ID, Name, Type, Direction, Protocol, Frequency |
| Technology Standards Catalog | Technology | ID, Name, Category, Status (Strategic/Sunset/Prohibited) |
| Technology Portfolio Catalog | Technology | ID, Name, Type, Owner, Lifecycle, EOL Date |

---

### Matrices {#matrices}

Matrices reveal relationships and dependencies between catalog entities.
They are the primary artifacts for gap analysis and impact assessment.

| Artifact | Domain | Axes / Relationships |
|---|---|---|
| Business Interaction Matrix | Business | Actor × Actor — interaction type and frequency |
| Actor / Role Matrix | Business | Organization Unit × Role — assignment and RACI |
| Business Function / Organization Matrix | Business | Business Function × Org Unit — ownership and participation |
| Application / Organization Matrix | Application | Application × Org Unit — ownership and usage |
| Application / Function Matrix | Application | Application × Business Function — functional coverage |
| Application Interaction Matrix | Application | Application × Application — integration dependencies |
| Data Entity / Business Function Matrix | Data | Data Entity × Business Function — CRUD ownership |
| Application / Technology Matrix | Technology | Application Component × Technology Component — platform dependencies |
| Technology / Application Matrix | Technology | Reverse view: platform × dependent applications |
| Consolidated Gaps / Solutions / Dependencies Matrix | Cross | Gap × Solution × Work Package × Dependency |

---

### Diagrams {#diagrams}

Diagrams communicate structural, behavioral, and deployment patterns. Select
diagrams by stakeholder concern, not by habit.

#### Business Architecture Diagrams
| Diagram | Purpose | Stakeholder Concern |
|---|---|---|
| Business Footprint Diagram | Org unit × capabilities × locations | Executive scope and boundary |
| Business Service / Information Diagram | Service flows with information exchange | Process owners |
| Functional Decomposition Diagram | Hierarchical capability/function breakdown | Business analysts |
| Product Lifecycle Diagram | Product stages with supporting capabilities | Product owners |
| Goal / Objective / Service Diagram | Motivation → capability → service traceability | Strategy and governance |
| Use Case Diagram | Actor-triggered business process flows | Process owners, BA |
| Organization Decomposition Diagram | Reporting structure and relationships | HR, change management |
| Process Flow Diagram | Step-by-step business process | Operations, BPM |
| Event Diagram | Triggering events and business responses | Operations, integration |

#### Data Architecture Diagrams
| Diagram | Purpose | Stakeholder Concern |
|---|---|---|
| Conceptual Data Diagram | High-level entity groupings and relationships | Business data owners |
| Logical Data Diagram | Canonical entity model with attributes | Data architects, MDM |
| Data Dissemination Diagram | Data flows across app/org boundaries | Integration architects |
| Data Security Diagram | Classification zones and access controls | Security, compliance |
| Data Migration Diagram | Source → target data movement paths | Delivery, DBA |
| Data Lifecycle Diagram | Data from creation through archival/purge | Compliance, data governance |

#### Application Architecture Diagrams
| Diagram | Purpose | Stakeholder Concern |
|---|---|---|
| Application Communication Diagram | Protocol-level interaction between applications | Integration architects |
| Application and User Location Diagram | App deployment × user location | Operations, infrastructure |
| Application Use Case Diagram | Business function → application interaction | BA, solution architects |
| Enterprise Manageability Diagram | Operations and management topology | Operations |
| Process / Application Realization Diagram | Business process → application support | BA, project delivery |
| Software Engineering Diagram | Internal application component structure | Solution architects, developers |
| Application Migration Diagram | Current → future state application portfolio | Programme, delivery |

#### Technology Architecture Diagrams
| Diagram | Purpose | Stakeholder Concern |
|---|---|---|
| Environments and Locations Diagram | Physical deployment sites and zones | Infrastructure, security |
| Platform Decomposition Diagram | Platform layers mapped to TRM categories | CTO, platform teams |
| Processing Diagram | Compute resource topology | Infrastructure |
| Networked Computing / Hardware Diagram | Physical infrastructure layout | Network, data centre |
| Communications Engineering Diagram | Network topology and protocols | Network architects |

---

## Artifact-to-Phase Mapping {#phase-mapping}

| Phase | Primary Artifacts (produced or significantly updated) |
|---|---|
| Preliminary | Principles Catalog, Organization Model, Tailored Framework |
| A | Architecture Vision, Statement of Architecture Work, Stakeholder Map |
| B | Business Capability Catalog, Value Stream, Org/Actor Catalog, Business Interaction Matrix, Footprint Diagram, Gap Analysis |
| C-Data | Data Entity Catalog, Data Entity/Function Matrix, Logical Data Diagram, Data Dissemination Diagram |
| C-App | Application Portfolio Catalog, App/Org Matrix, App/Function Matrix, App Interaction Matrix, App Communication Diagram, Gap Analysis |
| D | Technology Standards Catalog, Technology Portfolio Catalog, App/Technology Matrix, Platform Decomposition Diagram, Environments Diagram, Gap Analysis |
| E | Architecture Roadmap (initial), Transition Architectures, Implementation Factor Catalog, Consolidated Gaps Matrix |
| F | Architecture Roadmap (final), Migration Plan, Architecture Contracts |
| G | Architecture Contracts (project), Compliance Assessments, Dispensation Records |
| H | Change Request, Impact Assessment, Updated ADD and Roadmap |

---

## Deliverable Structures {#deliverables}

### Architecture Definition Document (ADD)
The primary deliverable produced across Phases A–D. Structure:

1. Introduction and Background
2. Architecture Vision (from Phase A)
3. Business Architecture (Baseline + Target + Gap)
4. Data Architecture (Baseline + Target + Gap)
5. Application Architecture (Baseline + Target + Gap)
6. Technology Architecture (Baseline + Target + Gap)
7. Rationale and Justification
8. Mapping to Architecture Repository

### Architecture Requirements Specification (ARS)
Companion to the ADD. Structure:

1. Functional Requirements (by domain)
2. Non-Functional Requirements (performance, security, availability, etc.)
3. Constraints (technical, organizational, regulatory)
4. Assumptions
5. Traceability: Concern → Requirement → Architecture Decision

### Architecture Roadmap
1. Summary of Gaps and Drivers
2. Work Package Inventory (ID, scope, business value, dependencies)
3. Transition Architecture States
4. Sequencing and Dependencies Diagram
5. Delivery Vehicle Mapping (programmes, projects, agile trains)

### Architecture Contract
1. Parties and Roles
2. Scope (domain, work packages, delivery period)
3. Architecture Compliance Obligations
4. Review Checkpoints and Dispensation Process
5. Escalation Path
6. Change Management Provisions

---

## Enterprise Continuum & Solutions Continuum {#continuum}

### Enterprise Continuum Classification

| Level | Description | Examples |
|---|---|---|
| **Foundation Architecture** | Generic, vendor-neutral services applicable universally | TRM service taxonomy, III-RM brokerage patterns |
| **Common Systems Architecture** | Widely applicable cross-industry patterns | Identity & Access Management, Integration Middleware patterns |
| **Industry Architecture** | Sector-specific patterns | BIAN (banking), TMForum (telecom), HL7 FHIR (healthcare) |
| **Organization-Specific Architecture** | Tailored to the enterprise's unique context | Company-specific capability models, proprietary platforms |

### Using the Continuum for SBB Selection
1. Start at Foundation: does TRM have a service category for this need?
2. Check Common Systems: is there a widely-adopted pattern (e.g., OAuth2 for
   identity federation)?
3. Check Industry: is there a sector reference model that narrows the choice?
4. Only then evaluate specific products/vendors as SBB candidates
5. Document which continuum level justifies the selection

### Architecture Repository Structure
| Layer | Contents |
|---|---|
| Architecture Metamodel | Tailored TOGAF metamodel documentation |
| Architecture Capability | Governance framework, roles, processes |
| Architecture Landscape | Current, Transition, and Target architecture artifacts |
| Standards Information Base | Technology standards catalog, versioned |
| Reference Library | TRM, III-RM, industry models, best practices |
| Governance Log | Board decisions, dispensations, change requests, compliance assessments |
