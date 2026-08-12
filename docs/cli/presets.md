# Preset Journey Maps

A preset is a published journey map for an open source product. Importing one
gives you that product's map in your own workspace in about a second. No scan
runs, no model spend, and nothing reads your code.

```bash
npx @holostaff/cli import opnform
```

Sign-in happens in the same command if you are not already signed in. The map
lands as a new source in your workspace: your copy, yours to edit on the
canvas.

Run `npx @holostaff/cli import` with no name to list every available preset.

Under the hood `import` is sugar for `scan --from`, which also accepts an
`https` URL or a local file path. The file is a plain scan artifact, either
bare or wrapped in `{ "artifact": ... }`, so you can also export a map from
your own workspace and hand it to a colleague.

## When to use a preset

Use a preset when you self-host a product that already has one. The scan of
public code produces the same map for everyone, so there is no reason to spend
ten minutes re-deriving it.

Run a normal `holostaff scan` instead when the code is yours, or when you have
forked the product heavily enough that the public map no longer matches it.

## Available presets

Presets live in the CLI repository under
[`presets/`](https://github.com/Holostaff-AI/holostaff-cli/tree/master/presets).

| Preset | Product |
|---|---|
| `opnform.json` | [OpnForm](https://github.com/OpnForm/OpnForm), open source form builder |
| `formbricks.json` | [Formbricks](https://github.com/formbricks/formbricks), open source survey platform |
| `atlas-cmms.json` | [Atlas CMMS](https://github.com/Grashjs/cmms), open source maintenance management |

## Example: your self-hosted OpnForm

OpnForm ships with an optional Holostaff plugin that stays off until two
environment variables are set. To turn it on for your install:

1. Import the preset with the command above.
2. Open the map it prints, and copy the two ids from the dashboard: the
   workspace id and the source id.
3. Set them in `client/.env` and rebuild:

```bash
NUXT_PUBLIC_HOLOSTAFF_TENANT_ID=your_workspace_id
NUXT_PUBLIC_HOLOSTAFF_SOURCE_ID=your_source_id
```

Nothing changes for your form respondents. The copilot only appears for the
people building forms, never inside published forms or embeds.

## Provenance

An imported map is recorded as `cli_preset`, not `cli_scan`. Your map shows
that nobody scanned your code, because nobody did.
