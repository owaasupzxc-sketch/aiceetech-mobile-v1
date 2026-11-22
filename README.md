# AI'ceeTech Mobile V1

Phone-first desktop-style PWA intended for Android and GitHub Pages.

## Included in this starter V1
- Aero Blue / Aero Dark themes
- Start menu, desktop shortcuts and taskbar
- Multi-window app shell with drag, minimize, maximize and close
- Touch-friendly controls and keyboard shortcuts
- Owaa Tech Agent with two visual skins
- Browser launcher, Google search link and external-browser fallback
- Local Notes, Calculator, Paint, File Manager and Settings
- PWA manifest and service worker for installation/offline shell

## Deploy to your own GitHub Pages
1. Create a repository in your GitHub account (for example `aiceetech-mobile`).
2. Upload **all files in this folder** to the repository root.
3. Open repository Settings → Pages.
4. Under Build and deployment, choose Deploy from a branch.
5. Select `main` and `/ (root)`, then Save.
6. Open the Pages URL on Android Chrome.
7. Chrome menu → Add to Home screen / Install app.

## Android notes
This is a web app, not an APK or a full Windows OS. It uses the Android browser engine. GitHub Pages cannot package its own Chromium binary. Many websites block iframe embedding; use the Browser app's **Open in Chrome** button for those sites. Phone, SMS, Bluetooth, file-system and native Android integrations require a separately built Android APK and explicit permissions; they are not silently simulated as working native features here.

## Data
Notes are stored in the browser's local storage. Export important notes before clearing browser data or uninstalling the PWA. This V1 does not upload notes to a server.
