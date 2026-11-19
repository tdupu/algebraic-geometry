# LAYOUT.md — repository layout contract

| Field | Value |
| --- | --- |
| Repo | `algebraic-geometry` |
| Status | Adopted |
| Date | `2026-11-19` |
| Approved by | Taylor Dupuy |
| Checked by | `check-layout` |
| Amended by | `new-repo-layout-policy` |

One document per repository, at the root. It says what goes where, what is
canonical, what is kept on disk but ignored, and what must never appear. The
tree is the target state; current deviations are listed in the Brownfield
register with a disposition, and are not part of the contract.

## Tree

```
algebraic-geometry/
├── curves-and-surfaces.tex  ← the manuscript: lecture notes on algebraic
│                               curves and surfaces (the only root .tex)
├── figures/                 ← one TikZ source per figure, named <slug>.tex,
│                               \input by the manuscript as fig:<slug>; also
│                               raster images the manuscript includes
├── ai/                      ← durable agent records, in dated dirs
│                               ai/YYYY-MM-DD-<slug>/; non-canonical
├── scratch/                 ← transient output (LY3); non-canonical, disposable
├── POLICY.md  LAYOUT.md     ← repository conventions and this layout contract
├── .gitignore               ← carries the LY9 stanza
└── ── gitignored but KEEP on disk ──
    curves-and-surfaces.pdf  ← build output of the manuscript (LY9)
    *.aux *.log *.out *.toc  ← LaTeX byproducts (LY9)
```

`.gitignore` stanza (LY9), type-shaped so relocation cannot evade it:

```gitignore
# LY9 — never tracked, wherever they sit
*.pdf
*.aux
*.log
*.out
*.toc
*.bbl
*.blg
*.fls
*.fdb_latexmk
*.synctex.gz
*.nav
*.snm
*.vrb
```

## Brownfield register (pending cleanup — NOT part of the contract)

| Current state | Target disposition |
| --- | --- |
| `LATEX.md`, `STYLE.md`, `ADR.md`, `AGENTS.md`, `AI-POLICY.md` absent (LY5) | TBD (human) |

A row is removed only after its cleanup has actually happened. Disposition
vocabulary: move to <declared dir> | merge into <path> | demote to scratch/ |
keep-untracked | delete (human-approved) | TBD (human).

## Rules

**Non-canonical trees.** `scratch/` (transient) and `ai/` (durable agent
records) are not part of the published notes. Every audit that excludes
non-canonical content excludes both.

**LY1 — Clean-tree test [C].** A collaborator opening the repo finds only
the manuscript, its figures, and the repo docs, plus the non-canonical trees.
Pass: every tracked path matches a tree row. Fail: any tracked path with no
row.

**LY2 — Tree + register are total [C].** Every top-level directory and
tracked root file has a tree row or a register row. Pass/Fail: mechanical
diff of `git ls-files` plus the root listing against tree ∪ register.

**LY3 — Transient output goes to scratch/ [C].** Anything a tool or agent
writes that is not the artifact goes under `scratch/YYYY-MM-DD-<slug>/`.
Pass: no transient files outside `scratch/` and `ai/`. Fail: stray notes,
previews or renders at the root or in `figures/`.

**LY4 — Tex placement [C].** `curves-and-surfaces.tex` is the only `.tex` at
the root; every other tracked `.tex` is a figure source in `figures/`.
Pass/Fail: `git ls-files '*.tex'` matches those two patterns.

**LY5 — Repo docs present [C].** `AI-POLICY.md`, `LAYOUT.md`, `LATEX.md`,
`STYLE.md`, `ADR.md`, `AGENTS.md` exist at the root, and `AGENTS.md` points
at the others. Pass/Fail: existence and pointer check. Currently registered
as pending.

**LY6 — Bloat guard [C].** Each repo doc stays within 120 non-blank lines
(`AI-POLICY.md`: 260). Over = finding.

**LY7 — Naming [C].** New file and folder names are lowercase,
hyphen-separated, with no spaces. Figure sources are `figures/<slug>.tex`,
where `<slug>` is also the label `fig:<slug>`.

**LY8 — Few folders [C].** A new top-level directory requires a LAYOUT
amendment first. Anything with no declared home goes to `scratch/`.

**LY9 — PDFs and build byproducts are never tracked [C].** No `.pdf` is
tracked anywhere, and neither are `.aux` `.log` `.out` `.toc` `.bbl` `.blg`
`.fls` `.fdb_latexmk` `.synctex.gz` `.nav` `.snm` `.vrb`. Pass:
`git ls-files '*.pdf'` (and each byproduct pattern) returns nothing. Fail:
any match. Remediation: `git rm --cached <path>` plus the `.gitignore` entry;
the file stays on disk. Image files used as figures are tracked normally.

## Change Log

| Date | Change | Approved by |
| --- | --- | --- |
| `2026-11-19` | Instantiated from mathcity-repo-docs template | Taylor Dupuy |
| `2026-11-19` | Cleared register rows: untracked the PDF, added `.gitignore`, moved `grr.jpeg`, `schubert.png` to `figures/` and the figure plan to `ai/2026-11-19-figures/` | Taylor Dupuy |
