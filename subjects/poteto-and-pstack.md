# Poteto and pstack

Sources read: 2026-10-10. The playbooks are living repository documents; the public PR example below is dated 2026-10-06.

Poteto's full-autopilot playbook assigns independent changes to cloud agents, with one owner carrying each pull request through building, checks, repairs and merging. Once implementation is ready, verification, CI and independent reviews run together. These are published workflow instructions. [Full autopilot playbook](https://github.com/cursor/plugins/blob/main/pstack/skills/poteto-mode/playbooks/autopilot-full.md).

The verification guide calls for repeatable setup, checks against the real command or application, retained evidence and cleanup. The babysitting playbook keeps the PR owner responsible for checking findings and batching repairs. [Verify and ship](https://github.com/cursor/plugins/blob/main/pstack/docs/guide/06-verify-and-ship.md), [Babysit](https://github.com/cursor/plugins/blob/main/pstack/skills/poteto-mode/playbooks/babysit.md).

Independent changes land separately. Dependent stacks land from the bottom, with renewed verification when the code changes. [Shipping playbook](https://github.com/cursor/plugins/blob/main/pstack/skills/poteto-mode/playbooks/shipping.md).

Public PR 511, dated 2026-10-06 in the source record, shows Cursor agent commits and a merge by poteto. That is evidence of a particular public contribution. The playbooks and this example do not establish a universal production procedure, installed protections or delivery performance. [PR 511](https://github.com/cursor/plugins/pull/511).
