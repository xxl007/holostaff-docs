# Quickstart

The terminal is the front door. One command scans your codebase and puts your product's journey map on a live canvas. From there you create autopilots on your workflows, certify them with synthetic users, and ship them through a pull request.

## 1. Run the CLI

In the repository of the app:

```bash
npx @holostaff/cli
```

Requires Node 20+. The CLI signs you in with a device flow: your browser opens, you confirm, and the terminal continues. New here? The same flow creates your account and workspace.

## 2. Scan

```
> /scan
```

The scan agent reads your code the way an engineer would: routes, components, workflows, and the copy your users actually see.

![The CLI scanning a project](../assets/images/app/terminal-scan.png)

The scan runs in two phases:

1. **Skeleton.** The structure of your journey map (routes, components, workflows with stages) is published the moment it is coherent. Your map is live in about 90 seconds.
2. **Deep pass.** The agent keeps working: risk moments, handover candidates, signals, copy strings, brand voice. The finished artifact lands as a second version while you explore the map.

Before anything uploads, a trust report shows exactly what will be sent. Your source code stays on your machine; only the structured artifact goes up. See [what leaves your machine](../cli/index.md#what-stays-on-your-machine).

## 3. Open your map

When the skeleton lands, the CLI prints your workspace URL. From there the path is the lifecycle:

1. **[Explore the Journey Map](../journey-maps/index.md).** Every workflow the scan found, with risks flagged.
2. **[Meet your synthetic users](../evaluations/index.md).** Personas drafted from your scan; they will rehearse everything.
3. **[Create an autopilot](../autopilots/create.md).** Pick the workflow users dread and click Certify.
4. **[Deploy through a PR](../deploy/index.md).** `npx @holostaff/cli deploy` opens a pull request your engineers review.
5. **[Verify](../impact/index.md).** Watch handovers land, each one logged and counted only when complete.

!!! tip "A scan is not a deploy"
    Scanning makes your **map** live in the dashboard. Nothing changes in your product until the deploy PR merges and a certified autopilot's toggle is on.
