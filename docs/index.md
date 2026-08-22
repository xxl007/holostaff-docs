# Holostaff Documentation

Holostaff creates workflow autopilots for your product. An autopilot is a "Do it for me" button on a workflow: the user hands over the task, and the autopilot completes it on screen, in the user's own session. Autopilots are built and certified by synthetic users before any human meets them, and deployed with one pull request.

## What is a workflow autopilot?

Every product has workflows users dread: the long form, the bulk import, the multi-step setup. A workflow autopilot takes those over on request.

The user clicks the offer, watches the autopilot do the task step by step, answers a short question when the autopilot is unsure, and personally approves anything consequential. Sensitive fields are never typed by the autopilot.

Holostaff is not a chatbot. It never chats: it acts, and it shows its work on screen. It is not a product tour: a tour explains the task, an autopilot does it. And it is not autonomous: handover is always the user's explicit act.

## The lifecycle

| Stage | What happens |
|---|---|
| **[Map](journey-maps/index.md)** | One scan turns your repo into a journey map of your workflows. |
| **[Rehearse](evaluations/index.md)** | Synthetic users walk your real flows and show you what breaks. |
| **[Certify](how-it-works/rehearsal-evaluations.md)** | Suites gate every PR. An autopilot ships only while its workflow passes. |
| **[Deploy](deploy/index.md)** | The offer appears on the workflow. The user hands over. The autopilot does the task in their session. |
| **[Verify](impact/index.md)** | Every handover is logged, verified, and only then counted. |

## The product surfaces

* **Journey Maps.** The canvas your scan produces: every workflow, with risk and handover moments flagged.
* **Personas.** Your synthetic users: the AI people who rehearse your product before real users do.
* **Autopilots.** One per workflow. Their certification state, and the deploy toggle.
* **Environments.** The deployments your simulation runs point at.
* **Evaluations.** The coverage board: scenarios, runs, verdicts, and clips.
* **Impact.** What changed, attributed, with a live feed.

## Who is in control?

You are, and your user is.

* Autopilots are created by your team and certified by synthetic users on every build they ship to.
* Deployment goes through your normal pull request review.
* In the session, the autopilot runs with the user's own permissions. Consequential clicks need the user's Allow. Sensitive fields stay human-typed. Any keystroke pauses it, and Stop is always on screen.
* Every handover is logged. Everything is revocable.

## Quick links

* [Quickstart](getting-started/quickstart.md) — one command to put your product on the map
* [Journey Maps](journey-maps/index.md) — the canvas your scan produces
* [Autopilots](autopilots/index.md) — what they are and how they behave
* [Creating an autopilot](autopilots/create.md) — from workflow to certified to live
* [The safety envelope](how-it-works/guarded-actions.md) — the rules an autopilot can never break
* [Deploying](deploy/index.md) — the PR path and [the SDK](deploy/sdk.md)
* [Billing](billing/index.md) — two meters, nothing else
* [CLI reference](cli/index.md) — every command, CI mode, and what leaves your machine
