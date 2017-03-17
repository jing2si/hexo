---
title: Windows上的各种命令
date: 2016-05-23 13:16:54
tags:
  - 命令
  - npm
categories: 前端
---

## 设置npm镜像

```bash
npm config set registry https://registry.npm.taobao.org
npm config set disturl https://npm.taobao.org/dist
npm config set SASS_BINARY_SITE https://npm.taobao.org/mirrors/node-sass/
npm config set PHANTOMJS_CDNURL https://npm.taobao.org/mirrors/phantomjs/
npm config set ELECTRON_MIRROR https://npm.taobao.org/mirrors/electron/
```

## 设置npm代理

```bash
npm config set proxy=代理host
```

## 生成新文件

cmd

```bash
echo {} > .eslintrc
```

[cmder](http://cmder.net/)

```bash
touch .eslintrc
```

PowerShell

```bash
New-Item .eslintrc
```