# Preset Journey Maps

A preset is a published journey map for an open source product. Importing one
gives you that product's map in your own workspace in about a second. No scan
runs, no model spend, and nothing reads your code.

```bash
npx @holostaff/cli import atlas-cmms
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
| `atlas-cmms.json` | [Atlas CMMS](https://github.com/Grashjs/cmms), open source maintenance management |
| `formbricks.json` | [Formbricks](https://github.com/formbricks/formbricks), open source survey platform |
| `opnform.json` | [OpnForm](https://github.com/OpnForm/OpnForm), open source form builder |

Want a preset for a product you self-host? Any checkout can be scanned, and a
map exported from your workspace works as a preset file for your whole team.

## From map to copilot

The preset gives you the map. To put the copilot in front of your users, the
product's frontend also needs the Holostaff SDK plugin, and there are two
ways to get it:

1. **The product already ships the plugin.** Some products include an
   optional, off-by-default Holostaff plugin. There, enabling the copilot is
   two environment variables on your install, the workspace id and source id
   shown on your imported map, set wherever that product documents them.
2. **Add it with the CLI.** In any checkout, `holostaff deploy` wires the
   same env-gated, off-by-default plugin into the frontend and opens a pull
   request against your repository, so you review every line before anything
   ships.

Either way the plugin loads only for signed-in users of the product itself.
Public surfaces such as published forms, surveys, or request portals never
load it.

## Provenance

An imported map is recorded as `cli_preset`, not `cli_scan`. Your map shows
that nobody scanned your code, because nobody did.
