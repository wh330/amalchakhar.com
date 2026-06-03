# CV

LaTeX source for Amal Chakhar's CV, in two flavours:

| Folder        | Audience                          | Length       |
| ------------- | --------------------------------- | ------------ |
| `academic/`   | postdoc, fellowship, faculty      | multi-page   |
| `industry/`   | data / EO / ML roles in industry  | one A4 page  |

**Each folder is fully self-contained** — `main.tex` and its `publications.bib` live side by side, no shared files, no relative paths. Drag the folder into Overleaf and it just works.

For *content* advice — what to put in, what to cut, how to phrase it — see [`GUIDE.md`](GUIDE.md).

---

## Use on Overleaf (recommended)

1. **Zip the variant folder you want.** From the repo root:
   ```bash
   cd /home/neo/wh330/amalchakhar/cv
   zip -r industry.zip industry/    # or: zip -r academic.zip academic/
   ```
2. **Open Overleaf → New Project → Upload Project** and drop in the zip.
3. The project opens with `main.tex` already as the main document. Click **Recompile**.
4. If the bibliography doesn't appear on the first compile, click **Recompile** once more — biber needs an extra pass on first run. After that Overleaf caches it.
5. (Optional) Open the **Menu** (top-left of the editor) and confirm:
   - **Compiler:** pdfLaTeX
   - **TeX Live version:** latest

That's it. Both `main.tex` and `publications.bib` are in the project root, so biblatex finds the bib without any path setup.

### If you want both variants in one Overleaf project

Upload the whole `cv/` folder instead. In Overleaf, set **Menu → Main document** to whichever `main.tex` you're editing. Each variant still finds its own `publications.bib` because they're co-located.

---

## Build locally (optional)

You need a TeX distribution with `pdflatex` and `biber`. On macOS the easiest path is **[MacTeX](https://www.tug.org/mactex/)** (~5 GB) or **BasicTeX** (~100 MB) plus `sudo tlmgr install biber latexmk biblatex charter fontawesome5`.

```bash
cd cv/academic            # or cv/industry
latexmk -pdf main.tex     # produces main.pdf in this folder
latexmk -c                # cleans up intermediate files
```

If you don't have `latexmk`:

```bash
pdflatex main.tex
biber main
pdflatex main.tex
pdflatex main.tex
```

---

## Adding a new publication

When a new paper is accepted, update **three** places so they stay in sync:

1. `cv/academic/publications.bib` — add the BibTeX entry.
2. `cv/industry/publications.bib` — same entry.
3. `index.html` — add it to the `<ul class="pub-list">` block.

A quick way to keep the two bibs identical after editing one:

```bash
# from repo root, after editing academic/publications.bib:
cp cv/academic/publications.bib cv/industry/publications.bib
```

(Or vice versa.)

If you want the industry resume to actually *show* the new paper in its "Selected Publications" section, also add its citation key to the `\nocite{...}` line in `cv/industry/main.tex`.

---

## Adapting for a specific application

Don't edit the canonical templates. Duplicate first:

```bash
cd /home/neo/wh330/amalchakhar/cv
cp -r industry applications/<company>-<role>      # e.g. applications/esa-eo-scientist
```

Then tailor `applications/<company>-<role>/main.tex` to match the job description. The `applications/` folder is where one-off variants live; `academic/` and `industry/` stay clean.

If you need a cover letter, add `cl.tex` next to `main.tex` in the application folder. The `cl.tex` template at `/home/neo/wh330/career-hub/anthropic-infra-engineer/cl.tex` is a working reference.
