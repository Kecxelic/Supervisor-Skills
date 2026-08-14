---
name: benchmark-paper-template
description: 使用五支柱框架（研究空白、构建管线、评估框架、实证发现、可选的伴随方法）结构化 Benchmark 与评估论文。返回完整性审计、六段式 Introduction 逻辑链、第 2-7 节骨架、投稿前检查单。在撰写 Benchmark 论文、结构化 Benchmark 论文、检查 Benchmark 想法是否实质充分、起草 Benchmark Introduction、规划数据构建管线或实验时使用。
license: CC-BY-4.0
---

# Benchmark 论文模板

## 概述

Benchmark 论文不靠提出新算法取胜，而是靠定义新的评估维度并交付一个使测量具备高质量、可扩展、可复现的构建管线。本技能搭建审稿人会检查的五支柱，然后给出六段式 Introduction 逻辑链、第 2-7 节骨架和投稿前检查单。各阶段深度资料存放在 `references/` 下的七个参考文件中。

## 核心能力

1. **五支柱完整性审计**：研究空白是否阐述清楚？构建管线是否有原则？评估框架是否细粒度？实证发现是否揭示能力边界？伴随方法是否必要？
2. **Introduction 六段式逻辑链**：背景 + 运行示例、现有 Benchmark 局限（不超过三条）、研究问题、设计考量、我们的提案、贡献。
3. **第 2-7 节骨架**：任务与设计目标、构建管线、可选伴随方法、按 RQ 组织的实验、讨论与研究机会、含 Benchmark 对比表的 Related Work、结论。
4. **投稿前自检**：四类审稿人检查单（Introduction、Benchmark 部分、实验、整体），按 Critical、Major、Minor 分严重性。

## Benchmark 论文 vs 技术论文

| 维度 | 技术论文 | Benchmark 论文 |
|---|---|---|
| 主要贡献 | 新算法或新方法 | 新评估维度或数据集 |
| Introduction 轴线 | 关键想法或机制 | 评估空白与 Benchmark 设计理由 |
| 问题定义 | 一句话目标 | 问题定义本身就是贡献 |
| 最重章节 | 方法 | 构建管线 + 评估框架 |
| 实验目的 | 证明"我的方法胜过基线" | 揭示"模型能力边界在哪里" |
| 典型 Figure 1 | 方法框架图 | 运行示例 + 管线图 |

技术论文和立场论文请使用 `tech-paper-template` 技能。单独的 Introduction 大纲请使用 `intro-drafter`。

## 五支柱

1. **研究空白**。现有工作遗漏了哪个评估维度？用一个具体失败案例锚定空白，引用至少三个你正在解决其局限性的已有 Benchmark（不超过三个）。范例：StatQA 突出了统计方法适当性评估的缺失；nvBench 2.0 突出了查询歧义盲区；VisJudge-Bench 突出了可视化评估中保真度-表达力-美学三位一体。
2. **构建管线**。如何构建高质量、可扩展、可复现的数据？三种常见范式：逆向合成（先种子知识再实例化）、受控注入（先种子查询再注入针对性歧义或错误）、自适应生成 + 专家验证。明确数据源选择、生成、标注、质量控制、划分策略和统计概况。深度展开：`references/construction-pipeline.md`。
3. **评估框架**。超越单一总分：难度分层、错误分类法、各维度评分量表。解释为什么这套分类法能诊断空白所指向的问题。深度展开：`references/benchmark-design.md`。
4. **实证发现**。多角度对比（人类 vs LLM、架构家族、错误分布）凝练为加粗的 *Finding X:* 句式，读起来像引理。每条 Finding 必须对未来研究可操作。深度展开：`references/experiments.md`。
5. **伴随方法（可选）**。为该 Benchmark 调优的专用模型，表明社区可以基于发现采取行动。示例：Step-Text2Vis、VisJudge。非强制，但对于面向成熟任务的 Benchmark 强烈推荐。

## Introduction 六段式流程图

1. **研究背景 + 运行示例（Figure 1）**。确立任务、其重要性、一个贯穿全文的具体示例。
2. **现有 Benchmark 局限**。至多三条，每条具体且可追溯到评估盲区。避免模糊的"有局限"表述。
3. **研究问题**。两到三个 RQ，覆盖构建质量、能力边界和人机差距。
4. **设计考量**。一个好的该维度 Benchmark 应具备什么？质量、规模、覆盖、可复现、抗污染。
5. **我们的提案**。一段话：Benchmark 加上伴随方法（如有）。
6. **贡献**。通常四项：Benchmark + 管线创新 + 系统评估 + 发现或伴随方法。

## 章节骨架

- **§2 任务 + 设计目标**：问题形式化、目标（G1 覆盖、G2 细粒度诊断、G3 可复现、G4 抗污染）。见 `references/benchmark-design.md`。
- **§3 构建管线**：数据源、生成、标注协议、质量控制、统计概况。Figure 2 是标准管线图。见 `references/construction-pipeline.md`。
- **§4 伴随方法（可选）**：以该 Benchmark 为训练集的专用模型。
- **§5 实验**：按 RQ 组织。包括总体性能表（通常是论文中最大的表）、细粒度分析、人类基线（如有）、加粗的 *Finding X:* 摘要。见 `references/experiments.md`。
- **§6 讨论 + 研究机会**：发现揭示了什么，下一步是什么。
- **§7 Related Work**：Benchmark 对比表（通常标记为 Table 1）是必需的，放在这里或 §1 末尾。

完整的逐节写作指南（含页面预算和图表位置）见 `references/paper-structure.md`。

## 提示模板

将以下内容粘贴到 AI 助手中，填入输入槽位。

```markdown
# 角色
你是一位在顶会（NeurIPS Datasets and Benchmarks Track、SIGMOD、VLDB、ICML、ICLR）发表过多篇 Benchmark 论文的资深研究者。你知道审稿人在 Benchmark 投稿中关注什么，以及这些标准与技术论文有何不同。

# 任务
我将给你一份 Benchmark 或评估论文的核心信息。请用五支柱框架审计它，然后产出论文的完整逻辑骨架。

# 五支柱（均须回应）
1. 研究空白：现有工作遗漏了哪个评估维度？
2. 构建管线：如何在不损失质量的前提下大规模构建数据？
3. 评估框架：细粒度分类法是什么？
4. 实证发现：揭示了什么能力边界？
5. 伴随方法（可选）：为该 Benchmark 调优的专用模型。

# 输入
- 研究领域：[如 Text-to-SQL、Text-to-Visualization、代码生成]
- Benchmark 名称：[名称]
- 研究空白与动机：[你针对的评估盲区]
- 构建方法：[数据如何构建]
- 评估框架：[指标与分类法]
- 数据规模：[任务数、领域数、难度分层]
- 关键发现或洞察：[一到三条]

# 输出

## 步骤 1：五支柱完整性表

| 支柱 | 是否覆盖？ | 你的内容 | 改进建议 |
|---|---|---|---|
| 研究空白 | 是或否 | ... | ... |
| 构建管线 | 是或否 | ... | ... |
| 评估框架 | 是或否 | ... | ... |
| 实证发现 | 是或否 | ... | ... |
| 伴随方法 | 是、否或不适用 | ... | ... |

## 步骤 2：Introduction 六段式逻辑链

| 部分 | 你的内容 |
|---|---|
| 1. 背景 + 运行示例 | ... |
| 2. 现有 Benchmark 局限（至多 3 条） | 局限 1: ... | 局限 2: ... | 局限 3: ... |
| 3. 研究问题 | RQ1: ... | RQ2: ... | RQ3（可选）: ... |
| 4. 设计考量 | ... |
| 5. 我们的提案 | ... |
| 6. 贡献 | 1. ... | 2. ... | 3. ... | 4. ... |

## 步骤 3：第 2-7 节大纲

每节产出一段概要，标明承载该节权重的图或表。

## 步骤 4：投稿前自检

加载 `references/checklist.md`，逐条走四类检查单。报告任何未解决的 Critical 或 Major 项。
```

## 参考范例

- **StatQA（NeurIPS 2024）**：空白是统计方法适当性评估；管线是从教科书逆向合成；发现是 LLM 即使数值计算正确也常选错统计检验。
- **nvBench 2.0（NeurIPS 2025）**：空白是 Text-to-Visualization 中查询歧义盲区；管线是受控歧义注入；发现是 LLM 输出质量随措辞微变而剧烈波动，而人类通过澄清对话应对。
- **VisJudge-Bench（ICLR 2026）**：空白是可视化质量中保真度-表达力-美学三位一体；管线是专家策划 + 自适应生成；伴随方法是 VisJudge，一个在该 Benchmark 上训练的专用评判模型。

## 使用建议

- 尽早使用，在范围锁定时。缺少某支柱最便宜的修复是在数据构建开始之前。
- 当用户对某支柱的回答是"有但比较乱"时，引导他们去看 `references/` 中的对应文件，而不是试图在一轮对话中解决。
- 不要将本 Introduction 流程图与技术论文流程图混淆；它们在结构上不同。技术论文请调用 `tech-paper-template`。
- 投稿前自检时，加载 `references/checklist.md`，与用户逐条过。

## 参考文件

- [`references/gap-analysis.md`](references/gap-analysis.md)：系统化识别评估盲区。
- [`references/benchmark-design.md`](references/benchmark-design.md)：设计目标、任务范围、分类法模式、评估框架。
- [`references/construction-pipeline.md`](references/construction-pipeline.md)：三种构建范式、管线阶段、质量控制。
- [`references/experiments.md`](references/experiments.md)：基线选择、RQ 驱动分析、*Finding X* 模式、案例研究。
- [`references/paper-structure.md`](references/paper-structure.md)：逐节写作指南，含页面预算和图表位置。
- [`references/checklist.md`](references/checklist.md)：四类投稿前检查单，含严重性分级。
- [`references/instantiation-template.md`](references/instantiation-template.md)：可填写的模板，用于在你的论文上实例化此思考模型。
- [`references/orchestrator-notes.md`](references/orchestrator-notes.md)：早期分阶段编排器架构的历史记录，保留供参考。
