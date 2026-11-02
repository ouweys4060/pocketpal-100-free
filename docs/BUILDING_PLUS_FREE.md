# Personal build: PocketPal Plus features

This fork keeps the upstream PocketPal Plus implementation intact.

## Free personal builds

The upstream `CONTRIBUTING.md` documents the intended build-flag behavior:

- If `PLUS_STORE_GATE` is **unset** when the JavaScript bundle is produced, all PocketPal Plus features are available and the purchase UI is not shown.
- If `PLUS_STORE_GATE=true`, Plus is gated behind an in-app purchase. Official store builds set this flag.
- E2E builds are gated by default; the documented opt-out is `PLUS_STORE_GATE=false`.

For a personal Android build, make sure the variable is absent from the environment of the build process. On Linux, this can be enforced for the build command with:

```sh
env -u PLUS_STORE_GATE yarn build:android
```

For a debug session where Metro bundles the JavaScript, restart Metro with a clean cache and the variable unset:

```sh
env -u PLUS_STORE_GATE yarn start:reset
```

Do not set `PLUS_STORE_GATE=true` for a personal free build.

## Scope

This documents the upstream-supported build configuration. It does not modify purchase validation, forge receipts, alter store transactions, or bypass a server-side entitlement check. The upstream Plus feature catalogue and device/RAM eligibility rules remain in place.

Build and test the resulting app before relying on it. This document does not claim that an APK has been built or tested.
