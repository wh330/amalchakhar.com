# CLAUDE.md

Guidance for Claude / AI assistants working in this repo.

## No runtime dependencies

Static HTML + LaTeX. Nothing to install at session start. See [`../CLAUDE.md`](../CLAUDE.md) for workspace conventions.

---

## What this repo is

Two artefacts for **Dr Amal Chakhar**:

1. **Website** — `index.html` (single-file static site), deployed via GitHub Pages to `amalchakhar.com` (CNAME).
2. **CV** — LaTeX source under `cv/`, with two self-contained variants (`cv/academic/`, `cv/industry/`). Each holds its own copy of `publications.bib` next to `main.tex` so any one folder zips and uploads to Overleaf without path tweaks.

## Hard rules

- **Publications must stay in sync across THREE files.** Whenever you add, remove, or correct a publication, update all of: `cv/academic/publications.bib`, `cv/industry/publications.bib`, and the `<ul class="pub-list">` block in `index.html`. The two bibs must be byte-identical — easiest way is `cp cv/academic/publications.bib cv/industry/publications.bib` after editing one.
- **The CV templates are ATS-safe.** Don't introduce TikZ graphics, photos, two-column layouts, or text inside text-boxes in `cv/academic/main.tex` or `cv/industry/main.tex`. The full ATS rules are in `cv/GUIDE.md` §4.
- **Don't edit the canonical CV templates for a specific application.** Duplicate into `cv/applications/<company-role>/` and edit the copy. Same convention as `/Users/whajji/wh330/resume/`.
- **British English** throughout — written content, comments, file contents (per the user's global CLAUDE.md).
- **PDFs are not in `.gitignore`.** Compiled `main.pdf` files are kept in git so the latest CV is always available without rebuilding.

## Where to look

| Question                                       | File                       |
| ---------------------------------------------- | -------------------------- |
| How do I build the CV?                         | `cv/README.md`             |
| How does the Overleaf workflow work?           | `cv/README.md`             |
| What makes a resume bullet good?               | `cv/GUIDE.md`              |
| What are the ATS / formatting rules?           | `cv/GUIDE.md` §4           |
| Where do publications live?                    | `cv/academic/publications.bib` + `cv/industry/publications.bib` + `index.html` |

## Things to be careful with

- Don't change the LaTeX preamble in either `main.tex` without a reason — they're tuned for Charter font, biblatex/biber, and ATS-safe Unicode mapping. Match the partner repo's preamble at `/Users/whajji/wh330/resume/anthropic-infra-engineer/main.tex`.
- Don't add LaTeX packages that aren't on stock Overleaf (TeX Live latest); the templates must compile there with no extra setup.
- `index.html` has hand-written CSS and a small easter egg in JavaScript at the bottom. Don't strip the easter egg unless asked.
