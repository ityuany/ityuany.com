---
title: MacOS中的Rootless机制
categories:
  - MacOS
tags:
  - Rootless
abbrlink: 8714
date: 2019-07-16 21:00:22
---

# 是什么？

Mac OS X EL Capitan 10.11 版本的操作系统开始使用 Rootless 机制，这玩意主要就是限制了不允许用户针对以下 3 个目录的文件进行修改操作

- /system
- /sbin
- /usr

# 怎么开关 Rootless 机制？

重启 Mac , 听到开机启动声之后按下 command + R 进入恢复模式，在实用工具中打开 Termial(终端工具)

- 关闭 Rootless

      		csrutil disable

* 开启 Rootless

      		csrutil enable

回车、重启、生效
