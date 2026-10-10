# Agent instructions and enforcement

Sources read: 2026-10-10. The repository instructions and platform documentation cited here are undated living documents.

Pstack's Correct skill states: "Nothing fails when an agent skips them." The sentence refers to written agent rules. Its prescribed repairs prioritize architecture, types, lint or CI checks, and behavior tests, with documentation reserved for judgment. [pstack: Correct](https://github.com/cursor/plugins/blob/main/pstack/skills/correct/SKILL.md).

Matt Pocock's testing documentation reports agents implementing before writing the failing test despite reading the instruction. It also reports that an earlier refactoring step was rarely followed. These are reported experiences without a measured compliance rate. [Testing documentation](https://raw.githubusercontent.com/mattpocock/skills/main/docs/engineering/tdd.md).

OpenClaw's repository rules direct agents to scoped procedures. Its landing procedure binds review records to the commit being prepared and submits merging behind CI and required reviews, subject to documented exceptions. [Repository instructions](https://raw.githubusercontent.com/openclaw/openclaw/main/AGENTS.md), [Landing procedure](https://raw.githubusercontent.com/openclaw/openclaw/main/.agents/skills/openclaw-pr-maintainer/references/landing.md).

GitHub documents branch protection as a separate mechanism for requiring checks and reviews. Together, these sources suggest assigning different jobs to different mechanisms: written instructions explain the workflow, while configured required checks enforce selected conditions. This last distinction is a synthesis of the cited examples. [About protected branches](https://docs.github.com/en/repositories/configuring-branches-and-merges-in-your-repository/managing-protected-branches/about-protected-branches).
