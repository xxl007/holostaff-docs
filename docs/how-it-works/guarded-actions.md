# Guarded Actions

Guarded actions are how a Holostaff copilot acts on a user's screen without ever taking it over. The copilot performs one small action at a time, highlights every target before anything happens, and waits for explicit permission before any click that has consequences. The user stays in control at every moment.

## One small action at a time

A copilot never runs a long script against your interface. It takes a single step, watches what happened, and only then decides on the next one. If the page changed, if the user moved, or if anything looks different from what it expected, it stops and reassesses. There is no batch of queued-up clicks waiting to fire.

## Every target is highlighted first

Before the copilot clicks, types, or scrolls, it highlights the exact element it is about to act on. The user sees what is about to happen before it happens. Nothing is invisible, and nothing is surprising.

## Consequential clicks wait for Allow

Some clicks change things: paying, submitting, deleting, confirming. For any consequential action, the copilot pauses and shows an inline **Allow** button next to the highlighted target. It proceeds only when the user presses Allow.

No answer means no. If the user does not respond, the copilot does not act. Silence is never treated as consent.

## Fields it will never touch

A copilot never types into password fields or payment fields. Not with permission, not at the user's request, never. Credentials and card details are the user's alone to enter.

## The user can stop it at any moment

At any point, mid-step or mid-flow, the user can stop the copilot. Stopping is instant: the copilot halts, releases the page, and the user carries on by themselves.

## Why it works this way

Interventions only help if users trust them. A copilot that moves slowly, shows its work, and asks before anything consequential earns that trust. One that grabs the mouse does not.

## Related

- [Your AI Staff](../copilots/index.md): what copilots are and how they decide to step in.
- [Rehearsal Evaluations](rehearsal-evaluations.md): how every copilot is tested before it meets a real user.
