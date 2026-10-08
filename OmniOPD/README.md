# Project Page Scaffold (OmniNFT / Nerfies style)

A ready-to-fill project page modeled on `https://zghhui.github.io/OmniNFT/`.

## Files

```
/pfs/kaifan/project_page/
├── index.html          # the page — replace every ALL_CAPS placeholder
├── styles.css          # theme (accent #4169E1). Copy of OmniNFT's, no edits needed
├── README.md           # this file
└── static/
    ├── images/         # framework.png, teaser.png, case_*.gif ...
    └── video/
        ├── paper/{Baseline,Ours}/case_XXX.mp4
        └── more_case/{Baseline,Ours}/case_XXX.mp4
```

## Filling it in

Search `index.html` for the token `TODO` and for strings in `ALL_CAPS`. Each is a field:

| Placeholder | Meaning |
|---|---|
| `PROJECT_NAME` / `PROJECT_SUBTITLE` | short name + full title (also in `<title>`) |
| `AUTHOR_ONE` … | author names; keep `<sup>N</sup>` matching the affiliations line |
| `AFFILIATION_ONE/TWO` | institutions |
| `#` on **Paper/Code/arXiv** buttons | paste real URLs |
| `ABSTRACT_PARAGRAPH_*` | abstract text |
| `CONTRIB_*` | the three highlight cards in "Core Idea" |
| `STEP_*` | numbered pipeline steps (delete the whole `.method-details` section if unused) |
| baseline rows in `.results-table` | metric numbers; `class="best"` = blue best, `style="text-decoration:underline;"` = second best |
| `PROMPT_TEXT` | per-case prompt |
| `@article{...}` | the BibTeX block |

Notes:
- The table's category sub-header rows use `colspan="6"` — change it to match your total column count.
- Demo videos are `<video>` elements pointing at `static/video/...`; drop in matching filenames or delete rows.
- The `.gif-grid` section is an alternate results layout (6-up GIFs). Delete it if you use videos only.
- Figures referenced but not present: `static/images/teaser.png`, `framework.png`, `case_*.gif`. Add your own or delete those sections.

## Deploy to GitHub Pages

Two options:

**A. Dedicated repo (recommended)** — url becomes `https://fanzh03.github.io/<repo-name>/`
1. Create repo `<repo-name>` (e.g. `Bird-SR-project`), push these files to `main` (root).
2. Repo Settings → Pages → Source: *Deploy from a branch* → `main` / `/ (root)`.
3. Visit `https://fanzh03.github.io/<repo-name>/`.

**B. Under the existing user site** — `fanzh03.github.io` is a Jekyll **Chirpy** blog. Jekyll ignores
directories that contain no Markdown and don't start with `_`, so:
1. Copy this folder to `projects/<name>/` inside the `fanzh03.github.io` repo.
2. Add `projects/<name>/.nojekyll` (empty) to skip Jekyll processing entirely.
3. Push; live at `https://fanzh03.github.io/projects/<name>/`.

Note: the `fanzh03.github.io` landing page is stock Chirpy — it has no project grid. To add a link
from the homepage, add a Markdown page under `_tabs/` (Chirpy nav) or a post.

## Local preview

```bash
cd /pfs/kaifan/project_page && python3 -m http.server 8899
# open http://localhost:8899
```
