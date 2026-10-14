<p align="center">English | <a href="README.zh-CN.md">简体中文</a></p>

<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="assets/logo-dark.svg">
    <img alt="Kryspal Media" src="assets/logo-light.svg" height="56">
  </picture>
</p>

# Kryspal Media

**Your library, beautifully played.** A fast, self-hosted media server for your own movies and series. Run it with Docker on a NAS or any small machine and watch on the devices you already have.

**Website: [media.kryspal.net](https://media.kryspal.net/)**

<p align="center"><img alt="Kryspal Media web player home page" src="assets/viewer-home.webp" width="860"></p>

## Why we built it

<!-- DRAFT: the owner will replace this with the owner's own story. -->
We like owning our media, but the media servers we used kept getting in the way. Once the library grew, browsing and filtering slowed down and a scan could take hours. With cloud-mounted libraries, scanning and reading media info sent so many requests that the drive rate-limited us, and we worried about the account. Servers built around transcoding kept the NAS processor busy, although most players can play the original file directly. When file names were untidy, matching went wrong: one film turned into several entries and its versions got mixed up. And some important features sat behind a paid plan or an online account, so working offline or moving to a new machine broke things. Kryspal Media is our answer to each of these.

## Highlights

- **Fast on huge libraries.** Nearly 200,000 movies and 5,000+ series stay instant: under 50 ms to browse at that scale, and up to 30× faster browsing and filtering than traditional media servers (measured on a NAS with test and real libraries).
- **Original quality, no video transcoding.** Direct play keeps 4K, HDR and lossless audio exactly as in the file, so a small machine is enough.
- **Friendly to cloud drives.** `.strm` files play from a cloud drive without storing the video; the server proxies by default, and with PRO it can send the player straight to the drive on your local network. You choose when media info is read.
- **Works with the players you already use.** 3rd-party players built for Emby or Jellyfin connect as usual, next to Kryspal Media's own web player. Moving over? Import libraries, members and watch history from an existing Emby or Jellyfin server.
- **Tidy even when names are messy.** Flexible folder layouts work out of the box, name recognition (PRO) handles the rest, several files of one film become one title with a version picker, and series that share a TMDB ID can be shown as one.
- **Skip intros and outros.** Mark them once by hand, or let PRO detect them automatically and use community data.
- **Members, devices and parental controls.** Every member has their own history, resume positions and preferences; PRO adds parental controls with content rules, viewing hours and daily limits.
- **Back up and move on.** Back up and restore from the admin console, with password-encrypted manual backups (PRO), so a new machine is a restore away.
- **Plugins you can read and write.** Metadata, artwork, subtitles and casting are plugins, and the official open-source ones come with a [Plugin SDK](https://github.com/kryspal/plugin-sdk) for your own.
- **No account needed, FREE is complete.** A license is just an email address plus a key, and paid features keep working through an offline grace period. FREE is a full media server, not a trial.

## Install

Kryspal Media runs as two containers (the server and PostgreSQL) from one Docker Compose file. Images for amd64 and arm64 are listed on each [release](https://github.com/kryspal/kryspal-media/releases). Step-by-step instructions are in the [installation guide](https://media.kryspal.net/docs/install/).

## Plans

FREE, PRO and MAX differ in limits and smart features; see [Pricing](https://media.kryspal.net/pricing/).

## Plugins

The source of the open-source plugins is on GitHub: [tmdb](https://github.com/kryspal/plugin-tmdb), [fanart](https://github.com/kryspal/plugin-fanart), [dlna](https://github.com/kryspal/plugin-dlna), [opensubtitles](https://github.com/kryspal/plugin-opensubtitles), [assrt](https://github.com/kryspal/plugin-assrt) and [introdb](https://github.com/kryspal/plugin-introdb).

## Help

- [Documentation](https://media.kryspal.net/docs/)
- [Discussions](https://github.com/kryspal/kryspal-media/discussions): questions and ideas
- [Issues](https://github.com/kryspal/kryspal-media/issues): bug reports and concrete feature requests
- [SUPPORT.md](SUPPORT.md): where to ask what

Kryspal Media is proprietary software. This repository holds release notes, the issue tracker and discussions; it does not contain source code.
