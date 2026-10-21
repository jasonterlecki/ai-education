# REPORT.md

Version: 1.3.1
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
7. **French pages.** Decide whether to retranslate each page as its English version lands or in a batch afterward, per `PLAN_TRANSLATION.md`.
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

## Progress on the `test` branch

Phase 1 (pilot) is done on branch `test` and is waiting for review.

- **Voice guide:** added as sections 8.1 and 8.2 of `PLAN_AI_EDUCATION.md` (now 1.5.0).
- **Visual refresh:** new shared theme `assets/css/field-guide.css`. It gives a calmer background, flatter hero and cards, clearer type, automatic dark mode, and print rules. It is linked from the four pilot pages only. Checked with headless Chrome in light and dark.
- **Pilot pages (one per level):** `memory-vs-context-vs-instructions` (Beginner), `plan-md-vs-agent-plan-mode` (Intermediate), `skills-md-deep-dive` (Advanced), `ai-vendor-and-tool-selection` (Expert).
- **Findings actioned on the pilot pages:** T1 and T2 (voice and hero badges, memory page only), A2 (`SKILL.md` and `openai.yaml` removed; nav labels on `agents-md-deep-dive`, `test-first-ai-workflows`, and `index.html` updated), A3, and G3 (new "Same vendor, different account type" section on the vendor page).
- **Not yet done:** the other 83 pages, the G2 "Laws and Local Rules" page, A1, A4, A5, G1, G4 to G10, French pages (they will drift from the English text), and the `skills-md-deep-dive.html` filename decision.

## Full read results (second pass)

All 87 English pages were read after the first scan: the main body text of each page, with repeated prompt templates and long example blocks skimmed. The Beginner and Intermediate pages were read most closely. Several Advanced and Expert pages were read at section level (the first several substantive paragraphs per section, not every card), so a subtle error in a card I did not reach could remain.

**Result: still no fundamentally wrong pages.** The content is consistent, careful, and well aligned with its stated levels. The findings below are about overstatement, missing caveats, structure, and overlap. None needs an urgent fix.

| # | Priority | Page(s) | Finding | Recommendation |
| --- | --- | --- | --- | --- |
| F1 | High | `intermediate/prompt-injection-for-business-users`, `advanced/prompt-injection-for-agents`, `expert/mcp-security-and-permissions`, `expert/ai-security-architecture` | None of the prompt-injection pages says plainly that there is no known complete defense. The agent page says to layer controls "until the attack gets tired", which implies a stronger guarantee than exists. Readers could think a good filter or a strong instruction solves it. | Add one clear statement on each page: injection cannot currently be fully prevented, so assume some attempts will work and limit what a manipulated agent can reach (least privilege, approvals, no untrusted content plus sensitive data plus outbound action in one session). |
| F2 | High | `beginner/introduction-to-vibe-coding`, `intermediate/vibe-coding-vs-implementation-planning`, `intermediate/checkpointed-execution`, the `vibe-brief` prompt, `CODEX.md`, `PLAN_AI_EDUCATION.md`, `index.html`, and about 36 pages that use the term | **Decision: the site teaches two modes. *Vibe coding* is exploratory, unstructured, intent-first work: describe what you want, with little up-front planning, specification, documentation, or testing, and with the output often accepted without close review. *Agentic engineering* is the disciplined mode for real systems: plans and specs, checkpoints, tests and validation, scoped permissions, and human review of the result.** Today the site defines vibe coding more broadly (any exploratory AI-assisted making) and has no name for the structured mode. The repeated rule "vibe coding for exploration, planning for real systems, checkpointed execution for controlled agent work" should map onto these two terms. | Add a short definitions card to the two vibe-coding pages and use "agentic engineering" for the structured mode where the pages now say "implementation planning plus checkpointed execution". Keep "vibe coding" for exploration, including non-code exploration, but say so. Add both terms to the lexicon. Update the one-line principle in `CODEX.md`. Before publishing, confirm how the term "agentic engineering" is currently used by the wider community; I have not verified the sources. |
| F3 | Medium | `beginner/md-hierarchy-for-ai-agents`, `beginner/agents-md-vs-plan-md`, `beginner/project-file-structure-for-beginners`, `advanced/agent-context-suite`, `advanced/agents-md-deep-dive` | Overstatements: AGENTS.md is "always present and always relevant", and the file hierarchy is described as if tools enforce an authority order. In practice, support for instruction files, file names, and precedence varies by tool, and an agent may still ignore a rule. | Describe the hierarchy as a recommended convention, say tool support varies, and note that instruction files guide behavior but do not guarantee compliance. Keep the guidance that important rules also need technical controls. |
| F4 | Medium | all 10 pages under `prompts/` | They do not follow the Prompt Library Rules in `AGENTS.md`. None has a "Do not use when" section or labeled "Example input" and "Expected output" sections (the "Weak prompt / Stronger prompt" pairs are close but not the same). Only the checkpointed-execution prompt carries the five implementation lines (inspect before editing, one phase only, no unrelated changes, validate, stop and report). The implementation-plan prompt and the vibe-brief prompt do not. Several sensitive-topic prompts lack an explicit human-review caution. | Either add the missing sections, or relax the rule in `AGENTS.md` to match the pages as built. The first is more consistent with the stated goal. |
| F5 | Medium | `prompts/prompting-basics` and `beginner/prompting-basics` | Two pages with the same title and overlapping topic. They also differ: the Beginner page teaches five ingredients, the prompt page a seven-part scaffold that adds role and safety note. A reader will not know which is the reference. | Retitle the prompt page (for example, "Reusable Prompt Template") and cross-link, or align both to one scaffold. |
| F6 | Medium | several | Overlapping pages that could be merged or clearly differentiated: `token-economy` and `token-budgeting-for-real-work`; `model-selection-and-cost-management` and `cost-controls-for-teams`; `evaluation-and-red-teaming` and `evaluation-harnesses`; `review-gates-and-rollback` (Intermediate, thin) and `governed-ai-delivery` (Advanced); `agents-md-vs-plan-md` and the PLAN/SPEC/RUNBOOK page. | Decide per pair: merge, or add a one-line "how this differs from X" and cross-link. `review-gates-and-rollback` needs content to match its peers or a merge. |
| F7 | Low | `beginner/multimodal-ai-basics` | "Audio often works through transcription first" is true for some tools and not others. | Say "some tools transcribe audio first, which can mangle names and terms". |
| F8 | Low | `beginner/ai-lexicon-for-beginners` | Missing terms that now appear across the site or in current tools: reasoning model, open-weight model, guardrails, sycophancy, synthetic data, structured output, skill, sub-agent, context engineering. | Add the ones the site uses elsewhere. Keep entries short. |
| F9 | Low | `beginner/privacy-and-safe-use` | The "before" example uses an SSN-shaped number and a card ending, which look like real data. The page also does not mention chat history, shared links, or deleted chats possibly remaining in logs. | Use obviously fake values (for example, "000-00-0000") and add a short note on history and sharing. |
| F10 | Low | `beginner/prompting-basics` | Missing three common habits: tell the model it may say "I don't know", iterate in the same conversation, and keep step-by-step instructions optional for newer reasoning-style models. | Add one short card or three bullets. |
| F11 | Low | `advanced/ai-coding-agents`, `advanced/agent-permissions-ladder` | Good coverage of permissions and stop points. Missing modern modes noted in G7: sub-agents, parallel agents in isolated branches, and browser or computer-use agents. | See G7. |

Items from this pass that need no action: the hallucination page, source-quality page, MCP basics, retrieval and chunking pages, observability, risk tiers, and the Expert governance pages read as accurate and coherent.

## Caveats

- Page counts and percentages come from keyword searches and may miss pages that use different wording.
- The "no mention" findings mean the exact terms were not found, not that the idea is absent. Some pages may cover the concept in other words.
- Before publishing anything based on this report, verify any claim about current vendor features, standards, or law.
