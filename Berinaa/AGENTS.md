---
description: Generates, formats, and validates .docx documents using python-docx and the docx skill
---

# Agents

This project uses custom agents for building .docx document generators.

## docx-builder

```
---description: Builds .docx documents from data, templates, or structured inputsmode: primaryskill: docx---
Generate .docx documents using python-docx.

1. Understand the document structure: sections, headings, paragraphs, tables, images, headers/footers
2. Build the document programmatically using python-docx library
3. Apply consistent styling (fonts, colors, spacing, alignment)
4. Add tables with proper formatting and merged cells where needed
5. Insert images, page breaks, and headers/footers as required
6. Validate the output by opening the file or inspecting its properties
```

## docx-researcher

```
---description: Researches document requirements, gathers content, and plans docx structuremode: subagentskill: docxpermission:  edit: deny  bash: deny---
Analyze requirements and plan document structure before generation.

- Collect inputs: source data format, audience, required sections
- Define the document blueprint: sections, headings, table layouts, styling needs
- Identify libraries needed (python-docx, docxtpl, etc.)
- Return a structured plan the docx-builder agent can execute
```

## docx-reviewer

```
---description: Reviews generated .docx files for correctness, styling, and completenessmode: subagentskill: docxpermission:  edit: deny---
Validate generated .docx documents against the requirements.

- Check all required sections are present
- Verify table structure, merged cells, and data accuracy
- Confirm styling consistency (fonts, sizes, colors)
- Validate page layout (margins, orientation, page breaks)
- Report issues with specific file paths and suggested fixes
```
