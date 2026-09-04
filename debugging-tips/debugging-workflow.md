# MATLAB Debugging Workflow

1. Reproduce the problem with the smallest input that still fails.
2. Read the complete error message and inspect the line number.
3. Check sizes with `size`, classes with `class`, and values with `whos` or `disp`.
4. Use a breakpoint or `dbstop if error` to inspect variables before failure.
5. Add `assert` statements for assumptions such as dimensions, finiteness, and non-empty input.
6. Test boundary cases: empty vectors, one-element vectors, zeros, negative values, and mismatched dimensions.
7. Remove temporary prints only after the corrected behavior has been verified.

Common causes include one-based indexing, using `*` where `.*` was intended, row-versus-column orientation, and scripts that depend on variables left in the workspace.
