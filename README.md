# pengdongbo's Hugo Personal Website

A standalone Hugo website using Hugo 0.166.0. No theme installation, Node.js, or additional dependencies required.

## Edit content

- `content/_index.md`: homepage title and biography in Markdown.
- `hugo.toml`: site title, description, and GitHub link.
- `static/css/main.css`: colors, fonts, and layout.
- `layouts/index.html`: page structure.

## Local preview

Install Hugo: https://gohugo.io/installation/

Run from this project directory:

```sh
hugo server -D
```

Open the local URL printed in the terminal. Production build: `hugo --gc --minify`.

## Deploy to GitHub Pages

1. Sign in to GitHub as `pengdongbo`.
2. Create the public repository `pengdongbo.github.io`. If it already exists, inspect its contents before making changes.
3. Push this directory's source files to the repository root, including `.github/workflows/hugo.yaml`. Do not upload the generated `public` directory.
4. Under Settings → Pages → Build and deployment, set Source to GitHub Actions.
5. Run Deploy Hugo to GitHub Pages in Actions, or push a change to main.
6. Once deployment succeeds, visit https://pengdongbo.github.io/ .

For initial Git setup only, after confirming the remote repository is empty:

```sh
git init -b main
git add .
git commit -m "Create Hugo homepage"
git remote add origin https://github.com/pengdongbo/pengdongbo.github.io.git
git push -u origin main
```

Subsequent pushes to main automatically update the website. The workflow does not require a personal access token.

Official deployment guide: https://gohugo.io/host-and-deploy/host-on-github-pages/

## Academic-style template

This template recreates the Academic 3.2.0 layout at https://dishi.netlify.app/ for Hugo 0.166.0; it does not install the original legacy theme. Personal information, photographs, and publications from the reference site are not copied.

- `content/_index.md`: biography, role, organization, avatar path, interests array, and education array.
- Place the profile photo at `static/images/avatar.jpg` and set avatar to `images/avatar.jpg`.
- Each education entry uses degree, institution, and an optional year. Initials appear when no avatar is configured.
- `content/experience.md`, `news.md`, `publications.md`, and `awards.md`: Markdown sections for experience, news, publications, and awards. Adjust weight to reorder; delete a file to remove its section and navigation link.
- Unfilled sections say “To be updated.” Replace them with your information or remove unused sections.
