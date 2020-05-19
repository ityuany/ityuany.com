---
title: MacOS文件夹多语言显示设置
categories:
  - MacOS
tags:
  - 多语言
abbrlink: 37630
date: 2019-07-16 21:17:48
---

# 什么是多语言显示？

比如我们在 Finder 中看到的桌面、下载等中文描述的文件夹，实际上我们在执行终端命令的时候，我们会发现它都是英文的。

# 怎么实现？

- 授权

  - 进入系统目录

        		cd /System/Library/CoreServices/SystemFolderLocalizations/zh_CN.lproj


  - 授权

        		sudo chmod -R 777 *

* 转换格式

      文件本身的格式是二进制，所以需要转换为可读的文件进行修改，以下两种方式根据自己的习惯可选。

  - 转化为 JSON 文件
    plutil -convert json SystemFolderLocalizations.strings

  - 转化为 XML 文件

        		plutil -convert xml1 SystemFolderLocalizations.strings

- 添加配置

      		这里不做详细解释，配置文件转换格式之后基本上都能看的明白怎么添加配置


* 转换格式

      		格式再转回二进制：plutil -convert binary1 SystemFolderLocalizations.strings

- 添加文件

      		去你配置了多语言的文件夹下新增 .localized 空文件， 表示该文件夹需要支持多语言。


- 重启 Finder

      		执行命令：pkill Finder
