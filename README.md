# Cee'tech Mobile V1

**Your desktop. Your experience.**

A mobile-first desktop-style Progressive Web App (PWA), based on the original `aiceetech-mobile-v1-main` project and updated as one coordinated build.

## Included
- Cee'tech startup screen and branding.
- Floating app windows with drag, resize, minimize, maximize, restore, per-app saved position/size/scale, and optional edge snapping.
- Start Menu with searchable List/Grid views.
- Notes, Calculator, Paint, My Computer, Control Center, Owaa Tech Agent, Microsoft Hub, Media Player, Task Manager and Notification Center.
- Facebook, YouTube, Spotify and MovieBox web-app shortcuts with external-open fallbacks where embedding is blocked.
- White, Black, Blue and System Default themes; wallpaper presets and user-selected wallpaper.
- Global font style and numbered font-size settings.
- Draggable/resizable widgets with persistent position/size and hide/restore controls.
- Eye Care, Extra Dim, Privacy Shield overlay, optional UI sounds, and an optional on-screen keyboard with a landscape numeric keypad.
- File imports stored in browser IndexedDB when supported and within device quota.
- Responsive layout, service-worker caching and offline app shell.

## Install / test
1. Extract the ZIP.
2. Serve the folder over HTTPS or localhost (service workers and geolocation require a secure context).
3. Open `index.html` through the local web server or deploy the folder to a static HTTPS host.
4. On Android Chrome, use **Install app** / **Add to Home screen**.

## Important PWA limitations
- This is a PWA, not an Android APK or system launcher. It cannot replace Android's native Control Center, change protected Wi-Fi/Bluetooth radios, or manage Android processes.
- Physical keyboards and mice work through browser input support. The optional on-screen keyboard is an in-app typing aid; it cannot replace Android's system keyboard.
- Websites may block iframe embedding or login. Use the app's external-open action when necessary.
- Weather needs location permission and an internet connection. Wallpaper images and imported files use browser storage, which can be cleared or limited by Android/browser storage quotas.
- Privacy Shield is an in-app overlay only; it does not provide hardware viewing-angle protection or system-wide privacy.
- Browser support for battery status, geolocation, notifications, audio and persistent storage varies by device.

## Project files
- `index.html` — app shell and interface
- `style.css` — responsive styling and window/widget/keyboard presentation
- `app.js` — app logic and local persistence
- `manifest.webmanifest` — install metadata
- `sw.js` — offline app-shell cache
- `icon.svg` — Cee'tech icon

No GitHub push or live-site deployment is included in this build.
