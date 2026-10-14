<p align="center">English | <a href="README.zh-CN.md">简体中文</a></p>

<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="assets/logo-dark.svg">
    <img alt="Kryspal Media" src="assets/logo-light.svg" height="56">
  </picture>
</p>

# Kryspal Media

A fast, self-hosted media server for your own library. Run it with Docker on a NAS or any small machine, point it at your movies and shows, and watch on the devices you already have.

- **Fast on big libraries.** Browsing and filtering stay quick even with hundreds of thousands of titles.
- **Original quality.** Your files play as they are, so a small machine is enough.
- **Works with the players you already use.** 3rd-party players built for Emby or Jellyfin can connect, next to Kryspal Media's own web player.
- **Free to start.** FREE is a complete media server. PRO and MAX add more members, devices and smart features; see [Pricing](https://media.kryspal.net/pricing/).

## Install

Kryspal Media runs as two containers (the server and PostgreSQL) from one Docker Compose file. Images for amd64 and arm64 are listed on each [release](https://github.com/kryspal/kryspal-media/releases). Step-by-step instructions are in the [installation guide](https://media.kryspal.net/docs/install/).

## Plugins

Metadata, artwork, subtitles and casting come from plugins. The source of the open-source ones is on GitHub: [tmdb](https://github.com/kryspal/plugin-tmdb), [fanart](https://github.com/kryspal/plugin-fanart), [dlna](https://github.com/kryspal/plugin-dlna), [opensubtitles](https://github.com/kryspal/plugin-opensubtitles), [assrt](https://github.com/kryspal/plugin-assrt) and [introdb](https://github.com/kryspal/plugin-introdb). Write your own with the [Plugin SDK](https://github.com/kryspal/plugin-sdk).

## Help

- [Documentation](https://media.kryspal.net/docs/)
- [Discussions](https://github.com/kryspal/kryspal-media/discussions): questions and ideas
- [Issues](https://github.com/kryspal/kryspal-media/issues): bug reports and concrete feature requests
- [SUPPORT.md](SUPPORT.md): where to ask what

Kryspal Media is proprietary software. This repository holds release notes, the issue tracker and discussions; it does not contain source code.
