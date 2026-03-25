# Pandoc-Literary-novel-Theme
“Pandoc Literary-novel Theme” 文艺小说风格，适合电子书、小说、散文。

一个为小说、散文等文艺作品设计的 Pandoc 主题，风格极简、优雅，适配屏幕阅读与打印。

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

小说格式演示：[http://pandoc-theme.morlvoid.pro/](http://pandoc-theme.morlvoid.pro/)
或查看“演示副本.png”

## 特性

- 📱 响应式设计：手机、平板、电脑自动适配字号
- 🌗 深色模式：跟随系统偏好
- 📖 完整目录：`--toc` 自动生成，链接清晰可点
- 🎨 封面与题词：支持自定义封面页和题词页
- ✍️ 中文排版：首行缩进、标点悬挂、适配思源宋体
- 🖨️ 打印优化：A5 纸张、页眉页脚、分页控制

## 快速开始

### 第一步：安装 Pandoc

1. 访问 [Pandoc 官网](https://pandoc.org/installing.html) 下载对应系统的安装包。

   也可以尝试：

   ```bash
   winget install --source winget --exact --id JohnMacFarlane.Pandoc
   ```

   安装。

2. 安装完成后，打开终端（命令提示符或 PowerShell）输入以下命令验证：

   ```bash
   pandoc --version
   ```

   若显示版本信息，则安装成功。

------

### 第二步：下载主题

1. 克隆或下载本主题仓库：

   ```bash
   git clone https://github.com/Morlvoid/Pandoc-Literary-novel-Theme
   ```

   或直接下载 ZIP 包并解压。

2. 将主题文件 `theme.css` 复制到你的电子书项目根目录（即与 `.md` 文件同一文件夹）。

------

### 第三步：准备你的 Markdown 源文件

#### 单个文件电子书

如果你的电子书只有一个 Markdown 文件（例如 `novel.md`），确保文件开头包含 YAML 元数据（可选，但推荐）：

markdown

```
---
title: "书名"
author: "作者名"
subtitle: "副标题"
---
```



正文使用 Markdown 语法编写。

#### 单个文件电子书

示例：

```bash
pandoc example.md -s --toc --embed-resources --standalone -c theme.css -o example.html
```



#### 多个文件电子书

若你有多个章节文件（如 `01-intro.md`、`02-chapter1.md` 等），Pandoc 支持一次输入多个文件并按顺序合并。你无需手动合并，只需在命令中列出所有文件。

#### **推荐结构**：

```text
my-book/
├── theme.css
├── 01-序.md
├── 02-第一章.md
├── 03-第二章.md
└── 04-尾声.md
```



每个章节文件内部使用 `#` 或 `##` 等标题，但全书只能有一个一级标题（通常放在第一个文件作为书名）。

------

#### 第四步：生成 HTML 电子书

在终端中进入你的项目根目录（包含 `theme.css` 和所有 `.md` 文件），执行以下命令：

```bash
pandoc 01-序.md 02-第一章.md 03-第二章.md 04-尾声.md \
  -s --toc --embed-resources --standalone \
  -c theme.css \
  -o mybook.html
```

**参数说明**：

- `-s` / `--standalone`：生成完整 HTML 文档（含 `<head>`、`<body>` 等）。
- `--toc`：自动生成目录（基于所有标题）。
- `--embed-resources`：将 CSS 内嵌到 HTML 中，生成独立文件。
- `-c theme.css`：指定主题样式。
- `-o mybook.html`：输出文件名。

如果你只有一个 Markdown 文件，只需将文件列表替换为 `novel.md`。

------

### 演示页面

点击可查看“演示副本.png”

------

## 示例：完整工作流

假设你的项目结构如下：

```text
my-novel/
├── theme.css
├── 00-title.md          # 包含 YAML 元数据及手动封面（可选）
├── 01-序幕.md
├── 02-第一章.md
├── 03-第二章.md
└── 04-尾声.md
```

**生成 HTML**：

```bash
cd my-novel
pandoc 00-title.md 01-序幕.md 02-第一章.md 03-第二章.md 04-尾声.md \
  -s --toc --embed-resources --standalone \
  -c theme.css \
  -o novel.html
```

------

## 🧩 高级技巧

### 自定义封面页

在 Markdown 中直接插入 HTML 代码即可实现自定义封面（本主题已预设 `.title-page` 样式）：

```html
<div class="title-page">
  <div class="subtitle">TEST VER. / FIRST VER.</div>
  <h1 class="title">日月尘事</h1>
  <div class="author">Morlvoid</div>
  <div class="botanical-decoration"></div>
</div>
```

### 题词页

```html
<div class="dedication">
“神不是死去的，<br>
他们只是沉入了自己的深渊。” <br>
——《日月尘事》终卷·按语<br>
<br>
当最后一缕依附于太阳神像的金箔在风中剥落，我们终于获得了直视深渊的资格。<br>
</div>
```

### 特殊章节样式

```html
<div class="chapter-entry">
<div class="chapter-number">001 · 前言</div>
正文开始...
</div>
```

### 使用变量自定义样式

主题使用 CSS 变量，你可以在 `theme.css` 的 `:root` 部分修改颜色、字体、边距等，轻松定制。



## 常见问题

**Q：为什么生成的 HTML 目录没有显示？**
A：检查你的 Markdown 中是否至少有一个一级标题（`#`）。`--toc` 需要标题才能生成目录。另外，浏览器窗口过窄时目录样式可能为全宽，但内容仍在。

**Q：手机端正文边距太大？**
A：主题已做响应式，手机端正文边距自动变为 1cm，若仍需调整，可修改 `@media (max-width: 768px)` 中的 `padding-left` 和 `padding-right`。

**Q：表格或图片未居中？**
A：主题已默认设置 `margin: auto`，若未生效，请检查是否被其他样式覆盖。可尝试在 Markdown 中用 `<div class="center">` 包裹。

**Q：如何生成带页码的 PDF？**
A：浏览器打印时可设置页眉页脚；若用 weasyprint，CSS 中的 `@page` 规则会自动添加页码。

**Q：目录点击报错 `Unsafe attempt to load URL`？**
A：由于浏览器安全策略，直接双击打开 HTML 文件时，锚点跳转可能受限。请使用本地 HTTP 服务器预览（如 `python -m http.server 8000`），或直接通过浏览器打印为 PDF 查看。

------

## 许可证

本主题采用 MIT 许可证，欢迎自由使用、修改和分享。

------

祝你制作出精美的电子书！如有任何问题，欢迎提交 issue。
