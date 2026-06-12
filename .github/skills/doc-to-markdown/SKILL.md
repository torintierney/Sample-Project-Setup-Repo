---
name: doc-to-markdown
description: Converts DOCX and VTT files to clean Markdown (.md) files in place. Use when you upload meeting transcripts, Word documents, or caption/subtitle files to the input/ directory. The skill converts to Markdown in the same location and removes the original file. Handles single files or entire directories. Speaker labels are preserved from VTT files by default.
---

# Doc to Markdown Skill

## Goal
Convert one or more DOCX or VTT source files uploaded to the input/ directory into clean Markdown files in the same location, then delete the original files to keep the workspace tidy.

## Inputs Required
- A file path or directory containing `.docx` and/or `.vtt` files (typically `input/` or subdirectories like `input/meeting-notes/`, `input/requirements/`, `input/research/`).
- Optional: whether to suppress VTT speaker labels (default is to keep them).

**Standard workflow:** Upload files to `input/` → run this skill → Markdown files appear in the same directory → original files are deleted.

## Script
Run the bundled conversion script:

```bash
python .github/skills/doc-to-markdown/scripts/convert_to_markdown.py <input_path> [--vtt-speaker-labels] [--delete-source]
```

### Dependencies
```bash
pip install python-docx
```

### Arguments
| Argument | Required | Description |
|---|---|---|
| `input_path` | Yes | Path to a single file or a directory of files (e.g., `input/meeting-notes/`) |
| `--vtt-speaker-labels` | No | Preserve speaker labels in VTT output (on by default) |
| `--delete-source` | No | Delete the original file after successful conversion (recommended for keeping input/ clean) |

## Conversion Behavior

### DOCX → Markdown
- Heading styles (Heading 1–4) map to `#`, `##`, `###`, `####`.
- List paragraphs map to `- ` bullet items.
- Tables are converted to GitHub-flavored Markdown pipe tables.
- All other paragraphs are output as plain text lines.

### VTT → Markdown
- Speaker labels are detected from `<v Speaker>` tags and `Speaker Name:` patterns.
- When speaker labels are preserved, each new speaker gets a bold heading with a timestamp.
- Consecutive lines from the same speaker are merged into a single paragraph.
- HTML tags in VTT cues are stripped from output.
- Timestamps are simplified to HH:MM:SS.

## Output
- One `.md` file per input file, named `{original-stem}.md`, written to the same directory as the source file.
- If `--delete-source` is used, the original `.docx` or `.vtt` file is removed after conversion completes successfully.
- Example: `input/meeting-notes/2026-06-11-discovery.docx` → `input/meeting-notes/2026-06-11-discovery.md` + original file deleted.

## User uploads DOCX or VTT files to `input/` or a subdirectory (e.g., `input/meeting-notes/`).
2. Confirm the file path(s) exist and are valid.
3. Check that `python-docx` is installed; install it if not.
4. Run the conversion script with `--delete-source` flag to convert and remove originals in place.
5. Confirm output markdown file paths to the user.
6. Verify that original files have been deleted (when using `--delete-source`)
5. If the user wants to move output files to a specific project folder (for example: `NexTitle Test case/`), offer to do so after conversion.

## Guardrdelete the source file unless `--delete-source` is explicitly used or the conversion succeeds with zero errors.
- If a file fails to convert, report the error, do not delete the source file, and continue with remaining files.
- Do not invent content — output only what exists in the source document.
- Always confirm successful conversion before suggesting source file deletionng files.
- Do not invent content — output only what exists in the source document.

## Example Invocations in place and delete the original:
  `python .github/skills/doc-to-markdown/scripts/convert_to_markdown.py "input/meeting-notes/My Meeting.docx" --delete-source`

- Convert all DOCX and VTT files in a directory, leaving originals intact:
  `python .github/skills/doc-to-markdown/scripts/convert_to_markdown.py input/meeting-notes`

- Convert all DOCX and VTT files in a directory and clean up originals:
  `python .github/skills/doc-to-markdown/scripts/convert_to_markdown.py input/meeting-notes --delete-source`

- Convert a VTT file without speaker labels and delete the original:
  `python .github/skills/doc-to-markdown/scripts/convert_to_markdown.py input/research/transcript.vtt --delete-source`

## Typical Input Directory Structure
```
input/
├── meeting-notes/
│   ├── 2026-06-11-discovery.docx          [uploaded]
│   └── 2026-06-11-discovery.md            [generated]
├── requirements/
│   ├── functional-spec.docx               [uploaded]
│   └── functional-spec.md                 [generated]
└── research/
    ├── market-analysis-transcript.vtt     [uploaded]
    └── market-analysis-transcript.md      [generated]
``
  `python .github/skills/doc-to-markdown/scripts/convert_to_markdown.py transcript.vtt --no-vtt-speaker-labels`
