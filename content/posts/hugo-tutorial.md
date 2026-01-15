+++
date = '2026-01-15T10:01:26+08:00'
draft = false
title = '如何使用Hugo发布新文章'
+++

Hugo 是一个快速的静态网站生成器。下面介绍如何使用 Hugo 发布新文章。

## 创建新文章

使用 `hugo new content` 命令创建新文章：

```bash
hugo new content posts/my-new-post.md
```

这会在 `content/posts/` 目录下创建一个 Markdown 文件。

## 编辑文章

打开创建的文件，你会看到 Front Matter（前置元数据）：

```toml
+++
date = '2026-01-15T10:01:26+08:00'
draft = true
title = '文章标题'
+++
```

### Front Matter 说明

- `title`: 文章标题
- `date`: 发布日期
- `draft`: 是否为草稿
  - `true`: 草稿状态，构建时不会包含
  - `false`: 发布状态，会显示在网站上

在 Front Matter 下方使用 Markdown 语法编写文章内容。

## 发布文章

### 方式一：修改 draft 状态

将 `draft = true` 改为 `draft = false`，然后启动服务器：

```bash
hugo server
```

### 方式二：构建时包含草稿

如果想预览草稿文章，可以使用：

```bash
hugo server --buildDrafts
```

## 本地预览

启动开发服务器：

```bash
# 基本启动
hugo server

# 绑定所有网卡（局域网访问）
hugo server --bind 0.0.0.0

# 指定端口
hugo server --port 1313

# 包含草稿
hugo server --buildDrafts
```

访问 http://localhost:1313 查看效果。

## 构建静态网站

准备发布时，生成静态文件：

```bash
hugo
```

静态文件会生成到 `public/` 目录，可以将该目录部署到任何静态网站托管服务。

## 常用命令汇总

| 命令 | 说明 |
|------|------|
| `hugo new content <path>` | 创建新内容 |
| `hugo server` | 启动开发服务器 |
| `hugo server --buildDrafts` | 启动服务器并包含草稿 |
| `hugo` | 构建生产版本的静态网站 |
| `hugo -D` | 构建时包含草稿 |

## 小贴士

1. 文章放在 `content/posts/` 目录下会自动归档到博客文章
2. 使用 Markdown 语法编写内容
3. 保存文件后浏览器会自动刷新显示更改
4. Front Matter 使用 TOML 格式（用 `+++` 包围）

祝写作愉快！
