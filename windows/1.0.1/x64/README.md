# EasyShot 1.0.1 — Windows x64

- Installer: `EasyShot-Setup-1.0.1.exe`
- Size: 188483131 bytes (~180 MiB)
- SHA256: `2e31be04273251c0ae93a12089aa87afff9df199999f7a46505410f341f91caa`
- Download: https://github.com/Knignt9/easyshot-releases/releases/download/v1.0.1/EasyShot-Setup-1.0.1.exe

## What's new in 1.0.1

- Update checks in Settings → About: shows the current version, reports when a
  newer build is available and links to the installer. Checks run at most once a
  day and never upload screenshots, projects or recordings.
- The installer now closes a running EasyShot before replacing files, so an
  in-place upgrade over a tray-resident instance no longer fails with
  "EasyShot is still running".
- Explicit per-user installer settings: fixed install location, no directory
  prompt, desktop and Start menu shortcuts, settings preserved across upgrades.
- English and Simplified Chinese installer UI.

## Verify the download

```bat
certutil -hashfile EasyShot-Setup-1.0.1.exe SHA256
```

Compare the output with `SHA256SUMS.txt` in this directory.

## Install

This is an evaluation build and the installer is unsigned. Windows SmartScreen
will show a warning: choose **More info** then **Run anyway** only if you trust
where the file came from. Windows 10 or 11 on x64 is required.

## Upgrade from 1.0.0

Run the installer over the existing installation. No manual uninstall is needed:
the previous version is replaced in place, and settings, history and recording
projects under `%APPDATA%\EasyShot` are kept.
