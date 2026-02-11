# Chuanx Blog

[![Deploy Hugo site to Pages](https://github.com/chuanxo/chuanx-blog/actions/workflows/hugo.yaml/badge.svg)](https://github.com/chuanxo/chuanx-blog/actions/workflows/hugo.yaml)

基于 [Hugo](https://gohugo.io/) 和 [PaperMod](https://github.com/adityatelange/hugo-PaperMod) 主题构建的个人博客。

## 网站地址

访问博客：[https://chuanxo.github.io/chuanx-blog/](https://chuanxo.github.io/chuanx-blog/)

## 功能特性

- 全文搜索功能
- 评论功能（基于 [Giscus](https://giscus.app/) 和 GitHub Discussions）
- Google Analytics 4 网站分析
- 深色/浅色模式切换
- 完全响应式设计
- 极快的页面加载速度
- 通过 GitHub Actions 自动部署

## 技术栈

- **Hugo** (v0.155.3+) - 静态网站生成器
- **PaperMod** - Hugo 主题（git submodule）
- **GitHub Actions** - CI/CD 流水线
- **GitHub Pages** - 托管服务

## 创建新文章

```bash
hugo new posts/my-post-title.md
```

编辑 `content/posts/my-post-title.md` 文件，准备发布时将 `draft` 设置为 `false`。

## 本地开发

```bash
# 克隆仓库（包含子模块）
git clone --recurse-submodules git@github.com:chuanxo/chuanx-blog.git
cd chuanx-blog

# 启动 Hugo 服务器
hugo server -D

# 访问 http://localhost:1313/chuanx-blog/
```

## 更新主题

```bash
git submodule update --remote --merge
```

## 许可证

内容采用 [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/) 许可。
