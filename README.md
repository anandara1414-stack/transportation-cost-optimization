# Transportation Cost Optimization
Minimizing factory-to-store shipping cost using Least Cost, MODI, and linear programming for a final exam project in a Mathematical Programming course.

## Problem
Three factories supply five stores. The goal is to minimize the total
shipping cost while meeting every store's demand and staying within
each factory's capacity.

- Factory capacity: 50, 100, 150 units
- Store demand: 100, 70, 50, 40, 40 units
- Total supply = total demand = 300 units (balanced problem)

Shipping cost per unit:

| | Store 1 | Store 2 | Store 3 | Store 4 | Store 5 |
|---|---|---|---|---|---|
| Factory 1 | 1 | 9 | 13 | 36 | 51 |
| Factory 2 | 24 | 12 | 16 | 20 | 1 |
| Factory 3 | 14 | 33 | 1 | 23 | 26 |

## Method
1. **Least Cost method**: builds an initial allocation by always using
   the cheapest available route first. Total cost: 2,810.
2. **MODI (UV) method**: checks whether any unused route could lower the
   cost, and improves the allocation. One iteration reached the optimum.
3. **Linear programming (SciPy `linprog`)**: used to verify the result.

## Result
Total cost reduced from **2,810 to 2,700**. The manual MODI result and
the `linprog` solution both give 2,700.

| | Store 1 | Store 2 | Store 3 | Store 4 | Store 5 |
|---|---|---|---|---|---|
| Factory 1 | 40 | 10 | 0 | 0 | 0 |
| Factory 2 | 0 | 60 | 0 | 0 | 40 |
| Factory 3 | 60 | 0 | 50 | 40 | 0 |

## Files
- `Kode_Python.ipynb`: Python code (Least Cost and linprog)
- `Analytical Handwriting.pdf`: handwritten Least Cost and MODI calculation

## Tools
Python, NumPy, SciPy
