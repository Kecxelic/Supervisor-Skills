# 搜索策略

## 关键词构造

关键词系统化构造，不是自由联想。模式：

**模式 1：核心方法 × 应用领域**
- "retrieval augmented generation" + "question answering"
- "CRISPR base editing" + "clinical trial"

**模式 2：核心机制 × 目标任务**
- "chain of thought" + "scientific reasoning"

**模式 3：领域 + survey / benchmark / meta-analysis**
- "LLM agent survey 2025 2026"
- "social media adolescent mental health meta-analysis"

**模式 4：关键研究者 × 方向**（当纲要命名了特定研究者时）
- "Haidt social media adolescent"
- "Orben screen time well-being"

**模式 5：已知论文的引用网络**
- 从已找到的核心论文中提取关键术语；搜索它们引用的以及引用它们的

每种模式至少试一轮。在多视角搜索中，每个视角用一两种模式；三到五个视角各约两轮设定下限，无上限：覆盖决定。

## 盲区发现

第二轮之后，运行盲区检查：

1. **覆盖**：纲要的每个子方向有三篇以上工作？
2. **流派检查**：是否有方法流派完全缺席？
3. **引用链检查**：已找到论文本身高频引用的工作是否在列表中？
4. **丢弃检查**："找到但不计划使用"的结果是否指向未覆盖的子方向？不要丢弃它们；它们是盲区线索。
5. **时效检查**：去年有什么重要工作？全旧结果通常意味着关键词错过了当前浪潮。

## 按学科调整

文献在各领域分布不同：

- **CS / AI**：arXiv 预印本主导且更新快；最近六个月可能决定性的。
- **生物医学**：临床期刊重要；搜索"clinical trial"加疾病名；注意试验阶段。
- **社会科学**：同时搜索效应量和设计（RCT、DID、IV）。
- **跨学科主题**：分别搜索每个学科再合并；单一学科的关键词不会浮现其他学科的文献。
