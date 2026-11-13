`npx blowfish-tools`
`blowfish-tools`

## Prototyping page

Add project posts under `content/prototyping/`. Set `draft: true` to keep a post
out of normal builds; preview drafts with `hugo server -D`.
The project list shows each post's title, description, and optional `projectURL`.

You can also add projects to the `prototypes` list in `content/prototyping/_index.md`, newest first.
Each entry has a title, URL, short description, and a list of links (for example,
GitHub, Demo, or Website). An optional `date` uses `YYYY-MM-DD`.

Blog comments continue to use Disqus.

## Blogging

Blog posts live in `content/blogging/` and are published under `/blogging/`.
Writing remains a separate section at `/writing/`.
The previous `/blog/` URLs redirect to their new locations. Migrated posts retain
their original `disqus_url` to keep existing comment threads attached.

pandoc to convert latex to markdown

`pandoc --from latex+latex_macros --to markdown -s post.tex -o post.md`

tex_math_dollars


I implemented a global mathjax (https://gohugo.io/content-management/mathematics/)
and effectively ignored the available shortcode for katex
