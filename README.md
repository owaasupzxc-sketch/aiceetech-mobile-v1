# AI'ceeTech Mobile V1 — Aero Ultimate Update

Phone-first desktop-style PWA for Android and GitHub Pages. This package is based on the original `aiceetech-mobile-v1-main.zip` source, preserving its original project identity and built-in apps while extending the desktop shell.

## Existing features retained
- Aero Blue / Aero Dark
- Boot screen, desktop, Start Menu and taskbar
- Owaa Tech Agent and Microsoft Hub
- Notes, Calculator, Paint, File Manager / My Computer and Control Center
- PWA manifest and service worker

## Aero Ultimate additions
- Draggable desktop shortcuts with saved positions
- Desktop context menu: Refresh, Arrange Icons, Widgets and Control Center
- Aero floating windows, resize, maximize/restore, taskbar minimize/restore and edge snapping
- Built-in web view launched from inside Microsoft Hub; it is not listed as a standalone desktop or Start Menu app
- Browser tabs, address field and in-frame navigation controls
- Media Player for user-selected local audio/video files
- Task Manager for open AI'ceeTech windows
- Notification Center shell
- Clock and sticky-note widgets
- Quick Settings panel
- Wallpaper presets, large text and reduce-motion settings
- Paint PNG export and local file picker

## Important browser limitations
The internal web view uses an iframe. Many websites intentionally block embedding with browser security headers (for example, `X-Frame-Options` or CSP `frame-ancestors`). Those pages cannot be forced to display inside the PWA; an external browser may still be required for those specific sites. The built-in browser is not exposed as a separate app shortcut or Start Menu tile.

## Android / PWA limitations
This remains a web app, not a native Android APK or a full Windows operating system. A web page cannot directly toggle Android Wi-Fi, Bluetooth, brightness, or read full device process/memory information without native APIs and permissions. The Task Manager reports AI'ceeTech app windows and browser runtime information, not Android processes. File access is limited to files explicitly selected by the user. Weather requires a future data source and network access.

## Deploy
1. Keep a backup of the current GitHub repository files.
2. Extract this ZIP.
3. Upload the seven files from `aiceetech-mobile-v1-main` to the repository root, replacing the old versions.
4. Commit the changes to the branch used by GitHub Pages.
5. Open the Pages site and refresh. If an old version remains, close the installed PWA/browser tab and reopen it so the new service-worker cache activates.

## Data
Notes, sticky notes, theme and desktop shortcut positions are saved locally in browser storage on this device. Export important notes before clearing browser data or uninstalling the PWA.
