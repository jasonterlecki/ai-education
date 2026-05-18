# PLAN_TRANSLATION.md: Canadian French Translation Plan

Version: 1.0.10
Status: Active
Repository type: AI education knowledge base
Translation scope: English `en` AI Education pages to Canadian French `fr-CA`

## Purpose

This file defines the controlled process for translating the English AI Education index and education pages into Canadian French.

The translation work must preserve the existing education structure, visual language, file hierarchy, navigation intent, and page ordering. Translation happens one page at a time only when explicitly instructed by the user.

## Translation Rules

- Translate from English to Canadian French using `fr-CA` phrasing and spelling.
- Place translated education pages under `pages/fr/` using the same folder structure as `pages/en/`.
- Preserve the `pages/en/` folder hierarchy exactly under `pages/fr/`.
- Do not rename folders.
- Keep filenames in English to preserve navigation consistency.
- The only filename exception is `index.html` to `index_fr.html`.
- Do not modify files under `pages/en/`.
- Do not invent missing pages or additional content.
- Preserve the original structure, layout, sections, and ordering of each page.
- Do not add new sections.
- Do not remove sections.
- Do not summarize or rewrite content beyond what is necessary for natural Canadian French translation.
- Maintain the original tone, educational style, formatting density, and intent.
- Preserve CSS, JavaScript, SVG, classes, IDs, anchors, aria labels, and structural HTML unless translation is linguistically required.
- Preserve relative paths and asset references unless changes are required for French navigation.
- French-facing index links and previous/home/next guide navigation must point to the expected `pages/fr/` location for each page, even when that translated file does not exist yet.
- Temporary 404s from not-yet-translated French page links are acceptable during the translation project.
- Add `<html lang="fr-CA">` to every translated page.
- Retain UTF-8 accents and characters correctly.
- Keep English-to-French and French-to-English language-switch links visually subtle and consistent.

## Do Not Translate

- Filenames.
- CSS class names.
- HTML IDs.
- Technical filenames such as `README.md`, `AGENTS.md`, `PLAN.md`, `SPEC.md`, and `RUNBOOK.md`.

## Code, Preformatted Text, and Prompt Examples

- Preserve actual computer code exactly, including syntax, commands, configuration keys, variables, JSON, CSS, JavaScript, shell examples, and markup that is being taught as markup.
- Preserve English text inside `<pre>`, `<code>`, or code-style blocks only when it is actual computer code or when translation would make the example nonsensical.
- Translate prompt examples, sample AI instructions, review checklists, plain-language templates, and general English prose even when they appear inside `<pre>`, `<code>`, or visually code-styled blocks.
- Preserve placeholders, filenames, command names, API names, product names, and structural tokens inside translated prompt examples.

## Index Translation Process

The first translation phase is the root index pair:

1. Translate `index.html` into `index_fr.html`.
2. Add a small discreet link in the hero card of `index.html` pointing to `index_fr.html`.
3. Add a small discreet link in the hero card of `index_fr.html` pointing to `index.html` in the same visual location.
4. Keep both language-switch links same-tab, visually subtle, and consistent.

## Page Translation Process

After the index pair is complete, translate education pages from the checklist below.

Rules for page execution:

- Build the page list from `NAVIGATION.md`.
- Translate one page at a time only when instructed by the user.
- Do not translate all pages automatically.
- Wait for the user to request either the next page or a specific named page.
- When translating a page, update the matching checklist item from `[ ]` to `[X]`.
- When translating a page, update `NAVIGATION.md`, `index.html` or `index_fr.html` if needed, and `CODEX.md` in the same change set.
- Preserve previous/home/next navigation intent using the expected French page path.
- If a neighbouring French page does not exist yet, link to the expected future French location and leave the temporary 404 in place until that page is translated.

## Translation Checklist

- [X] `index.html` -> `index_fr.html`
- [X] `pages/en/beginner/ai-literacy-basics.html` -> `pages/fr/beginner/ai-literacy-basics.html`
- [X] `pages/en/beginner/ai-lexicon-for-beginners.html` -> `pages/fr/beginner/ai-lexicon-for-beginners.html`
- [X] `pages/en/beginner/ai-for-non-technical-people.html` -> `pages/fr/beginner/ai-for-non-technical-people.html`
- [X] `pages/en/beginner/prompting-basics.html` -> `pages/fr/beginner/prompting-basics.html`
- [X] `pages/en/beginner/privacy-and-safe-use.html` -> `pages/fr/beginner/privacy-and-safe-use.html`
- [X] `pages/en/beginner/hallucinations-and-verification.html` -> `pages/fr/beginner/hallucinations-and-verification.html`
- [X] `pages/en/beginner/source-quality-and-citation-hygiene.html` -> `pages/fr/beginner/source-quality-and-citation-hygiene.html`
- [ ] `pages/en/beginner/human-accountability.html` -> `pages/fr/beginner/human-accountability.html`
- [ ] `pages/en/beginner/multimodal-ai-basics.html` -> `pages/fr/beginner/multimodal-ai-basics.html`
- [ ] `pages/en/beginner/memory-vs-context-vs-instructions.html` -> `pages/fr/beginner/memory-vs-context-vs-instructions.html`
- [ ] `pages/en/beginner/introduction-to-vibe-coding.html` -> `pages/fr/beginner/introduction-to-vibe-coding.html`
- [ ] `pages/en/beginner/md-hierarchy-for-ai-agents.html` -> `pages/fr/beginner/md-hierarchy-for-ai-agents.html`
- [ ] `pages/en/beginner/project-file-structure-for-beginners.html` -> `pages/fr/beginner/project-file-structure-for-beginners.html`
- [ ] `pages/en/intermediate/vibe-coding-vs-implementation-planning.html` -> `pages/fr/intermediate/vibe-coding-vs-implementation-planning.html`
- [ ] `pages/en/intermediate/ai-use-case-intake.html` -> `pages/fr/intermediate/ai-use-case-intake.html`
- [ ] `pages/en/intermediate/ai-data-boundaries.html` -> `pages/fr/intermediate/ai-data-boundaries.html`
- [ ] `pages/en/intermediate/ai-for-sensitive-decisions.html` -> `pages/fr/intermediate/ai-for-sensitive-decisions.html`
- [ ] `pages/en/intermediate/prompt-injection-for-business-users.html` -> `pages/fr/intermediate/prompt-injection-for-business-users.html`
- [ ] `pages/en/intermediate/blast-radius-thinking.html` -> `pages/fr/intermediate/blast-radius-thinking.html`
- [ ] `pages/en/intermediate/human-in-the-loop-design.html` -> `pages/fr/intermediate/human-in-the-loop-design.html`
- [ ] `pages/en/intermediate/token-economy.html` -> `pages/fr/intermediate/token-economy.html`
- [ ] `pages/en/intermediate/token-budgeting-for-real-work.html` -> `pages/fr/intermediate/token-budgeting-for-real-work.html`
- [ ] `pages/en/intermediate/context-compression.html` -> `pages/fr/intermediate/context-compression.html`
- [ ] `pages/en/intermediate/context-and-prompt-drift.html` -> `pages/fr/intermediate/context-and-prompt-drift.html`
- [ ] `pages/en/intermediate/ai-output-acceptance-criteria.html` -> `pages/fr/intermediate/ai-output-acceptance-criteria.html`
- [ ] `pages/en/intermediate/implementation-plans-and-specs.html` -> `pages/fr/intermediate/implementation-plans-and-specs.html`
- [ ] `pages/en/intermediate/plan-md-vs-spec-md-vs-runbook-md.html` -> `pages/fr/intermediate/plan-md-vs-spec-md-vs-runbook-md.html`
- [ ] `pages/en/intermediate/review-gates-and-rollback.html` -> `pages/fr/intermediate/review-gates-and-rollback.html`
- [ ] `pages/en/intermediate/checkpointed-execution.html` -> `pages/fr/intermediate/checkpointed-execution.html`
- [ ] `pages/en/intermediate/agent-handoff-notes.html` -> `pages/fr/intermediate/agent-handoff-notes.html`
- [ ] `pages/en/intermediate/ai-assisted-debugging.html` -> `pages/fr/intermediate/ai-assisted-debugging.html`
- [ ] `pages/en/intermediate/ai-and-documentation-systems.html` -> `pages/fr/intermediate/ai-and-documentation-systems.html`
- [ ] `pages/en/intermediate/ai-content-lifecycle.html` -> `pages/fr/intermediate/ai-content-lifecycle.html`
- [ ] `pages/en/intermediate/ai-for-slide-and-visual-planning.html` -> `pages/fr/intermediate/ai-for-slide-and-visual-planning.html`
- [ ] `pages/en/advanced/ai-for-technical-teams.html` -> `pages/fr/advanced/ai-for-technical-teams.html`
- [ ] `pages/en/advanced/ai-coding-agents.html` -> `pages/fr/advanced/ai-coding-agents.html`
- [ ] `pages/en/advanced/repository-instructions-and-agents.html` -> `pages/fr/advanced/repository-instructions-and-agents.html`
- [ ] `pages/en/advanced/agent-context-suite.html` -> `pages/fr/advanced/agent-context-suite.html`
- [ ] `pages/en/advanced/agents-md-deep-dive.html` -> `pages/fr/advanced/agents-md-deep-dive.html`
- [ ] `pages/en/advanced/skills-md-deep-dive.html` -> `pages/fr/advanced/skills-md-deep-dive.html`
- [ ] `pages/en/advanced/test-first-ai-workflows.html` -> `pages/fr/advanced/test-first-ai-workflows.html`
- [ ] `pages/en/advanced/code-review-with-ai.html` -> `pages/fr/advanced/code-review-with-ai.html`
- [ ] `pages/en/advanced/ai-generated-code-smells.html` -> `pages/fr/advanced/ai-generated-code-smells.html`
- [ ] `pages/en/advanced/tool-calling-and-function-boundaries.html` -> `pages/fr/advanced/tool-calling-and-function-boundaries.html`
- [ ] `pages/en/advanced/mcp-basics.html` -> `pages/fr/advanced/mcp-basics.html`
- [ ] `pages/en/advanced/connectors-and-data-access.html` -> `pages/fr/advanced/connectors-and-data-access.html`
- [ ] `pages/en/advanced/prompt-injection-for-agents.html` -> `pages/fr/advanced/prompt-injection-for-agents.html`
- [ ] `pages/en/advanced/agent-permissions-ladder.html` -> `pages/fr/advanced/agent-permissions-ladder.html`
- [ ] `pages/en/advanced/controlled-automation.html` -> `pages/fr/advanced/controlled-automation.html`
- [ ] `pages/en/advanced/agent-observability.html` -> `pages/fr/advanced/agent-observability.html`
- [ ] `pages/en/advanced/security-privacy-and-governance.html` -> `pages/fr/advanced/security-privacy-and-governance.html`
- [ ] `pages/en/advanced/ai-governance-without-theater.html` -> `pages/fr/advanced/ai-governance-without-theater.html`
- [ ] `pages/en/advanced/ai-risk-tiers.html` -> `pages/fr/advanced/ai-risk-tiers.html`
- [ ] `pages/en/advanced/infrastructure-and-iac-risk.html` -> `pages/fr/advanced/infrastructure-and-iac-risk.html`
- [ ] `pages/en/advanced/review-gates-and-rollback.html` -> `pages/fr/advanced/review-gates-and-rollback.html`
- [ ] `pages/en/advanced/ai-for-incident-response-support.html` -> `pages/fr/advanced/ai-for-incident-response-support.html`
- [ ] `pages/en/advanced/ai-pilot-to-production.html` -> `pages/fr/advanced/ai-pilot-to-production.html`
- [ ] `pages/en/advanced/shadow-ai-and-unsanctioned-use.html` -> `pages/fr/advanced/shadow-ai-and-unsanctioned-use.html`
- [ ] `pages/en/advanced/source-of-truth-design.html` -> `pages/fr/advanced/source-of-truth-design.html`
- [ ] `pages/en/advanced/retrieval-failure-modes.html` -> `pages/fr/advanced/retrieval-failure-modes.html`
- [ ] `pages/en/advanced/embeddings-and-vector-search.html` -> `pages/fr/advanced/embeddings-and-vector-search.html`
- [ ] `pages/en/advanced/chunking-strategy.html` -> `pages/fr/advanced/chunking-strategy.html`
- [ ] `pages/en/expert/ai-operating-model.html` -> `pages/fr/expert/ai-operating-model.html`
- [ ] `pages/en/expert/strategic-ai-portfolio.html` -> `pages/fr/expert/strategic-ai-portfolio.html`
- [ ] `pages/en/expert/ai-architecture-strategy.html` -> `pages/fr/expert/ai-architecture-strategy.html`
- [ ] `pages/en/expert/ai-vendor-and-tool-selection.html` -> `pages/fr/expert/ai-vendor-and-tool-selection.html`
- [ ] `pages/en/expert/local-models-vs-hosted-models.html` -> `pages/fr/expert/local-models-vs-hosted-models.html`
- [ ] `pages/en/expert/model-selection-and-cost-management.html` -> `pages/fr/expert/model-selection-and-cost-management.html`
- [ ] `pages/en/expert/cost-controls-for-teams.html` -> `pages/fr/expert/cost-controls-for-teams.html`
- [ ] `pages/en/expert/ai-security-architecture.html` -> `pages/fr/expert/ai-security-architecture.html`
- [ ] `pages/en/expert/mcp-security-and-permissions.html` -> `pages/fr/expert/mcp-security-and-permissions.html`
- [ ] `pages/en/expert/retrieval-and-knowledge-governance.html` -> `pages/fr/expert/retrieval-and-knowledge-governance.html`
- [ ] `pages/en/expert/evaluation-harnesses.html` -> `pages/fr/expert/evaluation-harnesses.html`
- [ ] `pages/en/expert/evaluation-and-red-teaming.html` -> `pages/fr/expert/evaluation-and-red-teaming.html`
- [ ] `pages/en/expert/change-management-and-adoption.html` -> `pages/fr/expert/change-management-and-adoption.html`
- [ ] `pages/en/prompts/prompting-basics.html` -> `pages/fr/prompts/prompting-basics.html`
- [ ] `pages/en/prompts/email-and-communication-prompt.html` -> `pages/fr/prompts/email-and-communication-prompt.html`
- [ ] `pages/en/prompts/meeting-summary-prompt.html` -> `pages/fr/prompts/meeting-summary-prompt.html`
- [ ] `pages/en/prompts/executive-summary-prompt.html` -> `pages/fr/prompts/executive-summary-prompt.html`
- [ ] `pages/en/prompts/document-review-prompt.html` -> `pages/fr/prompts/document-review-prompt.html`
- [ ] `pages/en/prompts/vibe-brief-prompt.html` -> `pages/fr/prompts/vibe-brief-prompt.html`
- [ ] `pages/en/prompts/implementation-plan-prompt.html` -> `pages/fr/prompts/implementation-plan-prompt.html`
- [ ] `pages/en/prompts/risk-review-prompt.html` -> `pages/fr/prompts/risk-review-prompt.html`
- [ ] `pages/en/prompts/checkpointed-execution-prompt.html` -> `pages/fr/prompts/checkpointed-execution-prompt.html`
- [ ] `pages/en/prompts/code-review-prompt.html` -> `pages/fr/prompts/code-review-prompt.html`

## Validation Expectations

For each translation change set:

- Run `git diff --check`.
- Confirm translated HTML keeps `lang="fr-CA"`.
- Confirm changed HTML includes required version metadata and HTML version comments.
- Confirm internal education navigation links do not use `_blank`.
- Confirm translated page paths preserve the English folder hierarchy under `pages/fr/`.
- Confirm language-switch links are same-tab and visually subtle.
- Confirm `CODEX.md` matches the translated file status and version.
