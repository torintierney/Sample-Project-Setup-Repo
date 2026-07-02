---
name: doc-to-markdown
description: Converts DOCX, PDF, and VTT files to clean Markdown (.md) files in place. Use when you upload meeting transcripts, Word documents, PDFs, or caption/subtitle files to the input/ directory. The skill converts to Markdown in the same location and optionally removes the original file. Handles single files or entire directories. Speaker labels are preserved from VTT files by default. Images in PDFs are extracted to subdirectories with Markdown references.
---

# Doc to Markdown Skill

## Goal
Convert one or more DOCX, PDF, or VTT source files uploaded to the input/ directory into clean Markdown files in the same location, then optionally delete the original files to keep the workspace tidy.

## Inputs Required
- A file path or directory containing `.docx`, `.pdf`, and/or `.vtt` files (typically `input/` or subdirectories like `input/meeting-notes/`, `input/requirements/`, `input/research/`).
- Optional: whether to suppress VTT speaker labels (default is to keep them).
- Optional: whether to delete source files after conversion (default is to keep them).

**Standard workflow:** Upload files to `input/` → run this skill → Markdown files appear in the same directory → optionally delete original files.

## Script
Run the bundled conversion script:

```bash
python .github/skills/doc-to-markdown/scripts/convert_to_markdown.py <input_path> [--vtt-speaker-labels] [--delete-source]
```

### Dependencies
```bash
pip install python-docx pdfplumber
```

### Arguments
| Argument | Required | Description |
|---|---|---|
| `input_path` | Yes | Path to a single file or a directory of files (e.g., `input/meeting-notes/`) |
| `--vtt-speaker-labels` | No | Preserve speaker labels in VTT output (on by default) |
| `--delete-source` | No | Delete the original file after successful conversion (recommended for keeping input/ clean) |
| `--output-dir` | No | Directory to write output .md files (defaults to same directory as input) |

## Conversion Behavior

### DOCX → Markdown
- Heading styles (Heading 1–4) map to `#`, `##`, `###`, `####`.
- List paragraphs map to `- ` bullet items.
- Tables are converted to GitHub-flavored Markdown pipe tables.
- All other paragraphs are output as plain text lines.

### PDF → Markdown
- Text extraction preserves paragraph structure.
- Tables are automatically detected and converted to GitHub-flavored Markdown pipe tables.
- Headings are heuristically detected based on font size and position (larger fonts and first-page text are identified as potential headings).
- Images are automatically extracted to a `{filename}_images/` subdirectory.
- Image references are embedded in the output Markdown with the format `![Image](image_N.png)`.
- When `--delete-source` is used with PDFs containing images, a warning is displayed noting that images are preserved while the source PDF is deleted.

### VTT → Markdown
- Speaker labels are detected from `<v Speaker>` tags and `Speaker Name:` patterns.
- When speaker labels are preserved, each new speaker gets a bold heading with a timestamp.
- Consecutive lines from the same speaker are merged into a single paragraph.
- HTML tags in VTT cues are stripped from output.
- Timestamps are simplified to HH:MM:SS.

## Output
- One `.md` file per input file, named `{original-stem}.md`, written to the same directory as the source file.
- For PDF files with images: a `{filename}_images/` subdirectory containing extracted images.
- If `--delete-source` is used, the original `.docx`, `.pdf`, or `.vtt` file is removed after conversion completes successfully.
- Example: `input/meeting-notes/2026-06-11-discovery.docx` → `input/meeting-notes/2026-06-11-discovery.md` + original file deleted.
- Example: `input/requirements/spec.pdf` → `input/requirements/spec.md` + `input/requirements/spec_images/image_0.png` (+ others) + original file deleted.

## Workflow

1. User uploads DOCX, PDF, or VTT files to `input/` or a subdirectory (e.g., `input/meeting-notes/`, `input/requirements/`).
2. Confirm the file path(s) exist and are valid.
3. Check that `python-docx` and `pdfplumber` are installed; install them if not.
4. Run the conversion script with or without `--delete-source` flag.
5. Confirm output markdown file paths to the user.
6. For PDF files with images, confirm the `_images/` subdirectory was created.
7. Verify that original files have been deleted (when using `--delete-source`).
8. If the user wants to move output files to a specific project folder (for example: `NexTitle Test case/`), offer to do so after conversion.

## Guards
- Do not delete the source file unless `--delete-source` is explicitly used or the conversion succeeds with zero errors.
- If a file fails to convert, report the error, do not delete the source file, and continue with remaining files.
- Do not invent content — output only what exists in the source document.
- Always confirm successful conversion before suggesting source file deletion.

## Example Invocations

- Convert a single DOCX file in place and delete the original:
  ```bash
  python .github/skills/doc-to-markdown/scripts/convert_to_markdown.py "input/meeting-notes/My Meeting.docx" --delete-source
  ```

- Convert a single PDF file and extract images:
  ```bash
  python .github/skills/doc-to-markdown/scripts/convert_to_markdown.py "input/requirements/spec.pdf" --delete-source
  ```

- Convert all DOCX, PDF, and VTT files in a directory, leaving originals intact:
  ```bash
  python .github/skills/doc-to-markdown/scripts/convert_to_markdown.py input/meeting-notes
  ```

- Convert all files in a directory and clean up originals:
  ```bash
  python .github/skills/doc-to-markdown/scripts/convert_to_markdown.py input/requirements --delete-source
  ```

- Convert a VTT file without speaker labels and delete the original:
  ```bash
  python .github/skills/doc-to-markdown/scripts/convert_to_markdown.py input/research/transcript.vtt --delete-source
  ```

## Typical Input Directory Structure
```
input/
├── meeting-notes/
│   ├── 2026-06-11-discovery.docx          [uploaded]
│   └── 2026-06-11-discovery.md            [generated]
├── requirements/
│   ├── functional-spec.pdf                [uploaded]
│   ├── functional-spec.md                 [generated]
│   └── functional-spec_images/            [generated, images extracted]
│       ├── image_0.png
│       └── image_1.png
└── research/
    ├── market-analysis-transcript.vtt     [uploaded]
    └── market-analysis-transcript.md      [generated]
```
