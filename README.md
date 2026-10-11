`npx blowfish-tools`
`blowfish-tools`

## Prototyping page

Add projects to the `prototypes` list in `content/prototyping.md`, newest first.
Each entry has a title, URL, short description, and a list of links (for example,
GitHub, Demo, or Website). An optional `date` uses `YYYY-MM-DD`.

Blog comments continue to use Disqus.

## Writing

Posts live in `content/writing/` and are published under `/writing/`.
The previous `/blog/` URLs redirect to their new locations. Migrated posts retain
their original `disqus_url` to keep existing comment threads attached.

pandoc to convert latex to markdown

`pandoc --from latex+latex_macros --to markdown -s post.tex -o post.md`

tex_math_dollars


I implemented a global mathjax (https://gohugo.io/content-management/mathematics/)
and effectively ignored the available shortcode for katex
