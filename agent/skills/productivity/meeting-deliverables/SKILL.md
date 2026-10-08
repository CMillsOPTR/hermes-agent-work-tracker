---
name: meeting-deliverables
description: "Use for meeting briefs, one-pagers, and flowcharts."
version: 1.0.0
author: Hermes Agent
license: MIT
platforms: [windows, macos, linux]
metadata:
  hermes:
    tags: [meetings, executive-briefs, Minto, one-pagers, flowcharts, deliverables, documentation]
    related_skills: [docx, pdf, powerpoint, xlsx, meeting-action-items]
---

# Meeting Deliverables

Create concise, evidence-grounded meeting packages for operational, systems-architecture, cybersecurity, and process-improvement discussions. Produce the appropriate combination of speaking notes, a one-page handout, dependency diagrams, and downloadable source files.

## When to Use

Use when the user needs to:

- Prepare for a deliverables, leadership, systems, cybersecurity, or architecture meeting.
- Turn operational findings into a brief, one-pager, proposal, or pitch deck.
- Convert a spreadsheet or system inventory into a dependency map or flowchart.
- Separate confirmed facts from assumptions and unknowns.
- Define containment, improvement, owner, target date, and success evidence.
- Package Word/PDF/PowerPoint/diagram artifacts for download.

## User-facing style

- Prefer concise, meeting-ready documents over long explanatory prose.
- Use the **Minto Pyramid Principle**: answer/BLUF first, then grouped reasons, then evidence and actions.
- Put the decision requested near the top or immediately after the BLUF.
- Use tables for owners, dates, risks, and decisions.
- Keep executive materials readable in under five minutes unless the user requests a detailed appendix.
- Separate **Confirmed facts**, **Assumptions to validate**, and **Unknowns**; never present inferred relationships as confirmed.

## Core procedure

### 1. Identify the decision and audience

Capture:

- Meeting purpose and audience
- Decision or agreement required
- Selected vendor, dependency area, or process
- Required deliverables: speaking notes, one-pager, deck, flowchart, appendix
- Deadline and delivery format

If the user has not selected an area, recommend the area with the highest combination of business impact, dependency centrality, lack of recovery, and undocumented manual work.

### 2. Establish evidence before framing the recommendation

Use the source-of-truth artifact first: workbook, system export, repository, notes, or user-confirmed facts. For dependency spreadsheets:

- Preserve IDs where available; do not conflate duplicate names.
- Parse both upstream/reference and downstream/referenced-by columns.
- Deduplicate edges.
- Report node count, edge count, linked nodes, isolated nodes, and central nodes.
- State the relationship-direction interpretation explicitly.
- Treat missing relationships as unknown, not as proof of no dependency.

### 3. Build the Minto pyramid

Use this sequence:

1. **BLUF / Answer:** one or two sentences stating the recommendation.
2. **Key reasons:** usually three grouped arguments, not a long list.
3. **Evidence:** confirmed facts supporting each reason.
4. **Implications:** operational, security, reliability, financial, or customer impact.
5. **Actions:** containment first, then improvement.
6. **Owner/date:** name accountable business and technical owners separately.
7. **Decision request:** state exactly what leadership must approve or assign.
8. **Success measure:** define observable completion evidence.

### 4. Model ownership correctly

Distinguish:

- **Business/process owner:** owns policy, requirements, and outcomes.
- **Technical/system owner:** controls configuration, changes, integrations, and recovery.
- **Improvement owner:** coordinates mapping, containment, documentation, and implementation.
- **Approver:** authorizes risk acceptance, budget, migration, or policy decisions.

Do not collapse a department director, IT, and project coordinator into one owner unless the evidence supports it. A common pattern is: department director owns business/hiring requirements; IT owns the form and technical change authority; the named improvement owners coordinate remediation.

### 5. Walk the failure path

For the selected process or dependency, cover:

- Intake/submission failure
- Notification/routing failure
- Data mapping or handoff failure
- Downstream dependency failure
- Manual workaround and single-person dependency
- Access/ownership failure
- Backup/export/recovery failure
- Detection and escalation gap

Translate each failure point into business impact without overstating certainty.

### 6. Produce the artifacts

Recommended package:

- **Speaking notes:** Minto structure with facts, assumptions, failure points, decisions, and script.
- **One-page PDF:** BLUF, three reasons, action table, owner/date, decision request.
- **Detailed flowchart:** all source entities and relationships, with IDs preserved.
- **Simplified flowchart:** business-readable path showing the main system/process chain and control points.
- **Optional deck:** only when the user needs leadership presentation rather than a handout.

Use a detailed appendix for large inventories; do not force hundreds of nodes into a tiny unreadable executive page.

### 7. Validate before delivery

- DOCX: validate package health and read back structure/text.
- PDF: verify it is one page when requested, not encrypted, and has a text layer.
- PPTX: read back outline, slide count, notes, and tables; render if LibreOffice/Poppler are available.
- Flowchart: inspect visually; verify arrow direction and label legibility.
- Cross-check counts in the diagram against the source analysis.
- Ensure every proposed action has an owner, target, and completion evidence.

### 8. Package for reliable download

On Windows, if direct `MEDIA:/...docx`, `.pdf`, or `.pptx` attachments are associated with Windows Media Player or otherwise open incorrectly, package the artifact in a ZIP and deliver the ZIP as the primary download. Include clear extraction instructions and keep the original file inside the archive.

For HTML deliverables that depend on adjacent JavaScript/CSS files, also create a self-contained browser version with dependencies embedded when users may open the HTML directly from a downloaded folder.

## Standard owner/action table

| Action | Business owner | Technical owner | Improvement owner | Target | Evidence |
|---|---|---|---|---|---|
| Contain changes | Department director | IT | Cody + DOIT | Today | Change log and approval rule |
| Map dependencies | Department directors | IT | Cody + DOIT | +5 business days | Reviewed dependency map |
| Document recovery | Department director | IT | Cody + DOIT | +10 business days | Tested runbook |
| Pilot improvement | Affected department | IT | Cody + DOIT | +20 business days | Test results and sign-off |

## Common risk framing

For an undocumented form/integration process, frame the risk as **silent failure and recoverability**, not merely "too many forms." For a user-owned My Drive destination, frame the risk as **ownership, access, continuity, retention, and backup dependency**. Do not claim that a Zapier-to-My-Drive flow is inherently wrong; verify the owner, OAuth connection, permissions, task history, failure alerts, retention, and business need first.

## Pitfalls

- Leading with background instead of the recommendation.
- Treating a large system list as an architecture without owners, dependencies, or decisions.
- Calling a missing relationship "no dependency" when it may be an inventory gap.
- Presenting inferred spreadsheet relationships as confirmed business logic.
- Recommending a migration before classifying customer-facing versus internal workflows.
- Treating a configured ClickUp instance as the problem when adoption and workflow fit are the actual problem.
- Treating Wix backup as the issue when the actual request is a fundraising-platform production map.
- Mixing business ownership with technical change authority.
- Delivering a beautiful but unreadable detailed diagram.
- Sending raw office files when the user's Windows environment mis-associates them; provide a ZIP fallback.

## Reference

See `references/minto-meeting-package.md` for a reusable Minto Pyramid outline, evidence/assumption matrix, dependency-map interpretation notes, and meeting-ready language.
