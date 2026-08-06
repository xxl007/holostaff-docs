# What Leaves Your Machine

When the Holostaff CLI scans your repository, your source code stays on your machine. `/scan` reads your source with read-only tools, and before anything uploads, a trust report shows you exactly what is about to be sent. You see the full inventory first, and only the artifact described below ever leaves.

## What the artifact contains

The uploaded artifact contains only:

- **Product identity**: name, one-line description, framework, language.
- **Routes**: paths and descriptions, and component names with roles.
- **Customer-facing copy strings**: the literal text users see, with locations.
- **Brand voice**: tone and keywords.
- **Workflows** and their steps.
- **Coverage gaps** the scan flagged.

That is the complete list. It is what Holostaff needs to build your journey map and give your copilots their working knowledge of the product, and nothing more.

## What never leaves

Your source code, file contents beyond the excerpted UI strings, `.env` files, secrets, and git history never leave your machine.

The scan does not upload your repository, does not send file bodies, and does not read credentials. The only literal text taken from your code is the customer-facing copy your users already see on screen.

## The trust report

Before upload, the CLI prints a trust report: the exact artifact it is about to send, itemized. Nothing uploads until you have had the chance to read it. If something in the report should not be there, you stop the upload and nothing is sent.

## Verify it yourself

The CLI is a package you can read, and the artifact is inspectable before it uploads. You do not have to take this page's word for it: run `/scan`, read the trust report, and see the boundary hold.

## Related

- [Commands & CI](../cli/index.md): the full CLI reference.
- [Deploying via Pull Request](deploying-via-pull-request.md): how the integration itself ships as reviewable code.
- [Data Deletion Policy](../support/data-deletion.md): removing your data from Holostaff.
