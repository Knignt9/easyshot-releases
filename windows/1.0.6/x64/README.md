# EasyShot 1.0.6 — Windows x64

- Installer: `EasyShot-Setup-1.0.6.exe`
- Size: 188517674 bytes (~180 MiB)
- SHA256: `e475cd0cb8effba1f3dca966a7cd39d3ebf4f7d27139dd15f401d3264f922534`
- Download: https://github.com/Knignt9/easyshot-releases/releases/download/v1.0.6/EasyShot-Setup-1.0.6.exe

## What's new in 1.0.6

The history panel is no longer read-only: tick the screenshots you want and drag
them straight into a chat window, a folder, or any application that accepts
dropped files.

### Dragging captures out of the panel

- **A tick on every card.** Hovering a card reveals a checkbox in its top-left
  corner; it stays visible once checked. The checkbox only decides what a drag
  carries — clicking the rest of the card still opens the original image.
- **Whole batches at once.** Dragging any ticked card carries every ticked
  screenshot; an unticked card travels on its own.
- **Reachable from the compact strip too.** With a selection active, the strip's
  header grows a "N selected / Drag to app" pill, and the expanded panel adds a
  "Drag to app" button to its footer toolbar.
- **Real files, readable names.** What lands in the target application is the
  screenshot's own name rather than its content hash, so a paste into a chat
  input shows a filename a human can read.
- **The panel no longer dismisses itself mid-drag.** An unpinned panel used to
  close on blur, and a drag always hands focus to the drop target. The panel now
  stays alive for the length of the drag, then applies its normal rule: pinned
  panels keep their place, unpinned panels leave once the drag is over.
- **Unresponsive targets stay guarded.** The out-of-process drag guard added in
  1.0.5 still cancels a drag into a virtual machine or remote desktop that never
  answers, so neither the panel nor the mouse gets stuck.
- **Keys.** `⇧` selects a range, `⌘/Ctrl` adds a card, `⌘/Ctrl + A` selects all.
  `Esc` now peels one layer at a time: clear the ticks, collapse the expanded
  panel, close the panel.

## Verify the download

```bat
certutil -hashfile EasyShot-Setup-1.0.6.exe SHA256
```

Compare the output with `SHA256SUMS.txt` in this directory.

## Install

This is an evaluation build and the installer is unsigned. Windows SmartScreen
will show a warning: choose **More info** then **Run anyway** only if you trust
where the file came from. Windows 10 or 11 on x64 is required.

## Upgrade from 1.0.2 or earlier

Run the installer over the existing installation. No manual uninstall is needed:
the previous version is replaced in place, and settings, history and recording
projects under `%APPDATA%\EasyShot` are kept.
