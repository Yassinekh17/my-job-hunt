---
name: resume-formatter
description: Convert the final CV Markdown into a clean, ATS-safe, print-ready DOCX and PDF following the CV design spec. Use after the content is final and the ATS audit passed.
---

# Resume Formatter

Produces the deliverable files. Content is already final; this skill only controls form.

## Inputs
`jobs/<slug>/cv.md`, the design choices from `cv-design`, ATS rules from `resume-ats-optimizer`.

## Procedure

1. **Read the file-creation skills first:** use the `docx` skill to build the Word file and the `pdf` skill to produce the PDF (or convert the DOCX to PDF with LibreOffice). Read each SKILL.md before building.
2. **Build the DOCX** from the Markdown with these settings (unless `cv-design` overrides within ATS limits):
   - Page: A4 for Tunisia/Europe/Gulf, US Letter for the US/Canada. Margins 1.5 to 2 cm (0.6 to 0.8 in).
   - Font: Calibri (or Arial), body 10.5 pt, name 18 to 22 pt bold, section titles 11 to 12 pt bold uppercase with a thin bottom border, entry titles 10.5 pt bold.
   - Line spacing 1.0 to 1.1, 4 pt after bullets, 8 to 10 pt before section titles.
   - Single column, standard round bullets via real list styles (not typed characters), real paragraph styles (Heading 1/2) for sections so parsers read structure.
   - Right-aligned dates using a right tab stop, **not** a table.
   - Contact line in the body, not in the Word header or footer.
   - Hyperlinks: show the visible URL text.
3. **Fit to one page** by trimming content (back to `resume-build-writer`), not by shrinking below 10 pt or margins below 1.2 cm.
4. **Export PDF** from the DOCX; ensure text is selectable (not an image). Embed fonts. Set document title and author in the properties.
5. **Verify:**
   - Convert the PDF to text (pdftotext) and confirm reading order is correct: name, contact, summary, experience, ... with no jumbled columns.
   - Render the PDF page to an image and inspect visually: nothing cut off, consistent alignment, no orphan heading at the bottom, no overflow to a second page.
   - Confirm page count, file size under 1 MB, file names as below.
6. **Name files:** `Firstname_Lastname_<Company>_<Role>_CV.docx` and `.pdf`; save to `jobs/<slug>/` and send both with SendUserFile.

## Which file to submit
- Upload the **PDF** unless the portal or posting asks for DOCX. If the portal parses poorly or requests Word, use the DOCX.
- Keep the DOCX as the editable master.

## Do not
- Use tables, columns, text boxes, icons, graphics, skill bars, photos (unless the user asks and the region expects it).
- Use colours beyond one dark accent (navy or dark grey) for section lines and name; body text stays black.
- Put content in headers/footers.
