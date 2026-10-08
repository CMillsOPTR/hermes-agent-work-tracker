---
name: corporate-training-artifacts
description: "Use for corporate training decks and handbooks."
version: 1.0.0
author: Hermes Agent
license: MIT
platforms: [windows, macos, linux]
metadata:
  hermes:
    tags: [training, onboarding, powerpoint, docx, cybersecurity-awareness, customer-service]
    related_skills: [productivity:powerpoint, productivity:docx, productivity:pdf, research:grounded-citations]
---

# Corporate Training Artifacts

Create practical onboarding and awareness materials for mixed audiences: frontline operations, sales, marketing, administration, IT, managers, and leadership.

## Trigger

Use when the user asks for a training handbook, facilitator guide, trainee walkthrough, onboarding schedule, corporate training deck, policy-awareness material, or a multi-format training package.

## Core approach

1. **Start with the audience and job behavior.** Identify what the learner must do, what decisions they may make, what they must document, and when they must stop and escalate.
2. **Use authoritative source material.** Apply current company T&C, policies, approved forms, and internal resources. Treat external regulations/frameworks as applicability guidance unless the organization has made a formal determination.
3. **Separate roles.** The facilitator guide teaches how to demonstrate, coach, observe, and score. The trainee guide gives concrete steps, checks, escalation triggers, and practice cases. Do not produce two copies of the same deck.
4. **Use plain language and match requested brevity.** When the user asks for a checklist, make it literally a checklist: short action-oriented checkbox items, minimal explanation, clear section headings, and no long narrative. Prefer “What this tool is for,” “What to do,” “What to write down,” “Who approves this,” and “When to stop and ask for help” over abstract labels such as “operating model,” “governance,” “control point,” or “readiness decision.” Explain technical terms only when necessary.
5. **Combine related artifacts when requested.** If the user asks to turn a checklist into a deck, put role/team introductions first, then preserve the checklist as distinct onboarding slides. Do not replace checklist tasks with a high-level summary.
6. **Build from explicit slide/content specifications.** Do not automatically extract and reflow an earlier deck as the final design. Reflow can duplicate footers, create awkward wording, and produce random or context-free sections. Write each slide/module intentionally.
6. **Make the visual system consistent.** When a brand emblem or palette is supplied, extract only usable brand cues and ignore incidental screenshot/page background. For the black/white/red shield style used by this user: black provides structure, white provides readability, and red marks action, warning, escalation, or approval.
7. **Balance content density.** Prefer a consistent three-part slide structure: context/purpose, specific steps, and check/stop/escalate. Split dense content across slides instead of shrinking text until it is technically contained but uncomfortable to present.
8. **Use scenario-based instruction.** Include realistic cases, especially money/refunds, customer communications, privacy, failed automation, missing handoffs, vendor issues, and publication/approval gates.
9. **Make financial and policy rules explicit.** Put formulas and worked examples on their own slide. For this customer-service context, teach that refund is the amount paid toward the trip minus TPP cost minus 20% of total package price; TPP is non-refundable; no refund or exception is promised without authorization.
10. **Include presenter notes.** Facilitator decks should have slide-specific coaching prompts, answer keys, and assessment cues. Generic notes on every slide are insufficient.
11. **When combining decks, preserve the requested source treatment.** If the user names an in-progress deck as the visual source, match its aspect ratio, palette, layout rhythm, and logo placement; use the newer approved emblem as an intentional asset replacement rather than inventing a different visual system. Merge content by topic and remove duplicate section/title slides.
12. **Design for the requested runtime.** A near-hour awareness session needs pacing support: short content slides, section transitions, discussion prompts, scenario practice, and a knowledge check. Put approximate timing and facilitation prompts in speaker notes; do not fill slides with prose just to increase slide count.
13. **Separate training modules cleanly.** If a separate cybersecurity deck already exists, a team-introduction/onboarding deck should reference it as a completion item rather than reproducing its threat, framework, or AI-training content. Conversely, a combined CYSEC deck should include the full awareness content and an explicit AI-safe/AI-unsafe section.

## Required content patterns

### Facilitator guide

- Training objective and learner contract
- What each system is for
- Demonstration steps per system
- Questions to ask the trainee
- Expected behavior and failure cases
- Policy/T&C answer key
- Scenario lab
- Scoring rubric and readiness decision

### Trainee walkthrough

- Start-here role and authority boundaries
- Universal request workflow
- Step-by-step system procedures
- Plain-language policy rules
- Stop/escalate triggers
- Documentation checklist
- Practice cases
- Final self-check

### Company-wide security awareness

Include role-specific handling for PII, registration, payment, travel documents, health information, employee data, credentials, AI use, phishing, privacy exposure, and incident reporting. Explain that HIPAA, PCI DSS, GDPR, CCPA/CPRA, and FERPA may apply conditionally; never claim organizational compliance solely because a control exists.

## QA and verification

Before delivery:

- Run `pptx_read.py --outline` and confirm slide count, titles, body text, notes, and distinct facilitator/trainee roles.
- Confirm every content slide has a consistent layout and autosizing; inspect for duplicate footer text, accidental placeholder text, and awkward global replacements.
- Validate DOCX/PDF packages with the relevant document tools.
- If rendering tools are available, render every slide and inspect actual images. XML geometry is not a substitute for a projector/PowerPoint check; explicitly disclose when visual rendering was unavailable.
- Send the completed candidate to QA JIM for independent review. Treat findings as release blockers until fixed and re-reviewed.
- Package final artifacts with corporate, Google-Drive-friendly filenames. Keep draft/candidate/QA-fixed variants distinct so the user does not confuse them.

## Pitfalls

- Do not call a deck “final” before independent QA and the user’s internal approval.
- Do not bury the BLUF or decision request after background material.
- Do not use corporate jargon in frontline training.
- Do not teach a policy rule only by implication; show the formula, trigger, authority, and documentation requirement.
- Do not let a global text replacement change context-dependent phrases (for example, turning “Check the current T&C” into “Check your work T&C”). Re-read extracted slide text after replacements.
- Do not conflate business ownership with technical ownership. Department directors may own business/hiring requirements while IT controls form changes and publication.
- Do not treat an internal form-to-form dependency map as a complete integration map. External Zapier, Google Workspace, email, ClickUp, Freshservice, WeTravel, APIs, and manual handoffs need a separate inventory.
- Do not include personal/customer data in training examples unless explicitly necessary and approved; prefer synthetic examples.

## Supporting reference

See `references/training-artifact-checklist.md` for a reusable pre-delivery checklist.
