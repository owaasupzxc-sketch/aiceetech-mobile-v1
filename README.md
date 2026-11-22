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
- Per-window browser tabs with close/new-tab controls, per-tab navigation history, saved bookmarks, address field and in-frame navigation controls
- Media Player for user-selected local audio/video files
- Task Manager for open AI'ceeTech windows
- Notification Center shell
- Clock, monthly calendar, opt-in local weather lookup (location permission only after tapping), and sticky-note widgets
- Quick Settings panel
- Wallpaper presets, large text and reduce-motion settings
- Paint PNG export and local file picker

## Important browser limitations
The internal web view uses an iframe. Many websites intentionally block embedding with browser security headers (for example, `X-Frame-Options` or CSP `frame-ancestors`). Those pages cannot be forced to display inside the PWA; an external browser may still be required for those specific sites. The built-in browser is not exposed as a separate app shortcut or Start Menu tile.

## Android / PWA limitations
This remains a web app, not a native Android APK or a full Windows operating system. A web page cannot directly toggle Android Wi-Fi, Bluetooth, brightness, or read full device process/memory information without native APIs and permissions. The Task Manager reports AI'ceeTech app windows and browser runtime information, not Android processes. File access is limited to files explicitly selected by the user. Weather uses the Open-Meteo forecast endpoint and requires internet plus optional device-location permission. The user must tap the weather button to request location; no location is requested automatically.

## Repair pass 01
- Fixed browser state so each internal browser window has its own tabs and navigation history.
- Added close-tab controls and saved bookmarks.
- Added a monthly calendar widget.
- Added opt-in local weather lookup.
- Bumped the service-worker cache version to prevent stale assets from persisting after deployment.

## Deploy
1. Keep a backup of the current GitHub repository files.
2. Extract this ZIP.
3. Upload the seven files from `aiceetech-mobile-v1-main` to the repository root, replacing the old versions.
4. Commit the changes to the branch used by GitHub Pages.
5. Open the Pages site and refresh. If an old version remains, close the installed PWA/browser tab and reopen it so the new service-worker cache activates.

## Data
Notes, sticky notes, theme and desktop shortcut positions are saved locally in browser storage on this device. Export important notes before clearing browser data or uninstalling the PWA.


## Repair pass 02
- Added a persistent browser-local workspace in My Computer with create, edit, rename, download, and delete for text files and folders.
- Added persistent Notification Center entries for app launches and closes, with clear-all.
- Added previous/next month controls to the calendar widget.
- Fixed taskbar app-button minimize/restore/switch behavior.
- Kept the Browser internal-only: no desktop or Start Menu shortcut; Microsoft Hub opens the in-app web window. External opening is user-triggered only.
- Bumped the service-worker cache version.


## Repair pass 03 — functionality and preservation pass
- Restored the original Aero base stylesheet before applying Repair 02 additions. This was important: Repair 02's stylesheet had only the additions and omitted the original desktop/window/taskbar foundation.
- Improved floating windows: stable drag handling, maximize/restore geometry, edge snapping, and a touch resize handle.
- Improved My Computer: nested folders, navigation breadcrumbs, recursive folder deletion, persistent text files, small-file import, and workspace JSON export. Existing Repair 02 workspace entries are migrated in place with IDs so they remain visible.
- Improved internal browser: each tab now owns its own iframe so switching tabs preserves each loaded page where browser security allows it; tabs keep separate app-side history and bookmarks.
- Added local calendar notes/events by tapping a date; event days receive a marker.
- Added simulated Sleep, Resume, Shut down, and Power on actions in the Start Menu. These are desktop-shell simulations, not Android power controls.
- Added live refresh of an open Notification Center when app notifications arrive, and cleanup of media playback when a window closes.
- Added responsive styles for browser frames, calendar event markers, and touch window resizing.
- Bumped the service-worker cache version.

## Known limitations
- This is still a browser-based PWA. Sleep/shutdown are visual shell states only; they do not power off or sleep Android.
- File Manager stores its workspace in browser localStorage. Imported files are embedded only when small enough; large files may be listed without a stored copy. Export important workspace data regularly.
- Browser iframe restrictions are imposed by destination websites. Some pages will refuse to load inside any embedded browser.
- Weather requires HTTPS, internet access, and a user-approved location request.
- Task Manager reports AI'ceeTech windows, not Android system processes.


## Final polish candidate
- Calendar rendering is now independent from the one-second clock refresh, preventing unnecessary calendar DOM rebuilds while the user interacts with the desktop.
- Browser address handling accepts HTTP/HTTPS destinations and search phrases, rejects malformed addresses, and caps the tab count to keep mobile memory use reasonable.
- My Computer prevents duplicate names in the same folder and avoids treating non-text imported files as editable text.
- Media object URLs are released when a new file is selected or the player window closes.
- Improved mobile safe-area spacing, start/quick panel scrolling, touch target sizes, keyboard focus visibility, and window bounds.
- Service-worker cache name updated for this candidate build.

## Testing status
- JavaScript syntax validation and ZIP integrity checks pass.
- Static HTML/asset reference checks pass.
- A real-device test on the target Android phone is still required before calling this release final.
