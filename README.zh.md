<div align="center">

# Markdown 编辑器

一款在浏览器里「即开即用」的 Markdown 写作工具。<br>
**无安装、无账号、无订阅，你的文字只属于你。**

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)[![纯前端](https://img.shields.io/badge/Architecture-Pure%20Frontend-success)](./markdown-editor.html)[![多语言](https://img.shields.io/badge/I18N-10%20Languages-orange)](./i18n.js)

<p align="center">
  <a href="./README.md" style="display:inline-block;padding:6px 18px;background:#f3f4f6;color:#4b5563;border-radius:6px 0 0 6px;text-decoration:none;font-weight:600;">English</a>  |  <a href="./README.zh.md" style="display:inline-block;padding:6px 18px;background:#4f46e5;color:#fff;border-radius:0 6px 6px 0;text-decoration:none;font-weight:600;">简体中文</a>
</p>

</div>

<p align="center">
  <img src="public/产品海报.png" width="100%" alt="Markdown 编辑器主界面" />
</p>

---

## 🌟 为什么做这个工具？

AI 时代，Markdown 这件事，本该足够简单。

作为一个喜欢死磕 Prompt、Agent、Skills 的 Vibe Coding 开发者，我用过太多的 Markdown 工具：有的太重，有的订阅太贵，有的动不动就云端同步你的内容。我只想打开浏览器，输入文字，看到排版，然后把它带走。

于是有了这个编辑器。

它只有**一个 HTML 文件**。双击打开就能写，所有数据都存在本地，断网也能继续。它几乎支持 Codex、Claude Code、Openclaw 等市面上所有的 Agent，无论是 AGENTS.md 还是 Skill.md，你都可以通过它完成设计。

> 如果你也相信：AI 时代，markdown 就是第一语言。欢迎你来用、来改、来 Star。

---

## ✨ 功能特性

### 🚀 即开即用，极简使用

- 单文件 `markdown-editor.html`，双击即可在浏览器中运行。
- 所有核心样式、结构、逻辑内联在 HTML 中，离线也能使用。

### 🖊️ 完整的 Markdown 体验
- **拖拽导入**：直接把文件拖进来。
- **实时预览**：左侧写作，右侧同步预览。
- **双栏/单栏/纯预览布局**：支持「编辑 + 预览」「仅编辑」「仅预览」三种模式，自由切换。
- **源码模式**：右侧可直接编辑 Markdown 源码，所见即所得。
- **拖拽分栏**：拖动中间分隔线调整编辑区与预览区比例，位置自动记忆。

### 🛠️ 丰富的编辑工具

| 功能 | 说明 |
|------|------|
| 标题 | H1-H6 快速插入 |
| 文本样式 | 加粗、斜体、下划线、删除线、上标、下标 |
| 列表 | 无序列表、有序列表、任务列表 |
| 引用与代码 | 引用块、行内代码、代码块 |
| 链接与图片 | 支持 URL 插入与本地图片 Base64 嵌入 |
| 表格 | 可视化 8×8 表格选择器 |
| 查找替换 | 支持查找下一个、替换、全部替换 |

### 🌐 多语言支持（10 种语言）

内置 `i18n.js`，支持：**简体中文、繁体中文、English、日本語、한국어、Español、Français、Deutsch、Русский、Português**。

语言状态会持久化到 `localStorage`，下次打开自动沿用。

### 🎨 深色 / 浅色主题

- 一键切换深色/浅色模式，主题偏好自动保存。
- 所有颜色使用 CSS 变量定义，扩展或覆盖都非常方便。

### 💾 本地自动保存

- 编辑器每 500ms 自动保存内容到浏览器 `localStorage`。
- 意外关闭、刷新页面，内容都会自动恢复。
- 文件名、分栏比例、折叠状态、主题、语言等偏好也会一并记忆。

### 📤 多格式导出

| 格式 | 说明 |
|------|------|
| `.md` | 原始 Markdown 文件 |
| `.html` | 独立 HTML 文件，可直接在浏览器打开 |
| `.doc` | Word 文档（可直接在 office 里打开） |
| `.pdf` | 调用浏览器，打印为 PDF |
| `.png` | 长图导出，支持 9:16、4:5、3:4、1:1、16:9 多种比例，适合小红书、公众号、Instagram 分享 |

### ⌨️ 快捷键

| 快捷键 | 功能 |
|--------|------|
| `Ctrl + S` | 保存 |
| `Ctrl + Z` | 撤销 |
| `Ctrl + Y` / `Ctrl + Shift + Z` | 重做 |
| `Ctrl + B` | 加粗 |
| `Ctrl + I` | 斜体 |
| `Ctrl + U` | 下划线 |
| `Ctrl + K` | 插入链接 |
| `Ctrl + Shift + K` | 插入图片 |
| `Ctrl + F` | 查找替换 |
| `Tab` | 插入 4 空格缩进 |

---

## 🛠️ 技术架构

### 技术栈

- **纯原生前端**：HTML5 + CSS3 + Vanilla JavaScript，无框架依赖。
- **Markdown 渲染**：`marked.js`
- **数学公式**：`KaTeX`（支持 `$...$` 行内公式和 `$$...$$` 块级公式）
- **图表渲染**：`Mermaid 10`支持思维导图和流程图
- **图片导出**：`dom-to-image-more`
- **本地代理**：`Python 3` + `http.server`（可选，用于网页转 Markdown）

### 核心设计

```
┌─────────────────────────────────────────────────────────────┐
│                    markdown-editor.html                      │
│  ┌──────────────┐         ┌──────────────┐                  │
│  │  Editor      │  同步   │  Preview     │                  │
│  │  (textarea)  │ ──────▶ │  (marked.js) │                  │
│  └──────────────┘         └──────────────┘                  │
│         │                         │                         │
│         ▼                         ▼                         │
│   localStorage               KaTeX / Mermaid               │
│         │                         │                         │
│         ▼                         ▼                         │
│   自动保存 / 状态恢复        公式 / 图表渲染               │
└─────────────────────────────────────────────────────────────┘
                              │
                              ▼
                   web-to-md-proxy.py (可选)
                    网页抓取 + 反爬绕过
```
---

## 📁 项目结构

```
.
├── markdown-editor.html    # 主编辑器（单文件应用）
├── i18n.js                 # 多语言字典（10 种语言）
├── web-to-md-proxy.py      # 本地代理脚本（可选）
├── public/                 # 静态资源
│   ├── 关于作者.md
│   ├── 产品海报.png
│   ├── 产品界面.png
└── README.md               # 本文件
```

---

## 🚀 快速开始

### 方式一：直接打开（最简单）

```bash
# 克隆项目
git clone https://github.com/woyin2024/lengyi-markdown-editor.git

# 直接双击打开
markdown-editor.html
```

### 方式二：本地服务器（推荐）

```bash
cd markdown-editor

# Python 3
python -m http.server 8080

# 或 Node.js
npx serve .

# 打开浏览器访问
open http://localhost:8080/markdown-editor.html
```

### 方式三：使用本地代理（网页转 Markdown）

```bash
# 安装 requests（可选，推荐）
pip install requests

# 启动代理
python web-to-md-proxy.py

# 默认端口 8765
# 在编辑器中勾选「使用本地代理」即可
```

---

## 🖼️ 界面预览

<p align="center">
  <img src="public/产品界面2.png" width="48%" />
  <img src="public/产品界面3-主题切换.png" width="48%" />
</p>

<p align="center">
  <img src="public/产品界面-多格式导出.png" width="48%" />
  <img src="public/产品界面-多语言支持.png" width="48%" />
</p>

---

## 🤝 参与贡献

这个项目诞生于「自己用着顺手」的需求，但我相信它还能更好。

如果你有任何想法——新功能、Bug 修复、界面优化、语言补充、文档改进——都非常欢迎：

1. Fork 本仓库
2. 创建你的特性分支：`git checkout -b feature/AmazingFeature`
3. 提交更改：`git commit -m 'Add some AmazingFeature'`
4. 推送分支：`git push origin feature/AmazingFeature`
5. 提交 Pull Request

---

## 📜 开源协议

本项目基于 [MIT License](LICENSE) 开源。

你可以自由使用、修改、分发，如需商用请获取授权。只希望你在某个安静的午后，用它写出让自己满意的文章时，能想起这个项目的起点。

---
## 👤 关于作者

**冷逸**，中国 Top AI 技术媒体「沃垠AI」博主，不会写代码的 Vibe Coding 开发者，喜欢死磕 Prompt、Skills 和 Agent。

- **全平台统一账户**：沃垠AI
- **内容矩阵**：公众号、小红书、知乎、GitHub、B站、X 等

欢迎关注公众号「沃垠AI」，获取更多 AI 干货：
<p align="center">
  <img src="public/公众号二维码.png" width="90%" alt="沃垠AI 公众号二维码" />
</p>

---
<div align="center">

### 如果它帮到了你，给个 ⭐ 吧。

**写得好，比什么都重要。**

</div>
