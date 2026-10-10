# Contributing

- Submit one practice or correction per pull request. Keep it complete and reviewable, following [Google's guidance on self-contained changes](https://google.github.io/eng-practices/review/developer/small-cls.html).
- Put a public primary source beside every factual claim. Open the source and check that it supports the wording. Add new sources to [SOURCES.md](SOURCES.md), with publisher and read date.
- Attribute every quotation. Keep each quote to at most two sentences and keep quoted words from any one source within 25 words across the guide.
- Preserve the source's scope and date. Distinguish published team accounts, repository instructions and configurable platform features. Label synthesis explicitly.
- Include no private details, internal conversations, credentials or unpublished implementation details.
- Write original prose under the repository's [CC BY 4.0 license](LICENSE).

## Check links

The [weekly workflow](.github/workflows/link-check.yml) uses immutable commit pins for [checkout](https://raw.githubusercontent.com/actions/checkout/11bd71901bbe5b1630ceea73d27597364c9af683/action.yml) and [lychee-action](https://raw.githubusercontent.com/lycheeverse/lychee-action/7da8ec1fc4e01b5a12062ac6c589c10a4ce70d67/action.yml). It fails when the checker reports errors or finds no links.

To run the same scan from the repository root with [lychee v0.16.1](https://raw.githubusercontent.com/lycheeverse/lychee/lychee-v0.16.1/README.md) installed:

```sh
lychee --verbose --no-progress --max-concurrency 8 './**/*.md'
```

This checks local link targets and remote responses. It does not establish that a source supports its adjacent claim. Investigate failures before changing citations. Explain specific exceptions; do not accept failure statuses or skip whole hosts merely to make the check pass.
