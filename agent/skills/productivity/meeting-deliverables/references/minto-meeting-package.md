# Minto Meeting Package Reference

## Executive one-pager outline

1. **BLUF / Recommendation** — state the answer, owner, and target date.
2. **Why now** — group into three reasons: business impact, visibility/control gap, and recoverability/reliability.
3. **Evidence** — separate confirmed facts from assumptions and unknowns.
4. **Containment** — actions that reduce risk today without waiting for redesign.
5. **Improvement** — durable process, architecture, or control change.
6. **Owner / target table** — business owner, technical owner, improvement owner, target date, completion evidence.
7. **Decision requested** — one explicit approval or assignment.
8. **30-second close** — a spoken version of the recommendation.

## Evidence and assumption matrix

| Category | Example language |
|---|---|
| Confirmed fact | The workbook lists Employee Onboarding [64] as a reference/dependency for multiple forms. |
| Inferred risk | A change may affect downstream workflows; validate with owners and test cases. |
| Unknown | The current Zapier owner, OAuth connection, failure alerting, and retention behavior are not yet confirmed. |

## Dependency spreadsheet method

- Preserve form IDs to avoid conflating duplicate names.
- Parse both `References` and `Referenced By` columns.
- Use `Referenced By` for the direct downstream view and `References` for upstream prerequisites, while clearly stating the interpretation.
- Deduplicate edges and report node/edge counts.
- Use a simplified diagram for leadership and a full appendix map for technical follow-up.
- Label isolated/no-recorded-link nodes as **unvalidated**, not independent.

## Ownership language

Use the following pattern when business and technical authority are separate:

> The department director owns the business requirements and hiring/process outcome. IT owns the form configuration, integrations, technical changes, and recovery controls. Cody + DOIT own the initial mapping, containment, documentation, and improvement effort.

## Meeting-ready risk language

For form and integration processes, emphasize **silent failure, dependency blast radius, and recoverability**. For files landing in an individual employee's My Drive through Zapier, state that the design may be intentional but creates an ownership, access, continuity, retention, and backup dependency that must be verified before changing it.

## Download packaging

If Windows associates direct DOCX/PDF/PPTX attachments with the wrong application, place the original artifact in a ZIP and deliver the ZIP as the primary download. Keep a readable filename inside the archive and include extraction instructions.