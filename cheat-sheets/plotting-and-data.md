# MATLAB Plotting and Data Cheat Sheet

## Basic plots

```matlab
x = linspace(0, 2*pi, 200);
y1 = sin(x);
y2 = cos(x);
plot(x, y1, 'LineWidth', 1.5);
hold on;
plot(x, y2, '--', 'LineWidth', 1.5);
grid on;
xlabel('x (radians)');
ylabel('Amplitude');
title('Sine and cosine');
legend('sin(x)', 'cos(x)', 'Location', 'best');
```

Use `subplot(m,n,p)` for older releases or `tiledlayout` and `nexttile` for newer layouts. Use `xlim`, `ylim`, `axis equal`, and `axis tight` to control the view. Use `exportgraphics(gcf, 'figure.png', 'Resolution', 150)` to save a reproducible image.

## Common chart types

| Purpose | Function |
|---|---|
| Line series | `plot` |
| Scatter relationship | `scatter` |
| Distribution | `histogram` |
| Group comparison | `boxchart` or `boxplot` |
| Matrix image | `imagesc` |
| Surface | `surf` |
| Contours | `contour` |
| Error bars | `errorbar` |

## Tables and files

```matlab
T = readtable('measurements.csv');
writetable(T, 'clean_measurements.csv');
data = readmatrix('numeric_data.csv');
text = readlines('notes.txt');
```

Inspect imported data with `head(T)`, `summary(T)`, `T.Properties.VariableNames`, and `ismissing(T)`. Parse dates explicitly with `datetime` and document the input format.

## Figure quality checklist

Use descriptive axis labels with units, a title that states the subject, a legend only when it adds information, readable tick labels, and consistent line widths. Avoid relying only on color to distinguish series. Save the data and code needed to reproduce a figure.
