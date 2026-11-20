# EasyShot 1.0.9 — Windows x64

- Installer: `EasyShot-Setup-1.0.9.exe`
- Size: 223177044 bytes (~213 MiB)
- SHA256: `35fd6e27eb4a80712d67c70848517fbbd2a3ecd9cd87c33ddae93968f6eab6b5`
- Download: https://github.com/Knignt9/easyshot-releases/releases/download/v1.0.9/EasyShot-Setup-1.0.9.exe

## What's new in 1.0.9

Choosing what to record from a window no longer blanks every display and waits
for a click: the `Window` tile now answers with a list inside the toolbar.

- **The `Window` tile opens a thumbnail list.** Capturable windows are listed
  front to back, each with a live thumbnail, its app icon and its size. One click
  commits the target; the toolbar stays where it is and no full-screen overlay
  opens.
- **The list and the recorder accept the same windows.** Cards come from native
  on-screen windows intersected with capturable sources, so a card can never
  promise a window the recorder would refuse. When nothing matches, the panel
  says why and offers a refresh instead of leaving a dead control.
- **The on-screen pick is still there.** Use `Pick a window on screen` in the
  panel footer to pick directly on the desktop; Esc closes the panel.
- **The list is lighter.** Windows returns an app's full-size icon — one
  1024x1024 icon measured 255 KB — for a slot that paints at 14px. Icons are now
  capped at 32px: the same eight-window list dropped from 443 KB to 179 KB, with
  icons accounting for 18 KB instead of 277 KB.
- **The editor's English unpin is its own sentence.** The recognition result
  window reads `Unpin from the editor window`; the history panel keeps `Unpin`.
- **Optional local control surface.** With `EASYSHOT_API_TOKEN` set, the app
  exposes a loopback-only API (port 4319 by default, `EASYSHOT_API_PORT` to
  change it) for scripted listing and importing of recording projects, timeline
  saves and renders. Without that variable the feature stays dormant and normal
  use is unchanged.

Everything else matches 1.0.8 (bundled PP-OCRv6 text recognition on Windows,
the rectangle tool as the editor default, and live drawing during recording).

## Verify the download

```bat
certutil -hashfile EasyShot-Setup-1.0.9.exe SHA256
```

Compare the output with `SHA256SUMS.txt` in this directory.

## Install

This is an evaluation build and the installer is unsigned. Windows SmartScreen
will show a warning: choose **More info** then **Run anyway** only if you trust
where the file came from. Windows 10 or 11 on x64 is required.

## Upgrade from 1.0.8 or earlier

Run the installer over the existing installation. No manual uninstall is needed:
the previous version is replaced in place, and settings, history and recording
projects under `%APPDATA%\EasyShot` are kept.
