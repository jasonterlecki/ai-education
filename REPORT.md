# REPORT.md

Version: 1.0.4
Status: Draft review report
Expertise: Expert (audience: AI committee, maintainers)
Review date: 2026-10-21
Scope: English pages under `pages/en/` (87 HTML files: 14 Beginner, 22 Intermediate, 28 Advanced, 13 Expert, 10 Prompt Library)

## Method and limits

- Extracted the visible text from every `pages/en/**/*.html` file and searched it for vendor names, product-specific terms, dated or numeric claims, regulatory references, and key concepts.
- Read in full: the `SKILLS.md` Deep Dive, `MCP Basics`, and `Memory vs. Context vs. Instructions`.
- Read in part: `AGENTS.md Deep Dive`, `PLAN.md vs Agent Plan Mode`, and the lexicon's core entries.
- All other pages were checked only through keyword searches and spot checks. Treat this as a targeted review, not a line-by-line audit of ~124,000 words.
- No external sources were consulted. Statements about current vendor behavior, standards, and regulations below come from my background knowledge. Verify them before acting.

## Overall verdict

**The pages are largely accurate, relevant, and vendor-neutral. No page needs urgent correction.**

The content is principle-based (least privilege, human accountability, checkpoints, verify before reuse), so it ages well. It contains almost no model names, prices, version numbers, or benchmarks that would go stale. The OpenAI mindset shows in only a few places (below). The larger problems are gaps and one tone issue, not errors.

## Findings: accuracy and neutrality

| # | Priority | Page(s) | Finding | Recommendation |
| --- | --- | --- | --- | --- |
| A1 | Medium | `advanced/agents-md-deep-dive.html` | Section "How Codex-style instruction discovery works" describes discovery as one tool's behavior, including a "Codex home directory". AGENTS.md is an emerging cross-tool convention, but not every tool reads it natively. Some tools use their own file names (for example `CLAUDE.md`, `GEMINI.md`, Copilot and Cursor rule files). Some can reference or symlink to `AGENTS.md`. | Retitle to "How instruction discovery typically works" and add a short note: "Check your tool's documentation for the file names it reads and for precedence rules." Name two or three alternatives as examples without endorsing any. |
| A2 | Medium | `advanced/skills-md-deep-dive.html` and every page that mentions `SKILLS.md` (also `agent-context-suite`, `project-file-structure-for-beginners`, `md-hierarchy-for-ai-agents`, `agents-md-deep-dive`, `test-first-ai-workflows`, `token-budgeting-for-real-work`) | **Decision: use `SKILL.md`.** The recognized unit is a skill folder with a singular `SKILL.md` manifest. The plural `SKILLS.md` catalog idea is not part of that standard. The skeleton also shows `agents/openai.yaml`, which is not in the open spec. | Replace `SKILLS.md` with `SKILL.md` (and "skills folder" where the catalog idea is meant) across all pages, including the page title and the "SKILLS.md Deep Dive" link text in navigation. Update `NAVIGATION.md`, `index.html`, `CODEX.md`, and the French siblings to match. Remove `agents/openai.yaml` from the example tree. It is not part of the open Agent Skills specification and I found no current documentation for it. Replace it with the spec's standard optional folders: `scripts/` (executable helpers), `references/` (docs loaded on demand), and `assets/` (templates and static files). The example already shows templates and checklists, so these may just need regrouping under those names. Optionally mention the spec's optional frontmatter fields (`license`, `compatibility`, `metadata`, `allowed-tools`) and that `name` must match the folder name. Source: the open spec at agentskills.io/specification. |
| A3 | Low | `intermediate/plan-md-vs-agent-plan-mode.html` | The tool list "Codex, Cursor, Claude Code, Windsurf, Copilot" is accurate but will date quickly. | Replace with "different AI coding tools" or keep the list and mark it as examples. |
| A4 | Low | `beginner/ai-lexicon-for-beginners.html` | The Temperature entry is correct but incomplete. Many current reasoning-oriented models fix or ignore sampling settings, and low temperature does not prevent hallucination. A beginner may infer that it does. | Add: "Lower temperature makes output more consistent, not more correct. Some tools do not expose it." |
| A5 | Low | `advanced/mcp-basics.html`, `expert/mcp-security-and-permissions.html` | MCP descriptions (host/client/server, tools/resources/prompts) are accurate at a conceptual level. MCP evolves quickly (authorization, transports, remote servers). The pages do not say so. | Add a one-line "Protocol details change; check the current specification" note. Optionally mention OAuth-based authorization for remote servers on the expert page. |
| A6 | Low | `intermediate/agent-handoff-notes.html`, `advanced/agent-observability.html` | The Observability page correctly says not to depend on private chain-of-thought as the audit record. This is good guidance and needs no change. | None. Listed as a positive. |
| A7 | Low | `advanced/chunking-strategy.html`, `embeddings-and-vector-search.html`, `retrieval-failure-modes.html` | Content is sound (hybrid search, reranking, metadata filters, ACLs on chunks). Retrieval practice has moved toward agentic or tool-based retrieval and very long context windows. The failure-modes page mentions agentic retrieval once. | Add a short "when retrieval is not needed" or "long context vs retrieval" decision card to the embeddings page. |

## Findings: tone and presentation

| # | Priority | Finding | Recommendation |
| --- | --- | --- | --- |
| T1 | High | The whimsical style ("goblin", "raccoon energy", "paperwork dragon", "fog archaeology", "bow tie") appears about 95 times across 42 pages. Decision: this is a model quirk, not an editorial choice, so the whole site gets a voice rewrite to semi-informal and friendly. | Write a voice guide first (in `PLAN_AI_EDUCATION.md`), pilot one page per level, then roll out by level. See the order of work below. |
| T2 | Low | 23 pages show the hero badge `Core Skill: Apply the guide`. This is a placeholder-like label that tells the reader nothing, and the `AGENTS.md` badge rules ask for "what the reader will learn or practice". Other pages use `Use: Use when answers feel inconsistent`, which repeats the label. | Replace with specific skills per page, for example "Core Skill: Separate memory, context, and instructions". Fix the doubled "Use: Use when". |
| T3 | Low | `beginner/multimodal-ai-basics-corrected.html` is in the repo as a Draft but is not linked from `NAVIGATION.md` or `index.html`. | Merge its CSS fix into the active page and retire the copy, or document why it stays. |
| T4 | Low | `beginner/md-hierarchy-for-ai-agents.html` (about 15 KB) and `intermediate/review-gates-and-rollback.html` (about 16 KB) are roughly half the size of their peers. | Check whether they are intentionally short or need parity with the others. |

## Gaps

### Gaps (G3 is the most important; G2 is out of scope)

| # | Gap | Why it matters | Suggested vehicle |
| --- | --- | --- | --- |
| G1 | **Security frameworks (optional).** No page mentions OWASP guidance for LLM applications. Searches returned zero hits. This is voluntary technical guidance and not law, so it is jurisdiction-neutral. | The security pages are practical but do not point readers to a widely used external reference list. | Add a short "further reading" card to `prompt-injection-for-agents` or `ai-security-architecture`. NIST AI RMF and ISO/IEC 42001 are voluntary frameworks and could be listed the same way, if you want them. |
| G2 | **Out of scope: laws, regulations, and copyright.** Not recommended. The site cannot account for every jurisdiction, and `disclaimer.html` already covers professional and legal review. | Decision made after the first draft of this report. | None. If wanted later, a single line in existing pages saying "ownership, licensing, and disclosure rules vary by place; check your organization's policy" is enough. |
| G3 | **Tool data-handling tiers.** The privacy pages tell users not to paste sensitive data. They do not explain the practical difference between consumer, team or business, enterprise, and API tiers: training-use defaults, retention, admin controls, and opt-outs. The vendor-selection page mentions opt-outs only in passing. | The most common real-world mistake is using a personal account for work. The pages say "approved tools" but never explain what makes a tool approved. | Add a comparison card to `privacy-and-safe-use` (Beginner) and a checklist to `ai-vendor-and-tool-selection` (Expert). Keep it vendor-neutral and tell readers to verify against current vendor terms. |

### Moderate gaps

| # | Gap | Suggested action |
| --- | --- | --- |
| G4 | **Bias and fairness** appear in 13 pages, but only as a side note; `ai-for-sensitive-decisions` is the one page that treats it in depth. There is no dedicated treatment of testing for disparate outcomes. | Add a short evaluation section to `evaluation-and-red-teaming` or `evaluation-harnesses`. |
| G5 | **Supply-chain risk from AI-suggested dependencies.** `ai-generated-code-smells` says to verify calls and review licenses, but never names package hallucination (invented or look-alike package names that attackers can register). | Add one risk card with a "verify the package exists, is maintained, and is the one you intend" check. |
| G6 | **Sycophancy and over-agreement.** Zero hits. The hallucination and verification pages cover invented facts but not the model's tendency to agree with the user's framing. | Add a card to `hallucinations-and-verification` and a "ask for counterarguments" tip to `prompting-basics`. |
| G7 | **Agent features that are now mainstream**: sub-agents and parallel agents, isolated work trees or branches per agent, hooks, and browser or computer-use agents. Zero hits for sub-agents, worktrees, and computer use. Prompt-injection and permission pages cover the risk generally, but not these modes. | Extend `agent-permissions-ladder` and `prompt-injection-for-agents` with a short section on multi-agent and browser-agent setups. Keep it principle-based. |
| G8 | **Reasoning models and cost levers.** Cost pages mention caching and model routing. They do not explain that reasoning or "thinking" modes consume extra tokens, or that provider-side prompt caching and batch options exist. | Add two bullets to `token-economy` and `model-selection-and-cost-management`. |
| G9 | **AI disclosure and synthetic media**, as organizational practice and not law. No mention of deepfakes, watermarking, or when to tell recipients that AI helped. | Short card in `human-accountability` or `ai-content-lifecycle`. |
| G10 | **Environmental and energy cost.** Seven loose mentions, no treatment. | Optional. Low priority for most audiences. |

### Not a gap

- Prompt injection, least privilege, human-in-the-loop, checkpointed execution, evaluation, observability, vendor selection, and shadow AI are well covered across levels.
- The Beginner to Expert progression is coherent, and the exploration vs. implementation distinction is applied consistently.

## Suggested order of work

Each item is a separate checkpoint, per `AGENTS.md`. Stop after each one.

1. **Voice guide.** Add a "semi-informal and friendly" section to `PLAN_AI_EDUCATION.md` (Major bump). Plain language and direct address are fine. Allow at most one light metaphor per section. List the stock phrases to retire.
2. **Pilot.** Rewrite one Beginner, one Intermediate, one Advanced, and one Expert page. Review the voice before continuing.
3. **Rollout by level**, in batches: Beginner, Intermediate, Advanced, Expert, Prompt Library. Fix the hero badges (T2) in the same pass as each page.
4. **Copy fixes outside the voice work**: A1, A2, A3, A4, A5.
5. **Housekeeping**: T3, T4.
6. **New content**, in this order: G3, then G5 to G9, and G1 if wanted. G2 is out of scope.
7. **French pages.** Decide whether to retranslate each page as its English version lands or in a batch afterward, per `PLAN_TRANSLATION.md`.
8. For any new pages, update `NAVIGATION.md`, `index.html`, `CODEX.md`, and `PLAN_AI_EDUCATION.md` together.

## Caveats

- Page counts and percentages come from keyword searches and may miss pages that use different wording.
- The "no mention" findings mean the exact terms were not found, not that the idea is absent. Some pages may cover the concept in other words.
- Before publishing anything based on this report, verify any claim about current vendor features, standards, or law.
