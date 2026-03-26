# ALZnote - 个人知识库

[![部署状态](https://github.com/zykkkl/ALZnote.github.io/workflows/Deploy%20Site/badge.svg)](https://github.com/zykkkl/ALZnote.github.io/actions)

> 为了找寻曾经的热爱

这是一个基于 Zensical 构建的个人知识库网站，记录我的学习笔记、技术分享和个人思考。

## 🌟 功能特性

- **学习笔记**: CS 课程笔记（MIT 6.092、UMich CV、UCB CS61A、SJTU AI2615）、离散数学、日语学习
- **博客系统**: 月度随笔和个人思考，支持按时间归档
- **标签分类**: 文章标签系统，方便内容检索
- **全文搜索**: 支持中文分词的智能搜索
- **评论互动**: 基于 GitHub Discussions 的 Giscus 评论系统
- **RSS 订阅**: 支持 RSS feed 订阅更新
- **数学公式**: 支持 LaTeX 数学公式渲染
- **暗色模式**: 优化的日间/夜间模式切换
- **思维导图**: Markmap 可视化支持
- **图片预览**: Lightbox 图片查看器

## 🚀 本地开发

### 环境要求

- Python 3.11+
- pip

### 安装依赖

```bash
pip install -r requirements.txt
```

### 本地预览

```bash
zensical serve
```

访问 http://127.0.0.1:8000 查看网站。

### 构建网站

```bash
zensical build --clean
```

生成的静态文件位于 `site/` 目录。

## 📦 部署

本项目使用 GitHub Actions 自动部署到 GitHub Pages。每次推送到 main 分支时，会自动触发构建和部署流程。

手动部署命令（本地仅构建）：

```bash
zensical build --clean
```

## 🛠️ 技术栈

- [Zensical](https://zensical.org/) - 静态站点生成器
- [PyMdown Extensions](https://facelessuser.github.io/pymdown-extensions/) - Markdown 扩展
- [Giscus](https://giscus.app/) - 评论系统
- [MathJax](https://www.mathjax.org/) - 数学公式渲染
- [Markmap](https://markmap.js.org/) - 思维导图
- [Jieba](https://github.com/fxsjy/jieba) - 中文分词

## 📝 内容结构

```
docs/
├── index.md              # 首页
├── Note/                 # 学习笔记
│   ├── Classthought/     # 课程笔记
│   ├── Jap/              # 日语学习
│   └── Refold/           # Refold 语言习得
├── thought/              # 个人思考
│   ├── suibi/            # 月度随笔（博客）
│   ├── Trans/            # 转载文章
│   └── zhaichao/         # 摘抄
└── tech/                 # 实用工具
```

## 📄 许可证

Copyright © 2024 ZAL

## 🔗 链接

- 网站: https://ALznote.org/greater
- GitHub: https://github.com/zykkkl
- Bilibili: https://space.bilibili.com/252925972
