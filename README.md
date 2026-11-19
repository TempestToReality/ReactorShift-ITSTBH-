# Is this supposed to be here?

A 2D pixel-art nuclear reactor simulator. Run the core, manage rods and coolant, hire a crew, take contracts, order supplies by truck, and try not to melt down. Plays on Android, Windows and in a browser. The in-game Help page (Menu > Help, with search and tags) explains every mechanic.

Made by Angelo (TempestToReality). Inspired by Meltdown Crew.
This is the final version of this game. A new game is in the works; follow the Discord for news.
Devlogs, updates and feedback: https://discord.gg/gcqKTUpdKn

## Download

**[Get the latest version here](../../releases/latest)**

Scroll to **Assets** on that page and pick your version:

| Platform | File | How to install |
| --- | --- | --- |
| Android | `ReactorShift.apk` | Open the file on your phone, allow installing from this source if asked, tap **Install**. |
| Windows | `ReactorShift.exe` | Double-click it. Windows may show a SmartScreen warning: click **More info**, then **Run anyway**. |

You don't need a GitHub account to download. Saves stay on your device.

## Updating

When a new version is released, the game shows a message on the title menu: *"A new version has been released, titled "..." Update?"*

- **Yes**: in the web version the game reloads with the new version. In the Android and Windows apps it opens the Releases page. Download the new file and install it over the old one. Your saves are kept.
- **No**: the game asks once more, then leaves you alone until you next launch it.

Before updating, you can back up your saves in the game: Pause menu > Backup saves > Export.

The full history of changes is in the game: Menu > Changelog.

## About the install warnings

Android may say "App not scanned" or "Blocked by Play Protect", and Windows may show a SmartScreen warning. This is expected and does not mean anything is wrong.

- The apps are **unsigned builds distributed outside the Play Store and the Microsoft Store**. Both systems warn about every app that isn't signed with a paid certificate.
- On Android tap **More details** then **Install anyway**.
- On Windows click **More info** then **Run anyway**.

You can check what the game does for yourself:

- **The whole game is one readable file:** `index.html`. There is no hidden or compiled game code.
- **Both apps are built in public** by GitHub Actions from the files in this repository (see `.github/workflows/`). You can read every build step.
- **No accounts, no ads, no tracking, no analytics.** The game sends no personal data anywhere.
- **Saves stay on your device**, in the app's own storage.
- **Network use is minimal.** The game works offline. It makes two kinds of requests: it loads a pixel font from Google Fonts (with a default font as fallback), and it reads `version.json` from this repository to check for updates.
- **No access to your files, contacts, camera, microphone or location.**

If you are unsure, don't install it. Read the source here first, or build it yourself from this repository.

## For developers

| File | What it is |
| --- | --- |
| `index.html` | The entire game |
| `version.json` | Tells installed games whether a newer version exists |
| `manifest.webmanifest`, `sw.js` | Web-app install and offline files |
| `capacitor.config.json`, `package.json` | Settings for the Android wrapper (Capacitor) |
| `icon-*.png` | App icons |
| `debug.keystore` | Fixed debug signing key so new Android builds install over old ones |
| `.github/workflows/android.yml` | Builds the APK and publishes it under Releases |
| `.github/workflows/windows.yml` | Builds the Windows exe (Electron) and publishes it under Releases |

Every time `index.html` changes, GitHub builds a new APK and exe and adds them to **Releases**.

### Announcing an update to players

1. Edit `version.json` on the `main` branch.
2. Set `title` to the update's name, for example `"Truck Day Update"`.
3. Set `version` to a number higher than the build number inside the game (the `BUILD` value in `index.html`).
4. Commit. Players are prompted the next time they open the title menu.

```json
{
  "version": 79,
  "title": "Your Update Name",
  "url": "https://github.com/TempestToReality/ReactorShift-ITSTBH-/releases/latest"
}
```

`url` is where the Android and Windows apps send players to download the new build.

## Status

In development. Bugs and feedback are welcome on the Discord.
