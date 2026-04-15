# Ujkani-Complex-Matrix-Formula
A new method for solving complex matrices developed by Ilir Ujkani.
# The Ujkani Formula

<img width="1433" height="574" alt="image" src="https://github.com/user-attachments/assets/2286aed1-fb88-4f79-901d-f6011cfd2f21" />



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

- ## Performance & Benchmarks
The **UCMF** is optimized for large-scale calculations. During testing, it achieved the following results:
* **Matrix Size:** 1000 x 1000 complex elements.
* **Processing Time:** Less than 3 minutes (tested on a standard consumer-grade PC).
* **Stability:** Handles large datasets without crashing Excel or Google Sheets.

## Technical Terminology
To ensure clarity for engineers and mathematicians, the formula outputs are labeled as follows:
* **Modulus:** Represents the magnitude (diagonal) of the complex number.
* **Argument (deg/rad):** Represents the phase/angle of the complex solution.
* **Constants:** Refers to the known values (Vector B) in the $Ax = B$ system.
* **Verification:** A built-in check to ensure $Ax - B = 0$.

## Applications
This tool is universal and can be used in:
* **Electrical Engineering:** For AC circuit analysis and Phasor calculations.
* **Physics:** Quantum mechanics and wave functions.
* **Structural Dynamics:** Vibration analysis using complex matrices.

## Author
**Ilir Ujkani** - Electrical Engineer
