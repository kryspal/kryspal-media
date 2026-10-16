<p align="center"><a href="README.md">English</a> | 简体中文</p>

<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="assets/logo-dark.svg">
    <img alt="Kryspal Media" src="assets/logo-light.svg" height="56">
  </picture>
</p>

<p align="center"><strong>片库再大，依然飞快的媒体服务器。</strong></p>

<p align="center"><em>自托管，原画质播放，近 20 万部电影也不卡。</em></p>

<p align="center">
  <a href="https://github.com/kryspal/kryspal-media/releases"><img alt="Latest release" src="https://img.shields.io/github/v/release/kryspal/kryspal-media?style=flat&labelColor=0d1726&color=086a8b"></a>
  <img alt="Platforms: amd64 and arm64" src="https://img.shields.io/badge/platform-amd64%20%7C%20arm64-086a8b?style=flat&labelColor=0d1726">
  <img alt="Docker Compose" src="https://img.shields.io/badge/docker-compose-086a8b?style=flat&labelColor=0d1726">
  <img alt="Self-hosted" src="https://img.shields.io/badge/self--hosted-yes-086a8b?style=flat&labelColor=0d1726">
  <a href="https://github.com/kryspal/kryspal-media/discussions"><img alt="Discussions" src="https://img.shields.io/badge/discussions-join-086a8b?style=flat&labelColor=0d1726"></a>
</p>

<p align="center"><strong>官网：<a href="https://media.kryspal.net/zh/">media.kryspal.net/zh</a></strong></p>

<p align="center"><img alt="Kryspal Media 网页播放器首页" src="assets/viewer-home.webp" width="860"></p>

## 为什么做这个产品

- 片库一大，浏览和筛选越来越慢，扫描动辄数小时。
- 云盘挂载的片库请求太多，被限流，还怕连累账号。
- 围绕转码设计的服务器，让 NAS 处理器满载，其实播放器能直接播放。
- 文件名不规范时，一部电影被拆成多条，版本也混在一起。
- 核心功能锁在在线账号后面，离线就出问题。

Kryspal Media 把这些问题一一解决。

## 技术底座

- **Go 编写的服务器。** 单个静态可执行文件，占用低，NAS 上也轻快。
- **PostgreSQL 承担重活。** 查询、排序、筛选都在数据库里完成。
- **搜索更快。** 使用三元组和二元组索引。
- **原生媒体解析。** 用 Go 解析 MKV、MP4，并原生抽取内嵌字幕。
- **只封装，不转码。** 浏览器播放仅转封装，必要时才转音频，视频从不重新编码。
- **声纹识别片头片尾。** 整季比对，自动检测（PRO）。
- **插件隔离，目录签名。** 独立进程，经 gRPC 通信，校验哈希。
- **安全加固。** 非 root 运行，正式版经签名与完整性自检。

## 功能特色

- **超大片库依然飞快。** 近 20 万部电影，浏览不到 50 毫秒（NAS 实测）。
- **支持拼音模糊搜索。** 输入拼音或首字母，就能找到中文片名。
- **原画质，不转码。** 直接播放，4K、HDR 与无损音轨原样保留。
- **对云盘友好。** 直接播放你自己网盘上的 `.strm` 文件；局域网内可直连（PRO）。
- **沿用你的播放器。** 兼容 Emby、Jellyfin（12）的第三方播放器，可导入旧库。
- **文件名再乱也能整理。** 灵活的目录、多版本归并、名称识别（PRO）。
- **跳过片头片尾。** 手动标记，或自动检测（PRO）。
- **成员与家长控制。** 每位成员独立记录；可设观看时段（PRO）。
- **备份与还原。** 手动备份可用密码加密（PRO）。
- **插件与开放 SDK。** 官方开源插件，另有 Apache-2.0 协议的 Plugin SDK 供你自己写。
- **无需账号。** 一个邮箱加授权码；FREE 就是完整的媒体服务器。

## 安装

```sh
curl -fsSL https://media.kryspal.net/install.sh | bash -s -- --media /srv/media
```

把 `/srv/media` 换成你的媒体文件夹。更多文件夹请重复使用 `--media`。

NAS 请改用[安装指南](https://media.kryspal.net/zh/docs/install/)里的 Docker Compose 文件。

一个 Compose 文件，两个容器：服务器和 PostgreSQL。需要 Docker 和 Compose v2，64 位 Linux（amd64 或 arm64），建议 4 GB 内存。

[版本发布](https://github.com/kryspal/kryspal-media/releases)

## 方案

FREE、PRO、MAX 的区别见[价格](https://media.kryspal.net/zh/pricing/)。

## 插件

开源插件：[tmdb](https://github.com/kryspal/plugin-tmdb)、[fanart](https://github.com/kryspal/plugin-fanart)、[dlna](https://github.com/kryspal/plugin-dlna)、[opensubtitles](https://github.com/kryspal/plugin-opensubtitles)、[assrt](https://github.com/kryspal/plugin-assrt)、[introdb](https://github.com/kryspal/plugin-introdb)。

想自己写插件，见 [Plugin SDK](https://github.com/kryspal/plugin-sdk)。插件的问题请到该插件自己的仓库反馈。

## 获取帮助

[文档](https://media.kryspal.net/zh/docs/) · [Discussions](https://github.com/kryspal/kryspal-media/discussions) · [Issues](https://github.com/kryspal/kryspal-media/issues) · [SUPPORT.md](SUPPORT.md)

Kryspal Media 是闭源软件。本仓库只有发布说明、问题跟踪和讨论区，不含源代码。
