# EasyShot 1.0.7 — Windows x64

- Installer: `EasyShot-Setup-1.0.7.exe`
- Size: 223100313 bytes (~213 MiB)
- SHA256: `8e21ee03af005f917d698b6087ec6a0dcb8614ceb2ed7e624b71cbaea78890c4`
- Download: https://github.com/Knignt9/easyshot-releases/releases/download/v1.0.7/EasyShot-Setup-1.0.7.exe

## What's new in 1.0.7

Text recognition on Windows now runs a bundled PP-OCRv6 engine instead of only
the system recognizer, and the image editor opens with the rectangle tool.

### Recognition

- **Whole lines, not word fragments.** The helper ships PP-OCRv6 small models and
  runs them locally, so low-resolution coloured code screenshots come back as
  complete lines. A SQL condition that used to return as
  `or (dfkkop .OPRFI is not null ...` now reads end to end.
- **Visual rows.** Line numbers and their code merge into one row instead of
  splitting into misaligned fragments.
- **Highlights included.** Low-contrast highlighter rows get a grayscale contrast
  stretch and a second recognition pass when confidence is low.
- **Languages.** English, Simplified and Traditional Chinese, Japanese, French,
  German, Spanish, Portuguese, Italian and Vietnamese; other languages fall back
  to the Windows recognizer as before.
- **Brief warm-up.** Models are loaded in the background, so the first
  recognition takes one or two extra seconds and later calls stay warm. The
  models are Apache-2.0 licensed and ship inside the installer.

### Image editor

- **Rectangle by default.** The editor no longer opens on the arrow tool.
- **Compact crop actions.** The crop strip reads Apply / Reset, with the full
  labels kept in tooltips and accessible names; long labels scroll the strip
  instead of squeezing the buttons.

### Stability

- Fixed a double release of the window-capture frame object that could break
  native window capture or startup.
- Development builds no longer attempt code signing on non-macOS hosts.

## Verify the download

```bat
certutil -hashfile EasyShot-Setup-1.0.7.exe SHA256
```

Compare the output with `SHA256SUMS.txt` in this directory.

## Install

This is an evaluation build and the installer is unsigned. Windows SmartScreen
will show a warning: choose **More info** then **Run anyway** only if you trust
where the file came from. Windows 10 or 11 on x64 is required.

## Upgrade from 1.0.6 or earlier

Run the installer over the existing installation. No manual uninstall is needed:
the previous version is replaced in place, and settings, history and recording
projects under `%APPDATA%\EasyShot` are kept.
