<p align="center"><a href="README.md">English</a> | 简体中文</p>

<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="assets/logo-dark.svg">
    <img alt="Kryspal Media" src="assets/logo-light.svg" height="56">
  </picture>
</p>

<p align="center"><strong>片库再大，依然飞快的媒体服务器。</strong></p>

<p align="center"><em>自托管，原画质播放，近 20 万部电影也不卡。</em></p>

<p align="center"><strong>官网：<a href="https://media.kryspal.net/zh/">media.kryspal.net/zh</a></strong></p>

<p align="center"><img alt="Kryspal Media 网页播放器首页" src="assets/viewer-home.webp" width="860"></p>

## 为什么做这个产品

- 片库一大，浏览和筛选越来越慢，扫描动辄数小时。
- 云盘挂载的片库请求太多，被限流，还怕连累账号。
- 围绕转码设计的服务器，让 NAS 处理器满载，其实播放器能直接播放。
- 文件名不规范时，一部电影被拆成多条，版本也混在一起。
- 重要功能锁在付费或在线账号后面，离线、换机就出问题。

Kryspal Media 把这些问题一一解决。

## 亮点

- **超大片库依然飞快。** 近 20 万部电影，浏览不到 50 毫秒（NAS 实测）。
- **原画质，不转码。** 直接播放，4K、HDR 与无损音轨原样保留。
- **对云盘友好。** 直接播放 `.strm`；局域网内可直连云盘（PRO）。
- **沿用你的播放器。** 兼容 Emby、Jellyfin 的第三方播放器，可导入旧库。
- **文件名再乱也能整理。** 灵活的目录、名称识别（PRO）、多版本选择。
- **跳过片头片尾。** 手动标记，或自动检测（PRO）。
- **成员与家长控制。** 每位成员独立记录；可设观看时段（PRO）。
- **备份与换机。** 手动备份可用密码加密（PRO）。
- **插件与开放 SDK。** 官方开源插件，另有 Plugin SDK 供你自己写。
- **无需账号。** 一个邮箱加授权码；FREE 就是完整的媒体服务器。

## 安装

一个 Compose 文件，两个容器：服务器和 PostgreSQL。

支持 amd64 和 arm64。

[安装指南](https://media.kryspal.net/zh/docs/install/) · [版本发布](https://github.com/kryspal/kryspal-media/releases)

## 方案

FREE、PRO、MAX 的区别见[价格](https://media.kryspal.net/zh/pricing/)。

## 插件

开源插件：[tmdb](https://github.com/kryspal/plugin-tmdb)、[fanart](https://github.com/kryspal/plugin-fanart)、[dlna](https://github.com/kryspal/plugin-dlna)、[opensubtitles](https://github.com/kryspal/plugin-opensubtitles)、[assrt](https://github.com/kryspal/plugin-assrt)、[introdb](https://github.com/kryspal/plugin-introdb)。

想自己写插件，见 [Plugin SDK](https://github.com/kryspal/plugin-sdk)。

## 获取帮助

[文档](https://media.kryspal.net/zh/docs/) · [Discussions](https://github.com/kryspal/kryspal-media/discussions) · [Issues](https://github.com/kryspal/kryspal-media/issues) · [SUPPORT.md](SUPPORT.md)

闭源软件。本仓库只有发布说明、问题跟踪和讨论区，不含源代码。
