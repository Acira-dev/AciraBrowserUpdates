# Acira Browser public update feed

This repository holds public update metadata. Acira's application source remains private.
No installers, update archives, signing profiles, credentials or application source are included.

The feed is in standby. No application download is offered yet.
The channel documents use version `0.0.0` with an empty file list as a no-update sentinel;
this is not an Acira application release. Acira disables downgrades, so existing versions
remain installed and no payload is downloaded from this standby feed.

Feed directory: https://raw.githubusercontent.com/Acira-dev/AciraBrowserUpdates/main/feed/

| Platform | Stable | Beta |
| --- | --- | --- |
| macOS (Intel and Apple silicon) | `latest-mac.yml` | `beta-mac.yml` |
| Windows | `latest.yml` | `beta.yml` |

When a release is separately authorized, publish verified payloads first and update
only the matching channel metadata afterward. Metadata must include a higher version,
the exact SHA-512 and size of each payload, and an absolute public HTTPS download URL.
Mac payloads require Developer ID signing and notarization. Both Mac architectures
must be represented in the same channel document. Do not put private tokens in the feed.

This metadata does not enable a feed inside old installed apps. A build must already
have this public feed configured to discover future updates.
