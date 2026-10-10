# Agent tools and engineering teams

Sources read: 2026-10-10. Product documentation is undated unless an account date is given.

Cursor's account dated 2026-02-24 describes cloud agents testing running applications and returning PRs with evidence; developers decide what ships. Bugbot's default neutral result does not enforce resolution of findings merely because its check is required. [Cursor engineering account](https://cursor.com/blog/agent-computer-use), [Bugbot documentation](https://cursor.com/docs/bugbot).

Cognition's account dated 2026-02-27 describes requesting work through chat or tickets and having Devin repair review findings and CI failures. It does not establish compulsory internal merge or release gates. [How Cognition uses Devin to build Devin](https://cognition.com/blog/how-cognition-uses-devin-to-build-devin).

Factory's account dated 2025-09-05 says recurring mistakes become executable rules and passing them is a merge gate. Its review documentation separately describes reviewing PR updates and approving when no findings remain. [Using linters to direct agents](https://factory.com/news/using-linters-to-direct-agents), [Code review CI](https://docs.factory.com/software-factory/code-review-ci).

Amp's article dated 2026-02-04 describes separate reviewers and scoped checks that can return findings for repair. This is callable review. [Liberating code review](https://ampcode.com/news/liberating-code-review).

Graphite's 2025-06-02 queue account describes testing combined stacks and removing failed changes and dependents. Its 2025-05-27 release account describes staging and automatic promotion based on health and performance checks. [Stack-aware merge queue](https://graphite.com/blog/the-first-stack-aware-merge-queue), [Monorepo release account](https://graphite.com/blog/how-we-organize-our-monorepo-to-ship-fast).

CodeRabbit's optional approval workflow checks the latest reviewed commit and required conditions, with documented override commands. Configuration determines enforcement. [Request changes workflow](https://docs.coderabbit.ai/pr-reviews/request-changes-workflow).
