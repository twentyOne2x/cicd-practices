# GitHub

Sources read: 2026-10-10. Documentation is undated unless a dated account is identified below.

GitHub documents a coding agent that edits, tests and opens a pull request. It cannot approve or merge its own PR; human review remains required. Administrators can enable automatic Actions runs for agent PRs under the change announced 2026-03-13. Human workflow approval is the default. [Agent safeguards](https://docs.github.com/en/copilot/concepts/security-governance-and-network-settings/risks-and-mitigations), [Actions approval change](https://github.blog/changelog/2026-03-13-optionally-skip-approval-for-copilot-coding-agent-actions-workflows/).

GitHub recommends focused PRs that explain the change and its testing. Code owners receive review requests automatically, but their approval blocks merging only when configured as a requirement. Rulesets can require checks and identify the app permitted to report them. These are configurable capabilities. [Review guidance](https://docs.github.com/en/pull-requests/concepts/helping-others-review-your-changes), [About code owners](https://docs.github.com/en/repositories/managing-your-repositorys-settings-and-features/customizing-your-repository/about-code-owners), [Available rules for rulesets](https://docs.github.com/en/repositories/configuring-branches-and-merges-in-your-repository/managing-rulesets/available-rules-for-rulesets).

Merge queue checks the combination of current main and queued changes. Actions workflows need the `merge_group` trigger. Increasing merge limits groups completed merges without combining CI builds. [Managing a merge queue](https://docs.github.com/en/repositories/configuring-branches-and-merges-in-your-repository/configuring-pull-request-merges/managing-a-merge-queue).

GitHub's internal shipping account, published 2024-03-06, describes checking and deploying combined changes before merge. That historical account does not establish its complete 2026 policy. [How GitHub uses merge queue to ship hundreds of changes every day](https://github.blog/engineering/engineering-principles/how-github-uses-merge-queue-to-ship-hundreds-of-changes-every-day/).
