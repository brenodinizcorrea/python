# Python Studies

A structured repository for learning Python from the ground up — one concept at a time, through micro-learnings and hands-on practice.

## Goal

A complete Python study path — from the language fundamentals all the way to libraries, frameworks, and real-world applications. The repo is organized progressively: each module builds on the previous one, starting with pure Python and expanding into the broader ecosystem.

## Learning Philosophy

- **Why before what** — every topic starts with a concrete, relatable problem before naming the concept
- **Small steps** — each notebook covers one idea through minimal, runnable examples
- **Practice alongside theory** — every lesson has a companion exercise notebook in `exercises/`

## Notebook Anatomy

**Theory notebooks** follow a consistent arc:
1. `## The Problem` — a real scenario that motivates the concept
2. Content sections — each sub-concept explained in prose, immediately followed by a self-contained code demo
3. `# Summary` — a bullet-point recap of everything covered

**Exercise notebooks** pair with each theory notebook:
- 5 exercises per notebook, one per sub-concept
- Each exercise is a blank code cell with an imperative description — the learner fills it in

## Structure

```text
01-fundamentals/
│
├── 01-variables/
│   ├── 01-whats_a_variable.ipynb           Variables as named references; assignment, reassignment, naming rules
│   └── 02-variables_and_objects.ipynb      Python object model; mutable vs immutable; shared references
│
├── 02-data-types/
│   ├── 01-integer.ipynb                    Whole numbers; arithmetic; integer vs float division
│   ├── 02-floating-point.ipynb             Fractional numbers; binary precision; 0.1+0.2 ≠ 0.3
│   ├── 03-string.ipynb                     Immutable char sequences; creation; reassignment
│   ├── 04-list.ipynb                       Mutable ordered sequences; mutation vs reassignment
│   ├── 05-tuple.ipynb                      Immutable ordered sequences; shared refs
│   ├── 06-dict.ipynb                       Mutable key-value stores; access; mutation
│   ├── 07-set.ipynb                        Mutable unordered unique collections
│   ├── 08-bool.ipynb                       True/False singleton objects; immutability
│   └── 09-none.ipynb                       Singleton absence-of-value; None vs empty values
│
├── 03-expressions-and-operators/
│   ├── 01-arithmetic-operators.ipynb       +, -, *, /, //, %, **; type mixing int/float
│   ├── 02-comparison-operators.ipynb       ==, !=, >, <, >=, <=; bool results; string comparison
│   ├── 03-logical-operators.ipynb          and, or, not; combining comparisons; short-circuit
│   └── 04-expressions-and-statements.ipynb Expressions produce values; statements do things
│
├── 04-control-flow/
│   ├── 01-if-elif-else.ipynb               Conditional branching; indentation; evaluation order
│   ├── 02-for-loops.ipynb                  Iteration over lists, strings, dicts, range(); nested loops
│   ├── 03-while-loops.ipynb                Condition-based loops; update variable; infinite loop risk
│   └── 04-break-continue-pass.ipynb        Loop control: exit / skip / placeholder
│
├── 05-collections/
│   ├── 01-indexing-and-slicing.ipynb       Positive/negative index; slice start:stop:step; IndexError
│   ├── 02-collection-methods.ipynb         Methods; modify-in-place vs return-new; list/set/dict methods
│   ├── 03-unpacking.ipynb                  Destructuring; extended unpacking (*); loops
│   └── 04-nested-collections.ipynb         Collections inside collections; hashability; nested loops
│
├── 06-functions/
│   ├── 01-def-and-return.ipynb             Define/call; return vs print; multiple returns; functions as objects
│   ├── 02-parameters-and-arguments.ipynb   Positional vs keyword args; type hints; errors on mismatch
│   ├── 03-default-and-keyword-arguments.ipynb  Default values; ordering rules; evaluated-once trap
│   ├── 04-local-and-global-scope.ipynb     Local vs global; shadowing; global keyword; nested scope
│   └── 05-lambda-functions.ipynb           Anonymous single-expr functions; lambda as argument; limitations
│
├── 07-comprehensions-and-iteration/
│   ├── 01-list-comprehensions.ipynb        Loop→comprehension; transform; filter; transform+filter
│   ├── 02-set-and-dict-comprehensions.ipynb Set & dict comprehensions; comparison of all three types
│   └── 03-iterables-and-iterators.ipynb    iter()/next(); StopIteration; how for works under the hood
│
├── 08-errors-and-exceptions/
│   ├── 01-types-of-errors.ipynb            NameError, TypeError, ValueError, IndexError, KeyError
│   ├── 02-try-except.ipynb                 try/except blocks; catching specific vs generic errors; fallback
│   ├── 03-else-and-finally.ipynb           else (runs when no error); finally (always runs); cleanup patterns
│   └── 04-raising-exceptions.ipynb         raise keyword; when and why to raise; re-raising
│
├── 09-modules-and-packages/
│   ├── 01-modules-and-imports.ipynb        import; __name__ == '__main__'; module as namespace
│   ├── 02-import-variations.ipynb          from X import Y; aliasing (as); wildcard imports and why to avoid
│   ├── 03-packages.ipynb                   Folder-based packages; __init__.py; relative imports
│   └── 04-standard-library.ipynb           os, pathlib, datetime, math, random, json — practical stdlib tour
│
├── 10-files-and-data/
│   ├── 01-file-paths.ipynb                 Absolute vs relative paths; pathlib.Path; navigating the filesystem
│   ├── 02-reading-and-writing-files.ipynb  open(); modes (r/w/a); read/write; context manager (with)
│   ├── 03-context-managers.ipynb           with statement; __enter__/__exit__; why they matter
│   ├── 04-csv-files.ipynb                  csv module; reading rows; writing rows; DictReader/DictWriter
│   └── 05-json-files.ipynb                 json module; loads/dumps; load/dump; working with nested data
│
├── 11-object-oriented-programming/
│   ├── 01-classes-and-objects.ipynb        class keyword; creating instances; what an object is
│   ├── 02-attributes-and-methods.ipynb     Instance attributes; instance methods; self
│   ├── 03-init-and-instance-state.ipynb    __init__; setting initial state; attributes vs local variables
│   ├── 04-class-and-static-methods.ipynb   @classmethod vs @staticmethod vs instance method
│   ├── 05-inheritance.ipynb                Inheriting from a class; overriding; super()
│   └── 06-polymorphism.ipynb               Same interface, different behavior; duck typing; isinstance()
│
├── 12-python-data-model/
│   ├── 01-dunder-methods.ipynb             What dunder methods are; how Python calls them implicitly
│   ├── 02-str-and-repr.ipynb               __str__ (for users) vs __repr__ (for devs); when each is called
│   ├── 03-eq-and-comparisons.ipynb         __eq__, __lt__, __gt__; @functools.total_ordering
│   ├── 04-len-and-container-protocols.ipynb __len__, __contains__, __getitem__; making objects feel like collections
│   └── 05-iterable-protocol.ipynb          __iter__ and __next__; building a custom iterable class
│
└── 13-advanced-functions/
    ├── 01-args-and-kwargs.ipynb            *args; **kwargs; combining with positional/keyword params
    ├── 02-decorators.ipynb                 Wrapping functions; @syntax; preserving metadata (functools.wraps)
    └── 03-generators.ipynb                 yield; generator functions; lazy evaluation; generator vs list
```
