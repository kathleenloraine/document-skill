# Document Generator Agent

## Project Overview
This project builds an AI-powered document generator that creates `.docx` files using opencode skills. The generator accepts structured prompts and produces formatted Word documents.

## Skills Structure
Skills live under `espia/skills/<skill-name>/SKILL.md`. Each skill defines a reusable document-generation capability.

### docx Skill
Located at `espia/skills/docx/SKILL.md`. This skill should:
- Accept structured input (title, sections, styling, tables, etc.)
- Use `python-docx` to generate `.docx` files
- Output the file path of the generated document
- Support formatting: headings, paragraphs, bullet lists, tables, images, page breaks

## Conventions
- Use `python-docx` library for document generation
- Always lint with `ruff` after changes (`ruff check .`)
- Default output directory for generated docs: `output/`
- Skill parameters follow markdown YAML frontmatter format
- Test generated documents manually by opening in Word/LibreOffice
- Keep the AGENTS.md up to date as new skills are added
