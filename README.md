# Jia Liu — personal website

A Quarto website, based on [matdehaven/quarto-academic-website](https://github.com/matdehaven/quarto-academic-website).

## Build

```sh
quarto preview      # live preview while editing
quarto render       # build the site into docs/
```

## Add a new paper

Copy one of the files in `research/` and edit its front matter:

- `wp-*.qmd` files show under **Working Papers**; `wip-*.qmd` files show under **Work in Progress**.
- `order:` sets the position within its section (1 = top).
- Put the PDF in `files/` and link it from the page, e.g. `[Paper (PDF)](../files/my_paper.pdf)`.

## Other edits

- Home page text: `index.qmd` (save a photo as `profile.jpg` and uncomment `image:` to show it).
- CV: replace `files/cv.pdf`.
- Navbar and site settings: `_quarto.yml`.

## Publish on GitHub Pages

Push this folder to a GitHub repo, then in **Settings → Pages** choose
"Deploy from a branch", branch `main`, folder `/docs`.
