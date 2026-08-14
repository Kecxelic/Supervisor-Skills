# 图表工具矩阵

## 目录

1. 决策启发式
2. PowerPoint 和 Keynote
3. Figma
4. draw.io（diagrams.net）
5. Matplotlib 和 Seaborn
6. TikZ 和 PGFPlots
7. Plotly
8. OmniGraffle
9. 应避免的工具

## 1. 决策启发式

| 图类型 | 首选工具 | 备选 | 原因 |
|---|---|---|---|
| Motivated Example（Figure 1） | PowerPoint | Figma | 混合内容：文本、图标、代码、箭头 |
| Solution Overview（管线、架构、多层） | draw.io | PowerPoint、TikZ | 需要清晰模块布局、对齐网格 |
| 实验结果（柱、线、热力、散点等） | Matplotlib + Seaborn | TikZ + PGFPlots | 可复现、可脚本化、可版本控制 |
| 模式或关系图 | draw.io | TikZ | 标准数据库图惯例 |
| 图标和 Logo | Figma | Iconfont、Flaticon | 干净矢量编辑 |

先决定图类型；每种工具在特定类型上出色。不要试图让一个工具做所有事。

## 2. PowerPoint 和 Keynote

- 布局迭代快。
- 导出 PDF 保持矢量。
- 字体和对齐控制合理。
- 多数机构许可证免费。

最适合早期草稿、Figure 1 设计和任何混合内容图（文本块、图标、箭头、嵌入代码片段）。

弱点：不可从数据复现；每次编辑是手动的。

## 3. Figma

- 基于组件；跨图构建可复用元素。
- 在共享画布上协作。
- Camera-ready Figure 1 输出最干净。
- 基于 Web；无需本地安装。

最适合在布局稳定后精修 Motivated Example 或 Solution Overview。

弱点：仅浏览器；离线编辑有限。

## 4. draw.io（diagrams.net）

- 免费、跨平台、离线可用。
- 网格对齐保持管线和架构图对齐。
- 形状库覆盖典型 CS 图表需求。
- 导出 PDF 或 SVG。

最适合管线或系统架构的 Solution Overview 图。

弱点：视觉精致度低于 Figma 或 OmniGraffle。

## 5. Matplotlib 和 Seaborn

- 代码生成；完全可从数据复现。
- 可脚本化；每次实验重跑后重新生成所有实验图。
- 共享风格扩展到数十图。
- Python 原生；与实验脚本集成。

最适合每张实验结果图。

弱点：默认样式丑；始终导入共享 `plot_utils.py` 保持一致风格。

## 6. TikZ 和 PGFPlots

- 原生 LaTeX；与论文文本精确排版匹配。
- 矢量完美输出。
- 投入最高、学习曲线最陡。

最适合期望 TikZ 质量排版的期刊 Camera-ready 图。

弱点：早期草稿成本高；图设计稳定后再切换到 TikZ。

## 7. Plotly

- 交互式；适合补充材料或 HTML 附录。
- 导出静态 PNG 或 PDF 用于论文。

最适合探索性分析和补充交互图。

弱点：默认排版与学术规范不同；静态导出质量低于 Matplotlib。

## 8. OmniGraffle

- 专业图表质量。
- 仅 macOS 原生。
- 付费。

最适合如作者已使用 macOS 且有 OmniGraffle 许可证的精修 Solution Overview 图。

弱点：仅 macOS 限制了与 Windows 或 Linux 合作者的协作。

## 9. 应避免的工具

- **Excel 图表插入为图片**。质量差、风格不一致、难以重新生成。
- **在 Illustrator 中手动编辑 Matplotlib 输出**。一次性结果；每次数据更新都会断裂。
- **使用非学术规范的通用在线图表生成器**。图在顶会论文中会显得格格不入。
- **Procreate、GoodNotes、Notability** 用于早期手绘以外的任何用途。手绘缺乏对齐纪律。
- **AI 图像生成器** 用于论文图表。它们无法产出学术图所需的结构化内容。
