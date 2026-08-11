# ODOC desktop

This is the public release portal for the ODOC desktop app. It is the only
end-user location for installers, release notes, updater manifests and support
requests.

## Download

Installers for macOS (x64 / arm64) and Windows (x64) are published on the
[Releases](https://github.com/jedi-hex/odoc/releases) page. Published tags and
assets are never overwritten.

**macOS**: builds are not yet signed or notarized, so macOS reports the app as
damaged on first launch. After moving it to Applications, run
`xattr -cr /Applications/ODOC.AI.app` once, then open it normally. See
[SUPPORT.md](SUPPORT.md) for details.

## Update channels

The app has two channels:

- **Release** — stable builds. Clients on this channel only ever install
  release versions.
- **Alpha** — prerelease builds, published as GitHub prereleases. Clients on
  this channel install whichever of the alpha and release candidates has the
  higher SemVer, so `1.0.0-alpha.N` upgrades to `1.0.0` automatically.

Clients pick a default from their own version — a prerelease build defaults to
Alpha, a stable build defaults to Release — and a channel chosen manually is
always respected.

## Update index

`channels/latest.json` on the `main` branch is the single source of update
metadata. It carries the current release and alpha candidates plus the history
needed for a one-step rollback. Installers and signatures stay on GitHub
Releases; only the metadata lives here.

An Alpha release updates the alpha candidate only, a stable release updates the
release candidate only, and the file is replaced atomically after every platform
asset and signature is available.

## Support

Security reports: [SECURITY.md](SECURITY.md). Installation help and support
expectations: [SUPPORT.md](SUPPORT.md).
