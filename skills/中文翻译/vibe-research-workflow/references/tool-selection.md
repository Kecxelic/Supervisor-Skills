# Vibe Research 工具选择

## 目录

1. 选择启发式
2. Vibe Coding 工具
3. Vibe Figure 工具
4. Vibe Writing 工具
5. 成本考量
6. 中国大陆访问

## 1. 选择启发式

选匹配阶段的工具，而非反过来。

| 阶段 | 首选工具 | 备选 | 何时 |
|---|---|---|---|
| 编码（IDE 原生） | Cursor | VS Code + GitHub Copilot | 用户想留在 VS Code 兼容编辑器 |
| 编码（代理式 CLI） | Claude Code | Codex | 用户偏好 CLI，丰富 Skills 生态 |
| 编码（云集成） | Codex | Cursor | 用户想要 GitHub 集成云工作流 |
| 画图（概念草图） | Gemini 或 Nano Banana | 手绘加拍照 | 早期探索 |
| 画图（终版 Figure 1） | PowerPoint 后 Figma | OmniGraffle（macOS） | 论文就绪 |
| 画图（实验图表） | Matplotlib + Seaborn | TikZ + PGFPlots | 可复现科学图 |
| 写作（润色） | Claude | ChatGPT、Gemini | 长文润色保留上下文 |
| 写作（语法） | Grammarly | LanguageTool | 机械语法最终通过 |

## 2. Vibe Coding 工具

### Cursor
- 基于 VS Code 的 AI 原生编辑器。
- VS Code 用户采纳成本低。
- Pro 计划 20 美元/月。
- Plan Mode 加 Agent Mode 分离有价值。
- 推荐 HTTP 兼容模式设置：HTTP 1.1。

### Claude Code
- Anthropic 的 CLI 和桌面代理编码工具。
- 入门曲线较陡；投资回报是丰富 Skills 和 MCP 生态。
- 适合长时间自主会话。

### Codex
- OpenAI 代理编码工具，有 CLI 和桌面。
- 强 GitHub 集成和云环境支持。
- 20 美元/月起步。
- 无编辑器内代码界面；通过 CLI 或桌面应用工作。

### 工具特定技巧

Cursor：非平凡任务启用 Plan Mode。Shift+Tab 切换。

Claude Code：开始前安装相关 Skills（从市场或本地）。`ralph-loop`、`writing-skills` 和 `debugging` 常有用。

Codex：重任务用云环境；通过 GitHub 配置仓库访问。

## 3. Vibe Figure 工具

### 概念草图
- Gemini 可根据描述产出粗略视觉概念。
- Nano Banana 有用于快速布局探索。
- 纸上手绘仍是最快概念工具。

### 布局与精修
- PowerPoint：Motivated Example 迭代最快；导出 PDF 为矢量。
- Figma：最干净精修；组件复用；基于浏览器。
- OmniGraffle：macOS 专业图表质量；付费。
- draw.io：免费、离线、适合管线和架构。

### 实验图表
- Matplotlib 加 Seaborn：可复现、可脚本化、可版本控制。
- TikZ 加 PGFPlots：LaTeX 集成；学习曲线陡；Camera-ready 最佳。
- Plotly：交互式，适合补充材料。

## 4. Vibe Writing 工具

### 润色
- Claude：长上下文，可靠保留技术细节。
- ChatGPT：风格建议强；注意 AI 语调漂移。
- Gemini：免费层可用于轻度润色。

### 语法
- Grammarly：作为浏览器扩展集成 Overleaf。
- LanguageTool：开源替代。
- Overleaf 内置：基础语法和拼写检查。

### LaTeX
- Overleaf：基于云的 LaTeX 协作。
- 本地 LaTeX：论文重度修订或网络不稳时首选。

## 5. 成本考量

严肃 Vibe Research 设置的最低月费：

- 20 美元一个编码助手（Cursor 或 Codex 或 Claude Code）。
- 0 到 20 美元写作润色（多数选项免费）。
- 0 到 10 美元图表工具（多数免费；Figma Pro 可选）。

总计：约 20 到 50 美元/月。实验室或机构订阅通常覆盖。

注意：

- 高负载周（截止冲刺常触发限流）的推理配额限制。
- API 流中的按 token 付费；通过仪表板预算设上限。

## 6. 中国大陆访问

中国大陆研究者对 OpenAI 和 Anthropic 端点面临额外访问限制。选项：

- 代理服务（确保 OpenAI 和 Google 请求正确转发；检查延迟）。
- 实验室 OpenAI 兼容端点（课题组的 hk.yi-zhan.top 和 vip.yi-zhan.top 服务于此）。
- Cursor Pro 加代理设置。
- 云不可用时用本地模型离线开发。

网络稳定性本身是工具选择因素：不稳定网络偏好优雅降级的工具（Cursor 的本地模型选项、本地 Matplotlib）而非需要持续云访问的工具（长会话全代理 CLI）。
