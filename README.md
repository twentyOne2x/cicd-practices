# CI/CD practices for small teams using coding agents

A guide to making changes easy to check, review, merge and release. CI means continuous integration: automated checks on proposed and combined changes. CD means continuous delivery or deployment: preparing a releasable version, or sending it to users automatically.

## Ten practices to adopt this week

1. [Keep each change self-contained, with its related tests.](subjects/small-changes.md)
2. [Give each task an outcome that can be demonstrated or checked.](subjects/matt-pocock.md)
3. [Run focused checks frequently, then the broader suite.](subjects/matt-pocock.md)
4. [Get independent review of the proposed change.](subjects/google.md)
5. [Keep one owner responsible through findings and repairs.](subjects/poteto-and-pstack.md)
6. [Turn recurring agent mistakes into executable rules.](subjects/agent-instructions.md)
7. [Configure required checks and reviews before merging.](subjects/github.md)
8. [Check the combined merge candidate.](subjects/merge-queues.md)
9. [Use a working preview to review behavior.](subjects/railway.md)
10. [Release traceable artifacts](subjects/google.md), [stage rollout and keep a recovery path.](subjects/large-engineering-teams.md)

Public sources read: **2026-10-10**. The patterns below recur across published engineering accounts, repository instructions and platform documentation. Each example has its own scope. A platform feature describes what a team can configure; a published workflow describes what its authors ask contributors to do.

## Make each change small and complete

Deliver one understandable behavior with the code and tests it needs. Google calls for a self-contained change that leaves the system working. Matt Pocock's ticket skill asks for independently demonstrable behavior. Meta's Sapling supports reviewing an early change while later parts are built above it. None of these sources establishes a universal numerical size limit. [Google: Small CLs](https://google.github.io/eng-practices/review/developer/small-cls.html), [Matt Pocock: ticket skill](https://github.com/mattpocock/skills/blob/main/skills/engineering/to-tickets/SKILL.md), [Meta: Sapling](https://engineering.fb.com/2022/11/15/open-source/sapling-source-control-scalable/).

## Run fast checks first, then broader checks

Give the writer feedback while the change is still easy to fix. Matt Pocock specifies frequent type checks and focused tests, followed by the full suite. Google's published test infrastructure runs selected tests before submission and longer affected tests afterward. Amazon's deployment pipeline adds integration checks and progressively wider production trials. The point is a sequence of useful checks, with each stage's coverage understood. [Matt Pocock: implementation skill](https://github.com/mattpocock/skills/blob/main/skills/engineering/implement/SKILL.md), [Google: continuous integration](https://abseil.io/resources/swe-book/html/ch23.html), [Amazon: safe deployments](https://aws.amazon.com/builders-library/automating-safe-hands-off-deployments/).

## Check the combined result before merging

Two changes can pass separately and fail together. GitHub's merge queue checks a temporary combination of the target branch and queued pull requests. Mergify and Aviator document combined batches and isolation of failed changes. A job queue that merely limits concurrent builds does not provide this integration check. [GitHub: managing a merge queue](https://docs.github.com/en/repositories/configuring-branches-and-merges-in-your-repository/configuring-pull-request-merges/managing-a-merge-queue), [Mergify: batches](https://docs.mergify.com/merge-queue/batches/), [Aviator: batching](https://docs.aviator.co/mergequeue/concepts/batching).

## Keep the same owner through review and repair

A rejection is another step in finishing the change. Poteto's pstack workflow assigns an agent responsibility through verification, repairs and merge. Cognition describes Devin repairing review findings and CI failures on its proposed changes. These are published workflows; they do not establish every team's installed approval rules. [pstack: full autopilot](https://github.com/cursor/plugins/blob/main/pstack/skills/poteto-mode/playbooks/autopilot-full.md), [pstack: babysitting a PR](https://github.com/cursor/plugins/blob/main/pstack/skills/poteto-mode/playbooks/babysit.md), [Cognition: building Devin with Devin](https://cognition.com/blog/how-cognition-uses-devin-to-build-devin).

## Make admission rules executable

An instruction tells an agent what to do. A required check can stop an invalid change from merging. GitHub rulesets can require checks and reviews. Factory describes turning recurring agent mistakes into lint rules used as merge gates. Pstack recommends fixing repeated mistakes through architecture, types, checks and tests. Verify what a check actually reports: a warning or neutral result may allow a merge. [GitHub: available rules](https://docs.github.com/en/repositories/configuring-branches-and-merges-in-your-repository/managing-rulesets/available-rules-for-rulesets), [Factory: directing agents with linters](https://factory.com/news/using-linters-to-direct-agents), [pstack: Correct](https://github.com/cursor/plugins/blob/main/pstack/skills/correct/SKILL.md).

## Give every release a traceable identity

Know which source revision produced the version being released. Google's release engineering account describes selected revisions, packaged outputs and staged rollout. OpenClaw's published release procedure binds source, validation and published packages, with beta preceding stable validation. Amazon describes signed packages and automated rollback during rollout. A passing pull request and a successful release are separate pieces of evidence. [Google: release engineering](https://sre.google/sre-book/release-engineering/), [OpenClaw: releasing](https://github.com/openclaw/openclaw/blob/e12c0d2/docs/reference/RELEASING.md), [Amazon: safe deployments](https://aws.amazon.com/builders-library/automating-safe-hands-off-deployments/).

## Preview the behavior before merge

Let reviewers exercise a working version. Railway documents temporary environments for pull requests and their automatic removal. Linear describes preview builds, review and iteration during its design refresh. Preview infrastructure and feature switches answer different questions: the former provides a running candidate, while the latter controls who sees behavior. [Railway: PR environments](https://docs.railway.com/guides/preview-deployments-with-pr-environments), [Linear: design refresh](https://linear.app/now/behind-the-latest-design-refresh).

## Where these practices appear

The checklist is a synthesis. The labels below distinguish published instructions, configurable features and dated engineering accounts. Historical examples do not establish current company-wide policy.

| Practice | Public examples and their scope |
| --- | --- |
| Self-contained changes | [Google review guidance](https://google.github.io/eng-practices/review/developer/small-cls.html); [Graphite stacked-PR feature](https://graphite.com/docs/cli-quick-start). |
| Demonstrable task outcomes | [Matt Pocock's ticket instructions](https://github.com/mattpocock/skills/blob/main/skills/engineering/to-tickets/SKILL.md). |
| Focused, then broader checks | [Matt Pocock's implementation instructions](https://github.com/mattpocock/skills/blob/main/skills/engineering/implement/SKILL.md); [Google's testing account, 2020](https://abseil.io/resources/swe-book/html/ch23.html). |
| Independent review | [Google's review account, 2020](https://abseil.io/resources/swe-book/html/ch09.html); [Amp's separate-reviewer workflow, 2026](https://ampcode.com/news/liberating-code-review). |
| Ownership through repairs | [Poteto's pstack workflow](https://github.com/cursor/plugins/blob/main/pstack/skills/poteto-mode/playbooks/autopilot-full.md); [Cognition's Devin account, 2026](https://cognition.com/blog/how-cognition-uses-devin-to-build-devin). |
| Executable rules for recurring mistakes | [pstack's Correct instructions](https://github.com/cursor/plugins/blob/main/pstack/skills/correct/SKILL.md); [Factory's lint-gate account, 2025](https://factory.com/news/using-linters-to-direct-agents). |
| Required checks and reviews | [GitHub ruleset capabilities](https://docs.github.com/en/repositories/configuring-branches-and-merges-in-your-repository/managing-rulesets/available-rules-for-rulesets); [OpenClaw's landing policy, with documented exceptions](https://github.com/openclaw/openclaw/blob/e12c0d2/.agents/skills/openclaw-pr-maintainer/references/landing.md). |
| Combined-candidate checks | [GitHub's shipping account, 2024](https://github.blog/engineering/engineering-principles/how-github-uses-merge-queue-to-ship-hundreds-of-changes-every-day/); [GitHub merge-queue capability](https://docs.github.com/en/repositories/configuring-branches-and-merges-in-your-repository/configuring-pull-request-merges/managing-a-merge-queue). |
| Working previews | [Linear's design-refresh account, 2026](https://linear.app/now/behind-the-latest-design-refresh); [Railway PR-environment capability](https://docs.railway.com/guides/preview-deployments-with-pr-environments). |
| Traceable releases, staged rollout and recovery | [Google's release-engineering account, 2016](https://sre.google/sre-book/release-engineering/); [Amazon's deployment and rollback account, 2020](https://aws.amazon.com/builders-library/automating-safe-hands-off-deployments/). |

## A practical starting sequence

This sequence is a synthesis of the examples above, rather than a claim that every source uses an identical process:

1. Describe one complete outcome and how to check it.
2. Assign a writer who stays responsible for review findings and failed checks.
3. Run focused checks while implementing, then the broader checks needed for the change.
4. Review the proposed behavior, using a preview when it helps.
5. Require the relevant checks and reviews, then test the combined merge candidate.
6. Release an identifiable artifact, observe the result and keep a recovery path.

## Subject pages

- [Working with coding agents](subjects/working-with-coding-agents.md)
- [Poteto and pstack](subjects/poteto-and-pstack.md)
- [Matt Pocock](subjects/matt-pocock.md)
- [OpenClaw and Crabbox](subjects/openclaw-and-crabbox.md)
- [Agent instructions and enforcement](subjects/agent-instructions.md)
- [Small changes and stacked reviews](subjects/small-changes.md)
- [GitHub](subjects/github.md)
- [Merge queues](subjects/merge-queues.md)
- [Railway](subjects/railway.md)
- [Linear](subjects/linear.md)
- [Agent tools and engineering teams](subjects/agent-tools.md)
- [OpenAI and Anthropic](subjects/ai-labs.md)
- [Amazon, Microsoft, Netflix and Stripe](subjects/large-engineering-teams.md)
- [Google](subjects/google.md)
- [Meta, Uber and Shopify](subjects/meta-uber-shopify.md)

[SOURCES.md](SOURCES.md) lists every external source used, its publisher and the read date. Subject pages distinguish dated accounts from undated documentation. Historical descriptions retain their dates; they do not establish current company-wide policy. Original prose is licensed under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/); see [LICENSE](LICENSE).

To propose a practice or correction, see [CONTRIBUTING.md](CONTRIBUTING.md).
