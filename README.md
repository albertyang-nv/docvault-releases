# DocVault Desktop — Releases

Downloadable Windows builds of **DocVault Desktop**. This repository holds
published build artifacts only; the application source lives in a separate,
private repository.

## Install

1. Open the [latest release](../../releases/latest).
2. Download `DocVault-Setup-<version>.exe`.
3. Run it. DocVault installs for the current user, so no administrator rights
   are needed.

Windows SmartScreen may warn about an unrecognized publisher, because these
builds are not code-signed. Choose **More info ▸ Run anyway** if you trust this
source.

## Updates

An installed DocVault checks this repository shortly after it starts,
downloads a newer build in the background, verifies it against the SHA-256
digest in `latest.json`, and applies it the next time DocVault starts. Your
`conf` and `logs` folders are preserved across an update.

Automatic updates can be turned off in **Settings ▸ Preferences ▸ Updates**.

## Verifying a download

Each release includes `SHA256SUMS.txt`:

```powershell
Get-FileHash -Algorithm SHA256 .\DocVault-Setup-<version>.exe
```

`latest.json` is the update feed that installed copies read. `release-manifest.json`
records the commit and lockfile hash the build came from.
