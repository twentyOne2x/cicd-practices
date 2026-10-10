# Merge queues

Sources read: 2026-10-10. Vendor documentation is undated; the Rust migration account is dated 2026-01-13.

GitHub's queue validates changes together with the target branch and preceding queued PRs. Failed entries leave, and affected combinations are rebuilt. Its documentation states: "Merge limits do not combine `merge_group` builds." That setting controls completed merges rather than grouping their CI work. [Managing a merge queue](https://docs.github.com/en/repositories/configuring-branches-and-merges-in-your-repository/configuring-pull-request-merges/managing-a-merge-queue).

Mergify documents temporary batch PRs, ordered checks of later combinations and splitting failed batches to isolate failures. Aviator also documents combined batch checks and failure splitting. These are product capabilities; illustrative build counts are not measured customer savings. [Mergify queue modes](https://docs.mergify.com/merge-queue/queue-modes/), [Mergify batches](https://docs.mergify.com/merge-queue/batches/), [Aviator batching](https://docs.aviator.co/mergequeue/concepts/batching).

Trunk checks predicted combinations, retains healthy followers when an earlier change fails, and checks them again without that change. It also documents batching compatible changes and separating unrelated work. [Predictive testing](https://docs.trunk.io/merge-queue/optimizations/predictive-testing), [Queue optimizations](https://docs.trunk.io/merge-queue/optimizations).

Bors-NG checked combined changes on staging before advancing main and was archived in April 2024. Rust's 2026 migration concerns a different bot that checks one combined PR/main commit at a time. Legacy automatic batching should not be attributed to that implementation. [Bors-NG](https://github.com/bors-ng/bors-ng), [Rust migration report](https://blog.rust-lang.org/inside-rust/2026/01/13/infrastructure-team-q4-2025-recap-and-q1-2026-plan/), [Bors design](https://github.com/rust-lang/bors/blob/main/docs/design.md).
