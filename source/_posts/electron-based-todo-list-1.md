---
title: 基于electron的待办清单 (1)
date: 2025-11-03 23:47:38
tags:
---
想要找一个待办清单软件，满足这些要求：

- 本地存储，但是支持导出备份
- 支持设置截止时间，支持按照时间筛选和排序
- 支持设置周期任务
- 支持拆解子任务
- 已完成的任务自动折叠

其实最接近需求的是 Google Tasks 和 [好用便签](https://www.haoyong333.com/) ，但前者需要联网，后者会一直提示登录，而且链接无法直接打开。

因此萌生了自己做一个待办清单工具的想法。至于为什么选择Electron这么重的框架做这么小型的工具，主要还是为了学习和实践Electron的用法。以后不排除会试着用其他框架重写。

先参考 [Electron文档](https://www.electronjs.org/zh/docs/latest/) ，搭建Electron框架。

使用pnpm安装Electron时，需要执行 `pnpm approve-builds` ，才能运行postinstall脚本，实际完成安装。

postinstall脚本下载很慢，可以通过 `.npmrc` 文件指定npm和Electron的镜像地址加速。
