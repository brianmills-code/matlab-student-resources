# MATLAB Numerical Methods Guide

Numerical methods approximate mathematical quantities when an exact symbolic solution is unavailable, inconvenient, or too expensive. A responsible numerical result includes the method, inputs, step size or tolerance, stopping rule, and an error or convergence check.

## Method selection

| Task | Suitable first method | MATLAB tool |
|---|---|---|
| Scalar root on a bracket | Bisection or a safeguarded method | `fzero` |
| Scalar minimization on an interval | Bounded search | `fminbnd` |
| Definite integral | Adaptive quadrature | `integral` |
| Derivative from samples | Finite differences | `gradient`, `diff` |
| Values between known samples | Interpolation | `interp1` |
| Linear system | Factorization-based solve | `A\\b` |
| ODE initial-value problem | Adaptive time integration | `ode45` |

## Root finding

For a continuous function with a sign change on `[a,b]`, bisection repeatedly halves the interval. It is slower than some methods but easy to reason about and robust when the bracket is valid.

```matlab
f = @(x) cos(x) - x;
left = 0; right = 1; tolerance = 1e-10;
assert(f(left)*f(right) < 0, 'Interval must bracket a root.');

for k = 1:100
    midpoint = (left + right)/2;
    if abs(f(midpoint)) < tolerance || (right-left)/2 < tolerance
        break
    elseif f(left)*f(midpoint) < 0
        right = midpoint;
    else
        left = midpoint;
    end
end
fprintf('root = %.12f, residual = %.3e\n', midpoint, abs(f(midpoint)));
```

`fzero` is convenient for a scalar root, but still provide a sensible initial guess or bracket and inspect the returned exit information.

## Numerical integration

```matlab
f = @(x) exp(-x.^2);
value = integral(f, 0, 1);
```

Check the result by reducing tolerances or comparing with a known special case. For sampled data, `trapz(x,y)` applies the trapezoidal rule; use an explicit `x` vector when spacing is not one.

## Differentiation

For sampled values `y` at coordinates `x`, `gradient(y,x)` estimates the derivative while preserving the array size. Differentiation amplifies noise, so inspect the result and consider smoothing only when the smoothing choice is justified and documented.

```matlab
x = linspace(0, 2*pi, 200);
y = sin(x);
dy = gradient(y, x);
maxError = max(abs(dy - cos(x)));
```

## Interpolation

```matlab
xKnown = [0 1 2 3];
yKnown = [0 2 1 4];
xQuery = linspace(0, 3, 100);
yLinear = interp1(xKnown, yKnown, xQuery, 'linear');
ySpline = interp1(xKnown, yKnown, xQuery, 'spline');
```

Do not extrapolate without explaining the assumption. Compare interpolation methods near sharp changes and avoid using a high-order method merely because it looks smoother.

## Convergence and error

Run the same method with successively smaller step sizes or tighter tolerances. Record the result and estimated error in a table. A convergent method should approach a stable value; if it oscillates or diverges, investigate stability, conditioning, boundary conditions, and implementation errors.

For linear systems, inspect the residual rather than only the solution:

```matlab
x = A\\b;
residualNorm = norm(A*x - b, inf);
assert(residualNorm < 1e-10, 'Residual is too large.');
```

## Numerical-method checklist

State the mathematical model, define units, validate inputs, choose a method appropriate to the problem, record tolerances and stopping criteria, check residuals or conservation laws, perform a convergence study, and report limitations. Never hide a failed convergence or an unstable parameter choice.
