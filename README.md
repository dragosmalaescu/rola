# Rola

**Your music. Your device. Your privacy.**

Rola is a private music player for audio files you own, plus online radio. It runs in the browser as an installable PWA, keeps your library on the device, identifies untagged tracks by audio fingerprint, and ships a 10-band EQ with AutoEQ support. No account, no subscription, no ads, no trackers.

**Web app:** [dragosmalaescu.github.io/rola](https://dragosmalaescu.github.io/rola/)
An Android build for Google Play is in testing.

## Why I built it

I wanted a player for my own phone that could handle a local collection, FLAC included, without pushing anything to a cloud service. I also missed the old pocket players, so several themes use a scroll wheel and hardware-style keys you can operate without looking at the screen.

## Features

- Local playback of MP3, AAC/M4A, ALAC, FLAC, WAV and AIFF, including 24-bit files
- Library, favorites, playlists, history and settings stored on the device
- Reads embedded title, artist, album, album artist, genre and cover art
- Cleans noisy file names and fills missing metadata and artwork from online databases
- Identifies untagged or mistagged tracks with an AcoustID fingerprint (the audio is never uploaded)
- Review queue for tracks that still need attention, with manual editing and online matching
- Duplicate protection on import, plus a one-tap cleanup for the existing library
- Browse by artist, album, song or genre; favorites, recently added, most played, playlists, Up Next
- Online radio with search, categories, local stations and favorites
- 10-band graphic EQ with presets, AutoEQ parametric import and a built-in limiter
- Themes: Modern, Retro, Velour, Aura, Quartz, E-Ink
- Sleep timer, shuffle, repeat, drag-to-seek, hold-to-skip and resume where you left off
- English, Romanian, German, French, Spanish and Italian

Actual codec support also depends on the browser and OS.

## Install

**iPhone / iPad:** open the web app in Safari, tap Share, then Add to Home Screen, and launch it from the icon.

**Android:** open the web app in Chrome (or any Chromium browser), open the menu, choose Install app or Add to Home screen, and launch it from the icon.

Once installed, Rola runs full screen without the browser UI.

## Adding music

1. Put your songs in a folder in the Files app (on iPhone, `On My iPhone/Music` works well).
2. In Rola, choose **Add music**. In the scroll-wheel themes it's under **Settings → Add music**.
3. Open the folder and use **Select → Select All → Open**.
4. Keep the screen on until the import finishes.

Imported files are copied once into the app's local storage. After the import succeeds you can delete the originals from Files if you don't need them there, but keep a backup somewhere: removing the app or clearing site data deletes the library.

Duplicates are skipped automatically. Rola compares a fingerprint of each file's content and also the title, artist and album, and keeps the larger (usually better quality) copy.

### External storage (no copy)

**External storage** plays files straight from a USB stick, or from a microSD card on Android, without copying them to the phone. Pick the files and they start playing.

The browser only keeps access while the app is running, on both iOS and Android. After you close Rola completely you need to pick the files again. Swipe right on a track in the External storage list to import it permanently.

> Songs downloaded through an Apple Music subscription are protected and cannot be imported directly. DRM-free music purchased from the iTunes Store can be imported if you have access to the audio files.

## Metadata and identification

On import Rola reads the embedded tags, cleans up names like "Official Video 4K" and looks up anything missing. Tracks with a generic title such as "Track 8" get their real title from the album's track list.

Metadata comes from MusicBrainz and artwork from Cover Art Archive, in the web app and on Google Play alike.

A match is accepted only when the artist agrees with the one in the file, so a known artist is never replaced by a different one. Online lookups can be turned off in Settings.

### Identify by sound

Rola computes a Chromaprint fingerprint from the first two minutes of the track and queries AcoustID. Only the fingerprint and the duration leave the device.

- **Web:** an AcoustID key is built in.
- **Android:** add your own free AcoustID application key under **Settings → Tools → Identify by sound**. The `i` button next to the field explains how to get one.

### Tools

Under **Settings → Tools**:

- **Fix titles and covers:** rerun the online cleanup on the whole library
- **Restore original tags:** undo online corrections and go back to the tags stored in the files
- **Identify by sound** and **Identify unknown tracks**
- **Tracks to review:** tracks with no artist or album, a generic title or no confident match. Edit the tags by hand, or search online with what you typed and pick the right result. Saving also fetches the cover.
- **Remove duplicates:** merges copies already in the library. Favorites, play counts and playlist entries move to the copy that's kept.

## Playback

- Drag the progress bar to seek anywhere.
- Hold **Next** or **Previous** to skip forward or back, in 5-second steps at first and then 10.
- Shuffle and repeat work on albums, playlists and the queue.
- Rola remembers the last track and position.
- Sleep timer for listening at night.

## Themes

Pick one under **Settings → Theme**.

- **Modern:** standard layout with bottom tabs and a large player. Automatic, light or dark.
- **Retro:** pocket player with an LCD, a scroll wheel and five keys. Amber, green, blue or paper.
- **Velour:** soft and warm, with albums on a 3D shelf you flip through. Peach or night.
- **Aura:** blurred album art as the background, with the progress bar colored from the cover.
- **Quartz:** digital-watch look, grey-green display and seven-segment digits.
- **E-Ink:** high-contrast black and white with no animation, for e-paper devices like the Boox Palma.

### Scroll wheel

- Drag along the wheel to move through lists.
- Tap the wheel to select (same as **OK**); tap twice quickly to go back (same as **MENU**).
- Hold the wheel to open a track's options.
- **MENU** goes back; hold **MENU** to jump to the main menu.

On Now Playing, the current album or playlist is listed under the track info. Turn the wheel to pick another song and tap to play it.

## Equalizer

**Graphic EQ:** ten bands with presets including ISO 226 loudness, bass shelf, warm and bright tilt, vocal presence and de-ess. The graph shows the actual response.

**AutoEQ:** go to [autoeq.app](https://autoeq.app/), find your headphones, choose **Parametric EQ**, copy the text and paste it into Rola.

A limiter is on by default to prevent clipping; a calculated preamp is available as an alternative. The EQ processes local music and also radio stations that allow it. The equalizer sheet shows whether the current source is being processed.

## Online radio

Station data comes from [Radio Browser](https://www.radio-browser.info/). Stations that only stream over plain HTTP can't be played from a secure page, so they're hidden.

## Network access and privacy

Rola keeps your music files, library, playlists, favorites, listening history, and settings on your device. Your audio files are never uploaded.

Network access is used for the following features and resources:

* **Song recognition:** An audio fingerprint and track duration are sent to AcoustID. The audio file itself is never uploaded.
* **Metadata lookup:** Song titles, artist and album names are sent to MusicBrainz. MusicBrainz release identifiers and image requests are sent to Cover Art Archive. Online metadata matching can be disabled in Settings.
* **Album artwork:** External artwork is displayed directly from Cover Art Archive. Rola stores only the image URLs, not copies of the images. Artwork embedded in your own music files may be stored locally.
* **Online radio:** Requests are made to the Radio Browser station directory, to the radio streams you choose to play, and to station logo images.
* **Fonts and resources:** All of the app's code and fonts are loaded from GitHub Pages. The bundled fonts use Latin and, where supported by the font family, Latin Extended subsets. Characters not provided by a selected font are displayed using a local system fallback font.

Requests to third-party services necessarily disclose the user's IP address and basic connection information to those services. Rola does not upload audio files. Online metadata lookup may send title, artist and album values, while song recognition sends an audio fingerprint and track duration. Apart from the app itself, all other connections are requests for data, images and audio streams; no external code is loaded.

The web app and the Google Play edition use the same sources. The only difference: the web app includes an AcoustID key, while on Google Play you add your own.

Rola does not require an account and does not include advertising, analytics, or user tracking. It does not operate its own analytics or user-tracking servers.

Full details: [privacy policy](https://dragosmalaescu.github.io/rola/privacy.html).

## Known limitations

- Plain-HTTP radio streams aren't available.
- On some iOS versions audio can stop when the screen locks with the EQ on. Turn the EQ off if that happens.
- A browser can't guarantee bit-perfect output to an external DAC; the OS controls the sample rate.
- Imported files take space twice while the originals are still in Files.
- External storage access ends when the app is closed, on iOS and Android.
- iOS can't lock a web app to portrait, so Rola shows a hint to turn the phone upright. The Android app is locked to portrait.

## Project layout and updates

The player is `index.html` plus a few support files in the same folder:

| File | Purpose |
|---|---|
| `index.html` | the whole app |
| `jsmediatags.min.js` | tag reader |
| `fonts/` | self-hosted fonts and their licenses |
| `chromaprint.js`, `chromaprint.wasm` | fingerprinting for Identify by sound |
| `manifest.webmanifest`, icons | PWA install metadata |
| `privacy.html` | privacy policy |

To ship an update, upload the changed files and commit. On the phone, close Rola completely and reopen it. The Android app loads the same files, so it picks up web updates without a new Play release.

## License

Rola is proprietary and **not open source**. You're welcome to use the hosted app for personal, non-commercial listening. Copying, redistributing, publishing modified versions or commercial use requires my written permission. Full terms in [LICENSE](LICENSE).

## Credits

- [jsmediatags](https://github.com/aadsm/jsmediatags): tag and cover reading (BSD 3-Clause)
- [rusty-chromaprint](https://github.com/darksv/rusty-chromaprint) and rusty-chromaprint-wasm: audio fingerprinting (MIT)
- [AcoustID](https://acoustid.org/): fingerprint lookup
- [MusicBrainz](https://musicbrainz.org/) and [Cover Art Archive](https://coverartarchive.org/): metadata, genres and artwork
- [Radio Browser](https://www.radio-browser.info/): radio directory
- [AutoEQ](https://autoeq.app/): headphone profiles
- [DSEG](https://www.keshikan.net/fonts-e.html): seven-segment font in Quartz (SIL OFL 1.1)
- Onest, Familjen Grotesk, Barlow, VT323, Chakra Petch, Share Tech Mono via [Fontsource](https://fontsource.org), bundled in `fonts/` (SIL OFL 1.1)

---

A personal project by **Dragoș Mălăescu**.
