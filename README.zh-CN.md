<p align="center"><a href="README.md">English</a> | 简体中文</p>

<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="assets/logo-dark.svg">
    <img alt="Kryspal Media" src="assets/logo-light.svg" height="56">
  </picture>
</p>

# Kryspal Media

**你的片库，值得好好播放。** 一款快速的自托管媒体服务器，管理你自己的电影和剧集。用 Docker 装在 NAS 或任何小型主机上，就能在你已有的设备上观看。

**官网：[media.kryspal.net/zh](https://media.kryspal.net/zh/)**

<p align="center"><img alt="Kryspal Media 网页播放器首页" src="assets/viewer-home.webp" width="860"></p>

## 为什么做这个产品

<!-- DRAFT: 负责人会换成自己的真实经历（与英文 README 的 "Why we built it" 一起定稿）。 -->
我们喜欢把影视资料握在自己手里，可用过的媒体服务器总是不太顺手。片库一大，浏览和筛选就越来越慢，扫描一次动辄几个小时。片库放在云盘挂载上时，扫描和读取媒体信息会向云盘发出大量请求，被限流不说，还担心连累账号。有的服务器围绕转码设计，NAS 的处理器常年满载，可大多数播放器明明可以直接播放原文件。文件名不规范时，匹配乱成一团：同一部电影被拆成好几条，不同版本混在一起。还有一些重要功能被锁在付费或在线账号后面，离线或者换一台机器就出问题。Kryspal Media 就是我们对这些问题的回答。

## 亮点

- **超大片库依然飞快。** 近 20 万部电影、5,000+ 部剧集依然秒开：在这个规模下浏览响应不到 50 毫秒，浏览与筛选比传统媒体服务器快最高 30 倍（NAS 实测，含测试库与真实片库）。
- **原画质，不转码视频。** 直接播放，4K、HDR 与无损音轨原样保留，一台小机器就够用。
- **对云盘友好。** `.strm` 文件无需存放视频就能从云盘播放；默认由服务器代理，开通 PRO 后可以在局域网内让播放器直连云盘。媒体信息何时读取，由你决定。
- **沿用你喜欢的播放器。** 兼容 Emby 或 Jellyfin 的第三方播放器照常连接，另有 Kryspal Media 自带的网页播放器。想换过来？可以从现有的 Emby 或 Jellyfin 服务器导入片库、成员和观看记录。
- **文件名再乱也能整理好。** 灵活的文件夹结构开箱即用，名称识别（PRO）处理剩下的情况；同一部电影的多个文件合成一个条目并可选择版本；TMDB ID 相同的剧集还能合并显示。
- **跳过片头片尾。** 手动标记一次就行，也可以让 PRO 自动检测并使用社区数据。
- **成员、设备与家长控制。** 每位成员都有自己的观看记录、续播位置和偏好；PRO 另有家长控制：内容规则、可观看时段和每日时长上限。
- **备份，随时换机。** 在管理后台备份和还原，手动备份可用密码加密（PRO），换新机器只需还原一次。
- **看得到源码、也能自己写的插件。** 元数据、图片、字幕和投屏都由插件提供，官方的开源插件配有 [Plugin SDK](https://github.com/kryspal/plugin-sdk)，你也可以写自己的。
- **无需账号，FREE 就是完整版。** 授权只是一个邮箱加一个授权码，付费功能在离线宽限期内照常可用。FREE 是完整的媒体服务器，不是试用版。

## 安装

Kryspal Media 用一个 Docker Compose 文件运行两个容器（服务器和 PostgreSQL）。每个[版本](https://github.com/kryspal/kryspal-media/releases)都列有 amd64 和 arm64 镜像。分步说明见[安装指南](https://media.kryspal.net/zh/docs/install/)。

## 方案

FREE、PRO 和 MAX 在额度和智能功能上有所不同，详见[价格](https://media.kryspal.net/zh/pricing/)。

## 插件

开源插件的源码都在 GitHub：[tmdb](https://github.com/kryspal/plugin-tmdb)、[fanart](https://github.com/kryspal/plugin-fanart)、[dlna](https://github.com/kryspal/plugin-dlna)、[opensubtitles](https://github.com/kryspal/plugin-opensubtitles)、[assrt](https://github.com/kryspal/plugin-assrt) 和 [introdb](https://github.com/kryspal/plugin-introdb)。

## 获取帮助

- [文档](https://media.kryspal.net/zh/docs/)
- [Discussions](https://github.com/kryspal/kryspal-media/discussions)：提问和想法
- [Issues](https://github.com/kryspal/kryspal-media/issues)：问题反馈和具体的功能需求
- [SUPPORT.md](SUPPORT.md)：什么问题去哪里问

Kryspal Media 是闭源软件。本仓库只有发布说明、问题跟踪和讨论区，不含源代码。
