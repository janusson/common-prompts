# Common Prompts

**Copy-and-paste instructions for useful, evidence-based AI work.**

A small, public, vendor-neutral library of reusable prompts for software development, knowledge capture, and planning. Intended for ChatGPT, Claude, Codex, Delta, OpenCode, Hermes, and other assistants with varying levels of tools and context.

No dependencies, SDK, prompt compiler, or account setup. Open a file, copy the prompt you want, and paste it into your agent.

## Prompt catalogue

| Prompt | Purpose | Mode |
| --- | --- | --- |
| [Improve Repo](prompts/development/improve-repo.md) | Find and deliver one high-value verified improvement; Quick + Full variants | Implement |
| [Bug Hunter](prompts/development/bug-hunter.md) | Reproduce and correct a bounded defect | Implement |
| [Issue Reconciler](prompts/development/issue-reconciler.md) | Detect stale, duplicate, resolved, or actively owned issues | Audit |
| [Test Gap](prompts/development/test-gap.md) | Add the most useful missing deterministic test | Implement |
| [Invariant Auditor](prompts/development/invariant-auditor.md) | Verify math, accounting, scientific, or temporal invariants | Audit |
| [Failure-Path Auditor](prompts/development/failure-path-auditor.md) | Catch silent failures and misleading fallback behavior | Implement |
| [PR Reviewer](prompts/development/pr-review.md) | Independently review a pull request | Review |
| [Docs Drift](prompts/development/docs-drift.md) | Reconcile documentation with actual behavior | Implement |
| [Performance Scout](prompts/development/performance-scout.md) | Benchmark and fix one genuine bottleneck | Implement |
| [Archive Conversation](prompts/knowledge/archive-conversation.md) | Create an Obsidian-ready session record; Compact + Detailed variants | Archive |
| [Agent Handoff](prompts/knowledge/agent-handoff.md) | Preserve verified state so a different model can continue | Handoff |
| [Next Best Action](prompts/planning/next-best-action.md) | Select one justified task from an active project | Plan |

## Quick start

1. Pick a task in the table.
2. Open its Markdown file and copy only the text inside the **Prompt** code fence (not the surrounding explanation).
3. Give the agent access to the relevant repository/conversation if needed. A prompt does not grant tools or permissions.
4. Review the actual evidence and changes. A claimed test pass is not proof unless the agent ran it.

For cost-sensitive/free models, prefer the **Quick** version of [Improve Repo](prompts/development/improve-repo.md), or small read-only tasks such as [Issue Reconciler](prompts/development/issue-reconciler.md). Allow a single bounded task per run and avoid repeated full-repository scans.

## Operating principles

- **Evidence before edits.** Inspect current code and ongoing work; reproduce consequential defects before changing behavior.
- **One meaningful outcome per run.** Small, complete changes beat sprawling refactors.
- **No manufactured work.** `NO SAFE CHANGE` or `INSUFFICIENT EVIDENCE` is a valid result.
- **Honest verification.** Distinguish executed checks from unrun checks, assumptions, and proposals.
- **Safe autonomy.** Work on an isolated branch when possible; leave merges, releases, and risky policy decisions for human review.
- **Preserve context.** Report files, issue/PR references, decisions, test commands, and blockers so another agent can continue.
- **Vendor-neutral by default.** Avoid hardcoding platform/model names, tokens, URLs, or organization-specific infrastructure in generic prompts.

## Understanding the modes

**Audit / Review / Plan / Archive / Handoff:** Read and report; do not edit files unless explicitly directed. **Implement:** Make a narrow change only if the agent actually has file/terminal access and the working tree is safe. When an operation requires permission or a missing tool, report the blocker; do not claim it happened.

Financial, medical, security, privacy, and other high-impact domain decisions require additional scrutiny. The prompts are process templates, not a substitute for domain expertise or independent validation.

## Adding a prompt

Keep each entry short and task-specific. Prefer one Markdown file per action with a descriptive title, usage note, and a fenced copyable prompt. Add a catalogue row to this README. See [AGENTS.md](AGENTS.md) for maintenance rules.

## License

[MIT](LICENSE). Reuse, adapt, and share freely.
