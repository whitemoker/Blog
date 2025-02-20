---
title: 个人博客搭建实现指南
date: 2025-02-20
toc: true
---

# 个人博客搭建实现指南

## 技术栈详解
1. 核心环境
   - Node.js v22.12.0 (运行环境)
   - npm v10.8.3 (包管理器)

2. 博客框架
   - Hexo v4.3.2 (静态博客生成器)
   - hexo-toc (文章目录生成插件)

3. 部署平台
   - GitHub Pages (静态网站托管)
   - Git (版本控制)

4. 内容格式
   - Markdown (文章编写格式)
   - Front Matter (文章元数据配置)

## 实现步骤

### 1. 环境准备
```bash
# 检查 Node.js 环境
node -v  # v22.12.0
npm -v   # 10.8.3

# 安装 Hexo CLI
npm install -g hexo-cli
```

### 2. 项目初始化
```bash
# 创建并初始化博客项目
mkdir my-blog
cd my-blog
hexo init
npm install

# 安装 Git 部署插件
npm install hexo-deployer-git --save
```

### 3. 项目配置
主要配置文件为 `_config.yml`，包含以下关键配置：
- 基本信息（标题、作者等）
- URL 设置（GitHub Pages 地址）
- 文章设置（支持 Markdown）
- 主题设置（使用简洁的 landscape 主题）
- 部署设置（GitHub Pages 配置）

### 4. 文章管理
Hexo 支持两种方式管理文章：
1. Git 方式：直接编辑 source/_posts 目录下的 .md 文件
2. Web 界面：通过 GitHub 网页编辑器修改文件

### 5. 部署流程
1. 本地测试：
   ```bash
   hexo clean    # 清理缓存
   hexo generate # 生成静态文件
   hexo server   # 本地预览
   ```

2. 提交更改：
   ```bash
   git commit -m "更新说明"
   git push
   ```

3. 访问 https://whitemoker.github.io/Blog 查看更新
