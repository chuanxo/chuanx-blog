# 任务计划：Hugo 博客 + GitHub Pages

## 目标
搭建一个基于 Hugo 和 PaperMod 主题的全功能博客，部署到 GitHub Pages，包含自动化 CI/CD、评论系统（Giscus）、搜索功能和网站分析。

## 当前阶段
阶段 6

## 各阶段任务

### 阶段 1：需求分析与探索
- [x] 理解用户需求（Hugo + PaperMod + GitHub Pages）
- [x] 确定所需功能（评论、分析、搜索）
- [x] 探索当前项目状态
- **状态：** 已完成

### 阶段 2：Hugo 核心搭建
- [x] 初始化 Hugo 站点结构
- [x] 以 git submodule 方式安装 PaperMod 主题
- [x] 创建工作流和布局所需的目录结构
- **状态：** ✓ 已完成

### 阶段 3：配置文件创建
- [x] 创建 hugo.yaml 主配置文件
- [x] 创建 GitHub Actions 工作流文件
- [x] 创建 .gitignore 文件
- [x] 创建 Giscus 评论系统的 partial 模板
- [x] 创建文章模板（archetype）
- **状态：** ✓ 已完成

### 阶段 4：内容创建
- [x] 创建搜索页面
- [x] 创建归档页面
- [x] 创建关于页面
- [x] 创建示例博客文章（2篇）
- [x] 更新 README 项目文档
- **状态：** ✓ 已完成

### 阶段 5：本地测试
- [x] 使用 hugo server -D 测试
- [x] 验证所有页面正确加载
- [x] 测试导航和功能
- [x] 验证代码高亮效果
- **状态：** ✓ 已完成

### 阶段 6：GitHub 配置与部署
- [ ] 提交所有更改
- [ ] 推送到 GitHub
- [ ] 配置 GitHub Pages 设置
- [ ] 启用 GitHub Discussions
- [ ] 配置 Giscus 集成
- [ ] 设置 Google Analytics
- **状态：** 进行中

### 阶段 7：验证与完善
- [ ] 验证 GitHub Actions 工作流成功运行
- [ ] 测试线上网站功能
- [ ] 验证搜索功能
- [ ] 测试评论系统
- [ ] 记录最终配置说明
- **状态：** 待开始

## 关键问题
1. PaperMod 主题应该用 git submodule 吗？（是 - 便于更新）
2. 使用什么部署方式？（GitHub Actions - 自动化且现代）
3. 使用哪个评论系统？（Giscus - 基于 GitHub Discussions，无需外部服务）
4. 分析工具方案？（Google Analytics 4 - 用户要求）
5. 搜索如何实现？（PaperMod 内置 Fuse.js - 无需后端）

## 已做决策
| 决策 | 理由 |
|------|------|
| PaperMod 主题使用 git submodule | 便于更新，主题代码与内容清晰分离 |
| GitHub Actions 自动部署 | 2026年现代化标准，自动化流程 |
| Giscus 评论系统 | 使用 GitHub Discussions，无外部服务，支持主题同步 |
| YAML 配置格式 | 比 TOML 更易读，适合复杂配置 |
| Hugo extended 0.155.3 版本 | 最新稳定版，PaperMod SCSS 编译所需 |

## 遇到的错误
| 错误 | 尝试次数 | 解决方案 |
|------|---------|---------|
|      | 1       |         |

## 注意事项
- 用户系统需要安装 Hugo（本地测试时验证）
- Giscus 初始设置后需要手动配置步骤
- Google Analytics ID 需要用户创建 GA4 属性后添加
- baseURL 必须匹配 GitHub Pages URL: https://chuanxo.github.io/chuanx-blog/
