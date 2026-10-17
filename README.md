# Class Notes — Modern Indian History (GS Paper 1)

A modular, publication-quality LaTeX book template for **UPSC Civil Services Examination — General Studies Paper 1 (Modern Indian History)**.

Compiled locally with `pdflatex`. Every lecture or topic becomes a self-contained chapter file in `chapters/`; you never need to rewrite the overall book skeleton.

## Folder Structure

```text
main.tex               — The master book: title page, table of contents, and \include chapter list
preamble.tex           — Styling (Navy & Gold palette, note boxes, typography, tables, headers/footers)
chapters/
  01-advent-of-europeans-and-british-expansion.tex — Chapter 1: Advent of Europeans & British Conquest of Bengal
chapter-prompt.md      — Prompt for transforming transcripts or notes into structured LaTeX chapters
README.md              — Documentation and instructions
```

## Compilation

You need a TeX distribution: [TeX Live](https://tug.org/texlive/) (Windows/Linux) or [MacTeX](https://tug.org/mactex/) (Mac) or [MiKTeX](https://miktex.org/).

Run `pdflatex` twice (the second pass builds the table of contents and page references):

```bash
pdflatex main.tex
pdflatex main.tex
```

The output book will be generated as `main.pdf`.

## Adding a New Chapter

1. Open a chat with the **chapter prompt** (`chapter-prompt.md`) and paste your lecture transcript or study notes.
2. The prompt outputs **one LaTeX fragment** starting with `\chapter{...}` and ending with the chapter glossary.
3. Save it as `chapters/NN-short-slug.tex` (e.g., `chapters/02-expansion-and-consolidation.tex`).
4. In `main.tex`, add or uncomment the corresponding line:
   ```latex
   \include{chapters/02-expansion-and-consolidation}
   ```
5. Recompile with `pdflatex main.tex` (twice).

## Customisation

- **Running headers & styling**: Defined centrally in `preamble.tex`.
- **Book metadata**: Defined at the top of `main.tex` (`\BookExamLine`, `\BookTitle`, `\BookSubtitle`, `\BookDate`).
- **Drafting speed**: Uncomment `\includeonly{chapters/NN-topic}` in `main.tex` to compile only the active chapter while writing.
