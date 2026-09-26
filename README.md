# FazerWM

**Scrollable-tiling window manager for macOS.** This is the official public
repository for FazerWM — [downloads](https://github.com/Konstruukt-Labs/fazerwm/releases),
[release notes](https://github.com/Konstruukt-Labs/fazerwm/releases), and the
[issue tracker](https://github.com/Konstruukt-Labs/fazerwm/issues). The source
code itself is closed; product news and documentation live at
**[fazerwm.app](https://fazerwm.app)**.

## Download

Grab the latest `FazerWM-<version>.dmg` from the
[releases page](https://github.com/Konstruukt-Labs/fazerwm/releases/latest),
drag **FazerWM.app** to `/Applications`, and launch it — the setup assistant
walks you through the required permissions.

- macOS 14 (Sonoma) or later, Apple Silicon (M1 or later)
- Signed with a Developer ID and notarized
- In-app updates (Sparkle) are enabled by default; the app checks once a day

Homebrew users can skip the dmg:
`brew install --cask konstruuktlabs/tap/fazerwm` — in-app updates work
exactly the same either way.

## Beta channel

Pre-release builds are published as
[prereleases](https://github.com/Konstruukt-Labs/fazerwm/releases) and offered
over the same update feed, tagged for the `beta` channel. To receive them, in
FazerWM open **Settings → General → Beta updates**. Turn it off and you're
back on stable-only updates. Betas get features earlier and stability later —
report anything broken via the issue tracker.

## Versioning

CalVer: `YYYY.MM.DD` — the UTC date of the release. Betas append
`-beta.<build>` (e.g. `2026.09.01-beta.42`). A same-day hotfix appends
`.N` (`2026.09.01.1`); the build number keeps the plain date so Sparkle's
update ordering stays monotonic.

## The appcast file

[`appcast.xml`](./appcast.xml) on this branch is the Sparkle update feed the
app checks. It is **generated and EdDSA-signed by CI** after every release —
never hand-edit it (modifications invalidate the signature) and don't PR
changes to it. It appears after the first release is published.

## Issues

Bug reports and feature requests are welcome — please use the issue templates
and include the version (menu bar icon → **About** or Settings) and your macOS
version. Check the [docs](https://fazerwm.app/docs) and
[troubleshooting page](https://fazerwm.app/docs/troubleshooting) first; most
setup problems are permission or gesture-conflict issues covered there.

For security reports, see [SECURITY.md](./SECURITY.md) — please don't open
public issues for vulnerabilities.
