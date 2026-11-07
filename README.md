# sonora (Android)

Personal music player. Kotlin, Jetpack Compose, Media3.

## What works in this first build
- sonora UI: Home (hero, Quick Access, Recently Played), Library, Search, Queue, Equalizer, Settings, mini player, full player
- 8 color themes + light / dark / system
- Plays the music on your phone (MediaStore), in the background, with notification and lock-screen controls
- Real 5-band equalizer (uses the phone's built-in equalizer)
- Favorites, recently played, repeat modes
- Spotify: log in through Spotify's web player, then see your playlists and liked songs

## Not in this build yet
- Crossfade
- Synced lyrics
- Audio for Spotify songs (see below)

## Build the APK without Android Studio
1. Create an empty private repo on GitHub.
2. Push this folder to it (branch `main`).
3. Open the repo's **Actions** tab. The "Build APK" workflow runs on every push (or press Run workflow).
4. When it finishes, open the run and download the artifact `sonora-debug-apk`. Unzip it and install `app-debug.apk` on your phone (allow installs from your browser or files app).

If the build fails, open the failed run, copy the red error lines, and send them back.

## Build with Android Studio
Open this folder, let Gradle sync, press Run.

## Spotify
Tap Settings > Spotify > Log in. Spotify's own login page opens in the app. After you log in, the app loads
the web player in the background and reads the access token it uses, then calls Spotify's API with it.
Tokens last about an hour; the app refreshes them the same way.

This is unofficial and against Spotify's terms. Use it only for yourself.

### Spotify audio
Spotify gives the app your library and song info, not the audio. A Spotify song plays only if a file with the same
title and artist is on the phone. To play any Spotify song, the app needs an audio source to match songs
against (Yuma uses YouTube for this). That is the next milestone.
