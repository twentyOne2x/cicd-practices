# Working with coding agents

Sources read: 2026-10-10. Repository rules and product documentation are living documents. Anthropic's review-cost account below was published on 2026-03-09.

## Small tasks with explicit done checks

Matt Pocock's ticket skill defines small slices that deliver a complete behavior, can be demonstrated or verified independently, and fit one fresh context window. Each ticket includes acceptance criteria and its blocking dependencies. His implementation guide recommends one ticket per session, clearing context between tickets. [Ticket skill](https://github.com/mattpocock/skills/blob/main/skills/engineering/to-tickets/SKILL.md), [Implementation guide](https://www.aihero.dev/skills-implement).

## Independent review of the exact change

Pocock's review guide recommends a fresh session and separates repository standards from specification compliance. Review uses the committed diff between a named reference and `HEAD`; staged and working-tree changes are excluded. The guide also says findings need checking against their cited evidence. [Review guide](https://www.aihero.dev/skills-code-review).

CodeRabbit's optional request-changes workflow requires review of the latest commit and verifies that the PR head has not changed immediately before approval. Explicit approval commands can override review requirements, so this behavior depends on configuration and the approval path. [Request changes workflow](https://docs.coderabbit.ai/pr-reviews/request-changes-workflow).

## Feed recurring rejections back into instructions and checks

Anthropic recommends updating project instructions when an agent repeats a mistake or review catches something it should have known. It recommends concrete, verifiable instructions and moving scoped procedures into skills or rules. [Memory and instructions](https://code.claude.com/docs/en/memory).

Pstack's Correct skill groups repeated mistakes, prefers architecture, types, lint and behavior tests over more prose, and requires proving a check rejects a real past mistake. Its instruction file pairs rules with their enforcement. It states: "Nothing fails when an agent skips them." That sentence refers to written rules. [Correct skill](https://github.com/cursor/plugins/blob/main/pstack/skills/correct/SKILL.md).

## Separate contexts and preserve useful cache reads

Anthropic documents that a Claude Code subagent starts a separate conversation and builds its own cache; its first request does not read the parent's cache. Claude Code automatically caches unchanged request prefixes and bills cache reads below the standard input rate. Model switches rebuild the cache. Its guidance places model and effort choices at session start and compaction at natural breaks between tasks. [Prompt caching](https://code.claude.com/docs/en/prompt-caching).

Cached prefixes expire after inactivity. A longer cache lifetime charges more for writes and can cost more when short sessions never use the extra lifetime. These are Claude Code mechanisms, with billing and provider conditions documented on the same page. [Prompt caching](https://code.claude.com/docs/en/prompt-caching).

## Costs and limits

Anthropic's March 2026 Code Review account reports token-billed reviews generally averaging $15 to $25, depending on PR size and complexity. It documents monthly organization spending caps and repository controls. This is a dated product account, not a price estimate for every agent workflow. [Code Review](https://claude.com/resources/articles/code-review).

OpenAI documents that Codex discovers project instructions once per run and stops adding them at a configurable combined limit, 32 KiB by default. Anthropic recommends fewer than 200 lines per CLAUDE.md; that recommendation is not a hard file-size limit. It also distinguishes written guidance from enforced configuration. [Codex instructions](https://learn.chatgpt.com/docs/agent-configuration/agents-md), [Claude Code instructions](https://code.claude.com/docs/en/memory).
