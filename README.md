# DevFlow Manager

**DevFlow Manager** is a Windows desktop app for creating, running, monitoring, and configuring local development projects from one place.

Website / licensing: [devtune.app](https://devtune.app)  
Release assets: [GitHub Releases](https://github.com/MiladClark/devflow-app-updates/releases)

## What it does

DevFlow helps you manage day-to-day local development without juggling many terminals and folders:

- **Projects** — register local apps, open their folders, and keep project settings in one workspace
- **Run & monitor** — start/stop scripts and services, watch process status, and work with an integrated terminal
- **Configure** — edit env/config and project options without leaving the app
- **Account & license** — sign in via DevTune, activate plans, and manage subscription status
- **Onboarding** — first-run guided setup for new installs
- **Auto-update** — checks DevTune for newer builds, downloads the portable zip from this repo’s GitHub Releases, verifies integrity, then applies and restarts

## Platform

| | |
|---|---|
| OS | Windows (x64) |
| App type | Electron desktop (portable + Setup installer) |
| Current version | **0.1.11** |
| Theme | Clark Floor Light (Poppins) |

## Downloads

| Asset | Use |
|-------|-----|
| `DevFlowManager-Setup.exe` | First install (Inno Setup wizard) |
| `devflow-*-win-x64.zip` | Portable / OTA update package |

Latest release: [v0.1.11](https://github.com/MiladClark/devflow-app-updates/releases/tag/v0.1.11)

> Binaries live only on **GitHub Releases** — they are not committed into this git repo. The app asks DevTune for the latest version, then downloads the zip from the release URL registered there.

## How updates work

1. App calls DevTune: `GET /api/updates/check?product=devflow&channel=stable&version=…`
2. If a newer version exists, it downloads the zip from the GitHub Release asset URL
3. SHA-256 checksum is verified before apply
4. Files are replaced and the app restarts

## Releases

| Version | Date | SHA256 | Download |
|---------|------|--------|----------|
| 0.1.11 | 2026-07-14 | `8fbf8705c1683d9d…` | [zip](https://github.com/MiladClark/devflow-app-updates/releases/download/v0.1.11/devflow-0.1.11-win-x64.zip) |
| 0.1.10 | 2026-07-14 | `8f693bb366f7bddb…` | [zip](https://github.com/MiladClark/devflow-app-updates/releases/download/v0.1.10/devflow-0.1.10-win-x64.zip) |
| 0.1.4 | 2026-07-06 | `bda9754075c68c20…` | [zip](https://github.com/MiladClark/devflow-app-updates/releases/download/v0.1.4/devflow-0.1.4-win-x64.zip) |
| 0.1.3 | 2026-07-06 | `fa797242f62952fe…` | [zip](https://github.com/MiladClark/devflow-app-updates/releases/download/v0.1.3/devflow-0.1.3-win-x64.zip) |
| 0.1.2 | 2026-07-06 | `4965e96f881dc9c6…` | [zip](https://github.com/MiladClark/devflow-app-updates/releases/download/v0.1.2/devflow-0.1.2-win-x64.zip) |
| 0.1.1 | 2026-07-06 | `508276f410638321…` | [zip](https://github.com/MiladClark/devflow-app-updates/releases/download/v0.1.1/devflow-0.1.1-win-x64.zip) |
| 0.1.0 | 2026-07-06 | `705fc7ff5bba1186…` | [zip](https://github.com/MiladClark/devflow-app-updates/releases/download/v0.1.0/devflow-0.1.0-win-x64.zip) |

All releases: https://github.com/MiladClark/devflow-app-updates/releases

## For maintainers

Build and publish from `devflow-app`:

```bash
cd devflow-app
node scripts/publish-release.mjs --notes "Release notes here"
```

This creates a GitHub Release on this repo, updates the releases table above, and registers the release in DevTune.
