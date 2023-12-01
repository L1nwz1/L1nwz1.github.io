---
title: 我的常用软件和工作环境
date: 2023-11-30 13:51 +0800
categories: [工具]
tags: [推荐,windows]     # TAG names should always be lowercase
---

## 系统环境/工具
主系统Windows+虚拟Linux系统WSL2(Ubuntu22.04LTS)  
因为主系统Windows自然不必多说，下面介绍一下WSL2：  
相比于以往的WSL1，WSL2使用的是真Linux内核，而WSL1则是假Linux内核的虚拟机(VM)，相比于VMware，WSL2使用更少的内存和磁盘空间，I/O、网络性能也更好，而且只需在命令行输入：  
```cmd 
>wsl
Welcome to Ubuntu 22.04.2 LTS (GNU/Linux 5.10.16.3-microsoft-standard-WSL2 x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/advantage


This message is shown once a day. To disable it please create the
/root/.hushlogin file.
root@xxx:#
```

即可启动。  
但毕竟不是原生Linux系统，其稳定性和指令完整性不能保证，所以如有需要，还是自己弄一个原生Linux系统或者云服务器较好，用WSL主要也是追求方便。
> 有一个小问题，如果你使用Android模拟器例如MUMU模拟器，会与WSL发生冲突，请自行选择。
{: .prompt-warning }
### everything
快速寻找文件，输入文件名即可快速寻找文件，实用方便，Windows内置的搜索速度实在是太感人了(ˉ▽ˉ；)...
### notepad++
加了点功能的编辑器，又没有别的IDE那么臃肿，人称大型记事本，适用于临时修改一些小代码，支持代码高亮，宏。  
可以在Word文档中高亮或者突出代码块，具体方法是：
打开notepad++，选中想要复制的代码段，点击上方的`插件`->`NppExport`->`Copy HTML to clipboard`.
### gitbash
小型linux终端，在Windows上模拟linux命令，我常用于对当前文件夹进行git操作。

### vscode以及小插件

#### background
一款修改你vscode背景的插件，二次元必备.

#### github copilot
一个代码智能提示工具，很早就由GPT-4.0驱动，以后肯定还会继续更新。不用动脑，只需提供思路就可以给到很好的补全效果，谁用谁知道。

#### Markdown Preview Enhanced
实时预览markdown文件的插件，使用方法：  
在markdown文件页面按下`ctrl+k`+`v`.
配合网页，可在setting中自行修改latex/Mathjax等数学公式的渲染方式。

#### Remote
ssh插件，在vscode中编辑远程代码。

## 网站工具

### 网站以及评论功能的搭建
JerkII+github page+waline，部署过程请看[如何部署github page静态博客以及过程中踩过的坑](https://l1nwz1.cc/posts/Githubpage/)。

### 数学公式显示
采用MathJax显示公式，由于markdown的kramdown语法和MathJax语法有所冲突，需要修改一部分内容。下面介绍的是JerkII下的MathJax配置：  
1. 全局配置：  
在`_layout`文件夹中的`post.html`中加入
```javascript
<script type="text/javascript" id="MathJax-script" async
      src="https://cdn.jsdelivr.net/npm/mathjax@4.0.0-beta.3/tex-mml-chtml.js">
      </script>
```
即可在所有的page下配置MathJax数学公式渲染。
2. 单个页面配置：  
在需要渲染数学公式的markdown文件中加入：  
```javascript
<script type="text/javascript" id="MathJax-script" async
      src="https://cdn.jsdelivr.net/npm/mathjax@4.0.0-beta.3/tex-mml-chtml.js">
      </script>
```
即可，MathJax版本可选，这里用的是4.0.0的beta-3版本。

此外，由于冲突问题，我一律推荐使用
```
\\(数学公式\\):不换行插入公式
\\[数学公式\\]:换行居中插入公式
```

还有，由于MathJax的蜜汁bug，有些矩阵或者特定排布需要换行时使用双斜杠可能会失效，这里采用的简单粗暴的办法是直接在你需要支持中间换行的数学公式外套上html标签如div标签
```
<div>
\[
P=\begin{Vmatrix}
P_{00} & P_{01} & P_{02} & ... \\
P_{10} & P_{11} & P_{12} & ... \\
P_{20} & P_{21} & P_{22} & ... \\
P_{30} & P_{31} & P_{32} & ... \\
\end{Vmatrix}
\] 
<div>
```
这样可以保证矩阵每一行的换行。
### wiki
mkdocs，部署于github page，[L1nwz1's wiki](https://l1nwz1.cc/wiki/).

