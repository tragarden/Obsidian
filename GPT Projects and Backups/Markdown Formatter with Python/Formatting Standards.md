# 📜 MarkdownFormatter-GPT — Formatting Standards

This document defines the official formatting rules that MarkdownFormatter-GPT will enforce across all Markdown notes.

---

## ❖ General Formatting Rules

- **Headers:**  
  - Use `#`, `##`, `###`, etc. with exactly **one space** after the `#`.
  - Always add **one blank line** before and after any header.

- **Paragraphs and Line Breaks:**  
  - No trailing spaces at the end of lines.
  - Exactly **one blank line** between paragraphs or sections.
  - Collapse multiple blank lines into one.

- **Lists:**  
  - Use `-` (dash) consistently for unordered list items.
  - No mixing of `*`, `+`, or inconsistent indentation.
  - Add one space after list markers (e.g., `- Item`).

- **YAML Frontmatter (if present):**  
  - Must start and end with triple dashes `---`.
  - Must appear at the very top of the file.
  - No extra blank lines inside the YAML block.

---

## ❖ Code Block Formatting Rules

- **All code snippets must use fenced code blocks** (triple backticks ```).
- **Do not use `>` blockquotes for any code**.
- If language is obvious (e.g., SQL, Python, Bash), **specify it** after the opening triple backticks.
- If language is unknown or mixed, leave the opening as plain ``` with no language tag.

### ➤ Example: SQL Query

````markdown
```sql
SELECT * FROM users WHERE id = 5;
````

---

## ❖ Backup and Data Integrity

- Original files will remain untouched during formatting.
- Formatted output will be written to a `/output/` directory.
- Output filenames will mirror input filenames but will conform to formatting standards (e.g., hybrid capitalized kebab casing).
- No overwriting of original files will occur during formatting.
- (Optional future feature: Backup originals if explicit user config enables it.)
