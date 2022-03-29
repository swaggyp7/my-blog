title: Shell常用命令
author: John Doe
date: 2022-03-29 17:17:54
tags:
---
## 查看程序进程ID

```shell
ps -ef | grep [Process Name]
```

## 查看监听该端口的进程

```shell
sudo lsof -nP | grep LISTEN | grep [Port]
# or
sudo lsof -i :[Port]
```

## 查看该进程占用的端口

```shell
sudo lsof -nP -p [Process ID] | grep LISTEN
```

## 杀死进程

```shell
kill -9 [Process ID]
```

