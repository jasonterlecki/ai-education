# CODEX.md

Version: 1.9.1
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

This repository educates users about AI usage from Beginner to Expert levels.  It should help people understand practical AI workflows, safe prompting, vibe coding for exploration, implementation planning, checkpointed execution, AI-assisted technical work, governance, and enterprise AI operating models.

The repository should consistently reinforce this distinction:

```text
Vibe coding is useful for exploration.
Implementation planning is required for real systems.
Checkpointed execution is required for controlled AI-agent work.
```

## Governed File Rules

All governed documentation files must have a version.

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

When a governed file changes, update its version and update this inventory.

HTML files keep version numbers in machine-readable metadata and HTML comments, not visible page text.

Markdown files keep version numbers visible near the top.

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
| `AGENTS.md` | 1.2.0 | Active | N/A | Defines repository rules for AI agents, versioning, validation, scope, checkpointed execution, and content governance | Update when agent behavior, version rules, validation, or repo scope changes |
| `CODEX.md` | 1.9.1 | Active | N/A | Repository map, file inventory, page status, versions, and expertise mapping | Update for every file add, delete, rename, version change, page status change, or purpose change |
| `PLAN_AI_EDUCATION.md` | 1.2.0 | Active | N/A | Detailed plan for the AI education repository, curriculum, visual language, index page, implementation phases, and HTML Prompt Library direction | Update when the education strategy or planned curriculum changes |
| `README.md` | Planned | Planned | Beginner | Short public-facing overview of the repository and how to use it | Create during Phase 0 or Phase 2 |
| `index.html` | 1.9.0 | Active | Beginner | Main static HTML entry point with cards linking to education pages by expertise level plus completed Prompt Library pages; version is kept in machine-readable metadata and an HTML comment, not visible page text | Update whenever page library changes |

### Existing or First-Wave HTML Pages

| File | Version | Status | Expertise | Purpose | Update Notes |
| --- | --- | --- | --- | --- | --- |
| `pages/intermediate/vibe-coding-vs-implementation-planning.html` | 1.0.2 | Active | Intermediate | Visual guide comparing vibe coding and implementation planning | Retrofitted from earlier standalone draft into shared CSS, metadata, navigation, and versioning |
| `pages/intermediate/checkpointed-execution.html` | 1.0.1 | Active | Intermediate | Visual guide explaining phase-by-phase AI-agent execution, stop points, validation, and reporting | Retrofitted from earlier standalone draft into shared CSS, metadata, navigation, and versioning |

## Planned Page Inventory

### Beginner Pages

| File | Version | Status | Expertise | Purpose |
| --- | --- | --- | --- | --- |
| `pages/beginner/ai-literacy-basics.html` | 1.0.3 | Active | Beginner | Explain what AI is good at, where it fails, and why AI should be treated as an assistant rather than an authority |
| `pages/beginner/prompting-basics.html` | 1.0.1 | Active | Beginner | Teach goal, context, constraints, examples, and output format with before and after prompt examples |
| `pages/beginner/privacy-and-safe-use.html` | 1.0.1 | Active | Beginner | Explain what data should not be pasted into AI tools and safer alternatives such as redaction and approved tools |
| `pages/beginner/hallucinations-and-verification.html` | 1.0.1 | Active | Beginner | Explain hallucinations, confidence traps, and verification workflows |
| `pages/beginner/human-accountability.html` | 1.0.2 | Active | Beginner | Explain that humans own the outcome of AI-assisted work across emails, reports, code suggestions, customer communications, and decisions |
| `pages/beginner/ai-for-non-technical-people.html` | 1.0.1 | Active | Beginner | Teach non-technical users practical AI use for drafting, summarizing, comparing, and reviewing without treating AI as an authority |
| `pages/beginner/ai-lexicon-for-beginners.html` | 1.0.1 | Active | Beginner | Define common AI terms in plain language so new users can follow guides, tools, and governance conversations |
| `pages/beginner/introduction-to-vibe-coding.html` | 1.0.2 | Active | Beginner | Introduce vibe coding as exploratory AI-assisted making, with clear boundaries before implementation work |
| `pages/beginner/memory-vs-context-vs-instructions.html` | 1.0.1 | Active | Beginner | Clarify the difference between saved memory, current conversation context, custom instructions, project files, and repository instructions |
| `pages/beginner/source-quality-and-citation-hygiene.html` | 1.0.1 | Active | Beginner | Teach how to evaluate citations, stale sources, circular references, unverifiable claims, and AI's habit of polishing uncertainty |
| `pages/beginner/multimodal-ai-basics.html` | 1.0.1 | Active | Beginner | Explain what AI can and cannot reliably infer from images, screenshots, diagrams, PDFs, charts, and mixed-format files |

### Intermediate Pages

| File | Version | Status | Expertise | Purpose |
| --- | --- | --- | --- | --- |
| `pages/intermediate/vibe-coding-vs-implementation-planning.html` | 1.0.2 | Active | Intermediate | Teach when AI work should remain exploratory and when implementation planning is required |
| `pages/intermediate/checkpointed-execution.html` | 1.0.1 | Active | Intermediate | Teach one-phase-at-a-time AI execution with stop, summary, validation, and explicit continuation |
| `pages/intermediate/context-and-prompt-drift.html` | 1.0.1 | Active | Intermediate | Explain context bloat, forgotten constraints, repeated corrections, stale assumptions, contradictory instructions, durable repo rules, and fresh-session triggers |
| `pages/intermediate/implementation-plans-and-specs.html` | 1.0.1 | Active | Intermediate | Teach when to create a PLAN.md, design brief, spec, migration plan, or runbook before AI-assisted implementation |
| `pages/intermediate/review-gates-and-rollback.html` | 1.0.1 | Active | Intermediate | Teach diff review, tests, linting, approvals, feature flags, dry runs, rollback instructions, audit trails, and stopping conditions |
| `pages/intermediate/blast-radius-thinking.html` | 1.0.1 | Active | Intermediate | Teach how to assess what AI-assisted work can break across documents, pages, migrations, IAM, incidents, payments, and regulated data |
| `pages/intermediate/token-economy.html` | 1.0.1 | Active | Intermediate | Explain context windows, input/output tokens, hidden reasoning cost, long prompts, file bloat, and why more context is not always better |
| `pages/intermediate/token-budgeting-for-real-work.html` | 1.0.1 | Active | Intermediate | Teach users how to decide what belongs in the prompt, what belongs in attached files, and what should be summarized first |
| `pages/intermediate/ai-data-boundaries.html` | 1.0.1 | Active | Intermediate | Teach practical boundaries for what AI can see, what should be summarized or redacted, and what must stay out of prompts and files |
| `pages/intermediate/ai-use-case-intake.html` | 1.0.1 | Active | Intermediate | Teach structured intake for AI use cases before teams invest in tools, automations, or governance-heavy workflows |
| `pages/intermediate/human-in-the-loop-design.html` | 1.0.1 | Active | Intermediate | Teach how to design review, approval, escalation, and accountability checkpoints into AI-assisted workflows |
| `pages/intermediate/context-compression.html` | 1.0.1 | Active | Intermediate | Show how to convert large chats, plans, and documents into durable summaries without losing decisions, constraints, and open risks |
| `pages/intermediate/plan-md-vs-spec-md-vs-runbook-md.html` | 1.0.1 | Active | Intermediate | Compare planning artifacts and explain when each one should exist before AI edits code, infrastructure, or content |
| `pages/intermediate/prompt-injection-for-business-users.html` | 1.0.1 | Active | Intermediate | Teach non-technical users how malicious or untrusted content can manipulate AI behavior inside documents, webpages, and emails |
| `pages/intermediate/agent-handoff-notes.html` | 1.0.1 | Active | Intermediate | Explain how to preserve state between sessions using summaries, changed files, pending tasks, blockers, and validation results |
| `pages/intermediate/ai-assisted-debugging.html` | 1.0.1 | Active | Intermediate | Teach structured debugging with AI: symptoms, logs, hypotheses, reproduction steps, minimal changes, and proof of fix |
| `pages/intermediate/ai-and-documentation-systems.html` | 1.0.1 | Active | Intermediate | Show how AI can maintain docs, READMEs, decision records, changelogs, migration notes, and operational runbooks without inventing history |
| `pages/intermediate/ai-output-acceptance-criteria.html` | 1.0.1 | Active | Intermediate | Show how to define done for AI work before execution starts: behavior, tests, review evidence, rollback, and owner approval |
| `pages/intermediate/ai-for-sensitive-decisions.html` | 1.0.1 | Active | Intermediate | Explain when AI can assist but not decide in HR, legal, medical, financial, disciplinary, customer-impacting, and high-risk operational work |
| `pages/intermediate/ai-content-lifecycle.html` | 1.0.1 | Active | Intermediate | Cover drafting, review, approval, publishing, versioning, retirement, and ownership for AI-assisted educational or policy content |
| `pages/intermediate/ai-for-slide-and-visual-planning.html` | 1.0.1 | Active | Intermediate | Teach how to use AI for visual structure, slide hierarchy, diagrams, infographics, and speaker-friendly explanations |

### Advanced Pages

| File | Version | Status | Expertise | Purpose |
| --- | --- | --- | --- | --- |
| `pages/advanced/ai-for-technical-teams.html` | 2.0.1 | Active | Advanced | Teach developers, cloud engineers, QA, analysts, security practitioners, and technical leads safe AI support for code, tests, docs, diffs, logs, incidents, edge cases, and architecture-aware work |
| `pages/advanced/ai-coding-agents.html` | 1.0.1 | Active | Advanced | Teach how coding agents differ from chat assistants through repository access, file editing, command execution, permissions, branch discipline, stop points, and validation |
| `pages/advanced/repository-instructions-and-agents.html` | 1.0.1 | Active | Advanced | Teach how AGENTS.md, CODEX.md, README.md, PLAN.md, focused instruction files, validation commands, security rules, and version tracking guide AI work safely |
| `pages/advanced/test-first-ai-workflows.html` | 1.0.1 | Active | Advanced | Teach expected behavior, edge cases, regression tests, negative tests, acceptance criteria, smoke tests, and the limits of AI-drafted tests |
| `pages/advanced/code-review-with-ai.html` | 1.0.1 | Active | Advanced | Teach how to use AI for diff review, bugs, edge cases, security issues, maintainability, test gaps, and review coverage without replacing accountable review |
| `pages/advanced/infrastructure-and-iac-risk.html` | 1.0.1 | Active | Advanced | Teach stricter AI controls for Terraform, Kubernetes, IAM, DNS, networking, certificates, deployment automation, state, dry runs, protected branches, rollback, and secrets handling |
| `pages/advanced/security-privacy-and-governance.html` | 1.0.1 | Active | Advanced | Teach advanced security, privacy, and governance concerns including secrets, credentials, customer data, incidents, log sanitization, prompt injection, data leakage, vendors, auditability, approved tools, and escalation |
| `pages/advanced/controlled-automation.html` | 1.0.1 | Active | Advanced | Teach the difference between AI assistance, acceleration, and automation with human oversight, approval gates, monitoring, rollback, alerting, audit trails, and no-automation zones |
| `pages/advanced/agent-context-suite.html` | 1.0.1 | Active | Advanced | Introduce the ensemble of markdown files that guide coding agents: purpose, scope, hierarchy, validation, security rules, and handoff notes |
| `pages/advanced/agents-md-deep-dive.html` | 1.0.1 | Active | Advanced | Explain how to write durable repository guidance for AI coding agents without overloading them or giving unsafe permissions |
| `pages/advanced/skills-md-deep-dive.html` | 1.0.1 | Active | Advanced | Explain reusable task skills, when to create them, how specific they should be, and how they differ from general repo instructions |
| `pages/advanced/mcp-basics.html` | 1.0.1 | Active | Advanced | Explain Model Context Protocol as a way for AI tools to access external systems through controlled, explicit interfaces |
| `pages/advanced/tool-calling-and-function-boundaries.html` | 1.0.1 | Active | Advanced | Teach how AI chooses tools, what can go wrong, and why tool outputs need validation instead of blind trust |
| `pages/advanced/connectors-and-data-access.html` | 1.0.1 | Active | Advanced | Explain the risks and governance questions around connecting AI to email, drives, tickets, calendars, repositories, and internal systems |
| `pages/advanced/prompt-injection-for-agents.html` | 1.0.1 | Active | Advanced | Explain indirect prompt injection, poisoned files, malicious repo content, unsafe instructions, and defensive agent patterns |
| `pages/advanced/agent-permissions-ladder.html` | 1.0.1 | Active | Advanced | Define safe levels of autonomy, from read-only analysis to proposed diffs, local commands, deployment actions, and production changes |
| `pages/advanced/agent-observability.html` | 1.0.1 | Active | Advanced | Cover logs, transcripts, diffs, command history, approvals, checkpoints, and evidence trails for AI-assisted work |
| `pages/advanced/ai-for-incident-response-support.html` | 1.0.1 | Active | Advanced | Explain safe uses of AI during incidents: log triage, timeline building, hypothesis generation, stakeholder updates, and postmortems |
| `pages/advanced/ai-generated-code-smells.html` | 1.0.1 | Active | Advanced | Teach reviewers to spot overbroad rewrites, invented APIs, missing tests, unsafe defaults, fragile abstractions, and fake confidence |
| `pages/advanced/ai-pilot-to-production.html` | 1.0.1 | Active | Advanced | Teach how to move AI work from experiment to supported workflow with owners, controls, validation, rollout criteria, and stop conditions |
| `pages/advanced/shadow-ai-and-unsanctioned-use.html` | 1.0.1 | Active | Advanced | Explain why people bypass approved AI paths, what risks that creates, and how teams can respond with usable guardrails |
| `pages/advanced/ai-governance-without-theater.html` | 1.0.1 | Active | Advanced | Teach practical governance controls that guide real AI use without relying on performative policy theater |
| `pages/advanced/ai-risk-tiers.html` | 1.0.1 | Active | Advanced | Explain risk-tiering patterns for AI use cases and the controls that should increase with blast radius |
| `pages/advanced/retrieval-failure-modes.html` | 1.0.1 | Active | Advanced | Explain failure patterns in retrieval-backed AI systems, including stale sources, wrong chunks, weak citations, and missing context |
| `pages/advanced/source-of-truth-design.html` | 1.0.1 | Active | Advanced | Teach how to define authoritative sources, version rules, ownership, and update flows for AI-assisted knowledge systems |
| `pages/advanced/embeddings-and-vector-search.html` | 1.0.1 | Active | Advanced | Explain embeddings, similarity search, chunking, retrieval mistakes, and why found something similar is not the same as found the answer |
| `pages/advanced/chunking-strategy.html` | 1.0.1 | Active | Advanced | Teach how document splitting affects retrieval quality, citations, context quality, and hallucination risk |
| `pages/advanced/review-gates-and-rollback.html` | 1.0.1 | Active | Advanced | Teach technical review gates, rollback planning, stop points, and recovery evidence for AI-assisted changes |

### Expert Pages

| File | Version | Status | Expertise | Purpose |
| --- | --- | --- | --- | --- |
| `pages/expert/ai-operating-model.html` | 1.0.1 | Active | Expert | Teach AI committee members and governance owners how to define roles, approved tools, data classification, risk tiers, review gates, escalation paths, and ownership of outcomes |
| `pages/expert/ai-architecture-strategy.html` | 1.0.1 | Active | Expert | Teach senior architects and platform leaders how to treat AI capabilities as architecture across assistants, coding agents, retrieval, workflow automation, integration, auditability, and lifecycle management |
| `pages/expert/evaluation-and-red-teaming.html` | 1.0.1 | Active | Expert | Teach evaluation programs using task-specific test sets, expected answers, human review, safety testing, prompt injection testing, hallucination checks, fairness review, regression testing, red-team scenarios, and acceptance thresholds |
| `pages/expert/retrieval-and-knowledge-governance.html` | 1.0.1 | Active | Expert | Teach knowledge governance for retrieval systems, including source quality, ownership, freshness, permissions, citations, outdated policies, conflicting documents, sensitive content, retrieval boundaries, and lifecycle |
| `pages/expert/model-selection-and-cost-management.html` | 1.0.1 | Active | Expert | Teach model capability tiers, reasoning versus speed, context windows, coding models, small versus large models, cost per task, token bloat, repeated prompting, automation frequency, and cost controls |
| `pages/expert/ai-security-architecture.html` | 1.0.1 | Active | Expert | Teach security architecture for AI workflows including identity, access, least privilege, connector permissions, sandboxing, secrets isolation, logging, audit trails, DLP, prompt injection, incident response, and vendor review |
| `pages/expert/change-management-and-adoption.html` | 1.0.1 | Active | Expert | Teach organization-wide AI adoption through champions, training paths, role-based guidance, communication strategy, misuse prevention, feedback loops, adoption metrics, realistic expectations, and policy clarity |
| `pages/expert/strategic-ai-portfolio.html` | 1.0.1 | Active | Expert | Teach AI portfolio management through intake, prioritization, business value, risk, feasibility, data readiness, owner readiness, support burden, measurement, pilot-to-production paths, and stop criteria |
| `pages/expert/mcp-security-and-permissions.html` | 1.0.1 | Active | Expert | Cover tool exposure, least privilege, data boundaries, audit logs, prompt injection, and why available tool does not mean safe tool |
| `pages/expert/evaluation-harnesses.html` | 1.0.1 | Active | Expert | Explain lightweight ways to test AI outputs repeatedly using examples, expected answers, edge cases, regression checks, and scoring rubrics |
| `pages/expert/ai-vendor-and-tool-selection.html` | 1.0.1 | Active | Expert | Cover procurement questions around data use, retention, connectors, admin controls, auditability, model choice, cost, and support |
| `pages/expert/local-models-vs-hosted-models.html` | 1.0.1 | Active | Expert | Compare privacy, control, cost, maintenance, quality, latency, and governance tradeoffs between local and hosted AI |
| `pages/expert/cost-controls-for-teams.html` | 1.0.1 | Active | Expert | Explain quotas, model tiers, caching, batching, context limits, review loops, and practical habits that prevent token bonfires |

### Prompt Library Pages

| File | Version | Status | Expertise | Purpose |
| --- | --- | --- | --- | --- |
| `pages/prompts/prompting-basics.html` | 1.0.1 | Active | Beginner | Reusable general-purpose prompt structure covering role, goal, context, constraints, examples, output format, and review criteria |
| `pages/prompts/email-and-communication-prompt.html` | 1.0.1 | Active | Beginner | Prompt for drafting or improving emails and internal communications while preserving facts, tone, call to action, and sender accountability |
| `pages/prompts/document-review-prompt.html` | 1.0.1 | Active | Beginner | Prompt for reviewing documents for clarity, structure, missing sections, contradictions, unsupported claims, audience fit, tone, actionability, risks, and suggested edits |
| `pages/prompts/executive-summary-prompt.html` | 1.0.1 | Active | Beginner | Prompt for turning detailed information into executive summaries with decisions, options, recommendations, risks, cost, timeline, owners, and open questions; also useful for Intermediate users |
| `pages/prompts/meeting-summary-prompt.html` | 1.0.1 | Active | Beginner | Prompt for turning notes or transcripts into meeting summaries, decisions, action items, owners, due dates, unresolved questions, risks, and follow-up messages; also useful for Intermediate users |
| `pages/prompts/vibe-brief-prompt.html` | 1.0.1 | Active | Intermediate | Prompt for exploratory work, creative direction, design options, tradeoffs, recommended direction, missing information, and validation before implementation |
| `pages/prompts/implementation-plan-prompt.html` | 1.0.1 | Active | Intermediate | Prompt for turning ideas into formal implementation plans with scope, assumptions, non-goals, architecture, affected components, phases, validation, rollout, rollback, risks, and acceptance criteria |
| `pages/prompts/checkpointed-execution-prompt.html` | 1.0.1 | Active | Intermediate | Prompt for AI coding agents to implement one phase only, inspect before editing, keep diffs focused, validate, report, stop, and wait; also useful for Advanced users |
| `pages/prompts/code-review-prompt.html` | 1.0.1 | Active | Advanced | Prompt for reviewing code or diffs for correctness, edge cases, security, maintainability, test gaps, performance, unclear naming, behavior changes, and rollback concerns |
| `pages/prompts/risk-review-prompt.html` | 1.0.1 | Active | Advanced | Prompt for reviewing AI proposals, plans, or code changes for affected users and systems, data sensitivity, permissions, security, operations, compliance, rollback, monitoring, approval gates, and stop reasons; also useful for Expert users |

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

## Prompt Library

The prompt library is implemented as static HTML pages under `pages/prompts/`.

Do not add Markdown prompt-library companion pages unless the repository direction changes and `AGENTS.md` is updated to allow them.

## Planned Assets

| File or Directory | Version | Status | Purpose |
| --- | --- | --- | --- |
| `assets/css/ai-field-guide.css` | 1.4 | Active | Shared CSS for static HTML education pages using the AI Field Guide visual language, including Beginner, Intermediate, Advanced, Expert, and Prompt Library page patterns |
| `assets/js/` | N/A | Reserved | Reserved for future minimal scripts if needed.  Avoid JavaScript unless approved |
| `assets/images/` | N/A | Reserved | Reserved for diagrams or reusable visual assets |

## Legacy Archive

| File or Directory | Version | Status | Purpose |
| --- | --- | --- | --- |
| `old/` | N/A | Archived | Snapshot of earlier HTML pages and shared CSS retained for reference while the active pages live under `pages/` and `assets/` |

## Planned Examples

| File or Directory | Version | Status | Purpose |
| --- | --- | --- | --- |
| `examples/prompts/` | N/A | Planned | Example prompt inputs and outputs |
| `examples/plans/` | N/A | Planned | Example implementation plans and checkpointed execution plans |

## Index Page Requirements

`index.html` must include:

- Repository title and short purpose.
- Explanation of the education ladder.
- Grouped sections: Beginner, Intermediate, Advanced, Expert, and Prompt Library.
- Cards for active pages and any future planned pages.
- Visible expertise badges.
- Page status labels.
- Links to generated pages.
- `_blank` link behavior with `rel="noopener noreferrer"`.
- Responsive layout.
- Machine-readable index version and HTML comment version.

When a page is added, removed, renamed, or retired, update `index.html` and this file.

## HTML Page Requirements

Every HTML page under `pages/` must include:

- Visible title.
- Visible expertise level.
- Visible audience.
- Machine-readable education metadata, including version.
- HTML comment version.
- Responsive layout.
- Semantic HTML.
- Footer or closing note when appropriate, without visible version text.

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
HTML comment version
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

Retrofit both with expertise, machine-readable version metadata, and HTML comment versions.

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
Confirm HTML versions are comments and metadata, not visible page text.
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
