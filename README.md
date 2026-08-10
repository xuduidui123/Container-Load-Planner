# 📦 自动排柜工具（Container Loading Planner）

> 一个**纯前端、单文件、可离线**的集装箱拼柜/排柜工具。上传一批 PO 明细的 Excel → 自动算出能凑成几个整柜、哪些货拼哪个柜、剩下的走散货，并在原表最后加一列「排柜方案」导出。打开浏览器就能用，免安装、免费、数据不上传。

![license](https://img.shields.io/badge/license-MIT-blue.svg)
![deps](https://img.shields.io/badge/dependencies-0-brightgreen.svg)
![type](https://img.shields.io/badge/单文件-HTML-orange.svg)

## ✨ 在线体验

部署到 GitHub Pages 后即可访问：**[https://xuduidui123.github.io/container-loading-planner/](https://xuduidui123.github.io/Container-Load-Planner/)**

## 🎯 这是什么

仓库每月出货前，要人工把一堆 PO 按体积加起来、看能凑成几个集装箱、哪些走整柜、哪些走散货——费时又容易错。这个工具把它自动化：

- 上传 Excel（或 CSV / 直接粘贴），自动识别列
- 按客户、船期把货分组（不同客户 / 不同船期不混柜）
- 以体积凑柜、重量做红线，自动排出整柜与散货
- 结果在原表加一列「排柜方案」，导出成多 Sheet Excel

## 🧩 功能特性

- **上传导入**：支持 `.xlsx` / `.csv` 拖拽上传，也可从 Excel 直接粘贴；列自动识别 + 手动对应
- **分仓依据可自定义**：不同**客户**分开排柜；船期可选"按具体船期 / 按月份 / 不分"
- **各客户可用柜型**：每个客户单独勾选能用的柜型（有的客户不接受 20 尺柜）
- **柜型参数可编辑**：默认/期望体积、最大载重、柜型中文名（用于命名）
- **重量口径**：支持"每箱毛重（×箱数）"或"整批总重"
- **PO 拆分开关**：可选择是否允许一个 PO 拆到多个柜
- **成柜门槛**：可设最低成柜体积利用率，达不到的剩余货标为散货
- **柜名格式**：`日期船期客户-柜型序号`（如 `20260620船期客户C-40高柜1`），散货写"散货"
- **导出**：多 Sheet Excel（总表汇总 + 每客户一个 Sheet）、CSV、一键复制粘回 Excel
- **纯本地**：所有计算在浏览器完成，数据不上传服务器

## 🚀 快速开始

### 本地使用
下载 `index.html`，双击用浏览器（推荐 Chrome / Edge）打开即可。无需联网、无需安装。

### 部署到 GitHub Pages（供团队共用）
1. 新建仓库，例如 `container-loading-planner`
2. 上传本项目文件（确保根目录有 `index.html`）
3. 仓库 **Settings → Pages → Source** 选 `main` 分支、根目录 `/`，保存
4. 等一两分钟，得到网址发给同事即可

详细操作步骤见 [部署说明.md](./部署说明.md)。使用方法见 [使用说明.md](./使用说明.md)。

## 🔒 隐私说明

工具**完全在浏览器本地运行**，上传的表格只在你自己的电脑里解析，不会发送到任何服务器。

## 🛠️ 技术说明

- 单个 `index.html`，原生 HTML + CSS + JavaScript
- 内置 [SheetJS (xlsx)](https://sheetjs.com/) 用于读写 Excel（Apache-2.0 许可），已随文件打包，因此可离线运行
- 兼容现代浏览器（Chrome / Edge / Firefox / Safari）

## 📄 许可证

本项目代码采用 [MIT](./LICENSE) © 2026 Sherry。
内置的 SheetJS 库版权归 SheetJS LLC 所有，采用 Apache License 2.0。
