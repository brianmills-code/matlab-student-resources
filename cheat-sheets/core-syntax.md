# Core MATLAB Syntax Cheat Sheet

| Task | Syntax | Example |
|---|---|---|
| Comment | `% text` | `% Explain the next step` |
| Create row vector | `[a b c]` | `x = [1 2 3]` |
| Create sequence | `start:step:stop` | `t = 0:0.1:1` |
| Uniform points | `linspace(a,b,n)` | `x = linspace(0,1,100)` |
| Index | `A(row,column)` | `value = A(2,3)` |
| Logical selection | `A(condition)` | `positive = A(A > 0)` |
| Element-wise operations | `.*`, `./`, `.^` | `y = x.^2` |
| Matrix multiplication | `*` | `C = A * B` |
| Solve system | `\` | `x = A \ b` |
| Function handle | `@(x)` | `f = @(x) x.^2` |
| Plot | `plot(x,y)` | `plot(t,sin(t))` |

Always distinguish **matrix operations** from **element-wise operations**. For example, `A^2` is matrix power, while `A.^2` squares each entry.
