# LaTeX 格式规则

## 目录

1. 文件组织
2. 宏定义
3. 引用
4. 标签和引用
5. 图表
6. 公式
7. 引号和破折号
8. 修订约定

## 1. 文件组织

多节论文应将内容拆分到 `sections/` 目录下的文件中，`main.tex` 用 `\input{sections/...}`。典型结构：

```
sections/
figs/
exps/
algs/
main.tex
commands.tex
bibfile.bib
```

将所有内容内联在单一 `main.tex` 中对很短的论文可接受但跨多作者版本控制更难。

## 2. 宏定义

为重复出现的字符串定义宏：系统名、方法名、常拼错的词或常用高亮。

`commands.tex` 中示例：

```latex
\newcommand{\sys}{\texttt{Alpha-SQL}\xspace}
\newcommand{\hi}[1]{\vspace{.25em}\noindent \textbf{#1}}
\newcommand{\lgl}[1]{\textcolor{blue}{LGL: #1}}
\newcommand{\revision}[1]{\textcolor{blue}{#1}}
```

重命名成为一行更改而非跨数十节的查找替换。系统名在修订中变化时，宏是唯一需要编辑的。

## 3. 引用

规则 L1：词与其引用之间始终使用不间断波浪号，防止尴尬换行。

| 错 | 对 |
|---|---|
| `ResNet\cite{X}` | `ResNet~\cite{X}` |
| `ResNet \cite{X}` | `ResNet~\cite{X}` |

多条引用放一个命令内：

```latex
Artificial Intelligence~\cite{xxxx, yyyy, zzzz}
```

规则 L2：遵循会议引用风格。ACL 用 natbib，`\citep` 为括号式，`\citet` 为文本式。数据管理会议（SIGMOD、VLDB）用 IEEE 或 ACM 数字风格。投稿前转换。

规则 L3：bib 条目须包含会议名、年份、页码、作者、标题。从 DBLP 拉取以确保正确。

## 4. 标签和引用

规则 L4：标签使用下划线和前缀以可读。

- `\label{fig:system_overview}`（好）。
- `\label{sec:intro}`（好）。
- `\label{system overview}`（坏；含空格）。
- `\label{system-overview}`（坏；连字符破坏某些引用）。

规则 L5：引用也使用不间断波浪号。

```latex
as shown in Figure~\ref{fig:system_overview}
discussed in Section~\ref{sec:intro}
```

## 5. 图表

规则 L6：每个图表必须有标题。标题描述发现而非仅设置，尤其是实验图。

规则 L7：默认放置为页顶（`[t!]`）。图放不下顶部时 `[b!]`（底部）可接受。行内 `[h]` 很少工作；让 LaTeX 决定。

规则 L8：图使用矢量格式（PDF、EPS、SVG）。终稿绝不插入 PNG 或 JPG 截图；放大时像素化。

规则 L9：始终在图出现之前在正文中引用。"Figure 2 shows..." 是经典模式。

## 6. 公式

规则 L10：每个编号公式应在正文中至少被引用一次。如公式未被引用，要么引用它，要么用 `\begin{equation*}` 去掉编号。

规则 L11：公式编号在节内应连续。在每个编号公式上用 `\label` 以便重排时无需手动重新编号。

## 7. 引号和破折号

规则 L12：使用 LaTeX 引号约定。

- 双引号：用 `` `` `` 开，`'' ` 关。
- 单引号：用 `` ` `` 开，`' ` 关。
- 绝不用直 ASCII 打字机 `"` 字符。

规则 L13：LaTeX 中破折号有三种；各用其位。

- 连字符 `-`：复合形容词（high-efficiency、zero-shot）。
- en-dash `--`：数字范围（pages 10--15、2024--2026）。
- em-dash `---`：语义断开。项目规则：正文不用 em-dash。用逗号、冒号或句号代替。

## 8. 修订约定

修订投稿时，在专用文件中保留审稿历史。

```
responses/
  meta.tex
  r1.tex
  r2.tex
  r3.tex
```

用 `\revision{...}`（定义为蓝色宏）标记修订文本。用 `\marginpar` 在边距标记修订指针：

```latex
\marginpar[]{\revision{R1.W1}}{\revision{text}}
\marginpar[\revision{R3.W2}]{}{\revision{text}}
```

每个 `r<n>.tex` 文件以审稿人评论和回应章节的汇总表开头。使汇总表成为响应文件的第一内容，让审稿人一目了然做了什么。
