---
name: systems-architecture-meeting-briefs
description: "Use for systems-risk meeting briefs and dependency maps."
version: 1.0.0
author: Hermes Agent
license: MIT
platforms: [windows, linux, macos]
metadata:
  hermes:
    tags: [systems-architecture, cybersecurity, executive-briefing, dependency-mapping, risk, meeting-prep]
    related_skills: [productivity:meeting-action-items, productivity:weekly-review-planning, productivity:docx, productivity:pdf, productivity:xlsx]
---

# Systems Architecture Meeting Briefs

Use this workflow when converting system inventories, spreadsheets, process discoveries, or architecture findings into concise meeting notes, one-pagers, flowcharts, and decision-ready proposals.

## Core outcome

Produce a package that lets a decision-maker answer, quickly:

1. What is the recommendation?
2. Why does it matter now?
3. What evidence supports it?
4. What is fact versus assumption?
5. What fails and what depends on it?
6. Who owns the business process and who owns the technical control?
7. What happens next, by when, and how will completion be proven?
8. What decision or support is required?

## Minto Pyramid structure

Default to the Minto Pyramid Principle for meeting material:

1. **BLUF / answer first** — one clear recommendation or conclusion.
2. **Three grouped reasons** — usually impact, visibility/control gap, and recoverability/execution risk.
3. **Evidence** — facts, source, scope, and measured counts.
4. **Implications** — failure points, dependencies, and operational impact.
5. **Actions** — containment, improvement, owner, target date, and completion evidence.
6. **Decision requested** — the explicit approval, resource, owner, or policy choice needed.

Keep the executive one-pager to one page. Put detailed evidence, maps, and caveats in an appendix or separate artifact.

## Facts versus assumptions

Create two explicit sections:

### Confirmed facts

Only include facts directly supported by the source, the user, or a verified tool result. Examples:

- A workbook contains a specific number of rows/forms.
- A field is populated or absent.
- A user confirmed that IT controls form changes.
- A Zapier automation writes to an individual employee's My Drive.

### Assumptions to validate

Do not present inferred integrations, ownership, or failure modes as confirmed. Label them as assumptions or unknowns and turn them into discovery actions.

Examples:

- A form change may affect downstream workflows.
- A notification failure may be silent.
- A Zapier OAuth connection may be tied to an individual account.
- A form may have external ClickUp, Freshservice, or Google Workspace actions not represented in the source export.

## Spreadsheet dependency-map workflow

When a workbook contains form or system relationships:

1. Inspect all sheets, dimensions, headers, and populated columns before interpreting relationships.
2. Preserve stable IDs when names can duplicate.
3. Normalize references into canonical node keys such as `Name [ID]`.
4. Deduplicate edges and remove self-edges unless self-reference is meaningful.
5. Separate relationship types:
   - form-to-form references
   - external integrations
   - manual handoffs
   - ownership/change-control boundaries
6. Never infer external integrations from a form-to-form-only export.
7. State the scope explicitly: e.g. `Cognito form-to-form dependency map; external integrations pending discovery`.
8. If the source has status metadata, separate Active/In Use, Archived, and Unknown nodes.
9. Treat archived records as still in retention, backup, access-review, and recovery scope unless deletion is verified.
10. Produce both:
    - a detailed map containing all normalized nodes and directional edges
    - a simplified executive flow showing the principal process, external handoffs, and control points

## External integration discovery

A metadata export commonly omits Zapier, email, Drive, ClickUp, Freshservice, WeTravel, webhooks, and API connections. Build a separate integration inventory with:

- Form/system ID
- Business owner
- Technical owner
- Active/archived status
- Data classification
- Trigger
- Destination system/folder
- Zapier automation or OAuth connection
- Notification recipients
- Manual handoff
- Failure signal and alerting
- Backup/export status
- Retention
- Change authority
- Recovery procedure

For a discovered individual My Drive destination, treat it as an ownership and continuity risk even if the automation currently works. Preserve the configuration before changing it; evaluate an organization-owned Shared Drive and controlled integration identity.

## Ownership model

Keep business and technical ownership distinct:

- **Department director/business owner:** owns the business requirement, policy, and hiring/process decision.
- **IT/technical owner:** owns form/system configuration, integrations, changes, access, and rollback.
- **Improvement owner:** coordinates mapping, containment, documentation, and validation.

When a user names owners, use those names/roles exactly. Do not invent a business owner for an ambiguous process; mark it unresolved and make naming it a decision request.

## Risk framing

For each risk, state:

- Asset/process
- Failure point
- Dependency
- Business impact
- Security/privacy impact
- Current control
- Gap
- Containment
- Improvement
- Owner
- Target date
- Completion evidence

Prioritize realistic operational failure chains over generic security checklists.

## Privacy and evidence handling

When inspecting workbooks or exports:

- Ignore customer names, emails, phone numbers, addresses, payment details, travel details, health data, and free-text responses unless explicitly required.
- Use counts, IDs, folders, statuses, storage, entry totals, and relationship metadata instead.
- Never put personal data into executive notes, diagrams, filenames, or generated artifacts.
- State when the source does not contain enough information to confirm an external dependency.

## Artifact package

For a meeting deliverable, create:

- Concise Minto-style Word notes
- One-page PDF for leadership
- Simplified flowchart image for embedding
- Detailed flowchart as SVG/HTML or a multi-page artifact
- Optional source evidence appendix
- A ZIP package when direct office-file downloads are mis-associated on Windows

Validate:

- Word package health with a DOCX validator.
- PDF page count and metadata with a PDF reader.
- Spreadsheet-derived counts with a repeatable script.
- Flowchart legibility visually; correct arrow direction and legend.
- ZIP contents and file sizes before delivery.

## Meeting delivery sequence

For the agenda `identify area → visibility gap/impact → ownership/access/renewal/reliability → next steps/owner/date`:

1. Name one selected area, not the entire environment.
2. Give the BLUF in one sentence.
3. State the evidence and its source.
4. Separate confirmed facts from assumptions.
5. Walk failure points and dependencies.
6. State operational impact.
7. Agree on immediate containment before long-term redesign.
8. Assign business owner, technical owner, improvement owner, and target dates.
9. Define completion evidence.

## Pitfalls

- **Overclaiming a map:** form-to-form references are not proof of Google, Zapier, ClickUp, Freshservice, email, or WeTravel integrations.
- **Mixing active and archived data:** archived forms can contain material data and remain in backup/retention scope.
- **Conflating ownership:** the department director may own hiring requirements while IT owns every technical form change.
- **Leading with detail:** put the recommendation before the inventory.
- **Unlabeled inference:** label assumptions and convert them into discovery tasks.
- **Sending raw office files on Windows:** package them in a ZIP when the platform routes them to the wrong application.
- **Using unreadable diagrams:** provide a simplified executive flow and a separate detailed map.

## Reference

See `references/dependency-mapping-and-briefing.md` for a reusable field model, evidence checklist, and example output structure.
