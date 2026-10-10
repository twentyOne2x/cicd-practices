# Google

Sources read: 2026-10-10. The engineering book accounts date from 2020-03; the release engineering account is from 2016. Review guidance is undated.

Google's published review account describes independent review, code ownership and language readability requirements. One qualified person can cover several roles. [Software Engineering at Google: Code Review](https://abseil.io/resources/swe-book/html/ch09.html).

Its review guidance favors one self-contained concern with related tests and a working system after submission. Size examples leave room for reviewer judgment rather than establishing a universal numerical CI gate. [Small CLs](https://google.github.io/eng-practices/review/developer/small-cls.html).

The 2020 testing account describes fast selected tests before submission and longer affected tests after merge. Selection follows dependencies. It also describes assigning someone to repair broken builds and investigating flaky tests. This is a historical description of testing infrastructure. [Software Engineering at Google: Continuous Integration](https://abseil.io/resources/swe-book/html/ch23.html).

The release engineering account describes building a selected revision, running tests, packaging identifiable outputs and expanding limited production deployments according to risk. Submission and production release are separate decisions in that workflow. These accounts do not establish Google's complete current internal configuration. [Site Reliability Engineering: Release Engineering](https://sre.google/sre-book/release-engineering/).
