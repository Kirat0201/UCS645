# LAB 1 – Question 3  
## Parallel Computation of π using OpenMP

This experiment computes an approximate value of π using numerical
integration and evaluates the effect of multithreading on execution time.

---

## Problem Description

The value of π is calculated using the integral:

π = ∫₀¹ 4 / (1 + x²) dx

This integral is approximated using the rectangle (Riemann sum) method.
The interval [0, 1] is divided into a large number of steps, and the sum
of rectangle areas is computed.

---

## Parallelization Approach

- Each iteration of the summation loop is **independent**
- The loop is parallelized using **OpenMP**
- A `reduction(+:sum)` clause is used to avoid race conditions when
  accumulating partial results from multiple threads

Each thread computes a partial sum, and OpenMP safely combines them
at the end of the loop.

---

## Implementation Details

- Language: C++
- Parallelization: OpenMP
- Method: Parallel `for` loop with reduction
- Inputs:
  - Number of threads
  - Number of integration steps

The program outputs:
- The computed value of π
- The execution time

Python is used to:
- Run the program with different thread counts
- Collect timing data
- Plot execution time vs number of threads

---

## Observations

- The computed value of π is accurate (≈ 3.14159)
- Execution time decreases initially with increased threads
- Beyond a certain number of threads, performance does not improve and
  may slightly degrade

This behavior occurs due to:
- Thread creation and synchronization overhead
- Limited CPU cores available on Google Colab
- Memory bandwidth and scheduling constraints

---

## Conclusion

The experiment demonstrates that numerical integration is well-suited
for parallel execution when reduction is used correctly. However,
increasing the number of threads beyond the available hardware
capabilities does not guarantee better performance. Optimal performance
is achieved when the number of threads is close to the number of
physical cores.

---

## Files

- `Q3_pi_experiment.ipynb` – Python driver for execution and plotting  
- `README.md` – Description and analysis of the experiment

