#LAB 1 - Question 2 

##Parallel and Distributed Computing 

This experiment implements parallel matrix multiplication using two approaches: 

1. 1D Threading - Parallelizing only the outer loop
2. 2D Threading - Parallelizing outer two loops using collapse

##Observation 
The observation time decreases significantly when increasing threads from 2 to 4 due to improved parallelism. However, beyond 4 threads, the execution time increases for both 1D and 2D threading approaches. This behavior occurs because matrix multiplication is memory-bound, and increasing the number of threads leads to memory bandwidth saturation, cache contention, and thread management overhead. As a result, additional threads do not improve performance and may degrade it. The performance difference between 1D and 2D threading is minimal due to memory bottlenecks dominating execution time.

##Files 
-Q2_matrix_experiment.ipynb
