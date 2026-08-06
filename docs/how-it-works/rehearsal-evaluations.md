# Rehearsal Evaluations

Rehearsal evaluations are how Holostaff tests a copilot before it ever meets a real user. Simulated users run your product's real flows in real browsers, the copilot has to notice and intervene, and every run is graded. A copilot that fails rehearsal does not go live.

## Real flows, real browsers

A rehearsal is not a unit test or a mocked conversation. A simulated user is an AI visitor driving a real browser session against your actual product. It signs up, fills forms, hesitates, gets stuck, and abandons, the way real users do. Your copilot runs for real during the session and has to do its job: spot the struggle and step in.

## Scenarios come from your journey map

You do not write test cases. Every workflow and risk moment on your journey map becomes a scenario: complete the flow and reach the outcome, hesitate at the sensitive step, quietly give up mid-form. The map your scan produced already knows where users can struggle, so it already knows what to rehearse.

## Every run is graded

Each run gets a verdict with a reason:

- **Pass**: the intervention fired at the right moment and the simulated user reached the outcome.
- **Fail**: with the reason recorded. A fail can be the copilot's fault, or it can be a product finding, because sometimes the simulated user hits a real bug. Both are worth knowing before launch.
- **Needs setup**: the scenario needs one-time data, like a seeded test account.

You can watch any run: the session timeline, the live browser, the verdict, and the reasoning behind it.

## Failing rehearsal blocks going live

This is the point of the whole system. Rehearsal is the gate, not a report. A copilot that cannot pass its scenarios has no business meeting your users, so it does not. Fix the persona, the intervention, or the product bug the rehearsal surfaced, re-run, and go live when it passes.

## When rehearsals run

- After hiring a copilot, before its first deploy.
- After a re-scan changes the workflows in its stage.
- After editing identity or persona, since tone changes behavior.
- Before go-live, as the final gate.

## Related

- [Evaluations in the dashboard](../evaluations/index.md): the coverage board, run details, and verdicts.
- [Guarded Actions](guarded-actions.md): the rules a copilot follows once it is live.
