# Acira Browser public downloads and update feed

Acira's application source repository remains private. This public repository holds
update metadata, with selected manual downloads attached as GitHub release assets.
No installers, application payloads, signing profiles or credentials are committed
to this repository's Git history.

## Manual Mac beta downloads

[Download the latest Mac beta](https://github.com/Acira-dev/AciraBrowserUpdates/releases/tag/v0.1.0-beta.1-mac-107ad2d6), built from
commit `107ad2d6f1919bc4c89f1bb7a2878dd224b626d3`.
Separate DMGs support Apple silicon and Intel Macs running macOS 13 or later.
These are Developer ID signed, unnotarized beta builds. macOS may block opening them;
see [Apple's opening guidance](https://support.apple.com/102445).
Intel execution was checked with Rosetta on Apple silicon; physical Intel testing
remains pending. iCloud passkey authorization remains pending.

The release includes `SHA256SUMS` and `BUILD-INFO.json`. Agent features remain in
private early access.

## Automatic update feed

The automatic update feed remains in standby. The manual DMGs are not offered as
an automatic update. The channel documents use version `0.0.0` with an empty file
list as a no-update sentinel; this is not an Acira application release. Acira
disables downgrades, so existing versions remain installed and no payload is
downloaded from this standby feed.

Feed directory: https://raw.githubusercontent.com/Acira-dev/AciraBrowserUpdates/main/feed/

| Platform | Stable | Beta |
| --- | --- | --- |
| macOS (Intel and Apple silicon) | `latest-mac.yml` | `beta-mac.yml` |
| Windows | `latest.yml` | `beta.yml` |

When an automatic update is separately authorized, publish verified payloads first
and update only the matching channel metadata afterward. Metadata must include a
higher version, the exact SHA-512 and size of each payload, and an absolute public
HTTPS download URL. Mac automatic-update payloads require Developer ID signing
and notarization. Both Mac architectures must be represented in the same channel
document. Do not put private tokens in the feed.

This metadata does not enable a feed inside old installed apps. A build must already
have this public feed configured to discover future updates.
