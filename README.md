# MATLAB Student Resources

A practical, organized reference for students learning MATLAB through examples, quick-reference sheets, practice problems, debugging workflows, numerical methods, and official documentation. This repository is intended for active study: read a short guide, run an example, modify it, and verify the result.

## Resource map

| Section | Files | Best for |
|---|---:|---|
| [Cheat Sheets](#1-cheat-sheets) | 4 | Fast syntax lookup and concept review |
| [Common Commands](#2-common-commands) | 1 | Finding the right MATLAB command by task |
| [Practice Problems](#3-practice-problems) | 1 | Deliberate exercises with an extension challenge |
| [Debugging Tips](#4-debugging-tips) | 1 | Diagnosing errors and validating results |
| [Matrix Operations](#5-matrix-operations) | 1 | Linear algebra, dimensions, and matrix syntax |
| [Plotting Guide](#6-plotting-guide) | 1 | Clear figures and reproducible exports |
| [Numerical Methods](#7-numerical-methods) | 1 | Root finding, integration, differentiation, and convergence |
| [Documentation](#8-documentation) | 1 | Official MATLAB references and learning links |
| **Total** | **11** | Complete student reference collection |

## 1. Cheat sheets

The cheat sheets provide compact explanations with syntax tables and runnable code. Use them while coding, but consult the full MATLAB documentation when behavior depends on the release or a toolbox.

| Resource | Covers |
|---|---|
| [Core Syntax](cheat-sheets/core-syntax.md) | Comments, vectors, sequences, indexing, logical selection, operators, function handles, and plots |
| [Arrays and Matrices](cheat-sheets/arrays-and-matrices.md) | Array creation, dimensions, indexing, reshaping, concatenation, element-wise operators, and linear systems |
| [Control Flow and Functions](cheat-sheets/control-flow-and-functions.md) | `if`, loops, functions, anonymous functions, assertions, warnings, and errors |
| [Plotting and Data](cheat-sheets/plotting-and-data.md) | Line plots, chart types, tables, file import/export, figure quality, and `exportgraphics` |

## 2. Common commands

The [Common MATLAB Commands Reference](common-commands/reference.md) groups frequently used commands by task. It covers workspace and scripts, numeric and statistical operations, linear algebra, numerical methods, signal and image processing, timing, and profiling. Use `help commandName` or `doc commandName` inside MATLAB for release-specific details.

## 3. Practice problems

[Practice Set 01: Foundations](practice-problems/problem-set-01.md) contains five exercises covering vectors, matrix indexing, plotting, functions, and numerical integration. It also includes an extension challenge for filtering measurements and a self-check standard for solution quality.

## 4. Debugging tips

The [MATLAB Debugging Tips](debugging-tips/debugging-workflow.md) guide presents a repeatable workflow from reproducing a failure through clean-workspace verification. It includes a symptom-to-cause table for indexing errors, dimension mismatches, incorrect operators, missing functions, stale workspace variables, and misleading plots. It also covers breakpoints, `dbstop if error`, assertions, defensive programming, and edge-case testing.

## 5. Matrix operations

The [Matrix Operations](matrix-operations/README.md) reference explains dimensions, transposes, solving `A*x = b` with `A\\b`, eigenvalues, and the distinction between matrix and element-wise operations. Use it before implementing linear systems, decompositions, or matrix-based models.

## 6. Plotting guide

The [Plotting Guide](plotting-guide/README.md) provides a concise checklist for figures: create a figure, label axes with units, add a meaningful title, use a legend only when needed, enable a grid when useful, and export the result reproducibly with `exportgraphics`.

## 7. Numerical methods

The [MATLAB Numerical Methods Guide](numerical-methods/README.md) explains how to select and document methods for scalar roots, minimization, integration, differentiation, interpolation, linear systems, and ordinary differential equations. It includes bisection code, `fzero`, `integral`, `gradient`, `interp1`, residual checks, and convergence studies.

## 8. Documentation

The [Useful Documentation Links](documentation/official-links.md) page collects official MathWorks references for MATLAB documentation, getting started, language fundamentals, graphics, and numerical algorithms.

## Recommended learning paths

### Path A: First week with MATLAB

Read [Core Syntax](cheat-sheets/core-syntax.md), run the examples in [MATLAB Programming Examples](https://github.com/brianmills-code/matlab-programming-examples), and complete Practice Set 01 problems 1–3. Use [Arrays and Matrices](cheat-sheets/arrays-and-matrices.md) whenever a dimension or indexing question appears.

### Path B: Reliable scripts and functions

Study [Control Flow and Functions](cheat-sheets/control-flow-and-functions.md), complete Practice Set 01 problems 4–5, and use the [Debugging Tips](debugging-tips/debugging-workflow.md) guide to test normal, boundary, and invalid inputs. Finish by converting one script into a validated function.

### Path C: Numerical and engineering work

Read [Numerical Methods](numerical-methods/README.md), review [Matrix Operations](matrix-operations/README.md), and work through the heat-diffusion and RC-circuit projects in [MATLAB Project Ideas](https://github.com/brianmills-code/matlab-project-ideas). Record tolerances, units, residuals, and convergence evidence in your project notes.

### Path D: Analysis and presentation

Use [Plotting and Data](cheat-sheets/plotting-and-data.md), then study the plotting and data-analysis project briefs in [MATLAB Project Ideas](https://github.com/brianmills-code/matlab-project-ideas). Reproduce one figure, change its data or styling, and explain what the visualization does and does not show.

## How to use this repository

Start each study session with a specific question. Find the smallest relevant section, run its example, and change one thing at a time. Keep scripts independent of accidental workspace variables, document toolbox requirements, use descriptive names with units, and preserve the code and data needed to reproduce any reported result.

## Related repositories

- [MATLAB Programming Examples](https://github.com/brianmills-code/matlab-programming-examples): runnable examples organized by programming topic.
- [MATLAB Project Ideas](https://github.com/brianmills-code/matlab-project-ideas): complete project briefs from Beginner through Machine Learning.

## License

MIT License. See [LICENSE](LICENSE).
