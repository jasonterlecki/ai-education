# PLAN_AI_EDUCATION.md: AI Education Knowledge Base and HTML Guide Library

Version: 1.1
Status: Draft
Repository type: Documentation and static HTML education repository
Primary audience: AI committee members, business users, technical teams, managers, architects, governance teams, and approved AI coding-agent users

## 1. Purpose

This repository will become a shared AI education knowledge base.  It will explain AI concepts, safe usage patterns, prompting workflows, checkpointed execution, AI-assisted coding, governance, and advanced AI operating-model topics.

The goal is not to encourage everyone to become a vibe coder.  The goal is to help everyone become AI-literate while clearly distinguishing between low-risk creative exploration and higher-risk implementation work.

This repository should help answer four recurring questions:

1. What can I safely use AI for?
2. When is vibe-style exploration appropriate?
3. When do I need a specification, implementation plan, checkpointed execution, review gates, and rollback?
4. What level of expertise is required before using AI on real systems, codebases, data, infrastructure, or production-adjacent workflows?

## 2. Repository Outcome

The repository should contain:

- Markdown education documents.
- Static HTML explainer pages.
- Reusable prompts.
- Decision guides.
- Governance and safety checklists.
- A visual index page linking to all generated pages.
- A durable `AGENTS.md` that tells AI agents how to work in the repository.
- A durable `CODEX.md` that maps files, purposes, versions, and ownership notes.

The repository should not contain:

- Production application code.
- Infrastructure provisioning.
- Secrets, credentials, tokens, private keys, or sensitive operational data.
- Customer data or employee personal data.
- Unapproved internal documents copied wholesale.
- Anything requiring deployment access to production systems.

## 3. Educational Philosophy

The core message should be:

```text
Everyone should become AI-literate.
Many people can use AI to prototype ideas.
Fewer people should use AI to modify real systems.
Only trained people should use AI coding agents against production-adjacent repositories.
```
A second core message should be:

```text
Vibe coding is a creative technique, not a delivery methodology.
It is useful when exploring.
It is risky when deploying.
It is dangerous when applied blindly to systems people do not understand.
```

A third core message should be:

```text
AI is leverage.
The more leverage you apply, the more control you need.
```

The education material should avoid fearmongering.  It should also avoid cheerleading without guardrails.  The tone should be practical, visual, memorable, and respectful of different expertise levels.

## 4. Expertise Level Taxonomy

Every HTML education page and major Markdown guide must display a visible expertise level.

Use these primary levels:

| Level | Intended Audience | Expected Skill Level | Typical Risk Boundary |
| --- | --- | --- | --- |
| Beginner | Everyone | New or casual AI users | Drafting, summarizing, brainstorming, reviewing output |
| Intermediate | Frequent AI users, team leads, analysts, business power users | Comfortable with prompts and review | Reusable workflows, decision guides, structured prompting, safe prototypes |
| Advanced | Developers, cloud engineers, security teams, architects, QA, technical leads | Familiar with systems, code, data, and change control | AI-assisted implementation, repository work, tests, migrations, security review |
| Expert | AI committee, governance, senior architecture, platform owners, risk leaders | Responsible for strategy, controls, architecture, or enterprise adoption | Operating model, evaluations, security architecture, agentic workflows, governance |

HTML pages may also show a secondary audience, such as:

```text
Primary expertise: Intermediate
Useful for: Managers, developers, AI committee members
```

Do not create vague level labels such as "All users" as the primary level.  If a page is useful to everyone, mark it as Beginner and state that it is useful for all audiences.

## 5. HTML Page Metadata Requirements

Each HTML page should include visible and machine-readable metadata.

Required visible metadata near the top of each page:

```text
Expertise: Beginner | Intermediate | Advanced | Expert
Audience: <short list>
Use when: <one sentence>
Last updated: <date or version>
```

Required HTML metadata:

```html
<meta name="ai-education-level" content="Intermediate">
<meta name="ai-education-audience" content="AI committee, technical leads, business users">
<meta name="ai-education-version" content="1.0">
```

Recommended body data attributes:

```html
<body data-page-type="ai-education" data-expertise="intermediate">
```

Each page should include a visible version number, preferably in a footer or metadata card.

## 6. Initial HTML Page Library

Create a `pages/` directory for standalone HTML guide pages.

### 6.1 Existing Pages to Retrofit

The repository already has or will import two current pages.  Retrofit both to match the metadata and visual language rules.

| Page | Suggested Filename | Expertise | Purpose | Retrofit Notes |
| --- | --- | --- | --- | --- |
| Vibe Coding vs. Implementation Planning | `pages/vibe-coding-vs-implementation-planning.html` | Intermediate | Explain when exploratory AI work is appropriate versus when formal implementation planning is required | Add expertise badge, metadata panel, footer version, and index-compatible card summary |
| Checkpointed Execution | `pages/checkpointed-execution.html` | Intermediate | Explain why AI implementation should proceed phase by phase with stop points, validation, and reporting | Add expertise badge, metadata panel, footer version, and index-compatible card summary |

### 6.2 Beginner Pages

Recommended first Beginner pages:

| Page | Filename | Purpose |
| --- | --- | --- |
| AI Literacy Basics | `pages/ai-literacy-basics.html` | Explain what AI is good at, where it fails, and how humans remain accountable |
| Prompting Basics | `pages/prompting-basics.html` | Teach goal, context, constraints, examples, and output format |
| Hallucinations and Verification | `pages/hallucinations-and-verification.html` | Teach why confident output may be wrong and how to verify claims |
| Privacy and Safe Use | `pages/privacy-and-safe-use.html` | Explain what must not be pasted into AI tools |
| Human Accountability | `pages/human-accountability.html` | Explain that AI can assist, but humans own the outcome |

### 6.3 Intermediate Pages

Recommended Intermediate pages:

| Page | Filename | Purpose |
| --- | --- | --- |
| Practical Prompt Patterns | `pages/practical-prompt-patterns.html` | Provide reusable prompt structures for common work |
| Context Packaging | `pages/context-packaging.html` | Teach how to give enough context without flooding the model |
| Vibe Coding vs. Implementation Planning | `pages/vibe-coding-vs-implementation-planning.html` | Compare exploration and execution workflows |
| Checkpointed Execution | `pages/checkpointed-execution.html` | Teach phase-by-phase agent execution |
| AI Output Review | `pages/ai-output-review.html` | Teach review for accuracy, tone, bias, omissions, unsupported claims, and confidence traps |
| Business Workflow Acceleration | `pages/business-workflow-acceleration.html` | Show safe uses for summaries, drafts, checklists, meeting notes, and decision memos |

### 6.4 Advanced Pages

Recommended Advanced pages:

| Page | Filename | Purpose |
| --- | --- | --- |
| AI for Technical Teams | `pages/ai-for-technical-teams.html` | Explain coding, debugging, tests, refactoring, and documentation support |
| Repository Orientation for AI Agents | `pages/repository-orientation-for-ai-agents.html` | Teach agents to inspect project structure before editing |
| Implementation Plans and Specs | `pages/implementation-plans-and-specs.html` | Show how to turn ideas into buildable plans |
| Test-First AI Workflows | `pages/test-first-ai-workflows.html` | Encourage expected behavior and validation before code changes |
| AI Code Review | `pages/ai-code-review.html` | Use AI to identify bugs, missing tests, edge cases, and unclear logic |
| Security, Privacy, and Governance | `pages/security-privacy-and-governance.html` | Explain risk, policy, data handling, and human review |
| Data Classification for AI Use | `pages/data-classification-for-ai-use.html` | Explain public, internal, confidential, restricted, regulated, and secret data handling |
| Vendor and Tool Review | `pages/vendor-and-tool-review.html` | Provide questions for AI vendor/tool assessment |

### 6.5 Expert Pages

Recommended Expert pages:

| Page | Filename | Purpose |
| --- | --- | --- |
| Agentic Coding Governance | `pages/agentic-coding-governance.html` | Explain safe use of AI agents with repos, shells, tools, and CI/CD |
| AI Operating Model | `pages/ai-operating-model.html` | Define roles, permissions, ownership, controls, and escalation paths |
| RAG and Knowledge Governance | `pages/rag-and-knowledge-governance.html` | Explain source quality, freshness, access control, retrieval, and citations |
| AI Evaluation Frameworks | `pages/ai-evaluation-frameworks.html` | Teach how to measure accuracy, safety, usefulness, and consistency |
| Red-Teaming AI Workflows | `pages/red-teaming-ai-workflows.html` | Test for prompt injection, data leakage, unsafe actions, and brittle workflows |
| AI Security Architecture | `pages/ai-security-architecture.html` | Cover identity, access, logging, sandboxing, connector risk, and DLP |
| Cost and Context Management | `pages/cost-and-context-management.html` | Explain tokens, context bloat, repeated prompts, model choice, and workflow costs |
| Strategic AI Portfolio | `pages/strategic-ai-portfolio.html` | Help leadership prioritize AI initiatives based on value, feasibility, risk, and readiness |

## 7. Index Page Plan

Create a root-level `index.html` page that acts as the entry point for the education library.

### 7.1 Index Page Purpose

The index page should:

- Explain the education ladder.
- Group pages by expertise level.
- Provide several columns of page links.
- Show each page title, expertise level, short purpose, and audience.
- Open individual pages in a new tab by default.
- Make it easy to scan from Beginner to Expert.
- Reinforce that not everyone needs to become a vibe coder.

### 7.2 Link Behavior

Use `target="_blank"` for guide links so the index remains open while readers explore pages.

Every `_blank` link must include:

```html
rel="noopener noreferrer"
```

Example:

```html
<a href="pages/checkpointed-execution.html" target="_blank" rel="noopener noreferrer">
  Checkpointed Execution
</a>
```

### 7.3 Index Page Layout

Use a responsive multi-column layout.

Desktop:

```text
Hero
Education ladder summary
Four columns:
  Beginner
  Intermediate
  Advanced
  Expert
Featured comparison cards
Footer with repository/version note
```

Mobile:

```text
Hero
Level cards stacked vertically
Page cards stacked within each level
Footer
```

### 7.4 Index Page Card Fields

Each page card should include:

```text
Title
Expertise badge
Audience
Short description
Status: Draft | Ready | Retired
Open guide link
```

Example card content:

```text
Checkpointed Execution
Expertise: Intermediate
Audience: AI coding-agent users, technical leads, managers
Purpose: Learn why AI implementation should proceed one phase at a time with validation and stop points.
```

### 7.5 Index Page Versioning

The index page is governed documentation and should include visible version metadata.

Suggested footer:

```text
AI Education Knowledge Base.  Index version 1.0.  Repository mapping maintained in CODEX.md.
```

Whenever new pages are added, update:

1. `index.html`
2. `CODEX.md`
3. Any relevant page status in the file inventory
4. Version numbers according to the versioning rules in `AGENTS.md`

## 8. Visual Language

The visual language should make the material feel useful, energetic, and memorable without becoming unserious.

Recommended style name:

```text
AI Field Guide
```

Optional internal nickname:

```text
Bright Rails
```

### 8.1 Visual Principles

Use these design principles:

1. Color communicates level and risk.
2. Cards make content scannable.
3. Comparisons should be side-by-side where possible.
4. Decision points should be visually distinct.
5. Guardrails should feel practical, not punitive.
6. Pages should be friendly enough for beginners and precise enough for experts.
7. Pages should feel like field guides, not policy tombstones.

### 8.2 Color System

Use vibrant but controlled colors.

Suggested palette:

```css
:root {
  --ink: #172033;
  --muted: #526078;
  --paper: #fffaf3;
  --panel: rgba(255, 255, 255, 0.84);

  --beginner-a: #ffb000;
  --beginner-b: #ff6b35;

  --intermediate-a: #ff4fa3;
  --intermediate-b: #7c3cff;

  --advanced-a: #00b894;
  --advanced-b: #00a8ff;

  --expert-a: #1957ff;
  --expert-b: #172033;

  --safe: #00b894;
  --caution: #ffb000;
  --risk: #ff6b35;
  --critical: #d63031;

  --shadow: 0 24px 60px rgba(31, 38, 67, 0.18);
  --radius-xl: 30px;
  --radius-lg: 22px;
  --radius-md: 16px;
}
```

### 8.3 Expertise Level Colors

| Level | Primary Color | Secondary Color | Feeling |
| --- | --- | --- | --- |
| Beginner | Yellow/orange | Warm coral | Welcoming, energetic, low-threat |
| Intermediate | Pink | Purple | Creative, exploratory, structured |
| Advanced | Green | Blue | Technical, operational, controlled |
| Expert | Blue | Charcoal | Strategic, architectural, governance-focused |

### 8.4 Layout Patterns

Preferred patterns:

```text
Hero section with strong title and short explanation.
Metadata pill row.
Two-column comparisons.
Decision strips.
Fast decision matrices.
Risk cards.
Checklist panels.
Prompt example blocks.
"Use this when" and "Do not use this when" cards.
Footer with version and repository note.
```

Avoid:

```text
Long walls of text.
Dense policy language with no examples.
Unlabeled risk levels.
Tiny contrast.
Overuse of animation.
Hidden critical warnings.
```

### 8.5 Typography

Recommended font stack:

```css
font-family: Inter, ui-sans-serif, system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI", sans-serif;
```

Use:

```text
Large, expressive page titles.
Short paragraphs.
Strong section headings.
Readable tables.
Code-style prompt examples.
Plain-language labels.
```

### 8.6 Icon and Motif Guidance

Use simple symbolic motifs:

```text
Compass: choosing direction
Rails: guardrails and safe paths
Bridge: moving from idea to implementation
Checkpoint flag: stop, validate, continue
Shield: governance and security
Magnifier: verification and review
Stacked cards: context packaging
Circuit path: agentic workflows
```

Fox references are allowed as light personality touches if appropriate, but they should not make corporate education material feel childish.  A fox metaphor should clarify, not decorate.

### 8.7 Accessibility Requirements

Every HTML page must:

- Use semantic HTML.
- Include a single clear `h1`.
- Maintain strong color contrast.
- Avoid relying on color alone to communicate risk or expertise.
- Use descriptive link text.
- Include `rel="noopener noreferrer"` for `_blank` links.
- Be responsive on mobile.
- Avoid motion-heavy UI.
- Print reasonably cleanly.

### 8.8 Page Template Structure

Recommended standard structure:

```html
<main class="page">
  <section class="hero" aria-labelledby="page-title">
    <div class="eyebrow">AI Education Field Guide</div>
    <h1 id="page-title">Page Title</h1>
    <p>Short purpose statement.</p>
    <div class="metadata-row">
      <span class="pill">Expertise: Intermediate</span>
      <span class="pill">Audience: Technical leads</span>
      <span class="pill">Version: 1.0</span>
    </div>
  </section>

  <section class="content-grid">
    ...
  </section>

  <footer class="footer">
    ...
  </footer>
</main>
```

## 9. Markdown Documentation Plan

The repository should include Markdown versions or deeper companion documents for some HTML guides.

Recommended directories:

```text
docs/
  beginner/
  intermediate/
  advanced/
  expert/
  prompts/
  governance/
  templates/

pages/
  *.html

assets/
  css/
  js/
  images/

examples/
  prompts/
  plans/
```

In early versions, each HTML page may contain its own CSS for portability.  Later, extract shared CSS into:

```text
assets/css/ai-field-guide.css
```

Do this only after at least three pages share enough visual structure to justify it.

## 10. Reusable Prompt Library

The prompt library is implemented as static HTML under:

```text
pages/prompts/
```

Current prompt library pages:

```text
pages/prompts/prompting-basics.html
pages/prompts/email-and-communication-prompt.html
pages/prompts/document-review-prompt.html
pages/prompts/executive-summary-prompt.html
pages/prompts/meeting-summary-prompt.html
pages/prompts/vibe-brief-prompt.html
pages/prompts/implementation-plan-prompt.html
pages/prompts/checkpointed-execution-prompt.html
pages/prompts/code-review-prompt.html
pages/prompts/risk-review-prompt.html
```

Do not create Markdown prompt-library companion pages unless the repository direction changes.

Each prompt page should include:

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

## 11. Checkpointed Execution Doctrine

The repository should teach and model checkpointed execution.

Recommended standard wording:

```text
Implement one phase only.
Stop after completing that phase.
Summarize changed files, validation commands, assumptions, and blockers.
Do not proceed to the next phase until explicitly instructed.
```

This should appear in:

- `AGENTS.md`
- `CODEX.md`
- `PLAN_AI_EDUCATION.md`
- `pages/checkpointed-execution.html`
- `pages/prompts/checkpointed-execution-prompt.html`

### 11.1 Why Checkpointed Execution Matters

Checkpointed execution reduces:

```text
Context drift
Unreviewed blast radius
Unrelated refactors
Premature implementation
Architecture guessing
Hidden breaking changes
Testing omissions
Rollback confusion
```

It improves:

```text
Reviewability
Traceability
Team trust
Change control
Incremental learning
Safety
Agent reliability
```

## 12. Governance and Versioning

All governed documents must include a visible version.

Governed files include:

```text
AGENTS.md
CODEX.md
PLAN_AI_EDUCATION.md
index.html
pages/*.html
docs/**/*.md
examples/**/*.md
```

Use the versioning rules in `AGENTS.md`.

Every non-trivial change should update:

1. The edited file version.
2. `CODEX.md` inventory version.
3. The relevant index or navigation links.
4. Any changelog note if a changelog is later added.

Suggested future changelog file:

```text
CHANGELOG.md
```

Do not create it until the repository starts receiving multiple revisions unless desired from day one.

## 13. Initial Repository Structure

Recommended starting structure:

```text
.
├── AGENTS.md
├── CODEX.md
├── PLAN_AI_EDUCATION.md
├── README.md
├── index.html
├── pages/
│   ├── vibe-coding-vs-implementation-planning.html
│   └── checkpointed-execution.html
├── docs/
│   ├── beginner/
│   ├── intermediate/
│   ├── advanced/
│   ├── expert/
│   ├── governance/
│   ├── prompts/
│   └── templates/
├── assets/
│   ├── css/
│   ├── js/
│   └── images/
└── examples/
    ├── prompts/
    └── plans/
```

## 14. Implementation Phases

### Phase 0: Repository Bootstrap

Objectives:

- Create the repo.
- Add governance files.
- Add the first plan.
- Establish versioning and CODEX mapping.

Tasks:

```text
Create AGENTS.md.
Create CODEX.md.
Create PLAN_AI_EDUCATION.md.
Create README.md.
Create folders.
Commit initial structure.
```

Acceptance criteria:

```text
AGENTS.md includes repository rules.
CODEX.md maps all initial files.
PLAN_AI_EDUCATION.md explains the education program.
No secrets or production code exist in the repo.
```

### Phase 1: Import and Retrofit Existing HTML Pages

Objectives:

- Bring the two existing HTML pages into the new repo.
- Add expertise metadata.
- Normalize visual language enough for consistency.

Tasks:

```text
Add pages/vibe-coding-vs-implementation-planning.html.
Add pages/checkpointed-execution.html.
Add visible expertise badges.
Add meta tags.
Add version footer.
Ensure mobile layout still works.
Update CODEX.md.
Commit changes.
```

Acceptance criteria:

```text
Both pages open directly in a browser.
Both pages show expertise level.
Both pages show version.
Both pages are linked in CODEX.md.
```

### Phase 2: Create Root Index Page

Objectives:

- Create the main navigation page for the education library.

Tasks:

```text
Create index.html.
Add hero and education ladder explanation.
Add four columns: Beginner, Intermediate, Advanced, Expert.
Add cards for planned and existing pages.
Use target="_blank" and rel="noopener noreferrer" for guide links.
Add responsive mobile layout.
Add version footer.
Update CODEX.md.
Commit changes.
```

Acceptance criteria:

```text
Index opens in a browser.
All existing page links work.
Planned pages are visibly marked as planned or draft.
Columns collapse cleanly on mobile.
```

### Phase 3: Build Beginner Curriculum

Objectives:

- Create the foundational pages for all users.

Tasks:

```text
Create AI Literacy Basics.
Create Prompting Basics.
Create Hallucinations and Verification.
Create Privacy and Safe Use.
Create Human Accountability.
Update index.html.
Update CODEX.md.
Commit changes.
```

Acceptance criteria:

```text
Each page has expertise metadata.
Each page is understandable to non-technical users.
Each page includes practical examples.
Each page includes a review or self-check section.
```

### Phase 4: Build Intermediate Curriculum

Objectives:

- Create pages for frequent AI users and team leads.

Tasks:

```text
Create Practical Prompt Patterns.
Create Context Packaging.
Create AI Output Review.
Create Business Workflow Acceleration.
Refine Vibe vs. Implementation page if needed.
Refine Checkpointed Execution page if needed.
Update index.html.
Update CODEX.md.
Commit changes.
```

Acceptance criteria:

```text
Intermediate pages help users distinguish exploration from implementation.
Prompt examples are reusable.
Review checklists are clear.
```

### Phase 5: Build Advanced Curriculum

Objectives:

- Create technical and governance-adjacent AI pages.

Tasks:

```text
Create AI for Technical Teams.
Create Repository Orientation for AI Agents.
Create Implementation Plans and Specs.
Create Test-First AI Workflows.
Create AI Code Review.
Create Security, Privacy, and Governance.
Create Data Classification for AI Use.
Create Vendor and Tool Review.
Update index.html.
Update CODEX.md.
Commit changes.
```

Acceptance criteria:

```text
Advanced pages are useful to technical teams.
Pages avoid encouraging uncontrolled production edits.
Pages include validation, review, and rollback concepts where relevant.
```

### Phase 6: Build Expert Curriculum

Objectives:

- Create strategy, governance, and architecture pages.

Tasks:

```text
Create Agentic Coding Governance.
Create AI Operating Model.
Create RAG and Knowledge Governance.
Create AI Evaluation Frameworks.
Create Red-Teaming AI Workflows.
Create AI Security Architecture.
Create Cost and Context Management.
Create Strategic AI Portfolio.
Update index.html.
Update CODEX.md.
Commit changes.
```

Acceptance criteria:

```text
Expert pages support committee-level decision-making.
Pages discuss ownership, evidence, governance, risk, and operating model.
Pages do not read as generic AI hype.
```

### Phase 7: Prompt Library

Objectives:

- Provide reusable prompt templates that support the curriculum.

Tasks:

```text
Create pages/prompts/prompting-basics.html.
Create pages/prompts/email-and-communication-prompt.html.
Create pages/prompts/document-review-prompt.html.
Create pages/prompts/executive-summary-prompt.html.
Create pages/prompts/meeting-summary-prompt.html.
Create pages/prompts/vibe-brief-prompt.html.
Create pages/prompts/implementation-plan-prompt.html.
Create pages/prompts/checkpointed-execution-prompt.html.
Create pages/prompts/code-review-prompt.html.
Create pages/prompts/risk-review-prompt.html.
Update index.html.
Update CODEX.md.
Commit changes.
```

Acceptance criteria:

```text
Each prompt has use cases and limits.
Each prompt includes an output format.
Each prompt includes a review checklist.
```

### Phase 8: Shared CSS Extraction

Objectives:

- Reduce repeated CSS once several pages stabilize.

Tasks:

```text
Compare CSS across pages.
Extract shared visual language to assets/css/ai-field-guide.css.
Keep page-specific CSS minimal.
Update HTML references.
Verify pages still work locally.
Update CODEX.md.
Commit changes.
```

Acceptance criteria:

```text
Shared CSS reduces duplication.
Pages remain portable and visually consistent.
No page loses mobile responsiveness.
```

### Phase 9: Review and Publication

Objectives:

- Prepare the repository for internal sharing.

Tasks:

```text
Review all pages for consistency.
Check links.
Check versions.
Check CODEX inventory.
Review for sensitive information.
Run Markdown lint if configured.
Open index.html and key pages locally.
Commit final review updates.
```

Acceptance criteria:

```text
All existing links work.
All pages have visible expertise levels.
All governed files have visible versions.
CODEX.md matches repository contents.
No sensitive data is present.
```

## 15. Recommended AI Agent Workflow

Agents working in this repo should use checkpointed execution.

For any non-trivial request, use this flow:

```text
1. Read AGENTS.md.
2. Read CODEX.md.
3. Identify the relevant file or section.
4. Determine change classification: Minor, Major, or Full.
5. Make the smallest complete change.
6. Update visible version numbers.
7. Update CODEX.md.
8. Validate Markdown or HTML as appropriate.
9. Stage, commit, and push unless the user explicitly says not to.
10. Stop and report.
```

For phase-based implementation:

```text
Implement one phase only.
Do not proceed to the next phase without explicit instruction.
```

## 16. Validation Plan

### 16.1 Markdown Validation

If Markdown linting is configured, run it.  Until a tool is chosen, use the placeholder in `AGENTS.md`.

Manual Markdown checks:

```text
Headings are hierarchical.
Tables render cleanly.
Code fences close properly.
Links are not broken.
Visible version is present.
```

### 16.2 HTML Validation

Manual HTML checks:

```text
Open index.html locally.
Open each changed page locally.
Check desktop layout.
Check mobile layout with browser dev tools.
Check links open correctly.
Check _blank links use rel="noopener noreferrer".
Check visible expertise level.
Check visible version.
```

Optional future checks:

```text
HTML validator.
Link checker.
Accessibility checker.
Prettier for HTML/CSS.
Stylelint for shared CSS.
```

## 17. Risks and Mitigations

| Risk | Mitigation |
| --- | --- |
| The repository becomes a pile of disconnected pages | Maintain `index.html` and `CODEX.md` as navigation and inventory controls |
| AI-generated pages drift in tone and style | Use the visual language section and page template requirements |
| People read vibe coding as a universal delivery method | Repeat the distinction between exploration and implementation across the curriculum |
| Agents make broad uncontrolled edits | Enforce checkpointed execution in `AGENTS.md` |
| Versions become inaccurate | Require every change to update edited file versions and CODEX entries |
| Pages become too technical for beginners | Use expertise levels and audience tags |
| Pages become too generic for experts | Include governance, risk, validation, architecture, and ownership details |
| Sensitive information is accidentally committed | Keep scope documentation-only and ban secrets explicitly |

## 18. Definition of Done

The initial repository is ready when:

```text
AGENTS.md exists and defines repo rules.
CODEX.md exists and maps the repository.
PLAN_AI_EDUCATION.md exists and explains the program.
index.html exists and links to current guide pages.
The two existing HTML pages are included and show expertise levels.
Every governed file has a visible version.
The visual language is documented.
The education ladder is visible.
No production code, infrastructure code, or secrets exist in the repository.
```

The full education library is ready when:

```text
Beginner, Intermediate, Advanced, and Expert pages exist.
Each page has expertise metadata.
Each page appears on index.html.
Prompt templates exist.
Governance topics are covered.
Checkpointed execution is clearly explained.
CODEX.md accurately reflects file inventory and versions.
```

## 19. First Recommended Codex Prompt

Use this prompt after creating the repository:

```text
Read AGENTS.md, CODEX.md, and PLAN_AI_EDUCATION.md.
Implement Phase 0 only.
Create the initial repository structure and starter files described in the plan.
Do not create the full page library yet.
Do not proceed to Phase 1.
When complete, update versions and CODEX.md, then stage, commit, and push.
Stop and summarize changed files, validation performed, assumptions, and blockers.
```

## 20. Second Recommended Codex Prompt

Use this prompt after Phase 0 is complete:

```text
Read AGENTS.md, CODEX.md, and PLAN_AI_EDUCATION.md.
Implement Phase 1 only.
Import or create pages/vibe-coding-vs-implementation-planning.html and pages/checkpointed-execution.html.
Retrofit both pages with visible expertise level metadata, version metadata, and the shared AI Field Guide visual language where appropriate.
Do not proceed to Phase 2.
When complete, update versions and CODEX.md, then stage, commit, and push.
Stop and summarize changed files, validation performed, assumptions, and blockers.
```
