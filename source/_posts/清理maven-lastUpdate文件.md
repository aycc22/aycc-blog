---
title: 清理maven .lastUpdate文件
date: 2019-08-01 16:38:06
tags: maven
---
Maven jar依赖下载失败时，有可能出现.lastUpdated结尾的文件，这时需要删除后，重新下载。
删除所有以.lastUpdate结尾的文件

1. 切换到maven的本地仓库

2. 在当前目录打开cmd命令行

3. 执行命令：for /r %i in (*.lastUpdated) do del %i
