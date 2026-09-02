---
name: generate-exercise-notebook
description: Generates an exercise notebook .ipynb file for the Python study repo, pairing with a theory notebook. 5 blank-code-cell exercises, one per sub-concept.
argument-hint: "<topic> <module-folder> <notebook-number> <sub-concepts>"
user-invocable: true
---

# Skill: Generate Exercise Notebook

Creates a real `.ipynb` exercise file in the correct `exercises/` subfolder, pairing with a theory notebook.

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
   /Users/breno.diniz/Documents/studies/github/python/01-fundamentals/<module>/exercises/<number>-<kebab-topic>.ipynb
   ```
   Example: `01-fundamentals/08-errors-and-exceptions/exercises/02-try-except.ipynb`

2. **Check the `exercises/` folder exists.** If not, it will be created when writing the file.

3. **Generate the notebook** as valid Jupyter Notebook JSON (nbformat 4) with exactly **5 exercises** (6 only if there are 6 clearly distinct sub-concepts). Follow the same sub-concept order as the theory notebook.

   **For each exercise — exactly 2 cells:**

   **Cell A — Markdown:**
   ```
   # Exercise N — Short Descriptive Title
   ```
   *(em dash `—`, not hyphen `-`)*

   Followed by an imperative description specifying:
   - Exact variable or function names to use
   - What to print or return
   - Expected output inline: `# Expected output: True`
   - Given data if needed: `Given: numbers = [3, 6, 9]`

   **Cell B — Code:** completely empty — `"source": [""]`, `"outputs": []`

4. **Task type per exercise (in this order):**
   1. Write-from-scratch — "Create a variable / function that…"
   2. Given-data, transform — "Given: `x = [...]`. Create `y` where…"
   3. Conditional or logical — involves `if`/`elif`/`else` or boolean expressions
   4. Multi-step — chain 2–3 operations to reach the result
   5. Edge case — trigger a specific error OR demonstrate a subtle behavior

   *For errors-and-exceptions topics:* replace task 5 with "fix the error" — show broken code as a fenced block in the description, ask the learner to reproduce and fix it.

5. **Style rules:**
   - Imperative verbs: "Create", "Define", "Use", "Print", "Return", "Write"
   - Always name exact identifiers
   - Always state expected output when applicable
   - Each exercise fully self-contained (no shared state between exercises)
   - All content in English

6. **JSON cell format:**
   ```json
   { "cell_type": "markdown", "metadata": {}, "source": ["# Exercise 1 — Title\n\nDescription.\n"] }
   { "cell_type": "code", "execution_count": null, "metadata": {}, "outputs": [], "source": [""] }
   ```

7. **Write the file** using the Write tool at the resolved path.

8. **Confirm** the file path to the user.

## Usage Examples

```
/generate-exercise-notebook Try/Except 08-errors-and-exceptions 02 "try/except block, catching specific errors, multiple errors, fallback"
/generate-exercise-notebook Generators 13-advanced-functions 03 "yield, generator functions, lazy evaluation, generator vs list"
```
