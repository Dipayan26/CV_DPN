# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this repo is

A LaTeX-source CV/resume for Dipayan Sarkar (PhD researcher, computational biology, University of North Bengal), built with the `moderncv` class. The compiled PDF is published via GitHub Pages at `https://dipayansarkar.com/CV_DPN/CV_DPN.pdf`.

## The one file that matters

**`CV_DPN.tex`** is the actual, actively maintained CV. It's the only file compiled by CI and the only one linked from the README.

- `cv_altacv/` and `cv_awesomecv/` are one-off style experiments (AltaCV and Awesome-CV templates) seeded in a single early commit. They are **not kept in sync** with `CV_DPN.tex` and are not built by CI — treat edits to the real CV as `CV_DPN.tex`-only unless the user explicitly asks to update these alternates too.
- `DPN_CV.docx` is a static Word copy, not generated from the `.tex` source.
- `notes.md` contains scratch notes from prior sessions (moderncv style/option cheatsheet, `\cventry` argument reference, and the git skip-worktree rationale below) — useful background, not something to keep updated.
- `ref.bib` exists but is currently unused; the Publications section in `CV_DPN.tex` is hand-written with `\cvitem` + `\href` rather than driven by BibTeX (the `\bibliography{ref}` block is commented out).

## Building

Compile with `pdflatex` (or `latexmk`) from the repo root:

```
pdflatex -interaction=nonstopmode -halt-on-error CV_DPN.tex
```

Run it twice if cross-references/TOC-like elements change (not usually needed for this CV — no ToC or citations are active). Auxiliary files (`.aux`, `.log`, `.out`, `.fls`, `.fdb_latexmk`) are gitignored; clean them up after local test compiles along with any preview PNGs you generate.

To visually check a change, render the first page to an image rather than assuming the LaTeX is correct:

```
pdftoppm -png -r 150 -f 1 -l 1 CV_DPN.pdf page_preview
```

## CI: PDF is auto-committed, don't fight it

`.github/workflows/compile.yml` runs on every push to `main`: it recompiles `CV_DPN.tex` and commits the resulting `CV_DPN.pdf` back to the repo as `chore: auto-compile CV [skip ci]`. This means:

- `CV_DPN.pdf` is tracked in git (despite being listed in `.gitignore` — the gitignore entry only affects untracked clones going forward) and is meant to be written **only by CI**, not by local commits.
- On a fresh clone, run `git update-index --skip-worktree CV_DPN.pdf` once so local recompiles for previewing don't show up as a dirty `git status` or get committed, avoiding merge conflicts with CI's auto-commits on the binary. (This is a local-only git setting, not stored in the repo — it must be re-run per machine/clone.)
- Don't hand-edit or commit `CV_DPN.pdf`; only edit `CV_DPN.tex` and let CI regenerate the PDF after push.

## Document structure and header conventions

`CV_DPN.tex` uses `moderncv` with the `banking` style and `black` color, with several local overrides worth knowing before editing the header:

- First/last name font size and color are hardcoded via `\renewcommand*{\firstnamestyle}`/`\lastnamestyle` (both forced to black, matching size) rather than left to the style defaults.
- Vertical spacing between the name and the contact block is patched via `\patchcmd{\makehead}` (`makeatletter`/`makeatother` block) — if this patch target ever fails silently across a `moderncv` version bump, it emits a `PackageWarning` rather than erroring.
- Standard contact fields (`\phone`, `\email`, `\homepage`, `\social`) only support **one value each** in `moderncv`. Anything beyond that (the Hugging Face link, the second/institutional email `rs_dipayans@nbu.ac.in`) is appended manually inside `\extrainfo`, matching moderncv's internal icon/separator commands (`\emailsymbol`, `\emaillink`, `\makeheaddetailssymbol`) so it renders consistent with the built-in fields rather than as an ad hoc string. Follow this pattern for any further header additions.
- Fontawesome icons are provided by `moderncv` itself (fontawesome6 under the hood) — do not `\usepackage{fontawesome5}` separately, it clashes (see comment at the `\huggingfaceicon` definition).
- Sections follow a fixed order: Research Summary, Work Experience, Education, Publications, (page break) Skills, Software & Tools, Awards & Certificates, Grants & Computing Resources. Publications are newest-first; entries use `\cvitem{year}{...}`, work/education use `\cventry{date}{title}{institution}{location}{grade}{description}`.
- Commented-out `\cventry`/`\cvitem` blocks (e.g. secondary/higher-secondary schooling, the BibTeX-driven publications block) are intentionally kept as toggleable options, not dead code to delete.
