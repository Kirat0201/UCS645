# UCS645 – LAB 1

## Question 1: DAXPY Loop using OpenMP

This experiment evaluates the performance of the DAXPY operation:

X[i] = a * X[i] + Y[i]

### Implementation
- Language: C++
- Parallelization: OpenMP
- Vector size: 2^16
- Threads tested: 2, 4, 8, 16

### Observation
Execution time increases with increasing number of threads due to
parallel overhead dominating computation for small problem size.

### Files
- daxpy_experiment.ipynb : Experiment and graph
