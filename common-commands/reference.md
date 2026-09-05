# Common MATLAB Commands Reference

This reference groups frequently used commands by task. Run `help commandName` or `doc commandName` in MATLAB for release-specific details.

## Workspace and scripts

| Command | Use |
|---|---|
| `clc` | Clear the Command Window |
| `clear` | Remove variables from the workspace |
| `clearvars` | Remove selected or all variables |
| `close all` | Close open figure windows |
| `who`, `whos` | List workspace variables and details |
| `pwd` | Show current folder |
| `cd folder` | Change current folder |
| `dir` | List files and folders |
| `which name` | Show which file MATLAB will call |
| `help name` | Display concise help |
| `doc name` | Open full documentation |
| `edit name` | Open a script or function in the Editor |
| `run('script.m')` | Run a script explicitly |

## Numeric and statistical operations

| Command | Use |
|---|---|
| `sum`, `cumsum` | Sum and cumulative sum |
| `mean`, `median` | Central tendency |
| `std`, `var` | Spread and variance |
| `min`, `max` | Extremes |
| `range` | Maximum minus minimum |
| `sort`, `sortrows` | Ordering values or table rows |
| `find` | Indices satisfying a condition |
| `isfinite`, `isnan`, `ismissing` | Data-quality checks |
| `round`, `floor`, `ceil` | Rounding |
| `abs`, `sqrt`, `exp`, `log` | Element-wise mathematical functions |
| `norm` | Vector or matrix norm |

## Linear algebra and numerical methods

| Command | Use |
|---|---|
| `det(A)` | Determinant |
| `rank(A)` | Matrix rank |
| `eig(A)` | Eigenvalues and eigenvectors |
| `svd(A)` | Singular value decomposition |
| `lu`, `qr`, `chol` | Matrix factorizations |
| `A \ b` | Solve `A*x = b` |
| `fzero` | Find a scalar function root |
| `fminbnd` | Bounded scalar minimization |
| `integral` | Numerical integration |
| `gradient`, `diff` | Numerical differences |
| `interp1` | One-dimensional interpolation |

## Signal and image operations

| Command | Use |
|---|---|
| `fft`, `ifft` | Fourier transform and inverse |
| `spectrogram` | Time-frequency analysis |
| `filter`, `filtfilt` | Apply digital filters |
| `audioread`, `audiowrite` | Read and write audio |
| `imread`, `imwrite` | Read and write images |
| `im2gray`, `rgb2gray` | Convert to grayscale |
| `imshow`, `imagesc` | Display images or matrices |
| `edge` | Detect image edges |
| `bwlabel`, `bwconncomp` | Label connected components |
| `regionprops` | Measure image regions |

## Timing and profiling

```matlab
tic;
result = expensiveOperation();
elapsedSeconds = toc;

profile on;
run('analysis_script.m');
profile viewer;
```

Use `timeit(@() functionCall())` to benchmark a function repeatedly. Profile only after confirming that the code is correct.
