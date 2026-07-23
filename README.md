# AtomBook

**Minimal, beautiful EPUB reader for the web — part of the Atom ecosystem**

> A single HTML file. No install. No backend. No subscription.  
> Reads beautifully. Syncs quietly via your cloud drive.

---

## Features

- **Zero install** — one `index.html`, runs in any modern browser via GitHub Pages
- **Apple Books-quality typography** — Spectral + Noto Serif SC, Apple-style sepia / day / night themes
- **Dual-column layout** — wide-screen two-page spreads with book-spine detail line
- **Highlight & annotate** — four-color highlighting with linked notes panel
- **Cloud sync via local folder** — saves `atombook.json` to any folder your drive syncs (Baidu Netdisk, OneDrive, iCloud Drive, etc.)
- **PWA installable** — pin to taskbar from Chrome; runs as a standalone app with no browser chrome
- **Chrome Translation** — works natively since the reader is a real web page
- **Keyboard friendly** — `←` `→` to turn pages, `Space` to advance, `Esc` to close panels
- **Progress memory** — restores your exact position across sessions and devices

---

## Quick Start

### Use immediately (local, no deploy)

1. Download `index.html`
2. Open Chrome → drag the file onto a Chrome window
3. Drag any `.epub` file into the reader and start reading

> Chrome Translation and PWA install require HTTPS — use GitHub Pages for those features.

### Deploy to GitHub Pages

```
1. Create a new GitHub repository (e.g. "atombook")
2. Upload index.html to the repository root
3. Go to Settings → Pages → Source: Deploy from branch → Branch: main → / (root) → Save
4. Wait ~60 seconds → visit https://<your-username>.github.io/atombook/
```

Chrome will show a **⊕ Install AtomBook** button in the address bar — click to install as a PWA.

---

## Sync Setup

AtomBook uses the browser's **File System Access API** to read and write a local JSON file.  
Your cloud drive syncs that file automatically — no account, no server.

```
1. Open AtomBook → click "Connect…" at the bottom of the splash screen
2. Pick a folder inside your cloud drive's sync directory
   (e.g. C:\Users\You\Baidu Netdisk\Reading)
3. AtomBook saves atombook.json there — highlights, notes, and progress
4. On any other PC: open AtomBook → Connect… → pick the same synced folder → data loads
```

**Tip:** Only sync the JSON file this way. Keep epub files wherever you like locally — the reader loads them fresh each time you drag them in.

---

## Usage

| Action | How |
|---|---|
| Open a book | Drag `.epub` onto the page, or click **Open File…** |
| Turn page | Click arrow buttons, or press `←` `→` / `Space` |
| Change theme | Click the ◑ icon → Day / Sepia / Night |
| Adjust font size | Click **A−** / **A+** in the toolbar |
| View chapters | Click the ≡ icon (TOC panel slides in from left) |
| Highlight text | Select any text → choose a color dot |
| Add a note | Select text → click **Note** |
| View all highlights | Click the 💬 icon (Notes panel slides in from right) |
| Sync cloud data | Click **Connect…** on the splash screen |
| Close book | Click the small logo in the toolbar → returns to splash |

---

## Tech Stack

| Layer | Technology |
|---|---|
| EPUB rendering | [epub.js](https://github.com/futurepress/epub.js) 0.3.x |
| Typography | Spectral, Noto Serif SC (Google Fonts) |
| Persistence | File System Access API + IndexedDB |
| PWA | Blob-URL manifest + blob-URL service worker |
| Runtime | Vanilla JS — no framework, no build step |

---

## Known Limitations

- Highlight position is stored as an epub.js CFI string; complex fixed-layout EPUBs may not restore highlight positions perfectly
- The File System Access API requires a user gesture to re-authorize on each browser restart (click **Connect…** once per session)
- PWA install prompt only appears on HTTPS (GitHub Pages), not on local `file://` access
- No iOS/Android support — mobile browsers do not support the File System Access API

---

## Atom Ecosystem

AtomBook is part of the **Atom** project family — a personal toolkit of focused, minimal web tools, each a single file, each hosted on GitHub Pages. No backends, no accounts, no subscriptions.

---

## License

MIT — do whatever you want with it.

---
---

# AtomBook · 中文说明

**简约优雅的网页端 EPUB 阅读器 — Atom 生态系列之一**

> 单个 HTML 文件。无需安装。无后端。无订阅。  
> 排版精致。通过云盘静默同步。

---

## 功能特性

- **零安装** — 一个 `index.html`，通过 GitHub Pages 在任意现代浏览器中运行
- **接近 Apple 图书的排版质感** — Spectral + 思源宋体，sepia / 日间 / 夜间三套主题
- **双栏布局** — 宽屏下显示两页对开，带书脊装饰线
- **高亮与注释** — 四色高亮，附带笔记面板
- **云盘同步** — 将 `atombook.json` 保存到云盘同步文件夹（百度网盘、OneDrive 等均可）
- **PWA 可安装** — 在 Chrome 中固定到任务栏，以独立应用窗口运行
- **Chrome 翻译** — 网页原生支持，可直接翻译书中内容
- **键盘操作** — `←` `→` 翻页，`Space` 前进，`Esc` 关闭面板
- **进度记忆** — 跨设备恢复上次阅读位置

---

## 快速开始

### 本地直接使用（无需部署）

1. 下载 `index.html`
2. 打开 Chrome → 将文件拖入 Chrome 窗口
3. 将任意 `.epub` 文件拖入阅读器，即可开始阅读

> Chrome 翻译和 PWA 安装需要 HTTPS，使用 GitHub Pages 部署后方可体验这两项功能。

### 部署到 GitHub Pages

```
1. 新建 GitHub 仓库（如 "atombook"）
2. 将 index.html 上传到仓库根目录
3. 进入 Settings → Pages → Source: Deploy from branch → Branch: main → / (root) → Save
4. 等待约 60 秒 → 访问 https://<你的用户名>.github.io/atombook/
```

Chrome 地址栏右侧会出现 **⊕ 安装 AtomBook** 按钮，点击即可作为 PWA 安装到桌面。

---

## 同步设置

AtomBook 使用浏览器的 **File System Access API** 读写本地 JSON 文件，你的云盘自动同步该文件，无需账号和服务器。

```
1. 打开 AtomBook → 点击底部的"Connect…"
2. 选择云盘同步目录中的某个文件夹
   （例如 C:\Users\你的名字\百度网盘\Reading）
3. AtomBook 将 atombook.json 保存在此处 — 包含高亮、笔记和阅读进度
4. 在其他电脑上：打开 AtomBook → Connect… → 选择同一个同步文件夹 → 数据自动加载
```

**提示：** epub 文件无需放入同步文件夹，每次拖入阅读器即可本地加载。

---

## 操作说明

| 操作 | 方式 |
|---|---|
| 打开书籍 | 将 `.epub` 拖入页面，或点击**Open File…** |
| 翻页 | 点击箭头按钮，或按 `←` `→` / `Space` |
| 切换主题 | 点击 ◑ 图标 → 日间 / Sepia / 夜间 |
| 调整字号 | 点击工具栏 **A−** / **A+** |
| 查看章节 | 点击 ≡ 图标（目录面板从左侧滑入） |
| 高亮文本 | 选中任意文本 → 选择颜色圆点 |
| 添加笔记 | 选中文本 → 点击 **Note** |
| 查看所有高亮 | 点击 💬 图标（笔记面板从右侧滑入） |
| 连接云同步 | 在启动页点击 **Connect…** |
| 关闭书籍 | 点击工具栏小图标 → 返回启动页 |

---

## 已知限制

- 高亮位置以 epub.js CFI 字符串存储；复杂固定布局的 EPUB 可能无法精确还原高亮位置
- File System Access API 需要每次浏览器重启后点击一次 Connect… 重新授权
- PWA 安装提示仅在 HTTPS（GitHub Pages）下出现，本地 `file://` 访问不支持
- 不支持 iOS / 安卓 — 移动端浏览器尚不支持 File System Access API

---

## Atom 生态

AtomBook 是 **Atom** 项目家族的一员 — 一套个人工具集，每个工具都是单个文件，托管在 GitHub Pages 上，无后端、无账号、无订阅。

---

## 许可证

MIT — 随意使用。
