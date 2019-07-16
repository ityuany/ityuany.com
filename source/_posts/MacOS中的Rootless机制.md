---
title: MacOS中的Rootless机制
categories:
  - Mac
tags:
  - Rootless
abbrlink: 8714
date: 2019-07-16 21:00:22
---

![](https://ityuany.oss-cn-hangzhou.aliyuncs.com/blogs/macos.jpg?x-oss-process=style/Blogs)

<!-- more -->

# 是什么？
Mac OS X EL Capitan 10.11版本的操作系统开始使用Rootless机制，这玩意主要就是限制了不允许用户针对以下3个目录的文件进行修改操作

- /system
- /sbin
- /usr

# 怎么开关Rootless机制？
重启Mac , 听到开机启动声之后按下 command + R 进入恢复模式，在实用工具中打开 Termial(终端工具) 

- 关闭Rootless

		csrutil disable	
		
- 开启Rootless

		csrutil enable
		
回车、重启、生效