# Repository policy — algebraic-geometry

Conventions for working on the notes in this repository. Where files go is
set by [LAYOUT.md](LAYOUT.md); this document covers how they are written,
built and published.

## Figures

1. **One file per figure.** Every figure is a single `tikzpicture` in
   `figures/<slug>.tex`, containing no `figure` environment and no caption.
2. **Label matches file.** The manuscript includes it as
   `\input{figures/<slug>}` inside `\begin{figure}[H]`, with
   `\label{fig:<slug>}`.
3. **Placement.** The float sits immediately before the passage it
   illustrates and is cited from that passage with `Figure~\ref{fig:<slug>}`.
   Every figure is cited at least once.
4. **Shared style.** Figures use only the styles and colours defined in the
   preamble's figure style block (for example, exceptional divisors are
   `exc`, hyperplanes are `hyp`). A figure does not redefine those colours.
5. **TikZ only.** Figures are drawn in TikZ; pgfplots is not used. Raster
   images are allowed only for material that cannot be redrawn, such as a
   photograph of a notebook.
6. **Honest captions.** A caption says whether the picture shows real points
   of an explicit equation or is schematic, and defines every symbol and
   colour it uses.

## Notes to self

7. **Author notes.** Notes to the author use `\taylor{...}` and are removed
   when the work they ask for is done; a note asking for a drawing is removed
   when its figure is inserted.

## Building

8. **The manuscript builds.** `pdflatex curves-and-surfaces.tex`, run twice,
   finishes with no errors and no undefined references before any commit
   that touches `curves-and-surfaces.tex` or `figures/`.
9. **Build outputs are not tracked.** The PDF and LaTeX byproducts are never
   committed (LAYOUT.md LY9). Build in a scratch directory or rely on
   `.gitignore`.

## Commits and publishing

10. **Branches.** Work happens on a branch; it reaches `master` by
    fast-forward or pull request, and the branch is deleted once merged.
11. **Scoped commits.** A commit stages explicit paths only; it never mixes
    one session's edits with another's uncommitted work.
12. **Agent work is disclosed.** Commits written by an AI agent carry a
    `Co-Authored-By:` trailer naming the agent, and agent planning records go
    in `ai/YYYY-MM-DD-<slug>/`.
