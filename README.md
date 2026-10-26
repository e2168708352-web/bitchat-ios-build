# bitchat iOS unsigned IPA builds

Cloud builds of the upstream [permissionlesstech/bitchat](https://github.com/permissionlesstech/bitchat)
iOS app using GitHub Actions macOS runners. The upstream source is checked out
unmodified; the only repository content is the build workflow.

## Build

- Workflow: [`.github/workflows/build-unsigned-ipa.yml`](.github/workflows/build-unsigned-ipa.yml)
- Runner: `macos-26`
- Scheme: `bitchat (iOS)`, Release, `iphoneos`
- Signing: disabled (`CODE_SIGNING_ALLOWED=NO`)
- Output: `bitchat-unsigned.ipa` (unsigned device build)

Trigger manually from **Actions → Build unsigned bitchat iOS IPA → Run workflow**.
`source_ref` accepts a branch, tag, or commit SHA. Pin a SHA for reproducible
builds.

## Install

The IPA is unsigned and cannot be installed directly. Re-sign it with Sideloadly
or AltStore and an Apple ID, then trust the developer profile on the device.
A free Apple ID signature expires after 7 days. The share extension uses an App
Group, which a free Apple ID may not provision.

This repository only builds source from the upstream project. It is not
affiliated with or endorsed by the bitchat maintainers.
