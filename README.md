# Rola

Rola is the music player I made for my own phone. I use it to listen to my audio files (not streaming) and to a handful of online radio stations. It runs in the browser, sits on the home screen like an app, and doesn't need an account, a subscription or the App Store.

Open it here: **https://dragosmalaescu.github.io/rola/**

## Why I built it

I have a lot of music in files, some of it in FLAC, and I didn't want to upload it to a cloud just to enjoy it on my phone. I also missed the old pocket players with a scroll wheel, where you could move through albums without staring at the screen. So I built Rola.

## What it does

- Plays your local music: MP3, AAC/M4A, ALAC, FLAC, WAV and AIFF, including 24-bit files.
- Reads the title, artist, album, genre and cover art from your files. On import it also tidies messy names (like "[Official Video 4K]") and fills in the right title, artist, album and cover from iTunes or Deezer, with MusicBrainz as a fallback. The Google Play version uses only MusicBrainz.
- Can recognise songs with missing or wrong tags by their sound, using an AcoustID fingerprint (the web version has a key built in; in the Android app you add your own free AcoustID key in Settings, the i button explains how).
- Lists the tracks that still need attention (no artist, no album, a generic title or not recognised) under Settings, Tools, Tracks to review, where you can edit the tags by hand or search online with what you typed and pick the right match.
- Lets you browse by artists, albums, songs and genres. There are favorites, recently added, most played and an up next queue.
- Has online radio with search, categories and favorite stations.
- Has a 10-band equalizer and can import AutoEQ profiles for your headphones.
- Has a sleep timer, shuffle and repeat, and remembers where you left off.
- Lets you drag the progress bar to jump anywhere in a song. Hold the next or previous button to skip forward or back, 5 seconds at a time at first and then 10.
- Speaks English, Romanian, German, French, Spanish and Italian. It starts in English and you can switch in Settings.

## Install it on your phone

1. Open the address above in Safari on iPhone or Chrome on Android.
2. On iPhone tap Share, then Add to Home Screen. On Android, open the browser menu and choose Add to Home screen.
3. From now on, open it from the icon. It runs full screen, without the browser bar.

## Add your music

1. Put your songs in a folder in the Files app. On iPhone the easiest place is On My iPhone, in a folder called Music.
2. In Rola open the menu and choose Add music (in the scroll wheel themes: Settings, then Add music).
3. Open the folder, tap Select, then Select All and Open.
4. Keep the screen on until it finishes. Your music is copied into the player once.

**Play from external storage without copying** (a USB stick, or a microSD card on Android). Choose External storage in the add menu and select the songs (in a folder, tap Select, then Select All). Rola plays the files straight from the stick or card and uses no space on the phone. iOS only allows access while the app is open, so after you close it completely you pick the files again. Any song you like can be imported into the library with a swipe to the right.

Songs bought or downloaded from Apple Music can't be used. They are protected, and iOS doesn't share them with other apps.

## Themes

Change them in Settings, under Theme.

- **Modern** (automatic, light or dark): a regular layout with tabs at the bottom and a big player.
- **Retro** (amber, green, blue, paper): a pocket player with an LCD screen, a scroll wheel and five keys.
- **Velour** (peach, night): soft and warm, with albums on a 3D shelf you flip through with your finger.
- **Aura**: the background is the album cover, blurred, and the progress bar takes its colors from the cover.
- **Quartz**: styled like a digital watch, with a grey-green screen and seven segment digits.
- **E-Ink**: black and white with no animation, made for e-paper screens such as the Boox Palma.

In the scroll wheel themes:

- drag the wheel to move through lists;
- tap it to select, the same as OK;
- tap it twice quickly to go back, the same as MENU;
- hold it to open the options for a song;
- MENU goes back, and holding it takes you to the main menu.

On the Now Playing screen, the current album or playlist is listed under the song details. Turn the wheel to pick another song and press to play it.

## Equalizer

There are two modes.

**Graphic, 10 bands**, with presets for careful listening: Loudness based on ISO 226, a bass shelf, warm and bright tilt, vocal presence, de-ess and a few more. The graph shows the real curve.

**AutoEQ headphone profile.** Find your headphone model on autoeq.app, choose Parametric EQ, copy the text and paste it into Rola. It's the most accurate way to correct a specific pair of headphones.

The preamp is calculated from the curve so the sound doesn't clip. The equalizer applies to your music, not to radio.

## What stays on your phone and what goes online

Your music is never uploaded. The files, favorites, playlists, listening history and settings stay in the browser storage on your device.

Only a few things go over the internet:

- an audio fingerprint and the track length, when you identify a song by sound (sent to AcoustID; your audio is not uploaded);
- the song title and artist name, when tags and covers are matched on iTunes, Deezer, MusicBrainz or the Cover Art Archive (you can turn this off in Settings);
- requests to the radio directory, and the audio of the stations you listen to;
- the fonts and the tag reading library, loaded when the page opens.

Your library belongs to the page address and the browser. If you move the app to another address or clear the site data, you'll need to import your music again.

## Known limits

- Radio stations that only stream over plain http can't be played and are hidden from the list.
- On some iOS versions, sound can stop when the screen locks while the equalizer is on. If that happens, turn the equalizer off.
- A browser can't guarantee bit-perfect playback to an external DAC. iOS decides the sample rate.
- Music is copied into the player, so it takes space a second time. After importing you can delete the copy in Files.

## Updating

The whole player is one file, `index.html`. To publish a new version, upload it to this repository with Add file, then Upload files and Commit changes. On the phone, close the app and open it again.

## License

Rola is not open source. You're welcome to use the hosted app for your own personal, non-commercial listening. Copying, redistributing, publishing modified versions or using it commercially requires my written permission. The full terms are in [LICENSE](LICENSE).

## Thanks

- [jsmediatags](https://github.com/aadsm/jsmediatags), for reading tags and cover art (BSD 3-Clause)
- [DSEG](https://www.keshikan.net/fonts-e.html), the seven segment font in the Quartz theme (SIL Open Font License 1.1)
- [Radio Browser](https://www.radio-browser.info/), the public station directory
- [AutoEQ](https://autoeq.app/), for headphone profiles
- iTunes Search API and Deezer API, for song details and missing covers in the web version
- [AcoustID](https://acoustid.org/) and [rusty-chromaprint](https://github.com/darksv/rusty-chromaprint) (MIT), for recognising songs by sound
- [MusicBrainz](https://musicbrainz.org/) and the [Cover Art Archive](https://coverartarchive.org/), for song details, genres and missing covers
- Google Fonts: Onest, Familjen Grotesk, Barlow, VT323, Chakra Petch and Share Tech Mono (SIL Open Font License 1.1)

A personal project by Dragoș Mălăescu.
