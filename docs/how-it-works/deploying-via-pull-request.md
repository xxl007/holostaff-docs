# Deploying via Pull Request

Holostaff ships into your product like code, not like a widget pasted from a dashboard. `/embed` and `holostaff deploy` produce a branch and a pull request in your own repository, your engineers review the diff, and merging is what takes it live. Nothing lands on its own.

## What the pull request contains

The PR is ordinary, readable code:

- **SDK init**: the Holostaff SDK initialized in your app.
- **Journey stage markers**: small markers that tell the SDK where the user is on the journey map.
- **The embed**: the script tag that loads the copilot into your app.

That is the whole footprint. There is no hidden injection, no tag manager side door, and no change that does not appear in the diff.

## Engineers review the diff

The change goes through the same review your team applies to any other code. If a reviewer does not like where a marker sits or how the init is wired, they comment, and the change is fixed before it ships. Your codebase's standards apply, because the change lives in your codebase.

## Merging is going live

There is no separate publish button that bypasses your process. When the PR merges and your normal deploy pipeline runs, the copilot is live. Your existing release process is the release process.

## Reverting is rollback

Rollback is `git revert`. Because the whole integration is code in your repository, removing it is one revert commit away, reviewable and auditable like everything else. No support ticket, no dashboard hunt, no orphaned snippet left behind.

## Why this matters

Widgets installed by pasting a snippet live outside your engineering process: unreviewed, unversioned, and hard to remove. A pull request puts the integration inside the process you already trust. Everyone who can read a diff can see exactly what Holostaff adds to your product, before it is added.

## Related

- [The Deploy Flow](../deploy/index.md): the step-by-step deploy walkthrough.
- [The SDK](../deploy/sdk.md): what the SDK does once it is initialized.
- [What Leaves Your Machine](what-leaves-your-machine.md): what the scan sends, and what it never sends.
