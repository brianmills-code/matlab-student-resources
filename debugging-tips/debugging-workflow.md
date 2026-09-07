# MATLAB Debugging Tips

Debugging is a methodical process: reproduce the problem, isolate the cause, test a small correction, and verify the result. Do not treat a script that runs without an error as automatically correct; numerical and logical mistakes often produce plausible-looking output.

## A repeatable workflow

| Step | Action | Useful MATLAB tools |
|---:|---|---|
| 1 | Reproduce the failure with the smallest input that still fails. | A short script, fixed inputs, `rng(1)` |
| 2 | Read the complete error message and inspect the reported line. | Command Window, `dbstack` |
| 3 | Check shapes, classes, ranges, and missing values. | `size`, `class`, `whos`, `min`, `max`, `isfinite` |
| 4 | Stop immediately before the failure. | Breakpoint, `dbstop if error` |
| 5 | Check assumptions explicitly. | `assert`, `validateattributes`, `arguments` |
| 6 | Test boundary cases and a known simple case. | Empty, scalar, zero, negative, and mismatched inputs |
| 7 | Rerun the complete workflow from a clean workspace. | `clearvars`, `close all`, `clc` |

## Common error patterns

| Symptom | Likely cause | Check or correction |
|---|---|---|
| `Index exceeds array bounds` | Index is zero, too large, or assumes the wrong orientation. | Inspect `size(A)` and remember MATLAB indexing starts at 1. |
| `Matrix dimensions must agree` | Arrays have incompatible shapes or implicit expansion was not intended. | Display sizes and use `reshape`, transpose, or explicit broadcasting deliberately. |
| Wrong numerical result with no error | Used matrix operators instead of element-wise operators. | Compare `*` with `.*`, `/` with `./`, and `^` with `.^`. |
| Function not found | File is not on the path or the name does not match the primary function. | Use `which functionName`, `pwd`, and `addpath` carefully. |
| Results depend on earlier work | Script relies on variables left in the workspace. | Start clean and turn the script into a function. |
| Plot looks empty or misleading | NaN values, incorrect units, or a wrong axis range. | Check `isfinite`, units, `xlim`, `ylim`, and vector lengths. |

## Diagnostic snippets

```matlab
fprintf('Class: %s\n', class(x));
disp('Size:'); disp(size(x));
assert(isnumeric(x) && ~isempty(x), 'x must be a non-empty numeric array.');
assert(all(isfinite(x), 'all'), 'x contains NaN or Inf.');

% Stop at the first runtime error while developing.
dbstop if error
```

Use `dbstep`, `dbcont`, and `dbquit` while paused in the debugger. Remove or disable the breakpoint after the issue is understood. For a suspicious numerical result, compare against a hand-calculated small case, a limiting case, or an independent implementation.

## Defensive programming

Validate inputs at function boundaries rather than relying on comments. Preallocate arrays before loops, use descriptive variable names with units, and assert dimensions before matrix operations. For iterative algorithms, record the residual at every iteration and stop on both a tolerance and a maximum-iteration limit.

## Final verification checklist

Run the code from a clean workspace, test at least one normal case and several edge cases, confirm units and dimensions, inspect plots and residuals, and document any assumptions or toolbox requirements. A useful debugging note records the original symptom, root cause, correction, and the test that proves the correction works.
