# Vibe Writing：红线规则与推荐流程

## 目录

1. 已解决的矛盾
2. 红线规则
3. 推荐流程
4. AI 做得好的
5. AI 做不好的
6. 与 pre-submission-reviewer 的集成

## 1. 已解决的矛盾

项目 v1 内容包含表面矛盾：3.5 节严格禁止 AI 生成内容；5.1 节拥抱 Vibe Writing。v2 的解决：

- AI 辅助写作在机械加速（语法、措辞、结构建议）上是允许的。
- AI 生成草稿在未经用户逐句验证前不可作为提交文本。
- 3.5 节的机械写作规则（无破折号、无禁用 AI 语调词汇、无中式英语）由 `pre-submission-reviewer` 技能执行。
- 5.1 节的行为规则治理流程。

实际操作：先用用户自己的话写；用 AI 润色；润色后验证；投稿前扫描禁用模式。

## 2. 红线规则

不要：

- 逐字复制 AI 生成段落到论文。用用户自己的话重写。
- 让 AI 编造或预填引用。每条参考文献都是用户自己确认读过的。
- 发送部分提示并接受 AI 返回的任何内容；上下文必须包含论文方法、问题、背景和相关实验数据。
- 用 AI 隐藏剽窃或转述另一组的工作。
- 向禁止 AI 辅助内容的会议提交 AI 辅助正文而不披露。

任何红线规则违规是学术不端。完整上下文见 `references/behavior-guidelines.md`。

## 3. 推荐流程

### 步骤 A：用用户自己的话写核心声称和逻辑

- 产出段落骨架：主题句、证据句、收尾句。
- 先做这个；不外包。
- 骨架编码用户的思考，就是贡献。

### 步骤 B：用 AI 润色（构造性合规）

- 将用户段落粘贴给 AI，附显式润色提示，内联禁用词汇和标点规则。这在润色步骤防止漂移而非依赖下游审查者捕捉违规。模板：

```
润色以下段落的语言。硬规则：

1. 精确保留每个技术声称。不添加内容，不删除内容，不添加引用。
2. 不使用以下任何禁用词或短语：innovative, pioneering, revolutionary paradigm,
   transformative framework, superior, surpass, excel, remarkable,
   unprecedented, achieves SOTA, breakthrough performance, general-purpose,
   is capable of, notably, yet, yielding, at its essence, encompass,
   differentiate, reveal, underscore, pave the way for, highlight the
   potential of, profound challenges, stems from, rigid, impede。
3. 不使用破折号作为句子连接器或括注断开。用逗号、冒号或句号代替。
4. 使用逻辑引号标点：标点仅在是引用材料一部分时放入引号内。
5. 偏好短句、主动语态和具体技术动词（propose, introduce, design, show,
   demonstrate, report, observe）。
6. 保持段落长度大致与输入相当。

待润色段落：
<在此粘贴段落>
```

- AI 返回的润色版在投稿时已风格合规，不仅是语法正确。
- 用户仍在步骤 C 逐词比较以捕捉任何内容漂移，但步骤 D 的禁用词汇和破折号检查在常见情况下应返回空集。

### 步骤 C：逐句验证

- 对润色版每句问：这是否匹配用户的预期声称？
- 替换任何漂移为用户的措辞。
- 标记任何幻觉内容并删除。

### 步骤 D：扫描禁用模式（后盾）

步骤 B 的内联规则防止了大部分违规。步骤 D 是漏网的的后盾。

- 运行禁用词汇扫描（见 `pre-submission-reviewer` 的 `references/forbidden-patterns.md` 了解规范列表和严重性启发式）。
- 删除存活到步骤 D 的任何 AI 语调词。
- 删除用作句子连接器的破折号；替换为逗号、冒号或句号。
- 验证标点遵循逻辑（非美国）引号约定。

如步骤 D 发现大量违规，步骤 B 的润色提示模板不够完整；更新提示而非接受反复步骤 D 清理。

### 步骤 E：最终完整性检查

- 大声朗读整段。听起来像用户吗？
- 如声音漂移，重写。
- 最终文本应是用户的声音，非失去用户风格的 AI 润色版。

## 4. AI 做得好的

- 语法修正：冠词使用、主谓一致、时态一致性。
- 句长和拆分长句。
- 段落流畅：建议过渡。
- 地道英文与用户母语间翻译。
- 发现过长被动结构。
- 为已知概念建议措辞。

这些任务 AI 是净正面的；逐句验证仍须但很少发现问题。

## 5. AI 做不好的

- 技术准确性：AI 可能微妙地歪曲用户方法。
- 引用：AI 自信地编造参考文献。
- 新颖性框架：AI 默认通用膨胀语言。
- 声音：AI 将用户声音平滑为缺乏个性和区分度的中性调。
- 章节适当时态：AI 在段内混时态。
- 避免 AI 语调词汇：AI 倾向自己的禁用词。

这些任务 AI 是净负面的；用户须在验证时捕捉和更正。

## 6. 与 pre-submission-reviewer 的集成

Vibe Writing 和 pre-submission-reviewer 互补：

- Vibe Writing 治理起草流程。
- pre-submission-reviewer 审计最终草稿。

典型序列：

1. 用户用自己的声音起草第 X 节。
2. 用户用 AI 润色（Vibe Writing 步骤 B）。
3. 用户逐句验证（步骤 C）。
4. 用户对完成章节运行 `pre-submission-reviewer`。
5. 用户投稿前修复任何 MAJOR 发现。
6. 最终投稿前，`pre-submission-reviewer` 对全文运行禁用词汇和破折号扫描。

不执行 Vibe Writing 纪律直接运行 pre-submission-reviewter 倾向于产生许多需要从头重写章节的发现；执行 Vibe Writing 而不运行 pre-submission-reviewer 会留下一些问题（禁用词汇、破折号误用）让审稿人先发现。
