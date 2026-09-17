# fzhnf-blog

Zola blog ([Ametrine](https://github.com/welpo/tabi) theme), deployed to GitHub Pages on push to `master`. Zola version is pinned via [mise](https://mise.jdx.dev).

## Writing a post

```sh
mise post "My Post Title"    # scaffolds content/blog/<today>-my-post-title/index.md (draft)
mise serve                   # live preview at http://127.0.0.1:1111
mise banner out.png          # convert exported banner → banner.webp in the latest post
mise publish my-post-title   # flip draft = false
mise check                   # verify internal links before pushing
```

## Tasks

| Task | Effect |
|---|---|
| `mise post "<title>"` | Create draft post dir + `index.md` with front matter |
| `mise publish <slug>` | Set `draft = false` (slug matches partial dir name) |
| `mise check` | `zola check` — broken internal links / highlighting errors |
| `mise banner <img> [slug]` | Resize image to max 1280w → `banner.webp` in post dir (needs ImageMagick or ffmpeg) |

Scaffold front matter (authors name, categories, banner filename) lives in the `[tasks.post]` block of `mise.toml` — edit there if defaults change.
