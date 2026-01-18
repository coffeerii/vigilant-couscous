# Automated Linear System Solver
## Application Overview
A web-based tool that automatically transforms an augmented matrix into its Reduced Row Echelon Form (RREF). It serves both as a functional calculator and an educational aid by breaking down complex matrix manipulations into individual, understandable steps.
## The Gaussian Elimination Algorithm
The application implements a systematic version of Gaussian Elimination to transform any input matrix into its unique **Reduced Row Echelon Form (RREF)**.
### Phase 1: Forward Elimination (REF)
The goal of this phase is to reach *Row Echelon Form (REF)*, creating a "staircase" pattern of leading ones.
**Pivot Selection:** The algorithm searches for the first non-zero entry in the current column (the pivot column).
**Row Swapping (Type I):** If the entry in the current row is zero, the algorithm swaps it with a lower row that has a non-zero entry in that column.
**Normalization (Type II):** The pivot row is multiplied by a scalar to ensure the leading entry becomes exactly 1.
**Elimination Below (Type III):** Multiples of the pivot row are added to all rows below it to create zeros in the rest of the column.
### Phase 2: Backward Substitution (RREF)
To reach *Reduced Row Echelon Form (RREF)*, the algorithm ensures that each column containing a leading one has zeros in every other position.
**Elimination Above (Type III):** Starting from the last pivot and moving upwards, the algorithm adds multiples of the pivot row to the rows above it to zero out those entries.
**Final Cleanup:** Any values extremely close to zero (due to floating-point precision) are cleaned to appear as exactly 0 for the user.
## Technical Features
### Mathematical Foundation
The solver is built upon the three **Elementary Row Operations** used within the **Gaussian Elimination** framework defined in linear algebra:
**Type I (Eij):** Swapping row i and row j to ensure a non-zero element occupies the pivot position.
**Type II (Ej()):** Multiplying row i by a nonzero scalar  to normalize the leading entry to 1.
**Type III (Eij()):** Replacing row i by adding  times row j to it, effectively zeroing out other entries in the pivot column.
### Data Handling and UI
The application features a dark-themed interface with a unified purple color scheme (rgb(113, 97, 138)) for all borders and highlights.
**Dynamic Generation:** Users can specify a matrix size up to a maximum of 10 rows and 10 columns.
**Input Instructions:** A dedicated instruction box guides users on entering coefficients, using decimals, and handling negative signs.
**Randomization Logic:** The "Randomize Values" button includes algorithms to generate not only unique solutions but also inconsistent systems and systems with infinitely many solutions.
**Augmented Visualization:** The input grid and all result matrices feature a noticeable thick vertical bar to separate variable coefficients from the constant terms.


