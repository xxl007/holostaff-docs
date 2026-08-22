# Workflow Autopilots

An autopilot owns one workflow of your product. When a user enters that workflow, a small offer appears: hand the task over, and the autopilot completes it for them.

## How a handover works

1. **The offer.** The user enters an enabled workflow and sees the offer card. Nothing happens unless they accept: handover is always the user's explicit act.
2. **The intent form.** A compact overlay collects the few specifics the task needs. Anything the autopilot should not know, it does not ask for.
3. **The work.** The autopilot acts in the user's own browser session, one small step at a time, on screen. Every target is highlighted before anything happens.
4. **Questions.** When the autopilot is unsure, it asks one short question in a card placed beside the field it concerns, and waits.
5. **The gates.** Consequential clicks (pay, delete, submit, send, sign) pause for the user's own click on an inline **Allow** pill. Sensitive fields (passwords, payment, codes) are hard-refused: the autopilot points, the user types.
6. **Done.** The autopilot reports what it did. The user was watching the whole time; **Stop** never left the screen, and any keystroke of theirs pauses the run.

The autopilot runs client-side, with the user's own auth and permissions. No credentials or session tokens ever pass through Holostaff.

## Identity

Autopilots have no face and no persona. The offer carries the name of the task ("New expense claim"), because the task is the promise. A custom display name can be set per autopilot if your product prefers one.

## Certification

No autopilot meets a human before it has served synthetic users, on every build it ships to. Deployment requires both levels:

- **Level 1 — the workflow works.** Synthetic users complete the workflow themselves on your deployment.
- **Level 2 — the handover works.** Synthetic users hand the task to the autopilot and it completes it.

Certification state lives on the [Autopilots page](create.md), and [suites gate every PR](../how-it-works/rehearsal-evaluations.md).

## The deploy toggle

Once certified, an autopilot goes live with its deploy toggle. Turning it off stops new offers immediately; a handover already in flight finishes. Deployment into your app itself happens once, [through a pull request](../deploy/index.md).

## Next

- [Creating an autopilot](create.md)
- [The safety envelope](../how-it-works/guarded-actions.md)
- [Certification](../how-it-works/rehearsal-evaluations.md)
