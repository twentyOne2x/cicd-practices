# Meta, Uber and Shopify

Sources read: 2026-10-10. Dates identify the published engineering accounts.

Meta's Sapling account dated 2022-11-15 describes sending an early small change for review while building later parts above it. Sapling updates dependent changes when an earlier part changes. The review-policy account dated 2022-11-16 states that every change must be reviewed. [Sapling: source control that's user-friendly and scalable](https://engineering.fb.com/2022/11/15/open-source/sapling-source-control-scalable/), [Improving code review time at Meta](https://engineering.fb.com/2022/11/16/culture/meta-code-review-time-improving/).

Meta's article dated 2026-02-11 describes generating tests for changes, introducing deliberate faults and filtering findings before reporting bugs. This documents an AI testing approach without establishing removal of independent review. [Agentic development and JIT testing](https://engineering.fb.com/2026/02/11/developer-tools/the-death-of-traditional-testing-agentic-development-jit-testing-revival/).

Uber's account dated 2025-06-23 describes SubmitQueue testing possible future combinations of pending changes with main, then automatically landing qualifying changes. [Slashing CI costs at Uber](https://www.uber.com/us/en/blog/slashing-ci-costs-at-uber/).

Shopify's Shipit v2 account dated 2019-11-14 describes approved, passing PRs combined on a possible future main, checked together and then merged. This is a historical configuration, rather than confirmed current settings. [Successfully merging the work of 1,000 developers](https://shopify.engineering/successfully-merging-work-1000-developers).
