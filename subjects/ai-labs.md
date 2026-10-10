# OpenAI and Anthropic

Sources read: 2026-10-10. Dates below identify the published accounts.

OpenAI's guide dated 2026-01-14 describes engineers assigning background coding tasks to Codex, which writes tests and proposes PRs for engineer review. This is a reported workflow. [How OpenAI uses Codex](https://openai.com/business/guides-and-resources/how-openai-uses-codex/).

Its separate beta experiment, described 2026-02-11, summarizes the division of work as "Humans steer. Agents execute." Agents review and repair proposed changes until reviewers are satisfied. Linters and structural tests enforce architectural rules. Human PR review is optional in this experiment, and the account describes few blocking merge checks. That does not establish a company-wide policy. [Ryan Lopopolo, Harness engineering: leveraging Codex in an agent-first world](https://openai.com/index/harness-engineering/).

Anthropic's Code Review announcement dated 2026-03-09 describes agents finding, verifying and prioritizing bugs while humans approve changes. It reports use on nearly every internal PR. [Code Review](https://claude.com/resources/articles/code-review).

Anthropic's sandboxing account dated 2025-10-20 describes isolation boundaries, keeping cloud-session credentials outside the sandbox, and controlling branch writes through a proxy. These are execution and access controls; the account does not establish a release-approval rule. [Claude Code sandboxing](https://www.anthropic.com/engineering/claude-code-sandboxing).
