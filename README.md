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

## Example of how to edit the home page: 
The home page is the file index.qmd in your gitwebsite folder. Editing it takes three steps: change the file, preview it, then publish.

1. Open the file

Use any plain-text editor, such as VS Code, RStudio or TextEdit in plain-text mode. Don't use Word.

2. How the file is laid out

The file has two parts.

Settings (the top, between the two --- lines). These control the heading, the photo and the icon links:

---
title: "Name Example"                                   # big name at the top
subtitle: "Consultant, The World Bank" # line under your name
description: "..."                                 # summary Google shows in search results
about:
  template: jolla                                  # layout style
  # image: profile.jpg                             # photo (see below)
  links:                                           # icon buttons under your name
    - icon: envelope
      text: Email
      href: mailto:example@gmail.com
---

In this part:
- Keep the quotes and the indentation exactly as they are. YAML breaks if the spacing is off.
- A # turns a line into a comment, so it's ignored.

Body (everything after the second ---). This is the page text, written in Markdown:

┌───────────────────────┬───────────────────┐
│       You type        │      You get      │
├───────────────────────┼───────────────────┤
│ **World Bank**        │ World Bank (bold) │
├───────────────────────┼───────────────────┤
│ *text*                │ italic            │
├───────────────────────┼───────────────────┤
│ [my CV](files/cv.pdf) │ a link            │
├───────────────────────┼───────────────────┤
│ ## News               │ a section heading │
├───────────────────────┼───────────────────┤
│ - item                │ a bullet point    │
├───────────────────────┼───────────────────┤
│ a blank line          │ a new paragraph   │
└───────────────────────┴───────────────────┘

3. Common edits

Change the bio. Just rewrite the paragraphs.

Add a photo:
1. Put the photo in the gitwebsite folder and name it profile.jpg.
2. Change   # image: profile.jpg to   image: profile.jpg. That means deleting #  but keeping the two leading spaces.

Add an icon link, for example LinkedIn or Google Scholar. Add a block under links: with the same indentation as the others:
    - icon: linkedin
      text: LinkedIn
      href: https://www.linkedin.com/in/your-profile
Other icon names you can use include mortarboard (good for Google Scholar), twitter-x and file-earmark-text. The full list is at https://icons.getbootstrap.com.

Add a news section at the bottom of the body:
## News

- Oct 2026: New website launched!

4. Preview while you edit

In Terminal:
cd ~
quarto preview
A browser window opens and refreshes every time you save. Press Ctrl+C in Terminal to stop it.

5. Publish

quarto render
git add -A
git commit -m "Update home page"
git push
The live site updates within a minute or two.

If git push hangs and then fails with "port 22: Operation timed out", the network you're on is blocking GitHub's normal SSH connection. Run this once and plain git push will always work after that:
printf '\nHost github.com\n  Hostname ssh.github.com\n  Port 443\n  User git\n' >> ~/.ssh/config

You can also just tell me what to change, and I'll edit, preview and publish it for you.
