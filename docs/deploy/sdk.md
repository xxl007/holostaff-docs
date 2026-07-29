# The SDK

`@holostaff/sdk` is the small client the deploy PR adds to your app. It carries identity, stage detection, custom signals, and the copilot presence layer. You rarely write this code yourself: the PR places it, and this page explains what you're reviewing.

```bash
npm install @holostaff/sdk
```

## What the PR adds

```ts
import { holostaff } from '@holostaff/sdk'

// Once at app startup.
holostaff.init({
  sourceId: 'cli-source-abc',
  tenantId: 'your-tenant-id',
})

// At journey-stage boundaries, placed from your journey map.
holostaff.markStageEntry('onboarding')

// On sign-in completion.
holostaff.identify(user.id)

// On logout.
holostaff.clearIdentity()

// On events the scan flagged as worth observing.
holostaff.emitSignal('first_resource_created', { kind: 'project' })
```

## Behavior guarantees

- **Fail-soft.** No method ever throws into your code. Errors go to the optional `onError` callback passed to `init()`.
- **Order-independent.** Calls made before `init()` queue and replay once it runs.
- **Lifetime identity.** The SDK mints and persists a device id (localStorage plus a first-party cookie) and binds it to your user id on `identify()`.

## API

| Method | When it runs | What it does |
|---|---|---|
| `init(opts)` | App startup | Opens the session, binds source and tenant |
| `markStageEntry(stage)` | Entering a journey stage | Tells the runtime where the user is |
| `identify(userId)` | Sign-in | Links the device to your user |
| `clearIdentity()` | Logout | Unlinks it |
| `emitSignal(name, data?)` | Product events | Custom signals your map declared |
| `reportOutcome(id, outcome)` | Custom UIs only | Reports an intervention outcome. The built-in widget does this automatically |

## The presence layer

The SDK also renders the copilot's presence: the chip that shows a copilot is on duty, notes it can leave, and the Stage where it talks with the user face to face. All of it ships through the same deploy PR; none of it requires custom code.

## Instrumentation is verified, not trusted

On every scan, the CLI detects the `holostaff.*` calls actually present in your code and reconciles them with what the map expects. Drift (a stage marker deleted in a refactor, a signal that stopped firing) shows up on the canvas as a flagged change.
