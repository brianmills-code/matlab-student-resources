# MATLAB Arrays and Matrices Cheat Sheet

## Creation and inspection

| Task | Command | Example |
|---|---|---|
| Row vector | `[a b c]` | `x = [1 2 3]` |
| Column vector | `[a; b; c]` | `x = [1; 2; 3]` |
| Range | `start:step:stop` | `t = 0:0.1:1` |
| Evenly spaced values | `linspace(a,b,n)` | `x = linspace(0,1,100)` |
| Zeros or ones | `zeros`, `ones` | `A = zeros(3,4)` |
| Identity matrix | `eye(n)` | `I = eye(3)` |
| Random values | `rand`, `randn` | `r = randn(100,1)` |
| Dimensions | `size(A)` | `[rows, cols] = size(A)` |
| Number of elements | `numel(A)` | `n = numel(A)` |
| Data type | `class(A)` | `class(A)` |

## Indexing

MATLAB uses one-based indexing. For a matrix `A`, `A(i,j)` selects row `i`, column `j`; `A(i,:)` selects a complete row; `A(:,j)` selects a complete column; `A(:)` reshapes the contents into one column; and `A(end,:)` selects the last row.

Logical indexing is often clearer than manually computing positions:

```matlab
values = [3 -1 8 0 5];
positive = values(values > 0);
values(values < 0) = 0;
```

## Element-wise versus matrix operations

| Meaning | Operator |
|---|---|
| Matrix multiplication | `*` |
| Element-wise multiplication | `.*` |
| Matrix right division | `/` |
| Element-wise division | `./` |
| Matrix power | `^` |
| Element-wise power | `.^` |
| Transpose | `'` or `.'` |

Use `A \ b` to solve `A*x = b`. Prefer this over `inv(A)*b` because it is generally more appropriate numerically and communicates the intended operation directly.

## Common transformations

```matlab
column = A(:);
row = column.';
B = reshape(column, 2, 3);
C = [A B];       % horizontal concatenation
D = [A; B];      % vertical concatenation
sorted = sort(values);
uniqueValues = unique(values);
```

Always check dimensions before combining arrays. Use `assert(isequal(size(A), size(B)))` when an operation requires matching shapes.
