---
name: generate-theory-notebook
description: Generates a theory notebook .ipynb file for the Python study repo following the repo's lesson anatomy.
argument-hint: "<topic> <module-folder> <notebook-number> <sub-concepts>"
user-invocable: true
---

# Skill: Generate Theory Notebook

Creates a real `.ipynb` lesson file in the correct module folder, following the repo's anatomy.

## User Input

$ARGUMENTS

## Parameters

| Parameter | Required | Example |
|-----------|----------|---------|
| `topic` | yes | `Try/Except` |
| `module` | yes | `08-errors-and-exceptions` |
| `number` | yes | `02` |
| `sub-concepts` | yes | `try/except block, catching specific errors, multiple errors, fallback` |

If any parameter is missing, ask for it before proceeding.

## Instructions

1. **Resolve the file path:**
   ```
   /Users/breno.diniz/Documents/studies/github/python/01-fundamentals/<module>/<number>-<kebab-topic>.ipynb
   ```
   Example: `01-fundamentals/08-errors-and-exceptions/02-try-except.ipynb`

2. **Check the module folder exists.** If not, inform the user.

3. **Generate the notebook** as valid Jupyter Notebook JSON (nbformat 4) with this exact cell sequence:

   **Cell 1 — Markdown:** `# Topic Name`

   **Cell 2 — Markdown:** `## The Problem`
   A concrete, relatable scenario (1–3 sentences) showing *why* this concept matters. No Python jargon, no code yet.

   **Cell 3 — Code:** Minimal snippet that solves the problem.

   **For each sub-concept — repeat:**
   - **Markdown** `## Sub-Topic` — brief prose (1–5 sentences)
   - **Code** — minimal self-contained demo (5–15 lines)
   - **Markdown** *(optional)* — narrate what happened or highlight a subtlety
   - **Code** *(optional)* — contrasting case or deliberate error (show traceback as comment: `# Output: / # TypeError: ...`)

   **Comparison cell** *(when applicable)*: `## ConceptA vs. ConceptB`

   **Last cell — Markdown:** `# Summary` — one declarative bullet per key idea

4. **Style rules:**
   - "Why before what" — motivate before naming the concept
   - Each code cell independently runnable
   - Markdown-to-code ratio ~2:1 | ~20–30 cells total
   - Pure Python stdlib only
   - All content in English

5. **Recurring themes** (apply when relevant):
   - Data types → cover mutability + shared references
   - Functions → include `return` vs `print()` distinction
   - Iteration → show how `for` uses `__iter__`/`__next__`

6. **JSON cell format:**
   ```json
   { "cell_type": "markdown", "metadata": {}, "source": ["# Title\n"] }
   { "cell_type": "code", "execution_count": null, "metadata": {}, "outputs": [], "source": ["code here\n"] }
   ```
   Each `source` is an array of strings, one per line, each ending `\n` except the last.

7. **Write the file** using the Write tool at the resolved path.

8. **Confirm** the file path to the user.

## Usage Examples

```
/generate-theory-notebook Try/Except 08-errors-and-exceptions 02 "try/except block, catching specific errors, multiple errors, fallback"
/generate-theory-notebook Generators 13-advanced-functions 03 "yield, generator functions, lazy evaluation, generator vs list"
```
