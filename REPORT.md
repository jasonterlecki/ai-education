# REPORT.md

Version: 1.8.0
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
| T3 | Resolved | `beginner/multimodal-ai-basics-corrected.html` was listed as an unlinked Draft in `CODEX.md`. On review, the file no longer exists. Commit `6c6d7dc` ("Update multimodal AI basics page", 2026-05-18) merged the spacing fix into `multimodal-ai-basics.html` and deleted the copy. The active page already sits at position 9 in Beginner navigation, so there is nothing to insert. My earlier finding was wrong. | Remove the stale `CODEX.md` row for the corrected file (done). No page or navigation change needed. |
| T4 | Low | `beginner/md-hierarchy-for-ai-agents.html` (about 15 KB) and `intermediate/review-gates-and-rollback.html` (about 16 KB) are roughly half the size of their peers. | Check whether they are intentionally short or need parity with the others. |

## Gaps

### Gaps (G3 is the most important)

| # | Gap | Why it matters | Suggested vehicle |
| --- | --- | --- | --- |
| G1 | **Security frameworks (optional).** No page mentions OWASP guidance for LLM applications. Searches returned zero hits. This is voluntary technical guidance and not law, so it is jurisdiction-neutral. | The security pages are practical but do not point readers to a widely used external reference list. | Add a short "further reading" card to `prompt-injection-for-agents` or `ai-security-architecture`. NIST AI RMF and ISO/IEC 42001 are voluntary frameworks and could be listed the same way, if you want them. |
| G2 | **Laws, regulations, and copyright: one short neutral page, no legal claims.** The site cannot account for every jurisdiction, so it must not say what is or is not legal. A brief page is still useful so readers know to check. | Readers may assume the rules are the same everywhere, or that the site has covered them. `disclaimer.html` covers professional review but not this specific point. | Add a small Beginner page. See "Planned page: Laws and Local Rules" below. |
| G3 | **Tool data-handling tiers.** The privacy pages tell users not to paste sensitive data. They do not explain the practical difference between consumer, team or business, enterprise, and API tiers: training-use defaults, retention, admin controls, and opt-outs. The vendor-selection page mentions opt-outs only in passing. | The most common real-world mistake is using a personal account for work. The pages say "approved tools" but never explain what makes a tool approved. | Add a comparison card to `privacy-and-safe-use` (Beginner) and a checklist to `ai-vendor-and-tool-selection` (Expert). Keep it vendor-neutral and tell readers to verify against current vendor terms. |

### Moderate gaps

| # | Gap | Suggested action |
| --- | --- | --- |
| G4 | **Bias and fairness** appear in 13 pages, but only as a side note; `ai-for-sensitive-decisions` is the one page that treats it in depth. There is no dedicated treatment of testing for disparate outcomes. | Add a short evaluation section to `evaluation-and-red-teaming` or `evaluation-harnesses`. |
| G5 | **Hallucination topics, one place only.** The site already has `hallucinations-and-verification`, so these are not repeated on other pages. Two things that page may be missing: invented package or library names in AI-suggested code, and a model's tendency to agree with the user's framing (sycophancy). | Add one card each to `hallucinations-and-verification` only, after reading that page in full to confirm they are missing. Remove the earlier suggestions for `ai-generated-code-smells` and `prompting-basics`. |
| G6 | *Merged into G5.* | None. |
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
4. **Copy fixes outside the voice work**: A1, A2, A3, A4, A5, and F1 to F3, F7 to F10. F1 is the most important.
4a. **Prompt library alignment (F4, F5)** and **overlap decisions (F6)**.
5. **Housekeeping**: T3, T4.
6. **New content**, in this order: the G2 page (small, specified below), G3, then G5, G7 to G9, and G1 if wanted.
7. **French pages.** Done (see "Open items").
8. For any new pages, update `NAVIGATION.md`, `index.html`, `CODEX.md`, and `PLAN_AI_EDUCATION.md` together.

## Planned page: Laws and Local Rules (G2)

A small page, not yet created. Rules for the author:

- **Expertise:** Beginner. **Suggested filename:** `pages/en/beginner/laws-and-local-rules.html`. Place it after Privacy and Safe Use in the navigation, and confirm against `NAVIGATION.md`.
- **Hero badge:** `Beginner Field Guide · Local Rules`, per the badge rules in `AGENTS.md`.
- **Message, in plain words:**
  - Different countries and regions have different rules about using AI and about what AI helps produce, such as ownership and copyright of the output.
  - The rules are changing, so what applies can change over time.
  - If you plan to use AI for work, check what your local laws say and what your organization's policies say. When unsure, ask the people responsible for legal or compliance matters.
- **Do not:**
  - State or imply what is legal or not legal anywhere.
  - Name, tie to, or compare any nation, region, bloc, statute, regulator, court case, or framework. No examples of specific laws, even as illustrations.
  - Give advice that sounds like legal guidance.
- **Format:** a short hero, one decision strip ("Check local law, check company policy, ask if unsure"), a short checklist card, and a link to `disclaimer.html`. Keep it well under the size of the other pages.
- **Linked updates:** `NAVIGATION.md`, `index.html`, `CODEX.md`, `PLAN_AI_EDUCATION.md`, and the French sibling per `PLAN_TRANSLATION.md`. Optionally add a one-line link from `privacy-and-safe-use` and `ai-content-lifecycle`.

## Status on the `test` branch

All findings below were implemented on branch `test` (English pages only). French pages were not touched. Verification: every English page passes a headless-Chrome contrast audit in dark mode, internal links resolve, nav cards match `NAVIGATION.md`, page versions match `CODEX.md`, and no `_blank` links.

| Finding | Status | What changed |
| --- | --- | --- |
| T1 voice | Done | Stock whimsy removed from all five levels, in two sweeps. A few idioms ("magic prompt", "not magic") were kept as plain speech. |
| T2 badges | Done | All "Apply the guide" / "Reuse the prompt" pills replaced with specific skills. |
| T3, T4 | Done | `md-hierarchy-for-ai-agents` gained a "when two files disagree" section. `review-gates-and-rollback` was rebuilt (see F6). |
| A1, A3, A5, A7 | Done | Neutral instruction-discovery wording; tool list made generic; MCP "details change" notes and OAuth mention; "Do you need retrieval at all?" section. |
| A2 | Done | `SKILL.md` everywhere in English pages and the hierarchy SVG; `openai.yaml` removed; skill-folder layout shown. **Decision: keep the filename `skills-md-deep-dive.html`** so existing links stay valid. |
| A4, F8 | Done | Temperature caveat; 11 new lexicon terms (reasoning model, open-weight model, context engineering, synthetic data, structured output, skill, sub-agent, guardrails, sycophancy, vibe coding, agentic engineering). |
| F1 | Done | "No complete defense is known" callouts on all four prompt-injection and MCP security pages; "until the attack gets tired" wording replaced. |
| F2 | Done | Definitions carried to the intro, planning, checkpointed-execution, vibe-brief and lexicon pages, `CODEX.md` and `PLAN_AI_EDUCATION.md`, each with a "terms are still settling" note. |
| F3 | Done | "Always present, always relevant" and hierarchy-as-authority wording softened; tool support varies; instruction files do not guarantee compliance. |
| F4 | Done | "Do not use when", example input, expected output, implementation lines and human-review caution on all 10 prompt pages (shared `.fg-fit` styles). |
| F5 | Done | Prompt page retitled "Reusable Prompt Template", scaffold aligned and cross-linked; Beginner page keeps five ingredients plus a closing review habit. |
| F6 | Done | Token pages split (concept vs. practice); model-selection and cost-controls trimmed and cross-linked; evaluation pair given intro lines, a single loop, a judge-model rule and cross-links; plan family has a "which page" strip; `review-gates-and-rollback` rebuilt (about 900 words) and `governed-ai-delivery` extended. |
| F7, F9, F10 | Done | Audio wording; obviously fake sample values; chat-history and sharing note; three extra prompting habits. |
| F11, G7 | Done | Sub-agents, parallel agents, hooks, browser agents in the permissions ladder and prompt-injection page. |
| G1 | Done | Further-reading callouts (OWASP guidance, ISO/IEC 42001) as voluntary references; no national framework named. |
| G2 | Done | `pages/en/beginner/laws-and-local-rules.html` (1.0). Names no nation, bloc, statute or regulator, makes no legal claims. Wired into `NAVIGATION.md`, `index.html`, `CODEX.md`, `PLAN_AI_EDUCATION.md`. |
| G3 | Done | Account-type section on `privacy-and-safe-use`; four-card section on the vendor page. |
| G4, G9, G10 | Done | Bias-testing limits and red-team scope on the evaluation page; "Saying when AI helped" on `ai-content-lifecycle`; one compute/energy line on `token-economy`. |
| G5 | Done | Invented packages and agreement (sycophancy) added to `hallucinations-and-verification` only, plus a code row in its verification table. |
| G8 | Done | Output vs. input cost, thinking tokens, caching, batching on the token and model-selection pages. |
| Visuals | Done | Shared theme `assets/css/field-guide.css` (1.2.0) linked from every English page; per-page dark-mode fixes generated from the audit. |

### Open items

- **French pages: in sync with the English findings.** All changed English text now has a French counterpart: the voice rewrite, new sections, caveats, hero badges, `SKILL.md` naming and the prompt-library fit panels. The method edited only the French sentences whose English counterpart changed, located by a checked alignment, and inserted or removed whole sections by structure. An earlier attempt that regenerated whole pages scrambled labels and was reverted; a second pass with a weaker check misplaced 59 sentences and was also reverted before the final run. Every French page has the shared theme, the visible Expertise / Public / À utiliser pour line, and passes the dark-mode contrast audit. A French reviewer should still read the new translations, as they were written without one.
- **Theme caveat**: dark-mode fixes are per-page style blocks (marked `fg-dark-fixes`). If a page's own CSS changes, re-run the contrast audit.
- Not implemented on purpose: a merged token page, a merged evaluation page (verdict was keep both).

## Full read results (second pass)

All 87 English pages were read after the first scan: the main body text of each page, with repeated prompt templates and long example blocks skimmed. The Beginner and Intermediate pages were read most closely. Several Advanced and Expert pages were read at section level (the first several substantive paragraphs per section, not every card), so a subtle error in a card I did not reach could remain.

**Result: still no fundamentally wrong pages.** The content is consistent, careful, and well aligned with its stated levels. The findings below are about overstatement, missing caveats, structure, and overlap. None needs an urgent fix.

| # | Priority | Page(s) | Finding | Recommendation |
| --- | --- | --- | --- | --- |
| F1 | High | `intermediate/prompt-injection-for-business-users`, `advanced/prompt-injection-for-agents`, `expert/mcp-security-and-permissions`, `expert/ai-security-architecture` | None of the prompt-injection pages says plainly that there is no known complete defense. The agent page says to layer controls "until the attack gets tired", which implies a stronger guarantee than exists. Readers could think a good filter or a strong instruction solves it. | Add one clear statement on each page: injection cannot currently be fully prevented, so assume some attempts will work and limit what a manipulated agent can reach (least privilege, approvals, no untrusted content plus sensitive data plus outbound action in one session). |
| F2 | High | `beginner/introduction-to-vibe-coding`, `intermediate/vibe-coding-vs-implementation-planning`, `intermediate/checkpointed-execution`, the `vibe-brief` prompt, `CODEX.md`, `PLAN_AI_EDUCATION.md`, `index.html`, and about 36 pages that use the term | **Decision: the site teaches two modes. *Vibe coding* is exploratory, unstructured, intent-first work: describe what you want, with little up-front planning, specification, documentation, or testing, and with the output often accepted without close review. *Agentic engineering* is the disciplined mode for real systems: plans and specs, checkpoints, tests and validation, scoped permissions, and human review of the result.** Today the site defines vibe coding more broadly (any exploratory AI-assisted making) and has no name for the structured mode. The repeated rule "vibe coding for exploration, planning for real systems, checkpointed execution for controlled agent work" should map onto these two terms. | Add a short definitions card to the two vibe-coding pages and use "agentic engineering" for the structured mode where the pages now say "implementation planning plus checkpointed execution". Keep "vibe coding" for exploration, including non-code exploration, but say so. Add both terms to the lexicon. Update the one-line principle in `CODEX.md`. Before publishing, confirm how the term "agentic engineering" is currently used by the wider community; I have not verified the sources. |
| F3 | Medium | `beginner/md-hierarchy-for-ai-agents`, `beginner/agents-md-vs-plan-md`, `beginner/project-file-structure-for-beginners`, `advanced/agent-context-suite`, `advanced/agents-md-deep-dive` | Overstatements: AGENTS.md is "always present and always relevant", and the file hierarchy is described as if tools enforce an authority order. In practice, support for instruction files, file names, and precedence varies by tool, and an agent may still ignore a rule. | Describe the hierarchy as a recommended convention, say tool support varies, and note that instruction files guide behavior but do not guarantee compliance. Keep the guidance that important rules also need technical controls. |
| F4 | Medium | all 10 pages under `prompts/` | They do not follow the Prompt Library Rules in `AGENTS.md`. None has a "Do not use when" section or labeled "Example input" and "Expected output" sections (the "Weak prompt / Stronger prompt" pairs are close but not the same). Only the checkpointed-execution prompt carries the five implementation lines (inspect before editing, one phase only, no unrelated changes, validate, stop and report). The implementation-plan prompt and the vibe-brief prompt do not. Several sensitive-topic prompts lack an explicit human-review caution. | Either add the missing sections, or relax the rule in `AGENTS.md` to match the pages as built. The first is more consistent with the stated goal. |
| F5 | Medium | `prompts/prompting-basics` and `beginner/prompting-basics` | Same title, related topic, different job. Verdict: **keep both, retitle and align.** See "Overlap evaluation (F5, F6)" below. | See the evaluation section. |
| F6 | Medium | several | Evaluated pair by pair. Verdict: **no page needs deleting.** One pair needs a real split (token pages), one page needs real content (`review-gates-and-rollback`), the rest need trimming and cross-links. | See the evaluation section. |
| F7 | Low | `beginner/multimodal-ai-basics` | "Audio often works through transcription first" is true for some tools and not others. | Say "some tools transcribe audio first, which can mangle names and terms". |
| F8 | Low | `beginner/ai-lexicon-for-beginners` | Missing terms that now appear across the site or in current tools: reasoning model, open-weight model, guardrails, sycophancy, synthetic data, structured output, skill, sub-agent, context engineering. | Add the ones the site uses elsewhere. Keep entries short. |
| F9 | Low | `beginner/privacy-and-safe-use` | The "before" example uses an SSN-shaped number and a card ending, which look like real data. The page also does not mention chat history, shared links, or deleted chats possibly remaining in logs. | Use obviously fake values (for example, "000-00-0000") and add a short note on history and sharing. |
| F10 | Low | `beginner/prompting-basics` | Missing three common habits: tell the model it may say "I don't know", iterate in the same conversation, and keep step-by-step instructions optional for newer reasoning-style models. | Add one short card or three bullets. |
| F11 | Low | `advanced/ai-coding-agents`, `advanced/agent-permissions-ladder` | Good coverage of permissions and stop points. Missing modern modes noted in G7: sub-agents, parallel agents in isolated branches, and browser or computer-use agents. | See G7. |

Items from this pass that need no action: the hallucination page, source-quality page, MCP basics, retrieval and chunking pages, observability, risk tiers, and the Expert governance pages read as accurate and coherent.

## Overlap evaluation (F5, F6)

Each pair was read in full. The question was whether the two pages answer the same question for the same reader. Where they do not, the fix is to sharpen the split and trim duplicated blocks, not to merge. Every change below stays inside the page's own level: no Beginner page picks up Expert vocabulary, and no Expert page re-teaches basics.

### Verdict summary

| Pair | Same page twice? | Verdict |
| --- | --- | --- |
| Prompting Basics (Beginner) / Prompting Basics Template (Prompt Library) | No. One teaches, one is a tool. | Keep both. Retitle, align the scaffold, cross-link. |
| Token Economy / Token Budgeting for Real Work (both Intermediate) | Largely yes. About half the content is duplicated. | Keep both, but split them cleanly: "why and what" vs. "how". Remove the duplicated blocks. |
| Model Selection and Cost Management / Cost Controls for Teams (both Expert) | No. Per-task decision vs. organizational spend governance. | Keep both. Trim two shared blocks to pointers. |
| Evaluation and Red Teaming / Evaluation Harnesses (both Expert) | Partly. Different lenses on one loop. | Keep both. Make the split explicit and remove the duplicated loop. |
| Review Gates and Rollback (Intermediate) / Governed AI Delivery (Advanced) | No, but the Intermediate page is a stub. | Keep both. Rebuild the Intermediate page (see "Extra for `review-gates-and-rollback`"). |
| AGENTS.md vs. PLAN.md / Where Should the Plan Live? / PLAN vs SPEC vs RUNBOOK / Implementation Plans and Specs | No. Four different questions. | Keep all four. Add a short "which page answers my question" cross-link. |

### 1. Prompting Basics (F5)

| | Beginner page | Prompt Library page |
| --- | --- | --- |
| Job | Teaches the habit | Gives a copy-ready template |
| Scaffold | "Five ingredients", but the skeleton and matrix show six (review requirements) | "Seven-part" scaffold (adds Role and Safety note) |
| Unique value | Prompt upgrades, "when the answer is bad" diagnostics | Weak vs. stronger prompt, task-type customization matrix |

Findings:

- **The title collision is the real problem.** A search result or a nav list shows two identical names.
- **Internal inconsistency on the Beginner page.** It says "five ingredients", then the skeleton and the matrix both list a sixth (review requirements). Either call it six, or keep five and present review as a separate closing step. Recommended: five ingredients plus "ask for review points" as the sixth habit, stated that way everywhere.
- **The two scaffolds disagree.** The Beginner page has no Role; the library page has Role and Safety note. A reader moving from one to the other sees two different "official" structures. Recommended: the library page is the Beginner scaffold plus two optional extras (Role, Safety note), and says so.
- **Level fit.** Keep the Beginner page free of tooling vocabulary. Keep "jurisdiction" and similar words out of the library constraints list unless explained (it is a G2 neutrality risk as well as a level one).
- Retitle the library page: "Reusable Prompt Template". Add one cross-link each way ("learn the five parts first" / "grab the template").
- Library rules gap (F4): the page lacks "Do not use when", "Example input" and "Expected output".

### 2. Token Economy / Token Budgeting for Real Work (F6)

Both are Intermediate, adjacent in the nav, and tagged `FinOps`. The overlap is large:

| Block | Token Economy | Token Budgeting |
| --- | --- | --- |
| Reusable prompt | "help me reduce token waste" | "help me budget the context" (near-identical) |
| Checklist | Preflight checklist | Budget checklist (6 of 7 items equivalent) |
| Handoff pattern | Handoff capsule | Checkpoint capsule |
| Source pattern | Evidence ledger | Source ledger |
| Situation table | Token economy decision matrix | "Budgeting by real workflow" and the Prompt/file/summary/omit table |

What is genuinely different:

- **Token Economy** covers what tokens are, what they pay for (input, output, context, tool results), the repeat and waste factors, and the common traps.
- **Token Budgeting** covers the five buckets, routing context to the right place, and the preflight workflow.

Recommendation: **keep both, with a clean split.**

- Economy = *why and what*: the concept and the cost mechanics. Keep the basic idea, what tokens pay for, the token math model, and the traps. Drop its prompt, its checklist and its "patterns" block, and link to Budgeting for them.
- Budgeting = *how*: keep buckets, routing, preflight, workflows, prompt and checklist. Drop the repeated capsule/ledger duplicates or keep one copy.
- Add a one-line "how this differs" to each.
- Content gaps in Economy (G8): output tokens usually cost more than input tokens, reasoning/thinking tokens count, prompt caching and batch options exist, and context limits cause truncation. Keep the wording generic and tell readers to check current provider pricing. No numbers.
- Level check: Intermediate readers need the concept ("a token is a chunk of text") but not provider billing detail. Put billing mechanics in one short box; leave the rest to the Expert cost pages.
- Fix: Budgeting still says `SKILLS.md` (A2). Economy hero badge is "Apply the guide" (T2).

### 3. Model Selection and Cost Management / Cost Controls for Teams (F6)

Different questions, same Expert level:

- **Model Selection** asks: *which model, how much context, what review, for this task?* (classify the task, capability ladder, routing matrix.)
- **Cost Controls** asks: *how does an organization keep AI spend owned, visible and bounded?* (budgets with owners, quotas, spend register, renewal brief, shadow spend.)

Verdict: keep both. The overlap is two blocks and one list:

- Model Selection's closing section "Govern the route, not just the invoice" (approved catalog, routing policy, budget guardrails, evaluation scoreboard, cleanup) restates Cost Controls. Replace it with a short paragraph and a link.
- Cost Controls' "Model routing" lever and the "Premium by default" and "Retry storms" failure modes repeat Model Selection's "Cost traps". Keep the traps on one page (Model Selection, since it is the per-task view) and point to them from the other.
- Both include a reusable prompt. They serve different jobs (classify a task / review a spend profile), so keep both.

Things to amend, at Expert depth:

- **Capability ladder is dated.** It treats "Reasoning" and "Long context" as separate model classes. Many current models have adjustable reasoning depth and long context built in. Reword it as *capabilities to match*, not *tiers of model*, and say the names change.
- **Caching and batching (G8).** Cost Controls' "Caching and reuse" covers reusing answers but not provider-side prompt caching or batch options. Add one line to each, generic and unpriced.
- **Spend limits at the account level.** Cost Controls lists budgets with owners but not the provider-side controls that make them real (per-project keys, usage caps, alerts). Add a line.
- **Tone:** both pages carry heavy whimsy ("tiny billing goblin", "raccoon in a trench coat", "invoice dragon"). Rewrite in the voice pass.
- Hero badges: "Apply the guide" (Model Selection) and a two-pill set that omits Risk on Cost Controls. Fix in T2.

### 4. Evaluation and Red Teaming / Evaluation Harnesses (F6)

Different lenses on one activity:

- **Evaluation Harnesses**: the *machinery*. Datasets, graders, thresholds, run metadata, artifacts, grader choice.
- **Evaluation and Red Teaming**: the *what to test*. Risk lanes, red-team probes, failure patterns, scoring lanes.

Overlap: both define "the evaluation loop" (nearly the same five or six steps), both have a "regression suite / promote regressions" idea, both have a failure-taxonomy block, both have a reusable prompt, and both have a score-lanes block.

Verdict: keep both and make the dependency explicit.

- **Reading order is already consistent** in `NAVIGATION.md` (Harnesses at 76, then Red Teaming at 77). Make that sequence explicit with one intro line on each: Harnesses is the machinery, Red Teaming is what to point it at.
- Keep the loop on only one page (Harnesses, since it is the "operational" page). On the other, replace it with one sentence and a link.
- Merge the two failure taxonomies into one table on one page, or at least align the names. Today they use "Fact / Scope / Policy / Retrieval / Tool / Expectation failure" on one page and "False precision / Authority laundering / Scope seepage / Policy bypass / Unequal assumptions / Silent degradation" on the other.
- **LLM-as-judge needs a stronger caveat** in Harnesses: judges need calibration, position bias and self-preference exist, and a judge must not approve its own family's output. The page has a short version; make it a visible rule at Expert level.
- **Bias (G4).** Red Teaming already has a paired-prompt bias probe. Add a note that a clean result on one test set is not a bias-free result, and that no test replaces policy review by humans. No legal claims.
- **Red teaming scope.** Add a sentence that red-team testing should be run only against systems you are authorized to test, in a non-production environment, with a named owner. (AGENTS.md scope rule.)
- Tone: "pocket full of bees", "tiny goblins", "fake mustache", "dragon respawn with a clipboard". Rewrite in the voice pass.

### 5. Review Gates and Rollback / Governed AI Delivery (F6)

These are **not** duplicates, but they are badly mismatched in depth: the Intermediate page is 384 words and nearly a list of nouns; the Advanced page is 1,630 words with risk-tiered gates, rollback-by-work-type and a failure catalogue. The shape is right (Intermediate teaches the habit, Advanced builds the system). The Intermediate page just has no teaching content yet.

Structural defects on the Intermediate page (separate from content):

- Two heroes and two "Core Skill" pills.
- In-page "Previous: Plans and Specs / Next: Blast Radius Thinking" links that conflict with the canonical navigation card (Previous: PLAN vs SPEC vs RUNBOOK, Next: Checkpointed Execution). It also has "Back to index", which duplicates Home.
- A visible footer "Page version 1.0" while the file is 1.2.4. `AGENTS.md` says versions are not visible page text.
- Hero badges "Apply the guide" and "Rule: Workflow owners and reviewers" (not a rule).

### Extra for `review-gates-and-rollback` (Intermediate)

What to add, kept at Intermediate level (an individual or team lead who uses AI and approves changes; no organization-wide governance machinery):

1. **Why AI changes the review problem.** AI output is fluent, fast and voluminous. The risk is the reviewer trusting a summary or skimming a big diff. One short section: *review the change, not the explanation of the change*.
2. **What to look for in an AI-made diff.** Unrequested changes, deleted or weakened tests, new dependencies, hard-coded values, changed config, and secrets. Link to `ai-generated-code-smells` (Advanced) for the longer list, and `code-review-with-ai`.
3. **"Tests pass" is a weak gate by itself.** AI can write tests that pass trivially or edit a failing test. Check that the tests were not changed to fit, and that a test fails before the fix. Short, plain.
4. **Three gate levels, not four.** A simple low / medium / high table: what gate, who approves, what rollback. Link to `blast-radius-thinking` for how to decide the level. Keep "Blocked" and risk-tier mapping for the Advanced page.
5. **Rollback basics.** Capture the previous state before the change; know the exact undo; test it once when the stakes justify it. Include non-code work: a document (version history), a message (cannot be unsent, so the gate must come before sending).
6. **Some things cannot be rolled back.** Sending, deleting, paying, publishing, and permission grants. Those need the gate *before* the action, not a rollback plan after. This is the single most useful Intermediate-level idea the page is missing.
7. **Concrete stopping conditions.** Examples such as "the diff touches files outside the plan", "a test was edited", "the agent asks for broader permissions", "the output cites something you cannot find".
8. **Who reviews.** The person who prompted the change should not be the only approver on high-impact work. An AI reviewing AI output is a helper, not a gate. (Keep separation-of-duties detail for Advanced.)
9. **Gate vs. checkpoint.** Next page is Checkpointed Execution. One short box: checkpoints are stops *during* the work; gates are decisions *before* the change reaches users or systems.
10. **A worked example.** A before/after: a "looks good" approval versus one that names the diff, the tests, the approver and the undo step.
11. **Prompt card and checklist.** A short prompt ("design the review gates and rollback for this change") and a checklist, for parity with its peers. Keep privacy in mind for the audit-trail item: do not store prompts that contain sensitive data.
12. **Add "Do not use when" and a link to the Advanced page** for readers who need risk-tiered gates, decision records and monitoring plans.

Target size: roughly 900 to 1,100 words, i.e. closer to its Intermediate peers but still the lighter of the pair.

### Extra for `governed-ai-delivery` (Advanced)

- Add a one-line pointer to the Intermediate page ("start there if you are new to gates").
- **Risk-level names disagree** with `ai-risk-tiers` (Low / Moderate / High / Blocked here; T1 to T4 there). Pick one vocabulary, or add a mapping line.
- **Separation of duties** for high-impact work: the author of the change (human or agent) cannot be the sole approver.
- **Automated gates**: required checks, protected branches, policy-as-code. Keep it generic.
- **AI reviewer = advisory.** An AI reviewer can add findings; it does not satisfy a human approval gate.
- **Gate health metrics**: override rate, time to approve, and escapes (issues found after release). Gates that nobody ever fails are probably rubber stamps.
- **Rollback vs. roll forward.** Sometimes a forward fix is safer. State the decision rule.
- **Irreversible actions** belong in the Blocked row with a pre-action gate, not a rollback plan. The table already hints at it; say it outright.
- Tone cleanup: "7,500 pounds of chicken", "panic with a keyboard", "tap shoes", "dashboard aquarium".

### 6. The plan/spec/runbook family (F6)

Four pages, four different questions. No overlap that justifies a merge:

| Page | Level | Question |
| --- | --- | --- |
| AGENTS.md vs. PLAN.md | Beginner | Is this a standing rule or a task step? |
| Where Should the Plan Live? | Intermediate | A file, or the tool's plan mode? |
| PLAN vs SPEC vs RUNBOOK | Intermediate | Which document do I write? |
| Implementation Plans and Specs | Intermediate | How do I write a good plan or spec? |

Amendments:

- Add a short "which page answers my question" strip to each page linking to the other three.
- `plan-md-vs-spec-md-vs-runbook-md` and `implementation-plans-and-specs` share the SPEC/PLAN/RUNBOOK checklists. Keep the definitions on the first and the "how to write" checklists on the second.
- Beginner page: "AGENTS.md is always present and always relevant" overstates (F3). Reword to "meant to apply every session" and note that tools differ in what they load. Do not add tool-specific detail at Beginner level.
- Beginner page: treat the hierarchy lightly. Keep the lifespan idea (permanent vs. temporary), which is the point at that level.
- `PLAN.md` file name is a convention, not a standard. Say so once on the Intermediate "where should the plan live" page.

### Order of work for these items

1. Review Gates and Rollback rebuild (largest gap, one page).
2. Token Economy / Token Budgeting split.
3. Evaluation pair: intro lines, loop and taxonomy.
4. Prompting Basics retitle and align.
5. Model Selection / Cost Controls trims.
6. Plan family cross-link strips.

Each is its own checkpoint. Neither French sibling is touched on the `test` branch; drift is tracked here.

## New pages added on the `test` branch

- **`pages/en/intermediate/vibe-coding-vs-agentic-engineering.html` (1.0):** text-only comparison built from the diagram you supplied. It covers definitions, pros and cons of each mode, the same lifecycle done both ways, example agent roles, quality gates, a "which one" matrix, moving from vibe to engineering, and common mistakes. It sits at position 16 in `NAVIGATION.md`, after `vibe-coding-vs-implementation-planning`. It carries a naming note saying the terms are still settling. This is the first page to use the F2 terminology decision. The wider F2 rollout (lexicon, other vibe-coding pages, `CODEX.md` principle line) is still open.
- **French drift:** `NAVIGATION.md` now lists the expected French sibling, but the two neighbouring French pages (`vibe-coding-vs-implementation-planning`, `ai-use-case-intake`) still link to each other. Their "next" and "previous" cards need updating when the French page is translated.
- **Metadata finding:** 10 pages lack the `ai-education-level` and `ai-education-audience` meta tags, and none of the 87 shows the visible "Expertise / Audience / Use when" line that `AGENTS.md` describes. Either backfill them or relax the rule.

## Caveats

- Page counts and percentages come from keyword searches and may miss pages that use different wording.
- The "no mention" findings mean the exact terms were not found, not that the idea is absent. Some pages may cover the concept in other words.
- Before publishing anything based on this report, verify any claim about current vendor features, standards, or law.
