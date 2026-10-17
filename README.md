# 🎵 Vinylogger

**Scrobble records from your Discogs collection to Last.fm – for Linux and Windows.**

Pick an album from your collection, tick the tracks you're playing, and scrobble them live while the record spins – or afterwards.
*Formerly called “Vinyl Scrobbler” – updating keeps your settings, history and logins.*

The app is available in **English** and **German** (switch under *Settings … → Language / Sprache*).

<!-- Screenshot: drag an image here while editing this file on GitHub -->

## Features

- Browse, search and sort your **Discogs collection** as a cover grid
- Load an album's tracklist and pick what you're playing with checkboxes or “Side A / B …”
- **▶ Listen now:** follows the tracklist in real time, sends “Now Playing” and scrobbles each track when it ends. Pauses at the end of a side so you can flip the record.
- **✓ Already listened:** scrobble tracks afterwards (up to 14 days back)
- Enter missing track lengths yourself – the app remembers them
- Works offline: scrobbles are stored and sent later
- Credentials are kept in your system keyring (KWallet / Secret Service or Windows Credential Manager)

## Installation

Download the latest ZIP under **Releases** (or **Code → Download ZIP**) and unpack it.

### Linux (any distribution)

Open a terminal in the unpacked folder and run:

```
./install-linux.sh
```

- **Arch, CachyOS, Manjaro, EndeavourOS:** builds a native pacman package that uses your system's Qt, so the app matches your desktop theme.
- **Ubuntu, Debian, Mint, Pop!\_OS, Fedora, openSUSE and others:** installs into your home folder. The script fetches a suitable Python and all libraries with [uv](https://docs.astral.sh/uv/), without touching your system Python. It may ask for your password once to install a few small Qt libraries.

Afterwards “Vinylogger” is in your application menu, and you can delete the download folder.
Uninstall: `./uninstall-linux.sh`

Requirements: a 64-bit system (x86_64 or ARM64) with a desktop environment. Run it as your normal user, not with sudo.

### Windows 10 / 11

Double-click **`install-windows.bat`** in the `windows` folder. It downloads everything needed, builds the app and creates shortcuts in the Start menu and on the desktop.
If Windows warns you (“Windows protected your PC”): **More info → Run anyway**.
Uninstall: `windows\uninstall-windows.bat`

## Setup (once)

Click **“Settings …”** in the app:

- **Discogs:** “Get token …” → on discogs.com click “Generate new token” → paste the token → “Connect”
- **Last.fm:** “Create API account …” → paste the API key and shared secret → “Log in to Last.fm” → allow access in your browser

Everyone needs their **own** Discogs token and Last.fm API key. This repository contains no credentials.

## Good to know

- Last.fm doesn't accept tracks shorter than 30 seconds or scrobbles older than 14 days.
- Last.fm doesn't allow deleting scrobbles through its API. Remove wrong ones in your Library on last.fm.
- Live mode relies on the track lengths from Discogs. If you lift the needle, click “Pause” in the app.

## Deutsch

Vinylogger ist auch auf Deutsch verfügbar: In der App **Settings … → Language / Sprache → Deutsch** wählen und neu starten.
Eine deutsche Anleitung liegt in [ANLEITUNG.md](ANLEITUNG.md).

## Tech

Python 3 · PySide6 (Qt 6) · requests · keyring · SQLite
Uses the [Discogs API](https://www.discogs.com/developers) and the [Last.fm API](https://www.last.fm/api).

This project is not affiliated with Discogs or Last.fm.

## License

MIT – see [LICENSE](LICENSE).
