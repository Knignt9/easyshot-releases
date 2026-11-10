# EasyShot 1.0.2 — Windows x64

- Installer: `EasyShot-Setup-1.0.2.exe`
- Size: 188554864 bytes (~180 MiB)
- SHA256: `8ca901e5b0ce38ff11a370af65833e680f0cf6755243e20679ba40508f873921`
- Download: https://github.com/Knignt9/easyshot-releases/releases/download/v1.0.2/EasyShot-Setup-1.0.2.exe

## What's new in 1.0.2

Fixes the Quick Access floating panel (悬浮框) positioning.

- **Screenshots missing after the capture shortcut**: the bottom-docked Quick
  Access panel is anchored to the bottom of the screen. When the Windows taskbar
  is set to auto-hide (or the OS reports a work area that still includes the
  taskbar), the panel was placed at the very bottom of the screen and hidden
  behind the taskbar, so the new capture looked like it never appeared.
- **"Share to Quick Access" hidden behind the taskbar**: the same root cause —
  the panel overlapped the taskbar by half.

The panel is now taskbar-aware: when the work area already excludes the taskbar
nothing changes; when it does not, the panel reserves the taskbar thickness
(learned from other displays when possible, otherwise `40 × scale factor`,
DPI-aware). This covers panel creation, drag-resize, cross-display follow, and
reflow.

## Verify the download

```bat
certutil -hashfile EasyShot-Setup-1.0.2.exe SHA256
```

Compare the output with `SHA256SUMS.txt` in this directory.

## Install

This is an evaluation build and the installer is unsigned. Windows SmartScreen
will show a warning: choose **More info** then **Run anyway** only if you trust
where the file came from. Windows 10 or 11 on x64 is required.

## Upgrade from 1.0.1

Run the installer over the existing installation. No manual uninstall is needed:
the previous version is replaced in place, and settings, history and recording
projects under `%APPDATA%\EasyShot` are kept.
