# Coptic Khmi — Update Metadata

Public **metadata only** for Coptic Khmi desktop app update checks. No binaries, no source code, no secrets.

One file per platform: `latest-windows.json`, `latest-linux.json`, `latest-macos.json`.

## Schema

```json
{
  "version": "1.0.9",
  "notes": "Short release summary shown in the in-app notice (Arabic).",
  "url": "",
  "publishedAt": "2026-11-25"
}
```

- `version` (string, semver): latest available version for this platform. The app shows an update notice only when this is newer than the installed version.
- `notes` (string): human-readable summary shown in the notice.
- `url` (string, optional): download page for the new version. When empty or absent, the notice shows information only and renders no download action.
- `publishedAt` (string, ISO date): informational.

Each platform owner publishes only their own file. Apps fetch `https://raw.githubusercontent.com/abr429701-oss/coptic-khmi-updates/main/latest-<platform>.json` with no-store caching; fetch failures (offline) are silent.
