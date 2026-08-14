# 禁止模式

## 目录

1. 破折号误用
2. 禁用 AI 语调词汇
3. 图表噪音模式
4. 过度声称模式
5. 剽窃红线
6. 检测启发式

## 1. 破折号误用

本项目写作规范中禁止将破折号用作句子连接器。两种常见误用模式：

### 误用 A：连接两个独立子句
- 错："... closes the research loop, from literature analysis to deployment."
- 对（用逗号加从句）："... closes the research loop, covering literature analysis, hypothesis generation, simulation, validation, and deployment."

### 误用 B：插入括注
- 错："This approach, though simple, is highly effective."
- 对（用从句）："Although simple, this approach is highly effective."

学术写作中破折号的可接受用法罕见。不确定时不用。逗号、冒号或句号几乎处理所有情况。

检测：grep Unicode 破折号字符。正文中每次出现为 MAJOR 发现，除非在代码示例或保留引用中。

## 2. 禁用 AI 语调词汇

以下词汇向经验丰富的审稿人传递 AI 代笔或 AI 辅助信号，应避免。一篇论文中三次或以上使用为 MAJOR 发现。

### 创新夸张
innovative, pioneering, revolutionary paradigm, transformative framework

### 性能夸张
superior, surpass, excel, remarkable, unprecedented, achieves SOTA, breakthrough performance

### 贡献摘要标记
general-purpose, is capable of

### 逻辑连接标记
notably, yet, yielding, at its essence

### 过度使用动词
encompass, differentiate, reveal, underscore, surpass, exhibit superior capability, exceed, pave the way for, highlight the potential of

### 过度使用短语
profound challenges（此搭配在标准写作中不存在）, stems from

### 过度使用形容词和动词
rigid, impede

替换为 section-guides 参考中的中性技术动词：propose, introduce, design, present, show, demonstrate, report, observe。

## 3. 图表噪音模式

增加视觉噪声但不含信息的图表元素：

- 3D 柱状图、3D 饼图。
- 柱或点上的投影。
- 渐变填充，除非渐变编码连续变量。
- 重网格线。
- 装饰性交叉线。
- 与标题重复的图表标题。
- 超过六项的图例（尝试分组）。

每个图表噪音实例为 MINOR 或 MAJOR 发现，视严重性而定。

## 4. 过度声称模式

草稿论文中常见的过度声称：

- "Our method is state-of-the-art" 无限定。应说明在哪个 benchmark 上、什么条件下 SOTA。
- "Comprehensive experiments" 作为贡献。实验是预期的；具体展示了什么？
- "Extensive analysis"。命名分析发现了什么，不是分析存在。
- "We solve the problem of X"。解决是强声称；通常论文改善 X 而非解决。
- "We are the first to"。仔细验证；如声称错误，审稿人会找到并引用。

每个过度声称为 MAJOR 发现。审稿人对在 Introduction 中过度声称的论文保持运行中的记恨；成本在审稿周期中复合。

## 5. 剽窃红线

绝不从其他论文复制句子，包括作者自己的前序论文而无明确复用确认。这适用于：

- 已有方法的 Related Work 摘要。
- Introduction 中对已有工作的引用。
- 与基线论文自身描述相似的方法描述。

剽窃检测为 CRITICAL 发现，阻止投稿。当 Related Work 或 Introduction 过度接近地转述已有工作时，用作者自己的话重写。

## 6. 检测启发式

禁用词汇扫描：
- 对每个禁用词做不区分大小写的子串搜索。
- 计算每词出现次数。
- 任何单一禁用词三次或以上出现为 MAJOR。
- 单次出现为 MINOR。

破折号扫描：
- 搜索 Unicode 破折号字符。
- 每次出现为发现。
- 正文中为 MAJOR；保留引用中为 MINOR。

图表噪音扫描：
- 无法自动完成；技能依赖用户的图描述或上传的图。

过度声称扫描：
- 查找无条件最高级："is state-of-the-art"、"is superior"、"beats all"。
- 对每个出现标记请求限定或证实。

剽窃：
- 对 Related Work 和 Introduction 进行随机句子级公开文本搜索在技能内不可行。建议最终投稿前使用外部剽窃检查器。
