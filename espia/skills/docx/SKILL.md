---
name: docx
description: Generate .docx files from structured prompts using python-docx
---

# docx Skill

Generates formatted Word documents from structured input.

## Input Format

The skill accepts a JSON-like structure with these fields:

```yaml
title: "Document Title"
author: "Author Name"
sections:
  - type: heading
    level: 1
    text: "Section Title"
  - type: paragraph
    text: "Some body text with **bold** and *italic*."
  - type: bullet_list
    items:
      - "Item 1"
      - "Item 2"
  - type: table
    headers: ["Col1", "Col2"]
    rows:
      - ["A", "B"]
      - ["C", "D"]
  - type: image
    path: "path/to/image.png"
    width: 500
  - type: page_break
```

## Implementation

Use `python-docx` package. The generator script lives at `espia/skills/docx/generate.py`.

### Steps
1. Parse the input YAML/JSON
2. Create a `python-docx` Document
3. Iterate sections and append elements
4. Save to `output/<title>.docx`
5. Return the file path

### Style defaults
- Font: Calibri, 11pt
- Heading 1: 18pt bold
- Heading 2: 16pt bold
- Heading 3: 14pt bold
- Normal: 11pt
- Table style: `Light Grid Accent 1`

## Usage

```python
from espia.skills.docx.generate import generate_docx

path = generate_docx("output/MyDoc.docx", {
    "title": "My Document",
    "author": "Me",
    "sections": [...]
})
```
