# CODEX.md

Version: 1.3
Status: Draft repository map
Repository type: AI education knowledge base

## Purpose

This file is the repository map and source-of-truth inventory for the AI education knowledge base.

Use this file to understand:

- Which files exist or are planned.
- What each file is for.
- Which expertise level each education page targets.
- What version each governed file currently has.
- Which files must be updated together.

Before making non-trivial edits, read this file and confirm where the change belongs.

## Repository Goal

This repository educates users about AI usage from Beginner to Expert levels.  It should help people understand practical AI workflows, safe prompting, vibe-style exploration, implementation planning, checkpointed execution, AI-assisted technical work, governance, and enterprise AI operating models.

The repository should consistently reinforce this distinction:

```text
Vibe coding is useful for exploration.
Implementation planning is required for real systems.
Checkpointed execution is required for controlled AI-agent work.
```

## Governed File Rules

All governed documentation files must have a visible version.

Governed files include:

```text
AGENTS.md
CODEX.md
PLAN_AI_EDUCATION.md
README.md
index.html
pages/*.html
docs/**/*.md
examples/**/*.md
```

When a governed file changes, update its visible version and update this inventory.

Version rules are defined in `AGENTS.md`.

## Expertise Level Taxonomy

Allowed primary expertise levels:

| Level | Audience | Notes |
| --- | --- | --- |
| Beginner | Everyone, new AI users, casual business users | Safe everyday use, review, privacy, basic prompts |
| Intermediate | Frequent AI users, team leads, analysts, business power users | Structured prompting, workflow design, vibe vs. implementation decisions |
| Advanced | Developers, cloud engineers, security, QA, architects, technical leads | Code, repositories, tests, implementation plans, technical guardrails |
| Expert | AI committee, senior architects, governance, platform owners, security leadership | Operating model, evaluation, agentic governance, architecture, risk |

Do not create alternate primary levels without updating `AGENTS.md` and `PLAN_AI_EDUCATION.md`.

## Current File Inventory

### Root Files

| File | Version | Status | Expertise | Purpose | Update Notes |
| --- | --- | --- | --- | --- | --- |
| `AGENTS.md` | 1.1 | Active | N/A | Defines repository rules for AI agents, versioning, validation, scope, checkpointed execution, and content governance | Update when agent behavior, version rules, validation, or repo scope changes |
| `CODEX.md` | 1.3 | Active | N/A | Repository map, file inventory, page status, versions, and expertise mapping | Update for every file add, delete, rename, version change, page status change, or purpose change |
| `PLAN_AI_EDUCATION.md` | 1.0 | Active | N/A | Detailed plan for the AI education repository, curriculum, visual language, index page, and implementation phases | Update when the education strategy or planned curriculum changes |
| `README.md` | Planned | Planned | Beginner | Short public-facing overview of the repository and how to use it | Create during Phase 0 or Phase 2 |
| `index.html` | 1.2 | Active | Beginner | Main static HTML entry point with columns linking to education pages by expertise level, Beginner, Intermediate, and Advanced guide pages | Update whenever page library changes |

### Existing or First-Wave HTML Pages

| File | Version | Status | Expertise | Purpose | Update Notes |
| --- | --- | --- | --- | --- | --- |
| `pages/intermediate/vibe-coding-vs-implementation-planning.html` | 1.0 | Active | Intermediate | Visual guide comparing vibe coding and implementation planning | Retrofitted from earlier standalone draft into shared CSS, metadata, navigation, and versioning |
| `pages/intermediate/checkpointed-execution.html` | 1.0 | Active | Intermediate | Visual guide explaining phase-by-phase AI-agent execution, stop points, validation, and reporting | Retrofitted from earlier standalone draft into shared CSS, metadata, navigation, and versioning |

## Planned Page Inventory

### Beginner Pages

| File | Version | Status | Expertise | Purpose |
| --- | --- | --- | --- | --- |
| `pages/beginner/ai-literacy-basics.html` | 1.0 | Active | Beginner | Explain what AI is good at, where it fails, and why AI should be treated as an assistant rather than an authority |
| `pages/beginner/prompting-basics.html` | 1.0 | Active | Beginner | Teach goal, context, constraints, examples, and output format with before and after prompt examples |
| `pages/beginner/privacy-and-safe-use.html` | 1.0 | Active | Beginner | Explain what data should not be pasted into AI tools and safer alternatives such as redaction and approved tools |
| `pages/beginner/hallucinations-and-verification.html` | 1.0 | Active | Beginner | Explain hallucinations, confidence traps, and verification workflows |
| `pages/beginner/human-accountability.html` | 1.0 | Active | Beginner | Explain that humans own the outcome of AI-assisted work across emails, reports, code suggestions, customer communications, and decisions |

### Intermediate Pages

| File | Version | Status | Expertise | Purpose |
| --- | --- | --- | --- | --- |
| `pages/intermediate/vibe-coding-vs-implementation-planning.html` | 1.0 | Active | Intermediate | Teach when AI work should remain exploratory and when implementation planning is required |
| `pages/intermediate/checkpointed-execution.html` | 1.0 | Active | Intermediate | Teach one-phase-at-a-time AI execution with stop, summary, validation, and explicit continuation |
| `pages/intermediate/context-and-prompt-drift.html` | 1.0 | Active | Intermediate | Explain context bloat, forgotten constraints, repeated corrections, stale assumptions, contradictory instructions, durable repo rules, and fresh-session triggers |
| `pages/intermediate/implementation-plans-and-specs.html` | 1.0 | Active | Intermediate | Teach when to create a PLAN.md, design brief, spec, migration plan, or runbook before AI-assisted implementation |
| `pages/intermediate/review-gates-and-rollback.html` | 1.0 | Active | Intermediate | Teach diff review, tests, linting, approvals, feature flags, dry runs, rollback instructions, audit trails, and stopping conditions |
| `pages/intermediate/blast-radius-thinking.html` | 1.0 | Active | Intermediate | Teach how to assess what AI-assisted work can break across documents, pages, migrations, IAM, incidents, payments, and regulated data |

### Advanced Pages

| File | Version | Status | Expertise | Purpose |
| --- | --- | --- | --- | --- |
| `pages/advanced/ai-for-technical-teams.html` | 1.0 | Active | Advanced | Teach developers, cloud engineers, QA, analysts, security practitioners, and technical leads safe AI support for code, tests, docs, diffs, logs, incidents, edge cases, and architecture-aware work |
| `pages/advanced/ai-coding-agents.html` | 1.0 | Active | Advanced | Teach how coding agents differ from chat assistants through repository access, file editing, command execution, permissions, branch discipline, stop points, and validation |
| `pages/advanced/repository-instructions-and-agents.html` | 1.0 | Active | Advanced | Teach how AGENTS.md, CODEX.md, README.md, PLAN.md, focused instruction files, validation commands, security rules, and version tracking guide AI work safely |
| `pages/advanced/test-first-ai-workflows.html` | 1.0 | Active | Advanced | Teach expected behavior, edge cases, regression tests, negative tests, acceptance criteria, smoke tests, and the limits of AI-drafted tests |
| `pages/advanced/code-review-with-ai.html` | 1.0 | Active | Advanced | Teach how to use AI for diff review, bugs, edge cases, security issues, maintainability, test gaps, and review coverage without replacing accountable review |
| `pages/advanced/infrastructure-and-iac-risk.html` | 1.0 | Active | Advanced | Teach stricter AI controls for Terraform, Kubernetes, IAM, DNS, networking, certificates, deployment automation, state, dry runs, protected branches, rollback, and secrets handling |
| `pages/advanced/security-privacy-and-governance.html` | 1.0 | Active | Advanced | Teach advanced security, privacy, and governance concerns including secrets, credentials, customer data, incidents, log sanitization, prompt injection, data leakage, vendors, auditability, approved tools, and escalation |
| `pages/advanced/controlled-automation.html` | 1.0 | Active | Advanced | Teach the difference between AI assistance, acceleration, and automation with human oversight, approval gates, monitoring, rollback, alerting, audit trails, and no-automation zones |

### Expert Pages

| File | Version | Status | Expertise | Purpose |
| --- | --- | --- | --- | --- |
| `pages/agentic-coding-governance.html` | Planned | Planned | Expert | Explain safe use of AI agents with repositories, shells, tools, and CI/CD |
| `pages/ai-operating-model.html` | Planned | Planned | Expert | Define roles, permissions, ownership, controls, and escalation paths |
| `pages/rag-and-knowledge-governance.html` | Planned | Planned | Expert | Explain retrieval, source quality, freshness, citations, and access control |
| `pages/ai-evaluation-frameworks.html` | Planned | Planned | Expert | Teach how to measure accuracy, safety, usefulness, and consistency |
| `pages/red-teaming-ai-workflows.html` | Planned | Planned | Expert | Test for prompt injection, data leakage, unsafe actions, and brittle workflows |
| `pages/ai-security-architecture.html` | Planned | Planned | Expert | Cover identity, access, logging, sandboxing, connector risk, and DLP |
| `pages/cost-and-context-management.html` | Planned | Planned | Expert | Explain tokens, context bloat, repeated prompts, model choice, and cost controls |
| `pages/strategic-ai-portfolio.html` | Planned | Planned | Expert | Help leadership prioritize AI initiatives by value, feasibility, risk, and readiness |

## Planned Markdown Documentation Inventory

### Beginner Docs

| File | Version | Status | Expertise | Purpose |
| --- | --- | --- | --- | --- |
| `docs/beginner/ai-literacy-basics.md` | Planned | Planned | Beginner | Markdown companion for AI literacy basics |
| `docs/beginner/prompting-basics.md` | Planned | Planned | Beginner | Markdown companion for prompting basics |
| `docs/beginner/privacy-and-safe-use.md` | Planned | Planned | Beginner | Markdown companion for privacy and safe use |

### Intermediate Docs

| File | Version | Status | Expertise | Purpose |
| --- | --- | --- | --- | --- |
| `docs/intermediate/vibe-coding-vs-implementation-planning.md` | Planned | Planned | Intermediate | Deeper written guide for vibe vs. implementation decisions |
| `docs/intermediate/checkpointed-execution.md` | Planned | Planned | Intermediate | Deeper written guide for checkpointed execution |
| `docs/intermediate/context-packaging.md` | Planned | Planned | Intermediate | Context packaging guidance and examples |

### Advanced Docs

| File | Version | Status | Expertise | Purpose |
| --- | --- | --- | --- | --- |
| `docs/advanced/ai-for-technical-teams.md` | Planned | Planned | Advanced | Technical team guidance |
| `docs/advanced/repository-orientation-for-ai-agents.md` | Planned | Planned | Advanced | Repository inspection guidance for agents |
| `docs/advanced/implementation-plans-and-specs.md` | Planned | Planned | Advanced | Guidance for creating implementation plans and specs |

### Expert Docs

| File | Version | Status | Expertise | Purpose |
| --- | --- | --- | --- | --- |
| `docs/expert/ai-operating-model.md` | Planned | Planned | Expert | Operating model guidance |
| `docs/expert/agentic-coding-governance.md` | Planned | Planned | Expert | Agentic coding governance guidance |
| `docs/expert/ai-security-architecture.md` | Planned | Planned | Expert | AI security architecture guidance |

## Planned Prompt Library

| File | Version | Status | Expertise | Purpose |
| --- | --- | --- | --- | --- |
| `docs/prompts/prompting-basics.md` | Planned | Planned | Beginner | Foundational prompt patterns |
| `docs/prompts/vibe-brief-prompt.md` | Planned | Planned | Intermediate | Prompt for creative exploration and direction-setting |
| `docs/prompts/implementation-plan-prompt.md` | Planned | Planned | Advanced | Prompt for producing buildable implementation plans |
| `docs/prompts/checkpointed-execution-prompt.md` | Planned | Planned | Advanced | Prompt for one-phase-at-a-time AI-agent execution |
| `docs/prompts/code-review-prompt.md` | Planned | Planned | Advanced | Prompt for AI-assisted code review |
| `docs/prompts/risk-review-prompt.md` | Planned | Planned | Advanced | Prompt for risk, security, and governance review |
| `docs/prompts/executive-summary-prompt.md` | Planned | Planned | Intermediate | Prompt for executive summaries |
| `docs/prompts/meeting-summary-prompt.md` | Planned | Planned | Beginner | Prompt for meeting notes and action items |

## Planned Assets

| File or Directory | Version | Status | Purpose |
| --- | --- | --- | --- |
| `assets/css/ai-field-guide.css` | 1.2 | Active | Shared CSS for static HTML education pages using the AI Field Guide visual language, including Beginner, Intermediate, and Advanced page patterns |
| `assets/js/` | N/A | Reserved | Reserved for future minimal scripts if needed.  Avoid JavaScript unless approved |
| `assets/images/` | N/A | Reserved | Reserved for diagrams or reusable visual assets |

## Planned Examples

| File or Directory | Version | Status | Purpose |
| --- | --- | --- | --- |
| `examples/prompts/` | N/A | Planned | Example prompt inputs and outputs |
| `examples/plans/` | N/A | Planned | Example implementation plans and checkpointed execution plans |

## Index Page Requirements

`index.html` must include:

- Repository title and short purpose.
- Explanation of the education ladder.
- Four columns: Beginner, Intermediate, Advanced, Expert.
- Cards for existing and planned pages.
- Visible expertise badges.
- Page status labels.
- Links to generated pages.
- `_blank` link behavior with `rel="noopener noreferrer"`.
- Responsive layout.
- Visible index version.

When a page is added, removed, renamed, or retired, update `index.html` and this file.

## HTML Page Requirements

Every HTML page under `pages/` must include:

- Visible title.
- Visible expertise level.
- Visible audience.
- Visible version.
- Machine-readable education metadata.
- Responsive layout.
- Semantic HTML.
- Footer with version and repository note.

Recommended metadata snippet:

```html
<meta name="ai-education-level" content="Intermediate">
<meta name="ai-education-audience" content="AI committee, technical leads, business users">
<meta name="ai-education-version" content="1.0">
```

## Visual Language Summary

The repository visual language is `AI Field Guide`.

Core style:

```text
Vibrant colors
Glass-like cards
Strong hero sections
Readable tables
Decision strips
Metadata pills
Expertise badges
Responsive grids
Clear contrast
Minimal scripts
```

Expertise colors:

| Level | Color Family |
| --- | --- |
| Beginner | Yellow / orange |
| Intermediate | Pink / purple |
| Advanced | Green / blue |
| Expert | Blue / charcoal |

Use `PLAN_AI_EDUCATION.md` for full visual language details.

## Change Coupling Rules

Some files must change together.

### Adding a New HTML Page

Update:

```text
pages/<new-page>.html
index.html
CODEX.md
```

Also update any relevant Markdown companion file if it exists.

### Renaming a Page

Update:

```text
old page filename
new page filename
index.html links
CODEX.md inventory
any markdown references
```

### Changing a Page Expertise Level

Update:

```text
page visible metadata
page meta tags
index.html card
CODEX.md inventory
```

### Changing Versioning Rules

Update:

```text
AGENTS.md
CODEX.md
PLAN_AI_EDUCATION.md if the plan references the old rules
```

### Changing Visual Language

Update:

```text
PLAN_AI_EDUCATION.md
AGENTS.md if agent rules change
assets/css/ai-field-guide.css if it exists
affected HTML pages
CODEX.md versions
```

## Recommended Initial Work Order

Use checkpointed execution.

### Phase 0

Create:

```text
AGENTS.md
CODEX.md
PLAN_AI_EDUCATION.md
README.md
folder structure
```

Stop and report.

### Phase 1

Create or import:

```text
pages/intermediate/vibe-coding-vs-implementation-planning.html
pages/intermediate/checkpointed-execution.html
```

Retrofit both with expertise and version metadata.

Stop and report.

### Phase 2

Create:

```text
index.html
```

Link to existing pages and list planned pages.

Stop and report.

## Current Known External Inputs

The repository is expected to incorporate or adapt two existing static HTML guides:

1. Vibe Coding vs. Implementation Planning.
2. Checkpointed Execution.

When importing them, preserve useful visual structure but retrofit metadata and versioning.

## Validation Checklist

Before completing any change:

```text
Read AGENTS.md.
Check this CODEX.md entry.
Update edited file version.
Update CODEX.md version inventory.
Update index.html if page links changed.
Run git diff --check.
Open changed HTML files locally if possible.
Confirm expertise level is visible.
Confirm _blank links include rel="noopener noreferrer".
Confirm no secrets or sensitive data were added.
```

## Open Decisions

| Decision | Status | Notes |
| --- | --- | --- |
| Markdown lint command | Open | Placeholder in AGENTS.md is `[TO_FILL]` |
| Shared CSS extraction timing | Open | Recommended after at least three pages stabilize |
| Whether to add README in Phase 0 or Phase 2 | Open | Phase 0 is recommended |
| Whether planned pages should have placeholder HTML cards only or full draft pages | Open | Prefer index cards first, then create pages phase by phase |
| Whether to create CHANGELOG.md from day one | Open | Optional.  Not required until revision volume increases |

## Do Not Add

Do not add:

```text
Secrets
Credentials
Production code
Terraform
Kubernetes manifests
CI/CD deployment logic
Tracking scripts
External analytics
Sensitive internal records
Customer or employee data
```

## Agent Reminder

When in doubt, make a smaller change, update the map, validate, commit, push, and stop.

Do not let a documentation repo become a runaway implementation burrow.
