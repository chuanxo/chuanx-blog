---
title: "如何搭建这个 Hugo 博客"
date: 2026-02-12T00:00:00+08:00
draft: false
slug: "hugo-setup"
tags: ["hugo", "教程", "github-pages"]
categories: ["技术"]
author: "Chuanx"
showToc: true
TocOpen: true
description: "搭建 Hugo + PaperMod + GitHub Pages 博客的详细指南"
summary: "一步步记录使用 Hugo 和 PaperMod 主题配合 GitHub Pages 创建博客的过程"
comments: true
---

## 概述

本文记录了搭建本博客的全过程，希望能帮助想创建类似网站的朋友。

## 技术栈

- **Hugo** (v0.155.3+) - 静态网站生成器
- **PaperMod** - Hugo 主题
- **GitHub Actions** - CI/CD 流水线
- **GitHub Pages** - 托管服务

## 安装步骤

### 1. 初始化 Hugo 站点

```bash
hugo new site myblog --format yaml
cd myblog
```

### 2. 安装 PaperMod 主题

使用 git submodule 便于后续更新：

```bash
git submodule add --depth=1 https://github.com/adityatelange/hugo-PaperMod.git themes/PaperMod
```

### 3. 配置 hugo.yaml

关键配置部分：

- 基础设置（URL、标题、主题）
- PaperMod 参数
- 菜单结构
- 搜索功能
- 分析集成

### 4. GitHub Actions 工作流

创建 `.github/workflows/hugo.yaml` 实现 main 分支推送时的自动部署。

### 5. 启用 GitHub Pages

仓库设置 → Pages → 来源：GitHub Actions

## 已实现的功能

### 搜索功能

PaperMod 内置了基于 Fuse.js 的搜索。只需：

1. 在配置中启用 JSON 输出
2. 创建带有 `layout: search` 的搜索页面

### 评论系统

集成了基于 GitHub Discussions 的 Giscus：

- 无需数据库
- 通过 GitHub 进行审核
- 与网站主题自动同步

### 网站分析

只需在配置中添加 Google Analytics 的测量 ID 即可。

## 部署流程

每次推送到 `main` 分支会触发：

1. Hugo 构建并压缩
2. 上传到 GitHub Pages
3. 自动部署

网站地址：`https://chuanxo.github.io/chuanx-blog/`

## 结语

Hugo + PaperMod + GitHub Pages 是打造现代、快速、易维护博客的绝佳组合。

整套搭建过程不到一小时，现在我就拥有了一个功能齐全、零托管成本的博客！
