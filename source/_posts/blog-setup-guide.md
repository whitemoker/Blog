---
title: 个人博客搭建实现指南
date: 2025-02-20
tags: [教程, 入门]
categories: 指南
toc: true
---

# 个人博客搭建实现指南

## 环境要求
1. Node.js
   - 版本要求：>= 12.0
   - 下载地址：https://nodejs.org
   - 安装后会自动包含 npm 包管理器

2. Hexo CLI
   ```bash
   # 安装 Hexo 命令行工具
   npm install -g hexo-cli
   ```

## 技术栈详解
1. 核心环境
   - Node.js v22.12.0 (运行环境)
   - npm v10.8.3 (包管理器)
   - Hexo CLI (命令行工具)

2. 博客框架
   - Hexo v4.3.2 (静态博客生成器)
   - hexo-toc (文章目录生成插件)

3. 部署平台
   - GitHub Pages (静态网站托管)
   - Git (版本控制)

4. 内容格式
   - Markdown (文章编写格式)
   - Front Matter (文章元数据配置)

## 文章上传和更新流程

### 方法一：GitHub网页方式
1. 访问 https://github.com/whitemoker/Blog
2. 进入 source/_posts 目录
3. 点击 "Add file" 按钮上传 .md 文件
4. 提交文件后，需要在本地生成静态文件：
   ```bash
   # 克隆仓库
   git clone https://github.com/whitemoker/Blog.git
   cd Blog
   
   # 安装依赖
   npm install
   npm install hexo-cli
   
   # 生成静态文件
   hexo clean
   hexo generate
   
   # 提交生成的文件
   git add public/
   git commit -m "Generate static files for new blog post"
   git push origin gh-pages
   ```

### 方法二：Git命令行方式
1. 克隆仓库：
   ```bash
   git clone https://github.com/whitemoker/Blog.git
   cd Blog
   ```

2. 添加文章：
   - 将 .md 文件复制到 source/_posts/ 目录
   - Markdown文件格式示例：
     ```markdown
     ---
     title: 文章标题
     date: 2025-02-20
     tags: [标签1, 标签2]
     categories: 分类
     toc: true
     ---
     
     # 一级标题
     
     ## 二级标题
     
     ### 三级标题
     
     文章内容...
     ```

3. 生成静态文件：
   ```bash
   # 安装依赖
   npm install
   npm install hexo-cli
   
   # 生成静态文件
   hexo clean
   hexo generate
   ```

4. 提交更改：
   ```bash
   # 提交Markdown源文件
   git add source/_posts/your-article.md
   git commit -m "Add new article: 文章标题"
   
   # 提交生成的静态文件
   git add public/
   git commit -m "Generate static files for new article"
   
   # 推送到GitHub
   git push origin gh-pages
   ```

### 注意事项
1. 所有更改都在 gh-pages 分支上进行
2. 每次添加新文章后都需要重新生成静态文件
3. 文章会显示在 https://whitemoker.github.io/Blog

## 实现步骤

[原有内容保持不变...]
