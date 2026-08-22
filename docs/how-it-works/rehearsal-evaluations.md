# Certification

Certification is the rule that no autopilot meets a human before it has served synthetic users, on every build it ships to. It is a gate, not a report.

## Two levels, both required

A workflow's autopilot is deployable only when both levels pass on the current build:

- **Level 1 — the workflow works.** Synthetic users complete the workflow themselves against your deployment. If real users could not get through it unaided, that is worth knowing before an autopilot is offered on it.
- **Level 2 — the handover works.** Synthetic users hand the task over and the autopilot completes it: offer, intent form, steps, questions, Allow gates, done.

One **Certify** click on the [Autopilots page](../autopilots/create.md) runs both.

## On every PR

Certification is continuous. Wire the suite into CI and every pull request gets its runs; the PR comment reads **workflow certified (n/n runs)** when the suite passes. Green means the autopilots on that build are certified; a failing suite takes the offer down rather than shipping a broken handover.

```bash
holostaff scan --quiet --json --out artifact.json   # CI-friendly scan
```

CI runs use [workspace API keys](../cli/index.md#ci-keys) and count as 1 unit each on the [simulation-runs meter](../billing/index.md); runs in Holostaff's cloud count as 3.

## Failing certification blocks going live

A workflow that cannot pass its scenarios has no business carrying an offer, so it does not. Fix the flow, the autopilot's intent form, or the product bug the run surfaced, re-run, and go live when it passes.

## When certification re-runs

- Before an autopilot's first deploy.
- On every PR, from CI.
- After a re-scan changes a workflow's steps.

## Related

- [Evaluations in the dashboard](../evaluations/index.md): personas, environments, the board, runs, and clips.
- [The safety envelope](guarded-actions.md): the rules an autopilot follows once it is live.
