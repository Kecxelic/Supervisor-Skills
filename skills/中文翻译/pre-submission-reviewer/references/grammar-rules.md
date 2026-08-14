# 非英语母语作者的语法规则

## 目录

1. 冠词使用
2. 主谓一致
3. 时态一致性
4. 句子复杂度
5. which vs that
6. 被动语态
7. 中式英语模式
8. 引号标点

## 1. 冠词使用

规则 G1：单数可数名词需要冠词（a、an、the），除非是泛指复数或专有名词。

| 错 | 对 |
|---|---|
| We propose novel method. | We propose a novel method. |
| in descending order | in a descending order |
| Our model supports the case changed. | Our model supports the case that changed. |

快速测试：如名词可数且单数，且句子关于具体实例，则需要冠词。泛指复数省略冠词。不可数名词（information、evidence）通常省略冠词。

## 2. 主谓一致

规则 G2：第三人称单数主语用第三人称单数动词。

- it predicts, it proposes, it improves.
- we propose, we show, we introduce.
- they demonstrate, they report.

ICML 或 VLDB 论文（单数）用第三人称单数动词形式：

- The method predicts accurately.
- 非：The method predict accurately.

## 3. 时态一致性

规则 G3：不同章节有不同默认时态。

- 摘要：论文用现在时，实验用过去时。
- Introduction：论文声称用现在时，已有工作引用用过去时。
- 方法论：现在时（方法做 X）。
- 实验：过去时（we ran the experiment, we observed）。
- Related Work：总结已有工作贡献用过去时。
- 结论：现在完成时（we have shown, we have proposed）。

在单句或单段内混用时态是常见的审稿人抱怨。

## 4. 句子复杂度

规则 G4：一句一主要想法。一句中两个动词需要连接词。避免仅用逗号连接两个独立子句（逗号拼接）。

| 错 | 对 |
|---|---|
| We propose a method has high efficiency. | We propose a method that has high efficiency. |
| We propose a method has high efficiency. | We propose a high-efficiency method. |
| We propose a method, it has high efficiency. | We propose a method. It has high efficiency. |
| We propose a method, it has high efficiency. | We propose a method with high efficiency. |

长句应在自然边界拆分。用"Specifically,"或"In particular,"开始续句，而非把所有内容塞进一个复杂句。

## 5. which vs that

规则 G5：限定性从句用"that"（对意思必需）；非限定性从句用"which"（括注性，用逗号隔开）。

- 限定性："the method that achieves state of the art"（从中选出达成的那个）。
- 非限定性："the method, which achieves state of the art,"（旁白）。

非英语母语作者常在两种情况都用"which"。从句为限定性时改为"that"。

## 6. 被动语态

规则 G6：优先主动语态，除非主语确实不重要。"The method was evaluated"在评估者身份不重要时可接受；"We evaluated the method"在重要时更强。

过度使用被动语态使正文感觉含糊。审查段落中的被动结构串，将最重要句子改为主动语态。

## 7. 中式英语模式

需标记的常见中式英语模式：

- 中文成语直译在英文中不成立。
- 过度使用"very"（很多中文用户会用"very"；常不必要）。
- 短时间内多次使用同一词而同义词更清晰。
- 过度对冲的陈述（"it may be the case that perhaps the method possibly"）而直接陈述更清晰。
- 用机器翻译翻译中文草稿。绝不要这样做；输出积累不地道的措辞，审稿人立即注意到。从头用英文写。

## 8. 引号标点

规则 G8：学术写作中，使用逻辑标点（标点仅在是引用材料一部分时放入引号内）。LLM 生成的文本常默认美国排版（标点始终在内）；学术英文中需更正。

| 美国（避免） | 逻辑（使用） |
|---|---|
| approach is called "data-centric AI," which emphasises | approach is called "data-centric AI", which emphasises |
| outputs what it calls "semantic summaries." | outputs what it calls "semantic summaries". |

另外：按 LaTeX 惯例使用反引号和单双引号：`` `` `` 开，`'' '` 关，非直打字机字符。
