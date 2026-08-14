# 贡献段落模式

## 目录

1. 经典结构
2. 强贡献措辞
3. 弱贡献措辞
4. 反模式
5. 章节编号映射
6. 投稿前贡献审计

## 1. 经典结构

典型 Introduction 第六段包含三到四条编号贡献：

- **C1**：问题形式化或设定（仅新问题/设定论文）或系统/框架设计（技术论文）。
- **C2**：一到两个关键技术贡献。这些是论文引入的具体算法、数据结构或理论结果。
- **C3**：实证评估，含具体亮点。
- **C4**（可选）：次要贡献如开源发布、专用模型或跨领域迁移结果。

每条贡献应：

- 一到两句话。
- 足够具体，删除它会改变论文声称。
- 映射到一个章节或一组章节。

## 2. 强贡献措辞

强贡献命名具体机制或结果、引用章节，并经得起审稿人问"你在论文哪里交付了这个？"。

示例：

- "We propose `<framework name>`, the first system to do X under constraint Y, described in Section 3."
- "We introduce `<algorithm name>`, which reduces Z from O(n^2) to O(n log n), with proofs in Section 4."
- "We evaluate on `<benchmark>` against 12 baselines and show <gain> point gains on <metric>, with fine-grained analysis in Section 5."
- "We release `<dataset name>`, the first dataset to contain <property>, available at <url>. See Section 6."

## 3. 弱贡献措辞

弱贡献模糊、不可证伪或是不应算作贡献的预期工作。

应避免的弱措辞示例：

- "Extensive experiments demonstrate the effectiveness of our method."（预期的；不是贡献。）
- "We provide a comprehensive analysis."（模糊；描述每篇论文。）
- "Our approach is state-of-the-art."（声称，非贡献。）
- "We improve on prior work."（提升多少，在什么上？）
- "We propose a new method."（哪个？做什么的？）

## 4. 反模式

- **注水贡献数**：论文只有三个贡献却用四个。最后一个位置是模糊短语。删掉。
- **重叠贡献**：贡献 2 和贡献 3 从不同角度描述同一机制。合并。
- **贡献-章节不匹配**：贡献引用第 5 节但第 5 节未交付。审稿人会在大修中引用。
- **承诺遗忘**：贡献承诺具体结果（如"10x speedup"）但实验章节不支持。
- **事后 retrofit**：实验成功后才写贡献，cherry-pick 只写有效的。纪律：在跑实验前写贡献。
- **营销式膨胀**："revolutionary"、"paradigm-shifting"、"breakthrough"作为形容词。删掉；让证据说话。

## 5. 章节编号映射

每个贡献引用至少一个章节。典型映射：

- C1（问题形式化或框架设计）-> 第 2 或 3 节。
- C2（关键技术贡献）-> 第 3 或 4 节。
- C3（实证评估）-> 第 5 节。
- C4（可选：数据集、发布、跨领域迁移）-> 第 6 节或附录。

映射在 Introduction 中显式，如"(Section 3.2)"或"(Sections 4-5)"。如贡献不映射到章节，要么章节缺失要么贡献过度；相应修复。

## 6. 投稿前贡献审计

投稿前，对贡献段落运行此快速审计：

- [ ] 贡献数为 3 或 4。
- [ ] 每条贡献一到两句话。
- [ ] 每条贡献命名具体机制、结果或制品。
- [ ] 每条贡献引用章节。
- [ ] 无贡献仅用模糊短语。
- [ ] 第 4 段的每个挑战都有贡献回应。
- [ ] 贡献中的每个声称都被引用章节交付。
- [ ] 无贡献超出论文实验所示。

任何项失败为 MAJOR 缺口。缺少章节映射即使一条也为 CRITICAL。
