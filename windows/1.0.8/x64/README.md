# EasyShot 1.0.8 — Windows x64

- Installer: `EasyShot-Setup-1.0.8.exe`
- Size: 223100536 bytes (~213 MiB)
- SHA256: `5a84fe8baeeb20db3f01142226f69953f2773addf68ee830fa1af4cf90fe67ec`
- Download: https://github.com/Knignt9/easyshot-releases/releases/download/v1.0.8/EasyShot-Setup-1.0.8.exe

## What's new in 1.0.8

A small interface-text release: the recording drawing toolbar no longer lets the
exit button crowd out its neighbours.

- **`Exit annotations` is now `Exit`.** The recording drawing toolbar's exit
  button was wide enough to squeeze the buttons beside it. It now reads `Exit`;
  the full wording stays in its tooltip and accessible name. The Simplified
  Chinese interface is unchanged.
- **`取消固定` reads `Unpin` everywhere.** The recognition viewer and the history
  panel shared this Chinese key with two different English values, so one of them
  was silently dropped when the catalogues merged. Both now read `Unpin`.

Everything else matches 1.0.7 (bundled PP-OCRv6 text recognition on Windows and
the rectangle tool as the editor default).

## Verify the download

```bat
certutil -hashfile EasyShot-Setup-1.0.8.exe SHA256
```

Compare the output with `SHA256SUMS.txt` in this directory.

## Install

This is an evaluation build and the installer is unsigned. Windows SmartScreen
will show a warning: choose **More info** then **Run anyway** only if you trust
where the file came from. Windows 10 or 11 on x64 is required.

## Upgrade from 1.0.7 or earlier

Run the installer over the existing installation. No manual uninstall is needed:
the previous version is replaced in place, and settings, history and recording
projects under `%APPDATA%\EasyShot` are kept.
