# hannah-braswell

Source for [hannah-braswell.com](https://hannah-braswell.com/) — a [Hugo](https://gohugo.io/)
site using the [hugo-goa](https://github.com/shenoydotme/hugo-goa) theme.

## Local development

The theme is a git submodule, so clone with it:

```sh
git clone --recurse-submodules https://github.com/hbraswelrh/hannah-braswell.git
cd hannah-braswell/site
hugo server -D
```

If you already cloned without `--recurse-submodules`:

```sh
git submodule update --init --recursive
```

Content lives in `site/content/` — `about`, `posts`, `projects`, `talks`.
Add a post with `hugo new content posts/my-post.md` from inside `site/`.

## Deployment

Deployed by [Cloudflare Pages](https://pages.cloudflare.com/) on push to `main`.
Build settings:

| Setting                 | Value               |
| ----------------------- | ------------------- |
| Root directory          | `site`              |
| Build command           | `hugo --gc --minify` |
| Build output directory  | `public`            |
| `HUGO_VERSION` env var  | `0.167.0`           |

`HUGO_VERSION` is required — Cloudflare's default Hugo is older than the theme
supports. Bump it here and in the dashboard together when upgrading Hugo.

Generated output (`site/public/`) is gitignored and built by Cloudflare, not committed.
