# PDF 页面尺寸工具 / PDF Page Size Tool

## 中文
> 起因：macOS 自带的预览和我试过的几款 PDF 工具，在合并页面尺寸不一致的
> 文件时都会把版面弄乱。找不到能用的，就自己写了一个。

一个纯前端的小工具，用来处理 PDF 合并时页面大小不一致的问题。基于 [pdf-lib](https://pdf-lib.js.org/) 实现，所有处理都在浏览器本地完成，文件不会上传到任何服务器。界面支持中文、English、Deutsch 三种语言切换。

### 功能

- 拖拽或选择多个 PDF 文件，自动检测每一页的尺寸（识别 A4 / Letter / Legal / A3 / A5 等标准纸张，非标准尺寸会标出具体 mm 数值）
- 当同一批文件里页面尺寸不一致时，自动标出与多数页面不同的页
- 两种处理模式：
  - **保留原始尺寸合并**：按文件顺序拼接，每页尺寸保持不变
  - **统一为指定尺寸**：选择 A4 / Letter 或自定义 mm 尺寸，所有页面等比缩放、居中放入目标画布，多余部分留白，不裁切、不变形
- 处理完成后直接在浏览器中下载生成的 PDF
- 右上角可切换界面语言：中文 / English / Deutsch

### 使用方法

直接用浏览器打开 `index.html`，或部署到 GitHub Pages 后通过链接访问。首次加载需要联网获取字体和 pdf-lib 库，之后的 PDF 处理过程完全离线、本地运行。

### 技术实现

单文件 HTML + 原生 JS，通过 CDN 引入 [pdf-lib](https://cdnjs.cloudflare.com/ajax/libs/pdf-lib/1.17.1/pdf-lib.min.js) 完成页面读取、合并与缩放。

---

## English
> Built because neither macOS Preview nor the PDF tools I tried could merge
> files with mismatched page sizes without wrecking the layout.

A pure front-end tool for handling PDFs with mismatched page sizes when merging. Built on [pdf-lib](https://pdf-lib.js.org/); everything runs locally in the browser and files are never uploaded to any server. The interface supports Chinese, English, and German.

### Features

- Drag and drop or select multiple PDF files; each page's size is detected automatically (recognizing standard paper sizes like A4 / Letter / Legal / A3 / A5, with exact mm dimensions shown for non-standard sizes)
- When page sizes differ within a batch, pages that don't match the majority size are flagged
- Two processing modes:
  - **Merge, keep original sizes** — concatenates pages in file order, each page keeps its original size
  - **Normalize to one size** — choose A4 / Letter or a custom mm size; every page is scaled proportionally and centered on the target canvas, with extra space left blank (never cropped or distorted)
- Download the generated PDF directly from the browser once processing finishes
- Switch the interface language (Chinese / English / German) from the top right

### Usage

Open `index.html` directly in a browser, or deploy it to GitHub Pages and access it via the link. The first load needs an internet connection to fetch the font and the pdf-lib library; PDF processing itself then runs fully offline and locally.

### Implementation

A single HTML file with vanilla JS, using [pdf-lib](https://cdnjs.cloudflare.com/ajax/libs/pdf-lib/1.17.1/pdf-lib.min.js) via CDN to read, merge, and scale pages.
