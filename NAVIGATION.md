# NAVIGATION.md

Version: 1.0.0
Status: Active
Repository type: AI education knowledge base

## Purpose

This file defines the canonical previous and next navigation order for every active HTML education page under `pages/`. AI agents should use this file when adding, renaming, retiring, or editing education pages so page-level navigation remains consistent with the learning path.

## Agent Rules

- Treat the table below as the source of truth for page-to-page navigation.
- When a page is added, removed, renamed, or moved under `pages/`, update this file, the affected HTML navigation cards, `index.html` when applicable, and `CODEX.md` in the same change set.
- Each HTML page under `pages/` should include navigation immediately after the hero section and again after the takeaway card.
- Navigation cards should include Previous, Home, and Next destinations.
- Use `index.html` as Home. Do not use `_blank` targets for internal education navigation.

## Navigation Order

| Order | Level | Page | Previous | Next |
| --- | --- | --- | --- | --- |
| 1 | Beginner | `pages/beginner/ai-literacy-basics.html` | Start | `pages/beginner/ai-lexicon-for-beginners.html` |
| 2 | Beginner | `pages/beginner/ai-lexicon-for-beginners.html` | `pages/beginner/ai-literacy-basics.html` | `pages/beginner/ai-for-non-technical-people.html` |
| 3 | Beginner | `pages/beginner/ai-for-non-technical-people.html` | `pages/beginner/ai-lexicon-for-beginners.html` | `pages/beginner/prompting-basics.html` |
| 4 | Beginner | `pages/beginner/prompting-basics.html` | `pages/beginner/ai-for-non-technical-people.html` | `pages/beginner/privacy-and-safe-use.html` |
| 5 | Beginner | `pages/beginner/privacy-and-safe-use.html` | `pages/beginner/prompting-basics.html` | `pages/beginner/hallucinations-and-verification.html` |
| 6 | Beginner | `pages/beginner/hallucinations-and-verification.html` | `pages/beginner/privacy-and-safe-use.html` | `pages/beginner/source-quality-and-citation-hygiene.html` |
| 7 | Beginner | `pages/beginner/source-quality-and-citation-hygiene.html` | `pages/beginner/hallucinations-and-verification.html` | `pages/beginner/human-accountability.html` |
| 8 | Beginner | `pages/beginner/human-accountability.html` | `pages/beginner/source-quality-and-citation-hygiene.html` | `pages/beginner/multimodal-ai-basics.html` |
| 9 | Beginner | `pages/beginner/multimodal-ai-basics.html` | `pages/beginner/human-accountability.html` | `pages/beginner/memory-vs-context-vs-instructions.html` |
| 10 | Beginner | `pages/beginner/memory-vs-context-vs-instructions.html` | `pages/beginner/multimodal-ai-basics.html` | `pages/beginner/introduction-to-vibe-coding.html` |
| 11 | Beginner | `pages/beginner/introduction-to-vibe-coding.html` | `pages/beginner/memory-vs-context-vs-instructions.html` | `pages/beginner/md-hierarchy-for-ai-agents.html` |
| 12 | Beginner | `pages/beginner/md-hierarchy-for-ai-agents.html` | `pages/beginner/introduction-to-vibe-coding.html` | `pages/intermediate/vibe-coding-vs-implementation-planning.html` |
| 13 | Intermediate | `pages/intermediate/vibe-coding-vs-implementation-planning.html` | `pages/beginner/md-hierarchy-for-ai-agents.html` | `pages/intermediate/ai-use-case-intake.html` |
| 14 | Intermediate | `pages/intermediate/ai-use-case-intake.html` | `pages/intermediate/vibe-coding-vs-implementation-planning.html` | `pages/intermediate/ai-data-boundaries.html` |
| 15 | Intermediate | `pages/intermediate/ai-data-boundaries.html` | `pages/intermediate/ai-use-case-intake.html` | `pages/intermediate/ai-for-sensitive-decisions.html` |
| 16 | Intermediate | `pages/intermediate/ai-for-sensitive-decisions.html` | `pages/intermediate/ai-data-boundaries.html` | `pages/intermediate/prompt-injection-for-business-users.html` |
| 17 | Intermediate | `pages/intermediate/prompt-injection-for-business-users.html` | `pages/intermediate/ai-for-sensitive-decisions.html` | `pages/intermediate/blast-radius-thinking.html` |
| 18 | Intermediate | `pages/intermediate/blast-radius-thinking.html` | `pages/intermediate/prompt-injection-for-business-users.html` | `pages/intermediate/human-in-the-loop-design.html` |
| 19 | Intermediate | `pages/intermediate/human-in-the-loop-design.html` | `pages/intermediate/blast-radius-thinking.html` | `pages/intermediate/token-economy.html` |
| 20 | Intermediate | `pages/intermediate/token-economy.html` | `pages/intermediate/human-in-the-loop-design.html` | `pages/intermediate/token-budgeting-for-real-work.html` |
| 21 | Intermediate | `pages/intermediate/token-budgeting-for-real-work.html` | `pages/intermediate/token-economy.html` | `pages/intermediate/context-compression.html` |
| 22 | Intermediate | `pages/intermediate/context-compression.html` | `pages/intermediate/token-budgeting-for-real-work.html` | `pages/intermediate/context-and-prompt-drift.html` |
| 23 | Intermediate | `pages/intermediate/context-and-prompt-drift.html` | `pages/intermediate/context-compression.html` | `pages/intermediate/ai-output-acceptance-criteria.html` |
| 24 | Intermediate | `pages/intermediate/ai-output-acceptance-criteria.html` | `pages/intermediate/context-and-prompt-drift.html` | `pages/intermediate/implementation-plans-and-specs.html` |
| 25 | Intermediate | `pages/intermediate/implementation-plans-and-specs.html` | `pages/intermediate/ai-output-acceptance-criteria.html` | `pages/intermediate/plan-md-vs-spec-md-vs-runbook-md.html` |
| 26 | Intermediate | `pages/intermediate/plan-md-vs-spec-md-vs-runbook-md.html` | `pages/intermediate/implementation-plans-and-specs.html` | `pages/intermediate/review-gates-and-rollback.html` |
| 27 | Intermediate | `pages/intermediate/review-gates-and-rollback.html` | `pages/intermediate/plan-md-vs-spec-md-vs-runbook-md.html` | `pages/intermediate/checkpointed-execution.html` |
| 28 | Intermediate | `pages/intermediate/checkpointed-execution.html` | `pages/intermediate/review-gates-and-rollback.html` | `pages/intermediate/agent-handoff-notes.html` |
| 29 | Intermediate | `pages/intermediate/agent-handoff-notes.html` | `pages/intermediate/checkpointed-execution.html` | `pages/intermediate/ai-assisted-debugging.html` |
| 30 | Intermediate | `pages/intermediate/ai-assisted-debugging.html` | `pages/intermediate/agent-handoff-notes.html` | `pages/intermediate/ai-and-documentation-systems.html` |
| 31 | Intermediate | `pages/intermediate/ai-and-documentation-systems.html` | `pages/intermediate/ai-assisted-debugging.html` | `pages/intermediate/ai-content-lifecycle.html` |
| 32 | Intermediate | `pages/intermediate/ai-content-lifecycle.html` | `pages/intermediate/ai-and-documentation-systems.html` | `pages/intermediate/ai-for-slide-and-visual-planning.html` |
| 33 | Intermediate | `pages/intermediate/ai-for-slide-and-visual-planning.html` | `pages/intermediate/ai-content-lifecycle.html` | `pages/advanced/ai-for-technical-teams.html` |
| 34 | Advanced | `pages/advanced/ai-for-technical-teams.html` | `pages/intermediate/ai-for-slide-and-visual-planning.html` | `pages/advanced/ai-coding-agents.html` |
| 35 | Advanced | `pages/advanced/ai-coding-agents.html` | `pages/advanced/ai-for-technical-teams.html` | `pages/advanced/repository-instructions-and-agents.html` |
| 36 | Advanced | `pages/advanced/repository-instructions-and-agents.html` | `pages/advanced/ai-coding-agents.html` | `pages/advanced/agent-context-suite.html` |
| 37 | Advanced | `pages/advanced/agent-context-suite.html` | `pages/advanced/repository-instructions-and-agents.html` | `pages/advanced/agents-md-deep-dive.html` |
| 38 | Advanced | `pages/advanced/agents-md-deep-dive.html` | `pages/advanced/agent-context-suite.html` | `pages/advanced/skills-md-deep-dive.html` |
| 39 | Advanced | `pages/advanced/skills-md-deep-dive.html` | `pages/advanced/agents-md-deep-dive.html` | `pages/advanced/test-first-ai-workflows.html` |
| 40 | Advanced | `pages/advanced/test-first-ai-workflows.html` | `pages/advanced/skills-md-deep-dive.html` | `pages/advanced/code-review-with-ai.html` |
| 41 | Advanced | `pages/advanced/code-review-with-ai.html` | `pages/advanced/test-first-ai-workflows.html` | `pages/advanced/ai-generated-code-smells.html` |
| 42 | Advanced | `pages/advanced/ai-generated-code-smells.html` | `pages/advanced/code-review-with-ai.html` | `pages/advanced/tool-calling-and-function-boundaries.html` |
| 43 | Advanced | `pages/advanced/tool-calling-and-function-boundaries.html` | `pages/advanced/ai-generated-code-smells.html` | `pages/advanced/mcp-basics.html` |
| 44 | Advanced | `pages/advanced/mcp-basics.html` | `pages/advanced/tool-calling-and-function-boundaries.html` | `pages/advanced/connectors-and-data-access.html` |
| 45 | Advanced | `pages/advanced/connectors-and-data-access.html` | `pages/advanced/mcp-basics.html` | `pages/advanced/prompt-injection-for-agents.html` |
| 46 | Advanced | `pages/advanced/prompt-injection-for-agents.html` | `pages/advanced/connectors-and-data-access.html` | `pages/advanced/agent-permissions-ladder.html` |
| 47 | Advanced | `pages/advanced/agent-permissions-ladder.html` | `pages/advanced/prompt-injection-for-agents.html` | `pages/advanced/controlled-automation.html` |
| 48 | Advanced | `pages/advanced/controlled-automation.html` | `pages/advanced/agent-permissions-ladder.html` | `pages/advanced/agent-observability.html` |
| 49 | Advanced | `pages/advanced/agent-observability.html` | `pages/advanced/controlled-automation.html` | `pages/advanced/security-privacy-and-governance.html` |
| 50 | Advanced | `pages/advanced/security-privacy-and-governance.html` | `pages/advanced/agent-observability.html` | `pages/advanced/ai-governance-without-theater.html` |
| 51 | Advanced | `pages/advanced/ai-governance-without-theater.html` | `pages/advanced/security-privacy-and-governance.html` | `pages/advanced/ai-risk-tiers.html` |
| 52 | Advanced | `pages/advanced/ai-risk-tiers.html` | `pages/advanced/ai-governance-without-theater.html` | `pages/advanced/infrastructure-and-iac-risk.html` |
| 53 | Advanced | `pages/advanced/infrastructure-and-iac-risk.html` | `pages/advanced/ai-risk-tiers.html` | `pages/advanced/review-gates-and-rollback.html` |
| 54 | Advanced | `pages/advanced/review-gates-and-rollback.html` | `pages/advanced/infrastructure-and-iac-risk.html` | `pages/advanced/ai-for-incident-response-support.html` |
| 55 | Advanced | `pages/advanced/ai-for-incident-response-support.html` | `pages/advanced/review-gates-and-rollback.html` | `pages/advanced/ai-pilot-to-production.html` |
| 56 | Advanced | `pages/advanced/ai-pilot-to-production.html` | `pages/advanced/ai-for-incident-response-support.html` | `pages/advanced/shadow-ai-and-unsanctioned-use.html` |
| 57 | Advanced | `pages/advanced/shadow-ai-and-unsanctioned-use.html` | `pages/advanced/ai-pilot-to-production.html` | `pages/advanced/source-of-truth-design.html` |
| 58 | Advanced | `pages/advanced/source-of-truth-design.html` | `pages/advanced/shadow-ai-and-unsanctioned-use.html` | `pages/advanced/retrieval-failure-modes.html` |
| 59 | Advanced | `pages/advanced/retrieval-failure-modes.html` | `pages/advanced/source-of-truth-design.html` | `pages/advanced/embeddings-and-vector-search.html` |
| 60 | Advanced | `pages/advanced/embeddings-and-vector-search.html` | `pages/advanced/retrieval-failure-modes.html` | `pages/advanced/chunking-strategy.html` |
| 61 | Advanced | `pages/advanced/chunking-strategy.html` | `pages/advanced/embeddings-and-vector-search.html` | `pages/expert/ai-operating-model.html` |
| 62 | Expert | `pages/expert/ai-operating-model.html` | `pages/advanced/chunking-strategy.html` | `pages/expert/strategic-ai-portfolio.html` |
| 63 | Expert | `pages/expert/strategic-ai-portfolio.html` | `pages/expert/ai-operating-model.html` | `pages/expert/ai-architecture-strategy.html` |
| 64 | Expert | `pages/expert/ai-architecture-strategy.html` | `pages/expert/strategic-ai-portfolio.html` | `pages/expert/ai-vendor-and-tool-selection.html` |
| 65 | Expert | `pages/expert/ai-vendor-and-tool-selection.html` | `pages/expert/ai-architecture-strategy.html` | `pages/expert/local-models-vs-hosted-models.html` |
| 66 | Expert | `pages/expert/local-models-vs-hosted-models.html` | `pages/expert/ai-vendor-and-tool-selection.html` | `pages/expert/model-selection-and-cost-management.html` |
| 67 | Expert | `pages/expert/model-selection-and-cost-management.html` | `pages/expert/local-models-vs-hosted-models.html` | `pages/expert/cost-controls-for-teams.html` |
| 68 | Expert | `pages/expert/cost-controls-for-teams.html` | `pages/expert/model-selection-and-cost-management.html` | `pages/expert/ai-security-architecture.html` |
| 69 | Expert | `pages/expert/ai-security-architecture.html` | `pages/expert/cost-controls-for-teams.html` | `pages/expert/mcp-security-and-permissions.html` |
| 70 | Expert | `pages/expert/mcp-security-and-permissions.html` | `pages/expert/ai-security-architecture.html` | `pages/expert/retrieval-and-knowledge-governance.html` |
| 71 | Expert | `pages/expert/retrieval-and-knowledge-governance.html` | `pages/expert/mcp-security-and-permissions.html` | `pages/expert/evaluation-harnesses.html` |
| 72 | Expert | `pages/expert/evaluation-harnesses.html` | `pages/expert/retrieval-and-knowledge-governance.html` | `pages/expert/evaluation-and-red-teaming.html` |
| 73 | Expert | `pages/expert/evaluation-and-red-teaming.html` | `pages/expert/evaluation-harnesses.html` | `pages/expert/change-management-and-adoption.html` |
| 74 | Expert | `pages/expert/change-management-and-adoption.html` | `pages/expert/evaluation-and-red-teaming.html` | `pages/prompts/prompting-basics.html` |
| 75 | Prompt library | `pages/prompts/prompting-basics.html` | `pages/expert/change-management-and-adoption.html` | `pages/prompts/email-and-communication-prompt.html` |
| 76 | Prompt library | `pages/prompts/email-and-communication-prompt.html` | `pages/prompts/prompting-basics.html` | `pages/prompts/meeting-summary-prompt.html` |
| 77 | Prompt library | `pages/prompts/meeting-summary-prompt.html` | `pages/prompts/email-and-communication-prompt.html` | `pages/prompts/executive-summary-prompt.html` |
| 78 | Prompt library | `pages/prompts/executive-summary-prompt.html` | `pages/prompts/meeting-summary-prompt.html` | `pages/prompts/document-review-prompt.html` |
| 79 | Prompt library | `pages/prompts/document-review-prompt.html` | `pages/prompts/executive-summary-prompt.html` | `pages/prompts/vibe-brief-prompt.html` |
| 80 | Prompt library | `pages/prompts/vibe-brief-prompt.html` | `pages/prompts/document-review-prompt.html` | `pages/prompts/implementation-plan-prompt.html` |
| 81 | Prompt library | `pages/prompts/implementation-plan-prompt.html` | `pages/prompts/vibe-brief-prompt.html` | `pages/prompts/risk-review-prompt.html` |
| 82 | Prompt library | `pages/prompts/risk-review-prompt.html` | `pages/prompts/implementation-plan-prompt.html` | `pages/prompts/checkpointed-execution-prompt.html` |
| 83 | Prompt library | `pages/prompts/checkpointed-execution-prompt.html` | `pages/prompts/risk-review-prompt.html` | `pages/prompts/code-review-prompt.html` |
| 84 | Prompt library | `pages/prompts/code-review-prompt.html` | `pages/prompts/checkpointed-execution-prompt.html` | End |
