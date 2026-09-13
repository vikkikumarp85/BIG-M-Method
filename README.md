Big-M Method – Product Mix Optimization

Project Description

This project implements the Big-M Simplex Method in Python to solve a constrained Linear Programming Problem (LPP).

The selected case study is a product-mix optimization problem in which a company decides how many units of two products to manufacture in order to maximize profit while satisfying resource, minimum-requirement, and equality constraints.

The program performs the simplex iterations computationally and reports the optimal decision-variable values and maximum objective value.

Problem Statement

A company manufactures two products:

x1 = units of Product A

x2 = units of Product B

Profit per unit:

Product A = ₹40

Product B = ₹30

The production plan must satisfy:

2x1 + x2 <= 40

x1 + 2x2 >= 20

x1 + x2 = 30

x1, x2 >= 0

Objective

Maximize:

Z = 40x1 + 30x2

Standard Form

For the <= constraint, add a slack variable:

2x1 + x2 + s1 = 40

For the >= constraint, subtract a surplus variable and add an artificial variable:

x1 + 2x2 - s2 + a2 = 20

For the equality constraint, add an artificial variable:

x1 + x2 + a3 = 30

Therefore, the Big-M objective is:

Z = 40x1 + 30x2 - M a2 - M a3

where M is a very large positive number.

Method

The implementation:

Builds the initial simplex tableau.

Adds slack, surplus, and artificial variables according to each constraint.

Applies the Big-M penalty to artificial variables.

Selects entering variables using the objective row.

Uses the minimum-ratio test to select leaving variables.

Performs pivot operations.

Repeats until no improving variable remains.

Checks that artificial variables are zero.

Reports the optimal solution.

Requirements

Python 3.x and NumPy.

Install NumPy if required:

pip install numpy

How to Run

python big_m_method.py

Expected Output

Big-M Simplex Method
Initial basic variables: s1, a2, a3
Iteration 1: Enter x2, Leave a2
Iteration 2: Enter x1, Leave s1
Iteration 3: Enter s2, Leave a3

Optimal Solution
x1 = 10.00
x2 = 20.00
Maximum Profit = 1000.00

Final Result

Product A (x1) = 10 units

Product B (x2) = 20 units

Maximum profit = ₹1000

The artificial variables become zero, confirming that the original LPP is feasible.

Files

big_m_method.py – Python implementation of the Big-M Simplex Method.

README.md – Project description, formulation, method, and execution instructions.

Big_M_Method_Report.pdf – Detailed assignment report.

Conclusion

The Big-M Simplex Method successfully solves the selected product-mix LPP. The optimal production plan is to manufacture 10 units of Product A and 20 units of Product B, giving a maximum profit of ₹1000.
