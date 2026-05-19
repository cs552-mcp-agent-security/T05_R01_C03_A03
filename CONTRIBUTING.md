# Contributing

This is a community-maintained Compose sample. To keep reviews tractable:

1. **One concern per PR.** Combine architectural moves with UI tweaks in
   separate PRs.
2. **Compose Compiler updates** require bumping the Kotlin version pin too;
   call this out in your PR body.
3. **No new third-party dependencies** in the `data/` module without a design
   note in `docs/architecture.md`.

## Reporting issues

Use the bug-report template under `.github/ISSUE_TEMPLATE/`. Include the device
manufacturer, Android API level, and the exact build variant (`debug` /
`release`).
