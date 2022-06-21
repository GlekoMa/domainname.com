---
title: "Quarto Template for CUMCM"
toc: false
---

Last updated: May 9 2022

### 关于Quarto

[Quato](https://quarto.org/)是一个开源的科技出版系统，支持Jupyter、RStudio和VS Code等多种代码编辑器。其官方描述如下：

- 创建代码与文本结合的可动态编译内容。支持Python、R、Julia和Observable。

- 使用markdown文本或Jupyter笔记本的形式进行编译。

- 渲染高质量论文、报告、幻灯片、网站、博客和书籍，并以HTML、PDF、MS Word、ePub或其他格式输出。

- 支持数学公式、引文、交叉引用、图表、标注、高级布局以及其他特性。

### 使用须知

本文主要介绍Quarto在数学建模论文排版上的应用。关于此数学建模论文模板的使用，需要声明以下几点：

1. 该模板谨按照全国大学生数学建模竞赛的标准进行设计，不适用于美赛、深圳杯等其他数学建模赛事。

2. 本模板仅适合对排版要求不高的朋友采用。模板主要使用LaTeX编写，由于一篇论文的编译流程大致为：ipynb/qmd -> md -> Pandoc -> PDF，层层抽象过多，故自定义排版布局对使用者相关知识的要求较高，且一旦编写格式逾矩，排错难度较大。

3. 对模板的过度依赖会导致使用者个人的排版能力下降，即使理想的未来情况为内容创作者不再需要为各式样的排版劳心，但就目前来说，社会对于个人的排版能力仍然有一定要求。

### 准备工作

1. 从[Quato](https://quarto.org/)官网下载并安装Quarto

2. 使用终端（Terminal）执行命令：

```bash
quarto tools install tinytex
```

3. 安装[Typora](https://download.typora.io/windows/typora-update-x64-1117.exe)编辑器beta版

### 数学公式

Quarto使用LaTeX格式的数学公式。LaTeX数学公式是计算机中最为广泛使用的公式输入格式，大多数文字或文档编辑软件都对LaTeX数学公式提供支持，例如：Word、Jupyter、Matlab等。下面介绍Quarto中数学公式的输入。

LaTeX中数学公式的输入分两种模式：行内模式（\$ ... \$）与行间模式

````markdown
$$
...
$$
````

前者是在正文的行文中插入数学公式；后者单独成行，且自动居中。

例如``$E=mc^2$``显示为$E=mc^2$,而

````markdown
$$
E=mc^2
$$
````

则显示为：
$$
E=mc^2
$$

输入带自动编号的公式则需要使用Quarto的交叉引用功能，例如：

````markdown
$$
E=mc^2
$$ {#eq-einstein}

# 第二个$$和{}间的空格不能少
````

显示为：
$$
E=mc^2
$$ {#eq-einstein}

交叉引用功能留待后面小节进行介绍。

### 图片与表格

#### 插入图片

图片插入请使用'!+[图片名]+(路径/链接)'的形式，支持插入的图片格式包括JPG、PNG、PDF等（不支持SVG），例如：

````markdown
![MIT LOGO](_mit.png){#fig-mit}

# “{#fig-MIT}”的用处将在后面进行说明
````

显示为：

![MIT LOGO](_mit.png){#fig-mit}

特别的，针对PDF输出，可在``{}``中添加参数控制输出样式，例如：

````markdown
![MIT LOGO](_mit.png){fig.pos="H" width="50%" height="25%"}
````

代表禁止图片浮动（有时会失效）、图片宽度占PDF页面的50%，高度占页面的25%。

#### 插入表格

例如：

````markdown
| 符号  | 说明        | 单位 |
|-------|-------------|------|
| $x_i$ | 第$i$次相遇 | 毫厘 |
| $y_j$ | 第$j$次错过 | 千里 |

: 符号说明 {#tbl-符号说明}

# “: 符号说明” 代表指定表格名称
# “{#tbl-符号说明}”的用处将在后面进行说明,其与表名间的空格不可省略
````

显示为：

| 符号  | 说明        | 单位 |
|-------|-------------|------|
| $x_i$ | 第$i$次相遇 | 毫厘 |
| $y_j$ | 第$j$次错过 | 千里 |

: 符号说明 {#tbl-符号说明}

### 交叉引用

本节介绍Quarto的交叉引用，我们在先前小节的数学公式、图片和表格中分别标记了``{#eq-einstein}``、``{#fig-mit}``和``{#tbl-符号说明}``，我们可以在文中任何地方引用他们，格式为``@...``，例如：

````markdown
 @eq-einstein 、 @fig-mit 和 @tbl-符号说明
````

分别显示为： @eq-einstein 、 @fig-mit 和 @tbl-符号说明

### 建模模板的使用

1. 下载模板文件``cumcm.tex``：

::: {.callout-note appearance="minimal"}
<i class="bi bi-journal-code"></i> [Download cumcm.tex](_cumcm.tex){download="cumcm.tex"}
:::

2. 下载文档示例与示例图片：

::: {.callout-note appearance="minimal"}
<i class="bi bi-journal-code"></i> [Download Demo](_Demo.md){download="Demo.md"}
:::

::: {.callout-note appearance="minimal"}
<i class="bi bi-file-earmark-image"></i> [Download mit.png](_mit.png){download="mit.png"}
:::

3. 将这三个文件放入同一文件夹，使用终端（Terminal）执行命令：

```bash
quarto preview 你的.md文档路径
```

### 资料与工具

#### 演示视频

[测试](https://www.bilibili.com/video/BV1YS4y1q7Qy/)

#### 相关资料

[Quato官网](quarto.org)

[一份其实很短的LaTeX入门文档](https://liam.page/2014/09/08/latex-introduction/)

[使用knitr包输出各种类型的LaTeX表格](https://haozhu233.github.io/kableExtra/awesome_table_in_pdf.pdf)

#### 工具

[在线LaTeX公式编辑器](https://latexlive.com/home)

[流程图：Draw.io](https://www.draw.io/index.html)

[思维导图：XMind](https://www.xmind.cn/)

### BUG

```bash
updating tlmgr

updating existing packages

compilation failed- error
LaTeX3 Error: Mismatched LaTeX support files detected.
(LaTeX3)        Loading 'expl3.sty' aborted!
(LaTeX3)
(LaTeX3)        The L3 programming layer in the LaTeX format
(LaTeX3)        is dated 2022-06-02, but in your TeX tree the files require
(LaTeX3)        at least 2022-06-16.

For immediate help type H <return>.
 ...

l.77      \ExplLoaderFileDate{expl3.sty}}
                                         %
```

终端输入：

```bash
fmtutil-sys --all
```

