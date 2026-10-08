# Dependency Mapping and Briefing Reference

## Standard evidence record

| Field | Purpose |
|---|---|
| Source | Workbook, system export, interview, or verified observation |
| Scope | What the source does and does not contain |
| Node | Canonical system/form name plus stable ID |
| Status | Active, archived, unknown |
| Business owner | Process/policy owner |
| Technical owner | Configuration/change/access owner |
| Relationship | Form-to-form, external integration, manual handoff, or ownership boundary |
| Failure point | What can break |
| Impact | Customer, revenue, operations, security, or recovery effect |
| Evidence | Count, field, row, export, or user-confirmed fact |
| Assumption | Inference requiring validation |
| Next action | Observable discovery or remediation step |
| Target | Owner and date |

## Source-scope rule

A workbook with only `References` and `Referenced By` columns supports a form-to-form dependency map. It does not establish Zapier, Google Workspace, email, ClickUp, Freshservice, WeTravel, API, webhook, or manual dependencies. Those require separate discovery.

## Status-aware chart rules

- Active/In Use: include in the primary operational flow.
- Archived: place in a separate retention/recovery lane; do not treat as deleted.
- Unknown: use a distinct color and create a validation action.
- Use stable IDs to prevent duplicate names from collapsing into one node.
- Provide a simplified executive chart and a detailed all-node map.

## Minto meeting template

**BLUF:** [recommendation and time-bound action]

**Why:**
1. [business impact]
2. [visibility/control gap]
3. [recoverability/execution risk]

**Confirmed facts:** [source-backed items]

**Assumptions/unknowns:** [labeled inferences]

**Failure points and dependencies:** [short chain]

**Containment:** [what happens today]

**Improvement:** [what changes]

**Ownership:** business owner / technical owner / improvement owner

**Target dates:** [5/10/20 business-day milestones]

**Decision requested:** [specific approval or assignment]
