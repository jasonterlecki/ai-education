# NAVIGATION.md

Version: 1.3.2
Status: Active
Repository type: AI education knowledge base

## Purpose

This file defines the canonical previous and next navigation order for every active English HTML education page under `pages/en/`. AI agents should use this file when adding, renaming, retiring, translating, or editing education pages so page-level navigation remains consistent with the learning path.

## Agent Rules

- Treat the table below as the source of truth for English page-to-page navigation.
- Keep English pages under `pages/en/`. Future translated pages should use sibling language directories such as `pages/fr/` and `pages/es/`.
- Locale-specific navigation should point to the expected sibling path in that locale, even before the translated file exists. Temporary 404s are acceptable during translation.
- When a page is added, removed, renamed, moved, or translated under `pages/`, update this file, the affected HTML navigation cards, `index.html` when applicable, and `CODEX.md` in the same change set.
- Each HTML page under `pages/en/` should include navigation immediately after the hero section and again after the takeaway card.
- Navigation cards should include Previous, Home, and Next destinations.
- Use `index.html` as Home. Do not use `_blank` targets for internal education navigation.

## Navigation Order

| Order | Language | Level | Page | Previous | Next |
| --- | --- | --- | --- | --- | --- |
| 1 | en | Beginner | `pages/en/beginner/ai-literacy-basics.html` | Start | `pages/en/beginner/ai-lexicon-for-beginners.html` |
| 1 | fr-CA | Beginner | `pages/fr/beginner/ai-literacy-basics.html` | Start | `pages/fr/beginner/ai-lexicon-for-beginners.html` |
| 2 | en | Beginner | `pages/en/beginner/ai-lexicon-for-beginners.html` | `pages/en/beginner/ai-literacy-basics.html` | `pages/en/beginner/ai-for-non-technical-people.html` |
| 2 | fr-CA | Beginner | `pages/fr/beginner/ai-lexicon-for-beginners.html` | `pages/fr/beginner/ai-literacy-basics.html` | `pages/fr/beginner/ai-for-non-technical-people.html` |
| 3 | en | Beginner | `pages/en/beginner/ai-for-non-technical-people.html` | `pages/en/beginner/ai-lexicon-for-beginners.html` | `pages/en/beginner/prompting-basics.html` |
| 3 | fr-CA | Beginner | `pages/fr/beginner/ai-for-non-technical-people.html` | `pages/fr/beginner/ai-lexicon-for-beginners.html` | `pages/fr/beginner/prompting-basics.html` |
| 4 | en | Beginner | `pages/en/beginner/prompting-basics.html` | `pages/en/beginner/ai-for-non-technical-people.html` | `pages/en/beginner/privacy-and-safe-use.html` |
| 4 | fr-CA | Beginner | `pages/fr/beginner/prompting-basics.html` | `pages/fr/beginner/ai-for-non-technical-people.html` | `pages/fr/beginner/privacy-and-safe-use.html` |
| 5 | en | Beginner | `pages/en/beginner/privacy-and-safe-use.html` | `pages/en/beginner/prompting-basics.html` | `pages/en/beginner/hallucinations-and-verification.html` |
| 5 | fr-CA | Beginner | `pages/fr/beginner/privacy-and-safe-use.html` | `pages/fr/beginner/prompting-basics.html` | `pages/fr/beginner/hallucinations-and-verification.html` |
| 6 | en | Beginner | `pages/en/beginner/hallucinations-and-verification.html` | `pages/en/beginner/privacy-and-safe-use.html` | `pages/en/beginner/source-quality-and-citation-hygiene.html` |
| 6 | fr-CA | Beginner | `pages/fr/beginner/hallucinations-and-verification.html` | `pages/fr/beginner/privacy-and-safe-use.html` | `pages/fr/beginner/source-quality-and-citation-hygiene.html` |
| 7 | en | Beginner | `pages/en/beginner/source-quality-and-citation-hygiene.html` | `pages/en/beginner/hallucinations-and-verification.html` | `pages/en/beginner/human-accountability.html` |
| 7 | fr-CA | Beginner | `pages/fr/beginner/source-quality-and-citation-hygiene.html` | `pages/fr/beginner/hallucinations-and-verification.html` | `pages/fr/beginner/human-accountability.html` |
| 8 | en | Beginner | `pages/en/beginner/human-accountability.html` | `pages/en/beginner/source-quality-and-citation-hygiene.html` | `pages/en/beginner/multimodal-ai-basics.html` |
| 8 | fr-CA | Beginner | `pages/fr/beginner/human-accountability.html` | `pages/fr/beginner/source-quality-and-citation-hygiene.html` | `pages/fr/beginner/multimodal-ai-basics.html` |
| 9 | en | Beginner | `pages/en/beginner/multimodal-ai-basics.html` | `pages/en/beginner/human-accountability.html` | `pages/en/beginner/memory-vs-context-vs-instructions.html` |
| 9 | fr-CA | Beginner | `pages/fr/beginner/multimodal-ai-basics.html` | `pages/fr/beginner/human-accountability.html` | `pages/fr/beginner/memory-vs-context-vs-instructions.html` |
| 10 | en | Beginner | `pages/en/beginner/memory-vs-context-vs-instructions.html` | `pages/en/beginner/multimodal-ai-basics.html` | `pages/en/beginner/introduction-to-vibe-coding.html` |
| 10 | fr-CA | Beginner | `pages/fr/beginner/memory-vs-context-vs-instructions.html` | `pages/fr/beginner/multimodal-ai-basics.html` | `pages/fr/beginner/introduction-to-vibe-coding.html` |
| 11 | en | Beginner | `pages/en/beginner/introduction-to-vibe-coding.html` | `pages/en/beginner/memory-vs-context-vs-instructions.html` | `pages/en/beginner/md-hierarchy-for-ai-agents.html` |
| 11 | fr-CA | Beginner | `pages/fr/beginner/introduction-to-vibe-coding.html` | `pages/fr/beginner/memory-vs-context-vs-instructions.html` | `pages/fr/beginner/md-hierarchy-for-ai-agents.html` |
| 12 | en | Beginner | `pages/en/beginner/md-hierarchy-for-ai-agents.html` | `pages/en/beginner/introduction-to-vibe-coding.html` | `pages/en/beginner/agents-md-vs-plan-md.html` |
| 12 | fr-CA | Beginner | `pages/fr/beginner/md-hierarchy-for-ai-agents.html` | `pages/fr/beginner/introduction-to-vibe-coding.html` | `pages/fr/beginner/agents-md-vs-plan-md.html` |
| 13 | en | Beginner | `pages/en/beginner/agents-md-vs-plan-md.html` | `pages/en/beginner/md-hierarchy-for-ai-agents.html` | `pages/en/beginner/project-file-structure-for-beginners.html` |
| 13 | fr-CA | Beginner | `pages/fr/beginner/agents-md-vs-plan-md.html` | `pages/fr/beginner/md-hierarchy-for-ai-agents.html` | `pages/fr/beginner/project-file-structure-for-beginners.html` |
| 14 | en | Beginner | `pages/en/beginner/project-file-structure-for-beginners.html` | `pages/en/beginner/agents-md-vs-plan-md.html` | `pages/en/intermediate/vibe-coding-vs-implementation-planning.html` |
| 14 | fr-CA | Beginner | `pages/fr/beginner/project-file-structure-for-beginners.html` | `pages/fr/beginner/agents-md-vs-plan-md.html` | `pages/fr/intermediate/vibe-coding-vs-implementation-planning.html` |
| 15 | en | Intermediate | `pages/en/intermediate/vibe-coding-vs-implementation-planning.html` | `pages/en/beginner/project-file-structure-for-beginners.html` | `pages/en/intermediate/ai-use-case-intake.html` |
| 15 | fr-CA | Intermediate | `pages/fr/intermediate/vibe-coding-vs-implementation-planning.html` | `pages/fr/beginner/project-file-structure-for-beginners.html` | `pages/fr/intermediate/ai-use-case-intake.html` |
| 16 | en | Intermediate | `pages/en/intermediate/ai-use-case-intake.html` | `pages/en/intermediate/vibe-coding-vs-implementation-planning.html` | `pages/en/intermediate/ai-data-boundaries.html` |
| 16 | fr-CA | Intermediate | `pages/fr/intermediate/ai-use-case-intake.html` | `pages/fr/intermediate/vibe-coding-vs-implementation-planning.html` | `pages/fr/intermediate/ai-data-boundaries.html` |
| 17 | en | Intermediate | `pages/en/intermediate/ai-data-boundaries.html` | `pages/en/intermediate/ai-use-case-intake.html` | `pages/en/intermediate/ai-for-sensitive-decisions.html` |
| 17 | fr-CA | Intermediate | `pages/fr/intermediate/ai-data-boundaries.html` | `pages/fr/intermediate/ai-use-case-intake.html` | `pages/fr/intermediate/ai-for-sensitive-decisions.html` |
| 18 | en | Intermediate | `pages/en/intermediate/ai-for-sensitive-decisions.html` | `pages/en/intermediate/ai-data-boundaries.html` | `pages/en/intermediate/prompt-injection-for-business-users.html` |
| 18 | fr-CA | Intermediate | `pages/fr/intermediate/ai-for-sensitive-decisions.html` | `pages/fr/intermediate/ai-data-boundaries.html` | `pages/fr/intermediate/prompt-injection-for-business-users.html` |
| 19 | en | Intermediate | `pages/en/intermediate/prompt-injection-for-business-users.html` | `pages/en/intermediate/ai-for-sensitive-decisions.html` | `pages/en/intermediate/blast-radius-thinking.html` |
| 19 | fr-CA | Intermediate | `pages/fr/intermediate/prompt-injection-for-business-users.html` | `pages/fr/intermediate/ai-for-sensitive-decisions.html` | `pages/fr/intermediate/blast-radius-thinking.html` |
| 20 | en | Intermediate | `pages/en/intermediate/blast-radius-thinking.html` | `pages/en/intermediate/prompt-injection-for-business-users.html` | `pages/en/intermediate/human-in-the-loop-design.html` |
| 20 | fr-CA | Intermediate | `pages/fr/intermediate/blast-radius-thinking.html` | `pages/fr/intermediate/prompt-injection-for-business-users.html` | `pages/fr/intermediate/human-in-the-loop-design.html` |
| 21 | en | Intermediate | `pages/en/intermediate/human-in-the-loop-design.html` | `pages/en/intermediate/blast-radius-thinking.html` | `pages/en/intermediate/token-economy.html` |
| 21 | fr-CA | Intermediate | `pages/fr/intermediate/human-in-the-loop-design.html` | `pages/fr/intermediate/blast-radius-thinking.html` | `pages/fr/intermediate/token-economy.html` |
| 22 | en | Intermediate | `pages/en/intermediate/token-economy.html` | `pages/en/intermediate/human-in-the-loop-design.html` | `pages/en/intermediate/token-budgeting-for-real-work.html` |
| 22 | fr-CA | Intermediate | `pages/fr/intermediate/token-economy.html` | `pages/fr/intermediate/human-in-the-loop-design.html` | `pages/fr/intermediate/token-budgeting-for-real-work.html` |
| 23 | en | Intermediate | `pages/en/intermediate/token-budgeting-for-real-work.html` | `pages/en/intermediate/token-economy.html` | `pages/en/intermediate/context-compression.html` |
| 23 | fr-CA | Intermediate | `pages/fr/intermediate/token-budgeting-for-real-work.html` | `pages/fr/intermediate/token-economy.html` | `pages/fr/intermediate/context-compression.html` |
| 24 | en | Intermediate | `pages/en/intermediate/context-compression.html` | `pages/en/intermediate/token-budgeting-for-real-work.html` | `pages/en/intermediate/context-and-prompt-drift.html` |
| 24 | fr-CA | Intermediate | `pages/fr/intermediate/context-compression.html` | `pages/fr/intermediate/token-budgeting-for-real-work.html` | `pages/fr/intermediate/context-and-prompt-drift.html` |
| 25 | en | Intermediate | `pages/en/intermediate/context-and-prompt-drift.html` | `pages/en/intermediate/context-compression.html` | `pages/en/intermediate/ai-output-acceptance-criteria.html` |
| 25 | fr-CA | Intermediate | `pages/fr/intermediate/context-and-prompt-drift.html` | `pages/fr/intermediate/context-compression.html` | `pages/fr/intermediate/ai-output-acceptance-criteria.html` |
| 26 | en | Intermediate | `pages/en/intermediate/ai-output-acceptance-criteria.html` | `pages/en/intermediate/context-and-prompt-drift.html` | `pages/en/intermediate/implementation-plans-and-specs.html` |
| 26 | fr-CA | Intermediate | `pages/fr/intermediate/ai-output-acceptance-criteria.html` | `pages/fr/intermediate/context-and-prompt-drift.html` | `pages/fr/intermediate/implementation-plans-and-specs.html` |
| 27 | en | Intermediate | `pages/en/intermediate/implementation-plans-and-specs.html` | `pages/en/intermediate/ai-output-acceptance-criteria.html` | `pages/en/intermediate/plan-md-vs-agent-plan-mode.html` |
| 27 | fr-CA | Intermediate | `pages/fr/intermediate/implementation-plans-and-specs.html` | `pages/fr/intermediate/ai-output-acceptance-criteria.html` | `pages/fr/intermediate/plan-md-vs-agent-plan-mode.html` |
| 28 | en | Intermediate | `pages/en/intermediate/plan-md-vs-agent-plan-mode.html` | `pages/en/intermediate/implementation-plans-and-specs.html` | `pages/en/intermediate/plan-md-vs-spec-md-vs-runbook-md.html` |
| 28 | fr-CA | Intermediate | `pages/fr/intermediate/plan-md-vs-agent-plan-mode.html` | `pages/fr/intermediate/implementation-plans-and-specs.html` | `pages/fr/intermediate/plan-md-vs-spec-md-vs-runbook-md.html` |
| 29 | en | Intermediate | `pages/en/intermediate/plan-md-vs-spec-md-vs-runbook-md.html` | `pages/en/intermediate/plan-md-vs-agent-plan-mode.html` | `pages/en/intermediate/review-gates-and-rollback.html` |
| 29 | fr-CA | Intermediate | `pages/fr/intermediate/plan-md-vs-spec-md-vs-runbook-md.html` | `pages/fr/intermediate/plan-md-vs-agent-plan-mode.html` | `pages/fr/intermediate/review-gates-and-rollback.html` |
| 30 | en | Intermediate | `pages/en/intermediate/review-gates-and-rollback.html` | `pages/en/intermediate/plan-md-vs-spec-md-vs-runbook-md.html` | `pages/en/intermediate/checkpointed-execution.html` |
| 30 | fr-CA | Intermediate | `pages/fr/intermediate/review-gates-and-rollback.html` | `pages/fr/intermediate/plan-md-vs-spec-md-vs-runbook-md.html` | `pages/fr/intermediate/checkpointed-execution.html` |
| 31 | en | Intermediate | `pages/en/intermediate/checkpointed-execution.html` | `pages/en/intermediate/review-gates-and-rollback.html` | `pages/en/intermediate/agent-handoff-notes.html` |
| 31 | fr-CA | Intermediate | `pages/fr/intermediate/checkpointed-execution.html` | `pages/fr/intermediate/review-gates-and-rollback.html` | `pages/fr/intermediate/agent-handoff-notes.html` |
| 32 | en | Intermediate | `pages/en/intermediate/agent-handoff-notes.html` | `pages/en/intermediate/checkpointed-execution.html` | `pages/en/intermediate/ai-assisted-debugging.html` |
| 32 | fr-CA | Intermediate | `pages/fr/intermediate/agent-handoff-notes.html` | `pages/fr/intermediate/checkpointed-execution.html` | `pages/fr/intermediate/ai-assisted-debugging.html` |
| 33 | en | Intermediate | `pages/en/intermediate/ai-assisted-debugging.html` | `pages/en/intermediate/agent-handoff-notes.html` | `pages/en/intermediate/ai-and-documentation-systems.html` |
| 33 | fr-CA | Intermediate | `pages/fr/intermediate/ai-assisted-debugging.html` | `pages/fr/intermediate/agent-handoff-notes.html` | `pages/fr/intermediate/ai-and-documentation-systems.html` |
| 34 | en | Intermediate | `pages/en/intermediate/ai-and-documentation-systems.html` | `pages/en/intermediate/ai-assisted-debugging.html` | `pages/en/intermediate/ai-content-lifecycle.html` |
| 34 | fr-CA | Intermediate | `pages/fr/intermediate/ai-and-documentation-systems.html` | `pages/fr/intermediate/ai-assisted-debugging.html` | `pages/fr/intermediate/ai-content-lifecycle.html` |
| 35 | en | Intermediate | `pages/en/intermediate/ai-content-lifecycle.html` | `pages/en/intermediate/ai-and-documentation-systems.html` | `pages/en/intermediate/ai-for-slide-and-visual-planning.html` |
| 35 | fr-CA | Intermediate | `pages/fr/intermediate/ai-content-lifecycle.html` | `pages/fr/intermediate/ai-and-documentation-systems.html` | `pages/fr/intermediate/ai-for-slide-and-visual-planning.html` |
| 36 | en | Intermediate | `pages/en/intermediate/ai-for-slide-and-visual-planning.html` | `pages/en/intermediate/ai-content-lifecycle.html` | `pages/en/advanced/ai-for-technical-teams.html` |
| 36 | fr-CA | Intermediate | `pages/fr/intermediate/ai-for-slide-and-visual-planning.html` | `pages/fr/intermediate/ai-content-lifecycle.html` | `pages/fr/advanced/ai-for-technical-teams.html` |
| 37 | en | Advanced | `pages/en/advanced/ai-for-technical-teams.html` | `pages/en/intermediate/ai-for-slide-and-visual-planning.html` | `pages/en/advanced/ai-coding-agents.html` |
| 37 | fr-CA | Advanced | `pages/fr/advanced/ai-for-technical-teams.html` | `pages/fr/intermediate/ai-for-slide-and-visual-planning.html` | `pages/fr/advanced/ai-coding-agents.html` |
| 38 | en | Advanced | `pages/en/advanced/ai-coding-agents.html` | `pages/en/advanced/ai-for-technical-teams.html` | `pages/en/advanced/repository-instructions-and-agents.html` |
| 38 | fr-CA | Advanced | `pages/fr/advanced/ai-coding-agents.html` | `pages/fr/advanced/ai-for-technical-teams.html` | `pages/fr/advanced/repository-instructions-and-agents.html` |
| 39 | en | Advanced | `pages/en/advanced/repository-instructions-and-agents.html` | `pages/en/advanced/ai-coding-agents.html` | `pages/en/advanced/agent-context-suite.html` |
| 39 | fr-CA | Advanced | `pages/fr/advanced/repository-instructions-and-agents.html` | `pages/fr/advanced/ai-coding-agents.html` | `pages/fr/advanced/agent-context-suite.html` |
| 40 | en | Advanced | `pages/en/advanced/agent-context-suite.html` | `pages/en/advanced/repository-instructions-and-agents.html` | `pages/en/advanced/agents-md-deep-dive.html` |
| 40 | fr-CA | Advanced | `pages/fr/advanced/agent-context-suite.html` | `pages/fr/advanced/repository-instructions-and-agents.html` | `pages/fr/advanced/agents-md-deep-dive.html` |
| 41 | en | Advanced | `pages/en/advanced/agents-md-deep-dive.html` | `pages/en/advanced/agent-context-suite.html` | `pages/en/advanced/skills-md-deep-dive.html` |
| 41 | fr-CA | Advanced | `pages/fr/advanced/agents-md-deep-dive.html` | `pages/fr/advanced/agent-context-suite.html` | `pages/fr/advanced/skills-md-deep-dive.html` |
| 42 | en | Advanced | `pages/en/advanced/skills-md-deep-dive.html` | `pages/en/advanced/agents-md-deep-dive.html` | `pages/en/advanced/test-first-ai-workflows.html` |
| 42 | fr-CA | Advanced | `pages/fr/advanced/skills-md-deep-dive.html` | `pages/fr/advanced/agents-md-deep-dive.html` | `pages/fr/advanced/test-first-ai-workflows.html` |
| 43 | en | Advanced | `pages/en/advanced/test-first-ai-workflows.html` | `pages/en/advanced/skills-md-deep-dive.html` | `pages/en/advanced/code-review-with-ai.html` |
| 43 | fr-CA | Advanced | `pages/fr/advanced/test-first-ai-workflows.html` | `pages/fr/advanced/skills-md-deep-dive.html` | `pages/fr/advanced/code-review-with-ai.html` |
| 44 | en | Advanced | `pages/en/advanced/code-review-with-ai.html` | `pages/en/advanced/test-first-ai-workflows.html` | `pages/en/advanced/ai-generated-code-smells.html` |
| 44 | fr-CA | Advanced | `pages/fr/advanced/code-review-with-ai.html` | `pages/fr/advanced/test-first-ai-workflows.html` | `pages/fr/advanced/ai-generated-code-smells.html` |
| 45 | en | Advanced | `pages/en/advanced/ai-generated-code-smells.html` | `pages/en/advanced/code-review-with-ai.html` | `pages/en/advanced/tool-calling-and-function-boundaries.html` |
| 45 | fr-CA | Advanced | `pages/fr/advanced/ai-generated-code-smells.html` | `pages/fr/advanced/code-review-with-ai.html` | `pages/fr/advanced/tool-calling-and-function-boundaries.html` |
| 46 | en | Advanced | `pages/en/advanced/tool-calling-and-function-boundaries.html` | `pages/en/advanced/ai-generated-code-smells.html` | `pages/en/advanced/mcp-basics.html` |
| 46 | fr-CA | Advanced | `pages/fr/advanced/tool-calling-and-function-boundaries.html` | `pages/fr/advanced/ai-generated-code-smells.html` | `pages/fr/advanced/mcp-basics.html` |
| 47 | en | Advanced | `pages/en/advanced/mcp-basics.html` | `pages/en/advanced/tool-calling-and-function-boundaries.html` | `pages/en/advanced/connectors-and-data-access.html` |
| 47 | fr-CA | Advanced | `pages/fr/advanced/mcp-basics.html` | `pages/fr/advanced/tool-calling-and-function-boundaries.html` | `pages/fr/advanced/connectors-and-data-access.html` |
| 48 | en | Advanced | `pages/en/advanced/connectors-and-data-access.html` | `pages/en/advanced/mcp-basics.html` | `pages/en/advanced/prompt-injection-for-agents.html` |
| 48 | fr-CA | Advanced | `pages/fr/advanced/connectors-and-data-access.html` | `pages/fr/advanced/mcp-basics.html` | `pages/fr/advanced/prompt-injection-for-agents.html` |
| 49 | en | Advanced | `pages/en/advanced/prompt-injection-for-agents.html` | `pages/en/advanced/connectors-and-data-access.html` | `pages/en/advanced/agent-permissions-ladder.html` |
| 49 | fr-CA | Advanced | `pages/fr/advanced/prompt-injection-for-agents.html` | `pages/fr/advanced/connectors-and-data-access.html` | `pages/fr/advanced/agent-permissions-ladder.html` |
| 50 | en | Advanced | `pages/en/advanced/agent-permissions-ladder.html` | `pages/en/advanced/prompt-injection-for-agents.html` | `pages/en/advanced/controlled-automation.html` |
| 50 | fr-CA | Advanced | `pages/fr/advanced/agent-permissions-ladder.html` | `pages/fr/advanced/prompt-injection-for-agents.html` | `pages/fr/advanced/controlled-automation.html` |
| 51 | en | Advanced | `pages/en/advanced/controlled-automation.html` | `pages/en/advanced/agent-permissions-ladder.html` | `pages/en/advanced/agent-observability.html` |
| 51 | fr-CA | Advanced | `pages/fr/advanced/controlled-automation.html` | `pages/fr/advanced/agent-permissions-ladder.html` | `pages/fr/advanced/agent-observability.html` |
| 52 | en | Advanced | `pages/en/advanced/agent-observability.html` | `pages/en/advanced/controlled-automation.html` | `pages/en/advanced/security-privacy-and-governance.html` |
| 52 | fr-CA | Advanced | `pages/fr/advanced/agent-observability.html` | `pages/fr/advanced/controlled-automation.html` | `pages/fr/advanced/security-privacy-and-governance.html` |
| 53 | en | Advanced | `pages/en/advanced/security-privacy-and-governance.html` | `pages/en/advanced/agent-observability.html` | `pages/en/advanced/ai-governance-without-theater.html` |
| 53 | fr-CA | Advanced | `pages/fr/advanced/security-privacy-and-governance.html` | `pages/fr/advanced/agent-observability.html` | `pages/fr/advanced/ai-governance-without-theater.html` |
| 54 | en | Advanced | `pages/en/advanced/ai-governance-without-theater.html` | `pages/en/advanced/security-privacy-and-governance.html` | `pages/en/advanced/ai-risk-tiers.html` |
| 54 | fr-CA | Advanced | `pages/fr/advanced/ai-governance-without-theater.html` | `pages/fr/advanced/security-privacy-and-governance.html` | `pages/fr/advanced/ai-risk-tiers.html` |
| 55 | en | Advanced | `pages/en/advanced/ai-risk-tiers.html` | `pages/en/advanced/ai-governance-without-theater.html` | `pages/en/advanced/infrastructure-and-iac-risk.html` |
| 55 | fr-CA | Advanced | `pages/fr/advanced/ai-risk-tiers.html` | `pages/fr/advanced/ai-governance-without-theater.html` | `pages/fr/advanced/infrastructure-and-iac-risk.html` |
| 56 | en | Advanced | `pages/en/advanced/infrastructure-and-iac-risk.html` | `pages/en/advanced/ai-risk-tiers.html` | `pages/en/advanced/governed-ai-delivery.html` |
| 56 | fr-CA | Advanced | `pages/fr/advanced/infrastructure-and-iac-risk.html` | `pages/fr/advanced/ai-risk-tiers.html` | `pages/fr/advanced/governed-ai-delivery.html` |
| 57 | en | Advanced | `pages/en/advanced/governed-ai-delivery.html` | `pages/en/advanced/infrastructure-and-iac-risk.html` | `pages/en/advanced/ai-for-incident-response-support.html` |
| 57 | fr-CA | Advanced | `pages/fr/advanced/governed-ai-delivery.html` | `pages/fr/advanced/infrastructure-and-iac-risk.html` | `pages/fr/advanced/ai-for-incident-response-support.html` |
| 58 | en | Advanced | `pages/en/advanced/ai-for-incident-response-support.html` | `pages/en/advanced/governed-ai-delivery.html` | `pages/en/advanced/ai-pilot-to-production.html` |
| 58 | fr-CA | Advanced | `pages/fr/advanced/ai-for-incident-response-support.html` | `pages/fr/advanced/governed-ai-delivery.html` | `pages/fr/advanced/ai-pilot-to-production.html` |
| 59 | en | Advanced | `pages/en/advanced/ai-pilot-to-production.html` | `pages/en/advanced/ai-for-incident-response-support.html` | `pages/en/advanced/shadow-ai-and-unsanctioned-use.html` |
| 60 | en | Advanced | `pages/en/advanced/shadow-ai-and-unsanctioned-use.html` | `pages/en/advanced/ai-pilot-to-production.html` | `pages/en/advanced/source-of-truth-design.html` |
| 61 | en | Advanced | `pages/en/advanced/source-of-truth-design.html` | `pages/en/advanced/shadow-ai-and-unsanctioned-use.html` | `pages/en/advanced/retrieval-failure-modes.html` |
| 62 | en | Advanced | `pages/en/advanced/retrieval-failure-modes.html` | `pages/en/advanced/source-of-truth-design.html` | `pages/en/advanced/embeddings-and-vector-search.html` |
| 63 | en | Advanced | `pages/en/advanced/embeddings-and-vector-search.html` | `pages/en/advanced/retrieval-failure-modes.html` | `pages/en/advanced/chunking-strategy.html` |
| 64 | en | Advanced | `pages/en/advanced/chunking-strategy.html` | `pages/en/advanced/embeddings-and-vector-search.html` | `pages/en/expert/ai-operating-model.html` |
| 65 | en | Expert | `pages/en/expert/ai-operating-model.html` | `pages/en/advanced/chunking-strategy.html` | `pages/en/expert/strategic-ai-portfolio.html` |
| 66 | en | Expert | `pages/en/expert/strategic-ai-portfolio.html` | `pages/en/expert/ai-operating-model.html` | `pages/en/expert/ai-architecture-strategy.html` |
| 67 | en | Expert | `pages/en/expert/ai-architecture-strategy.html` | `pages/en/expert/strategic-ai-portfolio.html` | `pages/en/expert/ai-vendor-and-tool-selection.html` |
| 68 | en | Expert | `pages/en/expert/ai-vendor-and-tool-selection.html` | `pages/en/expert/ai-architecture-strategy.html` | `pages/en/expert/local-models-vs-hosted-models.html` |
| 69 | en | Expert | `pages/en/expert/local-models-vs-hosted-models.html` | `pages/en/expert/ai-vendor-and-tool-selection.html` | `pages/en/expert/model-selection-and-cost-management.html` |
| 70 | en | Expert | `pages/en/expert/model-selection-and-cost-management.html` | `pages/en/expert/local-models-vs-hosted-models.html` | `pages/en/expert/cost-controls-for-teams.html` |
| 71 | en | Expert | `pages/en/expert/cost-controls-for-teams.html` | `pages/en/expert/model-selection-and-cost-management.html` | `pages/en/expert/ai-security-architecture.html` |
| 72 | en | Expert | `pages/en/expert/ai-security-architecture.html` | `pages/en/expert/cost-controls-for-teams.html` | `pages/en/expert/mcp-security-and-permissions.html` |
| 73 | en | Expert | `pages/en/expert/mcp-security-and-permissions.html` | `pages/en/expert/ai-security-architecture.html` | `pages/en/expert/retrieval-and-knowledge-governance.html` |
| 74 | en | Expert | `pages/en/expert/retrieval-and-knowledge-governance.html` | `pages/en/expert/mcp-security-and-permissions.html` | `pages/en/expert/evaluation-harnesses.html` |
| 75 | en | Expert | `pages/en/expert/evaluation-harnesses.html` | `pages/en/expert/retrieval-and-knowledge-governance.html` | `pages/en/expert/evaluation-and-red-teaming.html` |
| 76 | en | Expert | `pages/en/expert/evaluation-and-red-teaming.html` | `pages/en/expert/evaluation-harnesses.html` | `pages/en/expert/change-management-and-adoption.html` |
| 77 | en | Expert | `pages/en/expert/change-management-and-adoption.html` | `pages/en/expert/evaluation-and-red-teaming.html` | `pages/en/prompts/prompting-basics.html` |
| 78 | en | Prompt library | `pages/en/prompts/prompting-basics.html` | `pages/en/expert/change-management-and-adoption.html` | `pages/en/prompts/email-and-communication-prompt.html` |
| 79 | en | Prompt library | `pages/en/prompts/email-and-communication-prompt.html` | `pages/en/prompts/prompting-basics.html` | `pages/en/prompts/meeting-summary-prompt.html` |
| 80 | en | Prompt library | `pages/en/prompts/meeting-summary-prompt.html` | `pages/en/prompts/email-and-communication-prompt.html` | `pages/en/prompts/executive-summary-prompt.html` |
| 81 | en | Prompt library | `pages/en/prompts/executive-summary-prompt.html` | `pages/en/prompts/meeting-summary-prompt.html` | `pages/en/prompts/document-review-prompt.html` |
| 82 | en | Prompt library | `pages/en/prompts/document-review-prompt.html` | `pages/en/prompts/executive-summary-prompt.html` | `pages/en/prompts/vibe-brief-prompt.html` |
| 83 | en | Prompt library | `pages/en/prompts/vibe-brief-prompt.html` | `pages/en/prompts/document-review-prompt.html` | `pages/en/prompts/implementation-plan-prompt.html` |
| 84 | en | Prompt library | `pages/en/prompts/implementation-plan-prompt.html` | `pages/en/prompts/vibe-brief-prompt.html` | `pages/en/prompts/risk-review-prompt.html` |
| 85 | en | Prompt library | `pages/en/prompts/risk-review-prompt.html` | `pages/en/prompts/implementation-plan-prompt.html` | `pages/en/prompts/checkpointed-execution-prompt.html` |
| 86 | en | Prompt library | `pages/en/prompts/checkpointed-execution-prompt.html` | `pages/en/prompts/risk-review-prompt.html` | `pages/en/prompts/code-review-prompt.html` |
| 87 | en | Prompt library | `pages/en/prompts/code-review-prompt.html` | `pages/en/prompts/checkpointed-execution-prompt.html` | End |
