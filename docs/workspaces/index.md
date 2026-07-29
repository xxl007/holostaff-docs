# Workspaces & Collaboration

A workspace is where a team runs its staffed products. It holds your journey maps, copilots, evaluation results, impact data, and the teammates who work on them.

Every account starts with one workspace. Create more when you need real separation: different brands, different clients, or products whose data should not mix.

## What lives in a workspace

- **Journey Maps** — every product scanned into this workspace, each with its canvas
- **Copilots** — the staff roster, shared across the workspace's products
- **Evaluations and Impact** — rehearsal results and attribution, per product
- **Team members** — collaborators with roles and permissions
- **CLI keys** — workspace-scoped API keys for CI ([reference](../cli/index.md#ci-keys))

The CLI is bound to a workspace too: `npx @holostaff/cli workspace` shows which one your scans land in.

## Creating a workspace

1. Open **Settings → Workspace**.
2. Click **Create New Workspace**.
3. Name it, optionally invite a first teammate by email, and confirm.

Switch between workspaces from the same tab. Your active workspace decides which maps, copilots, and data you see.

## When to create another workspace

- **Agencies and consultancies** — one workspace per client keeps maps, copilots, and billing separate.
- **Multiple brands** — separate brand voice, separate rosters.

One product with several repositories does not need several workspaces: merge repos into one source with `/scan --add-repo`.

## Managing team access

Invite teammates and assign roles from **Settings → Workspace**. See [Team Management](team-management.md) for roles and permissions.

!!! warning "Deleting a workspace"
    Deleting a workspace is permanent. It removes its journey maps, copilots, evaluation history, and member access.
