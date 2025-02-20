---
title: Hexo博客环境搭建指南
date: 2025-02-20
tags: [教程, 入门]
categories: 指南
toc: true
---

# Hexo博客环境搭建指南

## 环境准备

### 1. 安装Node.js
1. 访问 [Node.js官网](https://nodejs.org)
2. 下载并安装Node.js (建议选择LTS版本)
3. 安装完成后，打开命令行验证：
   ```bash
   node -v  # 检查Node.js版本
   npm -v   # 检查npm版本
   ```

### 2. 安装Hexo命令行工具
```bash
npm install -g hexo-cli
```

## 初始化博客项目

### 1. 创建项目目录
```bash
mkdir my-blog
cd my-blog
```

### 2. 初始化Hexo
```bash
# 初始化项目
hexo init

# 安装依赖
npm install
```

### 3. 获取现有博客内容
```bash
# 克隆仓库
git clone https://github.com/whitemoker/Blog.git temp

# 复制文章
cp -r temp/source/_posts/* source/_posts/

# 清理临时文件
rm -rf temp
```

## 写作和发布文章

### 1. 创建新文章
```bash
# 方法一：使用Hexo命令
hexo new post "文章标题"

# 方法二：直接在source/_posts目录创建.md文件
```

### 2. Markdown文件格式
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

### 3. 生成和预览
```bash
# 清理旧文件
hexo clean

# 生成静态文件
hexo generate

# 本地预览（可选）
hexo server
```

### 4. 提交更改
```bash
# 提交Markdown源文件
git add source/_posts/your-article.md
git commit -m "Add new article: 文章标题"

# 生成并提交静态文件
hexo generate
git add public/
git commit -m "Generate static files for new article"

# 推送到GitHub
git push origin gh-pages
```

## 常见问题

### 1. npm安装失败
- 检查Node.js是否正确安装
- 尝试使用管理员权限运行命令
- 检查网络连接

### 2. hexo命令未找到
- 确保全局安装了hexo-cli
- 重新运行 `npm install -g hexo-cli`

### 3. 文章不显示
- 确保文章front-matter格式正确
- 运行 `hexo clean && hexo generate`
- 检查文件编码是否为UTF-8

## 维护建议

1. 定期更新依赖：
   ```bash
   npm update
   ```

2. 备份源文件：
   - 保持source/_posts目录的内容备份
   - 定期提交到git仓库

3. 本地测试：
   - 修改后先本地预览
   - 确认无误后再推送到GitHub

