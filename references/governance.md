# Architecture Governance — Compliance, Contracts & Board Operations

## Table of Contents
1. [Governance Framework Overview](#overview)
2. [Architecture Board](#architecture-board)
3. [Compliance Review Process](#compliance-review)
4. [Architecture Contracts](#architecture-contracts)
5. [Dispensation Process](#dispensation)
6. [Architecture Change Management](#change-management)
7. [Architecture Maturity Assessment](#maturity)
8. [Governance in Scaled / Agile Contexts](#scaled)

---

## Governance Framework Overview {#overview}

Architecture governance ensures that architecture decisions are made
consistently, applied to delivery, and evolve in a controlled manner. In TOGAF,
governance operates at three levels:

| Level | Scope | Primary Mechanism |
|---|---|---|
| **Corporate Governance** | Enterprise-wide compliance, strategy alignment | Architecture principles, mandate |
| **Technology Governance** | Technology standards, portfolio decisions | Technology standards catalog, Architecture Board |
| **IT Governance** | Project/programme compliance with architecture | Architecture contracts, compliance reviews |

The architecture practice is the custodian of all three levels, but exercises
direct control primarily at the Technology and IT governance levels.

### Governance Failure Modes to Diagnose
- **Governance theater**: reviews happen but have no teeth — no dispensation
  process, no escalation path, no board with decision authority
- **Late compliance**: architecture review occurs after build, not before design
- **Undocumented dispensations**: exceptions granted informally, no audit trail
- **Stale standards**: Technology Standards Catalog not maintained, teams default
  to whatever is available
- **Fragmented board**: multiple domain-specific boards with no cross-domain
  coordination authority

---

## Architecture Board {#architecture-board}

### Composition Principles
The Architecture Board must be able to make binding decisions across all
architecture domains. Recommended composition:

| Role | Representation | Voting |
|---|---|---|
| Chief Architect / EA Lead | Architecture practice | Yes — Chair |
| Business Architecture Lead | Business domain | Yes |
| Data Architecture Lead | Data domain | Yes |
| Application Architecture Lead | Application domain | Yes |
| Technology Architecture Lead | Technology/Infrastructure | Yes |
| Security Architecture Lead | Security | Yes |
| Business Sponsor Representative | Business stakeholder | Yes (or advisory) |
| Programme/PMO Representative | Delivery | Advisory |
| External Advisor (optional) | Industry / vendor neutral | Advisory |

Quorum: typically 50%+ of voting members. Define in the governance charter.

### Board Responsibilities
- Ratify architecture principles and standards
- Approve Target Architecture and major transitions
- Rule on dispensation requests
- Review and approve architecture change requests (Phase H triggers)
- Maintain the Governance Log
- Monitor compliance posture across the portfolio
- Escalate to corporate governance when required

### Meeting Cadence
| Type | Frequency | Purpose |
|---|---|---|
| Standards Review | Quarterly | Review Technology Standards Catalog updates |
| Compliance Review | Monthly or per programme milestone | Project compliance assessments |
| Dispensation Hearing | As needed (< 5 business days SLA recommended) | Rule on exception requests |
| ADM Phase Gate | At each ADM phase completion | Approve phase deliverables and gate passage |
| Emergency Review | < 48 hours | Critical architecture decisions blocking delivery |

### Architecture Board Brief Template
Use this structure when bringing a decision to the board:

```
1. DECISION REQUIRED
   One sentence: what the board is being asked to decide.

2. CONTEXT
   ADM phase, domain(s) affected, programme or project context.

3. ARCHITECTURE POSITION
   The recommended architecture position with rationale.
   Reference relevant principles, standards, or prior board decisions.

4. OPTIONS CONSIDERED
   2–3 alternatives with tradeoff summary.
   Why the recommended option is preferred.

5. IMPLICATIONS
   Impact on: roadmap, existing contracts, standards catalog,
   downstream architecture decisions.

6. RISKS IF NOT DECIDED
   What is blocked or at risk without a board decision.

7. ATTACHMENTS
   Relevant artifacts: gap analysis, compliance assessment, change request.
```

---

## Compliance Review Process {#compliance-review}

### Compliance Review Types

| Type | Trigger | Depth |
|---|---|---|
| **Lightweight** | Low-risk projects, standard patterns only | Checklist-based, < 2 hours |
| **Standard** | Medium complexity or first use of a pattern/technology | Full artifact review, 1–2 sessions |
| **Deep** | Strategic programmes, new domains, significant investment | Architecture Board involvement, multi-session |
| **Post-Implementation** | After delivery, before closing compliance contract | As-built vs. Target Architecture delta |

### Risk-Based Compliance Classification
Classify projects before assigning review depth:

| Factor | Low | Medium | High |
|---|---|---|---|
| Investment size | < $500K | $500K–$5M | > $5M |
| Domain impact | Single domain | 2–3 domains | Cross-domain / enterprise |
| Architectural novelty | Known pattern | Adapted pattern | New pattern or technology |
| Regulatory exposure | None | Moderate | High (PCI, HIPAA, GDPR, etc.) |
| Strategic alignment | Incremental | Capability enabling | Transformational |

Score: 3+ High factors → Deep review. 2+ Medium → Standard. Otherwise → Lightweight.

### Compliance Questionnaire — Core Areas

**Business Architecture Compliance**
- [ ] Capability impacts mapped and approved by capability owners
- [ ] No unintended process changes outside project scope
- [ ] Organization model changes formally managed

**Data Architecture Compliance**
- [ ] Data entities created or modified are registered in the Data Entity Catalog
- [ ] Master data ownership confirmed — no new MDM conflicts introduced
- [ ] Data residency and classification requirements met
- [ ] Data flows documented and consistent with Data Dissemination Diagram

**Application Architecture Compliance**
- [ ] No new point-to-point integrations unless dispensation granted
- [ ] API contracts registered in Interface Catalog
- [ ] Application Portfolio Catalog updated with any new or retired components
- [ ] Application lifecycle status confirmed (no new dependencies on sunset apps)

**Technology Architecture Compliance**
- [ ] All technology components on the Strategic or Permitted list
- [ ] No use of Prohibited technologies
- [ ] No net-new infrastructure patterns without Architecture Board approval
- [ ] Security architecture review completed (where applicable)

**Governance**
- [ ] Architecture contract signed before build commenced
- [ ] All dispensations formally documented and approved
- [ ] Repository updated with as-built artifacts post-delivery

### Compliance Assessment Report Structure
```
1. Project / Programme Identifier
2. Assessment Type (Lightweight / Standard / Deep / Post-Implementation)
3. Compliance Summary (RAG status by domain)
4. Findings
   - Compliant items (list)
   - Non-compliant items with severity (Critical / Major / Minor)
   - Dispensations in scope (reference dispensation log)
5. Recommendations
6. Sign-off (Architect, Architecture Board Chair if required)
```

---

## Architecture Contracts {#architecture-contracts}

### Contract Types

| Type | Parties | Scope |
|---|---|---|
| **Programme-level** | Architecture practice + Programme Board | Full programme, all work packages |
| **Project-level** | Architecture practice + Project Manager | Single project or work package |
| **Service-level** | Architecture practice + Operations | Ongoing operational architecture obligations |
| **Partner/Vendor** | Architecture practice + Third party | Externally delivered components |

### Architecture Contract Template

```
ARCHITECTURE CONTRACT

Reference:        [Unique ID]
Version:          [x.x]
Date:             [Date]
ADM Phase:        [F or G]

PARTIES
  Architecture Authority:   [Name, Role]
  Delivery Authority:       [Name, Role]

SCOPE
  Programme / Project:      [Name]
  Work Packages:            [List]
  Architecture Domains:     [Business / Data / Application / Technology]
  Effective Period:         [Start – End]

ARCHITECTURE OBLIGATIONS
  Target Architecture Reference:    [ADD version, Repository link]
  Technology Standards Reference:   [Standards Catalog version]
  Mandatory Constraints:            [List specific non-negotiables]
  Dispensations in Scope:           [Reference approved dispensations]

COMPLIANCE OBLIGATIONS
  Review Checkpoints:       [Phase gates, sprint reviews, milestones]
  Review Type:              [Lightweight / Standard / Deep]
  Compliance Lead:          [Named architect]
  Reporting:                [Frequency and format]

CHANGE PROVISIONS
  Architecture Change Request process reference: [Link]
  Escalation path:          [Architect → Architecture Board → Sponsor]

SIGN-OFF
  Architecture Authority:   [Signature / Date]
  Delivery Authority:       [Signature / Date]
  Architecture Board Chair: [Signature / Date — if programme-level]
```

---

## Dispensation Process {#dispensation}

### When Dispensation Applies
A dispensation is a formally approved, time-bounded exception to an architecture
standard, principle, or constraint. It is **not** an informal workaround.

Dispensation triggers:
- Use of a Prohibited or Sunset technology
- Deviation from an approved integration pattern
- Temporary retention of a retired application
- Non-compliance with a data residency or classification requirement
- Inability to meet a non-functional requirement (performance, availability)
  within architectural constraints

### Dispensation Request Template

```
DISPENSATION REQUEST

Reference:        [Unique ID]
Date:             [Date]
Requestor:        [Name, Role, Project]

NATURE OF EXCEPTION
  Standard / Constraint being waived:   [Reference ID from standards catalog
                                         or ADD]
  Nature of deviation:                  [Specific non-compliant element]

JUSTIFICATION
  Business driver:          [Why this is necessary]
  Alternatives considered:  [Why compliant options were rejected]
  Risk assessment:          [Technical, security, operational, regulatory risk
                             of the exception]

MITIGATING CONTROLS
  [Compensating controls that reduce the risk of the exception]

SCOPE AND DURATION
  Affected systems / work packages:   [Specific scope]
  Expiry:                             [Date or event trigger, e.g., "until
                                       platform migration completes in Q3"]

RESOLUTION COMMITMENT
  Path to compliance:       [How and when the exception will be resolved]
  Owner:                    [Named accountable person]

ARCHITECTURE BOARD DECISION
  Decision:         [Approved / Approved with conditions / Rejected]
  Conditions:       [If applicable]
  Board Chair sign-off:     [Signature / Date]
```

### Dispensation Log
The Governance Log in the Architecture Repository must record:
- All dispensation requests (approved and rejected)
- Expiry dates and resolution commitments
- Status: Active / Resolved / Overdue
- Quarterly review by the Architecture Board of all Active dispensations

---

## Architecture Change Management {#change-management}

### Change Classification

| Class | Description | Response |
|---|---|---|
| **Simplification** | Reduced complexity, no new capability | Maintenance update, no new ADM cycle |
| **Incremental** | Extended capability within existing patterns | Partial ADM cycle (B–D update + E–F revision) |
| **Re-architecting** | Significant structural change, new patterns | Full or near-full ADM cycle |
| **Strategic** | Direction change driven by business or technology disruption | Full ADM cycle, new Architecture Vision |

### Change Request Template

```
ARCHITECTURE CHANGE REQUEST

Reference:        [Unique ID]
Date:             [Date]
Requestor:        [Name, Role]
Source:           [Business driver / Technology change / Lessons learned /
                   Regulatory / Performance]

CHANGE DESCRIPTION
  Current state:    [What exists today]
  Proposed change:  [What would change]
  Affected domains: [Business / Data / Application / Technology]

IMPACT ASSESSMENT
  Architecture Vision impact:     [Yes / No — detail if yes]
  Architecture Roadmap impact:    [Work packages affected]
  Architecture Contracts impact:  [Contracts requiring amendment]
  Standards impact:               [Standards Catalog updates required]
  Repository impact:              [Artifacts requiring update]

CLASSIFICATION
  Change class:     [Simplification / Incremental / Re-architecting / Strategic]
  Recommended ADM response:       [Maintenance / Partial cycle / Full cycle]

URGENCY
  [ ] Standard (next board cycle)
  [ ] Urgent (< 5 business days)
  [ ] Emergency (< 48 hours)

ARCHITECTURE BOARD DECISION
  Decision:         [Approved / Rejected / Deferred]
  ADM cycle triggered:    [Yes / No — reference new Statement of Architecture Work]
  Board Chair sign-off:   [Signature / Date]
```

---

## Architecture Maturity Assessment {#maturity}

### ACMM-Aligned Maturity Levels

| Level | Name | Characteristics |
|---|---|---|
| 0 | **None** | No architecture practice; ad hoc decisions |
| 1 | **Initial** | Informal architecture activity; no standards, no governance |
| 2 | **Under Development** | Architecture processes defined but inconsistently applied |
| 3 | **Defined** | Consistent process, Architecture Board in place, standards catalog maintained |
| 4 | **Managed** | Metrics-driven governance; compliance tracked; repository actively used |
| 5 | **Optimizing** | Continuous improvement; architecture drives business strategy; full traceability |

### Assessment Domains

Rate each domain 0–5:

| Domain | Assessment Questions |
|---|---|
| **Architecture Process** | Is the ADM followed? Are phases documented and gated? |
| **Architecture Content** | Are artifacts produced, maintained, and accessible? |
| **Architecture Governance** | Is the Architecture Board empowered? Is compliance tracked? |
| **Architecture Repository** | Is the repository populated, versioned, and used by delivery? |
| **Architecture Linkage** | Does architecture drive IT investment and portfolio decisions? |
| **IT Security** | Is security architecture integrated into the EA practice? |
| **Architecture Skills** | Are architects qualified? Is a CoE or guild model in place? |

### Maturity Assessment Output
- Domain scores (0–5) with evidence
- Priority improvement recommendations (top 3)
- Target maturity level and timeline
- Governance gaps requiring immediate remediation

---

## Governance in Scaled / Agile Contexts {#scaled}

### Architecture Board → Architecture Guild / Chapter

In SAFe or LeSS environments, the Architecture Board function is typically
distributed:

| Traditional Role | Agile Equivalent |
|---|---|
| Architecture Board | Architecture Guild / Community of Practice |
| Architecture Contract | Definition of Done + Architecture NFRs in PI objectives |
| Compliance Review | Architecture review ceremony (per PI or sprint) |
| Dispensation | Architecture Debt backlog item with time-box |
| Architecture Change Request | Architecture spike or enabler epic |

### Governing Principles for Agile Contexts
- **Intentional architecture** sets guardrails; **emergent design** operates
  within them — don't conflate the two
- Architecture runway must stay 1–2 PI increments ahead of delivery
- NFRs (non-functional requirements) are the primary compliance mechanism;
  embed them in the Definition of Done
- Architecture debt must be visible in the programme backlog and prioritized
  alongside features — not deferred indefinitely
- The Architecture Guild does not replace the Architecture Board for strategic
  or cross-programme decisions; escalation path must remain clear

### Federated Architecture Governance

For multi-divisional or geographically distributed enterprises:

| Level | Scope | Authority |
|---|---|---|
| **Enterprise Architecture Board** | Cross-division standards, enterprise principles | Final authority on cross-cutting decisions |
| **Segment / Domain Board** | Division or domain-specific standards | Authority within segment; must escalate cross-segment impacts |
| **Programme Architecture Review** | Programme-level compliance | Delegated from Segment Board |

Federated governance requires:
- Explicit escalation triggers (what forces a decision to enterprise level)
- Shared Architecture Repository with segment partitioning
- Cross-segment standards reconciliation process (at least annually)
