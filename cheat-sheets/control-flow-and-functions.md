# MATLAB Control Flow and Functions Cheat Sheet

## Conditions

```matlab
if score >= 90
    grade = "A";
elseif score >= 80
    grade = "B";
else
    grade = "Needs review";
end
```

Use `&&` and `||` for scalar short-circuit logic, and `&` and `|` for element-wise logical operations on arrays. Use `~` for logical negation and `==`, `~=`, `<`, `<=`, `>`, and `>=` for comparisons.

## Loops

```matlab
for k = 1:10
    result(k) = k^2;
end

while errorValue > tolerance
    errorValue = updateError(errorValue);
end
```

Preallocate arrays before loops when the final size is known. Use `break` to exit a loop and `continue` to skip to the next iteration. Prefer vectorized expressions when they remain readable and correct.

## Functions

A function file begins with a signature and ends with `end`:

```matlab
function [meanValue, rangeValue] = summarize(values)
arguments
    values (1,:) double {mustBeFinite}
end
meanValue = mean(values);
rangeValue = max(values) - min(values);
end
```

The file name should match the primary function name. Keep functions focused on one responsibility, validate assumptions near the boundary, and document units and output meaning.

## Anonymous and nested functions

```matlab
square = @(x) x.^2;
root = fzero(@(x) cos(x) - x, [0 1]);
```

Use `@(x)` for short expressions. For larger algorithms, create a named function so it can be tested independently.

## Errors and assertions

```matlab
assert(isnumeric(x), 'x must be numeric.');
assert(~isempty(x), 'x must not be empty.');
error('Unsupported method: %s', method);
warning('Using default parameter value.');
```

Meaningful validation messages make debugging faster and prevent invalid results from being mistaken for successful output.
