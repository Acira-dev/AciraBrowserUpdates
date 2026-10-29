# Acira Browser public downloads and update feed

Acira's application source repository remains private. This public repository holds
update metadata; application update payloads and selected manual downloads are
attached as GitHub release assets. No application binaries, signing profiles or
credentials are committed to Git history.

## Mac beta updates

[Acira Browser 0.1.0-beta.3](https://github.com/Acira-dev/AciraBrowserUpdates/releases/tag/v0.1.0-beta.3-mac-a5472445)
is offered on the **Mac Beta** update channel for Apple silicon and Intel Macs
running macOS 13 or later. Existing signed beta installations with this feed can
choose **Settings → About → Check for updates**, then **Restart to update** when
the download finishes. Updating keeps the existing browser profile, tabs and settings.

The beta is **Developer ID signed, unnotarized and unstapled**. macOS may warn or
block opening unnotarized software; see [Apple's opening guidance](https://support.apple.com/102445).
iCloud passkey authorization remains pending. Native Apple silicon install and
update checks passed on isolated test profiles; physical Intel testing remains pending.

The release contains architecture-specific browser update ZIPs, `SHA256SUMS` and
`BUILD-INFO.json`. The new standalone beta 3 DMG installers remain local.

## Manual Mac downloads

[The published Mac beta 2 DMGs](https://github.com/Acira-dev/AciraBrowserUpdates/releases/tag/v0.1.0-beta.2-mac-281c88db)
remain available for new installations. They contain the public update configuration
and can receive the beta 3 update after installation. These DMGs are also signed,
unnotarized betas. Agent features remain in private early access.

## Update feed

Feed directory: https://raw.githubusercontent.com/Acira-dev/AciraBrowserUpdates/main/feed/

| Platform | Stable | Beta |
| --- | --- | --- |
| macOS (Intel and Apple silicon) | `latest-mac.yml` — standby | `beta-mac.yml` — beta 3 |
| Windows | `latest.yml` — standby | `beta.yml` — standby |

Windows downloads and channel documents are unchanged. Standby documents use
version `0.0.0` with no files; this is a no-update sentinel, not an app release.
Downgrades are disabled.

Publish verified update assets before changing matching channel metadata. Each
active document contains the exact SHA-512, size and absolute public HTTPS URL
for each payload. Both Mac architectures belong in the same Mac channel document.
The current Mac Beta channel explicitly distributes a signed, unnotarized beta;
notarized stable-distribution gates remain separate. No security checks are disabled.

Only builds already carrying this public update configuration can discover these
updates. Automatic checks run after launch and every eight hours; Settings can
check immediately. With automatic downloads off, choose Download in Settings first.
