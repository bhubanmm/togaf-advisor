# TOGAF Advisor Skill — Decision Support

A Claude skill that provides expert-level enterprise architecture decision
support grounded in the TOGAF 10 framework. Designed for practicing architects
who want a peer-level advisor — not a textbook explainer.

---

## What This Skill Does

When installed, this skill activates Claude as a TOGAF-fluent enterprise
architect focused on **decision support and recommendations**. It covers all
major TOGAF domains and is calibrated for practitioners who already speak the
framework natively.

Every response:
- Leads with a clear architectural recommendation
- Anchors reasoning to ADM phases, Content Framework artifacts, or governance
  mechanisms
- Closes with a **Suggested Artifacts** section listing the specific matrices
  and diagrams relevant to the decision

---

## Domain Coverage

| Domain | Scope |
|---|---|
| **ADM** | All phases (Preliminary through H) plus Requirements Management; iteration patterns; agile ADM adaptation |
| **Architecture Content Framework** | Full artifact catalog — catalogs, matrices, diagrams; ABB → SBB traceability; deliverable structuring |
| **Enterprise Continuum & Repository** | Continuum classification; Repository governance; TRM and III-RM as reference baselines |
| **TOGAF Reference Models** | TRM platform taxonomy; III-RM integration patterns; mapping cloud-native stacks to TRM service categories |
| **Architecture Governance & Capability** | Architecture Board operations; compliance reviews; architecture contracts; dispensation process; maturity assessment (ACMM-aligned); federated and agile governance |

---

## When It Triggers

The skill activates on any of the following:

- ADM phase planning, review, or gate decisions
- Architecture governance decisions (compliance, dispensations, change requests)
- Stakeholder concern resolution and requirements tracing
- Fit-gap analysis against Content Framework artifacts
- Transition architecture sequencing and roadmap planning
- Capability assessments and maturity evaluations
- SBB/ABB selection rationale
- Architecture Repository structuring
- Technology decisions evaluated through a TOGAF lens

It also triggers when TOGAF is not explicitly mentioned but the underlying
question is architectural in nature — platform decisions, integration patterns,
portfolio rationalization, and so on.

---

## Output Structure

For each decision, the skill follows a six-step workflow internally:

1. **Frame** — ADM phase and domain(s) in scope
2. **Concern** — stakeholder concerns and architecture requirements
3. **Baseline** — relevant constraints and current-state facts
4. **Options** — 2–3 architecturally distinct alternatives with tradeoff analysis
5. **Recommend** — single clear recommendation with TOGAF anchoring
6. **Governance** — compliance path, roadmap impact, Architecture Board considerations

Output format adapts to the question type:

| Question Type | Format |
|---|---|
| Single architectural question | Recommendation + rationale |
| Options evaluation | Comparison table + recommendation |
| Phase planning | ADM checklist with decision gates |
| Governance scenario | Compliance path + Board brief |
| Roadmap / transition | Work package sequence with dependency flags |

All responses close with a **Suggested Artifacts** section covering relevant
matrices (analytical instruments, produced first) and diagrams (communication
instruments, produced after).

---

## Installation

1. Download `togaf-advisor.skill`
2. Open Claude at [claude.ai](https://claude.ai)
3. Navigate to **Settings → Skills**
4. Click **Install Skill** and select the downloaded `.skill` file
5. Confirm installation — the skill will appear in your active skills list

The skill is now active across all conversations. No further configuration required.

---

## How to Use It

### Starting a session
Just describe your architecture problem naturally. You do not need to invoke
the skill explicitly — it activates automatically when your query is
architectural in nature.

**Effective prompt patterns:**

| Situation | Example Prompt |
|---|---|
| ADM phase decision | *"I'm in Phase E with four capability gaps from Phase D. How do I sequence these into transition architectures?"* |
| Governance question | *"A programme wants to deploy a SaaS platform on an unapproved cloud provider. They're six weeks from go-live. How do I handle this?"* |
| Artifact selection | *"I need to demonstrate the impact of retiring three legacy CRM applications to business stakeholders. What artifacts should I produce?"* |
| Maturity assessment | *"Our CIO wants to understand where our EA practice stands. We have a board and some ADM documentation but no compliance process. How do I frame this?"* |
| Options evaluation | *"Should we use an API gateway, ESB, or event mesh as our primary integration pattern? We're a hybrid cloud enterprise."* |
| Standards question | *"How do I map our AWS and Azure footprint onto TRM service categories for the Technology Architecture?"* |

### Getting the best results
- **Provide context on your baseline.** The skill distinguishes Baseline from
  Target Architecture — the more you describe current-state constraints, the
  sharper the recommendation.
- **State the stakeholder concern.** Who is asking, and what decision do they
  need to make? This drives the output format and artifact selection.
- **Specify the ADM phase if known.** It focuses the response and eliminates
  phase-selection reasoning you don't need.
- **Ask for a Board-ready brief if needed.** The skill can produce Architecture
  Board brief format directly — just ask.

### Reading the output
Every response is structured as:
1. A clear **recommendation up front** — never buried
2. **Reasoning** anchored to TOGAF constructs (phase, artifact, governance mechanism)
3. A **Suggested Artifacts** section at the close — matrices listed before
   diagrams, reflecting production order, with a Primary artifact marked

---

## File Structure

```
togaf-advisor/
├── README.md                        ← This file
├── SKILL.md                         ← Core skill instructions and behavior
└── references/
    ├── adm-phases.md                ← All ADM phases: artifacts, decisions, gates
    ├── content-framework.md         ← Full artifact catalog, metamodel, deliverables
    └── governance.md                ← Board operations, contracts, compliance,
                                        dispensations, maturity assessment
```

Reference files are loaded selectively — only the file relevant to the current
task is pulled into context.

---

## TOGAF Version

Defaults to **TOGAF 10**. Where a user's context implies TOGAF 9.2 (legacy
tooling, older certification references), version differences are flagged where
they materially affect the recommendation.

---

## Iteration Notes

This is v1.0. Planned areas for future iteration:

- Cross-domain traceability scenarios (concern → Phase B → Phase D decision chain)
- Incomplete information handling — explicit guidance on when to ask a clarifying
  question vs. flag unknowns inline
- Extended artifact templates for ADD, ARS, and Architecture Roadmap structures
