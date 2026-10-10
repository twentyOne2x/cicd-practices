# Small changes and stacked reviews

Sources read: 2026-10-10. The cited guidance and tool documentation are undated living documents.

Google's review guidance says: "In general, the right size for a CL is one self-contained change." A CL is a changelist, or proposed code change. The guidance includes related tests and requires the system to keep working after each part lands. Its numerical examples remain subject to reviewer judgment. [Google: Small CLs](https://google.github.io/eng-practices/review/developer/small-cls.html).

Danger's published example warns when additions plus deletions exceed 600 lines. A warning does not block merging; its `fail()` mechanism can report a failure. Requiring that result is a separate repository setting. Codely's PR size labeler likewise exposes configurable exclusions and blocking, with `fail_if_xl` defaulting to `false`. [Danger JS](https://danger.systems/js/), [PR size labeler](https://github.com/CodelyTV/pr-size-labeler).

Graphite documents parent-linked PRs so later work can progress while earlier parts receive CI and review. This supports decomposition without establishing a default blocking size limit. [CLI quick start](https://graphite.com/docs/cli-quick-start).

These examples distinguish scope, size feedback and admission. A complete, reviewable concern is a design choice. A size warning is feedback. A failing required check is an enforced merge condition. [Google: Small CLs](https://google.github.io/eng-practices/review/developer/small-cls.html), [Danger JS](https://danger.systems/js/), [GitHub: protected branches](https://docs.github.com/en/repositories/configuring-branches-and-merges-in-your-repository/managing-protected-branches/about-protected-branches).
