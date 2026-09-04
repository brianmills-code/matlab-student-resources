# Practice Set 01: Foundations

## Problems

1. Create a vector containing the integers from 1 through 20 and calculate its sum, mean, and standard deviation.
2. Given `A = [2 -1 4; 0 3 5; 1 2 -2]`, select the second row and third column, then calculate `det(A)`.
3. Generate 200 points from 0 to `2*pi`, plot `sin(x)` and `cos(x)` on the same axes, and include a legend.
4. Write a function that converts Celsius to Fahrenheit and validates that the input is finite.
5. Approximate the integral of `x.^2` from 0 to 3 using the trapezoidal rule, then compare it with the exact value.

## Extension challenge

Create a script that reads a vector of measurements, removes values outside two standard deviations of the mean, and plots the original and filtered data. Explain the choice of threshold in comments.

## Self-check

A strong solution should use vectorized operations where they improve clarity, label every plot, and include at least one assertion for input validation.
