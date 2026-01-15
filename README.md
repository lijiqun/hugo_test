# Hugo Blog

这是一个使用 Hugo 构建的静态博客网站。

## 本地运行

```bash
hugo server
```

访问 http://localhost:1313

## 部署到 GitHub Pages

### 步骤 1: 创建 GitHub 仓库

1. 访问 https://github.com/new
2. 创建一个新仓库，例如：`my-hugo-blog`
3. **不要**初始化 README、.gitignore 或 license

### 步骤 2: 推送代码到 GitHub

将下面的命令中的 `YOUR_USERNAME` 替换为你的 GitHub 用户名：

```bash
git init
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/my-hugo-blog.git
git push -u origin main
```

### 步骤 3: 启用 GitHub Pages

1. 进入仓库的 **Settings** (设置)
2. 点击左侧的 **Pages**
3. 在 **Build and deployment** 下：
   - **Source** 选择：**GitHub Actions**
4. 保存设置

GitHub Actions 会自动构建并部署你的网站。

### 步骤 4: 访问你的网站

部署完成后（约1-2分钟），访问：
```
https://YOUR_USERNAME.github.io/my-hugo-blog/
```

## 发布新文章

```bash
hugo new content posts/new-post.md
```

编辑文件后，推送更改到 GitHub：
```bash
git add .
git commit -m "Add new post"
git push
```

GitHub Actions 会自动重新部署。
