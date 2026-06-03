# Dr Amal Chakhar — site & CV

This repo holds two things:

- **The personal website** — `index.html`, deployed via GitHub Pages to **[amalchakhar.com](https://amalchakhar.com)** (the custom domain is set in `CNAME`).
- **The CV** — LaTeX source under [`cv/`](cv/), with both an academic and an industry variant. See [`cv/README.md`](cv/README.md) for build instructions and Overleaf workflow, and [`cv/GUIDE.md`](cv/GUIDE.md) for content/strategy advice.

## Repo layout

```
.
├── index.html              the website
├── CNAME                   custom-domain config for GitHub Pages
├── robots.txt
├── sitemap.xml
└── cv/
    ├── README.md           build & Overleaf instructions
    ├── GUIDE.md            how to make the CV shine
    ├── academic/
    │   ├── main.tex           multi-page academic CV
    │   └── publications.bib   bibliography (self-contained for Overleaf)
    └── industry/
        ├── main.tex           one-page industry resume
        └── publications.bib   identical copy of academic/publications.bib
```

Each variant is self-contained — drag the folder into Overleaf and it builds.

## Keeping it in sync

When a new paper is accepted, update **three** places:

1. `cv/academic/publications.bib`.
2. `cv/industry/publications.bib` (keep it identical — `cp cv/academic/publications.bib cv/industry/publications.bib`).
3. The `<ul class="pub-list">` block in `index.html`.

The website and the bibs are all your public record — they should never disagree.
