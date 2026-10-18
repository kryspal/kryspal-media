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

<p align="center"><strong><a href="https://demo.kryspal.net">在线演示</a></strong>：在浏览器里浏览示例片库和管理后台。仅含示例数据。</p>

<p align="center">状态：<strong>测试版</strong>。升级前请先备份数据库。</p>

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
- **音频指纹识别片头片尾。** 整季比对，自动检测（PRO）。
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

NAS 或想手动安装，请按下面的步骤用 Docker Compose。更多说明见[安装指南](https://media.kryspal.net/zh/docs/install/)。

一个 Compose 文件，两个容器：服务器和 PostgreSQL。需要 Docker 24 以上并带 Compose v2，64 位 Linux（amd64 或 arm64），建议 4 GB 内存。

### 1. 取得文件

从[版本发布](https://github.com/kryspal/kryspal-media/releases)页面下载 `compose.yaml`，放进一个空文件夹。没有 `.env` 文件，所有设置都在 `compose.yaml` 里。

### 2. 设置

编辑 `compose.yaml`：把 `/path/to/media:/media` 里的 `/path/to/media` 换成你的片库文件夹。每多一个片库文件夹，就多加一行。这是唯一要改的地方，数据库密码会在第一次启动时生成，并自动在两个容器之间共用。

媒体文件夹是刻意以可读写方式挂载的：字幕下载和 NFO 回写（都是可选功能，默认关闭）会把文件写在视频文件旁边。只有你打开这些功能，服务器才会往里写。

带文件 ACL 的 NAS（例如群晖）：在 `server` 服务里加上 `user: "<uid>:<gid>"`，填你媒体文件所有者的 uid 和 gid（用 `id -u`、`id -g` 查看）。

### 3. 启动

```sh
docker compose up -d
docker compose logs -f server      # 等到出现 "listening"
```

打开 `http://<主机>:5797`，按设置向导创建第一位管理员，然后在管理后台添加片库。

### 4. 连接播放器

在兼容 Emby 或 Jellyfin 的播放器里，服务器地址填 `http://<主机>:5797`。同一局域网内的播放器可能会自动找到服务器（需先在 compose 文件里启用 UDP 7359）。如果只用兼容 Jellyfin 的播放器，请在管理后台切换兼容模式。

### 端口

| 端口 | 用途 |
| --- | --- |
| 5797/tcp | HTTP：播放器、网页播放器、管理后台 |
| 7359/udp | 局域网自动发现（compose 文件里默认注释掉；如果主机上没有别的程序占用这个端口，例如 Emby，就去掉 `#`） |
| 5798/tcp | 仅供外网使用的端口（compose 文件里已有）：路由器只转发这一个端口，从它进来的请求视为来自家庭网络之外 |

PostgreSQL 不对主机开放端口。需要远程访问时，请在 5797 端口前放一个带 HTTPS 的反向代理。

### 升级

```sh
docker compose pull
docker compose up -d
```

升级前先备份：管理后台 → 备份，或执行 `docker compose exec postgres pg_dump -U mediaserver mediaserver > backup.sql`。

### 使用自己的 PostgreSQL

需要 PostgreSQL 16 或更新版本，并已安装 `pg_bigm` 扩展（以有权限的用户执行一次 `CREATE EXTENSION pg_bigm`）。从 `compose.yaml` 中删掉 `postgres` 服务、`pgdata` 卷和 `depends_on`，再把 `DATABASE_URL` 设为你的连接字符串。

### 卸载

`docker compose down` 会保留数据。`docker compose down -v` 会删除命名卷（设置和数据库）。移除容器不会碰你的媒体文件夹；服务器写进去的文件（下载的字幕、NFO）会留在原处。

[版本发布](https://github.com/kryspal/kryspal-media/releases)

### 镜像

| 镜像 | 标签 |
| --- | --- |
| `kryspal/kryspalmedia` | `0.9.0-beta`、`beta`、`latest` |
| `kryspal/kryspalmedia-postgres` | `16`（带 pg_bigm 的 PostgreSQL 16） |

## 方案

FREE、PRO、MAX 的区别见[价格](https://media.kryspal.net/zh/pricing/)。

## 插件

开源插件：[tmdb](https://github.com/kryspal/plugin-tmdb)、[fanart](https://github.com/kryspal/plugin-fanart)、[dlna](https://github.com/kryspal/plugin-dlna)、[opensubtitles](https://github.com/kryspal/plugin-opensubtitles)、[assrt](https://github.com/kryspal/plugin-assrt)、[introdb](https://github.com/kryspal/plugin-introdb)。

想自己写插件，见 [Plugin SDK](https://github.com/kryspal/plugin-sdk)。插件的问题请到该插件自己的仓库反馈。

## 获取帮助

[文档](https://media.kryspal.net/zh/docs/) · [Discussions](https://github.com/kryspal/kryspal-media/discussions) · [Issues](https://github.com/kryspal/kryspal-media/issues) · [SUPPORT.md](SUPPORT.md)

Kryspal Media 是闭源软件。本仓库放发布说明、compose 示例、安装说明、问题跟踪和讨论区，不含源代码。第三方组件及其许可见每个版本附带的 `NOTICE.md`。
