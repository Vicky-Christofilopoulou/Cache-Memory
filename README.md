# Cache-memory
The task is to design a "family" of three microprocessors that differ in performance and cost for the same computational task, as a project in "Computer Architecture 2" course.

The implementation and the results are explained on this pdf. [ReadMe.pdf](https://github.com/Vicky-Christofilopoulou/Cache-memory/files/14550329/ReadMe.pdf)

# Description 
The computational task involves multiplying two square matrices of order n (i.e., dimensions nxn) and searching for a number in the final product matrix of the two initial matrices. The elements of the initial matrices are small signed integers with values in the range [-64, +63]. Your program should perform two separate steps:

1. Given two square matrices X and Y of dimensions nxn, calculate their product in the matrix Z (the elements of the matrices can be of any byte size). Consider the possibility of overflow during the computation of Z and terminate if it occurs.
2. Search for any integer K in matrix Z and store in variable C the number of occurrences.

The three processors share a common design in the core of their pipeline: they have a 2-bit branch predictor with a 5-bit BHT, and branch resolution occurs in the EX stage, along with a full hazard unit with forwarding. They differ in the memory system.

# The first processor (codename: Qatar) 
A cost-effective version of the family with the minimum possible cost, meaning it does not use a cache. Access to the main memory takes 40 clock cycles. The cost of the processor is 20 euros, and its clock speed is 500 MHz.

# The second processor (codename: Portugal)
A mid-range version of the family that uses only one level of cache (L1) for both instructions and data. Access to main memory on this processor also takes 40 cycles. The instruction/program (L1 program cache in QtMips terminology) and data (L1 data cache) caches have sizes of 4, 8, or 16 KB each (same size for both). They can also contain 4, 8, or 16 words per block (same choices for both). You can choose any associativity you desire (again, the same for both L1 caches), and the replacement policy should be LRU. In L1 data cache, the write policy is write back, and the allocation policy is write allocate. The cost of this processor is 20, 25, or 30 euros higher than the previous one if the L1 caches have sizes of 4, 8, or 16 KB each, respectively. The clock speed is 500 MHz if the associativity is 1 (direct mapped), but it decreases by 10 MHz for each doubling of associativity.

# The third processor (codename: Argentina)
An advanced version of the family that uses two levels of cache (separate L1 for instructions and data, and a unified L2). Access to main memory on this processor also takes 40 cycles, while accessing the L2 cache takes 5 cycles. The L1 caches are the same as the previous processor (you will keep the design you arrived at, including cost and clock speed). The L2 cache has a size of 16, 32, or 64 KB, and it has the same block size as the L1 caches of the previous processor. You can choose any associativity for the L2 (it can be different from the L1). The write policy and allocation policy should be write back and write allocate, respectively, with LRU replacement. The cost of this processor is 50, 75, or 100 euros higher than the previous one if the L2 cache has a size of 16, 32, or 64 KB, respectively. The clock speed is the same as that of the previous processor.

## Contributors of the project :
* [Eleni Feslian](https://github.com/sdi2000204)
* [Zannis Vidalis](https://github.com/sdi2000022)
