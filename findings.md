# 研究发现与决策

## 需求清单
<!-- 从用户请求中提取 -->
- 使用 Hugo 搭建博客网站
- 托管到 GitHub Pages
- 使用 PaperMod 主题
- 包含评论系统（Giscus + GitHub Discussions）
- 包含网站分析（Google Analytics 4）
- 包含搜索功能（PaperMod 内置）
- 通过 GitHub Actions 自动部署

## 研究发现
<!-- 探索过程中的关键发现 -->
- 当前项目是全新的 git 仓库，只有 README.md
- Git 远程仓库已配置：git@github.com:chuanxo/chuanx-blog.git
- Hugo 尚未初始化 - 完全空白的起点
- PaperMod 是 2026 年推荐的主题 - 快速、功能丰富、文档完善
- PaperMod 需要 Hugo extended 版本来编译 SCSS
- GitHub Actions 现在是推荐的部署方法（取代了 gh-pages 分支方法）
- PaperMod 内置使用 Fuse.js 的搜索功能（客户端，无需后端）
- Giscus 是基于 GitHub Discussions 的评论系统（无需外部服务）

## 技术决策
| 决策 | 理由 |
|------|------|
| 主题使用 git submodule | 清晰分离，通过 `git submodule update --remote` 轻松更新 |
| YAML 配置格式 | 复杂配置下比 TOML 更易读 |
| GitHub Actions 工作流 | 2026 年 GitHub Pages 的现代标准，自动部署 |
| Hugo 0.155.3 extended | 最新稳定版本，PaperMod SCSS 所需 |
| Giscus 评论系统 | GitHub 原生，无外部服务，支持主题同步 |
| Fuse.js 搜索 | PaperMod 内置，客户端实现，无需后端 |
| JSON 输出格式 | 搜索索引生成所需 |

## 遇到的问题
| 问题 | 解决方案 |
|------|---------|
| hugo new site 需要 --force 标志 | 目录非空（有 README.md 和 .git） |

## 资源链接
<!-- URL、文件路径、API 参考 -->
- PaperMod 安装指南：https://github.com/adityatelange/hugo-PaperMod/wiki/Installation
- Hugo GitHub Pages 部署：https://gohugo.io/host-and-deploy/host-on-github-pages/
- Giscus 配置：https://giscus.app/
- PaperMod Wiki：https://github.com/adityatelange/hugo-PaperMod/wiki
- Hugo 配置文档：https://gohugo.io/configuration/

## 实现后的项目结构
```
chuanx-blog/
├── .github/workflows/hugo.yaml    # CI/CD 流水线
├── archetypes/posts.md            # 文章模板
├── content/
│   ├── posts/                     # 博客文章
│   ├── about.md                   # 关于页面
│   ├── archives.md                # 归档列表
│   └── search.md                  # 搜索页面
├── layouts/partials/
│   └── comments.html              # Giscus 集成
├── themes/PaperMod/               # Git submodule
├── hugo.yaml                      # 主配置文件
├── .gitignore                     # 忽略规则
└── README.md                      # 项目文档
```

## 关键配置要点

### hugo.yaml 核心设置
```yaml
baseURL: "https://chuanxo.github.io/chuanx-blog/"
theme: ["PaperMod"]
outputs:
  home: [HTML, RSS, JSON]  # JSON 用于搜索

services:
  googleAnalytics:
    id: G-XXXXXXXXXX  # 需要替换

params:
  env: production
  comments: true
  ShowReadingTime: true
  ShowShareButtons: true
  ShowCodeCopyButtons: true
  fuseOpts:  # 搜索配置
    keys: ["title", "permalink", "summary", "content"]
```

### GitHub Actions 工作流要点
- Hugo 版本：0.155.3 extended
- 触发条件：推送到 main 分支
- Submodules：递归获取
- 部署：通过 actions/deploy-pages@v4 到 GitHub Pages

### Giscus 集成要点
- 仓库：chuanxo/chuanx-blog
- 映射方式：pathname
- 主题：preferred_color_scheme（自动同步网站主题）
- 条件渲染：基于 front matter

## 视觉/浏览器发现
<!-- 关键：每 2 次 view/browser 操作后更新 -->
- 本任务无需视觉/浏览器研究

---
*每 2 次 view/browser/search 操作后更新此文件*
