# Bio Research Forge · 单页介绍站

参考 https://www.textvision.top:666/webui-intro/ 的版式和配色，为 **Bio Research Forge**（MiniMax Code 社区插件）做的单页介绍。

**在线地址：https://presisitence.github.io/bio-research-forge-intro/**

页面用三个 case 说明能力：植物（拟南芥春化 FLC 通路）、医学（人 TP53 轴，肿瘤 vs 正常）、微生物（16S 属水平，健康 vs 代谢综合征）。三个 case 的公共查询都是真实执行的，示例数据表为模拟数据。

## 打开方式

直接双击 `index.html` 即可。无构建、无框架、无外部依赖，字体走系统字体，图片在本地 `assets/`。

## 目录

```
bio-research-forge-intro/
├── index.html            单文件页面（内联 CSS + 一段放大查看脚本）
├── assets/
│   ├── overview.png      植物 case 总览（5 张图 + 账本）
│   ├── volcano.png       火山图（植物）
│   ├── pca.png           样本 PCA（植物）
│   ├── heatmap.png       Top-30 基因热图（植物）
│   ├── boxplot.png       代表基因箱线图（植物）
│   ├── enrichment.png    功能富集气泡图（植物）
│   ├── medical-volcano.png  火山图（医学，TP53 轴）
│   ├── medical-boxplot.png  代表基因箱线图（医学）
│   ├── micro-pca.png     样本 PCA（微生物，12 样本 × 40 属）
│   └── micro-boxplot.png 代表属丰度箱线图（微生物）
└── preview/              渲染核对用的截图（已 gitignore，可删）
```

## 部署

任意静态托管都能放：GitHub Pages、对象存储、nginx、`python -m http.server`。
上传 `index.html` + `assets/` 两个东西即可，不需要 Node、不需要构建。

当前用的是 GitHub Pages：`main` 分支根目录，push 后约 30 秒自动重建。

本地起服务预览：

```bash
cd bio-research-forge-intro
python -m http.server 8080
# 打开 http://127.0.0.1:8080
```

## 维护

- 文案：直接改 `index.html`，各节用 `<section id="...">` 分开（能力 / 案例 / 安装 / 图集 / FAQ）。
- 换图：同名覆盖 `assets/*.png`，比例保持 2100×1650 或 1800×1500 最稳（横向图）。
- 配图来源：植物 5 张在 `mcode-case/case2/out/`，医学 2 张在 `mcode-case/case3/out/`，微生物 2 张在 `mcode-case/case4/out/`；示例数据（模拟），公共查询为 2026-11-09 真实执行。
- Review 报告：`mcode-case/case2|case3|case4/review-report.md`；manifest 在各自目录下。
- 已知小瑕疵：微生物箱线图的纵轴沿用出图接口默认标签 `Expression`，数值实为相对丰度（%）；图注已写明。
- 发布：改完执行 `git add -A && git commit -m "update" && git push`，Pages 自动更新。

## 声明

页面为作者自述，功能以实际安装版本与配置为准；示例数据为模拟，未使用未发表研究数据。
