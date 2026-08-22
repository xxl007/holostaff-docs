# Creating an Autopilot

Every workflow on your journey map is an autopilot candidate. The **Autopilots** page lists them per scanned product, each with its certification state and deploy toggle.

## From workflow to live

1. **Pick the workflow.** Open **Autopilots** and find the workflow worth taking over: the long form, the setup flow, the task users abandon. The scan already mapped its steps.
2. **Certify.** Click **Certify**. One run covers both levels: synthetic users first complete the workflow themselves (Level 1), then hand it to the autopilot under test (Level 2). Runs land on the [Evaluations board](../evaluations/index.md) with clips.
3. **Go live.** A certified workflow shows the **Autopilot certified** badge and its deploy toggle becomes real. Toggle on to start offering; toggle off to stop new offers instantly.

!!! note "Certification is the gate"
    The toggle only works on a workflow whose autopilot passed both levels on the current build. A failing suite takes the offer down with the next deploy. See [Certification](../how-it-works/rehearsal-evaluations.md).

## Naming

The offer carries the task name by default: users hand a task to "New expense claim", not to a character. If your product prefers a branded name, set a display name on the autopilot; it appears on the offer card, the intent overlay, and the progress panel.

## What the autopilot needs from you

Very little. The workflow's steps come from the scan. The intent form (the few fields collected at handover) is derived from the workflow and editable. The safety rules are [not configurable per autopilot](../how-it-works/guarded-actions.md): they hold everywhere, always.

## Wiring into your app

The offer only renders where the SDK runs. That integration ships once, [through a pull request](../deploy/index.md): the SDK, the init call, and stage markers. After that PR merges, going live is the toggle, and every later change is certification-gated, not code-gated.
