# EasyShot 1.0.5 — Windows x64

- Installer: `EasyShot-Setup-1.0.5.exe`
- Size: 188572692 bytes (~180 MiB)
- SHA256: `cea86263789fa7d13d844a3a85205f8d21634d16b1260e88ef52af65a2d96060`
- Download: https://github.com/Knignt9/easyshot-releases/releases/download/v1.0.5/EasyShot-Setup-1.0.5.exe

## What's new in 1.0.5

Fixes the Quick Access floating panel (悬浮框) across multiple monitors, virtual
displays, and when dragging files into a virtual machine.

### Positioning

- **Multi-monitor and secondary taskbars**: only the primary display used to
  reserve taskbar space. On a secondary monitor whose taskbar is auto-hidden
  (`workArea == bounds`) the panel was anchored to the very bottom of the screen
  and hidden behind the taskbar. The taskbar thickness is now learned from any
  display and reused everywhere.
- **Side and top taskbars**: the panel detects taskbar placement on the top,
  bottom, left or right edge and reserves the correct edge, instead of always
  assuming bottom.
- **Wrong position after switching displays**: remembered bounds were reused even
  when they belonged to a different display, clamping the panel to a screen edge
  instead of the configured corner. Bounds are now reused only on the same
  display; otherwise the panel snaps back to the configured anchor.
- **New virtual displays**: a `display-added` listener now reflows the panel when
  a virtual display appears (spacedesk, streaming virtual monitors, docking), so
  it no longer strands at stale coordinates.

### Drag into a virtual machine

Dragging an image from the panel into a Windows App / RDP virtual machine could
make the panel disappear permanently. The native OLE drag loop can stay blocked
when the drop target answers late or never, which occupied the main thread and
left the panel unreachable. Dragging is now supervised by a separate process:
if the drop target goes silent it cancels the drag with ESC, `WM_CANCELMODE` and
a synthetic left-button release. A normal drag is never touched — the guard exits
as soon as the drag finishes.

### Self-healing and recovery

- The panel is health-checked every 1.5 seconds (only while it holds entries):
  re-shown when hidden, re-centred when its bounds fall outside every display,
  recreated when its renderer crashes, and re-raised when covered by a full-screen
  topmost window (without stealing focus).
- The tray entry "restore recently closed overlay" now works for a panel that is
  hidden but still alive, instead of reporting that there is nothing to restore.

### Diagnostics

The panel now writes `%APPDATA%\EasyShot\logs\quick-access.log` (256 KB rotation,
disable with `EASYSHOT_QUICK_LOG=0`): panel create/show/hide/destroy, drag start
and end with duration, the foreground window after a drag, and every healing
action. Attach it when reporting a positioning problem.

## Verify the download

```bat
certutil -hashfile EasyShot-Setup-1.0.5.exe SHA256
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
