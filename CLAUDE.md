# Alli Marney-Bell — personal research website

Handoff from a claude.ai conversation (Sep 26, 2026). Read this first.

## What this is
A simple personal academic website Alli will grow through grad school and her career. Alli is a Research Assistant at the Federal Reserve Bank of Chicago (applied microeconomics).

## Files
- `index.html`: the whole site. Plain HTML/CSS/JS, no build step. Two "pages" (About, Research) switched by URL hash (`#about`, `#research`); default is About.
- `files/Marney-Bell_2024_Baltimore_Crime_Thesis.pdf`: undergrad thesis.
- `files/Marney-Bell_2024_APPAM_Poster.pdf`: poster for the same paper.
- `warm-academia-design-system.md`: the design system (tokens, components, voice). **Follow it for every design change.** Key rules: cream paper backgrounds, brown ink text, terracotta accent #A34A2A; Instrument Serif headings (never bold), Newsreader body 18/1.62, IBM Plex Mono uppercase labels; structure via hairline rules, not boxes; unicode glyphs instead of icons; no emoji; sentence case; first-person voice.

## Current content (all confirmed by Alli)
- About page: name "Alli Marney-Bell", title "Research Assistant, Federal Reserve Bank of Chicago", a two-sentence draft bio (Alli may edit), 4:5 photo placeholder. To add the photo: save `photo.jpg` next to `index.html` and swap in the `<img>` tag per the HTML comment.
- Research page:
  - Thesis: "How Crime Relates to Investment and Disinvestment in Residential Properties: A Baltimore City Case Study." Title is a download link; abstract below it (verbatim from the thesis). Meta line: "B.A. thesis, Public Policy Studies, The University of Chicago, April 2024. Awarded with Honors."
  - Poster: same title, presented at the 2024 Association for Public Policy Analysis & Management (APPAM) Fall Research Conference. Download link.
  - Each item has View (inline PDF viewer, lazy-loaded), Download PDF, and Open in new tab.
  - Disclaimer at the bottom: "The views expressed on this website are my own and do not necessarily reflect the views of the Federal Reserve Bank of Chicago or the Federal Reserve System."
- Walnut footer on every page.

## Next step (where we left off)
Push this folder to https://github.com/amarneyb44/personalsite.git (public repo, existing `main` branch with at least one commit, so pull/merge before pushing). Then enable GitHub Pages: Settings → Pages → Deploy from a branch → `main`, `/ (root)`. Expected URL: https://amarneyb44.github.io/personalsite/. After it's live, check that both pages load and the PDF links work (paths are relative: `files/...`).
