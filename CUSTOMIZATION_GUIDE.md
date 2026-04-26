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
- **License:** MIT License (applies to template repository structure only)

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

## Template Formatting DOS AND DON'Ts

### ✅ DO's - Maintain Template Consistency

#### 1. Content Editing
- ✅ Add your project title, student names, and faculty guide names
- ✅ Replace placeholder text in sections with your actual content
- ✅ Add figures, tables, and diagrams relevant to your project
- ✅ Expand chapter sections with your research and findings
- ✅ Add references in IEEE format as shown in Chapter 11
- ✅ Include your acknowledgements and abbreviations
- ✅ Add appendices with plagiarism reports, certificates, and cyber laws

#### 2. Document Structure
- ✅ Keep the 10-chapter structure (Introduction through Conclusions)
- ✅ Maintain chapter numbering (1, 2, 3... 10)
- ✅ Use proper section numbering (1.1, 1.2, 1.3... for subsections)
- ✅ Keep subsection numbering as 1.1.1, 1.1.2 for sub-subsections
- ✅ Add new subsections within existing chapters as needed

#### 3. Formatting Consistency
- ✅ Use the provided `\figurelegend{}` command for figure legends at 10pt
- ✅ Place figure captions at the bottom (12pt)
- ✅ Place table titles at the top (12pt)
- ✅ Use provided table environments (longtable, tabular)
- ✅ Maintain 1.5 line spacing throughout document
- ✅ Keep text justified with left alignment

#### 4. Academic Content
- ✅ Add minimum 10 research papers in Literature Review
- ✅ Include functional and non-functional requirements
- ✅ Document all project phases with timelines
- ✅ Provide cost estimation using COCOMO model
- ✅ Include UML diagrams (Use Case, Class, Sequence, Activity, ER, Component, Deployment)
- ✅ Add test cases and performance metrics
- ✅ Include comparison with existing solutions

#### 5. Header/Footer
- ✅ Keep the standard header: "NAME OF PROJECT" (centered, 10pt)
- ✅ Keep the standard footer: "COLLEGE - IT - YEAR | Page Number" (centered, 10pt)
- ✅ Header and footer apply from Contents page onward

---

### ❌ DON'Ts - Preserve Template Structure

#### 1. Layout and Design
- ❌ DO NOT change page margins (1" top/bottom, 1.25" left/right)
- ❌ DO NOT modify line spacing from 1.5 lines
- ❌ DO NOT change page size from A4
- ❌ DO NOT alter the two-sided printing layout
- ❌ DO NOT change the overall document geometry

#### 2. Font and Typography
- ❌ DO NOT change the main font from Times New Roman
- ❌ DO NOT change body text size from 12pt
- ❌ DO NOT change chapter title size from 16pt or style from bold/uppercase
- ❌ DO NOT change section heading size from 12pt or style from bold
- ❌ DO NOT modify header/footer font size from 10pt
- ❌ DO NOT change text alignment from justified for body text

#### 3. Page Numbering
- ❌ DO NOT start page numbering before the Contents page
- ❌ DO NOT number pages in front matter (cover, front page, certificates)
- ❌ DO NOT change page numbering format from arabic numerals
- ❌ DO NOT move the page number location from footer center

#### 4. Document Structure
- ❌ DO NOT remove any required pages:
   - Cover page
   - Front page
   - Institute certificate
   - Industry certificate (if applicable)
   - Acknowledgement
   - List of Figures
   - List of Tables
   - List of Abbreviations
   - Table of Contents
   - Abstract
- ❌ DO NOT remove any standard chapters:
   - Chapter 1: Introduction
   - Chapter 2: Literature Review
   - Chapter 3: Requirements
   - Chapter 4: Project Plan
   - Chapter 5: Methodology
   - Chapter 6: Design
   - Chapter 7: Implementation
   - Chapter 8: Testing
   - Chapter 9: Results and Discussions
   - Chapter 10: Conclusions and Future Work
- ❌ DO NOT remove References or Appendices
- ❌ DO NOT reorder chapters or sections

#### 5. Metadata Fields
- ❌ DO NOT remove metadata commands from main.tex:
   ```latex
   \ProjectTitle
   \StudentOne, \StudentTwo, \StudentThree, \StudentFour
   \PRNOne, \PRNTwo, \PRNThree, \PRNFour
   \GuideOne, \GuideTwo
   \HODName
   \CollegeName, \CollegeAddress
   \AcademicYear
   ```
- ❌ DO NOT hardcode student names instead of using placeholders

#### 6. File Structure
- ❌ DO NOT delete section files (*.tex files in sections/)
- ❌ DO NOT rename section files or main.tex
- ❌ DO NOT modify file includes in main.tex (the \input{} commands)
- ❌ DO NOT create a different folder structure

#### 7. College-Specific Information
- ❌ DO NOT remove PCCOE college name
- ❌ DO NOT remove Savitribai Phule Pune University affiliation
- ❌ DO NOT remove Department of Information Technology reference
- ❌ DO NOT remove college address or location
- ❌ DO NOT remove HOD name reference

#### 8. Styling Elements
- ❌ DO NOT modify figure styling commands
- ❌ DO NOT change table formatting templates
- ❌ DO NOT alter caption formatting or styling
- ❌ DO NOT remove placeholder boxes for diagrams/figures until replaced
- ❌ DO NOT change list formatting (\begin{itemize}, \begin{enumerate})

#### 9. Header and Footer
- ❌ DO NOT remove or modify header content
- ❌ DO NOT remove or modify footer content
- ❌ DO NOT add extra footer information beyond provided template
- ❌ DO NOT change footer alignment from center
- ❌ DO NOT remove college name from footer

#### 10. Compilation Settings
- ❌ DO NOT change document class from `report`
- ❌ DO NOT modify packages included in preamble
- ❌ DO NOT remove graphics capability (\usepackage{graphicx})
- ❌ DO NOT remove hyperref package
- ❌ DO NOT modify the preamble setup

---

## Quick Checklist Before Submission

Before submitting your report, verify:

**Content Checklist:**
- ☐ All 4 student names and PRNs are filled in
- ☐ Both faculty guide names are filled in
- ☐ HOD name is filled in (Dr. Jayashree Kati)
- ☐ Project title is appropriate and centered
- ☐ Academic year is set to 2025-26
- ☐ All 10 chapters contain relevant content
- ☐ Literature Review contains at least 10 research papers
- ☐ Requirements section has functional and non-functional requirements
- ☐ References are in IEEE format
- ☐ All figures have titles and legends (10pt)
- ☐ All tables have titles at top (12pt)
- ☐ Acknowledgements mention all contributors

**Formatting Checklist:**
- ☐ Page margins are 1" top/bottom and 1.25" left/right
- ☐ Font is Times New Roman throughout
- ☐ Line spacing is 1.5 everywhere
- ☐ Body text is 12pt and justified
- ☐ Chapter titles are 16pt, bold, uppercase, centered
- ☐ Section headings are 12pt, bold, left-aligned
- ☐ Page numbering starts from Contents (as page 1)
- ☐ Front matter pages (cover, front, certificates) are unnumbered
- ☐ Header shows project title (10pt, centered)
- ☐ Footer shows "COLLEGE - IT - YEAR | Page Number" (10pt, centered)
- ☐ No page overlaps or content spilling to extra pages
- ☐ All figures and diagrams are sharp, clear, black/white or color
- ☐ Maximum 2 figures per page, ideally 1
- ☐ Proper margins around all illustrations

**Compliance Checklist:**
- ☐ Report is in A4 size
- ☐ Report is printed/prepared for two-sided printing
- ☐ Maximum page limit (60 pages) is not exceeded
- ☐ Total project has 3 copies (1 for candidate, 1 for guide, 1 for library)
- ☐ Document is signed by guide, HOD, and Director
- ☐ Plagiarism report is included in appendix
- ☐ All cyber laws and compliance noted in appendix

---

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
├── README.md                             # Setup and build instructions
├── LICENSE                               # MIT License (template repository)
├── .gitignore                            # Git ignore rules
├── CUSTOMIZATION_GUIDE.md               # Customization instructions
├── sections/
│   ├── 00_cover_page.tex
│   ├── 01_front_page.tex
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

For questions about the template or to report issues, visit the GitHub repository:
https://github.com/SidddhantJain/PCCOE_Blackbook_Latex_Template

Template created by: Siddhant Mishrikotkar
License: MIT (applies to template repository structure only)

---

**Last Updated:** April 25, 2026
