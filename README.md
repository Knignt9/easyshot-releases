# EasyShot Releases

Official distribution repository for EasyShot, a local-first desktop screenshot,
annotation and recording application.

## Downloads

| Platform | Version | Architecture | File |
| --- | --- | --- | --- |
| Windows 10/11 | 1.0.0 | x64 | [EasyShot-Setup-1.0.0.exe](https://github.com/Knignt9/easyshot-releases/releases/download/v1.0.0/EasyShot-Setup-1.0.0.exe) |
| macOS | 1.0.0 | Apple Silicon (arm64) | pending |

Windows SHA256: `09c0704d4daf3b8bb0e792d9cc420d7454b49e944f43eaae49030191013cc391`

See the [v1.0.0 release](https://github.com/Knignt9/easyshot-releases/releases/tag/v1.0.0)
for assets and per-platform notes.

## Repository layout

```
windows/<version>/<arch>/   download instructions and SHA256SUMS.txt
macos/<version>/<arch>/     download instructions and SHA256SUMS.txt
```

Application binaries belong in GitHub Release assets, not Git history. This
repository keeps the version and architecture layout, download links, checksums
and platform notes.

## Platform status

- Windows x64: 1.0.0 evaluation build. The installer is unsigned, so Windows
  SmartScreen will warn; this is not a production release.
- macOS Apple Silicon: internal evaluation builds; formal Developer ID signing,
  notarization and release acceptance are pending.
- macOS Intel and Linux: no public builds available.

## Repository scope

This repository contains distribution documentation. Application binaries belong
in GitHub Release assets, not Git history. Application source is maintained in a
separate private repository.

Future releases will document supported platforms, known limitations and upgrade
instructions. Checksums establish file integrity, not publisher identity or
security approval.
