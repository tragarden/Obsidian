# Project Start: MarkdownFormatter-GPT

## Audit Goals and Initial Planning

---

## ❖ Project Assumptions

- I will be working primarily with **Markdown** `.md` files.
- Files may be **inconsistent**, **unstructured**, and **vary in formatting quality**.
- Core use case: **Batch process** or **single file process** formatting with minimal data loss.
- Python will be the primary language.
- Goal is **efficiency, reliability, and repeatability**, **not** overengineering.
- Files must be **backed up** before **any destructive action** (overwrites, moves, deletions).
- Solution must be **portable** — runnable on any clean machine with minimal setup.

---

## ❖ Key Goals and Checklist (Pre-Code)

| Goal | Priority | Notes |
|:-----|:---------|:------|
| 1. Define strict input and output formatting rules | Critical | e.g., consistent headers, spacing, frontmatter |
| 2. Plan for file backup before modifications | Critical | Automatic copy to a `/backup/` directory |
| 3. Set up a config system for adjustable options | High | User can toggle features like "add blank line after headers" |
| 4. Create a safe testing environment | High | Local "sandbox" directory with dummy files |
| 5. Identify mandatory Markdown standards to enforce | High | Eg: headers (#), bold, italic, code blocks |
| 6. Plan version control strategy | Medium | Git, manual version notes, or simple logging |
| 7. Prepare a minimum viable UI (CLI at first) | Medium | Simple flags: `--backup`, `--dry-run`, etc. |
| 8. Modularize the logic from the beginning | Medium | File loading, parsing, transforming, saving should be separate |
| 9. Avoid hard-coding file paths | Medium | Use relative paths or config files |
| 10. Plan for crash/error handling | Medium | Catch bad markdown, file permission errors |
| 11. Build a "dry-run" mode that simulates changes | Nice to Have | Outputs changes without writing them |
| 12. Track and report which files were changed | Nice to Have | Simple text log or output summary |

---

## ❖ Known Risks / Pitfalls

- **Accidental overwrite of original data**  
  ➔ **Mandatory**: automatic backups before writes.
- **Misinterpretation of file structure**  
  ➔ Solve by starting with strict, narrow rules, expand cautiously.
- **Feature creep**  
  ➔ Start with only core formatting needs — fancy features later.
- **Inconsistent Markdown edge cases** (bad inputs)  
  ➔ Try to fail gracefully, maybe skip file or isolate broken content.
- **Slow batch processing** (if folders are huge)  
  ➔ Optimize only *after* MVP is working.

---

## ❖ Immediate Next Steps

1. Draft example Markdown files:
   - **Good Format**, **Messy Format**, **Worst Case Format**  
   ➔ These are your future unit tests.
2. Write a document defining **"what makes a Markdown file properly formatted"**.
   - Clear written standard = clear coding target.
3. Set up a project directory:
   - `/input/`, `/output/`, `/backup/`, `/logs/`
4. Plan CLI arguments for initial version:
   - `python formatter.py --input ./input --backup --dry-run`

---

# 🚀 Reminder Before Coding

**Don't start coding until:**
- You have your example Markdown files created.
- You have your “proper format” spec written out.
- You know what a successful run looks like.

---

## Optional Next Steps

If desired, begin drafting:
- Example "good" and "bad" markdowns
- "Proper formatting spec" outline
- CLI design draft

**Choose one to proceed.**
