---
title: 我的常用软件和工作环境
date: 2023-11-30 13:51 +0800
categories: [工具]
tags: [推荐]     # TAG names should always be lowercase
---

## 系统环境
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
## everything
快速寻找文件，输入文件名即可快速寻找文件，实用方便，Windows内置的搜索速度实在是太感人了(ˉ▽ˉ；)...
## notepad++
加了点功能的编辑器，又没有别的IDE那么臃肿，人称大型记事本，适用于临时修改一些小代码，支持代码高亮，宏。
可以在Word文档中高亮或者突出代码块，具体方法是：
打开notepad++，选中想要复制的代码段，点击上方的`插件`->`NppExport`->`Copy HTML to clipboard`.
## gitbash
小型linux终端，在Windows上模拟linux命令，我常用于对当前文件夹进行git操作。

