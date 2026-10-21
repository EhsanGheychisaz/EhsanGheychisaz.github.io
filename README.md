# Quiet Notes

A minimal English-language personal blog built with Jekyll and GitHub Pages.

## Publish on GitHub Pages

1. Create a new repository on GitHub. A repository named `YOUR-USERNAME.github.io` gives you the root site URL.
2. Upload the contents of this folder to the repository's root (not the ZIP file itself).
3. Open **Settings → Pages**.
4. Under **Build and deployment**, choose **Deploy from a branch**, select `main` and `/ (root)`, then save.
5. Wait a minute or two for GitHub Pages to publish the site.

For a project repository with a URL like `https://YOUR-USERNAME.github.io/quiet-notes/`, set `baseurl: "/quiet-notes"` in `_config.yml`. For a user repository named `YOUR-USERNAME.github.io`, leave `baseurl` empty.

## Add a new post

Create a Markdown file in `_posts/` with a filename that starts with the date, e.g. `_posts/2026-10-25-what-i-am-thinking.md`:

```markdown
---
layout: post
title: "What I Am Thinking"
date: 2026-10-25
categories: Reflections
description: "A short summary shown on the home page."
---

Write your post here. Use Markdown for paragraphs, **bold**, links, and headings.
```

On GitHub: open the `_posts` folder → **Add file** → **Create new file**. Enter the filename and content, then commit the changes. GitHub Pages will rebuild the site automatically.

## Customize

- Change the site name and description in `_config.yml`.
- Edit the introduction in `index.html`.
- Edit the About page in `about.md`.
- Change colors, spacing, and typography in `assets/css/style.css`.

## Note

This site is static: posts are published by committing Markdown files to GitHub. It does not have a visitor comment form or private admin panel.
