# pengdongbo 的 Hugo 个人主页

纯 Hugo 网站，无需安装主题、Node.js 或其他依赖。使用 Hugo 0.166.0。

## 修改内容

- `content/_index.md`：主页标题和介绍，使用 Markdown。
- `hugo.toml`：网站名称、描述和 GitHub 链接。
- `static/css/main.css`：配色、字体和布局。
- `layouts/index.html`：页面结构。

## 本地预览

安装 Hugo：https://gohugo.io/installation/

在本项目目录运行：

```sh
hugo server -D
```

打开终端显示的本地地址。生产构建命令：`hugo --gc --minify`。

## 发布到 GitHub Pages

1. 使用 `pengdongbo` 账号登录 GitHub。
2. 创建公开仓库 `pengdongbo.github.io`。如果已经存在，先检查原内容，不要覆盖。
3. 将本目录的源码上传到仓库根目录，必须包含 `.github/workflows/hugo.yaml`，不要上传生成的 `public` 目录。
4. 在仓库 Settings → Pages → Build and deployment 中，将 Source 设为 GitHub Actions。
5. 在 Actions 中运行 Deploy Hugo to GitHub Pages，或推送一次修改到 main。
6. 等待部署成功，访问 https://pengdongbo.github.io/ 。

如果使用 Git，在确认远端是空仓库后，可以在本目录运行：

```sh
git init -b main
git add .
git commit -m "Create Hugo homepage"
git remote add origin https://github.com/pengdongbo/pengdongbo.github.io.git
git push -u origin main
```

后续提交到 main 会自动更新网站，无需设置个人访问令牌。

官方部署文档：https://gohugo.io/host-and-deploy/host-on-github-pages/

## Academic 风格模板

当前版本参考 https://dishi.netlify.app/ 的 Academic 3.2.0 布局，自行实现兼容 Hugo 0.166.0 的模板，并非安装原版旧主题。未复制参考站的个人资料、照片或论文。

- `content/_index.md`：简介，以及 role（职位）、organization（单位）、avatar（照片路径）、interests（研究兴趣数组）、education（教育经历数组）。
- 照片放入 `static/images/avatar.jpg`，将 avatar 设置为 `images/avatar.jpg`。
- 教育经历每项包含 degree、institution 和 year。未填写头像时使用字母标识。
- `content/experience.md`、`news.md`、`publications.md`、`awards.md`：经历、动态、论文、荣誉，均使用 Markdown。调整 weight 可排序；删除对应文件即可移除栏目及导航。
- 栏目当前为明确的“待补充”，请在公开发布前替换为你的资料或删除不用的栏目。
