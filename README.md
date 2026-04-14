# Ujkani-Complex-Matrix-Formula
A new method for solving complex matrices developed by Ilir Ujkani.
# The Ujkani Formula

<img width="1887" height="406" alt="Complex Matrix Formula" src="https://github.com/user-attachments/assets/6b750f6b-bd52-45ed-bcf1-ab01748ff695" />

## Overview
This repository presents the **Ujkani Formula**, a novel mathematical approach for solving complex matrices, developed by **Ilir Ujkani**, Electrical Engineer.

## The Problem
Solving complex matrices $A \cdot X = B$ typically requires expanding the matrix into a real-block format, which doubles the dimensions and increases computational overhead.

## The Solution: The Ujkani Formula
The formula provides a direct path to the solution:

=IFERROR(BYROW(TRANSPOSE(WRAPROWS(LET(mat, A2:J11, re, MAP(mat, LAMBDA(a, IMREAL(a))), im, MAP(mat, LAMBDA(a, IMAGINARY(a))), MMULT(MINVERSE(HSTACK(VSTACK(re, im), VSTACK(-im, re))), VSTACK(MAP(L2:L11, LAMBDA(a, IMREAL(a))), MAP(L2:L11, LAMBDA(a, IMAGINARY(a)))))), ROWS(A2:J11))), LAMBDA(a, COMPLEX(TAKE(a,, 1), TAKE(a,, -1)))), "Singuluar Matrix")

## Key Benefits
- **Direct Computation:** Avoids the need for massive block-matrix expansions.
- **Efficiency:** Ideal for electrical engineering applications and signal processing.
- **Implementation:** Can be easily translated into Python, MATLAB, or Excel Lambda functions.

## Author
**Ilir Ujkani** - Electrical Engineer
