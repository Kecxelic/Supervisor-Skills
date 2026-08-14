# 引用风格参考

## 目录

1. 默认：数字引用序
2. 按参考类型的条目格式
3. 作者列出规则
4. 缺失字段处理
5. 按需替代风格
6. 通用引用纪律

## 1. 默认：数字引用序

除非用户另有指定，使用数字引用序系统：引用按首次出现顺序编号 `[1]`、`[2]`、...，贯穿全文，参考文献列表按编号排序。这匹配 IEEE 参考格式，在工程、CS 和大部分自然科学中是标准。

正文用法：

```
Transformer architectures have become the dominant paradigm in NMT [1].
Smith et al. [2] extended this line of work by introducing adaptive
scheduling, while several concurrent efforts explored curriculum-based
approaches [3, 4, 7].
```

| 情况 | 形式 |
|---|---|
| 单一工作 | `[1]` |
| 多个工作 | `[2, 5, 7]` |
| 连续范围 | `[1-3]` |
| 正文中命名作者 | `Smith et al. [2] proposed...` |
| 无来源可用 | 用文献检索能力搜索；如找不到，重写句子使其无需引用 |

## 2. 按参考类型的条目格式

每段一条目，条目内无硬换行。

**会议论文**：
```
[N] Authors, "Title," in Proc. VENUE, Year, pp. X-Y.
[1] A. Vaswani et al., "Attention is all you need," in Proc. NeurIPS, 2017, pp. 5998-6008.
```

**期刊论文**：
```
[N] Authors, "Title," Journal, vol. X, no. Y, pp. X-Y, Year.
```

**预印本 / arXiv**：
```
[N] Authors, "Title," arXiv:XXXX.XXXXX, Year.
```

**书籍**：
```
[N] Authors, Title. City: Publisher, Year.
```

## 3. 作者列出规则

- 三位或以下作者：全部列出，最后一位前加"and"。
- 四位或以上：列出前三位加"et al."，或按会议偏好只列第一作者加"et al."；在同一文档内保持一致。
- 姓在后名缩写在先：`A. B. Smith`。

## 4. 缺失字段处理

| 缺失 | 处理 |
|---|---|
| 会议（会议或期刊名） | 省略会议字段（预印本常规），或通过检索补全 |
| 页码 | 省略 `pp.` 字段（常规） |
| 年份 | 通过检索补全；如无法确认，删除该条目 |
| 整条目不确定 | 不生成条目，不写引用它的句子 |

无缺失字段用方括号占位符修补。

## 5. 按需替代风格

仅在用户要求特定风格时切换。

### APA 第 7 版（心理学、教育学、社会科学）

正文：`(Author, Year)` 或 `Author (Year)`；直接引用加页码 `(Author, Year, p. 12)`。两位作者 `(Smith & Jones, 2023)`；三位或以上从首次使用起 `(Smith et al., 2023)`。

条目：
```
Smith, A. B., Jones, C. D., & Lee, E. F. (2023). Title of article. Journal
Name, 45(3), 123-145. https://doi.org/10.xxxx/xxxxx
```
按姓氏字母排序，不编号；期刊名斜体；文章标题句首大写；最多列出 20 位作者。

### Chicago 作者-日期（部分社会科学和经济学）

正文：`(Smith 2023)`，无逗号。条目：
```
Smith, Adam B. 2023. "Title of Article." Journal Name 45 (3): 123-145.
```

### Chicago 注释-参考文献（人文学科）

上标注释编号。首次注释：
```
1. Adam B. Smith, "Title of Article," Journal Name 45, no. 3 (2023): 125.
```
后续注释缩短为 `Smith, "Title of Article," 130.` 参考文献条目反转第一作者名。

### Harvard（部分英国和澳大利亚会议）

正文同 Chicago 作者-日期。条目：
```
Smith, A.B. (2023) 'Title of article', Journal Name, 45(3), pp. 123-145.
```

### Vancouver（医学、生物医学）

正文数字编号，`(1)` 或上标。条目：
```
1. Smith AB, Jones CD, Lee EF. Title of article. Journal Name. 2023;45(3):123-145.
```
作者名内无句点或逗号（`Smith AB`）；期刊名用 NLM 缩写。

## 6. 通用引用纪律

以下在每种风格下均有效：

1. **双向对应**：每个正文标记有参考文献条目；每个条目在正文中被引用。
2. **一条目一段**：条目绝不合并为一块。
3. **条目内无中断**：条目的标题、会议和页码保持在一条逻辑行上。
4. **综合保留标记**：多篇工作压缩为一个综合判断时，引用标记保留（`[1-3]` 或 `(Smith, 2023; Jones, 2024)`）；合并观点绝不抹除归因。
5. **不写引用次数声称**：不写"highly cited"或"cited N times"，除非用户明确要求文献计量。
6. **仅可追溯来源**：每个条目来自用户材料或本次会话检索。绝不来自模型记忆。
