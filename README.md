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
- Student names and PRN numbers (all 4 students)
- Faculty guide names (both guides)
- HOD name (Optional - defaults to Dr. Jayashree Kati)
- Academic year (preset to 2025-26)
- College name, address (already set to PCCOE)

## 5) Logo

Place your institute logo at:

- assets/college-logo.png

If missing, LaTeX prints a boxed placeholder.

## 6) License

This LaTeX template and repository structure are provided under the **MIT License**.

The license covers the template framework, structure, and LaTeX code only. All project-specific content, academic work, research data, and figures added by users remain the intellectual property of the respective project authors and their institutions.

See LICENSE file for full details.

## 7) Template Notes

- Page numbering starts from the Contents page as page 1.
- Pages before Contents are intentionally unnumbered.
- Template is set to A4, 1.5 line spacing, Times-style text, and two-sided report layout.
