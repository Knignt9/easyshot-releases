# EasyShot Releases

Official distribution repository for EasyShot, a local-first desktop screenshot,
annotation and recording application.

## Downloads

| Platform | Version | Architecture | File |
| --- | --- | --- | --- |
| Windows 10/11 | 1.0.7 | x64 | [EasyShot-Setup-1.0.7.exe](https://github.com/Knignt9/easyshot-releases/releases/download/v1.0.7/EasyShot-Setup-1.0.7.exe) |
| macOS | 1.0.1 | Apple Silicon (arm64) | pending |

Windows SHA256: `8e21ee03af005f917d698b6087ec6a0dcb8614ceb2ed7e624b71cbaea78890c4`

See the [v1.0.7 release](https://github.com/Knignt9/easyshot-releases/releases/tag/v1.0.7)
for assets and per-platform notes. The previous
[v1.0.6 release](https://github.com/Knignt9/easyshot-releases/releases/tag/v1.0.6),
[v1.0.5 release](https://github.com/Knignt9/easyshot-releases/releases/tag/v1.0.5),
[v1.0.2 release](https://github.com/Knignt9/easyshot-releases/releases/tag/v1.0.2)
and [v1.0.1 release](https://github.com/Knignt9/easyshot-releases/releases/tag/v1.0.1)
stay available for reference.

## Repository layout

```
windows/<version>/<arch>/   download instructions and SHA256SUMS.txt
macos/<version>/<arch>/     download instructions and SHA256SUMS.txt
```

Application binaries belong in GitHub Release assets, not Git history. This
repository keeps the version and architecture layout, download links, checksums
and platform notes.

## Platform status

- Windows x64: 1.0.7 evaluation build with in-app update checks. The installer is
  unsigned, so Windows SmartScreen will warn; this is not a production release.
- macOS Apple Silicon: internal evaluation builds; formal Developer ID signing,
  notarization and release acceptance are pending.
- macOS Intel and Linux: no public builds available.

## Upgrade notes

Windows: run the new installer over the existing installation. It replaces the
previous version in place, and settings, history and recording projects under
`%APPDATA%\EasyShot` are preserved. No manual uninstall is needed.

## Repository scope

This repository contains distribution documentation. Application binaries belong
in GitHub Release assets, not Git history. Application source is maintained in a
separate private repository.

Future releases will document supported platforms, known limitations and upgrade
instructions. Checksums establish file integrity, not publisher identity or
security approval.
