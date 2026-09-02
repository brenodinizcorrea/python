# Python Studies — Project Context

This is a structured Python study repo. Each module lives in `01-fundamentals/NN-topic-name/` and contains:
- **Theory notebooks** (`NN-topic.ipynb`) — lesson content
- **Exercise notebooks** (`exercises/NN-topic.ipynb`) — blank-cell practice

The full topic map is in `README.md`.

---

## Available Skills

Complete registry at `.claude/skills/registry.yaml`.

| Skill | Description |
|-------|-------------|
| `/generate-theory-notebook` | Creates a theory `.ipynb` file following the repo's lesson anatomy |
| `/generate-exercise-notebook` | Creates an exercise `.ipynb` file with 5 blank-code-cell exercises |

### Usage

```
/generate-theory-notebook <topic> <module> <number> "<sub-concepts>"
/generate-exercise-notebook <topic> <module> <number> "<sub-concepts>"
```

**Example:**
```
/generate-theory-notebook Try/Except 08-errors-and-exceptions 02 "try/except block, catching specific errors, multiple errors, fallback"
/generate-exercise-notebook Try/Except 08-errors-and-exceptions 02 "try/except block, catching specific errors, multiple errors, fallback"
```
