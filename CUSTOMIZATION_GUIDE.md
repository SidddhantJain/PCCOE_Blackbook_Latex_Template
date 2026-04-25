# PCCOE LaTeX Template - Customization Guide

## Pre-Filled Information

The following information is already configured in the template:

### College Details (✅ Already Filled)
- **College Name:** Pimpri Chinchwad College of Engineering
- **College Address:** Pimpri, Pune 411018, Maharashtra, India
- **University Affiliation:** Savitribai Phule Pune University
- **Department:** Information Technology

### Template Configuration (✅ Already Set)
- **Page Layout:** A4 (210mm × 297mm)
- **Margins:** 1" top/bottom, 1.25" left/right (as per guidelines)
- **Font:** Times New Roman throughout (12pt main text, 14-16pt headings)
- **Line Spacing:** 1.5 lines (justified alignment)
- **Header/Footer:** With college name, department, and page numbering
- **Page Numbering:** Starts from Contents page as page 1
- **Front Matter Pages:** Unnumbered (as per guidelines)
- **Chapters:** 10 complete chapters + References + Appendices
- **Author & License:** Siddhant Mishrikotkar with usage restrictions

---

## Information To Customize

Edit `main.tex` (lines 19-34) with your project details:

### 1. Project Information
```latex
\newcommand{\ProjectTitle}{PROJECT TITLE}
```
Replace with your actual project title (e.g., "IoT-Based Smart Agriculture System")

### 2. Student Information (All 4 students)
```latex
\newcommand{\StudentOne}{NAME OF STUDENT 1}
\newcommand{\PRNOne}{PRN NO: 1}
\newcommand{\StudentTwo}{NAME OF STUDENT 2}
\newcommand{\PRNTwo}{PRN NO: 2}
\newcommand{\StudentThree}{NAME OF STUDENT 3}
\newcommand{\PRNThree}{PRN NO: 3}
\newcommand{\StudentFour}{NAME OF STUDENT 4}
\newcommand{\PRNFour}{PRN NO: 4}
```
Replace each with the student's full name and PRN.

### 3. Faculty Guides (Both guides)
```latex
\newcommand{\GuideOne}{FACULTY GUIDE 1}
\newcommand{\GuideTwo}{FACULTY GUIDE 2}
```
Replace with your two faculty guides' names.

### 4. Head of Department
```latex
\newcommand{\HODName}{Dr. Jayashree Kati}
```
Already filled with HOD name. Update only if different.

### 5. Academic Year
```latex
\newcommand{\AcademicYear}{2025-26}
```
Already set to 2025-26.

---

## Additional Customizations

### 1. College Logo
Place your PCCOE logo at: `assets/college-logo.png`
- Recommended format: PNG with transparent background
- Size: ~200×200 pixels minimum
- If not found, template displays a placeholder box

### 2. Chapter Content
Edit individual section files in `sections/` folder:
- `07_chapter1_introduction.tex` - Add your introduction content
- `08_chapter2_literature_review.tex` - Add paper reviews
- `09_chapter3_requirements.tex` - Add functional/non-functional requirements
- `10_chapter4_sample.tex` - Chapter 4: Project Plan
- `11_chapter5_methodology.tex` - Chapter 5: Methodology
- `12_chapter6_design.tex` - Chapter 6: Design (UML diagrams)
- `13_chapter7_implementation.tex` - Chapter 7: Implementation details
- `14_chapter8_testing.tex` - Chapter 8: Testing and validation
- `15_chapter9_results_discussions.tex` - Chapter 9: Results and analysis
- `16_chapter10_conclusions.tex` - Chapter 10: Conclusions and future work
- `17_references.tex` - Add your IEEE-formatted references
- `18_appendix.tex` - Add appendices, certificates, plagiarism report

### 3. Student Names in Certificates
Update certificate pages with your names:
- `02_institute_certificate.tex`
- `03_industry_certificate.tex`

### 4. Acknowledgements
Edit `04_acknowledgement.tex` to add your custom acknowledgement text

---

## Important Notes

⚠️ **Do NOT Modify:**
- Document layout, margins, or spacing (as per college specifications)
- Page numbering scheme or header/footer format
- Font sizes or typesetting rules specified in college guidelines
- The author license declaration (as per Siddhant Mishrikotkar's terms)

✅ **Only Modify:**
- Project-specific content (titles, chapters, data)
- Student and guide information
- Figures, tables, and project-specific diagrams
- Academic year and references

---

## Building the Report

### Option 1: If latexmk is installed
```powershell
cd "D:\Siddhant\projects\Black book"
latexmk -pdf -interaction=nonstopmode -synctex=1 main.tex
```

### Option 2: Using pdflatex (if latexmk unavailable)
```powershell
cd "D:\Siddhant\projects\Black book"
pdflatex -interaction=nonstopmode main.tex
pdflatex -interaction=nonstopmode main.tex
```

The PDF will be generated as `main.pdf` in the project root folder.

---

## File Structure

```
d:\Siddhant\projects\Black book\
├── main.tex                              # Main document file
├── README.md                             # This file
├── .gitignore                            # Git ignore rules
├── CUSTOMIZATION_GUIDE.md               # Customization instructions
├── sections/
│   ├── 00_cover_page.tex
│   ├── 01_front_page.tex
│   ├── 01a_license_author.tex           # License and author declaration
│   ├── 02_institute_certificate.tex
│   ├── 03_industry_certificate.tex
│   ├── 04_acknowledgement.tex
│   ├── 05_abbreviations.tex
│   ├── 06_abstract.tex
│   ├── 07_chapter1_introduction.tex
│   ├── 08_chapter2_literature_review.tex
│   ├── 09_chapter3_requirements.tex
│   ├── 10_chapter4_sample.tex           # Project Plan
│   ├── 11_chapter5_methodology.tex
│   ├── 12_chapter6_design.tex
│   ├── 13_chapter7_implementation.tex
│   ├── 14_chapter8_testing.tex
│   ├── 15_chapter9_results_discussions.tex
│   ├── 16_chapter10_conclusions.tex
│   ├── 17_references.tex
│   └── 18_appendix.tex
└── assets/
    ├── README.md                         # Logo instructions
    └── college-logo.png                  # (To be added)
```

---

## Questions?

For template modifications or queries regarding usage rights, contact the template author: Siddhant Mishrikotkar

---

**Last Updated:** April 25, 2026
