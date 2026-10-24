# Changelog

What changed for you in each release, newest first. The full notes, install and upgrade steps are on each release page.

## [0.9.10-beta](https://github.com/kryspal/kryspal-media/releases/tag/v0.9.10-beta) · 2026-10-24

- Built-in webhooks, free on every plan: Emby-compatible messages for playback, watched, favorite and new-title events, with per-webhook events, members and libraries, optional signing, a test button and the last 50 deliveries.
- Automatic matching is decided by the metadata plugin instead of a fixed score; subtitles are downloaded automatically only when the subtitle plugin is sure they fit (needs TMDB 2.6.0, OpenSubtitles 1.3.0 and ASSRT 1.1.0).
- A video with incomplete media info, such as an older Blu-ray ISO, is read when you press play instead of failing.
- A title with several versions plays the main file by default in the web player, Emby apps and when casting; Emby apps get default audio and subtitle tracks from the member's preferences.
- Link a TV from the web player by typing the code the TV shows.
- Casting marks the title watched at the end and keeps the resume position.
- Server support for app offline downloads, except disc sources.
- System settings has eight tabs, and the attention cards have one fixed height.
- arm64 images are published again, next to amd64.

## [0.9.9-beta](https://github.com/kryspal/kryspal-media/releases/tag/v0.9.9-beta) · 2026-10-23

- Network storage over WebDAV, free: add a NAS, rclone or OpenList address, pick folders, and the server scans and plays them without mounting anything. Sending the player straight to the storage is a PRO feature.
- Blu-ray ISOs and folders, embedded subtitles, intro and credits detection and split videos work on network sources as they do on local files.
- Each library can have its own value for a plugin setting, with a Scrape again button when the new value could change results; name recognition rules are tracked per library.
- Danmaku is off by default, shows its loading state, scrolls at the screen's refresh rate, and has a display area, font size and opacity settings.
- Posters and backdrops the scraper downloads are written next to the video in libraries with write-back on.

## [0.9.8-beta](https://github.com/kryspal/kryspal-media/releases/tag/v0.9.8-beta) · 2026-10-22

- Blu-ray folders in movie libraries are added as one movie each and play like a Blu-ray ISO; a Blu-ray folder inside a show folder counts as one episode.
- Videos without a keyframe index (TS, M2TS, AVI and similar) start faster and no longer stall when you resume from the middle.
- A show whose episodes only match with absolute numbering is found again automatically.
- The Libraries cards on the home page are a row of their own that you can move or hide.
- New account sync, used with a sync plugin.
- The setup wizard returns the administrator to it if closed halfway, and the install script takes `--name` and `--port` so a second copy can run on the same machine.

## [0.9.7-beta](https://github.com/kryspal/kryspal-media/releases/tag/v0.9.7-beta) · 2026-10-21

- The web player's search page suggests titles before you type, from your recent watches or the recently added.
- Videos without an index start faster in the web player and the apps, and playing from the start always begins at the very beginning.
- Float and other PCM audio can be converted and played; audio the server cannot decode is said plainly, with an external player offered.
- New setting Allowed web origins for opening the web page through a reverse proxy that rewrites the Host header.
- Memory use adjusts to the machine by itself, so small machines use less.

## [0.9.6-beta](https://github.com/kryspal/kryspal-media/releases/tag/v0.9.6-beta) · 2026-10-20

- Dual-layer Dolby Vision (profile 7) videos play as Dolby Vision on devices that support only a single layer.
- A sleep timer, chapters on the progress bar, adjustable back and forward steps, and an undo after an automatic skip.
- Media keys, the lock screen and Chrome's media panel show the title and poster and can skip and change episode.
- A plugin can confirm a match, so a title it is certain about is matched without waiting for you.
- Poster badges can go in more corners, use your own icons and show a live preview; plugins can suggest badges for their tags.
- Subtitle auto-fill has a daily limit for each plugin.

## [0.9.5-beta](https://github.com/kryspal/kryspal-media/releases/tag/v0.9.5-beta) · 2026-10-19

First public beta.

- Web player with a home page, favorites, titles, people and search; original quality with no video transcoding; HLS, Dolby Vision signaling and AirPlay in Safari; casting to Chromecast and DLNA.
- Works with 3rd-party players for Emby and Jellyfin; move over from an existing Emby or Jellyfin server with libraries, members, metadata, images, watch history and favorites.
- Details and images from several sources, name recognition for difficult file names (PRO), real-time folder watching and actor pages with photo galleries.
- Subtitles: ASS styling, picture subtitles, adjustable delay and two tracks at once; Blu-ray ISO playback with PGS subtitles; skip buttons for intros and credits.
- Members with an optional PIN, parental controls (PRO), backup and restore (PRO), a task center, and three interface languages.
- Plugins you install, update and turn off in the console, an open-source Plugin SDK and six open-source plugins.
- FREE, PRO and MAX plans, and no online account needed.
