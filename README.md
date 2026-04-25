# PCCOE B.Tech Project Report LaTeX Template

This project is a complete LaTeX setup for Pimpri Chinchwad College of Engineering (PCCOE) B.Tech IT project reports, based on official formatting guidelines and specifications.

## 1) Required Directory Layout

- main.tex
- sections/
- assets/

Already included in this workspace.

## 2) Build Requirements

Install a LaTeX distribution:

- Windows: TeX Live or MiKTeX

Recommended tools:

- latexmk
- pdflatex

## 3) Build Commands

From this folder, run:

```powershell
latexmk -pdf -interaction=nonstopmode -synctex=1 main.tex
```

If latexmk is unavailable:

```powershell
pdflatex main.tex
pdflatex main.tex
```

## 4) What To Edit First

Update metadata in main.tex:

- Project title
- Student names and PRN numbers
- Guide name
- College name and address
- Academic year

## 5) Logo

Place your institute logo at:

- assets/college-logo.png

If missing, LaTeX prints a boxed placeholder.

## 6) Notes

- Page numbering starts from the Contents page as page 1.
- Pages before Contents are intentionally unnumbered.
- Template is set to A4, 1.5 line spacing, Times-style text, and two-sided report layout.
