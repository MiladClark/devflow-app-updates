# devflow-app-updates

Official **release channel** for [DevFlow Manager](https://github.com/MiladClark/devflow-app-updates) — Windows portable builds and OTA update assets.

Binaries are published as **GitHub Releases** (not committed to this repo). The DevFlow desktop app checks [DevTune](https://devtune.dev) for the latest version, then downloads the zip from here.

## Releases

| Version | Date | SHA256 | Download |
|---------|------|--------|----------|
| 0.1.1 | 2026-07-06 | `508276f410638321…` | [zip](https://github.com/MiladClark/devflow-app-updates/releases/download/v0.1.1/devflow-0.1.1-win-x64.zip) |
| 0.1.0 | 2026-07-06 | `705fc7ff5bba1186…` | [zip](https://github.com/MiladClark/devflow-app-updates/releases/download/v0.1.0/devflow-0.1.0-win-x64.zip) |

All releases: https://github.com/MiladClark/devflow-app-updates/releases

## For maintainers

Build and publish from `devflow-app` (with explicit approval):

```bash
cd devflow-app
node scripts/publish-release.mjs --notes "Release notes here"
```

This creates a GitHub Release on this repo, updates this README, and registers the release in DevTune.
