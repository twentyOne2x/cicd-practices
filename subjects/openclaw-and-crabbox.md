# OpenClaw and Crabbox

Sources read: 2026-10-10. OpenClaw links identify a repository snapshot; the Crabbox documentation is undated.

OpenClaw's landing procedure uses `scripts/pr` to review, prepare and submit a commit-bound squash or auto-merge request. Ordinary landing waits for required checks and reviews. The policy also documents limited exceptions, so it does not promise that main is always green. [Landing procedure](https://github.com/openclaw/openclaw/blob/e12c0d2/.agents/skills/openclaw-pr-maintainer/references/landing.md).

Its CI instructions select PR checks according to the change, leaving some broader checks to hourly main CI or release validation. Its release policy normally uses beta before stable publication and binds source, validation and publishing identities. These are separate documented verification stages. [CI instructions](https://github.com/openclaw/openclaw/blob/e12c0d2/.agents/skills/openclaw-ci-limits/SKILL.md), [Release policy](https://github.com/openclaw/openclaw/blob/e12c0d2/docs/reference/RELEASING.md).

Crabbox is a separate execution tool. Its `run` documentation describes obtaining a box, copying working files, running a command, streaming output and returning the exit status. Separate boxes support independent runs. [Run documentation](https://crabbox.sh/commands/run.html).

Default synchronization includes uncommitted edits and excludes `.git`. A successful command therefore does not, by itself, establish the tested commit. That distinction follows from the documented copying behavior. [Synchronization documentation](https://crabbox.sh/features/sync.html).
