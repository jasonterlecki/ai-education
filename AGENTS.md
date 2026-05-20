# AGENTS.md

Version: 1.5.2
Status: Active
Repository type: AI education knowledge base

## Goal

This repository is a shared knowledge base for AI-related information, practical guides, visual explainers, and reusable prompts that can be used by others.

The repository should help people understand AI safely and practically.  It should clearly distinguish between AI literacy, vibe coding for exploration, implementation planning, checkpointed execution, technical agent workflows, and enterprise governance.

## Scope

In scope:

- Markdown documentation about AI workflows, guidance, governance, and prompts.
- Static HTML education pages.
- Reusable prompt templates.
- Decision guides and visual explainers.
- Repo-level behavior rules for AI agents.
- Repository mapping in `CODEX.md`.
- Education index page at `index.html`.

Out of scope:

- Production application code.
- Infrastructure provisioning.
- Sensitive credential storage.
- Secrets, API keys, tokens, passwords, certificates, or private keys.
- Customer data, employee personal data, medical data, regulated records, or privileged internal material.
- Direct integrations with production systems.
- Unreviewed agent automation against external systems.

## Source of Truth for Repository Mapping

Use `CODEX.md` to track:

- File inventory.
- Each file's intended purpose.
- Current file version numbers.
- Page expertise levels.
- File status, such as planned, draft, active, or retired.

Before making non-trivial edits, review `CODEX.md` to confirm where the change belongs.

If a file is created, deleted, renamed, moved, or materially changed, update `CODEX.md` in the same change set.

## Source of Truth for Education Strategy

Use `PLAN_AI_EDUCATION.md` to track:

- Education goals.
- Expertise levels.
- Planned curriculum.
- HTML page requirements.
- Index page requirements.
- Visual language.
- Implementation phases.

Before creating new education pages, review the plan to ensure the new page fits the curriculum.

## Expertise Level Rules

Every governed education page must display a visible expertise level.

Allowed primary levels:

```text
Beginner
Intermediate
Advanced
Expert
```

Do not invent alternate primary levels such as "All Users" or "General".  If a page is useful to everyone, use `Beginner` and describe the broader audience separately.

HTML pages must include visible metadata near the top:

```text
Expertise: <level>
Audience: <audience>
Use when: <short purpose>
```

HTML pages should also include machine-readable metadata and an HTML comment for the version:

```html
<meta name="ai-education-level" content="Intermediate">
<meta name="ai-education-audience" content="AI committee, technical leads, business users">
<meta name="ai-education-version" content="1.0">
<!-- Version: 1.0 -->
```

Markdown guides must include a visible version and expertise level near the top.

## Visual Language Rules

The repository uses the `AI Field Guide` visual language.

The visual style should be:

- Vibrant but professional.
- Clear enough for beginners.
- Precise enough for technical and governance audiences.
- Friendly without becoming unserious.
- Visual, scannable, and committee-friendly.

Preferred visual patterns:

- Hero sections.
- Expertise badges.
- Metadata pills.
- Side-by-side comparisons.
- Decision strips.
- Risk cards.
- Fast decision matrices.
- Checklist panels.
- Prompt example cards.
- Version comments in HTML.

Avoid:

- Dense walls of policy text.
- Generic corporate grayness everywhere.
- Unlabeled risk levels.
- Tiny text or weak contrast.
- Overuse of animation.
- Hiding critical warnings in footnotes.

Use the visual language defined in `PLAN_AI_EDUCATION.md` when creating or editing HTML pages.

### Hero Badge and Eyebrow Rules

Generated pages must include a concise hero badge or eyebrow label that helps visitors immediately understand both the page level and the page's practical area of focus.

For standard education guide pages, use this pattern:

```text
[Expertise Level] Field Guide · [Focus Area]
```

For prompt-library pages, use this pattern:

```text
[Expertise Level] Prompt Library · [Focus Area]
```

Rules:

- Expertise level must be one of: Beginner, Intermediate, Advanced, Expert.
- Focus area must be 1 to 3 relevant words.
- Focus area describes the subject domain or practical category of the page, such as AI Literacy, Security, Governance, Architecture, Technical Practice, Prompting, Agents, Retrieval, Cost Control, or Documentation.
- The bracketed terms are placeholders only. Do not include the words "Expertise Level" or "Focus Area" in the visible badge text.
- Use the middle dot separator exactly as shown: `·`.
- Keep the badge short enough to fit comfortably in the hero section.
- Do not use the badge as a long description, subtitle, or marketing phrase.

Examples:

```text
Beginner Field Guide · AI Literacy
Intermediate Field Guide · Governance
Advanced Field Guide · Security
Expert Field Guide · Architecture
Beginner Prompt Library · Communication
Intermediate Prompt Library · Delivery Planning
Advanced Prompt Library · Technical Practice
Expert Prompt Library · Evaluation
```

### Hero Metadata Badge Rules

Generated AI Education pages should use short pill-style metadata badges near the bottom of the hero card. These badges must summarize practical page context, not repeat the page level.

Use these badge labels only for English pages:

```text
Core Skill:
Use:
Rule:
Risk:
```

Use these badge labels only for Canadian French pages:

```text
Compétence:
Usage:
Règle:
Risque:
```

Required badges:

- Core Skill or Compétence: what the reader will learn or practice.
- Use or Usage: when the reader should use the page or prompt.

Optional badges:

- Rule or Règle: only include when there is a clear practical rule that is central to the page.
- Risk or Risque: only include when a specific risk is highly relevant to the page.

Do not include hero metadata badges for:

- Skill Level
- Expertise Level
- Level
- Beginner / Intermediate / Advanced / Expert
- Page type
- Generic category labels that repeat the hero eyebrow

The expertise level already appears in the hero badge or eyebrow, so it should not be repeated in the hero metadata badges.

Badge examples:

```text
Rule: Do not paste sensitive data casually
Core Skill: Replace details with safe placeholders
Use: Images, docs, audio, screenshots
Risk: Token bonfires

Core Skill: Verify claims before reuse
Use: Summaries, reports, citations
Risk: Confident wrong answers

Core Skill: Break work into checkpoints
Use: AI coding agents and delivery plans
Rule: Stop after each phase

Core Skill: Compare model tradeoffs
Use: Vendor and tool selection
Risk: Hidden cost drift
```

Style requirements:

- Keep each badge short and scannable.
- Prefer plain language over abstract labels.
- Use sentence case after the label.
- Do not make the badges full sentences unless needed for clarity.
- Avoid more than four hero metadata badges.
- Prefer two or three badges for most pages.
- Do not invent dramatic risks if the risk is not central to the page.
- Use "Rule" and "Risk" sparingly.

## Static HTML Rules

HTML pages are static education artifacts.  They should not require a build step unless the repository later explicitly adopts one.

Rules:

- Use semantic HTML.
- Use one clear `h1` per page.
- Include expertise metadata.
- Include machine-readable version metadata and an HTML version comment.
- Keep pages responsive.
- Keep pages readable when printed.
- Do not add external scripts without explicit approval.
- Avoid JavaScript unless it materially improves the education page.
- Do not add tracking scripts.
- Do not add forms that collect data.
- Do not add secrets or internal endpoints.

Links from `index.html` to internal guide pages should use same-tab navigation:

```html
<a href="pages/en/example.html">Open guide</a>
```

Do not use `_blank` targets for internal education-page navigation.

Every HTML page under `pages/en/` should include a previous/home/next navigation card immediately after the hero section and again after the takeaway card. Use `NAVIGATION.md` as the canonical source of truth for page order.

When adding or renaming an HTML page, update `NAVIGATION.md`, `index.html`, and `CODEX.md` in the same change set.

## File Versioning Rules

All governed documentation files should include a version.

HTML files must keep version numbers as HTML comments and machine-readable metadata, not visible page text.

Markdown files must keep version numbers visible near the top.

Default:

- If no version exists, initialize it to `1.0`.

Change classification must be determined before finalizing edits.

### 1. Minor Change

Definition:

- Simple additions or removals that do not materially change intent.
- Typos, small clarifications, small link fixes, or small card additions.

Version bump:

- Increment the third segment.
- Example: `1.0` -> `1.0.1`.
- Example: `1.1.2` -> `1.1.3`.

If the file only has two segments, add the third segment when making a minor change.

### 2. Major Change

Definition:

- Significant section additions or removals.
- Meaningful structural changes.
- New page modules.
- Major rule changes.
- New curriculum categories.

Version bump:

- Increment the second segment and reset the third segment if present.
- Example: `1.1` -> `1.2`.
- Example: `1.1.4` -> `1.2.0`.

### 3. Full Change

Definition:

- Near-complete document rewrite.
- Major shift in intent.
- Major restructuring that makes the prior version meaningfully obsolete.

Version bump:

- Increment the first segment and reset lower segments.
- Example: `1.4` -> `2.0`.
- Example: `1.4.9` -> `2.0.0`.

Commit message requirement:

- Mark the change as `FULL` in the commit message and changelog notes if a changelog exists.

## Change Governance: Git

After each completed change set:

1. Stage updates.
2. Commit with a relevant message describing what changed and why.
3. Push to the active remote branch.

Rules:

- Do not force-push.
- Keep commits focused and scoped to the implemented change.
- Include version bump rationale in the commit message when versions change.
- Do not combine unrelated curriculum additions in one large commit unless explicitly requested.
- Do not proceed to the next implementation phase unless explicitly instructed.

Suggested command pattern:

```sh
git status
git add AGENTS.md CODEX.md PLAN_AI_EDUCATION.md index.html pages docs assets examples
git commit -m "Add AI education repository foundation"
git push
```

Adjust staged files to match the actual change set.

## Required Update Flow for Agents

For every change:

1. Read `AGENTS.md`.
2. Review `CODEX.md` to locate the correct file and current version.
3. Review `PLAN_AI_EDUCATION.md` when adding or changing curriculum structure.
4. Determine if the change is Minor, Major, or Full.
5. Update the edited file version accordingly.
6. Update `CODEX.md` so file purpose, version, status, and expertise entries remain accurate.
7. Update `index.html` when page links, page status, or page titles change.
8. Perform validation checks appropriate to the edited files.
9. Stage, commit, and push with a focused message unless the user explicitly says not to.
10. Stop and summarize changes, validation, assumptions, and blockers.

## Checkpointed Execution Rules

Use checkpointed execution for non-trivial work.

Default rule:

```text
Implement one phase only.
Stop after completing that phase.
Summarize changed files, validation commands, assumptions, and blockers.
Do not proceed to the next phase until explicitly instructed.
```

Do not implement a whole multi-phase plan in one pass unless the user explicitly asks for that and the work is small enough to be safely reviewed.

When a user says "implement the plan," interpret that as:

```text
Implement the next incomplete phase only, unless the user explicitly says to implement all phases.
```

When editing a complex page or document, avoid broad rewrites.  Prefer focused changes that preserve existing structure unless a Full change is requested.

## AI Education Content Rules

Content should:

- Educate rather than hype.
- Separate exploration from implementation.
- Encourage review, verification, and human accountability.
- Use practical examples.
- State risks plainly.
- Avoid pretending AI output is automatically correct.
- Avoid telling all users to use vibe coding for production work.
- Encourage role-appropriate use.
- Provide clear escalation from Beginner to Expert.

Content should not:

- Encourage unreviewed production changes.
- Encourage pasting secrets or sensitive data into AI tools.
- Present AI as a replacement for accountable human decision-making.
- Make legal, medical, HR, security, or compliance claims without review guidance.
- Assume all users are technical.
- Assume all technical users are authorized to use AI agents on real repositories.

## Prompt Library Rules

Prompt templates should include:

```text
Version
Purpose
Expertise level
Use when
Do not use when
Prompt template
Example input
Expected output
Review checklist
```

Prompts that involve implementation must include:

```text
Inspect before editing.
Implement one phase only.
Do not make unrelated changes.
Run validation.
Stop and report.
```

Prompts that involve sensitive or regulated topics must include a caution that the output requires human review and may require official process review.

## Markdown Style

Markdown should be easy to scan.

Use:

- Clear headings.
- Short paragraphs.
- Tables where they improve comparison.
- Code fences for prompts and examples.
- Checklists for review steps.
- Plain language.

Avoid:

- Overly long paragraphs.
- Unexplained jargon.
- Unsupported claims.
- Hidden assumptions.
- Duplicating large sections across many files when a cross-reference is better.

## HTML Style

HTML pages should be self-contained unless a shared asset has been intentionally introduced.

Before extracting shared CSS, confirm that at least three pages use the same patterns.  Do not prematurely create a complex front-end framework.

Do not introduce:

- React.
- Build tooling.
- Package managers.
- External JavaScript dependencies.
- Analytics.
- Forms.

unless the user explicitly approves a repository direction change.

## Validation Expectations

Before considering work complete:

- Confirm Markdown renders cleanly.
- Run Markdown linting if configured: `[TO_FILL]`.
- Ensure `AGENTS.md` and `CODEX.md` stay consistent with actual repository contents.
- Open changed HTML files locally when possible.
- Check internal education navigation links do not use `_blank`.
- Check each changed page-level previous/home/next navigation card matches `NAVIGATION.md`.
- Check each changed education page has a visible expertise level.
- Check each governed file has the required version format: HTML comment and metadata for HTML files, visible version for Markdown files.
- Run `git diff --check` before committing.

Suggested validation commands until tooling is configured:

```sh
git diff --check
find . -name "*.md" -maxdepth 4 -print
find . -name "*.html" -maxdepth 4 -print
```

If markdownlint is later configured, replace `[TO_FILL]` with the exact command.

## Security and Privacy Rules

Never add:

- Secrets.
- Tokens.
- API keys.
- Passwords.
- Private certificates.
- Customer data.
- Employee personal data.
- Sensitive incident details.
- Unapproved internal documents.

If a user asks to include sensitive details, summarize or anonymize them instead.

If a file appears to contain secrets, stop and report the issue before proceeding.

## Repository Map Discipline

`CODEX.md` is not optional bookkeeping.  It is the navigation chart for humans and AI agents.

Update it when:

- A file is added.
- A file is removed.
- A file is renamed.
- A file version changes.
- A file purpose changes.
- A page expertise level changes.
- A page status changes.

## Completion Response Format

When an agent completes work, respond with:

```text
Completed: <short summary>
Files changed:
- <file>: <change>
Validation:
- <command or manual check>: <result>
Version updates:
- <file>: <old> -> <new>, <Minor/Major/Full>
Assumptions:
- <assumption, if any>
Blockers:
- <blocker, if any, or None>
```

Do not claim validation was performed unless it actually was.
