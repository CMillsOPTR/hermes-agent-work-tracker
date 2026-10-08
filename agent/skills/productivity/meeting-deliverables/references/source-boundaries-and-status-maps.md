# Source Boundaries and Status-Aware Dependency Maps

## Source scope

When the user restricts work to one authenticated Drive folder, inspect only that folder and its opened contents. A visible folder listing is not evidence of file contents. If individual files are not opened/readable, ask the user to open the relevant file or provide an export; do not infer content from filenames.

## Form metadata exports

A `form-details` workbook containing Title, Name, URL, ID, Folder, Entries, Storage, Payment, Encryption, Archived, References, and Referenced By supports:

- active/in-use versus archived separation
- folder and ownership-review prioritization
- entry/storage volume prioritization
- form-to-form relationship mapping
- duplicate-name disambiguation using IDs

It does **not** prove external integrations unless explicit destination fields exist. Do not infer Zapier, Google Workspace, email, ClickUp, Freshservice, WeTravel, API, or webhook dependencies from References alone. Build a separate external-integration inventory.

## Status-aware map rules

- Use distinct visual status classes: ACTIVE / IN USE, ARCHIVED, UNKNOWN.
- Keep archived nodes in the map; archived data remains in backup, retention, access-review, and recovery scope.
- Mark referenced identities that do not appear as source rows as UNKNOWN.
- Include a legend and report node/edge/status counts.
- Create a detailed appendix map and a simplified business flow; do not force the full graph into the executive diagram.
- Visually inspect arrow direction and label legibility before delivery.

## Ownership boundary

For Cognito onboarding and similar workflows:

- Department director owns business/hiring requirements.
- IT owns form configuration and all technical changes/moves.
- Named improvement owners coordinate containment, dependency mapping, documentation, and testing.

A Zapier handoff to an individual employee's My Drive is a separately confirmed external dependency requiring owner, OAuth, permissions, failure-alerting, retention, and backup review.
