# Amazon, Microsoft, Netflix and Stripe

Sources read: 2026-10-10. Each account describes a particular system and period.

Amazon's deployment account dated 2020-06-18 requires another team member's review before merge. Its pipeline then builds, tests, signs packages and deploys progressively. Alarms halt rollout and restore the previous version. This is the documented design, rather than confirmed current universal settings. [Automating safe, hands-off deployments](https://aws.amazon.com/builders-library/automating-safe-hands-off-deployments/).

Microsoft's account, updated 2022-11-28, describes PR checks and colleague approval, broader testing after merge, and progressive shipping from a release branch while main stays open. The account describes selected engineering systems. [How Microsoft develops DevOps](https://learn.microsoft.com/en-us/devops/develop/how-microsoft-develops-devops).

Stripe's coding-agent account dated 2026-02-19 describes isolated, prepared environments, quick local checks and at most two CI rounds before returning the branch to a person. Humans review the proposed code. This is a reported agent workflow. [Minions: Stripe's one-shot, end-to-end coding agents, Part 2](https://stripe.dev/blog/minions-stripes-one-shot-end-to-end-coding-agents-part-2).

Netflix's account dated 2025-12-16 takes built images through smoke tests, limited production trials and regional stages. It describes saved execution state and safe retries in rollout orchestration. It does not establish a company-wide code-authoring or review policy. [How Temporal powers reliable cloud operations at Netflix](https://netflixtechblog.com/how-temporal-powers-reliable-cloud-operations-at-netflix-73c69ccb5953).
