# The Safety Envelope

The safety envelope is the set of rules an autopilot can never break, no matter what its workflow is or who created it. The rules are enforced in the executor and on the server, not in a prompt. They hold everywhere, always, and are not configurable per autopilot.

## In the user's own session

The autopilot acts in the user's browser tab, with the user's own auth and permissions, on the same origin as the workflow. No credentials or session tokens pass through Holostaff, and nothing runs headless or in the background: if the user closes the tab, the run is over.

## One small action at a time

An autopilot never fires a script of queued-up clicks. It takes a single step, reads what happened, and only then decides the next one. If the page changed or anything looks different from what it expected, it stops and reassesses.

## Every target is highlighted first

Before it clicks, types, or scrolls, the autopilot highlights the exact element it is about to act on. The user sees what is about to happen before it happens. Nothing is invisible, and nothing is surprising.

## Consequential clicks wait for Allow

Some clicks change things: paying, submitting, deleting, sending, signing. For those the autopilot pauses and shows an inline **Allow** pill next to the highlighted target. It proceeds only when the user clicks Allow. No answer means no; silence is never consent.

## Fields it will never touch

Password fields, payment fields, and verification codes are hard-refused. Not with permission, not at the user's request, never. The autopilot points; the user types.

## Questions wait beside their field

When the autopilot is unsure, it asks one short question in a card anchored next to the field it concerns, never a modal covering the form, and it waits for the answer.

## The user can take the wheel back at any moment

**Stop** is always on screen, and stopping is instant. Any keystroke from the user pauses the run automatically. Each autopilot also carries a hard step budget, so a run can never wander.

## Why it works this way

Handover only happens where there is trust. An autopilot that moves visibly, asks before anything consequential, and yields the moment the user moves earns that trust. One that grabs the mouse does not.

## Related

- [Workflow autopilots](../autopilots/index.md): what autopilots are and how a handover works.
- [Certification](rehearsal-evaluations.md): how every autopilot is tested before it meets a real user.
