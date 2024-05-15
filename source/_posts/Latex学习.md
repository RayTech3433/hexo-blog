---
title: Latex学习
tags: Latex
categories: 学习记录
keyword: Latex
swiper_index: 1
abbrlink: 8837ae6a
description: 一些关于Latex学习中的笔记啦！
date: 2024-03-07 08:54:30
---

# Latex

## 安装

###  textive2023

使用[清华镜像源](https://mirrors.tuna.tsinghua.edu.cn/CTAN/systems/texlive/Images/)安装，iso文件大小约为4.8G，可以打开advance选择仅安装中文和English，可节约1G空间。

### vscode

安装Latex Workshop，同时在打开用户设置settings.json文件按如下代码配置：

```json
"latex-workshop.latex.autoBuild.run": "never",
    "latex-workshop.showContextMenu": true,
    "latex-workshop.intellisense.package.enabled": true,
    "latex-workshop.message.error.show": false,
    "latex-workshop.message.warning.show": false,
    "latex-workshop.latex.tools": [
        {
            "name": "xelatex",
            "command": "xelatex",
            "args": [
                "-synctex=1",
                "-interaction=nonstopmode",
                "-file-line-error",
                "%DOCFILE%"
            ]
        },
        {
            "name": "pdflatex",
            "command": "pdflatex",
            "args": [
                "-synctex=1",
                "-interaction=nonstopmode",
                "-file-line-error",
                "%DOCFILE%"
            ]
        },
        {
            "name": "latexmk",
            "command": "latexmk",
            "args": [
                "-synctex=1",
                "-interaction=nonstopmode",
                "-file-line-error",
                "-pdf",
                "-outdir=%OUTDIR%",
                "%DOCFILE%"
            ]
        },
        {
            "name": "bibtex",
            "command": "bibtex",
            "args": [
                "%DOCFILE%"
            ]
        }
    ],
    "latex-workshop.latex.recipes": [
        {
            "name": "XeLaTeX",
            "tools": [
                "xelatex"
            ]
        },
        {
            "name": "PDFLaTeX",
            "tools": [
                "pdflatex"
            ]
        },
        {
            "name": "BibTeX",
            "tools": [
                "bibtex"
            ]
        },
        {
            "name": "LaTeXmk",
            "tools": [
                "latexmk"
            ]
        },
        {
            "name": "xelatex -> bibtex -> xelatex*2",
            "tools": [
                "xelatex",
                "bibtex",
                "xelatex",
                "xelatex"
            ]
        },
        {
            "name": "pdflatex -> bibtex -> pdflatex*2",
            "tools": [
                "pdflatex",
                "bibtex",
                "pdflatex",
                "pdflatex"
            ]
        },
    ],
    "latex-workshop.latex.clean.fileTypes": [
        "*.aux",
        "*.bbl",
        "*.blg",
        "*.idx",
        "*.ind",
        "*.lof",
        "*.lot",
        "*.out",
        "*.toc",
        "*.acn",
        "*.acr",
        "*.alg",
        "*.glg",
        "*.glo",
        "*.gls",
        "*.ist",
        "*.fls",
        "*.log",
        "*.fdb_latexmk"
    ],
    "latex-workshop.latex.autoClean.run": "onFailed",
    "latex-workshop.latex.recipe.default": "lastUsed",
    "latex-workshop.view.pdf.internal.synctex.keybinding": "double-click"
```

## tex基础语法

### 认识Latex

1. 保留字符

   > $ % &̂ _ { } \


   #: 自定义命令时，用于标明参数序号。
   $: 数学环境命令符。
   %: 注释符。在其后的该行命令都会视为注释。如果在回车前输入这个命令，
   可以防止行末LATEX 插入一些奇怪的空白符。
   ^: 数学环境中的上标命令符。
   &: 表格环境中的跳列符。
   _: 数学环境中的下标命令符。
   {与}: 花括号用于标记命令的必选参数，或者标记某一部分命令成为一个
   整体。
   \: 反斜杠用于开始各种LATEX 命令。
   以上除了反斜杠外，均能用前加反斜杠的形式输出。

2. 导言区

```latex
\documentclass[options]{doc-class}
\begin{document}
...
\end{document}
```

其中，在语句\begin{document}之前的内容称为导言区。导言区可以留空，
以可以进行一些文档的准备操作。你可以粗浅地理解为：导言区即模板定义。

### 标点与强调



### 格式控制

1. 换行+分段：用\par来产生一个带缩进的新段。

2. 段落之间的距离由\parskip控制，默认0pt plus 1pt.

   ```latex
   \setlength{\parskip}{0pt}
   ```

3. 分页：用`\newpage`命令开始新的一页。

4. 缩进和对齐：英文的段首不需要缩进。但是对中文而言，段首缩进需要借助indentfirst 宏包来完成。你可能还需要使用`\setlength\parindent{2em}`这样的命令来设置缩进距离。如果在句首强制取消缩进，你可以在段首使用`\noindent`命令。

5. 子标题

   `\section{}`和`\subsection{}`

6. 首行缩进2em：使用`\usepackage{indentfirst}`

### 字体与颜色

1. 

---

持续更新中···

![image-20240322125009542](C:\Users\Noble丶Ray\AppData\Roaming\Typora\typora-user-images\image-20240322125009542.png)
