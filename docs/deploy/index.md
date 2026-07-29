# Deploying

Nothing reaches your users without going through your own code review. Deployment is a pull request, opened by the Holostaff GitHub App, reviewed and merged by your engineers.

## Connect GitHub (one time)

Install the Holostaff GitHub App on your organization from **Integrations → GitHub** in the dashboard. The app's only job is opening deploy PRs on the repositories you allow.

![The GitHub integration page](../assets/images/app/integrations-github.png)

## Run the deploy

From your repo:

```bash
npx @holostaff/cli deploy
```

The CLI:

1. Checks what's pending for this source: a new scan, edited assignments, or nothing.
2. Detects the target `owner/repo` from your git remote.
3. Registers the deploy and asks the server to open the PR.
4. Prints the PR URL.

Use `--dry-run` to see the plan without touching anything, and `--force` to push onto an open deploy non-interactively.

## The PR

The PR is small and readable: the SDK dependency, the `init` call, stage markers at journey boundaries, and the embed for the copilot presence. Your team reviews it like any change.

![A deploy pull request](../assets/images/app/deploy-pr.png)

Merging the PR makes the version live. The copilot's status flips to published, and from that moment its interventions and outcomes stream into [Impact](../impact/index.md).

## Rolling back

Everything is revocable:

- **Pause a copilot** from the roster: it stays deployed but stops intervening.
- **Revert the PR** to remove the integration entirely.

## Troubleshooting

| Error | Meaning | Fix |
|---|---|---|
| `no_repo` | No GitHub remote found | Run from a repo with an `origin` remote |
| `no-installation-for-repo` | GitHub App not installed for this org | Install it from Integrations → GitHub |
| An open deploy exists | A previous deploy PR is still open | Choose force-push, wait, or cancel at the prompt |
