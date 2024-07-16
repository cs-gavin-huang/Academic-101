### Overleaf 使用入门：面向CS学术论文

#### 目录
0. [引言](#引言)
1. [自己创建空白文档注意事项](#自己创建空白文档注意事项)
    1. [注册Overleaf账号](#注册Overleaf账号)
    2. [创建空白项目](#创建空白项目)
    3. [基本Latex语法](#基本Latex语法)
2. [使用学术会议模板](#使用学术会议模板)
    1. [找到会议官网并下载模板](#找到会议官网并下载模板)
    2. [导入模板并编辑](#导入模板并编辑)
3. [通过arXiv获取他人的TeX源文件](#通过arXiv获取他人的TeX源文件)
    1. [在arXiv上查找论文](#在arXiv上查找论文)
    2. [下载并上传TeX源文件](#下载并上传TeX源文件)
    3. [编辑和编译论文](#编辑和编译论文)

---
### 引言
尽管可以在本地部署LaTeX编辑环境，例如通过安装TeX Live或MikTeX，并使用编辑器如TeXstudio或VS Code进行编辑，但这些方式通常涉及较为复杂的配置和维护。

相比之下，Overleaf是一款在线LaTeX编辑器，省去了本地部署的麻烦，并且在大部分情况下是免费的。Overleaf不仅支持多平台访问，还提供了强大的协作功能，非常适合撰写学术论文。


### 自己创建空白文档注意事项

#### 注册Overleaf账号

![Overleaf注册](https://i.postimg.cc/25d069LM/Pix-Pin-2024-07-16-14-30-50.png)

1. 访问[Overleaf官网](https://www.overleaf.com/)，点击右上角的“注册”按钮。
2. 输入您的邮箱地址和密码，或使用Google、ORCID等第三方账号注册。

#### 创建空白项目
![Overleaf新建项目](https://i.postimg.cc/rs51nKGb/Pix-Pin-2024-07-16-14-40-19.png)
1. 登录后点击左上角的“New Project”按钮。
2. 选择“Blank Project”创建一个空白项目。
3. 为项目命名并点击“Create”按钮。

#### 基本Latex语法
```latex
\documentclass{article}
\begin{document}
\title{Your Paper Title}
\author{Your Name}
\date{\today}
\maketitle
\begin{abstract}
This is the abstract of the paper.
\end{abstract}
\section{Introduction}
This is the introduction section.
\end{document}
```

其中：
1. `\documentclass{article}`指定文档类型为文章，
2. `\title{}`、`\author{}`和`\date{}`分别设置标题、作者和日期，
3. `\maketitle`生成标题页，
4. `\begin{abstract}`和`\end{abstract}`包裹摘要内容，
5. `\section{}`和`\subsection{}`用于生成章节和子章节。

![Overleaf生成预览](https://i.postimg.cc/tCnxq1LV/Title-page.png)

#### 重要元素

- **图片**


![图片插入](https://i.postimg.cc/NM7KnVPs/Pix-Pin-2024-07-16-15-52-35.png)

```latex
\usepackage{graphicx}  % 导入图片包，一般放在开头，不需要重复放置

\begin{figure}

\centering % 图片居中
\includegraphics[width=0.5\textwidth]  {example-image-a.png}
% 宽度为当页宽度的一半 \textwidth即原宽度  % 图片文件名
\caption{This is a figure} % 图题
\label{fig:example} % 图标签， 从而可以在正文中索引

\end{figure}
```
---
---


![图片文件夹](https://i.postimg.cc/Nf1r2Kx9/Pix-Pin-2024-07-16-15-54-55.png)

0. 图片文件夹: 一般将图片放在一个文件夹中，方便管理。

---

![矢量图](https://i.postimg.cc/jd5StCFY/Pix-Pin-2024-07-16-16-07-18.png)

1. 矢量图：图片何必是图片，很多会议或者期刊会要求使用矢量图，如PDF，SVG等。很多时候一些模型图，在PPT绘制完毕后，可以直接导出为PDF（文字），然后以图片形式插入到LaTeX中。
```latex
\begin{figure}

\centering
\includegraphics[width=\textwidth]{image/alphabet.pdf}
\caption{This is vector alphabet} 
\label{fig:vector}
\end{figure}

```
---

2. 正文引用：使用`\ref{fig:example}`或者`~\ref(fig:example)`，这样在正文中引用时，自动进行编号。

---
3. 图片位置：可以使用`[h]`，`[t]`，`[b]`，`[p]`，`[!]`等参数，来控制图片的位置，然而图片的大小是影响版面的主要因素，可以合理控制宽度从而使在页面中的位置可控。







### 使用学术会议模板

#### 找到会议官网并下载模板
1. 访问目标学术会议的官方网站（例如，ACM、IEEE、会议等）。
2. 在网站上找到论文提交指南（通常在“Submission”或“Authors”部分）。
3. 下载官方提供的LaTeX模板包，一般举办多年的直接参照往年的模板就可以了，没有太大变化。

#### 导入模板并编辑
1. 解压下载的模板包。
2. 在Overleaf项目中，点击左侧文件树顶部的“Upload”按钮。
3. 上传模板包中的所有文件。
4. 编辑主文件（通常是`sample.tex`或`conference.tex`），按照会议要求撰写论文。

### 通过arXiv获取他人的TeX源文件
- 什么需要这个步骤：你做的恰好是作者同样的领域，并且使用差不多的数学公式，这样你可以直接参考他们的公式以及latex标记，而不用自己重新写一遍。

#### 在arXiv上查找论文
1. 访问[arXiv官网](https://arxiv.org/)。
2. 在搜索栏中输入感兴趣的论文标题、作者或关键词进行搜索。
3. 找到目标论文后，点击其标题进入详情页面。

#### 下载并上传TeX源文件
1. 在论文详情页面，点击“Download”按钮。
2. 选择“Other formats”中的“Source”下载TeX源文件包。
3. 在Overleaf项目中，点击左侧文件树顶部的“Upload”按钮。
4. 上传下载的TeX源文件包中的所有文件。

#### 编辑和编译论文
1. 找到并打开主文件（通常是`main.tex`或`ms.tex`）。
2. 根据需要修改内容，并点击“Recompile”按钮进行编译预览。
3. 确认无误后，点击“Download PDF”按钮下载最终的PDF文件。

---

以上三个部分分别介绍了如何创建空白文档、使用学术会议模板以及通过arXiv获取他人的TeX源文件进行编辑。希望这些步骤和示例对你有所帮助！下面是一些可以深入学习的Latex的资源：

1. 
