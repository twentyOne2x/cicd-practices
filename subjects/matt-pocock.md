# Matt Pocock

Sources read: 2026-10-10. The ticket and implementation skills are undated living documents. The testing skill snapshot is dated 2026-10-07; the review guide was updated 2026-08-24.

Matt Pocock's ticket skill turns an agreed plan into small, independently demonstrable behaviors, with dependencies named. The ticket skill says: "A completed slice is demoable or verifiable on its own." The implementation skill directs frequent type checks and individual test files, then "the full test suite once at the end", review and commit. [Ticket skill](https://github.com/mattpocock/skills/blob/main/skills/engineering/to-tickets/SKILL.md), [Implementation skill](https://github.com/mattpocock/skills/blob/main/skills/engineering/implement/SKILL.md).

The testing skill describes one failing test at an agreed public interface, enough implementation to pass it, and repetition. Expected results come from the specification or a known example. This is published testing policy. [Testing skill](https://github.com/mattpocock/skills/blob/3f599139104dfceabc7754eeb91319802f85e042/skills/engineering/tdd/SKILL.md).

The implementation and review documents have a coverage mismatch: implementation invokes review before committing, while review examines committed changes through `HEAD`. Pending changes can therefore fall outside that review. This describes the documented ordering, rather than a measured failure rate. [Implementation skill](https://github.com/mattpocock/skills/blob/main/skills/engineering/implement/SKILL.md), [Code review guide](https://www.aihero.dev/skills-code-review).

The public AI Hero CLI runs type checks, lint and tests on PRs and main. Its separate publishing workflow uses Changesets. These snapshots, dated 2025-11-04 and 2025-11-19 respectively, show configuration without establishing required-check settings. [CI workflow](https://github.com/mattpocock/ai-hero-cli/blob/d71d2bccad3d2474bd6e2a893f6834563305459a/.github/workflows/ci.yml), [Publishing workflow](https://github.com/mattpocock/ai-hero-cli/blob/6fafceba3a2a32a0c8dd82e9ba68624681c93e3c/.github/workflows/publish.yml).
