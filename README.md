# 我的 Hugo 博客

项目内置 Hugo Extended 0.166.0（Linux x86_64），可直接在当前目录运行。

## 本地预览

```sh
./bin/hugo server --buildDrafts
```

浏览器访问 <http://localhost:1313/>。

## 写新文章

```sh
./bin/hugo new content posts/my-first-post.md
```

编辑 `content/posts/my-first-post.md`，发布前将 `draft: true` 改为 `draft: false`。

## 构建

```sh
./bin/hugo --minify
```

生成的网站位于 `public/`，该目录不需要提交到 Git。

## 发布到 GitHub Pages

1. 在 GitHub 新建仓库，并把本项目推送到仓库的 `main` 分支。
2. 打开仓库的 **Settings → Pages**。
3. 将 **Build and deployment → Source** 设置为 **GitHub Actions**。
4. 再次推送内容，或在 **Actions** 页面手动运行工作流。

`.github/workflows/hugo.yaml` 会自动构建并发布网站。GitHub Actions 会自行下载固定版本的 Hugo，因此没有纳入 Git 的本地 `bin/hugo` 不会影响部署。
