# Setting up the GitHub Profile README

This folder contains the README that renders at the top of your GitHub
profile (https://github.com/juubaker).

## How GitHub profile READMEs work

GitHub looks for a public repository whose name **exactly matches your
username** and renders its `README.md` on your profile page.

For you, that's a repo named **`juubaker`**, owned by **`juubaker`**.

## One-time setup

1. **Create the repo.** On GitHub, create a new public repo named exactly
   `juubaker`. When you do, GitHub will show a green box noting "you
   found a secret" — that's the signal you got the special profile repo.
   Tick "Add a README" if you want, or just push these files.

2. **Push these files.** From this folder:

   ```bash
   git init
   git add .
   git commit -m "Profile README"
   git branch -M main
   git remote add origin https://github.com/juubaker/juubaker.git
   git push -u origin main
   ```

3. **Verify.** Visit https://github.com/juubaker — the README should
   render with the SVG hero at the top.

## Updating the hero image

The hero is `assets/hero.svg`. You can edit the text directly in the SVG
(open in any text editor) — name, tagline, location, and accent strip are
all inline `<text>` and `<line>` elements with comments calling out what
each one does.

If you want a dark-mode-aware version later, GitHub supports the
`<picture>` element in markdown:

```html
<picture>
  <source media="(prefers-color-scheme: dark)" srcset="./assets/hero-dark.svg" />
  <img src="./assets/hero.svg" alt="..." />
</picture>
```

## Keeping it in sync with the portfolio

The README links to `juubaker.github.io` as the source of truth for case
studies. When you ship a new project, add it to the portfolio's
`src/content/projects/` directory first, then (optionally) swap a card
in the README's "Selected work" table.
