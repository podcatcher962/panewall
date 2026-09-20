# 联屏 PaneWall

把散落各处的直播源收拢成一面墙的**单文件播放器**。一个 HTML 文件、双击即用、离线可跑、什么都不用装。

A **single-file player** that gathers your scattered live sources into one wall — one HTML file, double-click to run, works offline, installs nothing.

**[中文](#中文) | [English](#english)**

在线版 · Online: <https://podcatcher962.github.io/panewall/>

---

## 中文

### 这是什么

一个纯本地运行的 M3U / M3U8 / IPTV 播放器。它**不提供、不内置、不推荐任何频道源** —— 频道全部来自你自己导入的文件或自己填写的地址。程序本身不会向任何服务器上传你的数据。

### 功能

| 类别 | 内容 |
|---|---|
| 导入 | m3u / m3u8 文件、整个文件夹、拖拽、粘贴网址；每个文件夹自动成为独立源库，互不混串 |
| 管理 | 分类筛选、中文与拼音搜索（首字母 + 全拼）、收藏、自建清单、音视频分开、多库切换与重命名 |
| 播放 | hls.js 优先、原生 HLS 回退、多线路自动重试、断流自动重连 |
| 画面 | 多画面墙（1 / 2 / 4 格）、画中画、全屏、比例切换、深色 / 浅色 / 跟随系统 |
| 录制 | 截图、录像、录音、定时录制 |
| 字幕 | **抓播放器内部声音**做实时识别与翻译 —— 不需要麦克风；可译成 30 多种语言，台自带字幕轨也能接过来一起翻 |
| 翻译 | 浏览器内置离线模型（免注册、不要 Key、文字不出本机）/ MyMemory / 硅基流动免费模型，三选一 |
| 状态 | 播放器上方实时状态条：连接用时、试到第几条线路、起播耗时、缓冲进度、下载速度；连不上会说明原因 |
| 其他 | 一键字幕、一键体检、键盘与触摸操作、中文 / English 双语界面、JSON 备份与恢复 |

### 用哪个版本

| | 在线版（浏览器打开） | 本地版（下载文件双击） |
|---|---|---|
| 装什么 | 什么都不用 | 什么都不用 |
| http 源 | **播不了** —— 见下方说明 | 可以 |
| 数据 | 存在你浏览器里 | 存在你浏览器里 |
| 适合 | 试玩、分享给别人看 | 日常使用 |

**在线版为什么播不了 http 源**：GitHub Pages 走 https，网页在 https 下再去加载 http 的流，会被浏览器当成「混合内容」直接拦掉，这是浏览器的安全策略，不是本工具的限制。很多直播源恰恰是 http。所以：

- 想**试玩**、想**发给别人看一眼界面** → 用在线版
- 想**真的看** → 把 `PaneWall.html` 下载下来，双击用浏览器打开，本地打开没有这条限制

### 怎么用

1. 打开 `PaneWall.html`
2. 点「导入」，选你的 .m3u 文件，或整个文件夹，或粘贴一个网址
3. 左侧点频道即可播放
4. 播放条上的「字幕」按钮是一键开关：点一下自动选好识别引擎和免费翻译通道并开始出字幕；改设置请右键（手机长按）那个按钮

### 免责声明

1. 本工具是一个**纯本地的播放器工具**，不提供、不存储、不分发任何直播内容或频道源。所有频道数据来自你自行导入的文件或你自己填写的地址。
2. 本工具与任何电视台、内容平台、源站**均无关联**，也未经其授权或认可。频道名称、台标等权利归各自所有者。
3. 你在本工具中导入、播放、录制的一切内容，**仅保存在你自己的设备上**，不上传、不联网回传。
4. 网络直播源由第三方维护，其可用性、合法性、内容与画质**均不受本工具控制**，可能随时失效。
5. 请勿将本工具用于任何侵犯著作权、违反当地法律法规的用途。因使用本工具产生的任何后果，由使用者自行承担。
6. 本工具**不内置任何频道源**。请只导入你所在地区合法的、你有权访问的内容。
7. 本工具按「现状」提供，不附带任何明示或暗示的担保。

### 技术

- 单文件 HTML，内嵌 [hls.js](https://github.com/video-dev/hls.js/)（Apache-2.0）
- 无外部请求、无追踪、无统计；断网可用（在线字幕的识别与翻译除外）
- 数据存在浏览器 `localStorage`，清缓存会清掉，请用「导出备份」

### 名字

「联」是把散落各处的直播源联成一体，「屏」是那面同屏并列的画面墙。英文名 PaneWall 讲的是同一件事的另一头：pane 是窗玻璃的一格，wall 是许多格子并排成的那面墙 —— 一格一格拼起来，才成一面墙。

---

## English

### What it is

A purely local M3U / M3U8 / IPTV player. It **does not provide, bundle or recommend any channel source** — every channel comes from a file you import or a URL you type. Nothing you do is uploaded anywhere.

### Features

| Area | What you get |
|---|---|
| Import | .m3u / .m3u8 files, whole folders, drag & drop, paste a URL. Each folder becomes its own source library, never mixed |
| Organise | Category filter, Chinese and pinyin search (initials + full pinyin), favourites, custom lists, audio/video split, switchable libraries |
| Playback | hls.js first with native HLS fallback, multi-line retry, automatic reconnect |
| Viewing | Multi-view wall (1 / 2 / 4 panes), picture-in-picture, full screen, aspect fit, dark / light / system theme |
| Capture | Snapshot, video recording, audio recording, scheduled recording |
| Subtitles | **Taps the player's own audio** for live speech-to-text and translation — no microphone needed; 30+ target languages; a channel's own subtitle track is translated too |
| Translation | Built-in browser offline model (no signup, no key, text never leaves your machine) / MyMemory / SiliconFlow free models — pick one |
| Status | A live status bar above the player: connect time, which line is being tried, start-up time, buffer, download speed; failures explain themselves |
| And | One-click subtitles, one-click health check, keyboard and touch controls, Chinese / English UI, JSON backup and restore |

### Which build

| | Online (open in a browser) | Local (download and double-click) |
|---|---|---|
| Install | nothing | nothing |
| http sources | **will not play** — see below | fine |
| Data | stays in your browser | stays in your browser |
| Best for | trying it out, showing someone | everyday use |

**Why the online build can't play http sources**: GitHub Pages is served over https, and a page on https loading an http stream is blocked by the browser as *mixed content*. That is a browser security rule, not a limitation of this tool — and plenty of live sources are http. So use the online build to try the interface, and download `PaneWall.html` for real use.

### Usage

1. Open `PaneWall.html`
2. Click **Import** — pick a .m3u file, a whole folder, or paste a URL
3. Click any channel in the left list to play
4. The **Subtitles** button on the player bar is a one-click switch: one click lines up a recognition engine plus free translation and starts captioning. Right-click it (long-press on a phone) for settings.

### Disclaimer

1. This is a **purely local player tool**. It does not provide, store or distribute any broadcast content or channel source. All channel data comes from files you import or URLs you enter.
2. It is **unaffiliated with** and unendorsed by any broadcaster, platform or source. Channel names and logos belong to their owners.
3. Anything you import, play or record stays **on your own device** — nothing is uploaded.
4. Streams are maintained by third parties; their availability, legality, content and quality are **outside this tool's control** and may break at any time.
5. Do not use this tool to infringe copyright or violate local law. You bear all consequences of use.
6. This tool **bundles no channel source**. Import only content that is lawful and that you are entitled to access where you are.
7. Provided "as is", without warranty of any kind.

### Technical

- Single HTML file with [hls.js](https://github.com/video-dev/hls.js/) (Apache-2.0) embedded
- No external requests, no tracking, no analytics; works offline (except live subtitle recognition and translation)
- Data lives in browser `localStorage` — clearing it wipes your lists, so use **Export backup**

### The name

The Chinese name 联屏 says it from one end — "linked screens". PaneWall says the same thing from the other: a pane is one square of glass, a wall is what you get when many of them are set side by side.

---

© 永远的兰兰 (Lanlan Eternal). 可自由使用、原样转发，请保留署名。若要改动，请只留给自己看，改过的版本不要对外分发。保留所有权利。
