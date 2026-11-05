# Acira Browser downloads and update feed

This repository serves the Acira browser's downloads and the update feed that installed copies of Acira read. It holds no application code.

- **Download Acira:** https://acirabrowser.com/download
- **Source code:** https://github.com/Acira-dev/AciraBrowser, the source of every release under the AGPL-3.0 license.

## Releases

Every Acira release is on the [Releases](https://github.com/Acira-dev/AciraBrowserUpdates/releases) page, newest first. Each one has the
installer, disk images or AppImage, the update packages, `SHA256SUMS.txt` and `BUILD-INFO.json` (the source commit it was built from). Windows
releases also have `WINDOWS-SOURCE.patch`, and Linux releases have `AciraBrowser-Linux-SetupFiles.zip`, which installs the AppImage and adds it
to the app menu.

Current Mac builds are signed with an Apple Developer ID and notarized by Apple. Windows builds are not signed yet, so Windows may show an
unknown-publisher warning. Linux AppImages are not signed; compare their SHA-256 checksums.

## Update feed

Installed copies of Acira check the files in [`feed/`](feed/) after launch and every eight hours, or when you choose
**Settings › About › Check for updates**.

| File | Channel |
| --- | --- |
| `feed/beta-mac.yml` | Mac beta, Apple silicon and Intel |
| `feed/beta.yml` | Windows beta |
| `feed/linux/beta-linux.yml` | Linux beta, x86_64 AppImage |
| `feed/latest-mac.yml`, `feed/latest.yml`, `feed/linux/latest-linux.yml` | Stable. Nothing is offered yet (version `0.0.0`). |

Each entry lists the exact SHA-512, size and address of every update file. Acira checks them before it installs anything, and never
updates to an older version.
