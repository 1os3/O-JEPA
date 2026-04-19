# O-JEPA · Project Webpage

`O-JEPA` 项目主页的源代码。这是一个独立的、零构建的静态站点，自动部署到 GitHub Pages。

- 在线访问：<https://1os3.github.io/O-JEPA/>
- 仓库：<https://github.com/1os3/O-JEPA>

## 技术栈

- **零构建** · 单文件 `index.html` + 一份 `assets/style.css` + 一个 inline favicon
- **Tailwind CSS** · 通过官方 [Play CDN](https://cdn.tailwindcss.com) 加载
- **KaTeX 0.16** · 通过 jsDelivr 加载，自动渲染所有 `$…$` / `$$…$$` 公式
- **Google Fonts** · `Source Serif 4` (正文) + `Inter` (UI) + `Noto Serif SC` (中文) + `JetBrains Mono` (公式 / 代码)
- **架构图** · 全部使用纯 HTML + Tailwind 卡片 / 网格 / 字符箭头绘制，**无 SVG / 无 Canvas / 无图片资源**

## 目录结构

```
.
├── index.html                       # 主页面（单文件，arxiv 学术风）
├── assets/
│   └── style.css                    # 段落韵律 / 卡片 / TOC / KaTeX 微调
├── .github/workflows/
│   └── deploy-pages.yml             # GitHub Pages 自动部署
├── .gitignore
└── README.md
```

## 本地预览

任选其一：

```powershell
# 1. 直接双击 index.html
start index.html

# 2. 起一个本地静态服务器（推荐）
python -m http.server 5173
# 然后访问 http://localhost:5173
```

> 网页加载需要互联网（Tailwind / KaTeX / Google Fonts 均通过 CDN 拉取）。

## 部署到 GitHub Pages

仓库已自带 [`/.github/workflows/deploy-pages.yml`](.github/workflows/deploy-pages.yml)：

1. 把代码推送到 `main` 分支（或在 Actions 页手动触发 `Run workflow`）
2. 在仓库 **Settings → Pages → Build and deployment → Source** 处选择 `GitHub Actions`（**仅需一次**）
3. Actions 会把整个仓库根目录打包成 Pages 工件并自动部署
4. 部署完成后访问 `https://1os3.github.io/O-JEPA/`

## 内容组织

| 区块 | 锚点 | 说明 |
| --- | --- | --- |
| Hero | `#top` | 标题 / 副标题 / 作者 / 链接按钮 |
| Abstract | `#abstract` | 摘要与三大核心创新 |
| Introduction | `#introduction` | 端到端自动驾驶三大致命缺陷 |
| Methodology | `#methodology` | 完整 5 个小节 + 架构图 + O-HRM 振荡示意 |
| Training | `#training` | 两阶段训练 + 5 条损失公式 |
| Efficiency | `#efficiency` | 极度轻量化的四点分析 |
| Conclusion | `#conclusion` | 总结 |
| BibTeX | `#cite` | 引用条目 + 一键复制按钮 |
