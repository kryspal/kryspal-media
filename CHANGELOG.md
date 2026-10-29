# Changelog

What changed for you in each release, newest first. The full notes, install and upgrade steps are on each release page.

## [0.9.13](https://github.com/kryspal/kryspal-media/releases/tag/v0.9.13) · 2026-10-29

- Search takes several words in any order, and a phrase in quotes; your last 20 searches are kept so you can run one again or delete it
- "Still watching?": after several episodes in a row with no action from you, the player pauses and asks; choose off, 2, 3 or 5 episodes
- Frame stepping: press . or , to go one frame forward or back
- Remove a series from Next up; watching a new episode of it brings it back
- Subtitles start a little larger, the same as in the apps
- Image subtitles (PGS) now move out of the way only for the part the control bar covers
- The Kryspal apps switch to your local network by themselves at home: the first time an administrator opens the admin console at home, the LAN discovery address is filled in for you
- Updating a member's profile without sending the permission settings no longer clears the existing ones, such as the administrator role
- Clearing the "app check failed" notice no longer crashes the server
- A disc image (ISO) on cloud storage no longer loses its disc info after a rescan; the ones already affected are read again before playback
- Continuous scraping now handles titles marked as needing a new scrape, and the "gave up" notice goes away by itself once they recover
- Paging through search results is faster

## [0.9.12-beta](https://github.com/kryspal/kryspal-media/releases/tag/v0.9.12-beta) · 2026-10-28

- Trakt is now built in: it syncs watch history and adds Trakt community ratings to movies and series. There is nothing to install from the plugin center; each member's own Trakt connection works as before
- Continue watching also lists titles you finished and then started again, like Emby; a card with progress shows only the progress bar and the time left
- Previous and Next episode buttons, with Shift+P and Shift+N: at the end of a season playback goes on to the next season that has episodes, and skips specials
- Hide spoilers, off by default: episodes you have not watched get a blurred still and a folded synopsis
- An episode page shows the episode's own still beside the title
- Theme and light or dark apply only to the device you set them on
- A plugin can name each version of a title, and the name you write yourself ("title - version") still comes first
- When a plugin cannot be installed the plugin page says why
- A plugin loaded from the developer directory shows where it comes from instead of install and uninstall buttons
- Trakt and Bangumi plugins show their own icons
- Changing the address of a network storage account asks for the password again, so a saved password is never sent to a new address
- Reading media info for a whole library is part of STRM boost (PRO); reading a single title stays free, and the page shows an upgrade prompt when it is not included
- Bundled plugins updated: TMDB 2.6.0, OpenSubtitles 1.3.0 and Enhanced Metadata Recognition 1.3.0
- Web browsers no longer count toward the device limit
- A device that has not been used for 90 days releases its slot without being signed out, and takes a place in the queue again the next time it is used
- Servers whose clock runs slow no longer contact the license service every minute
- Changing your password in an app or the web player signs out every other device and keeps only the current one signed in; changing your PIN does the same
- Security hardening

## [0.9.11-beta](https://github.com/kryspal/kryspal-media/releases/tag/v0.9.11-beta) · 2026-10-27

- Files that share a main name become one title with several versions, and a metadata plugin can name each version
- Find duplicates by catalog number as well as by title
- Plugins can show their own icon, and plugin settings are grouped with icons
- Rating badges show the source's logo and score, and you choose the source and a minimum score
- A community rating badge rule is built in, and the 1080P badge is retired
- Badge size and an outline are yours to pick, with a live preview
- Poster badge settings are shorter: a compact rule list, a side panel, and changes save by themselves
- The title page groups its facts by meaning, with up to three ratings and the genres on their own row
- On narrow screens the filters fold behind one icon
- Search puts closer matches first, including pinyin initials
- Shift+N and Shift+P jump to the next and previous episode, and Esc closes the next-episode card
- Search results keep going: titles load as you scroll, and Show more reveals more actors
- Danmaku sliders move in 5% steps and save a second after you stop
- The cast list in title management shows each person's photo
- About now lives at the bottom of the System status page
- Webhook messages carry the server's product name and version
- Signing out and similar requests no longer break the connection on macOS
- DB_HOST and DB_PORT for setups where containers cannot reach each other by name

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
