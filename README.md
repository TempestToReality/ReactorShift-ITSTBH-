# Is this supposed to be here?

A 2D pixel-art nuclear reactor simulator for Android. Run the core, manage rods and coolant, hire a crew, take contracts, and try not to melt down. The tutorial is built into the game.

Made by Angelo (TempestToReality). Inspired by Meltdown Crew. Devlogs and updates: https://discord.gg/gcqKTUpdKn

## Download (Android)

**[Get the latest version here](../../releases/latest)**

1. Open that link and scroll to **Assets**.
2. Tap **ReactorShift.apk** to download it.
3. Open the downloaded file. If your phone asks, allow installing from this source, then tap **Install**.

Updating later: download the newest `ReactorShift.apk` the same way and install it over the old one. Your saves are kept.

Before an update, you can back up your saves in the game: Pause menu > Backup saves > Export.

You don't need a GitHub account to download.

## About the install warning (Google Play Protect)

When you install the APK you may see a warning such as "App not scanned" or "Blocked by Play Protect". This is expected and is not a sign that anything is wrong:

- The APK is a **debug build installed outside the Google Play Store**. Android shows a warning for every app that doesn't come from the Play Store or isn't signed with a registered developer key.
- It is not yet published on Google Play. A Play release needs a signed build and a developer account.
- To continue, tap **More details** then **Install anyway**.

You can check for yourself what the app does:

- **The whole game is one readable file:** `index.html`. There is no hidden or compiled game code.
- **The APK is built in public** by GitHub Actions from the files in this repository (see `.github/workflows/android.yml`). You can read every build step and the log of each run.
- **No accounts, no ads, no tracking, no analytics.** The game has no login and sends no data anywhere.
- **Saves stay on your device**, in the app's own storage.
- **Network use is minimal.** The game works offline. The only internet requests are loading a pixel font from Google Fonts (it falls back to a default font if offline) and opening the Discord link when you tap it. The Android wrapper (Capacitor) includes the standard Internet permission for this reason.
- **No access to your files, contacts, camera, microphone or location.**

If you are unsure, don't install it. Read the source here first, or build the APK yourself from this repository.

## For developers: how the repository is organised

You only need this section if you want to look at or build the project.

| File | What it is |
| --- | --- |
| `index.html` | The entire game |
| `manifest.webmanifest`, `sw.js` | Web-app install and offline files |
| `capacitor.config.json`, `package.json` | Settings for the Android wrapper (Capacitor) |
| `icon-*.png` | App icons |
| `debug.keystore` | Fixed debug signing key so new builds install over old ones |
| `.github/workflows/android.yml` | Builds the APK and publishes it under Releases |

Every time `index.html` changes, GitHub builds a new APK and adds it to **Releases**.

## Status

In development. Bugs and feedback are welcome on the Discord.
