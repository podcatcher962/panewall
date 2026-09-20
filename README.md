# 联屏 PaneWall

把散落各处的直播源收拢成一面墙的**单文件播放器**。一个 HTML 文件、双击即用、离线可跑、什么都不用装。

A **single-file player** that gathers your scattered live sources into one wall — one HTML file, double-click to run, works offline, installs nothing.

**[中文](#中文) | [English](#english)**

在线版 · Online: <https://podcatcher962.github.io/panewall/>

---

## 中文

### 这是什么

一个纯本地运行的 M3U / M3U8 / IPTV 播放器。它**不提供、不内置、不推荐任何频道源** —— 连第三方公开索引的地址也不预置，频道全部来自你自己导入的文件或自己填写的地址。程序本身不会向任何服务器上传你的数据。

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
| 其他 | 一键字幕、一键体检、键盘与触摸操作、中文 / English 双语界面（**默认跟随系统语言**，设置里可手动切换）、JSON 备份与恢复 |

### 三个版本，怎么选

| | 桌面版 exe（推荐） | 本地 HTML | 在线版 |
|---|---|---|---|
| 拿什么 | Release 里下载 `PaneWall.exe` | 下载 `web/PaneWall.html` | 直接打开网址 |
| 装什么 | 免安装，双击即用 | 什么都不用 | 什么都不用 |
| http 源 | 可以 | 可以 | **播不了** —— 见下方说明 |
| 截图 / 录像 / 录音 | **任何源都行**（本机代理） | 只对给了跨域许可的源有效 | 同左 |
| 实时字幕（抓内部音轨） | 可以，任何源 | 只对有跨域许可的源 | 同左 |
| 适合 | 日常使用 | 不想装 exe、想随手带走一个文件 | 试玩、分享给别人看 |

**桌面版多了什么**：exe 里自带一个**只监听本机**（127.0.0.1）的加速代理。浏览器有一条硬限制 —— 源不给跨域许可，页面就既截不了图、也录不了音、更抓不到音轨去做字幕。桌面版把这类请求先经你自己的电脑转一圈，浏览器就当成同源，于是**截图、录像、录音、实时字幕对任何源都能用**。数据始终在本机，代理不对外网开放。设置面板里有一键自检，会当场告诉你通没通；不想要就关掉，关掉即恢复直连（候选地址里始终留着一条直连兜底，代理出问题也不会因此看不了）。

**在线版为什么播不了 http 源**：GitHub Pages 走 https，网页在 https 下再去加载 http 的流，会被浏览器当成「混合内容」直接拦掉，这是浏览器的安全策略，不是本工具的限制。很多直播源恰恰是 http。所以：

- 想**试玩**、想**发给别人看一眼界面** → 用在线版
- 想**真的看** → 下载 exe，或者把 `PaneWall.html` 下载下来双击用浏览器打开，本地打开没有这条限制

### 桌面版（Windows）

1. 到 [Releases](https://github.com/podcatcher962/panewall/releases) 下载 `PaneWall.exe`，双击运行 —— 免安装、单文件、可离线
2. 首次运行若提示「Windows 已保护你的电脑」，点「更多信息 → 仍要运行」（未做代码签名，属正常现象）
3. 需要系统里有 **WebView2 运行时** —— Windows 10/11 一般自带；没有的话装一下微软官方的 [WebView2 Runtime](https://developer.microsoft.com/microsoft-edge/webview2/)（很小，装一次永久有效）

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

A purely local M3U / M3U8 / IPTV player. It **does not provide, bundle or recommend any channel source** — not even a preset link to a public index; every channel comes from a file you import or a URL you type. Nothing you do is uploaded anywhere.

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
| Proxy | The **desktop build** ships a local proxy (bound to `127.0.0.1` only) so that sources **without CORS headers** can still be snapshotted, recorded and transcribed; one-click self-test, can be switched off |
| And | One-click subtitles, one-click health check, keyboard and touch controls, Chinese / English UI (**follows your system language by default**, switchable in Settings), JSON backup and restore |

### Three builds, which one

| | Desktop exe (recommended) | Local HTML | Online |
|---|---|---|---|
| What to get | `PaneWall.exe` from Releases | `web/PaneWall.html` | just open the URL |
| Install | none — double-click | nothing | nothing |
| http sources | fine | fine | **will not play** — see below |
| Snapshot / video / audio | **any source** (local proxy) | only sources that send CORS headers | same as left |
| Live subtitles from the player's own audio | any source | only sources that send CORS headers | same as left |
| Best for | everyday use | a single file you can carry anywhere | trying it out, sharing |

**What the desktop build adds**: the exe carries a local accelerator proxy bound to `127.0.0.1` only. Browsers have a hard rule — if a source sends no CORS headers, the page can neither snapshot it, nor record it, nor tap its audio for subtitles. The desktop build routes those requests through your own machine first, so the browser sees one origin and **snapshot, video recording, audio recording and live subtitles work on any source**. Everything stays local; the proxy is never exposed to the network. The settings panel has a one-click self-test; switch it off and you are back to a direct connection (a direct fallback is always kept at the end of the list of addresses, so a proxy problem never costs you the channel).

**Why the online build can't play http sources**: GitHub Pages is served over https, and a page on https loading an http stream is blocked by the browser as *mixed content*. That is a browser security rule, not a limitation of this tool — and plenty of live sources are http. So use the online build to try the interface, and download the exe or `PaneWall.html` for real use.

### Desktop build (Windows)

1. Download `PaneWall.exe` from [Releases](https://github.com/podcatcher962/panewall/releases) and run it — no install, one file, works offline
2. If Windows shows "Windows protected your PC", click **More info → Run anyway** (the binary is not code-signed)
3. You need the **WebView2 runtime**, which Windows 10/11 normally ships already; otherwise install Microsoft's [WebView2 Runtime](https://developer.microsoft.com/microsoft-edge/webview2/) once

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
- The desktop build is the same HTML plus a thin Python shell ([pywebview](https://pywebview.flowrl.com/) over the system WebView2 engine). The shell serves the page over a read-only service on `127.0.0.1`, so the page runs in a secure context (downloads, screen capture and offline storage all behave) and is not boxed in by `file://` origin rules
- The local proxy **listens on `127.0.0.1` only** — never on the LAN or the internet. It forwards only the playback requests the page itself makes, collects and reports nothing, and stops the moment you switch it off

### The name

The Chinese name 联屏 says it from one end — "linked screens". PaneWall says the same thing from the other: a pane is one square of glass, a wall is what you get when many of them are set side by side.

---

© 永远的兰兰 (Lanlan Eternal). 可自由使用、原样转发，请保留署名。若要改动，请只留给自己看，改过的版本不要对外分发。保留所有权利。
