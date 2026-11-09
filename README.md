# Bio Research Forge · 单页介绍站

参考 https://www.textvision.top:666/webui-intro/ 的版式和配色，为 **Bio Research Forge**（MiniMax Code 社区插件）做的单页介绍。

## 打开方式

直接双击 `index.html` 即可。无构建、无框架、无外部依赖，字体走系统字体，图片在本地 `assets/`。

## 目录

```
bio-research-forge-intro/
├── index.html            单文件页面（内联 CSS + 一段放大查看脚本）
├── assets/
│   ├── overview.png      案例总览（5 张图 + 账本）
│   ├── volcano.png       火山图
│   ├── pca.png           样本 PCA
│   ├── heatmap.png       Top-30 基因热图
│   ├── boxplot.png       代表基因箱线图
│   └── enrichment.png    功能富集气泡图
└── preview/              渲染核对用的截图（可删，不影响页面）
```

## 部署

任意静态托管都能放：GitHub Pages、对象存储、nginx、`python -m http.server`。
上传 `index.html` + `assets/` 两个东西即可，不需要 Node、不需要构建。

本地起服务预览：

```bash
cd bio-research-forge-intro
python -m http.server 8080
# 打开 http://127.0.0.1:8080
```

## 维护

- 文案：直接改 `index.html`，各节用注释性的 `<section id="...">` 分开（能力 / 案例 / 安装 / 图集）。
- 换图：同名覆盖 `assets/*.png`，比例保持 2100×1650 或 1800×1500 最稳（横向图）。
- 配图来源：`mcode-case/case2/out/` 的 5 张图，示例数据（模拟）；7 个公共查询为 2026-11-09 真实执行。
- 内容口径与事实核对见 `mcode-article-pack-v2.md`；Review 报告见 `mcode-case/case2/review-report.md`。

## 声明

页面为作者自述，功能以实际安装版本与配置为准；示例数据为模拟，未使用未发表研究数据。
