# Is this supposed to be here?

A 2D pixel-art nuclear reactor simulator for Android and the browser. Run the core, manage rods and coolant, hire a crew, and try not to melt down. The tutorial is built into the game.

Made by Angelo (TempestToReality). Inspired by Meltdown Crew. Devlogs and updates: https://discord.gg/gcqKTUpdKn

## About the install warning (Google Play Protect)

When you install the APK you may see a warning such as "App not scanned" or "Blocked by Play Protect". This is expected and is not a sign of anything malicious:

- The APK is a **debug build installed outside the Google Play Store**. Android shows a warning for every app that doesn't come from the Play Store or isn't signed with a registered developer key.
- It is not yet published on Google Play. A Play release needs a signed build and a developer account.

You can check for yourself what the app does:

- **The whole game is one readable file:** `index.html`. There is no hidden or compiled game code.
- **The APK is built in public** by GitHub Actions from the files in this repository (see `.github/workflows/android.yml`). You can read every build step and the log of each run.
- **No accounts, no ads, no tracking, no analytics.** The game has no login and sends no data anywhere.
- **Saves stay on your device**, in the app's own storage. Use Pause menu > Backup saves to export or import them.
- **Network use is minimal.** The game works offline. The only internet requests are loading a pixel font from Google Fonts (it falls back to a default font if offline) and opening the Discord link when you tap it. Android apps built with the Capacitor wrapper include the standard Internet permission for this reason.
- **No access to your files, contacts, camera, microphone or location.**

If you are unsure, don't install it. Read the source here first, or build the APK yourself from this repository.

## How to install

1. Open the **Actions** tab, open the latest green run, and download the `reactor-shift-apk` artifact.
2. Extract the zip and open `app-debug.apk`.
3. Allow installing from this source when your phone asks, then tap Install.

## How the repository is organised

| File | What it is |
| --- | --- |
| `index.html` | The entire game |
| `manifest.webmanifest`, `sw.js` | Web-app install and offline files |
| `capacitor.config.json`, `package.json` | Settings for the Android wrapper (Capacitor) |
| `icon-*.png` | App icons |
| `.github/workflows/android.yml` | Builds the APK |

## Status

In development. Bugs and feedback are welcome on the Discord.
